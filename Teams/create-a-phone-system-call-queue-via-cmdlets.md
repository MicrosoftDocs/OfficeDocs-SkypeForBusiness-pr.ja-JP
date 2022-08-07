---
title: コマンドレットを使用して呼び出しキューを作成する
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.callqueues.overview
- Phone System
- seo-marvel-apr2020
description: コマンドレットを使用して通話キューを構成する方法について説明します
ms.openlocfilehash: b2439bf6b71fc7381494030c326db88660fa5eaf
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2022
ms.locfileid: "67268802"
---
# <a name="create-a-call-queue-via-cmdlets"></a>コマンドレットを使用して呼び出しキューを作成する

## <a name="assumptions"></a>仮定

1. PowerShell がコンピューターにインストールされている
   - [Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)用にコンピューターを設定する
   - MSTeams モジュールがインストールされている

     ```powershell
     Install-Module -Name MicrosoftTeams -Force -AllowClobber
     ```

   - MSOnline モジュールがインストールされている

     ```powershell
     Install-Module -Name MSOnline -Force -AllowClobber
     ```

2. テナント管理権限を持っている
3. Microsoft Teams 電話を購入しました
4. 以下に示すエージェント、配布リスト、Teams チャネルは既に作成されています

注: 以下で使用する Teams チャネル コマンドレットは、Teams PowerShell モジュールのパブリック プレビュー バージョンの一部です。  詳細については、「 [Teams PowerShell パブリック プレビューのインストール](teams-powershell-install.md) 」を参照し、 [Microsoft Teams PowerShell のリリース ノート](teams-powershell-release-notes.md)も参照してください。

MicrosoftTeams モジュールを既にインストールしているユーザーは、最新バージョンがインストールされていることを確認する必要があります `Update-Module MicrosoftTeams` 。

## <a name="scenario"></a>シナリオ

次の 3 つの呼び出しキューが作成されます。

Sales Call Queue の情報:

- 自動応答でフロント: はい
- PSTN からの直接通話: いいえ
- 言語: 英語 (米国)
- あいさつ文: なし
- 保留音: オーディオ ファイルを再生する
  - ファイル名: sales-hold-in-queue-music.wav
- 通話応答: ユーザー
  - Bill@contoso.com
  - Mary@contoso.com
- 会議モード: オン
- ルーティング方法: アテンダント
- プレゼンス ベースのルーティング: オフ
- 通話エージェントは通話をオプトアウトできます:はい
- 通話エージェントのアラート時間: 15
- 呼び出しオーバーフロー処理: 200
  - リダイレクト先: Adele@contoso.com
- 呼び出しタイムアウト処理: 120 秒
  - リダイレクト先: Adele@contoso.com

呼び出しキュー情報のサポート:

- 自動応答でフロント: はい
- PSTN からの直接通話: いいえ
- 言語: 英国英語
- あいさつ文: オーディオ ファイルを再生する
  - ファイル名: support-greeting.wav
- 保留音: オーディオ ファイルを再生する
  - ファイル名: support-hold-in-queue-music.wav
- 通話応答: 配布リストをサポートする
  - Support@contoso.com
- 会議モード: オン
- ルーティング方法: 最長アイドル状態
- プレゼンス ベースのルーティング: N/A – 既定では最長アイドル状態のためオン
- 通話エージェントは通話をオプトアウトできます:いいえ
- 通話エージェントのアラート時間: 15
- 呼び出しオーバーフロー処理: 200
  - リダイレクト: 共有ボイスメールをサポートする
    - オーディオ ファイルを再生する (support-shared-ボイスメール-greeting.wav)
    - 文字起こしが有効になっている
- 呼び出しタイムアウト処理: 45 分
  - リダイレクト: 共有ボイスメールをサポートする
    - TTS: "お待たせしました。申し訳ございません。通話をボイスメールに転送しています。
    - 文字起こしが有効になっている

Facilities Collaborative Calling Queue information:

