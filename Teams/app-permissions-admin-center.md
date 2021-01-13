---
title: Microsoft Teams 管理センターでアプリのアクセス許可を表示し、管理者の同意を付与する
author: cichur
ms.author: v-cichur
ms.reviewer: vaibhava
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: アプリから要求されたアクセス許可を表示し、Microsoft Teams 管理センターの [アプリの管理] ページでアプリに管理者の同意を付与する方法について説明します。
localization_priority: Normal
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6ec41760a7edd7de52d15995f39365b300cd797e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827537"
---
# <a name="view-app-permissions-and-grant-admin-consent-in-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターでアプリのアクセス許可を表示し、管理者の同意を付与する

Microsoft Teams [管理センターの](manage-apps.md) [アプリの管理] ページは、組織のすべての Teams アプリを表示および管理する場所です。 たとえば、アプリの組織レベルの状態とプロパティの表示、組織のアプリ ストアへの新しいカスタム アプリの承認またはアップロード、組織レベルでのアプリのブロックまたは許可、および組織全体のアプリ設定の管理を行います。

ここでは、データへのアクセス許可を要求し、アプリのリソース固有の同意 (RSC) アクセス許可を表示するアプリに対する組織全体の管理者の同意を付与することもできます。

## <a name="grant-org-wide-admin-consent-to-an-app"></a>組織全体の管理者にアプリへの同意を付与する

グローバル管理者の場合は、組織内のすべてのユーザーに代わってアクセス許可を要求するアプリを確認し、同意を付与できます。 この操作を行って、ユーザーがアプリの起動時にアプリから要求されたアクセス許可を確認して承諾する必要が生じなかったりします。 また、Azure Active Directory (Azure [](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent) AD) のユーザーの同意設定によっては、会社のデータにアクセスするアプリに対する同意を許可されないユーザーが存在する場合があります。

アプリから要求されたアクセス許可の例には、チームに保存されている情報の読み取り、ユーザーのプロファイルの読み取り、ユーザーの代わりにメールを送信する機能があります。 詳細については、Microsoft ID プラットフォーム エンドポイントのアクセス許可と同意 [を参照してください](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent)。 

[ **アクセス許可]** 列は、アプリに同意が必要なアクセス許可を持っているかどうかを示します。 同意が **必要なアクセス** 許可を持つ Azure ADアプリごとに [詳細の表示] リンクが表示されます。 これは、カスタム アプリとサード パーティ製アプリにのみ適用されます。 このリンクは表示されません。または、Microsoft が発行するアプリに対して管理者の同意を付与する必要があります。

:::image type="content" source="media/app-perm-admin-center-permissions-column.png" alt-text="[アプリの管理] ページの [アクセス許可] 列のスクリーンショット":::

アプリに対する組織全体の同意を付与するには、次の手順を実行します。

1. Microsoft Teams 管理センターの左側のナビゲーションで、Teams アプリの [アプリの **管理]**  >  **に移動します**。
2. 次のいずれかの操作を行います。
    - 目的のアプリを検索し、アプリ名をクリックしてアプリの詳細ページに移動し、[権限] タブ **を選択** します。
    - アクセス許可 **列を降** 順で並べ替え、アプリを見つけ、[詳細の表示 **] を選択します**。 これにより、アプリの詳細ページ **の** [アクセス許可] タブに移動します。

3. 組織 **全体のアクセス許可の下で、[** アクセス許可と同意 **のレビュー] を選択します**。

    :::image type="content" source="media/app-perm-admin-center-org-wide.png" alt-text="アプリの [権限] タブの組織全体のアクセス許可のスクリーンショット":::

    これを行うには、グローバル管理者である必要があります。 このオプションは、Teams サービス管理者は使用できません。

4. [アクセス **許可] タブ** で、アプリから要求されたアクセス許可を確認します。

    :::image type="content" source="media/app-perm-admin-center-org-wide-permissions.png" alt-text="アプリから要求されたアクセス許可のスクリーンショット":::

    > [!IMPORTANT]
    > アプリに対する組織全体の同意を付与すると、アプリは組織のデータにアクセスできます。 同意を付与する前に、アプリから要求されたアクセス許可を慎重に確認してください。
