---
title: Teams 会議室デバイスがサードパーティの会議に参加する
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: sohailta
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
localization_priority: Normal
description: この記事では、Cisco WebEx とズームへの参加をサポートするサードパーティ会議をサポートするために組織および Teams Rooms デバイスを構成する方法について説明します。
ms.openlocfilehash: 82369c534a616796382b1de69e37c64f15392f9b
ms.sourcegitcommit: db0dc45520503753567e99c0c016f0265d45aa66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/15/2020
ms.locfileid: "49682386"
---
# <a name="enable-teams-room-devices-to-join-third-party-meetings"></a>Teams Room デバイスがサードパーティの会議に参加する

Microsoft Teams Rooms デバイスは、サードパーティのオンライン会議 (直接ゲスト参加とも呼ばれます) に参加するワンタッチ操作をサポートします。 有効になっている場合は、Teams 会議室デバイスを使用して、Microsoft Teams でホストされている会議に参加できるのと同じ方法で、Cisco WebEx およびズームでホストされている会議に簡単に参加できます。

Teams 会議室デバイスからサードパーティ会議に参加するには、次の操作を行う必要があります。

1. サードパーティ会議への招待を処理するために、Teams Rooms デバイスの Exchange Online 会議室メールボックスを構成します。
2. サードパーティの会議サービスへの接続を妨げるポリシーが組織に与えされていないことを確認します。
3. サードパーティの会議を許可する Teams Rooms デバイスを構成します。

次のセクションでは、これらの各手順を実行する方法について説明します。

## <a name="step-1-allow-calendar-invite-processing-for-third-party-meetings"></a>手順 1: サードパーティ会議の予定表の招待処理を許可する

チーム ルーム デバイスからワンタッチで参加するには、まず、デバイスの Exchange Online 会議室メールボックスの予定表処理ルールを設定します。 会議室メールボックスでは、外部会議を許可し、メッセージ本文と件名を保持して、サードパーティ会議への参加に必要な URL を確認する必要があります。 [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/set-calendarprocessing?view=exchange-ps.)コマンドレットを使用してこれらのルーム メールボックス オプションを設定するには、次の操作を行います。

1. Exchange Online PowerShell に接続します。 詳細については、認証方法に応じて、「基本認証を使用して [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps) に接続する」または「多要素認証を使用して [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell?view=exchange-ps)に接続する」を参照してください。

2. 次のコマンドを実行して、それが分からない場合は、ルーム メールボックスのユーザー プリンシパル名 (UPN) を取得します。

    ```powershell
    Get-Mailbox | Where {$_.RoomMailboxAccountEnabled -eq $True} | Format-Table Name, UserPrincipalName
    ```
    
3. Teams Rooms デバイスに関連付けられている会議室メールボックスの名前を見つけて、UPN をメモします。

4. ルーム メールボックスの UPN が見つけたら、次のコマンドを実行します。 ルーム `<UserPrincipalName>` メールボックスの UPN に置き換える:

    ```powershell
    Set-CalendarProcessing <UserPrincipalName> -ProcessExternalMeetingMessages $True -DeleteComments $False -DeleteSubject $False
    ```

[Exchange Online PowerShell の詳細については、次を参照してください](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell?view=exchange-ps)。

## <a name="step-2-configure-office-365-threat-protection-and-link-rewrite"></a>手順 2: Office 365 Threat Protection を構成し、リンクを書き換える

ワンタッチ参加機能を有効にするには、サードパーティの会議からの会議参加リンク情報が会議の出席と読み取りが可能である必要があります。 組織で Office [365 Advanced Threat Protection の](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links) 安全なリンク機能を使用している場合、またはすべての受信 URL と送信 URL を脅威用にスキャンするサードパーティ ソリューションを使用している場合は、会議参加 URL が変更され、Teams Rooms デバイスで会議が認識不可になります。 この問題が発生しない場合は、サード パーティの会議サービスの URL を ATP の安全なリンクのリストに追加するか、サード パーティの URL 書き換え例外リストを "書き換えない" 必要があります。