- Fronted by Auto Attendant: No
- PSTN からの直接通話: いいえ (内部通話のみ)
- 言語: フランス語 (FR)
- あいさつ文: なし
- 保留音: 既定値
- 通話応答: チーム: 設備
- 通話応答チャネル: ヘルプ デスク
  - チャネル所有者: Fred@contoso.com
- 会議モード: オン
- ルーティング方法: ラウンド ロビン
- プレゼンス ベースのルーティング: オン
- 通話エージェントは通話をオプトアウトできます:いいえ
- 通話エージェントのアラート時間: 15
- 呼び出しオーバーフロー処理: 200
  - 切断
- 呼び出しタイムアウト処理: 45 分
  - 切断

## <a name="login"></a>ログイン

Teams 管理者の資格情報の入力を求めるメッセージが表示されます。

```powershell
$credential = Get-Credential
Connect-MicrosoftTeams -Credential $credential
Connect-MsolService -Credential $credential
```

## <a name="sales-queue"></a>Sales Queue

### <a name="create-audio-files"></a>オーディオ ファイルを作成する

"d:\\" は、wav ファイルがコンピューターに保存されている場所へのパスに置き換えます。

```powershell
$content = Get-Content "d:\sales-hold-in-queue-music.wav" -Encoding byte -ReadCount 0
$audioFileSalesHoldInQueueMusicID = (Import-CsOnlineAudioFile -ApplicationID HuntGroup -FileName "sales-hold-in-queue-music.wav" -Content $content).ID
```

### <a name="get-users-id"></a>ユーザー ID を取得する

```powershell
$userAdeleID = (Get-CsOnlineUser -Identity "sip:adele@contoso.com").Identity
$userSalesBillID = (Get-CsOnlineUser -Identity "sip:bill@contoso.com").Identity
$userSalesMaryID = (Get-CsOnlineUser -Identity "sip:mary@contoso.com").Identity
```

### <a name="get-list-of-supported-languages"></a>サポートされている言語の一覧を取得する

```powershell
Get-CsAutoAttendantSupportedLanguage
```

### <a name="create-call-queue"></a>呼び出しキューの作成

```powershell
New-CsCallQueue -Name "Sales" -AgentAlertTime 15 -AllowOptOut $true -MusicOnHoldAudioFileID $audioFileSalesHoldInQueueMusicID -OverflowAction Forward -OverflowActionTarget $userAdeleID -OverflowThreshold 200 -TimeoutAction Forward -TimeoutActionTarget $userAdeleID -TimeoutThreshold 120 -RoutingMethod Attendant -ConferenceMode $true -User @($userSalesBillID, $userSalesMaryID) -LanguageID "en-US"
```

### <a name="get-license-types"></a>ライセンスの種類を取得する

```powershell
Get-MsolAccountSku
```

### <a name="create-and-assign-resource-account"></a>リソース アカウントの作成と割り当て

注: 通話キューは自動応答によってフロントエンドされるため、ここでは電話番号は必要ありません

- ApplicationID
  - 自動応答: ce933385-9390-45d1-9512-c8d228074e07
  - 通話キュー: 11cd3e2e-fccb-42ad-ad00-878b93575e07

注: 次に示すライセンスの種類 (PHONESYSTEM_VIRTUALUSER) は、上記のGet-MsolAccountSkuコマンドレットによって一覧表示されているライセンスの種類である必要があります。

```powershell
New-CsOnlineApplicationInstance -UserPrincipalName Sales-RA@contoso.com -DisplayName "Sales" -ApplicationID "11cd3e2e-fccb-42ad-ad00-878b93575e07"

Set-MsolUser -UserPrincipalName "Sales-RA@contoso.com" -UsageLocation US

Set-MsolUserLicense -UserPrincipalName "Sales-RA@contoso.com" -AddLicenses "contoso:PHONESYSTEM_VIRTUALUSER"

$applicationInstanceID = (Get-CsOnlineUser -Identity "Sales-RA@contoso.com").Identity
$callQueueID = (Get-CsCallQueue -NameFilter "Sales").Identity

New-CsOnlineApplicationInstanceAssociation -Identities @($applicationInstanceID) -ConfigurationID $callQueueID -ConfigurationType CallQueue
```