5. アプリから要求されたアクセス許可に同意する場合は、[承諾] をクリックして同意を付与します。 要求されたアプリのアクセス許可が付与された場合は、ページの上部にバナーが一時的に表示されます。 これで、アプリは組織内のすべてのユーザーに対して指定されたリソースにアクセスできます。アクセス許可の確認を求めるメッセージは他に表示されません。

アクセス許可を承諾すると、アプリの詳細ページの組織全体のアクセス許可の下に、同意が許可されたというメッセージが表示されます。 アプリのアクセス許可に関する詳細を表示するには **、Azure Active Directory** リンクをクリックして、Azure AD ポータルでアプリのページに移動します。

:::image type="content" source="media/app-perm-admin-center-org-wide-accepted.png" alt-text="同意が付与された場合に表示されるメッセージのスクリーンショット":::

組織内のユーザーが同意を許可されている場合、および 1 人または複数のユーザーが特定のアプリに対する同意を許可した場合は、同意が付与されたことを知らせる同じメッセージと、Azure AD ポータルのアプリのページへの Azure Active Directory リンクも表示されます。

> [!NOTE]
> ただし、Teamsサービス管理者は [アクセス許可と同意の確認] オプションを使用できません。また、アプリに対する組織全体の管理者の同意を付与することはできませんが、Teams サービス管理者はアプリの [アクセス許可] タブでコンテンツを表示できます。 たとえば、Teams サービス管理者は Azure **Active Directory** リンクをクリックして、Azure Active Directory ポータルでアプリのアクセス許可の詳細ADできます。 

## <a name="view-resource-specific-consent-permissions-of-an-app"></a>アプリのリソース固有の同意アクセス許可を表示する

RSC アクセス許可を使用すると、チーム所有者はアプリがチームのデータにアクセスして変更する同意を付与できます。 RSC アクセス許可は、特定のチームでアプリが実行できる操作を定義する Teams 固有の権限です。 RSC アクセス許可の例としては、チャネルの作成と削除、チームの設定の取得、チャネル タブの作成と削除の機能があります。 

RSC アクセス許可は、Azure マニフェストではなく、アプリ マニフェストAD。 アプリをチームに追加すると、RSC アクセス許可に同意したと見なされます。 詳細については、リソース固有 [の同意 (RSC) を参照してください](https://docs.microsoft.com/microsoftteams/platform/graph-api/rsc/resource-specific-consent)。

グローバル管理者と Teams サービス管理者は、アプリの詳細ページの [アクセス許可] タブで、アプリの RSC アクセス許可を表示できます。 

アプリの RSC アクセス許可を表示するには、次の手順を実行します。

1. Microsoft Teams 管理センターの左側のナビゲーションで、Teams アプリの [アプリの **管理]**  >  **に移動します**。
2. 目的のアプリを検索し、アプリ名をクリックしてアプリの詳細ページに移動し、[権限] タブ **を選択** します。
3. **Microsoft Graph のリソース固有の同意 (RSC)** アクセス許可の下で、アプリから要求された RSC アクセス許可を確認します。

    :::image type="content" source="media/app-perm-admin-center-rsc.png" alt-text="アプリの RSC アクセス許可のスクリーンショット":::

## <a name="known-issues"></a>既知の問題

### <a name="the-view-details-link-isnt-displayed-in-the-permissions-column-for-some-third-party-apps-that-request-permissions"></a>アクセス許可を要求するサード パーティ製アプリの [アクセス許可] 列に [詳細の表示] リンクが表示されない

現在、アクセス許可を要求している Azure アカウントに登録されているサード パーティ製アプリの中には、アクセス許可を確認して同意を付与AD利用できる機能はありません。 [詳細の表示 **] リンクの** 代わりに、[アクセス許可 **--** ] 列 **に表示** されます。 現在、ISV と取り組み、アプリでこの機能を有効にしています。

## <a name="related-topics"></a>関連項目

- [Microsoft Teams 管理センターでアプリを管理する](manage-apps.md)
- [Microsoft ID プラットフォーム エンドポイントのアクセス許可と同意](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent)
- [Teams でのリソース固有の同意](resource-specific-consent.md)
- [リソース固有の同意 (RSC)](https://docs.microsoft.com/microsoftteams/platform/graph-api/rsc/resource-specific-consent)
- [Teams アプリのライフサイクル内を移動](https://aka.ms/PR132) する (Ignite 2020 セッション)


