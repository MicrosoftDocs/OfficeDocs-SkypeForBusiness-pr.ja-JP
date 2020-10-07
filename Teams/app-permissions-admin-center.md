---
title: Microsoft Teams 管理センターでアプリのアクセス許可を表示し、管理者の同意を与える
author: LanaChin
ms.author: v-lanac
ms.reviewer: vaibhava
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: アプリから要求されたアクセス許可を表示し、Microsoft Teams 管理センターの [アプリの管理] ページのアプリに管理者の同意を与える方法について説明します。
localization_priority: Normal
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a1c9f63c54711c5721ced661dc28d704c0b605c7
ms.sourcegitcommit: f4f5ad1391b472d64390180c81c2680f011a8a10
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2020
ms.locfileid: "48367597"
---
# <a name="view-app-permissions-and-grant-admin-consent-in-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターでアプリのアクセス許可を表示し、管理者の同意を与える

Microsoft Teams 管理センターの [ [アプリの管理](manage-apps.md) ] ページでは、組織のすべての Teams アプリを表示して管理できます。 たとえば、アプリの組織レベルの状態とプロパティの表示、組織のアプリストアへの新しいカスタムアプリの承認またはアップロード、組織レベルでのアプリのブロックまたは許可、組織全体のアプリ設定の管理を行うことができます。

ここでは、データへのアクセス許可を要求するアプリに対して、また、アプリに対するリソース固有の同意 (RSC) のアクセス許可を表示するように、組織全体の管理者の同意を付与することもできます。

## <a name="grant-org-wide-admin-consent-to-an-app"></a>アプリに組織全体の管理者の同意を与える

グローバル管理者の場合は、組織内のすべてのユーザーの代理としてアクセス許可を要求するアプリに対して、同意を確認して付与することができます。 これは、ユーザーがアプリを起動したときに、アプリによって要求されたアクセス許可を確認して受け入れる必要がないようにするためです。 さらに、Azure Active Directory (Azure AD) でのユーザーの [同意設定](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent) によっては、会社のデータにアクセスするアプリに対して承認を受けることができないユーザーもいます。

アプリから要求されるアクセス許可の例には、チームに保存されている情報の読み取り、ユーザーのプロファイルの読み取り、ユーザーに代わってメールを送信する機能などがあります。 詳細については、「 [Microsoft identity platform エンドポイントでの権限と同意](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent)」を参照してください。 