## <a name="support-queue"></a>サポート キュー

### <a name="create-audio-files"></a>オーディオ ファイルを作成する

"d:\\" は、wav ファイルがコンピューターに保存されている場所へのパスに置き換えます。

```powershell
$content = Get-Content "d:\support-greeting.wav" -Encoding byte -ReadCount 0
$audioFileSupportGreetingID = (Import-CsOnlineAudioFile -ApplicationID HuntGroup -FileName "support-greeting.wav" -Content $content).ID

$content = Get-Content "d:\support-hold-in-queue-music.wav" -Encoding byte -ReadCount 0
$audioFileSupportHoldInQueueMusicID = (Import-CsOnlineAudioFile -ApplicationID HuntGroup -FileName "support-hold-in-queue-music.wav" -Content $content).ID

$content = Get-Content "d:\support-shared-voicemail-greeting.wav" -Encoding byte -ReadCount 0
$audioFileSupportSharedVoicemailGreetingID = (Import-CsOnlineAudioFile -ApplicationID HuntGroup -FileName "support-shared-voicemail-greeting.wav" -Content $content).ID
```

### <a name="get-support-team-group-id"></a>サポート チーム グループ ID を取得する

```powershell
$teamSupportID = (Get-Team -displayname "Support").GroupID
```

### <a name="get-list-of-supported-languages"></a>サポートされている言語の一覧を取得する

```powershell
Get-CsAutoAttendantSupportedLanguage
```

### <a name="create-call-queue"></a>呼び出しキューの作成

```powershell
New-CsCallQueue -Name "Support" -AgentAlertTime 15 -AllowOptOut $false -DistributionLists $teamSupportID -WelcomeMusicAudioFileID $audioFileSupportGreetingID -MusicOnHoldAudioFileID $audioFileSupportHoldInQueueMusicID -OverflowAction SharedVoicemail -OverflowActionTarget $teamSupportID -OverflowThreshold 200 -OverflowSharedVoicemailAudioFilePrompt $audioFileSupportSharedVoicemailGreetingID -EnableOverflowSharedVoicemailTranscription $true -TimeoutAction SharedVoicemail -TimeoutActionTarget $teamSupportID -TimeoutThreshold 2700 -TimeoutSharedVoicemailTextToSpeechPrompt "We're sorry to have kept you waiting and are now transferring your call to voicemail." -EnableTimeoutSharedVoicemailTranscription $true -RoutingMethod LongestIdle -ConferenceMode $true -LanguageID "en-US"
```

### <a name="get-license-types"></a>ライセンスの種類を取得する

```powershell
Get-MsolAccountSku
```

### <a name="create-and-assign-resource-account"></a>リソース アカウントの作成と割り当て

注: 通話キューは自動応答によってフロントエンドされるため、ここでは電話番号は必要ありません

- ApplicationID
  - 自動応答: ce933385-9390-45d1-9512-c8d228074e07
  - 通話キュー: 11cd3e2e-fccb-42ad-ad00-878b93575e07

注: 次に示すライセンスの種類 (PHONESYSTEM_VIRTUALUSER) は、上記のGet-MsolAccountSkuコマンドレットによって一覧表示されているライセンスの種類である必要があります。

```powershell
New-CsOnlineApplicationInstance -UserPrincipalName Support-RA@contoso.com -DisplayName "Support" -ApplicationID "11cd3e2e-fccb-42ad-ad00-878b93575e07"

Set-MsolUser -UserPrincipalName "Support-RA@contoso.com" -UsageLocation US

Set-MsolUserLicense -UserPrincipalName "Support-RA@contoso.com" -AddLicenses "contoso:PHONESYSTEM_VIRTUALUSER"

$applicationInstanceID = (Get-CsOnlineUser -Identity "Support-RA@contoso.com").Identity
$callQueueID = (Get-CsCallQueue -NameFilter "Support").Identity

New-CsOnlineApplicationInstanceAssociation -Identities @($applicationInstanceID) -ConfigurationID $callQueueID -ConfigurationType CallQueue
```

