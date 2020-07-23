---
title: Teams 室のデバイスでサードパーティの会議に参加できるようにする
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
description: この記事では、組織とチーム室のデバイスを構成して、サードパーティの会議への参加をサポートする方法について説明します。
ms.openlocfilehash: 708fb7f9d243559a571b2b9016fab1e38aa63114
ms.sourcegitcommit: 3e5cac88911611c94c0330bf50af9c34db308cdf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/22/2020
ms.locfileid: "45372216"
---
# <a name="enable-teams-room-devices-to-join-third-party-meetings"></a>Teams Room デバイスでサードパーティの会議に参加できるようにする

Microsoft Teams の会議室のデバイスは、サードパーティのオンライン会議に参加するためのワンタッチエクスペリエンスをサポートしています。 有効にすると、チームルームデバイスを使って、Cisco WebEx でホストされている会議に参加したり、Microsoft Teams でホストされている会議に参加したりするのと同じように簡単<sup>にズームする</sup>ことができます。

Teams 室のデバイスからサードパーティの会議に参加するには、次の手順を実行する必要があります。

1. サードパーティの会議の招待を処理するために Teams 室デバイスの Exchange Online room メールボックスを構成する
2. サードパーティの会議サービスに接続できないポリシーが組織にないことを確認します。
3. サードパーティの会議を許可するようにチームルームデバイスを構成する

以下のセクションでは、これらの各手順を実行する方法について説明します。

## <a name="step-1-allow-calendar-invite-processing-for-third-party-meetings"></a>手順 1: サードパーティの会議の予定表の招待処理を許可する

