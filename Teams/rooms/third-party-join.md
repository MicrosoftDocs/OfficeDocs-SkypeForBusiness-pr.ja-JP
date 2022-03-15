---
title: 会議室Teamsサードパーティの会議に参加する
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
description: この記事では、Cisco WebEx と Zoom へのサードパーティの会議参加をサポートTeams会議室デバイスを構成する方法について説明します。
ms.openlocfilehash: a4ae34593570d4b81eb381eb0fe68f1dea26d578
ms.sourcegitcommit: a894e9397050e09bfaab02e700e943a3bbeb1302
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2022
ms.locfileid: "63503904"
---
# <a name="enable-teams-room-devices-to-join-third-party-meetings"></a>ルーム Teamsを有効にしてサードパーティの会議に参加する

Microsoft Teams会議室デバイスは、サード パーティのオンライン会議 (直接ゲスト参加とも呼ばれます) に参加するワンタッチ エクスペリエンスをサポートします。 有効にすると、Teams 会議室を使用して、Cisco WebEx および Zoom でホストされている会議に、Microsoft Teams でホストされている会議に参加できるのと同じ方法で簡単に参加できます。

Teams 会議室からサードパーティ会議に参加するには、次の操作を行う必要があります。

1. サードパーティ会議Teamsを処理Exchange Online会議室メールボックスを構成します。
2. 組織に、サードパーティの会議サービスへの接続を妨げるポリシーが設定されていないことを確認します。
3. サードパーティTeamsを許可する会議室を構成します。

次のセクションでは、これらの各手順を実行する方法について説明します。

## <a name="step-1-allow-calendar-invite-processing-for-third-party-meetings"></a>手順 1: サードパーティ会議の予定表の招待処理を許可する

チーム ルームからのワンタッチ参加エクスペリエンスを有効にするには、まず、デバイスの会議室メールボックスの予定表処理ルールをExchange Onlineがあります。 会議室メールボックスは、外部会議を許可し、メッセージの本文と件名を保持して、サード パーティ会議に参加するために必要な URL を確認できる必要があります。 [Set-CalendarProcessing](/powershell/module/exchange/set-calendarprocessing?view=exchange-ps.) コマンドレットを使用してこれらのルーム メールボックス オプションを設定するには、次の操作を行います。

1. Exchange Online PowerShell に接続します。 詳細については、「基本認証を使用Connect [PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps) をExchange Onlineする」を参照するか、認証方法に応じて多要素認証Connect [PowerShell Exchange Online PowerShell](/powershell/exchange/mfa-connect-to-exchange-online-powershell?view=exchange-ps) を使用する方法に関するページを参照してください。

2. 次のコマンドを実行して、ルーム メールボックスのユーザー プリンシパル名 (UPN) を取得します (分からない場合)。

    ```powershell
    Get-Mailbox | Where {$_.RoomMailboxAccountEnabled -eq $True} | Format-Table Name, UserPrincipalName
    ```
    
3. Teams Rooms デバイスに関連付けられている会議室メールボックスの名前を見つけて、その UPN をメモします。

4. ルーム メールボックスの UPN が見つけたら、次のコマンドを実行します。 を `<UserPrincipalName>` ルーム メールボックスの UPN に置き換える:

    ```powershell
    Set-CalendarProcessing <UserPrincipalName> -ProcessExternalMeetingMessages $True -DeleteComments $False -DeleteSubject $False
    ```

[PowerShell の詳細についてはExchange Online参照してください](/powershell/exchange/exchange-online-powershell?view=exchange-ps)。

## <a name="step-2-configure-office-365-threat-protection-and-link-rewrite"></a>手順 2: Threat Protection とOffice 365書き換えを構成する

ワンタッチ参加エクスペリエンスを有効にするには、サードパーティの会議からの会議参加リンク情報が会議の招待に表示され、読み取り可能である必要があります。 [組織で Office 365 Advanced Threat Protection セーフ リンク](/microsoft-365/security/office-365-security/atp-safe-links)機能を使用している場合、またはすべての受信 URL と送信 URL をスキャンして脅威を検出するサード パーティ製ソリューションを使用している場合は、会議参加 URL が変更され、Teams Rooms デバイスで会議が認識できない可能性があります。 この問題が発生しない場合は、サード パーティの会議サービスの URL を ATP セーフ リンクの "書き換えない" リストまたはサード パーティの URL 書き換え例外リストに追加する必要があります。

