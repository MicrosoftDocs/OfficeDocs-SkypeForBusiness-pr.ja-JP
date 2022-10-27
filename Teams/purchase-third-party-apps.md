---
title: サード パーティの Teams アプリのライセンスを購入する
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
ms.subservice: teams-apps
audience: admin
ms.date: 10/04/2022
ms.collection:
- M365-collaboration
ms.reviewer: chhavib, vaibhava, nsuter
search.appverid: MET150
f1keywords: ''
description: クレジット カード、デビット カード、または請求書請求を使用して、Teams ストアからライセンスのサード パーティ製アプリを購入する方法について説明します。
appliesto:
- Microsoft Teams
ms.localizationpriority: high
ms.openlocfilehash: 73f16f3b8bdb11971f4cd7602c4262250e9fe068
ms.sourcegitcommit: c2d8c7f779f4f938f8355632ecfbfc9147b53bb2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2022
ms.locfileid: "68738553"
---
# <a name="purchase-licenses-for-third-party-teams-apps"></a>サード パーティの Teams アプリのライセンスを購入する

一部の Teams アプリでは、アプリの完全な機能とスコープを体験するために、サービス サブスクリプションの購入が必要になる場合があります。 これらのサービス サブスクリプションは、サービスとしてのソフトウェア (SaaS) オファーと呼ばれます。 ライセンスは、 [AppSource](https://appsource.microsoft.com/) と [Microsoft Teams 管理センター](https://admin.teams.microsoft.com)を通じて購入できます。

有料アプリは、他のアプリと同じガバナンス コントロールを使用して管理されます。 Teams 管理センターの [アプリの管理] ページから、すべての Teams [アプリ](manage-apps.md) を表示および管理します。

[アプリの管理] ページでは、組織内のユーザー向けにサード パーティ製アプリによって提供されるサービスのライセンスを購入することもできます。 テーブルの **[ライセンス** ] 列は、アプリが購入のために SaaS サブスクリプションを提供しているかどうかを示します。 エンド ユーザーは、クレジット カード、デビット カード、または請求書請求を使用してアプリを購入できます。

:::image type="content" source="media/manage-apps-new-page.png" alt-text="Teams 管理センターの [アプリの管理] ページの [購入ライセンス] オプションを示すスクリーンショット。" lightbox="media/manage-apps-new-page-large.png":::

## <a name="purchase-apps-in-the-teams-admin-center"></a>Teams 管理センターでアプリを購入する

Teams 管理センターでアプリを購入するには、次の手順に従います:

1. Teams 管理センターにサインインし、**Teams アプリ** にアクセス **[してアプリ](https://admin.teams.microsoft.com/policies/manage-apps)** > を管理します。 ページにアクセスするには、グローバル管理者または Teams サービス管理者である必要があります。

1. 目的のアプリを名前で検索します。 アプリが有料 SaaS サブスクリプションを提供しているかどうかを確認するには、ライセンス列 **を** 参照してください。 各アプリには、次のいずれかの値があります:
    * **今すぐ購入**: このアプリは SaaS サブスクリプションを提供しており、購入が可能です。
    * **購入済み**: このアプリは SaaS サブスクリプションを提供しており、そのライセンスを購入済みです。
    * **- -**: このアプリは SaaS サブスクリプションを提供していません。

1. [ **購入** ] を選択して、アプリの詳細ページの [ **プランと価格** ] タブに移動します。 管理センターで利用できるプランと価格情報を確認できます。 [ **詳細情報** ] リンクを選択すると、 [AppSource](https://appsource.microsoft.com/) のアプリのページに移動できます。

1. アプリをサブスクライブするには、目的のプランを選択し、**[購入]** を選択します。 チェックアウト フローは、Teams 管理センターで直接開きます。

> [!NOTE]
> プライベート プランは購入用に一覧表示される場合もあります。これには、組織が個別にアプリ開発者と交渉できる特別価格が含まれます。 このようなプランには、プラン名の下に **プライベート プラン** というラベルが付けられます。

1. 購入するユーザー ライセンスの数を選択します。

1. 請求先アカウントと販売先住所が正しいことを確認します。 まだお持ちでない場合は、**[追加]** を選択します。 課金アカウントの詳細については、 [「課金アカウントについて」](/microsoft-365/commerce/manage-billing-accounts)を参照してください。 グローバル管理者のみが新しい課金アカウントを追加できます。

1. 正しい課金プロファイルが選択されていることを確認します。 まだお持ちでない場合は、**[新規追加]** を選択します。 クレジット カード、デビット カード、または [請求書請求](#invoice-billing)で支払うことができます。 課金プロファイルでは、後で注文を識別する発注書番号を追加することもできます。 課金プロファイルに関する詳細については、[「課金プロファイルを理解する」](/microsoft-365/commerce/billing-and-payments/manage-billing-profiles)を参照してください。

1. **[注文]** を選択します。

1. **[設定]** を選択して、アプリ開発者の Web サイトでサブスクリプションをアクティブ化します。 購入後にサブスクリプションを設定しない場合は、後で [ **サブスクリプションの管理**] を選択して行うことができます。

Teams アプリに関連付けられている SaaS オファーを購入すると、アプリの詳細ページの [ **プランとサブスクリプション** ] タブで次の購入の詳細を表示できます。

* **ライセンスのアクティブ化日**: ライセンスがアクティブ化された日付。
* **ライセンス**: 購入したライセンスの数。

  :::image type="content" source="media/manage-apps-plans-and-subscription.png" alt-text=" Teams 管理センターのアプリの詳細ページにある [プランと価格]タブのスクリーンショット" lightbox="media/purchase-third-party-apps-details-page.png":::

[ **サブスクリプションの管理** ] を選択して、購入したライセンスを表示および管理します。

グローバル管理者は、組織内のすべてのユーザーが購入したサブスクリプションを表示できますが、追加のライセンスの追加、ライセンスの削除、課金アカウント内のユーザーによる購入のサブスクリプションの取り消しのみが可能です。 Teams サービス管理者は、自分自身で行った購入に対して同じアクションを実行できます。

> [!NOTE]
> グローバル管理者が別のグローバル管理者が購入したサブスクリプションを管理する場合は、同じ課金アカウントに属している必要があります。 購入したサブスクリプションへの別のグローバル管理者アクセス権を付与するには、[Microsoft 365 管理センター](https://admin.microsoft.com)でアプリを選択します。 管理センターで、**[課金プロファイルの表示]** > **[課金アカウントの選択]** > **[ロールの割り当て]** > **[他のグローバル管理者の追加]** にアクセスします。

> [!IMPORTANT]
> アプリの購入を有効にすると、アプリ内購入も有効になります。 ユーザーには、アプリ開発者によって制御されるアプリ内購入オファーが表示される場合があります。 ユーザーがアプリの購入できないようにする場合は、アプリをブロックする必要があります。

### <a name="invoice-billing"></a>請求書の請求

* 請求書の請求は、一部のトランザクションの支払いオプションとして使用できます。
* 請求書の請求を初めて使用するときは、与信審査が必要で、承認には最大 24 ~ 48 時間かかる場合があります。 請求書の請求は、与信審査が完了するまで利用できません。 クレジット カードで注文を行うか、クレジット レビューが承認された後でもう一度お試しください。
* 請求書の請求は、全体管理者または Teams サービス管理者と課金管理者の両方のアクセス許可を持つ管理者のみが使用できます。
* 30 日間の無料試用版でプランを購入する場合、請求書の請求は利用できません。

## <a name="manage-subscriptions-in-teams-admin-center"></a>Teams 管理センターでサブスクリプションを管理する

Teams 管理者センターでは、購入したアプリのサブスクリプションとライセンスを管理できます。 アプリ サブスクリプションとその詳細の一覧を表示し、次のアクションを実行できます。

* プランを変更する
* ライセンスの購入または削除
* 支払い方法を更新する
* サブスクリプションを取り消す
* 請求書を表示する

  :::image type="content" source="media/manage-existing-subscriptions-actions.png" alt-text="アプリのサブスクリプションの詳細のスクリーンショット。" lightbox="media/manage-existing-subscriptions-all.png":::

サブスクリプションを管理するには、次の手順に従います。

1. Teams 管理センターにサインインし、**Teams アプリ** > にアクセス [**する アプリを管理します**](https://admin.teams.microsoft.com/policies/manage-apps)。

1. [サブスクリプション] タブ **を** 選択して、購入したサブスクリプションを表示します。

   :::image type="content" source="media/subscription-options-in-manage-apps.png" alt-text="[アプリの管理] ページのアプリのサブスクリプション オプションのスクリーンショット。" lightbox="media/manage-app-subscriptions-manage-apps.png":::

> [!NOTE]
> Teams 管理センターでは、自分または同じ課金アカウントの一部である他の管理者が購入したアプリ サブスクリプションを管理できます。 他の管理者が同じテナントで購入した、または別の課金アカウントを使用して購入したすべてのアプリ サブスクリプションを表示するには、[Microsoft 365 管理センター](https://admin.microsoft.com/adminportal/home#/homepage)にアクセスします。

## <a name="list-and-sell-a-saas-offer-for-a-teams-app"></a>Teams アプリの SaaS オファーの一覧表示と販売

開発者は、Teams アプリに関連付けられた SaaS オファーを作成できます。 これらのオファーは、[パートナー センター](https://partner.microsoft.com) を通じて公開され、組織は [AppSource](https://appsource.microsoft.com/) および Microsoft Teams 管理センターを通じて購入できます。

サード パーティ製アプリ開発者向けの詳細については[ SaaS オファーの作成](/azure/marketplace/partner-center-portal/create-new-saas-offer)を参照してください。

## <a name="related-articles"></a>関連記事

* [Microsoft Teams 管理センターで、Teams アプリの組織向けアプリを管理します。](manage-apps.md)
* [ SaaS オファーを作成します](/azure/marketplace/partner-center-portal/create-new-saas-offer)
* [Azure Active Directory 組み込みロール](/azure/active-directory/roles/permissions-reference)
* [Microsoft 365 管理者ロール](/microsoft-365/admin/add-users/about-admin-roles)
