---
title: Microsoft Teams 管理センターでアプリのアクセス許可を表示し、管理者の同承認を付与する
author: LanaChin
ms.author: v-lanac
ms.reviewer: vaibhava
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: アプリによって要求されたアクセス許可を表示し、管理者の承認を Microsoft Teams 管理センターの [アプリの管理] ページで許可する方法について説明します。
localization_priority: Normal
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 6aafd5cbdd1ae44844f69b78234f10a54abe7b85
ms.sourcegitcommit: bb5229c9f7999358dcf0ba185ecfd7c881627a38
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46824908"
---
# <a name="view-app-permissions-and-grant-admin-consent-in-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターでアプリのアクセス許可を表示し、管理者の同承認を付与する

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Microsoft Teams [管理センター](manage-apps.md) の [アプリの管理] ページでは、組織のすべての Teams アプリを表示して管理することができます。 たとえば、アプリのプロパティの組織レベルの状態とプロパティの確認、新しいカスタム アプリを組織のアプリ ストアに承認またはアップロードしたり、組織レベルのアプリをブロックまたは許可したり、組織全体のアプリ設定を管理したりすることができます。

ここでは、データへのアクセス許可を要求するアプリに対する組織全体の管理者の同じ設定を、アプリに対するリソース固有の同一 (RSC) アクセス許可を表示する方法もあります。

## <a name="grant-org-wide-admin-consent-to-an-app"></a>組織全体の管理者におもならず、アプリに管理者の承認を付けます。

全体管理者の場合は、組織内のすべてのユーザーに代わってアクセス許可をリクエストするアプリに対する同じ権限を確認して付与することができます。 この操作を行うことで、ユーザーがアプリを起動したときにアプリから要求されたアクセス許可を確認して承諾する必要がなくなります。 また、Azure Active Directory (Azure AD) の [ユーザー](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent) の同済設定によっては、一部のユーザーが、会社データにアクセスするアプリに同時に同済を許可できない場合があります。

アプリによって要求されるアクセス許可の例としては、チームに保存されている情報を読み取り、ユーザーのプロフィールを読み、ユーザーの代理でメールを送信する機能が含まれます。 詳細については、Microsoft ID プラットフォームエンドポイントの権限 [と同同編集を参照してください](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent)。 

[ **権限]** 列は、アプリに同一の権限が必要かどうかを示します。 Azure アカウント **に登録されている** アプリごとに、同じように同じ権限が必要なアクセス許可を持 ADつアプリごとに、[詳細の表示] リンクが表示されます。 これは、カスタム アプリとサードパーティのアプリとサードパーティのアプリにのみ適用されることに留まることに留めてください。 このリンクは表示されないか、Microsoft が発行したアプリに管理者の同同同権限を付けたりする必要があります。

:::image type="content" source="media/app-perm-admin-center-permissions-column.png" alt-text="[アプリの管理] ページの [アクセス許可] 列のスクリーンショット":::

組織全体のユーザーにアプリのユーザーに認識するには、次の手順に従います。

1. Microsoft Teams 管理センターの左側のナビゲーションで、Teams アプリの管理**アプリ**  >  **に移動します**。
2. 次のいずれかの操作を行います。
    - 目的のアプリを検索し、アプリ名をクリックしてアプリの詳細ページに移動し、[アクセス許可] タブ **を選択** します。
    - [アクセス **許可] 列** を降順で並べ替え、アプリを見つけ、[詳細の **表示] を選択します**。 これを行うと、アプリの **詳細ページの** [アクセス許可] タブに移動します。

3. [ **組織全体のアクセス許可] で [** アクセス許可と **同同編集] を選びます**。

    :::image type="content" source="media/app-perm-admin-center-org-wide.png" alt-text="アプリの [アクセス許可] タブにある、既定のアクセス許可のスクリーンショット":::

    これを行うには、グローバル管理者である必要があります。 このオプションは、Teams のサービス管理者は使用できません。

4. [権限 **] タブ** で、アプリから要求されたアクセス許可を確認します。

    :::image type="content" source="media/app-perm-admin-center-org-wide-permissions.png" alt-text="アプリから要求されたアクセス許可のスクリーンショット":::

    > [!IMPORTANT]
    > アプリに組織全体のユーザーを付付けると、アプリが組織のデータにアクセスできるようになります。 同ユーザーに同済を付与する前に、アプリによって要求されたアクセス許可を正常に確認してください。
5. アプリから要求されたアクセス許可に同意したら、[承諾] を **クリックして同** 意を許可します。 アプリに対して要求されたアクセス許可がアプリに対して与えされたことを知らせるバナーがページの上部に表示されます。 これでアプリは組織内のすべてのユーザーに対して指定されたリソースにアクセスでき、他のユーザーには権限を確認するように求めるメッセージが表示されなくなります。

