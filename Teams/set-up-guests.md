---
title: Microsoft Teams へのゲスト アクセスをオンまたはオフにする
author: LaithAlShamri
ms.author: lolaj
manager: serdars
ms.date: 10/18/2018
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
ms.openlocfilehash: 532886659d88707d8cd63c7c268dc9929f937b1c
ms.sourcegitcommit: 4f93bad9696db15de86c98a55398537c476e55d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2018
ms.locfileid: "25633752"
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

4.  ゲスト ユーザーを許可する機能によって**オン**または**オフ**を**呼び出し**、**会議**、および**メッセージ**の表示を切り替えます。 を設定します。

    - **秘密の呼び出しを行う**: ピア ツー ピアの呼び出しを行うには、来園者を許可する**に**は、この設定を有効にします。
    - **IP ビデオを許可する**が、通話や会議でビデオを使用するには、来園者を許可する**に**は、この設定を有効にします。
    - **画面モードを共有する**: この設定は、画面をゲスト ユーザーの共有の可用性を制御します。 
       - **無効になっている**チームでの画面を共有するには、来園者の機能を削除するには、この設定を有効にします。 
       - 個々 のアプリケーションの共有を許可する**単一のアプリケーション**にこの設定を有効にします。 
       - **全体の画面**の完了] 画面の共有を許可するのには、この設定を有効にします。
    - **により即時**に即時会議の機能を使用して、マイクロソフトのチームでは、来園者を許可する**上で**この設定を有効にします。
    - **編集メッセージを送信する**-この設定**を**編集するには、来園者を許可するが、メッセージを有効にする送信済みです。
    - 以前に送信を**来園者が送信したメッセージを削除できます**: この設定**を**削除するには、来園者を許可するが、メッセージを有効にするには。
    - **チャット**– を提供する**上で**この設定を有効にするには、チームでのチャットを使用することが来園者します。
    - **会話に Giphys を使用して**– 会話で Giphys を使用するには、来園者を許可する**に**は、この設定を有効にします。 Giphy は、オンライン データベースと検索エンジンを検索し、アニメーション GIF ファイルを共有することができます。 各 Giphy は、コンテンツの格付けを割り当てられます。
    - **Giphy コンテンツの規制**: ドロップ ダウン リストからレベルを選択:
       - **すべてのコンテンツを許可する**、来園者はコンテンツの規制に関係なく、チャットのすべての Giphys を挿入するのにはできるようになります。
       - **中程度**の来園者は、チャット、Giphys を挿入することになりますが、成人向けコンテンツからやや制限されています。
       - **Strict** : 来園者は、チャット、Giphys を挿入することになりますが、成人向けコンテンツを挿入することから厳密に制限されます。
    - **Memes の会話の中を使用して**の会話に Memes を使用するには、来園者を許可する**に**は、この設定を有効にします。
    - **会話にステッカーを使用して**– 会話にステッカーを使用するには、来園者を許可する**に**は、この設定を有効にします。 


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

## <a name="more-information"></a>追加情報

ゲスト アクセスの詳細については次のビデオを視聴します。

|  |  |
|---------|---------|
| Microsoft Teams でのゲストの追加   | <iframe width="350" height="200" src="https://www.youtube.com/embed/1daMBDyBLZc" frameborder="0" allowfullscreen></iframe>   | 
