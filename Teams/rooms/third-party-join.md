---
title: Teams Rooms デバイスがサード パーティの会議に参加できるようにする
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: sohailta
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: この記事では、Cisco Webex と Zoom へのサード パーティ会議への参加をサポートするように組織とTeams Rooms デバイスを構成する方法について説明します。
ms.openlocfilehash: 70d2cf03dea3fcfef3d08c07f4f771bd8a2ea70e
ms.sourcegitcommit: 89e3681a88f06a9c6860d9eaea598e57b928b68a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/16/2022
ms.locfileid: "67794996"
---
# <a name="enable-teams-rooms-devices-to-join-third-party-meetings"></a>Teams Rooms デバイスがサード パーティの会議に参加できるようにする

Microsoft Teams Rooms デバイスは、ダイレクト ゲスト参加とも呼ばれるサード パーティのオンライン会議に参加するためのワンタッチ エクスペリエンスをサポートします。 有効にすると、Teams Roomsを使用して、Microsoft Teams でホストされている会議に参加できるのと同じくらい簡単に Cisco Webex とズームでホストされている会議に参加できます。

サポートされているデバイスとサービス:

- Windows 上のTeams Rooms、すべての認定モデル – Zoom、Cisco Webex

- Android 上のTeams Rooms、すべての認定モデル – Zoom、Cisco Webex

    > [!NOTE]
    > Microsoft では、Android でTeams Roomsの新機能を定期的にリリースしています。 ただし、機能がリリースされたときと、デバイスで利用できるようになるまでの間に遅延が生じる可能性があります。 デバイスで機能が利用できない場合は、デバイスの製造元に問い合わせて、いつ利用可能になるかを確認してください。

> [!NOTE]
> Teams Rooms デバイスから Cisco Webex 会議に参加するには、Cisco Webex Web アプリケーション バージョン WBS 40.7 以降を使用して、Cisco 会議を Webex Meetings Pro でホストする必要があります。

Teams Roomsからサード パーティの会議に参加するには、次の操作を行う必要があります。

1. サード パーティの会議の招待を処理するために、Teams RoomsのExchange Online会議室メールボックスを構成します。
2. サードパーティの会議サービスへの接続を妨げるポリシーが組織にないことを確認します。
3. サード パーティの会議を許可するようにTeams Roomsを構成します。

次のセクションでは、これらの各手順を完了する方法について説明します。

## <a name="step-1-allow-calendar-invite-processing-for-third-party-meetings"></a>手順 1: サードパーティの会議の予定表の招待処理を許可する

Team Rooms からワンタッチ参加エクスペリエンスを有効にするために最初に行う必要があるのは、デバイスのExchange Online会議室メールボックスの予定表処理ルールを設定することです。 会議室メールボックスは、外部会議を許可し、サード パーティ会議に参加するために必要な URL を確認できるように、メッセージ本文と件名を保持する必要があります。 [Set-CalendarProcessing](/powershell/module/exchange/set-calendarprocessing.) コマンドレットを使用してこれらの会議室メールボックス オプションを設定するには、次の操作を行います。

1. Exchange Online PowerShell に接続します。 詳細については、認証方法に応じて、「[基本認証を使用して PowerShell Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell)[に接続する」または「多要素認証を使用して PowerShell に接続](/powershell/exchange/mfa-connect-to-exchange-online-powershell)Exchange Online」を参照してください。

2. 会議室メールボックスのユーザー プリンシパル名 (UPN) を取得するには、次のコマンドを実行します。

    ```powershell
    Get-Mailbox | Where {$_.RoomMailboxAccountEnabled -eq $True} | Format-Table Name, UserPrincipalName
    ```
    
3. Teams Rooms デバイスに関連付けられている会議室メールボックスの名前を見つけて、その UPN を書き留めます。

4. 会議室メールボックスの UPN を見つけたら、次のコマンドを実行します。 会議室メールボックスの UPN に置き換えます `<UserPrincipalName>` 。

    ```powershell
    Set-CalendarProcessing <UserPrincipalName> -ProcessExternalMeetingMessages $True -DeleteComments $False -DeleteSubject $False
    ```

[PowerShell Exchange Online](/powershell/exchange/exchange-online-powershell)の詳細については、こちらを参照してください。

## <a name="step-2-configure-office-365-threat-protection-and-link-rewrite"></a>手順 2: Office 365 Threat Protection とリンクの書き換えを構成する

ワンタッチ参加エクスペリエンスを有効にするには、サードパーティの会議からの会議参加リンク情報が会議の招待に表示され、読み取り可能である必要があります。 組織[でMicrosoft Defender for Office 365](/microsoft-365/security/office-365-security/safe-links)の安全なリンク機能を使用している場合、またはすべての受信 URL と送信 URL をスキャンして脅威を検出するサードパーティ ソリューションを使用している場合は、会議参加 URL が変更され、Teams Rooms デバイスで会議が認識できなくなる可能性があります。 これが発生しないようにするには、サード パーティの会議サービスの URL を Defender for [Office 365 安全なリンクの **書き換えリスト**](/microsoft-365/security/office-365-security/safe-links)またはサード パーティの URL 書き換え例外リストに追加する必要があります。

 サード パーティのソリューションを使用する場合は、そのソリューションの手順を参照して URL を URL 書き換え例外リストに追加します。