サード パーティの会議サービスの URL を ATP の安全なリンクの "書き換えない" リストに追加するには [、「ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-a-custom-do-not-rewrite-urls-list-with-atp?view=o365-worldwide)の安全なリンクを使用して、書き換えないカスタム URL リストを設定する」の手順に従います。 サード パーティのソリューションを使用する場合は、そのソリューションの手順を参照して、URL の書き換え例外リストに URL を追加します。

ATP の安全なリンクの "書き換えない" リストまたはサード パーティの URL 書き換え例外リストに追加する必要があるエントリの例を次に示します。

- **Cisco WebEx**`*.webex.com*`
- **ズーム** `*.zoom.us*` `*.zoom.com*` 、、 `*.zoomgov.com*`

ATP の安全なリンクの "書き換えない" リストまたはサード パーティの URL 書き換え例外リストに追加する URL の完全なリストについては、会議の招待を受け入れるサードパーティの会議サービス プロバイダーにお問い合わせください。 

> [!CAUTION]
> 信頼できる URL のみを ATP の安全なリンクのリストに追加するか、サード パーティ URL の書き換え例外リストを作成します。

## <a name="step-3-enable-third-party-meetings-on-device"></a>手順 3: デバイスでサードパーティ会議を有効にする

最後に行う必要がある手順は、各 Teams Rooms デバイスがサードパーティ会議に参加することを許可します。 サードパーティの会議に参加するには、ユーザー名とメール アドレスが必要です。 使用する必要があるユーザー名とメール アドレスがデバイスのルーム メールボックスと異なる場合は、デバイスに追加する必要があります。 これは、デバイスの設定または XML 構成ファイルで行います。

### <a name="use-device-settings"></a>デバイス設定を使用する

タッチスクリーンを使用して Teams Rooms デバイスを構成するには、次の操作を行います。

1. Microsoft Teams の会議室デバイスで、[その他 **...] を選択します**。
2. [ **設定]** を選び、デバイス管理者のユーザー名とパスワードを入力します。
3. [会議] タブ **に移動** し **、Cisco WebEx、ズーム**、または **両方を選択** します。
4. ルーム メールボックスに関連付けられているユーザー名とメール アドレスを使用して会議に参加する場合は、[ルーム情報で参加] を **選択します**。
5. 別のユーザー名とメール アドレスを使用して会議に参加する場合は、[ユーザー設定の情報で参加] を選択し、使用するユーザー名とメール アドレスを入力します。
6. **[保存して終了]** を選択します。 デバイスが再起動します。

### <a name="use-the-skypesettingsxml-configuration-file"></a>構成ファイルSkypeSettings.xml使用する

次の設定は、次の `SkypeSettings.xml` 場所にあるファイルに追加できます `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` 。 ファイルの詳細については、「XML 構成ファイルを使用して Microsoft Teams Rooms 本体の設定をリモート `SkypeSettings.xml` [で管理する」を参照してください](xml-config-file.md)。

Cisco WebEx 会議を有効にするには、次のように XML 要素 `WebExMeetingsEnabled` を **True** に設定します。

```xml
<WebExMeetingsEnabled>True</WebExMeetingsEnabled>
```

ズーム会議を有効にするには、次のように XML 要素 `ZoomMeetingsEnabled` を **True** に設定します。

```xml
<ZoomMeetingsEnabled>True</ZoomMeetingsEnabled>
```

必要に応じて、ユーザー設定のユーザー名とメール アドレスを指定して、次の XML 要素を使用してサードパーティの会議に参加できます。 入力した値が無効な場合、Teams Rooms デバイスは既定で会議室メールボックスのユーザー名とメール アドレスを使用します。

```xml
<UseCustomInfoForThirdPartyMeetings>true</UseCustomInfoForThirdPartyMeetings>

<CustomDisplayNameForThirdPartyMeetings>guestname</CustomDisplayNameForThirdPartyMeetings>

<CustomDisplayEmailForThirdPartyMeetings>guest@contoso.com</CustomDisplayEmailForThirdPartyMeetings>
```

> [!NOTE]
> Teams Rooms デバイスから Cisco WebEx 会議に参加するには、Cisco WebEx Web アプリケーション バージョン WBS 40.7 以降を使用して Cisco 会議をホストする必要があります。

