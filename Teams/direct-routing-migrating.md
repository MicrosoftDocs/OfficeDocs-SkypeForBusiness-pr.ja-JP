---
title: ダイレクト ルーティングに移行する
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
appliesto:
- Microsoft Teams
description: 移行する直接ルーティングでは、Skype のオンライン ビジネスとチームの構成の分析観点の必要なものについて説明します。
ms.openlocfilehash: 995883bd6f62607cd156f82e2c86255bab182303
ms.sourcegitcommit: ee3f79ce1b6da0885e1096f9fba894bcff1814da
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/25/2019
ms.locfileid: "33298645"
---
# <a name="migrate-to-direct-routing"></a>ダイレクト ルーティングに移行する

この資料では、直接ルーティングするのには、Skype のオンライン ビジネスおよびマイクロソフトのチーム構成の観点からの移行に必要なものについて説明します。 この資料では、次からの移行について説明します。 
 
- Office 365 電話通話での計画がチームとのオンライン ビジネスの Skype) 
- Office 365 電話システムに Skype のオンライン ビジネスの Skype) ビジネス サーバーの PSTN への接続を設置  
- クラウド コネクタ エディション (ビジネス オンラインの Skype) を使用して、PSTN への接続をオンプレミスと office 365 の電話システム

  
構成手順では、ほかの構成も必要セッション ボーダー コント ローラー (SBC) に新しいルートへの呼び出しをルーティングします。 このドキュメントの範囲外です。 詳細については、SBC のベンダーのマニュアルを参照してください。  

## <a name="user-provisioning-end-state-for-various-pstn-connectivity-options"></a>ユーザー プロビジョニングの PSTN 接続のさまざまなオプションの終了状態 

次の表は、ユーザーが Office 365 の電話システムで選択した PSTN 接続オプションを提供する最終状態を示しています。 ボイスに関連する属性のみが表示されます。