アクセス許可を承諾すると、アプリ全体のアクセス許可ページに **[組織** 全体のアクセス許可] に、同意が付与されたことを知らせるメッセージがアプリの詳細ページに表示されます。 アプリのアクセス許可の詳細を表示するには **、Azure Active Directory** リンクをクリックして、Azure AD ポータルのアプリのページに移動します。

:::image type="content" source="media/app-perm-admin-center-org-wide-accepted.png" alt-text="ユーザーからの資オン時に表示されるメッセージのスクリーンショット":::

組織内のユーザーが同じ内容を付けたり、1 人以上のユーザーに対して特定のアプリに同じ同資を付けた場合は、同じメッセージが表示され、同じメッセージが表示され、同じメッセージが表示され、同じメッセージが表示され、同じメッセージが表示され、同じメッセージが表示され、同じメッセージが表示され、同じメッセージが表示され、同じメッセージが表示されます。このメッセージは、同じメッセージが表示されます。このメッセージは、同じメッセージを表示し、同じメッセージが表示されます。同じメッセージが表示されます。このメッセージは、同じメッセージと同じです。このメッセージは、同じメッセージを表示し、同じメッセージが表示されます。同じメッセージが表示されます。このメッセージは、同じメッセージと、Azure AD ポータルのアプリのページにアクセスできることを知らせるメッセージも表示されます。

> [!NOTE]
> Teams サービス管理者 **は [アクセス許可と同時編集** ] オプションを使用できません。また、アプリに対する組織全体の管理者の同同権限を付与できませんが、Teams サービス管理者はアプリの [ **アクセス** 許可] タブでコンテンツを表示できます。 たとえば、Teams サービス管理者は Azure **Active Directory リンクをクリックして、Azure レポート** ポータルでアプリのアクセス許可の詳細をADできます。 

## <a name="view-resource-specific-consent-permissions-of-an-app"></a>アプリのリソース固有の同同権限を表示する

RSC 権限を使用すると、チーム所有者はアプリに同でき、チームのデータにアクセスして変更することができます。 RSC アクセス許可は、定期的に、特定のチームでアプリを実行できる操作を定義する Teams 固有のアクセス許可です。 RSC アクセス許可の例としては、チャネルの作成と削除、チームの設定の取得、チャネル タブの作成と削除などがあります。 

RSC アクセス許可は、Azure アクセス許可には含め、アプリ マニフェストで定義AD。 アプリをチームに追加するときに RSC 権限に同与します。 詳細については、 [リソース固有の問題 (RSC) を参照してください](https://docs.microsoft.com/microsoftteams/platform/graph-api/rsc/resource-specific-consent)。

グローバル管理者と Teams サービス管理者は、アプリの詳細ページの [**Permissions**アクセス許可] タブでアプリの RSC 権限を表示できます。 

アプリの RSC 権限を表示するには、次の手順を実行します。

1. Microsoft Teams 管理センターの左側のナビゲーションで、Teams アプリの管理**アプリ**  >  **に移動します**。
2. 目的のアプリを検索し、アプリ名をクリックしてアプリの詳細ページに移動し、[アクセス許可] タブ **を選択** します。
3. **Microsoft Graph のリソース固有の同同権限の下で、** アプリによって要求された RSC 権限を確認します。

    :::image type="content" source="media/app-perm-admin-center-rsc.png" alt-text="アプリの RSC アクセス許可のスクリーンショット":::

## <a name="known-issues"></a>既知の問題

### <a name="the-view-details-link-isnt-displayed-in-the-permissions-column-for-some-third-party-apps-that-request-permissions"></a>アクセス許可を要求する一部のサード パーティのアプリの [アクセス許可] 列に [詳細の表示] リンクは表示されません

現時代、アクセス許可を確認して同じように、アクセス許可を要求するすべてのサード パーティのアプリで、同じ資オンを ADできません。 [詳細の表示 **] リンクではなく** 、[アクセス許可] 列 **--** に **表示** されます。 MICROSOFT では、お客様のアプリでこの機能を有効にする ISV と一回用しています。

## <a name="related-topics"></a>関連項目

- [Microsoft Teams 管理センターでアプリを管理する](manage-apps.md)
- [Microsoft ID プラットフォーム エンドポイントでのアクセス許可と同同編集](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent)
- [Teams でのリソース固有の問題](resource-specific-consent.md)
- [リソース固有の問題 (RSC)](https://docs.microsoft.com/microsoftteams/platform/graph-api/rsc/resource-specific-consent)


