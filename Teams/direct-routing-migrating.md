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
- Teams_ITAdmin_Help
- M365-voice
appliesto:
- Microsoft Teams
description: Skype for Business Online と Teams の構成の観点から直接ルーティングに移行するために必要なものについて説明します。
ms.openlocfilehash: c9c8cafdf6e49dc127dee4cb76a92dae13b5c0b9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34290424"
---
# <a name="migrate-to-direct-routing"></a>ダイレクト ルーティングに移行する

この記事では、Skype for Business Online および Microsoft Teams の構成の観点から直接ルーティングに移行するために必要なものについて説明します。 この記事では、次の移行について説明します。 
 
- 通話プラン (Teams および Skype for Business Online の場合) が含まれる Office 365 の電話システム 
- Skype for Business Server のオンプレミスの PSTN 接続を使用した Office 365 の電話システム (Skype for Business Online)  
- Cloud Connector エディションを使用したオンプレミスの PSTN 接続搭載の Office 365 電話システム (Skype for Business Online)

  
この構成手順に加えて、セッションボーダーコントローラー (SBC) でも、新しいルートへの通話をルーティングするために構成が必要になります。 これは、このドキュメントの範囲外です。 詳細については、SBC ベンダーのドキュメントを参照してください。  

## <a name="user-provisioning-end-state-for-various-pstn-connectivity-options"></a>さまざまな PSTN 接続オプションのユーザープロビジョニングの終了状態 

次の表は、Office 365 Phone システムで、選んだ PSTN 接続オプション用にプロビジョニングされたユーザーの終了状態を示しています。 ボイスに関連する属性のみが表示されます。

|ユーザーオブジェクトの属性 |通話プランを使用した電話システム|Skype for Business Server を使用したオンプレミスの PSTN 接続を備えた電話システム|クラウドコネクタ経由のオンプレミスの PSTN 接続を備えた電話システム|ダイレクトルーティングによるオンプレミスの PSTN 接続を使用した電話システム|
|---|---|---|---|---|
|クライアント|Skype for Business または Teams |Skype for Business |Skype for Business |Teams|
|供与|Skype Business Online</br>プラン2</br></br>MCOProfessional または MCOPROFESSIONAL)</br></br></br>電話システム (MCOEV)</br></br></br>通話プラン</br>Teams|Skype Business Online プラン 2 (MCOProfessional または MCOPROFESSIONAL)</br></br></br>電話システム (MCOEV)|Skype Business Online プラン 2 (MCOProfessional または MCOPROFESSIONAL)</br></br></br>電話システム (MCOEV)|Skype Business Online プラン 2 (MCOProfessional または MCOPROFESSIONAL)</br></br></br>電話システム (MCOEV)</br></br>Teams|
OnPremLineURI |N/A|電話番号はオンプレミスの広告から同期されている必要があります。 |電話番号は、オンプレミスの Active Directory または Azure Active Directory のいずれかで管理できます。|電話番号は、オンプレミスの Active Directory または Azure Active Directory のいずれかで管理できます。 ただし、組織でオンプレミスの Skype for Business を使用している場合は、オンプレミスの Active Directory から電話番号を同期する必要があります。|
|LineURI|PSTN 通話の電話番号|OnPremLineURI パラメーターから自動的に設定する|OnPremLineURI パラメーターから自動的に設定する|OnPremLineURI パラメーターから自動的に設定する|
|EnterpriseVoiceEnabled|True|True|True|True|
|HostedVoiceMail |True|True|True|True|
|VoicePolicy|BusinessVoice|HybridVoice|HybridVoice|HybridVoice|
|HostedVoiceMailPolicy |BusinessVoice|BusinessVoice|BusinessVoice|BusinessVoice|
|VoiceRoutingPolicy|値があります|値があります|値があります|N/A|
|OnlineVoiceRoutingPolicy|$Null|$Null|$Null|値があります|
|TeamsUpgradePolicy<sup>1</sup>|TeamsOnly、Sfbのみ、または諸島|$Null|$Null|島々または TeamsOnly|
|TeamsInterPolicy<sup>2</sup></br>CallingDefaultClient –以下のメモをお読みください。|Teams または SfB |SfB|SfB|Teams|
|Teamスケール・ポリシー</br>AllowPrivateCalling|True|該当なし|該当なし|True|
|Teamスケール・ポリシー</br>AllowGroupCalling|True|該当なし|該当なし|True|
||||||