|ユーザー オブジェクトの属性 |通話プランと電話システム|システム設置の Skype 経由で PSTN への接続の電話ビジネス サーバー|オンプレミスとクラウドのコネクタ経由で PSTN への接続システムを電話します。|システム設置に直接ルーティングを使用して PSTN への接続に電話します。|
|---|---|---|---|---|
|クライアント|Skype ビジネスまたはチームの |Skype for Business |Skype for Business |Teams|
|ライセンス|Skype ビジネス オンライン</br>2 を計画します。</br></br>MCOProfessional または MCOSTANDARD)</br></br></br>電話システム (MCOEV)</br></br></br>通話プラン</br>Teams|Skype ビジネス オンライン プラン 2 MCOProfessional (MCOSTANDARD)</br></br></br>電話システム (MCOEV)|Skype ビジネス オンライン プラン 2 MCOProfessional (MCOSTANDARD)</br></br></br>電話システム (MCOEV)|Skype ビジネス オンライン プラン 2 (MCOProfessional または MCOSTANDARD</br></br></br>電話システム (MCOEV)</br></br>Teams|
OnPremLineURI |N/A|施設内の電話番号を同期する必要があります AD。 |Azure Active directory またはオンプレミスの Active Directory では、電話番号を管理できます。|Azure Active directory またはオンプレミスの Active Directory では、電話番号を管理できます。 ただし、組織のビジネスの Skype を設置の場合、数は、オンプレミスの Active Directory から同期する必要があります。|
|LineURI|PSTN の呼び出しの電話番号|OnPremLineURI パラメーターから自動的に設定します。|OnPremLineURI パラメーターから自動的に設定します。|OnPremLineURI パラメーターから自動的に設定します。|
|EnterpriseVoiceEnabled|True|True|True|True|
|HostedVoiceMail |True|True|True|True|
|VoicePolicy|BusinessVoice|HybridVoice|HybridVoice|HybridVoice|
|HostedVoiceMailPolicy |BusinessVoice|BusinessVoice|BusinessVoice|BusinessVoice|
|VoiceRoutingPolicy|値を持つ|値を持つ|値を持つ|N/A|
|OnlineVoiceRoutingPolicy|$Null|$Null|$Null|値を持つ|
|TeamsUpgradePolicy<sup>1</sup>|TeamsOnly、SfBOnly または諸島|$Null|$Null|諸島または TeamsOnly|
|TeamsInterPolicy<sup>2</sup></br>CallingDefaultClient – は、以下の注を参照してください。|チームまたはデバイス |デバイス|デバイス|Teams|
|TeamsCallingPolicy</br>AllowPrivateCalling|True|該当なし|該当なし|True|
|TeamsCallingPolicy</br>AllowGroupCalling|True|該当なし|該当なし|True|
||||||

<sup>1</sup>TeamsUpgradePolicy の右のモードを選択するかは、シナリオによって異なります。 [移行と相互運用性の組織のためのガイダンス](migration-interop-guidance-for-teams-with-skype.md)は、チームと、ビジネス用の Skype を使用して別のモードで音声の経験についてお読みください。

<sup>2</sup>以前に発表された (第 3 四半期の最後のターゲット)、TeamsInteropPolicy から退職して TeamsUpgradePolicy にその機能が統合されています。 相互運用と移行は、「共存モード」を使用して、現在利用可能な TeamsUpgradePolicy、によって管理されます。 ユーザーのモードの選択では、着信呼び出しとチャットの両方のルーティングとユーザーのチャットや通話を開始したり、会議をスケジュールするどのクライアントにします。 TeamsInteropPolicy から退職するときにも、phaseout の中に TeamsUpgradePolicy と同時に設定する必要があります。  

この取り組みの一環として、マイクロソフトは共存モードに基づいて、新しい管理モデルを反映するように、「マイクロソフトのチーム管理センター」(現代のポータルとも呼ばれます) を最近更新しました。 現代のポータルを構成する TeamsUpgradePolicy はこれで自動的に設定も TeamsInteropPolicy に一貫性のある値は、TeamsInteropPolicy が不要になったユーザー インターフェイスで公開されているようです。 ただし、PowerShell を使用して管理者が TeamsUpgradePolicy および TeamsInteropPolicy に適切なルーティングを確保する設定も必要があります。 TeamsUpgradePolicy への移行が完了した後、不要になった必要がありますも TeamsInteropPolicy を設定します。

詳細については、[移行と相互運用性チームと、ビジネス用の Skype を使用する組織向けのガイダンス](migration-interop-guidance-for-teams-with-skype.md)を参照してください。

## <a name="migrating-from-calling-plans"></a>通話プランからの移行

プランの呼び出しからの移行の詳細についてを参照してください。

- [通話プランの設定](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)
- [セット CsOnlineVoice ユーザー](https://docs.microsoft.com/powershell/module/skype/Set-CsOnlineVoiceUser?view=skype-ps)
- [Get CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/get-csonlinelislocation?view=skype-ps)  
 
 
Previouslycconfigured ライセンス プランの情報を次のように削除することをお勧めします。
 
```
$companyname = “contoso” 
$lic1 = $companyname + “:MCOPSTN1” 
$lic2 = $companyname + “:MCOPSTN2” 
Set-MsolUserLicense -UserPrincipalName <UPN> -RemoveLicenses $lic1 
Set-MsolUserLicense -UserPrincipalName <UPN> -RemoveLicenses $lic2 
```
## <a name="migrating-from-office-365-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>ビジネス サーバーの Office 365 の電話システムから Skype で設置した PSTN 接続に移行します。

ビジネス サーバーの Skype で設置した PSTN 接続の電話システムからの移行に関する詳細については、以下を参照してください。

- [計画](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity)
- [展開します。](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-users-for-phone-system) 

ルーティング情報を次のように既に構成済みの音声を削除することをお勧めします。

```
Grant-CsVoiceRoutingPolicy -PolicyName $NULL -Identity <UPN> 
```
## <a name="migrating-from-office-365-phone-system-with-on-premises-pstn-connectivity-via-cloud-connector-edition"></a>Office 365 電話システムからの移行は、クラウド コネクタのエディションを使用して PSTN 接続を設置 

クラウド コネクタ経由の PSTN への接続を設置と電話システムからの移行の詳細については、以下を参照してください。

- [計画](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-skype-for-business-cloud-connector-edition)  
- [展開します。](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-users-for-phone-system)
- [ユーザー構成](https://docs.microsoft.com/powershell/module/skype/set-csuserpstnsettings?view=skype-ps) 

ルーティング情報を次のように既に構成済みの音声を削除することをお勧めします。
 
```
Grant-CsVoiceRoutingPolicy -PolicyName $NULL -Identity <UPN> 
Set-CsUserPstnSettings -Identity <UPN> -AllowInternationalCalls $false -HybridPSTNSite $null 
```


## <a name="related-links"></a>関連リンク

[Teams を Skype for Business と一緒に使用する組織向けの移行と相互運用に関するガイダンス](migration-interop-guidance-for-teams-with-skype.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy)

[Get-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsTeamsUpgradePolicy)

[新しい-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsTeamsUpgradePolicy)

[削除 CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsTeamsUpgradePolicy)

[セット CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsUpgradePolicy)

[Get-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTeamsUpgradeConfiguration)

[Set-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsUpgradeConfiguration)

