---
title: ダイレクト ルーティングに移行する
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Skype for Business Online および Teams の構成パースペクティブからダイレクト ルーティングに移行するために必要な作業について説明します。
ms.openlocfilehash: de211dfae9bf2fc20a2cd367687e0fd7c5779a5f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122201"
---
# <a name="migrate-to-direct-routing"></a>ダイレクト ルーティングに移行する

この記事では、Skype for Business Online および Microsoft Teams の構成パースペクティブからダイレクト ルーティングに移行するために必要な作業について説明します。 この記事では、次の環境からの移行について説明します。 
 
- 電話システムプランの使用 (Teams および Skype for Business Online の場合) 
- 電話システムのオンプレミス PSTN 接続を使用したSkype for Business Server (Skype for Business Online の場合)  
- 電話システム Cloud Connector Edition を使用したオンプレミス PSTN 接続の使用 (Skype for Business Online の場合)


これらの構成手順に加えて、通話を新しいルートへルーティングするために、セッション ボーダー コントローラー (SBC) 上での構成も必要です。 これは、このドキュメントの範囲外です。 詳細については、SBC 業者の資料を参照してください。  

## <a name="user-provisioning-end-state-for-various-pstn-connectivity-options"></a>さまざまな PSTN 接続オプションのユーザー プロビジョニングの最終状態 

次の表は、選択した PSTN 接続オプションに対してプロビジョニングされたユーザーの終了状態を示電話システム。 音声に関連する属性だけが表示されています。

|ユーザー オブジェクトの属性 |通話プランが設定された電話システム|Skype for Business Server 経由のオンプレミス PSTN 接続による電話システム|クラウド コネクタ経由のオンプレミス PSTN 接続による電話システム|ダイレクト ルーティング経由のオンプレミス PSTN 接続による電話システム|
|---|---|---|---|---|
|クライアント|Skype for Business または Teams |Skype for Business |Skype for Business |Teams では、|
|ライセンス|Skype Business Online</br>プラン 2</br></br>(MCOProfessional または MCOSTANDARD)</br></br></br>電話システム (MCOEV)</br></br></br>通話プラン</br>Teams|Skype Business Online プラン 2 (MCOProfessional または MCOSTANDARD)</br></br></br>電話システム (MCOEV)|Skype Business Online プラン 2 (MCOProfessional または MCOSTANDARD)</br></br></br>電話システム (MCOEV)|Skype Business Online プラン 2 (MCOProfessional または MCOSTANDARD)</br></br></br>電話システム (MCOEV)</br></br>Teams|
OnPremLineURI |該当なし|電話番号は、オンプレミスの AD から同期する必要があります。 |電話番号は、オンプレミスの Active Directory または Azure Active Directory のいずれかで管理できます。|電話番号は、オンプレミスの Active Directory または Azure Active Directory のいずれかで管理できます。 ただし、組織がオンプレミスの Skype for Business を使用している場合は、番号はオンプレミスの Active Directory から同期する必要があります。|
|LineURI|PSTN 発信側電話番号|OnPremLineURI パラメーターから自動的に設定される|OnPremLineURI パラメーターから自動的に設定される|OnPremLineURI パラメーターから自動的に設定される|
|EnterpriseVoiceEnabled|正解|True|True|正解|
|HostedVoiceMail |正解|True|True|正解|
|VoicePolicy|BusinessVoice|HybridVoice|HybridVoice|HybridVoice|
|HostedVoiceMailPolicy |BusinessVoice|BusinessVoice|BusinessVoice|BusinessVoice|
|VoiceRoutingPolicy|値がある|値がある|値がある|該当なし|
|OnlineVoiceRoutingPolicy|$Null|$Null|$Null|値がある|
|TeamsUpgradePolicy<sup>1</sup>|TeamsOnly, SfBOnly|$Null|$Null|TeamsOnly|
|TeamsCallingPolicy</br>AllowPrivateCalling|True|該当なし|該当なし|True|
|TeamsCallingPolicy</br>AllowGroupCalling|True|該当なし|該当なし|True|
||||||

<sup>1</sup> TeamsUpgradePolicy の適切なモードの選択は、シナリオによって異なります。 異なるモードでの音声環境の詳細については、「[Teams を Skype for Business と一緒に使用する組織向けの移行と相互運用に関するガイダンス](migration-interop-guidance-for-teams-with-skype.md)」を参照してください。

Microsoft では、この取り組みとは別に、共存モードに基づく新しい管理モードを反映させるために Microsoft Teams 管理センター (モダン ポータルとも呼ばれます) を最近更新しました。 モダン ポータルでは、TeamsUpgradePolicy を構成することにより TeamsInteropPolicy も一貫性のある値に自動的に設定されため、TeamsInteropPolicy がユーザー インターフェイスに表示されなくなります。 ただし、PowerShell を使用している管理者は、適切なルーティングを確保するために、TeamsUpgradePolicy と TeamsInteropPolicy の両方を同時に設定する必要があります。 TeamsUpgradePolicy への移行が完了すると、TeamsInteropPolicy を設定する必要はなくなります。

詳細については、「[Teams を Skype for Business と一緒に使用する組織向けの移行と相互運用に関するガイダンス](migration-interop-guidance-for-teams-with-skype.md)」を参照してください。

## <a name="migrating-from-calling-plans"></a>通話プランからの移行

通話プランから移行の詳細については、次を参照してください。

- [通話プランの設定](/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)
- [Set-CsOnlineVoice ユーザー](/powershell/module/skype/Set-CsOnlineVoiceUser?view=skype-ps)
- [Get-CsOnlineLisLocation](/powershell/module/skype/get-csonlinelislocation?view=skype-ps)  
 
 
次を実行し、以前に構成したライセンス プラン情報を削除することをお勧めします。
 
```powershell
$companyname = “contoso” 
$lic1 = $companyname + “:MCOPSTN1” 
$lic2 = $companyname + “:MCOPSTN2” 
Set-MsolUserLicense -UserPrincipalName <UPN> -RemoveLicenses $lic1 
Set-MsolUserLicense -UserPrincipalName <UPN> -RemoveLicenses $lic2 
```
## <a name="migrating-from-office-365-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>Skype for Business Server のオンプレミス PSTN 接続による Office 365 電話システムからの移行

Skype for Business Server のオンプレミス PSTN 接続による電話システムからの移行の詳細については、次を参照してください。

- [計画](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity)
- [展開](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-users-for-phone-system) 

次を実行し、以前に構成した音声ルーティング情報を削除することをお勧めします。

```PowerShell
Grant-CsVoiceRoutingPolicy -PolicyName $NULL -Identity <UPN> 
```
> [!NOTE]
> グローバル CsVoiceRoutingPolicy が構成されている場合は、このグローバル ポリシーに関連付けられている PSTN 使用法をすべて削除してください。 

## <a name="migrating-from-office-365-phone-system-with-on-premises-pstn-connectivity-via-cloud-connector-edition"></a>クラウド コネクタ エディション経由のオンプレミス PSTN 接続による Office 365 電話システムからの移行 

> [!Important]
> Cloud Connector Edition は、2021 年 7 月 31 日に Skype for Businessされます。 組織が Teams にアップグレードしたら、直接ルーティング を使用してオンプレミスのテレフォニー ネットワークを Teams接続する方法[について説明します](direct-routing-landing-page.md)。

クラウド コネクタ エディション経由のオンプレミス PSTN 接続による電話システムからの移行の詳細については、次を参照してください。

- [計画](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-skype-for-business-cloud-connector-edition)  
- [展開](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-users-for-phone-system)
- [ユーザー構成](/powershell/module/skype/set-csuserpstnsettings?view=skype-ps) 

次を実行し、以前に構成した音声ルーティング情報を削除することをお勧めします。
 
```PowerShell
Grant-CsVoiceRoutingPolicy -PolicyName $NULL -Identity <UPN> 
Set-CsUserPstnSettings -Identity <UPN> -AllowInternationalCalls $false -HybridPSTNSite $null 
```


## <a name="related-links"></a>関連リンク

[Teams を Skype for Business と一緒に使用する組織向けの移行と相互運用に関するガイダンス](migration-interop-guidance-for-teams-with-skype.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy)

[Get-CsTeamsUpgradePolicy](/powershell/module/skype/Get-CsTeamsUpgradePolicy)

[New-CsTeamsUpgradePolicy](/powershell/module/skype/New-CsTeamsUpgradePolicy)

[Remove-CsTeamsUpgradePolicy](/powershell/module/skype/Remove-CsTeamsUpgradePolicy)

[Set-CsTeamsUpgradePolicy](/powershell/module/skype/Set-CsTeamsUpgradePolicy)

[Get-CsTeamsUpgradeConfiguration](/powershell/module/skype/Get-CsTeamsUpgradeConfiguration)

[Set-CsTeamsUpgradeConfiguration](/powershell/module/skype/Set-CsTeamsUpgradeConfiguration)