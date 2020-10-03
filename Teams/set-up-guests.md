---
title: Microsoft Teams へのゲスト アクセスをオンまたはオフにする
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: rafarhi
search.appverid: MET150
ms.custom: ms.teamsadmincenter.orgwidesettings.guestaccess.turnonguestaccessarticle
localization_priority: Normal
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
description: Office 365 管理者として Microsoft Teams のゲストアクセス機能を有効または無効にする方法について説明します。
ms.openlocfilehash: aa4530979054efc5a1aeb2c8fe0afa622b893f9d
ms.sourcegitcommit: 43e5a4aac11c20dd5a4c35b59695f309e1559e82
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/03/2020
ms.locfileid: "48346328"
---
# <a name="turn-on-or-turn-off-guest-access-to-microsoft-teams"></a>Microsoft Teams へのゲスト アクセスをオンまたはオフにする

既定では、ゲスト アクセスはオフになっています。 管理者またはチーム所有者がゲストを追加する前に、チームのゲストアクセスを有効にする必要があります。

ゲストアクセスを有効にすると、変更が反映されるまでに数時間かかることがあります。 ユーザーがチームにゲストを追加しようとするときに "Contact your administrator (管理者にお問い合わせください)" というメッセージが表示される場合、ゲスト アクセスがオンになっていないか、設定が有効になっていないかのいずれかの可能性があります。

> [!IMPORTANT]
> ゲストアクセスを有効にするかどうかは、Azure Active Directory、Microsoft 365、SharePoint、および Teams の設定によって異なります。 詳細については、「 [チームでゲストと共同作業](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)を行う」を参照してください。

## <a name="configure-guest-access-in-the-teams-admin-center"></a>Teams 管理センターでゲスト アクセスを構成する

1. [Microsoft Teams 管理センター](https://admin.teams.microsoft.com/)にサインインします。

2. [**組織全体の設定**] > [**ゲスト アクセス**] を選択します。

3. **[Microsoft Teams でのゲスト アクセスを許可]** を **[オン]** に設定します。

    ![ゲスト アクセスの許可の切り替えをオンに設定する ](media/set-up-guests-image1.png)

4. **[通話]**、**[会議]**、および **[メッセージング]** で、ゲスト ユーザーに何を許可する必要があるかに応じて、各機能の **[オン]** または **[オフ]** を選択します。

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

    ![Teams でのゲストのアクセス権の設定](media/manage-guest-access-image1.png)

5. **[保存]** をクリックします。

## <a name="external-access-federation-vs-guest-access"></a>外部アクセス (フェデレーション) とゲスト アクセス

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="see-also"></a>関連項目

[Microsoft 365 とのセキュリティで保護されたコラボレーションを設定する](https://docs.microsoft.com/microsoft-365/solutions/setup-secure-collaboration-with-teams)

[特定のチームからのゲストユーザーをブロックする](https://docs.microsoft.com/microsoft-365/solutions/per-group-guest-access)

[Set-CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration)