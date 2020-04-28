---
title: Microsoft Teams へのゲスト アクセスをオンまたはオフにする
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
description: Office 365 管理者として Microsoft Teams のゲストアクセス機能を有効または無効にする方法について説明します。
ms.custom: ms.teamsadmincenter.orgwidesettings.guestaccess.turnonguestaccessarticle
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: e634c58d34787a76477591ab4262c703e5773cbe
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "43903792"
---
<a name="turn-on-or-turn-off-guest-access-to-microsoft-teams"></a>Microsoft Teams へのゲスト アクセスをオンまたはオフにする
===================================================

既定では、ゲスト アクセスはオフになっています。 管理者やチームの所有者がゲストを追加できるようにするには、Office 365 管理者が Teams へのゲスト アクセスをオンにする必要があります。 ゲスト アクセスをオンにするには、[ゲスト アクセスのチェックリスト](guest-access-checklist.md)を使用します。 

ゲストアクセスを有効にすると、変更が反映されるまでに数時間かかることがあります。 ユーザーがチームにゲストを追加しようとするときに "Contact your administrator (管理者にお問い合わせください)" というメッセージが表示される場合、ゲスト アクセスがオンになっていないか、設定が有効になっていないかのいずれかの可能性があります。

> [!IMPORTANT]
> ゲスト アクセスをオンにする方法は、Azure Active Directory、Office 365、SharePoint Online、Teams の設定により異なります。 詳細については、「[Microsoft Teams でのゲスト アクセスを承認する](Teams-dependencies.md)」を参照してください。



## <a name="configure-guest-access-in-the-teams-admin-center"></a>Teams 管理センターでゲスト アクセスを構成する

1.    Microsoft Teams 管理センターにサインインする。

2.    [**組織全体の設定**] > [**ゲスト アクセス**] を選択します。

3. **[Microsoft Teams でのゲスト アクセスを許可]** を **[オン]** に設定します。

    ![ゲスト アクセスの許可の切り替えをオンに設定する ](media/set-up-guests-image1.png)

4.    **[通話]**、**[会議]**、および **[メッセージング]** で、ゲスト ユーザーに何を許可する必要があるかに応じて、各機能の **[オン]** または **[オフ]** を選択します。

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
       - **高** - ゲストは、Giphy をチャットに挿入することができますが、成人向けコンテンツの挿入については制限されます。
    - **会話でミームを使用する** – この設定を **[オン]** にすると、ゲストが会話でミームを使用することができるようになります。
    - **会話でステッカーを使用する** – この設定を [**オン**] にすると、ゲストが会話でステッカーを使用することができるようになります。 


5.    **[保存]** をクリックします。

## <a name="use-powershell-to-turn-guest-access-on-or-off"></a>PowerShell を使用してゲスト アクセスをオンまたはオフにする
「[PowerShell を使用してゲスト アクセスをオンまたはオフにする](guest-access-PowerShell.md#use-powershell-to-turn-guest-access-on-or-off)」を参照してください。


## <a name="video-adding-guests-in-teams"></a>ビデオ: Teams でのゲストの追加

|  |  |
|---------|---------|
| Microsoft Teams でのゲストの追加   | <iframe width="350" height="200" src="https://www.youtube.com/embed/1daMBDyBLZc" frameborder="0" allowfullscreen></iframe>   | 


## <a name="external-access-federation-vs-guest-access"></a>外部アクセス (フェデレーション) とゲスト アクセス

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]