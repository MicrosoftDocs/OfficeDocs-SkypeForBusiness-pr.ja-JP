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
ms.openlocfilehash: 5797486fb0993aa8630a8dedde131ad7751e7e5f
ms.sourcegitcommit: 1161cddd077056a9c1e2da99a84e35be0380b1b1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/20/2022
ms.locfileid: "68656023"
---
# <a name="manage-access-to-teams-apps-using-app-permission-policies"></a>アプリのアクセス許可ポリシーを使用して Teams アプリへのアクセスを管理する

管理者は、アプリのアクセス許可ポリシーを使用して、組織内の各ユーザーが使用できるアプリを制御できます。 すべてのアプリまたは特定のアプリを許可またはブロックするように設定したアクセス許可は、 [Teams のすべての種類のアプリに](deploy-apps-microsoft-teams-landing-page.md)適用できます。 これらのポリシーを管理するには、グローバル 管理または Teams サービス管理者である必要があります。

アプリを許可するには、 [組織全体のアプリ設定](manage-apps.md#manage-org-wide-app-settings)、 [個々のアプリの設定](manage-apps.md#allow-and-block-apps)、アプリのアクセス許可ポリシーでアプリを許可する必要があります。 他の 2 つの方法では、組織でのアプリの使用のみを許可しますが、アクセス許可ポリシーを使用すると、特定のアプリを使用できるユーザーを制御できます。 特定のユーザーにポリシーを作成して適用することで、ユーザーごとおよびアプリごとにアクセスを制御します。

Teams 管理センターでは、次の 2 種類のアクセス許可ポリシーを作成できます。

* `Global (Org-wide default)` ポリシーは既定で存在し、すべてのユーザーに適用されます。 このポリシーに加えられた変更は、このポリシーが既定ですべてのユーザーに適用されるため、すべてのユーザーに影響します。
* 管理者が作成したポリシーは、適用先のユーザーにのみ適用されます。 特定のユーザーまたはユーザーのグループのアプリを許可する新しいポリシーを作成します。

   :::image type="content" source="media/app-permission-policy-trimmed.png" alt-text="新しいアプリアクセス許可ポリシーが作成されていることを示すスクリーンショット。" lightbox="media/app-permission-policy.png":::

組織が既に Teams 上にある場合、Microsoft 365 管理センターの **[テナント全体の設定**] で構成したアプリ設定は、Teams 管理センターの [[アプリの管理](https://admin.teams.microsoft.com/policies/manage-apps)] ページの組織全体のアプリ設定に反映されます。 Teams を初めて使用し始めたばかりの場合、既定では、組織全体のグローバル設定ですべてのアプリが許可されます。 これには、Microsoft、サード パーティ ソフトウェア プロバイダー、組織によって発行されたアプリが含まれます。

> [!NOTE]
> Microsoft 365 Government Community Cloud High (GCCH) および国防総省 (DoD) 環境のサード パーティ製アプリ設定については、「 [Microsoft 365 Government の組織全体のアプリ設定を管理](manage-apps.md#manage-org-wide-app-settings-for-microsoft-365-government)する」を参照してください。

## <a name="create-an-app-permission-policy"></a>アプリのアクセス許可ポリシーを作成する

異なるユーザー グループで使用できるアプリを制御する場合は、1 つ以上のカスタム アプリのアクセス許可ポリシーを使用します。 アプリが Microsoft、サードパーティ、または組織のうちどこで公開されているかに基づいて、個別のカスタム ポリシーを作成し、割り当てることができます。 カスタム ポリシーを作成した後、組織全体のアプリ設定でサード パーティのアプリが無効になっている場合、ポリシーを変更できないのでご注意ください。

1. Teams 管理センターにサインインし、 **Teams アプリ** > **[のアクセス許可ポリシーにアクセスします](https://admin.teams.microsoft.com/policies/app-permission)**。
1. **[追加]** を選択します。
1. ポリシーの名前と説明を入力します。
1. [ **Microsoft アプリ**]、[ **サード パーティ製アプリ**]、[ **カスタム アプリ**] で、次のいずれかのオプションを選択します。

    * `Allow all apps`
    * `Allow specific apps and block all others`
    * `Block specific apps and allow all others`
    * `Block all apps`

1. **[特定のアプリを許可し、他のすべてのアプリをブロックする]** を選択した場合は、以下の手順で許可するアプリを追加します。

    1. **[アプリを許可]** を選びます。
    1. 許可するアプリを検索し、**[追加]** をクリックします。 検索結果は、アプリ開発者 (**Microsoft アプリ**、 **サード パーティ製** アプリ、または **カスタム アプリ**) にフィルター処理されます。
    1. 1 つ以上のアプリを選択したら、[ **許可**] を選択します。

1. [ **特定のアプリをブロックして他のすべてのアプリを許可** する] を選択した場合は、同様に、ブロックするアプリを検索して選択し、[ **ブロック**] を選択します。

1. **[保存]** を選択します。

## <a name="edit-an-app-permission-policy"></a>アプリのアクセス許可ポリシーを編集する

Teams 管理センターを使用して、グローバル ポリシーまたは作成したカスタム ポリシーを編集できます。

1. Teams 管理センターにサインインし、 **Teams アプリ** > **[のアクセス許可ポリシーにアクセスします](https://admin.teams.microsoft.com/policies/app-permission)**。
1. ポリシー名の左側をクリックしてポリシーを選び、**[編集]** を選択します。
1. 3 つのカテゴリごとに特定のアプリを許可またはブロックするように変更を加えます。
1. **[保存]** を選択します。

## <a name="assign-a-custom-policy-for-app-permissions-to-users"></a>アプリのアクセス許可のカスタム ポリシーをユーザーに割り当てる

アプリのアクセス許可ポリシーは、ユーザーまたはユーザーのグループにポリシーを適用する場合にのみ有効になります。 [ポリシーをユーザーに割り当てる](policy-assignment-overview.md#ways-to-assign-policies)さまざまな方法を参照してください。

## <a name="considerations-when-using-app-permission-policies"></a>アプリのアクセス許可ポリシーを使用するときの考慮事項

アプリのアクセス許可ポリシーを使用してアクセスを許可する場合、またはアプリへのアクセスを禁止する場合の考慮事項を次に示します。

* アプリのアクセス許可ポリシーは、ユーザーまたはユーザーのグループにポリシーを適用する場合にのみ有効になります。

* ポリシーを編集既するか割り当てた後、変更が反映されるまでに数時間かかる場合があります。

* エンド ユーザーは、ユーザーが使用できないアプリの機能を操作できません。

* ユーザーは、ブロックされたアプリを検索し、管理者の承認を要求できます。 管理者は、 [ユーザー要求を承認または無視](user-requests-approve-apps.md)するための完全な制御を保持します。

* アプリセットアップ ポリシーは、アプリのアクセス許可ポリシーと連携します。 許可されている一連のアプリからセットアップ ポリシーにピン留めするアプリを選択します。 ただし、ピン留めされたアプリの使用をブロックするアプリアクセス許可ポリシーをユーザーが持っている場合、ユーザーはアプリを使用できません。

* アプリ ポリシーは、Web、モバイル、またはデスクトップ上の任意の Teams を使用するユーザーに適用されます。

## <a name="related-articles"></a>関連記事

* [Teams でのアプリの管理設定](admin-settings.md)
* [ Teams でユーザーにポリシーを割り当てる](policy-assignment-overview.md)
* [Teams 機能の可用性の比較](/office365/servicedescriptions/teams-service-description#feature-availability)
