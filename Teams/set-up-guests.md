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
- m365initiative-externalcollab
ms.reviewer: rafarhi
search.appverid: MET150
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
- ms.teamsadmincenter.orgwidesettings.guestaccess.turnonguestaccessarticle
ms.localizationpriority: medium
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
description: Office 365 の管理者として Microsoft Teams のゲスト アクセス機能を有効または無効にする方法について説明します。
ms.openlocfilehash: 2b444b8357d8edef9aaa1c9c8e72ae6762f5bd52
ms.sourcegitcommit: 74d3ab35c344d70b2399bc46a6ced3ab2762a470
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60138243"
---
# <a name="turn-on-or-turn-off-guest-access-to-microsoft-teams"></a>Microsoft Teams へのゲスト アクセスをオンまたはオフにする

> [!Note]
>
> **2021 年 2 月** まで、ゲスト アクセスは既定で無効になっています。 管理者やチームの所有者がゲストを追加できるようにするには、Teams へのゲスト アクセスをオンにする必要があります。 ゲストアクセスを有効にするには、変更を反映するのに、数時間かかりることもあります。 ユーザーがチームにゲストを追加しようとするときに **Contact your administrator (管理者にお問い合わせください)** というメッセージが表示される場合、ゲスト アクセスがオンになっていないか、設定が有効になっていないかのいずれかの可能性があります。
>
> **2021 年 2 月** 以降、この設定を構成していない新規のお客様と既存のお客様へは、Microsoft Teams のゲスト アクセスが既定で有効になります。 この変更を実装すると、Microsoft Teams でゲスト アクセス機能をまだ構成していない場合、その機能はテナントで有効になります。 組織でゲスト アクセスを無効にしたままにする場合は、ゲスト アクセスの設定が **既定のサービス** ではなく **オフ** に設定されていることを確認する必要があります。

> [!IMPORTANT]
> ゲスト アクセスをオンにする方法は、Azure Active Directory、Office 365、SharePoint Online、Teams の設定により異なります。 詳細については、「[チームでゲストと共同作業を行う](/microsoft-365/solutions/collaborate-as-team)」を参照してください。

## <a name="configure-guest-access-in-the-teams-admin-center"></a>Teams 管理センターでゲスト アクセスを構成する

1. [Microsoft Teams 管理センター](https://admin.teams.microsoft.com/)にサインインする。

2. [ユーザー **の**  >  **ゲスト アクセス] を選択します**。

3. [Allow **guest access in Teams] を**[オン]**に設定します**。

    ![[ゲスト アクセス スイッチを許可する] を [オン] に設定します。](media/guest-access-setting.png)

4.  [**通話]、[****会議**]、および[**メッセージング**] で、ゲストに許可する内容に応じて、機能ごとに [オン] または [オフ] を選択します。

      - **プライベート通話の発信** – この設定を [**オン**] にするとゲストがピアツーピアの通話を発信することができるようになります。
      - **IP ビデオ** - ゲストが通話や **会議** でビデオを使用するには、この設定をオンにします。
      - **画面共有モード** – この設定は、ゲストの画面共有の可用性を制御します。
          - この設定を [**無効**] にすると、Teams で画面を共有するゲストの機能は削除されます。
          - この設定を [**1 つのアプリケーション**] にすると、個別のアプリケーションの共有を行えるようになります。
          - この設定を [**画面全体**] にすると、完全な画面共有を行えるようになります。
      - **[今すぐ** 会う]  - ゲストが [今すぐ会う] 機能を使用するには、この設定をオンMicrosoft Teams。
      - **送信済みメッセージの編集** - この設定を [**オン**] にすると、ゲストが以前送信したメッセージを編集することができるようになります。
      - **送信済みメッセージを** 削除する - ゲストが **以前に送信** したメッセージを削除するには、この設定をオンにします。
      - **チャット** – この設定を [**オン**] にすると、ゲストが Teams でのチャット機能を使用することができるようになります。
      - **会話中の Giphy** – この設定を **オンにすると** 、ゲストは会話で Giphys を使用できます。 Giphy は、ユーザーがアニメーション GIF ファイルを検索および共有することができる、オンライン データベースおよび検索エンジンです。 各 Giphy にはコンテンツ評価が割り当てられています。
      - **Giphy のコンテンツ評価** –  ドロップダウン リストから次の評価を選択します。
          - **すべてのコンテンツを許可** - ゲストは、コンテンツ評価に関係なく、すべての Giphy をチャットに挿入することができるようになります。
          - **中** - ゲストは、Giphy をチャットに挿入することができますが、成人向けコンテンツの挿入についてはある程度制限されます。
          - **高** - ゲストは、Giphy をチャットに挿入することができますが、成人向けコンテンツの挿入については制限されます。
      - **会話中のミーム** - この設定をオン **にすると** 、ゲストは会話でミームを使用できます。
      - **会話のステッカー** – この設定をオン **にすると** 、ゲストは会話でステッカーを使用できます。
      - **メッセージのイマーシブ リーダー** - この設定を **オンにすると**、ゲストはイマーシブ リーダーを使用 [Teams。](https://support.microsoft.com/topic/a700c0d0-bc53-4696-a94d-4fbc86ac7a9a)

    ![Teams のゲスト アクセス許可の設定。](media/manage-guest-access-image1.png)

5. **[保存]** を選択します。

## <a name="external-access-federation-vs-guest-access"></a>外部アクセス (フェデレーション) とゲスト アクセス

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="see-also"></a>関連項目

[Microsoft 365 とセキュリティで保護された共同作業を設定する](/microsoft-365/solutions/setup-secure-collaboration-with-teams)

[特定のチームからのゲストをブロックする](/microsoft-365/solutions/per-group-guest-access)

[Set-CsTeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)
