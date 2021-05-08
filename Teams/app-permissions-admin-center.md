---
title: アプリのアクセス許可を表示し、管理センターで管理者Microsoft Teams付与する
author: cichur
ms.author: v-cichur
ms.reviewer: vaibhava
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: アプリによって要求されたアクセス許可を表示し、管理センターの [アプリの管理] ページでアプリに管理者の同意Microsoft Teamsします。
localization_priority: Normal
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2833a548ccf66b327d9feb71155f1ed33a671f1c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094659"
---
# <a name="view-app-permissions-and-grant-admin-consent-in-the-microsoft-teams-admin-center"></a>アプリのアクセス許可を表示し、管理センターで管理者Microsoft Teams付与する

Microsoft Teams [](manage-apps.md)管理センターの [アプリの管理] ページでは、組織のすべてのアプリTeams表示および管理できます。 たとえば、アプリの組織レベルの状態とプロパティの表示、組織のアプリ ストアへの新しいカスタム アプリの承認またはアップロード、組織レベルでのアプリのブロックまたは許可、組織全体のアプリ設定の管理を行います。

ここでは、データへのアクセス許可を要求し、アプリのリソース固有の同意 (RSC) アクセス許可を表示するアプリに対して、組織全体の管理者の同意を付与することもできます。

## <a name="grant-org-wide-admin-consent-to-an-app"></a>組織全体の管理者の同意をアプリに付与する

グローバル管理者の場合は、組織内のすべてのユーザーに代わってアクセス許可を要求するアプリを確認し、同意を付与できます。 ユーザーがアプリの起動時にアプリから要求されたアクセス許可を確認して受け入れる必要が生じないので、この操作を行います。 さらに、Azure Active Directory (Azure AD)[](/azure/active-directory/manage-apps/configure-user-consent)のユーザーの同意設定によっては、会社のデータにアクセスするアプリに同意を付与できないユーザーもいます。

アプリによって要求されるアクセス許可の例には、チームに格納されている情報の読み取り、ユーザーのプロファイルの読み取り、ユーザーに代わって電子メールを送信する機能が含まれます。 詳細については、エンドポイントの[アクセス許可と](/azure/active-directory/develop/v2-permissions-and-consent)同意に関するページMicrosoft ID プラットフォームしてください。 

[ **アクセス許可]** 列は、アプリに同意が必要なアクセス許可を持っているかどうかを示します。 同意が必要な **アクセス許可を** 持つ Azure ADに登録されている各アプリの [詳細の表示] リンクが表示されます。 これは、カスタム アプリとサード パーティ製アプリにのみ適用されます。 このリンクは表示されません。または、Microsoft によって発行されたアプリに対して管理者の同意を付与する必要があります。

:::image type="content" source="media/app-perm-admin-center-permissions-column.png" alt-text="[アプリの管理] ページの [アクセス許可] 列のスクリーンショット":::

組織全体の同意をアプリに付与するには、次の手順に従います。

1. Microsoft Teams 管理センターの左側のナビゲーションで、**[Teams アプリ]** > **[アプリを管理]** の順に移動します。
2. 次のいずれかの操作を行います。
    - 目的のアプリを検索し、アプリ名をクリックしてアプリの詳細ページに移動し、[アクセス許可] **タブを選択** します。
    - [アクセス **許可] 列を** 降順に並べ替え、アプリを検索し、[詳細の表示] **を選択します**。 これにより、アプリの詳細ページ **の** [アクセス許可] タブに移動します。

3. [ **組織全体のアクセス許可] で、[** アクセス許可と **同意の確認] を選択します**。

    :::image type="content" source="media/app-perm-admin-center-org-wide.png" alt-text="アプリの [アクセス許可] タブの組織全体のアクセス許可のスクリーンショット":::

    これを行うには、グローバル管理者である必要があります。 このオプションは、サービス管理者Teams使用できません。

4. [アクセス **許可] タブ** で、アプリによって要求されたアクセス許可を確認します。

    :::image type="content" source="media/app-perm-admin-center-org-wide-permissions.png" alt-text="アプリによって要求されたアクセス許可のスクリーンショット":::

    > [!IMPORTANT]
    > アプリに組織全体の同意を付与すると、アプリは組織のデータにアクセスできます。 同意を付与する前に、アプリによって要求されたアクセス許可を慎重に確認してください。