<sup>1</sup>TeamsUpgradePolicy の適切なモードの選択は、シナリオによって異なります。 [Skype For business でチームと共同作業を行う組織](migration-interop-guidance-for-teams-with-skype.md)では、さまざまなモードでの音声操作をお読みください。

<sup>2</sup>前に発表したように、TeamsInteropPolicy は廃止 (Q3 の最終版) になり、その機能は TeamsUpgradePolicy に統合されます。 相互運用と移行は、TeamsUpgradePolicy によって決定される "共存モード" によって管理されます。この機能は現在利用できます。 ユーザのモードの選択によって、着信通話とチャットの両方のルーティングが管理され、ユーザーがチャットを開始したり、会議を予約したりすることができます。 TeamsInteropPolicy は廃止されますが、phaseout 中に TeamsUpgradePolicy と並列で設定する必要があります。  

この取り組みの一環として、Microsoft は最近、"Microsoft Teams 管理センター" ("モダンポータル" とも呼ばれます) を更新して、共存モードに基づいた新しい管理モデルを反映させています。 モダンポータルでは、TeamsUpgradePolicy を自動的に TeamsInteropPolicy に設定することもできます。そのため、TeamsInteropPolicy はユーザーインターフェイスでは公開されなくなりました。 ただし、PowerShell を使用している管理者は、TeamsUpgradePolicy と TeamsInteropPolicy の両方を一緒に設定して、適切なルーティングを確保する必要があります。 TeamsUpgradePolicy への移行が完了すると、TeamsInteropPolicy を設定する必要がなくなります。

詳細については、「 [Skype For business で Teams を使用する組織向けの移行と相互運用性のガイダンス](migration-interop-guidance-for-teams-with-skype.md)」を参照してください。

## <a name="migrating-from-calling-plans"></a>通話プランから移行する

通話プランからの移行の詳細については、以下を参照してください。

- [通話プランの設定](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)
- [Set-CsOnlineVoice User](https://docs.microsoft.com/powershell/module/skype/Set-CsOnlineVoiceUser?view=skype-ps)
- [ダウンロード-Csonlin¥ Location](https://docs.microsoft.com/powershell/module/skype/get-csonlinelislocation?view=skype-ps)  
 
 
ここでは、前に説明したように、構成済みのライセンス計画の情報を削除することをお勧めします。
 
```
$companyname = “contoso” 
$lic1 = $companyname + “:MCOPSTN1” 
$lic2 = $companyname + “:MCOPSTN2” 
Set-MsolUserLicense -UserPrincipalName <UPN> -RemoveLicenses $lic1 
Set-MsolUserLicense -UserPrincipalName <UPN> -RemoveLicenses $lic2 
```
## <a name="migrating-from-office-365-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>Skype for Business Server のオンプレミスの PSTN 接続を使用して Office 365 Phone システムから移行する

Skype for Business Server のオンプレミスの PSTN 接続を使用して電話システムから移行する方法の詳細については、以下を参照してください。

- [計画](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity)
- [展開](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-users-for-phone-system) 

以前に構成された音声ルーティング情報は、次のように削除することをお勧めします。

```
Grant-CsVoiceRoutingPolicy -PolicyName $NULL -Identity <UPN> 
```
## <a name="migrating-from-office-365-phone-system-with-on-premises-pstn-connectivity-via-cloud-connector-edition"></a>Cloud Connector エディションを使用して、オンプレミスの PSTN 接続を使用して Office 365 Phone システムから移行する 

クラウドコネクタによるオンプレミスの PSTN 接続を使用した電話システムからの移行の詳細については、次を参照してください。

- [計画](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-skype-for-business-cloud-connector-edition)  
- [展開](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-users-for-phone-system)
- [ユーザー構成](https://docs.microsoft.com/powershell/module/skype/set-csuserpstnsettings?view=skype-ps) 

以前に構成された音声ルーティング情報は、次のように削除することをお勧めします。
 
```
Grant-CsVoiceRoutingPolicy -PolicyName $NULL -Identity <UPN> 
Set-CsUserPstnSettings -Identity <UPN> -AllowInternationalCalls $false -HybridPSTNSite $null 
```


## <a name="related-links"></a>関連リンク

[Teams を Skype for Business と一緒に使用する組織向けの移行と相互運用に関するガイダンス](migration-interop-guidance-for-teams-with-skype.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy)

[Get-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsTeamsUpgradePolicy)

[新規-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsTeamsUpgradePolicy)

[Remove-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsTeamsUpgradePolicy)

[Set-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsUpgradePolicy)

[Get-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTeamsUpgradeConfiguration)

[Set-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsUpgradeConfiguration)

