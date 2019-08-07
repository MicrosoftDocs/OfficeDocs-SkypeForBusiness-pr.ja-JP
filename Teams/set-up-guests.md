---
title: Microsoft Teams へのゲストアクセスを有効または無効にする
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 03/06/2019
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
description: Microsoft Teams でのゲスト アクセス機能をオンまたはオフにします。
ms.custom:
- NewAdminCenter_Update
f1keywords: ms.teamsadmincenter.orgwidesettings.guestaccess.turnonguestaccessarticle
appliesto:
- Microsoft Teams
ms.openlocfilehash: 240e93d5f6329090940e6bf49cb2d6a4ee46ce2f
ms.sourcegitcommit: ca1ac291ab6394f050b9b517d9f3906f3a970b04
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2019
ms.locfileid: "35221452"
---
<a name="turn-on-or-turn-off-guest-access-to-microsoft-teams"></a>Microsoft Teams へのゲストアクセスを有効または無効にする
===================================================

Office 365 管理者は、組織のユーザー (具体的にはチーム所有者) がゲストを追加できるようにするため事前にゲスト機能を有効にする必要があります。

ゲスト設定は Azure Active Directory で設定します。その変更が Office 365 組織全体で有効になるまでに 2 時間から 24 時間かかります。ユーザーがチームにゲストを追加しようとするときに「Contact your administrator (管理者にお問い合わせください)」というメッセージが表示される場合、ゲスト機能が使用できる状態になっていないか、設定が有効になっていないかのいずれかの可能性があります。

> [!IMPORTANT]
> ゲストアクセス機能の完全なエクスペリエンスを有効にするには、Microsoft Teams、Azure Active Directory、Office 365との間で主な承認の依存関係を理解することが重要です。詳しくは、[Microsoft Teams でゲストアクセスを承認する](Teams-dependencies.md)を参照してください。

## <a name="guest-access-vs-external-access-federation"></a>ゲスト アクセスと外部アクセス (フェデレーション)

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="configure-guest-access-in-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターでゲスト アクセスをチームを設定する

1.  Microsoft Teams 管理センターにサインインする。

2.  [**組織全体の設定**] > [**ゲスト アクセス**] を選択します。

3. [**Microsoft Teams でのゲスト アクセスを許可**] の切り替えスイッチを [**オン**] に設定します。

    ![ゲスト アクセスの許可の切り替えをオンに設定する ](media/set-up-guests-image1.png)

4.  ゲスト ユーザーにどの機能を許可するかに応じて、[**通話**]、[**会議**]、および [**メッセージング**] の切り替えスイッチを [**オン**] または [**オフ**] に設定します。

    - **プライベート通話の発信** – この設定を [**オン**] にするとゲストがピアツーピアの通話を発信することができるようになります。
    - **IP ビデオを許可** - この設定を [**オン**] に切り替えると、ゲストは自分たちの通話および会議でビデオを使用することができるようになります。
    - **画面共有モード** – この設定は、ゲスト ユーザーが画面共有を利用可能かどうかを制御します。 
       - この設定を [**無効**] にすると、Teams で画面を共有するゲストの機能は削除されます。 
       - この設定を [**1 つのアプリケーション**] にすると、個別のアプリケーションの共有を行えるようになります。 
       - この設定を [**画面全体**] にすると、完全な画面共有を行えるようになります。
    - **会議の開始を許可** – この設定を [**オン**] にすると、Microsoft Teams でゲストが会議の開始機能を使用することができるようになります。
    - **送信済みメッセージの編集** - この設定を [**オン**] にすると、ゲストが以前送信したメッセージを編集することができるようになります。
    - **ゲストによる送信済みメッセージの削除** - この設定を [**オン**] にすると、ゲストが以前送信したメッセージを削除することができるようになります。
    - **チャット** – この設定を [**オン**] にすると、ゲストが Teams でのチャット機能を使用することができるようになります。
    - **会話で Giphys を使用する** – この設定を [**オン**] にすると、ゲストが会話で Giphys を使用することができるようになります。 Giphy は、ユーザーがアニメーション GIF ファイルを検索および共有することができる、オンライン データベースおよび検索エンジンです。 各 Giphy にはコンテンツ評価が割り当てられています。
    - **Giphy のコンテンツ評価** –  ドロップダウン リストから次の評価を選択します。
       - **すべてのコンテンツを許可** - ゲストは、コンテンツ評価に関係なく、すべての Giphy をチャットに挿入することができるようになります。
       - **中** - ゲストは、Giphy をチャットに挿入することができますが、成人向けコンテンツの挿入についてはある程度制限されます。
       - **Strict** –ゲストはチャットに giphy を挿入できますが、成人向けコンテンツの挿入は制限されます。
    - **会話でミームを使う**-この設定**** をオンにすると、ゲストが会話でミームを使用できるようになります。
    - **会話でステッカーを使用する** – この設定を [**オン**] にすると、ゲストが会話でステッカーを使用することができるようになります。 


5.  **[保存]** をクリックします。

## <a name="use-powershell-to-turn-guest-access-on-or-off"></a>PowerShell を使用してゲスト アクセスをオンまたはオフにする

1.  Skype for Business Online PowerShell モジュールを次からダウンローします https://www.microsoft.com/en-us/download/details.aspx?id=39366
 
2.  PowerShell セッションを Skype for Business Online エンドポイントに接続します。

    ```
    Import-Module SkypeOnlineConnector
    $Cred = Get-Credential
    $CSSession = New-CsOnlineSession -Credential $Cred
    Import-PSSession -Session $CSSession
    ```
3.  設定を確認して、`AllowGuestUser` が `$False` の場合は、[Set-CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) コマンドレットを使用して `$True` に設定します。

    ```
    Get-CsTeamsClientConfiguration

    Identity                         : Global
    AllowEmailIntoChannel            : True
    RestrictedSenderList             :
    AllowDropBox                     : True
    AllowBox                         : True
    AllowGoogleDrive                 : True
    AllowShareFile                   : True
    AllowOrganizationTab             : True
    AllowSkypeBusinessInterop        : True
    ContentPin                       : RequiredOutsideScheduleMeeting
    AllowResourceAccountSendMessage  : True
    ResourceAccountContentAccess     : NoAccess
    AllowGuestUser                   : True
    AllowScopedPeopleSearchandAccess : False
    
    Set-CsTeamsClientConfiguration -AllowGuestUser $True -Identity Global
    ```
これで、自分の組織の Teams にゲスト ユーザーを入れることができるようになりました。

## <a name="more-information"></a>詳細情報

ゲスト アクセスの詳細については以下のビデオをご覧ください。

|  |  |
|---------|---------|
| Microsoft Teams でのゲストの追加   | <iframe width="350" height="200" src="https://www.youtube.com/embed/1daMBDyBLZc" frameborder="0" allowfullscreen></iframe>   | 
