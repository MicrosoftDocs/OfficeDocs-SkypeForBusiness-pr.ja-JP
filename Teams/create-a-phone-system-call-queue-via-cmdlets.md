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
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.callqueues.overview"
- Phone System
- seo-marvel-apr2020
description: コマンドレットを使用して呼び出しキューを構成する方法について説明します
ms.openlocfilehash: 8ffbef5541a230755bb7439507e3002a5cb92462
ms.sourcegitcommit: 268660f101609852f02f3f9d1a8436f2a99dade7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/19/2022
ms.locfileid: "62071112"
---
# <a name="create-a-call-queue-via-cmdlets"></a>コマンドレットを使用して呼び出しキューを作成する

## <a name="assumptions"></a>前提条件
1)  PowerShell がコンピューターにインストールされている
- コンピューターを[セットアップしてWindows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
- MSTeams モジュールのインストール ````  (Install-Module -Name MicrosoftTeams -Force -AllowClobber) ````
- インストールされている MSOnline モジュール ```` Install-Module -Name MSOnline -Force -AllowClobber ````
2)  テナントの管理権限がある
3)  お客様が購入したMicrosoft Teams 電話
4)  以下に示すエージェント、配布リストTeamsチャネルは既に作成されています。

注: 以下Teams使用する Teams Channel コマンドレットは、PowerShell モジュールのパブリック プレビュー バージョンTeams一部です。  詳細については[、「PowerShell](teams-powershell-install.md)パブリック プレビュー Teamsインストールする」を参照し[、「PowerShell リリース Microsoft Teams」も参照してください](teams-powershell-release-notes.md)。

MicrosoftTeams モジュールが既にインストールされているユーザーは、最新バージョンがインストール ````Update-Module MicrosoftTeams```` されていることを確認する必要があります。


## <a name="scenario"></a>シナリオ

次の 3 つの呼び出しキューが作成されます。

Sales Call Queue の情報:
- 前に表示される自動応答: はい
- PSTN からの直接通話: いいえ
- 言語: 英語 (米国)
- あいさつ: なし
- 保留音: オーディオ ファイルを再生する
- - ファイル名: sales-hold-in-queue-music.wav
- 通話応答: ユーザー
- - Bill@contoso.com
- - Mary@contoso.com
- 会議モード: オン
- ルーティング方法: Attendant
- プレゼンス ベースのルーティング: オフ
- 通話エージェントは通話を受け取るのをオプトアウトできます:はい
- エージェントアラートの呼び出し時間: 15
- 呼び出しオーバーフロー処理: 200
- - リダイレクト先: Adele@contoso.com
- 呼び出しタイムアウト処理: 120 秒
- - リダイレクト先: Adele@contoso.com

サポート呼び出しキュー情報:
- 前に表示される自動応答: はい
- PSTN からの直接通話: いいえ
-   言語: 英国英語
-   あいさつ: オーディオ ファイルを再生する
-   - ファイル名: support-greeting.wav
-   保留音: オーディオ ファイルを再生する
-   - ファイル名: support-hold-in-queue-music.wav
-   通話応答: サポート配布リスト
-   - Support@contoso.com
-   会議モード: オン
-   ルーティング方法: アイドル時間が最も長い
-   プレゼンス ベースのルーティング: N/A – アイドル時間が最も長いため、既定では オン
-   通話エージェントは通話を受け取るのをオプトアウトできます:いいえ
-   エージェントアラートの呼び出し時間: 15
-   呼び出しオーバーフロー処理: 200
-   - リダイレクト: 共有ボイスメールのサポート
- - -   オーディオ ファイルを再生する (support-shared-voicemail-greeting.wav)
- - -   文字起こしが有効
-   呼び出しタイムアウト処理: 45 分
-   - リダイレクト: 共有ボイスメールのサポート
- - - TTS: "お待たせして申し訳ございません。通話をボイスメールに転送しています。"
- - - 文字起こしが有効


施設コラボレーション通話キューの情報:
- [Fronted by 自動応答: No]
- PSTN からの直接通話: いいえ (内部通話のみ)
-   言語: フランス語 (FR)
-   あいさつ: なし
-   保留音: 既定
-   通話応答: チーム: 施設
-   通話応答チャネル: ヘルプ デスク
-   - チャネル所有者: Fred@contoso.com
-   会議モード: オン
-   ルーティング方法: ラウンド ロビン
-   プレゼンス ベースのルーティング: オン
-   通話エージェントは通話を受け取るのをオプトアウトできます:いいえ
-   エージェントアラートの呼び出し時間: 15
-   呼び出しオーバーフロー処理: 200
-   - 切断
-   呼び出しタイムアウト処理: 45 分
-   - 切断


