---
title: Microsoft Teams へのゲスト アクセスをオンまたはオフにする
author: LaithAlShamri
ms.author: lolaj
manager: serdars
ms.date: 10/11/2018
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: sbhatta
search.appverid: MET150
description: Microsoft Teams でのゲスト アクセス機能をオンまたはオフにします。
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3ab67b3fa9ad58c1aa3e8fdd254e3b3515743b4c
ms.sourcegitcommit: 9dd5d8fe6888f0c7d2df1e40fdd8b4c80512f8f9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/11/2018
ms.locfileid: "25498122"
---
<a name="turn-on-or-off-guest-access-to-microsoft-teams"></a>Microsoft Teams へのゲスト アクセスをオンまたはオフにする
======================================

Office 365 管理者は、組織のユーザー (具体的にはチーム所有者) がゲストを追加できるようにするため事前にゲスト機能を有効にする必要があります。 

ゲスト設定は Azure Active Directory で設定します。 その変更が Office 365 組織全体で有効になるまでに 2 時間から 24 時間かかります。 ユーザーがチームにゲストを追加しようとするときに「Contact your administrator (管理者にお問い合わせください)」というメッセージが表示される場合、ゲスト機能が使用できる状態になっていないか、設定が有効になっていないかのいずれかの可能性があります。


> [!IMPORTANT]
> ゲスト アクセス機能の完全なエクスペリエンスを有効にするためには、Microsoft Teams、Azure Active Directory、および Office 365 の間での中心的な承認の依存関係を理解することが重要です。 詳細については、「[Microsoft Teams でのゲスト アクセスを承認する](Teams-dependencies.md)」をご覧ください。

## <a name="configure-guest-access-in-the-teams--skype-for-business-admin-center"></a>ビジネス管理センターのチームと Skype でゲスト アクセスを構成します。

1.  ビジネス管理センターは、チームと Skype にサインインします。

2.  **組織全体の設定**を選択して > **のゲスト アクセス**します。

3. **マイクロソフトのチームでのゲスト アクセスを許可する**オン/オフ スイッチを**オン**に設定します。

    ![ゲスト アクセスのスイッチが On に設定できるようにします。 ](media/set-up-guests-image1.png)

4.  **呼び出し**、**会議**、および**メッセージング**を**オン**または**オフ**をするを許可するアクセス権によって、表示を切り替えます。 を設定します。

5.  [**保存**] をクリックします。

## <a name="use-powershell-to-turn-guest-access-on-or-off"></a>PowerShell を使用して、ゲスト アクセスを有効または無効にするには

1.  ビジネス オンライン PowerShell モジュールからの Skype をダウンロードします。https://www.microsoft.com/en-us/download/details.aspx?id=39366
 
2.  PowerShell セッションを Skype のオンライン ビジネスのエンドポイントに接続します。

    ```
    Import-Module SkypeOnlineConnector
    $Cred = Get-Credential
    $CSSession = New-CsOnlineSession -Credential $Cred
    Import-PSSession -Session $CSSession
    ```
3.  構成を確認し、`AllowGuestUser`は、 `$False`、[セット CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)コマンドレットを使用] に設定して`$True`。

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
    AllowTBotProactiveMessaging      : False
    ContentPin                       : RequiredOutsideScheduleMeeting
    AllowResourceAccountSendMessage  : True
    ResourceAccountContentAccess     : NoAccess
    AllowGuestUser                   : True
    AllowScopedPeopleSearchandAccess : False
    
    Set-CsTeamsClientConfiguration -AllowGuestUser $True -Identity Global
    ```
ゲスト ユーザーは、組織のチームのようになりましたができます。

## <a name="more-information"></a>詳細情報

ゲスト アクセスの詳細については次のビデオを視聴します。

|  |  |
|---------|---------|
| Microsoft Teams でのゲストの追加   | <iframe width="350" height="200" src="https://www.youtube.com/embed/1daMBDyBLZc" frameborder="0" allowfullscreen></iframe>   | 
