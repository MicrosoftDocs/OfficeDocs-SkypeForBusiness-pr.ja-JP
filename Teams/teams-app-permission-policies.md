---
title: Microsoft Teams のアプリのアクセス許可ポリシーを管理する
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-apps
audience: Admin
ms.date: 09/29/2022
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.localizationpriority: high
search.appverid: MET150
description: Microsoft Teams のアプリのアクセス許可ポリシーと、エンドユーザーのアプリの可用性を制御する方法について説明します。
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.overview
- ms.teamsadmincenter.appsetuppolicies.addpinnedapp.permissions
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: 24c4b85bb1c4b97597bad6a38e6a67c35dc1abb0
ms.sourcegitcommit: 6e85f3f70f8488ab827ac352c0f324b6dfd4b856
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2022
ms.locfileid: "68377045"
---
# <a name="manage-access-to-teams-apps-using-app-permission-policies"></a>アプリのアクセス許可ポリシーを使用して Teams アプリへのアクセスを管理する

管理者は、アプリのアクセス許可ポリシーを使用して、組織内の各ユーザーが使用できるアプリを制御できます。 すべてのアプリまたは特定のアプリを許可またはブロックするように設定したアクセス許可は、 [Teams のすべての種類のアプリに適用されます](deploy-apps-microsoft-teams-landing-page.md)。 これらのポリシーを管理するには、グローバル 管理または Teams サービス管理者である必要があります。

