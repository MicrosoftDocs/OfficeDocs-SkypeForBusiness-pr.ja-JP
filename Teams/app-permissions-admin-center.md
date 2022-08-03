---
title: Microsoft Teams 管理センターでアプリのアクセス許可を表示し、管理者の同意を付与する
author: guptaashish
ms.author: guptaashish
ms.reviewer: vaibhava
manager: prkosh
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: アプリから要求されたアクセス許可を表示し、Microsoft Teams 管理センターの [アプリの管理] ページでアプリに管理者の同意を付与する方法について説明します。
ms.localizationpriority: high
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1e3d7ca4f86660080cb387a9d4cd80927f296040
ms.sourcegitcommit: a64574da14969a33a77c7d979ffde452b5b3a531
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/02/2022
ms.locfileid: "67175651"
---
# <a name="view-app-permissions-and-grant-admin-consent-in-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターでアプリのアクセス許可を表示し、管理者の同意を付与する

Microsoft Teams 管理センターの [[アプリの管理]](manage-apps.md) は、管理者が組織用のすべての Teams アプリを表示および管理できる場所です。 たとえば、アプリの組織レベルの状態とプロパティを確認したり、組織のアプリ ストアに新しいカスタム アプリを承認またはアップロードしたり、組織レベルでアプリをブロックまたは許可したり、組織全体のアプリ設定を管理したりできます。

ここでは、データへのアクセス許可を要求し、アプリのリソース固有の同意 (RSC) アクセス許可を表示するアプリに組織全体の管理者の同意を付与することもできます。

## <a name="grant-org-wide-admin-consent-to-an-app"></a>組織全体の管理者にアプリへの同意を付与する

グローバル管理者は、組織内のすべてのユーザーに代わってアクセス許可を要求するアプリを確認し、同意を付与することができます。 こうすることで、ユーザーがアプリの起動時にアプリから要求されたアクセス許可を確認して受け入れる必要はなくなります。 また、Azure Active Directory (Azure AD) のユーザーの[同意設定](/azure/active-directory/manage-apps/configure-user-consent)によっては、一部のユーザーが会社のデータにアクセスするアプリに同意を付与できない場合があります。

アプリから要求されるアクセス許可の例には、チームに格納されている情報の読み取り、ユーザーのプロファイルの読み取り、ユーザーの代わりにメールを送信する機能などがあります。 詳細については、「[Microsoft ID プラットフォーム エンドポイントのアクセス許可と同意](/azure/active-directory/develop/v2-permissions-and-consent)」を参照してください。

"**アクセス許可**" 列は、アプリに同意が必要なアクセス許可があるかどうかを示します。 同意が必要なアクセス許可を持つAzure ADに登録されている各アプリの **[詳細の表示]** リンクが表示されます。 これは、カスタムおよびサード パーティ製アプリにのみ適用されます。 このリンクは、Microsoft が提供するアプリでは使用できません。 また、管理者はそのようなアプリに対する同意を付与する必要はありません。

組織全体の同意をアプリに付与するには、次の手順に従います。

