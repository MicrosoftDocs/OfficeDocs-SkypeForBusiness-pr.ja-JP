---
title: Teams Rooms デバイスがサード パーティの会議に参加できるようにする
ms.author: czawideh
author: cazawideh
manager: serdars
ms.reviewer: sohailta
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: この記事では、Cisco WebEx と Zoom へのサード パーティ会議への参加をサポートするように組織とTeams Rooms デバイスを構成する方法について説明します。
ms.openlocfilehash: 6defa9c9287b130eb5534f0aea158a78f2de8b18
ms.sourcegitcommit: 480046a53dfb6e6cf867e1920f8fb43dda9d3774
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2022
ms.locfileid: "64846606"
---
# <a name="enable-teams-room-devices-to-join-third-party-meetings"></a>会議室デバイスTeamsサード パーティの会議に参加できるようにする

> [!NOTE]
> この機能は現在、WindowsのTeams Roomsでのみ使用できます。

Microsoft Teams Rooms デバイスは、ダイレクト ゲスト参加とも呼ばれるサード パーティのオンライン会議に参加するためのワンタッチ エクスペリエンスをサポートします。 有効にすると、Teams Roomsを使用して、Microsoft Teamsでホストされている会議に参加できるのと同じくらい簡単に Cisco WebEx とズームでホストされている会議に参加できます。

Teams Roomsからサード パーティの会議に参加するには、次の操作を行う必要があります。

1. サード パーティの会議の招待を処理するために、Teams RoomsのExchange Online会議室メールボックスを構成します。
2. サードパーティの会議サービスへの接続を妨げるポリシーが組織にないことを確認します。
3. サード パーティの会議を許可するようにTeams Roomsを構成します。

次のセクションでは、これらの各手順を実行する方法について説明します。

## <a name="step-1-allow-calendar-invite-processing-for-third-party-meetings"></a>手順 1: サードパーティの会議の予定表の招待処理を許可する

Team Rooms からワンタッチ参加エクスペリエンスを有効にするために最初に行う必要があるのは、デバイスのExchange Online会議室メールボックスの予定表処理ルールを設定することです。 会議室メールボックスは、外部会議を許可し、サード パーティ会議に参加するために必要な URL を確認できるように、メッセージ本文と件名を保持する必要があります。 [Set-CalendarProcessing](/powershell/module/exchange/set-calendarprocessing?view=exchange-ps.) コマンドレットを使用してこれらの会議室メールボックス オプションを設定するには、次の操作を行います。

1. Exchange Online PowerShell に接続します。 詳細については、「[基本認証を使用して PowerShell をExchange OnlineするConnect](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps)」を参照するか、認証方法に応じて[多要素認証を使用して PowerShell をExchange OnlineするConnect](/powershell/exchange/mfa-connect-to-exchange-online-powershell?view=exchange-ps)を参照してください。

2. 会議室メールボックスのユーザー プリンシパル名 (UPN) を取得するには、次のコマンドを実行します。

    ```powershell
    Get-Mailbox | Where {$_.RoomMailboxAccountEnabled -eq $True} | Format-Table Name, UserPrincipalName
    ```
    
3. Teams Rooms デバイスに関連付けられている会議室メールボックスの名前を見つけて、その UPN を書き留めます。

4. 会議室メールボックスの UPN を見つけたら、次のコマンドを実行します。 会議室メールボックスの UPN に置き換えます `<UserPrincipalName>` 。

    ```powershell
    Set-CalendarProcessing <UserPrincipalName> -ProcessExternalMeetingMessages $True -DeleteComments $False -DeleteSubject $False
    ```

[PowerShell Exchange Online](/powershell/exchange/exchange-online-powershell?view=exchange-ps)の詳細については、こちらを参照してください。

## <a name="step-2-configure-office-365-threat-protection-and-link-rewrite"></a>手順 2: Office 365 Threat Protection とリンクの書き換えを構成する

ワンタッチ参加エクスペリエンスを有効にするには、サードパーティの会議からの会議参加リンク情報が会議の招待に表示され、読み取り可能である必要があります。 組織[でMicrosoft Defender for Office 365](/microsoft-365/security/office-365-security/safe-links?view=o365-worldwide)の安全なリンク機能を使用している場合、またはすべての受信 URL と送信 URL をスキャンして脅威を検出するサードパーティ ソリューションを使用している場合は、会議参加 URL が変更され、Teams Rooms デバイスで会議が認識できなくなる可能性があります。 これが発生しないようにするには、サード パーティの会議サービスの URL を Defender for [Office 365 セーフ リンクの **書き換えリスト**](/microsoft-365/security/office-365-security/safe-links?view=o365-worldwide)またはサード パーティの URL 書き換え例外リストに追加する必要があります。

 サード パーティのソリューションを使用する場合は、そのソリューションの手順を参照して URL を URL 書き換え例外リストに追加します。

Defender for Office 365 セーフ リンクの *書き換えリスト* またはサード パーティの URL 書き換え例外リストに追加する必要があるエントリの例を次に示します。

- **Cisco WebEx** `*.webex.com*`
- **ズーム** `*.zoom.us*`、 、 `*.zoom.com*``*.zoomgov.com*`

Defender for Office 365 セーフ *リンクに* 追加する URL の完全な一覧については、会議の招待を受け入れるサード パーティの会議サービス プロバイダーにお問い合わせください。

> [!CAUTION]
> 信頼できる URL をMicrosoft Defender for Office 365 セーフ リンクにのみ追加する リストまたはサード パーティの URL 書き換え例外リストを書き換 *えないでください*。

## <a name="step-3-enable-third-party-meetings-on-teams-rooms"></a>手順 3: Teams Roomsでサード パーティの会議を有効にする

最後に行う必要がある手順は、Teams Roomsがサード パーティの会議に参加できるようにすることです。 サードパーティの会議に参加するには、ユーザー名と電子メール アドレスが必要です。 使用する必要があるユーザー名と電子メール アドレスがデバイスの会議室メールボックスと異なる場合は、デバイスに追加する必要があります。 これを行うには、Teams Rooms設定または XML 構成ファイルで行います。

### <a name="use-device-settings"></a>デバイス設定を使用する

タッチスクリーン コンソールを使用してTeams Roomsを構成するには、次の操作を行います。

1. Microsoft Teams Rooms コンソールで、**その他の ....** を選択します。
2. **設定** 選択し、デバイス管理者のユーザー名とパスワードを入力します。
3. **[会議**] タブに移動し、**Cisco WebEx**、**ズーム**、またはその両方を選択します。
4. 会議室メールボックスに関連付けられているユーザー名とメール アドレスを使用して会議に参加する場合は、[ **会議室情報を含む参加**] を選択します。
5. 別のユーザー名とメール アドレスを使用して会議に参加する場合は、[ **カスタム情報を使用して参加** する] を選択し、使用するユーザー名とメール アドレスを入力します。
6. **[保存して終了]** を選択します。 デバイスが再起動します。

### <a name="use-the-skypesettingsxml-configuration-file"></a>SkypeSettings.xml構成ファイルを使用する

次の設定をファイル`C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState`に`SkypeSettings.xml`追加できます。 ファイルの`SkypeSettings.xml`詳細については、「[XML 構成ファイルを使用してリモートでMicrosoft Teams Rooms コンソール設定を管理する」を参照](xml-config-file.md)してください。

Cisco WebEx 会議を有効にするには、次のように XML 要素を `WebExMeetingsEnabled` **True** に設定します。

```xml
<WebExMeetingsEnabled>True</WebExMeetingsEnabled>
```

Zoom 会議を有効にするには、次のように XML 要素を `ZoomMeetingsEnabled` **True** に設定します。

```xml
<ZoomMeetingsEnabled>True</ZoomMeetingsEnabled>
```

必要に応じて、次の XML 要素を使用して、サードパーティの会議に参加するためのカスタム ユーザー名と電子メール アドレスを指定できます。 指定した値が無効な場合、Teams Rooms デバイスは既定で会議室メールボックスのユーザー名と電子メール アドレスを使用します。

```xml
<UseCustomInfoForThirdPartyMeetings>true</UseCustomInfoForThirdPartyMeetings>

<CustomDisplayNameForThirdPartyMeetings>guestname</CustomDisplayNameForThirdPartyMeetings>

<CustomDisplayEmailForThirdPartyMeetings>guest@contoso.com</CustomDisplayEmailForThirdPartyMeetings>
```

> [!NOTE]
> Teams Rooms デバイスから Cisco WebEx 会議に参加するには、Cisco WebEx Web アプリケーション バージョン WBS 40.7 以降を使用して、WebEx Meetings Proで Cisco 会議をホストする必要があります。 