チームルームデバイスからワンタッチの参加を有効にするには、まず、デバイスの Exchange Online room メールボックスの予定表処理ルールを設定します。 会議室メールボックスでは、第三者の会議に参加するために必要な URL が表示されるように、外部会議を許可し、メッセージ本文と件名を保持する必要があります。 [[カレンダーの設定](https://docs.microsoft.com/powershell/module/exchange/set-calendarprocessing?view=exchange-ps.)] コマンドレットを使用して、会議室のメールボックスのオプションを設定するには、次の操作を行います。

1. Exchange Online PowerShell に接続します。 詳細については、認証方法に応じて、「Basic 認証を使用して[Exchange Online powershell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps)」または「[多要素認証を使用して exchange online powershell に](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell?view=exchange-ps)接続する」を参照してください。

2. 次のコマンドを実行して、会議室のメールボックスがわからない場合は、ユーザープリンシパル名 (UPN) を取得します。

    ```powershell
    Get-Mailbox | Where {$_.RoomMailboxAccountEnabled -eq $True} | Format-Table Name, UserPrincipalName
    ```
3. チームルームデバイスに関連付けられている会議室メールボックスの名前を検索し、その UPN をメモしておきます。

4. 会議室メールボックスの UPN が見つかったら、次のコマンドを実行します。 `<UserPrincipalName>`会議室のメールボックスの UPN に置き換えます。

    ```powershell
    Set-CalendarProcessing <UserPrincipalName> -ProcessExternalMeetingMessages $True -DeleteComments $False -DeleteSubject $False
    ```

詳細については、「 [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell?view=exchange-ps)」を参照してください。

## <a name="step-2-configure-office-365-threat-protection-and-link-rewrite"></a>手順 2: Office 365 の脅威保護とリンクの書き換えを構成する

ワンタッチの参加エクスペリエンスを有効にするには、サードパーティの会議からの会議の参加リンク情報が会議出席依頼に表示され、読むことができる必要があります。 組織で[Office 365 Advanced Threat Protection 安全なリンク](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links)機能を使用している場合、   またはすべての受信 Url と送信 url をスキャンするサードパーティソリューションを使用している場合は、会議の参加 url を変更して、チームルームデバイスでその会議を認識しないようにすることができます。 この問題が発生しないようにするには、サードパーティの会議サービスの Url を、ATP の安全なリンクの一覧またはサードパーティの URL リライト例外リストに追加する必要があります。

ATP の安全なリンクの "書き換えない" リストにサードパーティの会議サービスの Url を追加するには、「 [atp の安全なリンクを使用して、上書き不可の url リストを設定](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-a-custom-do-not-rewrite-urls-list-with-atp?view=o365-worldwide)する」の手順に従います。 サードパーティのソリューションを使用している場合は、そのソリューションの手順を参照して、URL リライト例外リストに Url を追加します。

ATP の安全なリンクに追加する必要があるエントリの例をいくつか紹介します。リストまたはサードパーティの URL リライト例外の一覧:

- **Cisco WebEx**`*.webex.com*`
- **ズーム** `*zoom.us*` 、 `*zoom.com*``*zoomgov.com*`

ATP の安全なリンクに追加する Url の完全なリストについては、「書き換えない」リストまたはサードパーティの URL リライト例外リストを使用して、会議の招待を承諾するサードパーティの会議サービスプロバイダーにお問い合わせください。 

> [!CAUTION]
> ATP の安全なリンクには、信頼できる Url のみを追加することができます。リストまたはサードパーティの URL リライト例外の一覧。

## <a name="step-3-enable-third-party-meetings-on-device"></a>手順 3: デバイスでサードパーティの会議を有効にする

最後の手順では、各チームルームデバイスがサードパーティの会議に参加できるようにします。 サードパーティの会議に参加するには、ユーザー名とメールアドレスが必要です。 使用する必要があるユーザー名とメールアドレスがデバイスの会議室メールボックスと異なる場合は、デバイスに追加する必要があります。 これは、デバイスの設定または XML 構成ファイルで行うことができます。

### <a name="use-device-settings"></a>デバイスの設定を使う

タッチスクリーンを使用して Teams 室のデバイスを構成するには、次の操作を行います。

1. Microsoft Teams の会議室のデバイスで、[ **その他.** ..] を選択します。
2. [ **設定**] を選択し、デバイス管理者のユーザー名とパスワードを入力します。
3. [ **会議**   ] タブに移動し、[ **Cisco WebEx**]、[ **Zoom**<sup>1</sup>]、または [両方] を選びます。
4. 会議室のメールボックスに関連付けられたユーザー名とメールアドレスを使って会議に参加する場合は、[会議**室の情報を使用**して参加する] を選択します。
5. 代替のユーザー名とメールアドレスを使って会議に参加する場合は、[**ユーザー設定情報を使用**して参加する] を選択し、使用するユーザー名とメールアドレスを入力します。
6. [ **保存して終了**] を選びます。 デバイスが再起動します。

### <a name="use-the-skypesettingsxml-configuration-file"></a>SkypeSettings.xml 構成ファイルを使用する

次の設定は、 `SkypeSettings.xml` にあるファイルに追加でき `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` ます。 ファイルの詳細につい `SkypeSettings.xml` ては、「 [Microsoft Teams のコンソール設定を XML 構成ファイルを使ってリモートで管理する](xml-config-file.md)」を参照してください。

Cisco WebEx 会議を有効にするには、 `WebExMeetingsEnabled` 次のように XML 要素を **True**に設定します。

```xml
<WebExMeetingsEnabled>True</WebExMeetingsEnabled>
```

ズーム<sup>1</sup>会議を有効にするには、 `ZoomMeetingsEnabled` 次のように XML 要素を **True**に設定します。

```xml
<ZoomMeetingsEnabled>True</ZoomMeetingsEnabled>
```

次の XML 要素を使用して、カスタムのユーザー名とメールアドレスを指定して、サードパーティの会議に参加することができます。 指定した値が有効でない場合は、Teams room デバイスによって、[会議室] メールボックスのユーザー名とメールアドレスが既定で使用されます。

```xml
<UseCustomInfoForThirdPartyMeetings>true</UseCustomInfoForThirdPartyMeetings>

<CustomDisplayNameForThirdPartyMeetings>guestname</CustomDisplayNameForThirdPartyMeetings>

<CustomDisplayEmailForThirdPartyMeetings>guest@contoso.com</CustomDisplayEmailForThirdPartyMeetings>
```

> [!NOTE]
> チームルームデバイスから Cisco WebEx 会議に参加するには、cisco WebEx web アプリケーションバージョン WBS 40.7 以降を使って、cisco の会議をホストする必要があります。

<sup>1</sup>ズーム会議の参加は、現在、テクノロジアクセスプログラムを通じて Microsoft Teams のルームのユーザーを選択する場合のみ利用できます (タップ)。