1. Microsoft Teams 管理センターの左側のナビゲーションで、**[Teams アプリ]** > **[[アプリを管理]](https://admin.teams.microsoft.com/policies/manage-apps)** の順に移動します。

1. 次のいずれかの操作を行います。
    * 目的のアプリを検索し、アプリ名をクリックしてアプリの詳細ページに移動し、**[アクセス許可]** タブを選択します。
    * **[アクセス許可]** 列を降順に並べ替え、アプリを検索し、**[詳細の表示]** を選択します。 これにより、アプリの詳細ページ の **[アクセス許可]** タブに移動します。

1. **[組織全体のアクセス許可]** で **[アクセス許可と同意を確認する]** を選択します。

    :::image type="content" source="media/app-perm-admin-center-org-wide.png" alt-text="アプリの [アクセス許可] タブの [組織全体のアクセス許可] のスクリーンショット。":::

    これを行うには、グローバル管理者である必要があります。 このオプションは、Teams サービス管理者は使用できません。

1. **[アクセス許可]** タブで、アプリから要求されるアクセス許可を確認します。

    :::image type="content" source="media/app-perm-admin-center-org-wide-permissions.png" alt-text="アプリから要求されるアクセス許可のスクリーンショット。":::

    > [!IMPORTANT]
    > 組織全体の同意をアプリに付与すると、アプリは組織のデータにアクセスできるようになります。 同意を付与する前に、アプリから要求されたアクセス許可を慎重に確認してください。

1. アプリから要求されたアクセス許可に同意する場合は **[同意する]** をクリックして同意します。 要求されたアクセス許可がアプリに付与されたことを知らせるバナーがページの上部に一時的に表示されます。 これで、アプリは組織内のすべてのユーザーに対して指定されたリソースにアクセスできるようになり、他のユーザーにアクセス許可の確認を求めるメッセージが表示されなくなります。

アクセス許可に同意すると、アプリの詳細ページに **[組織全体のアクセス許可]** の下に、同意が付与されたことを知らせるメッセージが表示されます。 アプリのアクセス許可の詳細を表示するには、**[Azure Active Directory]** リンクをクリックして、Azure AD ポータルのアプリのページに移動します。

:::image type="content" source="media/app-perm-admin-center-org-wide-accepted-new.png" alt-text="同意が付与されたときに表示されるメッセージのスクリーンショット。":::

組織内のユーザーが同意を許可され、1 人以上のユーザーが特定のアプリに同意を付与した場合は、同じメッセージが表示され、同意が付与されたことと、Azure AD portal のアプリのページへの Azure Active Directory リンクも表示されます。

> [!NOTE]
> ただし、**[アクセス許可と同意の確認]** オプションは Teams サービス管理者には使用できず、組織全体の管理者にアプリへの同意を付与することはできませんが、Teams サービス管理者はアプリの **[アクセス許可]** タブでコンテンツを表示できます。 たとえば、Teams サービス管理者は、**Azure Active Directory** リンクをクリックして、Azure AD portal でアプリのアクセス許可の詳細を表示できます。

## <a name="view-resource-specific-consent-permissions-of-an-app"></a>アプリのリソース固有の同意のアクセス許可を表示する

RSC アクセス許可を使用すると、チームの所有者は、アプリがチームのデータにアクセスして変更するための同意を付与できます。 RSC のアクセス許可は、アプリが特定のチームで何を実行できるかを定義する、粒度の細かい Teams 固有のアクセス許可です。 RSC アクセス許可の例には、チャネルの作成および削除、チームの設定の取得、チャネル タブの作成および削除があります。

RSC アクセス許可は、Azure AD ではなく、アプリ マニフェストで定義されます。 チームにアプリを追加するときに、RSC アクセス許可に同意を付与します。 詳細については、「[リソース固有の同意 (RSC)](/microsoftteams/platform/graph-api/rsc/resource-specific-consent)」を参照してください。

グローバル管理者と Teams サービス管理者は、アプリの詳細ページの **[アクセス許可]** タブで、アプリの RSC アクセス許可を表示できます。

アプリの RSC アクセス許可を表示するには、次の手順に従います。

1. Microsoft Teams 管理センターの左側のナビゲーションで、**[Teams アプリ]** > **[アプリを管理]** の順に移動します。
1. 目的のアプリを検索し、アプリ名をクリックしてアプリの詳細ページに移動し、**[アクセス許可]** タブを選択します。
1. **Microsoft Graph のリソース固有の同意 (RSC) アクセス許可** で、アプリから要求された RSC アクセス許可を確認します。

    :::image type="content" source="media/app-perm-admin-center-rsc-new.png" alt-text="アプリの RSC アクセス許可のスクリーンショット。":::

## <a name="known-issues"></a>既知の問題

### <a name="the-view-details-link-isnt-displayed-in-the-permissions-column-for-some-third-party-apps-that-request-permissions"></a>アクセス許可を要求する一部のサード パーティ製アプリの [アクセス許可] 列に [詳細の表示] リンクが表示されない

現時点では、アクセス許可を要求する Azure AD に登録されているすべてのサード パーティ製アプリで、アクセス許可を確認して同意を付与する機能は利用できません。 **[詳細の表示]** リンクの代わりに、**[アクセス許可]** 列に **--** が表示されます。 ISV と連携して、アプリに対してこの機能を有効にしています。

## <a name="related-topics"></a>関連項目

* [Microsoft Teams 管理センターで、Teams アプリの組織向けアプリを管理します。](manage-apps.md)
* [Microsoft ID プラットフォーム エンドポイントでのアクセス許可と同意](/azure/active-directory/develop/v2-permissions-and-consent)
* [Teams でのリソース固有の同意](resource-specific-consent.md)
* [リソース固有の同意 (RSC)](/microsoftteams/platform/graph-api/rsc/resource-specific-consent)
* [Teams アプリのライフサイクルに移動する](https://aka.ms/PR132) (Ignite 2020 セッション)