[ **権限** の列には、アプリに承認が必要な権限が与えられているかどうかを表示します。 Azure AD に登録されている各アプリの [ **詳細の表示** ] リンクが表示されます。これには、承認が必要なアクセス許可があります。 これは、カスタムアプリとサードパーティアプリにのみ適用されることに注意してください。 このリンクは表示されません。または、Microsoft が公開したアプリに管理者の同意を与える必要があります。

:::image type="content" source="media/app-perm-admin-center-permissions-column.png" alt-text="[アプリの管理] ページの [アクセス許可] 列のスクリーンショット":::

アプリに組織全体の同意を与えるには、次の手順を実行します。

1. Microsoft Teams 管理センターの左のナビゲーションで、[ **Teams アプリ**の管理] に移動  >  **Manage apps**します。
2. 次のいずれかの操作を行います。
    - 目的のアプリを検索し、アプリ名をクリックして [アプリの詳細] ページに移動し、[ **アクセス許可** ] タブを選択します。
    - [ **アクセス許可** ] 列を降順で並べ替えてアプリを見つけ、[ **詳細の表示**] を選択します。 この操作を行うと、[アプリの詳細] ページの [ **アクセス許可** ] タブに移動します。

3. [ **組織全体のアクセス許可**] で、[ **アクセス許可と同意を確認**する] を選択します。

    :::image type="content" source="media/app-perm-admin-center-org-wide.png" alt-text="アプリの [アクセス許可] タブにある組織全体のアクセス許可のスクリーンショット":::

    この操作を行うには、グローバル管理者である必要があります。 このオプションは、Teams サービスの管理者には使用できません。

4. [ **アクセス許可** ] タブで、アプリによって要求されたアクセス許可を確認します。

    :::image type="content" source="media/app-perm-admin-center-org-wide-permissions.png" alt-text="アプリから要求されたアクセス許可のスクリーンショット":::

    > [!IMPORTANT]
    > アプリに組織全体の同意を付与すると、アプリは組織のデータにアクセスできます。 同意を得る前に、アプリによって要求されたアクセス許可を慎重に確認してください。
5. アプリから要求されたアクセス許可に同意する場合は、[ **承諾** ] をクリックして同意を付与します。 バナーは、ページ上部に一時的に表示され、要求されたアクセス許可がアプリに付与されていることを知らせます。 これで、アプリは、組織内のすべてのユーザーに対して指定されたリソースにアクセスできるようになり、アクセス許可を確認するメッセージが表示されなくなります。

権限を承諾すると、[アプリの詳細] ページの [ **組織全体の権限** ] にメッセージが表示され、承諾が許可されたことがわかります。 アプリのアクセス許可に関する詳細を表示するには、 **Azure Active Directory** のリンクをクリックして、azure AD ポータルのアプリのページに移動します。

:::image type="content" source="media/app-perm-admin-center-org-wide-accepted.png" alt-text="承認が付与されたときに表示されるメッセージのスクリーンショット":::

組織内のユーザーが承諾を許可することが許可されていて、1人以上のユーザーが特定のアプリへの同意を許可している場合は、同じメッセージが表示されます。これには、承認が付与されたことと、Azure AD ポータルのアプリページへの Azure Active Directory へのリンクが表示されます。

> [!NOTE]
> Teams サービス管理者は [ **権限の確認] と [承認** ] オプションを使用できませんが、アプリに対して組織全体の管理者の同意を付与することはできません。 teams のサービス管理者は、アプリの [ **アクセス許可** ] タブでコンテンツを表示できます。 たとえば、Teams サービス管理者は、 **Azure Active Directory** のリンクをクリックすると、azure AD ポータルでアプリのアクセス許可の詳細を表示できます。 

## <a name="view-resource-specific-consent-permissions-of-an-app"></a>アプリのリソース固有の同意権限を表示する

RSC のアクセス許可を付与すると、チームの所有者はチームのデータにアクセスして変更するために、アプリの承認を与えることができます。 RSC 権限は、アプリが特定のチームで何を実行できるかを定義する、チーム固有の権限を細かく設定します。 RSC のアクセス許可には、チャネルの作成と削除、チームの設定の取得、チャネルタブの作成と削除などの機能が含まれます。 

RSC のアクセス許可は、Azure AD ではなく、アプリマニフェストで定義されます。 アプリをチームに追加するときに、RSC のアクセス許可に同意することを許可します。 詳細については、「 [リソース固有の同意 (RSC)](https://docs.microsoft.com/microsoftteams/platform/graph-api/rsc/resource-specific-consent)」を参照してください。

グローバル管理者と Teams サービス管理者は、アプリの詳細ページの [ **アクセス許可** ] タブでアプリの RSC 権限を確認できます。 

アプリの RSC 権限を表示するには、次の手順を実行します。

1. Microsoft Teams 管理センターの左のナビゲーションで、[ **Teams アプリ**の管理] に移動  >  **Manage apps**します。
2. 目的のアプリを検索し、アプリ名をクリックして [アプリの詳細] ページに移動し、[ **アクセス許可** ] タブを選択します。
3. [ **Microsoft Graph リソース固有の同意 (RSC) の権限**] で、アプリによって要求された RSC 権限を確認します。

    :::image type="content" source="media/app-perm-admin-center-rsc.png" alt-text="アプリの RSC のアクセス許可のスクリーンショット":::

## <a name="known-issues"></a>既知の問題

### <a name="the-view-details-link-isnt-displayed-in-the-permissions-column-for-some-third-party-apps-that-request-permissions"></a>権限を要求する一部のサードパーティ製アプリの [詳細の表示] リンクが [権限] 列に表示されない

現時点では、アクセス許可を確認したり許可を付与したりする機能は、Azure AD に登録されているすべてのサードパーティアプリで、アクセス許可を要求することはできません。 [詳細の **表示** ] リンクの代わりに、[ **--** **権限** ] 列に表示されます。 弊社では、Isv と協力して、アプリのこの機能を有効にしています。

## <a name="related-topics"></a>関連項目

- [Microsoft Teams 管理センターでアプリを管理する](manage-apps.md)
- [Microsoft identity platform エンドポイントでの権限と承認](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent)
- [Teams でのリソース固有の同意](resource-specific-consent.md)
- [リソース固有の同意 (RSC)](https://docs.microsoft.com/microsoftteams/platform/graph-api/rsc/resource-specific-consent)


