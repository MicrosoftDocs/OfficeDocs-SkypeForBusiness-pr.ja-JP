---
title: サード パーティ製アプリを購入Teams
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: chhavib, vaibhava
search.appverid: MET150
f1keywords: ''
description: 管理センターでサード パーティ製アプリを購入TeamsをMicrosoft Teamsします。
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.openlocfilehash: 77a54fc6c6cf45492143d0548e488324514b500a
ms.sourcegitcommit: c7b95254dec4420ba0a697fd49d11b448364c919
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/11/2022
ms.locfileid: "63442653"
---
# <a name="purchase-third-party-apps-for-teams"></a>サード パーティ製アプリを購入Teams

Teamsは無料でインストールできます。また、アプリの全機能とスコープを体験するために購入サービス サブスクリプションが必要な場合があります。 これらのサービス サブスクリプションは、サービスとしてのソフトウェア (SaaS) オファーと呼ばれるサービスであり、[AppSource](https://appsource.microsoft.com/) を通じて購入し、現在はサービス管理センターを通じてMicrosoft Teams利用できます。

管理[センターの](manage-apps.md) [Microsoft Teams] ページでは、組織のすべてのアプリTeams表示および管理できます。 たとえば、アプリの組織レベルの状態とプロパティの表示、組織のアプリ ストアへの新しいカスタム アプリのアップロード、組織レベルでのアプリのブロックまたは許可、組織全体のアプリ設定の管理を行います。

ここでは、組織内のユーザー向けサード パーティ製アプリによって提供されるサービスのライセンスを購入することもできます。 表 **の [** ライセンス] 列は、アプリが SaaS サブスクリプションを購入できるかどうかを示しています。

![購入ライセンスの [アプリの管理] ページのスクリーンショット。](media/manage-apps-new-page.png)

## <a name="purchase-apps-in-the-teams-admin-center"></a>管理センターでアプリTeams購入する

> [!IMPORTANT]
> ユーザーがアプリ ストアを通じてアプリを購入Teams場合は、アプリをブロックする必要があります。 アプリをブロックする方法の詳細については、「アプリ ポリシー[](app-policies.md)を管理する」または「組織レベルでアプリをブロックする方法[」を参照してください](manage-apps.md#allow-and-block-apps)。

1. Microsoft Teams 管理センターの左側のナビゲーションで、**[Teams アプリ]** > **[アプリを管理]** の順に移動します。 ページにアクセスするには、グローバル管理者Teamsサービス管理者である必要があります。
1. 必要なアプリを検索します。 有料 SaaS サブスクリプションを持つアプリを識別するには、[ライセンス] 列を **確認** します。 各アプリには、次のいずれかの値があります。
    - **購入**: アプリは SaaS サブスクリプションを提供し、購入できます。  
    - **購入:** アプリは SaaS サブスクリプションを提供し、そのライセンスを購入しました。
    - **- -**: アプリは SaaS サブスクリプションを提供しない。
1. アプリが見つけたら、[購入 **] を** クリックして、アプリの詳細ページの **[プラン** と価格] タブに移動します。 アプリの SaaS プランのプランと価格情報を確認します。 詳細が必要な場合は、[詳細] **を** 選択して AppSource のアプリのページに [移動します](https://appsource.microsoft.com/)。

   > [!NOTE]
   > また、組織が以前に ISV と交渉した特別な価格を含む、購入用のプライベート プランが一覧表示される場合があります。 これらのプランには、プラン名の **下に [プライベート** プラン] というラベルが表示されます。

1. アプリをサブスクライブするには、目的のプランを選択し、[購入] を選択 **します**。 チェックアウト フローは、管理センターのTeams開きます。

1. 購入するユーザー ライセンスの数を選択します。
1. 請求先アカウントと販売先住所が正しいか確認します。 まだお持ちでない場合は、[追加] を選択して新しい追加を行 **います**。 請求先アカウントの詳細については、「請求先アカウントについて [」を参照してください](/microsoft-365/commerce/manage-billing-accounts)。

   > [!NOTE]
   > 新しい請求先アカウントを追加するには、グローバル管理者である必要があります。

1. 正しい課金プロファイルが選択されていることを確認します。 まだお持ちでない場合は、[新規追加] を選択して新しい追加 **を行います**。 クレジット カード、デビット カード、または請求書の請求で支払う [オプションがあります](#invoice-billing)。 課金プロファイルでは、後で注文を識別する発注書番号を追加することもできます。 課金プロファイルの詳細については、「課金プロファイルについて [」を参照してください](/microsoft-365/commerce/billing-and-payments/manage-billing-profiles)。
1. [注文 **] を選択します**。
1. [ **設定] を** 選択して、発行元の Web サイトでサブスクリプションをアクティブ化します。 購入後にサブスクリプションを設定しない場合は、[ライセンスの管理] を選択して後で **設定できます**。

Teams アプリに関連付けられている SaaS オファーを購入すると、アプリの詳細ページの [プランと価格] タブで次の購入の詳細を表示できます。

- **ライセンスのライセンス認証日**: ライセンスがアクティブ化された日付。 アカウントがまだ設定されていない場合は、サブスクリプションのアクティブ化が保留中 **と表示されます**。
- **ライセンス**: 購入したライセンスの数。

:::image type="content" source="media/purchase-third-party-apps-details-page.png" alt-text="アプリの詳細ページの [プランと価格] タブのスクリーンショット。":::

[**ライセンスの管理]** を選択して、Microsoft 365 管理センターに移動して、購入したライセンスを表示および管理します。

グローバル管理者は、組織内のすべてのユーザーが行った購入のライセンスの追加、ライセンスの削除、サブスクリプションの取り消しを行います。 Teams管理者は、自分で行った購入に対して同じアクションを実行できます。 ただし、サービス管理者Teams課金管理者ロールを持っている場合は、組織内のすべてのユーザーが行った購入を管理できます。

> [!NOTE]
> グローバル管理者が別のグローバル管理者によって購入されたサブスクリプションを管理する場合は、同じ請求先アカウントに登録する必要があります。 購入したサブスクリプションに対して別のグローバル管理者アクセス権を付与するには、アプリを選択Microsoft 365 管理センター。 そこから、[課金プロファイルの表示課金 **アカウントの選択** > **][** > **ロールの割** り当て > **][他のグローバル管理者の追加] に移動します**。

### <a name="invoice-billing"></a>請求書の請求

- 請求書の請求は、一部のトランザクションの支払いオプションとして利用できます。
- 請求書の請求を初めて使用する場合は、与信審査が必要です。承認には最大 24 ~ 48 時間かかる場合があります。 クレジット チェックが完了するまで、請求書の課金は利用できません。 クレジット カードで注文するか、クレジット レビューが承認された後でもう一度やり直してください。
- 請求書の課金は、グローバル管理者またはサービス管理者と課金管理者の両方のアクセス許可Teams管理者にのみ使用できます。
- 30 日間の無料試用版でプランを購入する場合、請求書の課金は利用できません。

## <a name="have-a-saas-offer-for-a-teams-app-that-you-want-to-list-and-sell-in-the-microsoft-teams-admin-center-and-appsource"></a>Teams 管理センターと AppSource で一覧表示して販売する、Microsoft Teams アプリの SaaS オファーがありますか?

開発者は、アプリに関連付けられた SaaS オファー Teamsできます。 これらのオファーはパートナー センターを[通じて](https://partner.microsoft.com)公開され、[組織は AppSource](https://appsource.microsoft.com/) と管理センターから購入Microsoft Teamsできます。

サード パーティ製アプリ開発者は、「SaaS オファーを作成する」を [参照して](/azure/marketplace/partner-center-portal/create-new-saas-offer) 詳細を確認できます。

## <a name="related-topics"></a>関連項目

- [管理センターでアプリMicrosoft Teamsする](manage-apps.md)
- [SaaS オファーを作成する](/azure/marketplace/partner-center-portal/create-new-saas-offer)
- [Azure ADロールを作成する](/azure/active-directory/roles/permissions-reference)
- [Microsoft 365ロールを追加する](/microsoft-365/admin/add-users/about-admin-roles)
