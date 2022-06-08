---
title: Microsoft Teams でゲスト アクセスを有効または無効にする
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
ms.openlocfilehash: 935fac44863ef2c3da4a9fc4f07fcd7e34265024
ms.sourcegitcommit: cd9a1f7afaaf053741c81022e7052bf6f8008fcc
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2022
ms.locfileid: "65370810"
---
# <a name="turn-guest-access-in-microsoft-teams-on-or-off"></a>Microsoft Teams でゲスト アクセスを有効または無効にする

この記事では、Teams でゲスト アクセス設定 (通話、会議、チャットなど) を構成する方法について説明します。 Teams でのゲスト アクセスには、Azure AD、Microsoft 365 グループ、SharePoint の設定など、Microsoft 365 の他の設定を構成する必要があります。 ゲストを Teams に招待する準備ができている場合は、次のいずれかをお読みください。

- 一般的な使用のためにチームのゲスト アクセスを構成する方法については、「 [チームでゲストと共同作業する](/microsoft-365/solutions/collaborate-as-team)」を参照してください。
- Azure Active Directory を使用するパートナー組織とコラボレーションし、ゲストがチーム アクセスに自己登録できるようにするには、「[管理されたゲストで B2B エクストラネットを作成する](/microsoft-365/solutions/b2b-extranet)」を参照してください。

> [!NOTE]
> ただ他の組織の人々を見つけ、電話をかけ、チャットし、会議を設定する場合は、[外部アクセス](manage-external-access.md) を使用します。

## <a name="configure-guest-access-in-the-teams-admin-center"></a>Teams 管理センターでゲスト アクセスを構成する

1. [Microsoft Teams 管理センター](https://admin.teams.microsoft.com/)にサインインする。

2. **Users** > **Guest access** を選択します。

3. **[Teams へのゲスト アクセスを許可する]** を **[オン]** に設定します。

    ![ゲスト アクセスの許可の切り替えをオンに設定する。](media/guest-access-setting.png)

4. **[通話]**、**[会議]**、および **[メッセージング]** で、ゲストに何を許可する必要があるかに応じて、各機能の **[オン]** または **[オフ]** を選択します。

      - **プライベート通話の発信** – この設定を [**オン**] にするとゲストがピアツーピアの通話を発信することができるようになります。
      - **IP ビデオ** - この設定を [**オン**] に切り替えると、ゲストは自分たちの通話および会議でビデオを使用することができるようになります。
      - **画面共有モード** – この設定は、ゲストが画面共有を利用可能かどうかを制御します。
          - この設定を [**無効**] にすると、Teams で画面を共有するゲストの機能は削除されます。
          - この設定を [**1 つのアプリケーション**] にすると、個別のアプリケーションの共有を行えるようになります。
          - この設定を [**画面全体**] にすると、完全な画面共有を行えるようになります。
      - **会議の開始** – この設定を [**オン**] にすると、Microsoft Teams でゲストが会議の開始機能を使用することができるようになります。
      - **送信済みメッセージの編集** - この設定を [**オン**] にすると、ゲストが以前送信したメッセージを編集することができるようになります。
      - **送信済みメッセージの削除** - この設定を [**オン**] にすると、ゲストが以前送信したメッセージを削除することができるようになります。
      - **チャットの削除** - ゲストがチャット会話全体を削除できるようにするには、この設定を **オン** にします。
      - **チャット** – この設定を [**オン**] にすると、ゲストが Teams でのチャット機能を使用することができるようになります。
      - **会話で Giphys を使用** – この設定を [**オン**] にすると、ゲストが会話で Giphys を使用することができるようになります。 Giphy は、ユーザーがアニメーション GIF ファイルを検索および共有することができる、オンライン データベースおよび検索エンジンです。 各 Giphy にはコンテンツ評価が割り当てられています。
      - **Giphy のコンテンツ評価** –  ドロップダウン リストから次の評価を選択します。
          - **すべてのコンテンツを許可** - ゲストは、コンテンツ評価に関係なく、すべての Giphy をチャットに挿入することができるようになります。
          - **中** - ゲストは、Giphy をチャットに挿入することができますが、成人向けコンテンツの挿入についてはある程度制限されます。
          - **高** - ゲストは、Giphy をチャットに挿入することができますが、成人向けコンテンツの挿入については制限されます。
      - **会話でミームを使用** – この設定を [**オン**] にすると、ゲストが会話でミームを使用することができるようになります。
      - **会話でステッカーを使用** – この設定を [**オン**] にすると、ゲストが会話でステッカーを使用することができるようになります。
      - **メッセージのインマーシブ リーダー** - この設定を [**オン**] に切り替えて、ゲストが [Teams 内でイマーシブ リーダー](https://support.microsoft.com/topic/a700c0d0-bc53-4696-a94d-4fbc86ac7a9a)を使用できるようにします。

    ![Teams でのゲストのアクセス権の設定。](media/manage-guest-access-image1.png)

5. **[保存]** を選択します。

## <a name="turning-guest-access-off"></a>ゲスト アクセスをオフにする

Teams でゲスト アクセスをオフにすると、既存のゲストはチームにアクセスできなくなります。 ただし、チームから削除されることはありません。 チーム内のユーザーには引き続き表示され、@メンションできます。 Teams のゲスト アクセスを再度オンにすると、アクセスを回復します。

ゲスト アクセスをオフのままにする場合は、チームの所有者に、チームからゲスト アカウントを手動で削除するようにアドバイスすることをお勧めします。 これらのゲストはアクセスできませんが、チーム内にアカウントが表示されると、チーム内の他のユーザーが混乱する可能性があります。


## <a name="see-also"></a>関連項目

[Microsoft 365 とセキュリティで保護された共同作業を設定する](/microsoft-365/solutions/setup-secure-collaboration-with-teams)

[特定のチームのゲストをブロックする](/microsoft-365/solutions/per-group-guest-access)

[Set-CsTeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)