安全なリンクリストまたはサードパーティの URL *書き換え例外リストを書き換えない* Defender for Office 365に追加する必要があるエントリの例を次に示します。

- **Cisco Webex** `*.webex.com/*`
- **ズーム** `*.zoom.us/*`、 、 `*.zoom.com/*``*.zoomgov.com/*`

安全 *なリンクを* Defender for Office 365に追加する URL の完全な一覧については、会議の招待を受け入れるサード パーティの会議サービス プロバイダーにお問い合わせください。

> [!CAUTION]
> 信頼できる URL をMicrosoft Defender for Office 365セーフ リンクにのみ追加する リストまたはサードパーティの URL 書き換え例外リストを書き換 *える必要はありません*。

## <a name="step-3a-enable-third-party-meetings-on-teams-rooms-on-windows"></a>手順 3a: Windows でTeams Roomsでサード パーティの会議を有効にする

最後に行う必要がある手順は、Teams Roomsがサード パーティの会議に参加できるようにすることです。 サードパーティの会議に参加するには、ユーザー名と電子メール アドレスが必要です。 使用する必要があるユーザー名と電子メール アドレスがデバイスの会議室メールボックスと異なる場合は、デバイスに追加する必要があります。 これを行うには、Teams Rooms設定または XML 構成ファイルで行います。 これは、任意の対応するTeams RoomsのTeams Rooms設定、または Windows 上のTeams Rooms用の XML 構成ファイルで行うことができます。

### <a name="use-device-settings"></a>デバイス設定を使用する

タッチスクリーン コンソールを使用して Windows でTeams Roomsを構成するには、次の操作を行います。

1. Microsoft Teams Rooms コンソールで、[**その他**] を選択します。
2. **[設定] を** 選択し、デバイス管理者のユーザー名とパスワードを入力します。
3. **[会議**] タブに移動し、有効にするサードパーティの会議プロバイダー (**Webex**、**ズーム** など) を選択します。
4. 会議室メールボックスに関連付けられているユーザー名とメール アドレスを使用して会議に参加する場合は、[ **会議室情報を含む参加**] を選択します。
5. 別のユーザー名とメール アドレスを使用して会議に参加する場合は、[ **カスタム情報を使用して参加** する] を選択し、使用するユーザー名とメール アドレスを入力します。
6. **[保存して終了]** を選択します。 デバイスが再起動します。

### <a name="use-the-skypesettingsxml-configuration-file"></a>SkypeSettings.xml構成ファイルを使用する

次の設定をファイル`C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState`に`SkypeSettings.xml`追加できます。 ファイルの`SkypeSettings.xml`詳細については、「[XML 構成ファイルを使用してリモートでMicrosoft Teams Rooms コンソール設定を管理する」を参照](xml-config-file.md)してください。

Cisco Webex 会議を有効にするには、次のように XML 要素を `WebexMeetingsEnabled` **True** に設定します。

```xml
<WebexMeetingsEnabled>True</WebexMeetingsEnabled>
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
## <a name="step-3b-enable-third-party-meetings-on-teams-rooms-on-android"></a>手順 3b: Android でTeams Roomsでサード パーティの会議を有効にする

タッチスクリーン コンソールまたはルーム前面ディスプレイを使用して Android でTeams Roomsを構成するには、次の操作を行います。

1.  Microsoft Teams Rooms コンソールまたは部屋の前面ディスプレイで、[**その他**] を選択します。
2.  **[設定] を** 選択し、次の操作を行います。
    -   個人用アカウント (E5 ライセンスを持つアカウントなど) を使用する場合は、[ **会議** ] オプションを選択します。
    -   共有アカウント (たとえば、Teams Rooms ライセンスを持つリソース アカウント) を使用している場合は、[**デバイス設定**] を選択 **し、Teams 管理設定** を見つけて、管理者パスワードを入力して、[**会議**] オプションを選択します。
      > [!NOTE]
      > デバイスの一部の製造元では、 **デバイス設定** にアクセスする前に管理者パスワードが必要です。

    ![Android 上の MRT の会議設定](..\media\mtrandroid.png)

3.  有効にするサードパーティの会議プロバイダーを選択します。
4.  カスタム ユーザー名とメール アドレスを使用して会議に参加する場合は、[ **カスタム名とメールで参加** する] を選択します。 カスタム個人情報を更新するには、[ **カスタム情報の編集]** を押し、希望する名前とメール アドレスを入力します。