5. アプリによって要求されたアクセス許可に同意する場合は、[同意] をクリック **して** 同意を付与します。 要求されたアクセス許可がアプリに付与されたと知らせるバナーがページの上部に一時的に表示されます。 これで、アプリは組織内のすべてのユーザーに対して指定されたリソースにアクセスできます。アクセス許可の確認を求めるメッセージは他に表示されません。

アクセス許可を承諾すると、アプリの詳細ページの [組織全体のアクセス許可] に、同意が付与されたというメッセージが表示されます。 アプリのアクセス許可に関する詳細を表示するには、[Azure Active Directory] リンクをクリックして、Azure AD ポータルでアプリのページに移動します。 

:::image type="content" source="media/app-perm-admin-center-org-wide-accepted.png" alt-text="同意が付与された場合に表示されるメッセージのスクリーンショット":::

組織内のユーザーが同意を許可され、1 人または複数のユーザーが特定のアプリに同意を許可した場合は、同意が付与され、Azure AD ポータルのアプリのページへの Azure Active Directory リンクを知らせる同じメッセージも表示されます。

> [!NOTE]
> ただし、[アクセス許可と同意の確認] オプションは Teams サービス管理者には使用できません。また、Teams サービス管理者はアプリの [アクセス許可] タブでコンテンツを表示できます。  たとえば、Teams サービス管理者は、[Azure Active Directory] リンクをクリックして、Azure AD ポータルでアプリのアクセス許可の詳細を表示できます。 

## <a name="view-resource-specific-consent-permissions-of-an-app"></a>アプリのリソース固有の同意アクセス許可を表示する

RSC アクセス許可を使用すると、チーム所有者は、アプリがチームのデータにアクセスして変更する同意を付与できます。 RSC のアクセス許可は、アプリTeamsチームで実行できる操作を定義する、詳細で詳細なアクセス許可です。 RSC アクセス許可の例としては、チャネルの作成と削除、チームの設定の取得、チャネル タブの作成と削除が含まれます。 

RSC のアクセス許可は、Azure マニフェストではなく、アプリ マニフェストAD。 アプリをチームに追加するときに、RSC のアクセス許可に同意します。 詳細については、「リソース固有の [同意 (RSC)」を参照してください](/microsoftteams/platform/graph-api/rsc/resource-specific-consent)。

グローバル管理者とTeamsサービス管理者は、アプリの詳細ページの [アクセス許可] タブで、アプリの RSC アクセス許可を表示できます。 

アプリの RSC アクセス許可を表示するには、次の手順に従います。

1. Microsoft Teams 管理センターの左側のナビゲーションで、**[Teams アプリ]** > **[アプリを管理]** の順に移動します。
2. 目的のアプリを検索し、アプリ名をクリックしてアプリの詳細ページに移動し、[アクセス許可] **タブを選択** します。
3. [Microsoft Graph固有の同意 **(RSC)** アクセス許可] で、アプリによって要求された RSC アクセス許可を確認します。

    :::image type="content" source="media/app-perm-admin-center-rsc.png" alt-text="アプリの RSC アクセス許可のスクリーンショット":::

## <a name="known-issues"></a>既知の問題

### <a name="the-view-details-link-isnt-displayed-in-the-permissions-column-for-some-third-party-apps-that-request-permissions"></a>アクセス許可を要求する一部のサード パーティ製アプリの [アクセス許可] 列に [詳細の表示] リンクが表示されない

現時点では、アクセス許可を確認し、同意を付与する機能は、アクセス許可を要求する Azure ADに登録されているサード パーティ製アプリでは使用できません。 [詳細の表示 **] リンク** の代わりに、[アクセス許可 **--** ] 列 **に表示** されます。 ISV と取り組み、アプリでこの機能を有効にしています。

## <a name="related-topics"></a>関連トピック

- [管理センターでアプリMicrosoft Teams管理する](manage-apps.md)
- [Microsoft ID プラットフォーム エンドポイントのアクセス許可と同意](/azure/active-directory/develop/v2-permissions-and-consent)
- [リソース固有の同意 (Teams](resource-specific-consent.md)
- [リソース固有の同意 (RSC)](/microsoftteams/platform/graph-api/rsc/resource-specific-consent)
- [アプリのライフサイクルTeams移動](https://aka.ms/PR132)する (Ignite 2020 セッション)