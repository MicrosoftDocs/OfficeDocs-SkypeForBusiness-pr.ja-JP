---
title: Microsoft Teams へのゲストアクセスを有効または無効にする
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
description: Microsoft Teams でのゲスト アクセス機能をオンまたはオフにします。
ms.custom: ms.teamsadmincenter.orgwidesettings.guestaccess.turnonguestaccessarticle
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5bcdbc3251820bdcee860323ad993efc8d6673c0
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41835647"
---
<a name="turn-on-or-turn-off-guest-access-to-microsoft-teams"></a>Microsoft Teams へのゲストアクセスを有効または無効にする
===================================================

既定では、ゲストアクセスはオフになっています。 Office 365 管理者は、管理者またはチーム所有者がゲストを追加する前に、チームのゲストアクセスを有効にする必要があります。 ゲストアクセスを有効にするには、[ゲストアクセスのチェックリスト](guest-access-checklist.md)を使用します。 

ゲストアクセスを有効にすると、変更が有効になるまでに2-24 時間かかります。 ユーザーがチームにゲストを追加しようとしたときに、"管理者に連絡してください" というメッセージが表示された場合、ゲストアクセスが有効になっていないか、設定がまだ有効になっていない可能性があります。

> [!IMPORTANT]
> ゲストアクセスを有効にするかどうかは、Azure Active Directory、Office 365、SharePoint Online、および Teams の設定によって異なります。 詳細については、「 [Teams でゲストアクセスを承認](Teams-dependencies.md)する」を参照してください。



## <a name="configure-guest-access-in-the-teams-admin-center"></a>Teams 管理センターでゲストアクセスを構成する

1.  Microsoft Teams 管理センターにサインインする。

2.  [**組織全体の設定**] > [**ゲスト アクセス**] を選択します。

3. [ **Microsoft Teams でゲストアクセスを許可**する] を **[オン**] に設定します。

    ![ゲスト アクセスの許可の切り替えをオンに設定する ](media/set-up-guests-image1.png)

4.  [**通話**]、[**会議**]、および [**メッセージング**] で、ゲストユーザーのために何を許可するかに応じて、各機能の [**オン**] または [**オフ**] を選択します。

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
    - **会話でミームを使う**-**この設定を**オンにすると、ゲストが会話でミームを使用できるようになります。
    - **会話でステッカーを使用する** – この設定を [**オン**] にすると、ゲストが会話でステッカーを使用することができるようになります。 


5.  **[保存]** をクリックします。

## <a name="use-powershell-to-turn-guest-access-on-or-off"></a>PowerShell を使用してゲスト アクセスをオンまたはオフにする
「 [PowerShell を使用してゲストアクセスを有効または無効にする](guest-access-PowerShell.md#use-powershell-to-turn-guest-access-on-or-off)」を参照してください。


## <a name="video-adding-guests-in-teams"></a>ビデオ: Teams でゲストを追加する

|  |  |
|---------|---------|
| Microsoft Teams でのゲストの追加   | <iframe width="350" height="200" src="https://www.youtube.com/embed/1daMBDyBLZc" frameborder="0" allowfullscreen></iframe>   | 


## <a name="external-access-federation-vs-guest-access"></a>外部アクセス (フェデレーション) とゲスト アクセス

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]