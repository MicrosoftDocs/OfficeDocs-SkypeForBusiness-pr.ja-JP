---
title: Microsoft Teams へのゲスト アクセスをオンまたはオフにする
author: somakbhattacharyya
ms.author: sbhatta
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
ms.openlocfilehash: 6a4b0013e3e3ca31baea21e4e733a9606f3765c6
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885284"
---
<a name="turn-on-or-off-guest-access-to-microsoft-teams"></a>Microsoft Teams へのゲスト アクセスをオンまたはオフにする
======================================

Office 365 管理者は、組織のユーザー (具体的にはチーム所有者) がゲストを追加できるようにするため事前にゲスト機能を有効にする必要があります。 

The guest settings are set in Azure Active Directory. It takes 2 hours to 24 hours for the changes to be effective across your Office 365 organization. If a user sees the message "Contact your administrator" when they try to add a guest to their team, it's likely that either the guest feature hasn't been enabled or the settings aren't effective yet.

> [!IMPORTANT]
> To enable the full experience of the guest access feature, it's important to understand the core authorization dependency between Microsoft Teams, Azure Active Directory, and Office 365. For more information, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).

## <a name="guest-access-vs-external-access-federation"></a>ゲスト アクセスと外部アクセス (フェデレーション)

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="configure-guest-access-in-the-microsoft-teams-admin-center"></a>マイクロソフトのチームの管理センターでのゲスト アクセスを構成します。

1.  マイクロソフトのチームの管理センターにサインインします。

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
       - **高** - ゲストは、Giphy をチャットに挿入することができますが、成人向けコンテンツの挿入については厳格に制限されます。
    - **会話でミームを使用する** – この設定を [**オン**] にすると、ゲストが会話でミームを使用することができるようになります。
    - **会話でステッカーを使用する** – この設定を [**オン**] にすると、ゲストが会話でステッカーを使用することができるようになります。 


5.  [**保存**] をクリックします。

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