アプリを許可するには、[組織全体のアプリ設定、個々のアプリ](manage-apps.md#manage-org-wide-app-settings)[の設定](manage-apps.md#allow-and-block-apps)、アプリのアクセス許可ポリシーで許可する必要があります。 他の 2 つの方法では、アプリが組織内で使用できるようにするだけですが、アクセス許可ポリシーを使用すると、特定のアプリを使用できるユーザーを制御できます。 ポリシーを作成して特定のユーザーに適用することで、ユーザーごとおよびアプリ単位でアクセスを制御します。

Teams 管理センターでは、次の 2 種類のアクセス許可ポリシーを作成できます。

* `Global (Org-wide default)` ポリシーは既定で存在し、すべてのユーザーに適用されます。 このポリシーに加えられた変更は、このポリシーが既定ですべてのユーザーに適用されるため、すべてのユーザーに影響します。
* 管理者が作成したポリシーは、適用されるユーザーにのみ適用されます。 特定のユーザーまたはユーザーのグループに対してアプリを許可する新しいポリシーを作成します。

   :::image type="content" source="media/app-permission-policy-trimmed.png" alt-text="作成中の新しいアプリアクセス許可ポリシーを示すスクリーンショット。" lightbox="media/app-permission-policy.png":::

組織が Teams に既にある場合、Microsoft 365 管理センターの **テナント全体の設定** で構成したアプリ設定は、Teams 管理センターの [アプリの管理] ページの組織全体の [アプリ](https://admin.teams.microsoft.com/policies/manage-apps)設定に反映されます。 Teams を初めて使用し、開始したばかりの場合は、既定ですべてのアプリが組織全体のグローバル設定で許可されます。 これには、Microsoft、サード パーティ ソフトウェア プロバイダー、組織によって発行されたアプリが含まれます。

> [!NOTE]
> Microsoft 365 Government Community Cloud High (GCCH) 環境と国防総省 (DoD) 環境のサードパーティアプリ設定については、「 [Microsoft 365 Government の組織全体のアプリ設定を管理する」を](manage-apps.md#manage-org-wide-app-settings-for-microsoft-365-government)参照してください。

## <a name="create-an-app-permission-policy"></a>アプリのアクセス許可ポリシーを作成する

異なるユーザー グループで使用できるアプリを制御する場合は、1 つ以上のカスタム アプリのアクセス許可ポリシーを使用します。 アプリが Microsoft、サードパーティ、または組織のうちどこで公開されているかに基づいて、個別のカスタム ポリシーを作成し、割り当てることができます。 カスタム ポリシーを作成した後、組織全体のアプリ設定でサード パーティのアプリが無効になっている場合、ポリシーを変更できないのでご注意ください。

1. Teams 管理センターにサインインし、 **Teams アプリ** > **[のアクセス許可ポリシー](https://admin.teams.microsoft.com/policies/app-permission)** にアクセスします。
1. **[追加]** を選択します。
1. ポリシーの名前と説明を入力します。
1. **Microsoft アプリ**、**サード パーティ製アプリ**、および **カスタム アプリ** で、次のいずれかのオプションを選択します。

    * `Allow all apps`
    * `Allow specific apps and block all others`
    * `Block specific apps and allow all others`
    * `Block all apps`

1. **[特定のアプリを許可し、他のすべてのアプリをブロックする]** を選択した場合は、以下の手順で許可するアプリを追加します。

    1. **[アプリを許可]** を選びます。
    1. 許可するアプリを検索し、**[追加]** をクリックします。 検索結果は、アプリ開発者 (**Microsoft アプリ**、 **サード パーティアプリ**、または **カスタム アプリ**) にフィルター処理されます。
    1. 1 つ以上のアプリを選択したら、[ **許可**] を選択します。

1. [ **特定のアプリをブロックして他のすべてのアプリを許可** する] を選択した場合は、同様にブロックするアプリを検索して選択し、[ **ブロック**] を選択します。

1. **[保存]** を選択します。

## <a name="edit-an-app-permission-policy"></a>アプリのアクセス許可ポリシーを編集する

Teams 管理センターを使用して、グローバル ポリシーまたは作成したカスタム ポリシーを編集できます。

1. Teams 管理センターにサインインし、 **Teams アプリ** > **[のアクセス許可ポリシー](https://admin.teams.microsoft.com/policies/app-permission)** にアクセスします。
1. ポリシー名の左側をクリックしてポリシーを選び、**[編集]** を選択します。
1. 3 つのカテゴリのそれぞれに特定のアプリを許可またはブロックするように変更を加えます。
1. **[保存]** を選択します。

## <a name="assign-a-custom-app-permission-policy-to-users"></a>カスタム アプリのアクセス許可ポリシーをユーザーに割り当てる

アプリのアクセス許可ポリシーは、ユーザーまたはユーザーのグループにポリシーを適用する場合にのみ有効になります。 [ユーザーにポリシーを割り当てる](policy-assignment-overview.md#ways-to-assign-policies)さまざまな方法を参照してください。

## <a name="considerations-when-using-app-permission-policies"></a>アプリのアクセス許可ポリシーを使用する場合の考慮事項

アプリのアクセス許可ポリシーを使用してアクセスを許可する場合、またはアプリへのアクセスを禁止する場合の考慮事項を次に示します。

* アプリのアクセス許可ポリシーは、ユーザーまたはユーザーのグループにポリシーを適用する場合にのみ有効になります。

* ポリシーを編集既するか割り当てた後、変更が反映されるまでに数時間かかる場合があります。

* エンド ユーザーは、ユーザーが使用を許可されていないアプリの機能を操作することはできません。

* ユーザーは、ブロックされたアプリを検索し、管理者の承認を要求できます。 管理者は、 [ユーザー要求を承認または無視](user-requests-approve-apps.md)するための完全な制御を保持します。

* アプリのセットアップ ポリシーは、アプリのアクセス許可ポリシーと連携します。 許可されているアプリのセットからセットアップ ポリシーにピン留めするアプリを選択します。 ただし、ユーザーがピン留めされたアプリの使用をブロックするアプリアクセス許可ポリシーを持っている場合、ユーザーはそのアプリを使用できません。

* アプリ ポリシーは、Web、モバイル、またはデスクトップ上の任意の Teams を使用するユーザーに適用されます。

## <a name="related-articles"></a>関連記事

* [Teams でのアプリの管理設定](admin-settings.md)
* [ Teams でユーザーにポリシーを割り当てる](policy-assignment-overview.md)
* [Teams 機能の可用性の比較](/office365/servicedescriptions/teams-service-description#feature-availability)