## <a name="login"></a>ログイン
管理者の資格情報を入力するように求Teamsされます。
```
$credential = Get-Credential
Connect-MicrosoftTeams -Credential $credential
Connect-MsolService -Credential $credential
````

## <a name="sales-queue"></a>販売キュー
### <a name="create-audio-files"></a>オーディオ ファイルを作成する
"d: " は、wav ファイルがコンピューターに格納されている場所への \\ パスに置き換える必要があります。

````
$content = Get-Content “d:\sales-hold-in-queue-music.wav” -Encoding byte -ReadCount 0
$audioFileSalesHoldInQueueMusicID = (Import-CsOnlineAudioFile -ApplicationID HuntGroup -FileName "sales-hold-in-queue-music.wav" -Content $content).ID
````

### <a name="get-users-id"></a>ユーザー ID の取得
````
$userAdeleID = (Get-CsOnlineUser -Identity “sip:adele@contoso.com”).ObjectID
$userSalesBillID = (Get-CsOnlineUser -Identity “sip:bill@contoso.com”).ObectID
$userSalesMaryID = (Get-CsOnlineUser -Identity “sip:mary@contoso.com”).ObjectID
````

### <a name="get-list-of-supported-languages"></a>サポートされている言語の一覧を取得する
````
Get-CsAutoAttendantSupportedLanguage
````

### <a name="create-call-queue"></a>通話キューを作成する
````
New-CsCallQueue -Name “Sales” -AgentAlertTime 15 -AllowOptOut $true -MusicOnHoldAudioFileID $audioFileSalesHoldInQueueMusicID -OverflowAction Forward -OverflowActionTarget $userAdeleID -OverflowThreshold 200 -TimeoutAction Forward -TimeoutActionTarget $userAdeleID -TimeoutThreshold 120 -RoutingMethod Attendant -ConferenceMode $true -User @($userSalesBillID, $userSalesMaryID) -LanguageID “en-US”
````

### <a name="get-license-types"></a>ライセンスの種類を取得する
````
Get-MsolAccountSku
````

### <a name="create-and-assign-resource-account"></a>リソース アカウントの作成と割り当て
注: 電話キューはキューによってフロント エンドされるので、この番号は必須自動応答
- ApplicationID
- - 自動応答: ce933385-9390-45d1-9512-c8d228074e07
- - 通話キュー: 11cd3e2e-fccb-42ad-ad00-878b93575e07

````
New-CsOnlineApplicationInstance -UserPrincipalName Sales-RA@contoso.com -DisplayName "Sales" -ApplicationID "11cd3e2e-fccb-42ad-ad00-878b93575e07"

Set-MsolUser -UserPrincipalName "Sales-RA@contoso.com" -UsageLocation US

Set-MsolUserLicense -UserPrincipalName “Sales-RA@contoso.com” -AddLicenses "contoso:PHONESYSTEM_VIRTUALUSER"

$applicationInstanceID = (Get-CsOnlineUser -Identity "Sales-RA@contoso.com").ObjectID
$callQueueID = (Get-CsCallQueue -NameFilter "Sales").Identity

New-CsOnlineApplicationInstanceAssociation -Identities @($applicationInstanceID) -ConfigurationID $callQueueID -ConfigurationType CallQueue
````


## <a name="support-queue"></a>サポート キュー
### <a name="create-audio-files"></a>オーディオ ファイルを作成する
"d: " は、wav ファイルがコンピューターに格納されている場所への \\ パスに置き換える必要があります。

````
$content = Get-Content “d:\support-greeting.wav” -Encoding byte -ReadCount 0
$audioFileSupportGreetingID = (Import-CsOnlineAudioFile -ApplicationID HuntGroup -FileName "support-greeting.wav" -Content $content).ID

$content = Get-Content “d:\support-hold-in-queue-music.wav” -Encoding byte -ReadCount 0
$audioFileSupportHoldInQueueMusicID = (Import-CsOnlineAudioFile -ApplicationID HuntGroup -FileName "support-hold-in-queue-music.wav" -Content $content).ID

$content = Get-Content “d:\support-shared-voicemail-greeting.wav” -Encoding byte -ReadCount 0
$audioFileSupportSharedVoicemailGreetingID = (Import-CsOnlineAudioFile -ApplicationID HuntGroup -FileName "support-shared-voicemail-greeting.wav" -Content $content).ID
````

### <a name="get-support-team-group-id"></a>サポート チーム グループ ID を取得する
````
$teamSupportID = (Get-Team -displayname "Support").GroupID
````

### <a name="get-list-of-supported-languages"></a>サポートされている言語の一覧を取得する
````
Get-CsAutoAttendantSupportedLanguage
````

### <a name="create-call-queue"></a>通話キューを作成する
````
New-CsCallQueue -Name “Support” -AgentAlertTime 15 -AllowOptOut $false -DistributionLists $teamSupportID -WelcomeMusicAudioFileID $audioFileSupportGreetingID -MusicOnHoldAudioFileID $audioFileSupportHoldInQueueMusicID -OverflowAction SharedVoicemail -OverflowActionTarget $teamSupportID -OverflowThreshold 200 -OverflowSharedVoicemailAudioFilePrompt $audioFileSupportSharedVoicemailGreetingID -EnableOverflowSharedVoicemailTranscription $true -TimeoutAction SharedVoicemail -TimeoutActionTarget $teamSupportID -TimeoutThreshold 2700 -TimeoutSharedVoicemailTextToSpeechPrompt "We're sorry to have kept you waiting and are now transferring your call to voicemail." -EnableTimeoutSharedVoicemailTranscription $true -RoutingMethod LongestIdle -ConferenceMode $true -LanguageID “en-US”
````

### <a name="get-license-types"></a>ライセンスの種類を取得する
````
Get-MsolAccountSku
````

### <a name="create-and-assign-resource-account"></a>リソース アカウントの作成と割り当て
注: 電話キューはキューによってフロントエンドされるので、この番号は必須自動応答
- ApplicationID
- - 自動応答: ce933385-9390-45d1-9512-c8d228074e07
- - 通話キュー: 11cd3e2e-fccb-42ad-ad00-878b93575e07
````
New-CsOnlineApplicationInstance -UserPrincipalName Support-RA@contoso.com -DisplayName "Support" -ApplicationID "11cd3e2e-fccb-42ad-ad00-878b93575e07"

Set-MsolUser -UserPrincipalName "Support-RA@contoso.com" -UsageLocation US

Set-MsolUserLicense -UserPrincipalName “Support-RA@contoso.com” -AddLicenses "contoso:PHONESYSTEM_VIRTUALUSER"

$applicationInstanceID = (Get-CsOnlineUser -Identity "Support-RA@contoso.com").ObjectID
$callQueueID = (Get-CsCallQueue -NameFilter "Support").Identity

New-CsOnlineApplicationInstanceAssociation -Identities @($applicationInstanceID) -ConfigurationID $callQueueID -ConfigurationType CallQueue
````


## <a name="facilities-collaborative-calling-queue"></a>施設コラボレーション通話キュー
### <a name="get-facilities-team-group-id"></a>施設のチーム グループ ID を取得する
````
$teamFacilitiesGroupID = (Get-Team -DisplayName "Facilities").GroupID
````

### <a name="get-facilities-help-desk-team-channel-id"></a>Facilities ヘルプ デスク チームのチャネル ID を取得する
````
Get-TeamChannel -GroupId $teamFacilitiesGroupID
$teamFacilitiesHelpDeskChannelID = "{assign ID from output of above command}"
````

### <a name="get-facilities-help-desk-channel-ower-user-id"></a>Facilities ヘルプ デスク チャネルのユーザー ID を取得する
````
$teamFacilitiesHelpDeskChannelUserID = (Get-TeamChannelUser -GroupId $teamFacilitiesGroupID -DisplayName "Help Desk" -Role Owner).UserId
````

### <a name="get-on-behalf-of-calling-resource-account-id"></a>リソース アカウント ID の呼び出しに代わって取得する
````
$oboResourceAccountID = (Get-CsOnlineUser -Identity "MainAA-RA@contoso.com").ObjectID
````

### <a name="get-list-of-supported-languages"></a>サポートされている言語の一覧を取得する
````
Get-CsAutoAttendantSupportedLanguage
````

### <a name="create-call-queue"></a>通話キューを作成する
````
New-CsCallQueue -Name “Facilities” -AgentAlertTime 15 -AllowOptOut $false -ChannelId $teamFacilitiesHelpDeskChannelID -ChannelUserObjectId $teamFacilitiesHelpDeskChannelUserID  -ConferenceMode $true -DistributionList $teamFacilitiesGroupID -LanguageID “fr-FR” -OboResourceAccountIds $oboResourceAccountID -OverflowAction DisconnectWithBusy -OverflowThreshold 200 -RoutingMethod RoundRobin -TimeoutAction Disconnect -TimeoutThreshold 2700 -UseDefaultMusicOnHold $true 
````

### <a name="get-license-types"></a>ライセンスの種類を取得する
````
Get-MsolAccountSku
````

### <a name="create-and-assign-resource-account"></a>リソース アカウントの作成と割り当て
注: 電話キューはキューによってフロントエンドされるので、この番号は必須自動応答
- ApplicationID
- - 自動応答: ce933385-9390-45d1-9512-c8d228074e07
- - 通話キュー: 11cd3e2e-fccb-42ad-ad00-878b93575e07
````
New-CsOnlineApplicationInstance -UserPrincipalName Support-RA@contoso.com -DisplayName "Facilities" -ApplicationID "11cd3e2e-fccb-42ad-ad00-878b93575e07"

Set-MsolUser -UserPrincipalName "Facilities-RA@contoso.com" -UsageLocation US

Set-MsolUserLicense -UserPrincipalName “Facilities-RA@contoso.com” -AddLicenses "contoso:PHONESYSTEM_VIRTUALUSER"

$applicationInstanceID = (Get-CsOnlineUser -Identity "Facilities-RA@contoso.com").ObjectID
$callQueueID = (Get-CsCallQueue -NameFilter "Facilities").Identity

New-CsOnlineApplicationInstanceAssociation -Identities @($applicationInstanceID) -ConfigurationID $callQueueID -ConfigurationType CallQueue
````
