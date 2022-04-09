---
title: Microsoft Teams管理センターでアプリのアクセス許可を表示し、管理者の同意を付与する
author: guptaashish
ms.author: guptaashish
ms.reviewer: vaibhava
manager: prkosh
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: アプリによって要求されたアクセス許可を表示し、Microsoft Teams管理センターの [アプリの管理] ページでアプリに管理者の同意を付与する方法について説明します。
ms.localizationpriority: medium
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 54fbd67fffa666e7f07719305075be264f077976
ms.sourcegitcommit: f3c380f745af4c3aaa2720234860b45696a0c333
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2022
ms.locfileid: "63442273"
---
# <a name="view-app-permissions-and-grant-admin-consent-in-the-microsoft-teams-admin-center"></a>Microsoft Teams管理センターでアプリのアクセス許可を表示し、管理者の同意を付与する

Microsoft Teams管理センターの [[アプリの管理](manage-apps.md)] ページでは、組織のすべてのTeams アプリを表示および管理できます。 たとえば、アプリの組織レベルの状態とプロパティを確認したり、組織のアプリ ストアに新しいカスタム アプリを承認またはアップロードしたり、組織レベルでアプリをブロックまたは許可したり、組織全体のアプリ設定を管理したりできます。

ここでは、データへのアクセス許可を要求し、アプリに対するリソース固有の同意 (RSC) アクセス許可を表示するアプリに組織全体の管理者の同意を付与することもできます。

## <a name="grant-org-wide-admin-consent-to-an-app"></a>組織全体の管理者にアプリへの同意を付与する

グローバル管理者の場合は、組織内のすべてのユーザーに代わってアクセス許可を要求するアプリを確認して同意を与えることができます。 ユーザーがアプリの起動時にアプリから要求されたアクセス許可を確認して承諾する必要がないように、これを行います。 また、Azure Active Directory (Azure AD) のユーザーの[同意設定](/azure/active-directory/manage-apps/configure-user-consent)によっては、会社のデータにアクセスするアプリに同意を許可できないユーザーもあります。

アプリによって要求されるアクセス許可の例には、チームに格納されている情報の読み取り、ユーザーのプロファイルの読み取り、ユーザーの代わりに電子メールを送信する機能などがあります。 詳細については、[Microsoft ID プラットフォーム エンドポイントのアクセス許可と同意に関するページを](/azure/active-directory/develop/v2-permissions-and-consent)参照してください。

**[アクセス許可]** 列は、アプリに同意が必要なアクセス許可があるかどうかを示します。 同意が必要なアクセス許可を持つAzure ADに登録されている各アプリの **[詳細の表示]** リンクが表示されます。 これは、カスタム アプリとサード パーティ製アプリにのみ適用されます。 このリンクが表示されないか、Microsoft によって公開されたアプリの管理者の同意を付与する必要があります。

:::image type="content" source="media/app-perm-admin-center-permissions-column.png" alt-text="[アプリの管理] ページの [アクセス許可] 列のスクリーンショット。":::

組織全体の同意をアプリに付与するには、次の手順に従います。

1. Microsoft Teams 管理センターの左側のナビゲーションで、**[Teams アプリ]** > **[アプリを管理]** の順に移動します。
2. 次のいずれかの操作を行います。
    - 目的のアプリを検索し、アプリ名をクリックしてアプリの詳細ページに移動し、[ **アクセス許可** ] タブを選択します。
    - **[アクセス許可**] 列を降順で並べ替えてアプリを見つけ、[**詳細の表示**] を選択します。 これを行うと、アプリの詳細ページの **[アクセス許可** ] タブに移動します。

3. **組織全体のアクセス許可で**、[**アクセス許可と同意の確認**] を選択します。

    :::image type="content" source="media/app-perm-admin-center-org-wide.png" alt-text="アプリの [アクセス許可] タブの組織全体のアクセス許可のスクリーンショット。":::

    これを行うには、グローバル管理者である必要があります。 このオプションは、Teamsサービス管理者には使用できません。

4. [ **アクセス許可** ] タブで、アプリによって要求されたアクセス許可を確認します。

    :::image type="content" source="media/app-perm-admin-center-org-wide-permissions.png" alt-text="アプリによって要求されたアクセス許可のスクリーンショット。":::

    > [!IMPORTANT]
    > 組織全体の同意をアプリに付与すると、アプリは組織のデータにアクセスできます。 同意を付与する前に、アプリによって要求されたアクセス許可を慎重に確認してください。
5. アプリから要求されたアクセス許可に同意する場合は、[ **同意** ] をクリックして同意を付与します。 要求されたアクセス許可がアプリに付与されたことを知らせるバナーがページの上部に一時的に表示されます。 これで、アプリは組織内のすべてのユーザーに対して指定されたリソースにアクセスできるようになり、他のユーザーにアクセス許可の確認を求めるメッセージは表示されません。

アクセス許可を受け入れた後、同意が付与されたことを知らせるメッセージがアプリの詳細ページに **組織全体のアクセス許可** に表示されます。 アプリのアクセス許可の詳細を表示するには、Azure Active Directoryリンクをクリックして、**Azure AD** ポータルのアプリのページに移動します。

:::image type="content" source="media/app-perm-admin-center-org-wide-accepted-new.png" alt-text="同意が付与されたときに表示されるメッセージのスクリーンショット。":::

組織内のユーザーが同意を許可され、1 人以上のユーザーが特定のアプリに同意を与えた場合は、同じメッセージも表示され、同意が付与されたことと、Azure AD ポータルのアプリのページへのAzure Active Directoryリンクが表示されます。

> [!NOTE]
> サービス管理者Teams **アクセス許可と同意の確認** オプションは使用できず、組織全体の管理者にアプリへの同意を付与することはできませんが、Teamsサービス管理者はアプリの **[アクセス許可**] タブでコンテンツを表示できます。 たとえば、Teams サービス管理者は、Azure Active Directory リンクをクリックして **、Azure AD** ポータルでアプリのアクセス許可の詳細を表示できます。

## <a name="view-resource-specific-consent-permissions-of-an-app"></a>アプリのリソース固有の同意アクセス許可を表示する

RSC アクセス許可を使用すると、チームの所有者は、チームのデータにアクセスして変更するための同意をアプリに付与できます。 RSC のアクセス許可は、アプリが特定のチームで実行できる操作を定義する、きめ細かなTeams固有のアクセス許可です。 RSC アクセス許可の例には、チャネルの作成と削除、チームの設定の取得、チャネル タブの作成と削除が含まれます。

RSC のアクセス許可は、Azure ADではなく、アプリ マニフェストで定義されます。 チームにアプリを追加するときに、RSC アクセス許可に同意を付与します。 詳細については、「 [リソース固有の同意 (RSC)](/microsoftteams/platform/graph-api/rsc/resource-specific-consent)」を参照してください。

グローバル管理者とTeamsサービス管理者は、アプリの詳細ページの [アクセス許可] タブで、アプリの RSC **アクセス許可** を表示できます。

アプリの RSC アクセス許可を表示するには、次の手順に従います。

1. Microsoft Teams 管理センターの左側のナビゲーションで、**[Teams アプリ]** > **[アプリを管理]** の順に移動します。
2. 目的のアプリを検索し、アプリ名をクリックしてアプリの詳細ページに移動し、[ **アクセス許可** ] タブを選択します。
3. **Microsoft Graphリソース固有の同意 (RSC) のアクセス許可** で、アプリによって要求された RSC アクセス許可を確認します。

    :::image type="content" source="media/app-perm-admin-center-rsc-new.png" alt-text="アプリの RSC アクセス許可のスクリーンショット。":::

## <a name="known-issues"></a>既知の問題

### <a name="the-view-details-link-isnt-displayed-in-the-permissions-column-for-some-third-party-apps-that-request-permissions"></a>アクセス許可を要求する一部のサード パーティ製アプリの [アクセス許可] 列に [詳細の表示] リンクが表示されない

現時点では、アクセス許可を要求するAzure ADに登録されているすべてのサード パーティアプリで、アクセス許可を確認して同意を付与する機能は利用できません。 [**詳細の表示**] リンクの代わりに、[**アクセス許可]** 列に表示 **--** されます。 ISV と連携して、アプリに対してこの機能を有効にしています。

## <a name="related-topics"></a>関連項目

- [Microsoft Teams管理センターでアプリを管理する](manage-apps.md)
- [Microsoft ID プラットフォーム エンドポイントのアクセス許可と同意](/azure/active-directory/develop/v2-permissions-and-consent)
- [Teamsでのリソース固有の同意](resource-specific-consent.md)
- [リソース固有の同意 (RSC)](/microsoftteams/platform/graph-api/rsc/resource-specific-consent)
- [Teams アプリライフサイクルのナビゲート](https://aka.ms/PR132) (Ignite 2020 セッション)