## <a name="facilities-collaborative-calling-queue"></a>Facilities Collaborative Calling Queue

### <a name="get-facilities-team-group-id"></a>Facilities チーム グループ ID を取得する

```powershell
$teamFacilitiesGroupID = (Get-Team -DisplayName "Facilities").GroupID
```

### <a name="get-facilities-help-desk-team-channel-id"></a>Facilities Help Desk チーム チャネル ID を取得する

```powershell
Get-TeamChannel -GroupId $teamFacilitiesGroupID
$teamFacilitiesHelpDeskChannelID = "{assign ID from output of above command}"
```

### <a name="get-facilities-help-desk-channel-owner-user-id"></a>Facilities Help Desk チャネル所有者のユーザー ID を取得する

```powershell
$teamFacilitiesHelpDeskChannelUserID = (Get-TeamChannelUser -GroupId $teamFacilitiesGroupID -DisplayName "Help Desk" -Role Owner).UserId
```

### <a name="get-on-behalf-of-calling-resource-account-id"></a>リソース アカウント ID の呼び出しに代わって取得する

```powershell
$oboResourceAccountID = (Get-CsOnlineUser -Identity "MainAA-RA@contoso.com").Identity
```

### <a name="get-list-of-supported-languages"></a>サポートされている言語の一覧を取得する

```powershell
Get-CsAutoAttendantSupportedLanguage
```

### <a name="create-call-queue"></a>呼び出しキューの作成

```powershell
New-CsCallQueue -Name "Facilities" -AgentAlertTime 15 -AllowOptOut $false -ChannelId $teamFacilitiesHelpDeskChannelID -ChannelUserObjectId $teamFacilitiesHelpDeskChannelUserID  -ConferenceMode $true -DistributionList $teamFacilitiesGroupID -LanguageID "fr-FR" -OboResourceAccountIds $oboResourceAccountID -OverflowAction DisconnectWithBusy -OverflowThreshold 200 -RoutingMethod RoundRobin -TimeoutAction Disconnect -TimeoutThreshold 2700 -UseDefaultMusicOnHold $true 
```

### <a name="get-license-types"></a>ライセンスの種類を取得する

```powershell
Get-MsolAccountSku
```

### <a name="create-and-assign-resource-account"></a>リソース アカウントの作成と割り当て

**注**: 通話キューは自動応答によってフロントエンドされるため、ここでは電話番号は必要ありません

- ApplicationID
  - 自動応答: ce933385-9390-45d1-9512-c8d228074e07
  - 通話キュー: 11cd3e2e-fccb-42ad-ad00-878b93575e07

注: 次に示すライセンスの種類 (PHONESYSTEM_VIRTUALUSER) は、上記のGet-MsolAccountSkuコマンドレットによって一覧表示されているライセンスの種類である必要があります。

```powershell
New-CsOnlineApplicationInstance -UserPrincipalName Facilities-RA@contoso.com -DisplayName "Facilities" -ApplicationID "11cd3e2e-fccb-42ad-ad00-878b93575e07"

Set-MsolUser -UserPrincipalName "Facilities-RA@contoso.com" -UsageLocation US

Set-MsolUserLicense -UserPrincipalName "Facilities-RA@contoso.com" -AddLicenses "contoso:PHONESYSTEM_VIRTUALUSER"

$applicationInstanceID = (Get-CsOnlineUser -Identity "Facilities-RA@contoso.com").Identity
$callQueueID = (Get-CsCallQueue -NameFilter "Facilities").Identity

New-CsOnlineApplicationInstanceAssociation -Identities @($applicationInstanceID) -ConfigurationID $callQueueID -ConfigurationType CallQueue
```