サードパーティの会議サービス URL を ATP セーフ リンクの "書き換えない" リストに追加するには、「ATP セーフ リンクを使用してカスタムの書き換えない URL リストを設定する」の[手順に従](/microsoft-365/security/office-365-security/set-up-a-custom-do-not-rewrite-urls-list-with-atp?view=o365-worldwide)います。 サード パーティのソリューションを使用する場合は、そのソリューションの手順を参照して、URL 書き換え例外リストに URL を追加します。

ATP セーフ リンク "書き換えない" リストまたはサード パーティの URL 書き換え例外リストに追加する必要があるエントリの例を次に示します。

- **Cisco WebEx** `*.webex.com*`
- **ズーム**`*.zoom.us*`、、`*.zoom.com*`、`*.zoomgov.com*`

ATP セーフ リンクの "書き換えない" リストまたはサード パーティの URL 書き換え例外リストに追加する URL の完全な一覧については、会議の招待を受け入れるサードパーティの会議サービス プロバイダーにお問い合わせください。 

> [!CAUTION]
> 信頼できる URL のみを ATP アプリに追加セーフリンク "書き換えない" リストまたはサード パーティの URL 書き換え例外リスト。

## <a name="step-3-enable-third-party-meetings-on-teams-rooms"></a>手順 3: 会議室でサードパーティの会議Teamsする

最後に行う必要がある手順は、会議室Teamsサードパーティ会議への参加を許可します。 サードパーティ会議に参加するには、ユーザー名とメール アドレスが必要です。 使用する必要があるユーザー名とメール アドレスがデバイスのルーム メールボックスと異なる場合は、デバイスに追加する必要があります。 これは、会議室の設定Teams XML 構成ファイルで行います。

### <a name="use-device-settings"></a>デバイス設定を使用する

タッチスクリーン コンソールTeams会議室を構成するには、次の操作を行います。

1. [会議室] Microsoft Teamsで、[その他 **...] を選択します**。
2. **[設定**] を選択し、デバイス管理者のユーザー名とパスワードを入力します。
3. [会議] タブ **に移動** し、 **Cisco WebEx**、Zoom、または **両方** を選択します。
4. ルーム メールボックスに関連付けられているユーザー名とメール アドレスで会議に参加する場合は、[ルーム情報を使用して参加 **] を選択します**。
5. 別のユーザー名とメール アドレスで会議に参加する場合は、[カスタム情報で参加] を選択し、使用するユーザー名とメール アドレスを入力します。
6. **[保存して終了]** を選択します。 デバイスが再起動します。

### <a name="use-the-skypesettingsxml-configuration-file"></a>構成ファイルSkypeSettings.xml使用する

にある ファイルには、次の `SkypeSettings.xml` 設定を追加できます `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState`。 ファイルの詳細については`SkypeSettings.xml`、「XML 構成ファイルを使用して Microsoft Teams Rooms コンソール設定をリモート[で管理する」を参照してください](xml-config-file.md)。

Cisco WebEx 会議を有効にするには、次のように `WebExMeetingsEnabled` XML 要素を **True** に設定します。

```xml
<WebExMeetingsEnabled>True</WebExMeetingsEnabled>
```

Zoom 会議を有効にするには、次のように `ZoomMeetingsEnabled` XML 要素を **True** に設定します。

```xml
<ZoomMeetingsEnabled>True</ZoomMeetingsEnabled>
```

必要に応じて、カスタム ユーザー名とメール アドレスを指定して、次の XML 要素を使用してサードパーティの会議に参加できます。 指定した値が無効な場合、Teams 会議室デバイスは、既定で会議室メールボックスのユーザー名とメール アドレスを使用します。

```xml
<UseCustomInfoForThirdPartyMeetings>true</UseCustomInfoForThirdPartyMeetings>

<CustomDisplayNameForThirdPartyMeetings>guestname</CustomDisplayNameForThirdPartyMeetings>

<CustomDisplayEmailForThirdPartyMeetings>guest@contoso.com</CustomDisplayEmailForThirdPartyMeetings>
```

> [!NOTE]
> Teams Rooms デバイスから Cisco WebEx 会議に参加するには、Cisco WebEx Web アプリケーション バージョン WBS 40.7 以降を使用して、WebEx Meetings Pro で Cisco 会議をホストする必要があります。 
