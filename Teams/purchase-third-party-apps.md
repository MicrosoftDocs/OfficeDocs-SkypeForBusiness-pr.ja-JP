---
title: Teams 用のサード パーティ製アプリを購入する
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: chhavib, vaibhava, nsuter
search.appverid: MET150
f1keywords: ''
description: クレジット カード、デビット カード、または請求書の請求を使用して、Teams ストアからサード パーティ製アプリを購入する方法について説明します。
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.openlocfilehash: 8627d94fc384064b484019ecc17b2e4701e945e8
ms.sourcegitcommit: 89904ab4116294ad9e4fd407feba8d7e3eefef10
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/19/2022
ms.locfileid: "66880241"
---
# <a name="purchase-third-party-apps-for-teams"></a>Teams 用のサード パーティ製アプリを購入する

Teams アプリは無料でインストールでき、アプリの完全な機能とスコープを体験するためにサービス サブスクリプションの購入が必要になる場合があります。 これらのサービス サブスクリプションは、Software as a Service (SaaS) オファーと呼ばれ、 [AppSource](https://appsource.microsoft.com/) を通じて、現在 [は Microsoft Teams 管理センター](https://admin.teams.microsoft.com)を通じて購入できます。

Microsoft Teams 管理センターの [ [アプリの管理](manage-apps.md) ] ページでは、組織のすべての Teams アプリを表示および管理できます。 たとえば、アプリの組織レベルの状態とプロパティを確認したり、新しいカスタム アプリを組織のアプリ ストアにアップロードしたり、組織レベルでアプリをブロックまたは許可したり、組織全体のアプリ設定を管理したりできます。

ここでは、組織内のユーザー向けにサード パーティ製アプリによって提供されるサービスのライセンスを購入することもできます。 表の **[ライセンス** ] 列は、アプリが SaaS サブスクリプションを購入用に提供するかどうかを示します。

![購入ライセンスの [アプリの管理] ページのスクリーンショット。](media/manage-apps-new-page.png)

## <a name="purchase-apps-in-the-teams-admin-center"></a>Teams 管理センターでアプリを購入する

> [!IMPORTANT]
> アプリの購入を有効にすると、アプリ内購入も有効になります。 ユーザーには、アプリの ISV によって制御されるアプリ内購入オファーが表示される場合があります。 ユーザーがアプリを購入できないようにするには、アプリをブロックする必要があります。 アプリをブロックする方法の詳細については、「 [アプリ ポリシーの管理](app-policies.md) 」または [「組織レベルでアプリをブロックする方法」を参照](manage-apps.md#allow-and-block-apps)してください。

1. Microsoft Teams 管理センターの左側のウィンドウで、**Teams アプリ** の **[[アプリ](https://admin.teams.microsoft.com/policies/manage-apps)** > の管理] に移動します。 ページにアクセスするには、グローバル管理者または Teams サービス管理者である必要があります。

1. 目的のアプリをその名前で検索します。 有料 SaaS サブスクリプションを持つアプリを特定するには、[ **ライセンス** ] 列を確認します。 各アプリには、次のいずれかの値があります。
    * **今すぐ購入**: このアプリは SaaS サブスクリプションを提供しており、購入が可能です。  
    * **購入済み**: このアプリは SaaS サブスクリプションを提供しており、そのライセンスを購入済みです。
    * **- -**: このアプリは SaaS サブスクリプションを提供していません。

1. アプリが見つかると、[ **購入** ] を選択して、アプリの詳細ページの [ **プランと価格** ] タブに移動します。 アプリの SaaS オファーのプランと価格情報を確認します。 詳細が必要な場合は、[ **詳細情報** ] を選択して [AppSource](https://appsource.microsoft.com/) のアプリのページに移動します。

   > [!NOTE]
   > プライベート プランは、組織が ISV と以前に交渉した特別価格を含む、購入用に一覧表示される場合もあります。 これらのプランには、プラン名の下に **プライベート プラン** というラベルが付けられます。

1. アプリをサブスクライブするには、目的のプランを選択し、[ **購入**] を選択します。 チェックアウト フローは、Teams 管理センターで直接開きます。

1. 購入するユーザー ライセンスの数を選択します。

1. 課金アカウントと販売先住所が正しいことを確認します。 まだお持ちでない場合は、[追加] を選択 **します**。 課金アカウントの詳細については、「 [課金アカウントについて](/microsoft-365/commerce/manage-billing-accounts)」を参照してください。

   > [!NOTE]
   > グローバル 管理のみが新しい課金アカウントを追加できます。

1. 正しい課金プロファイルが選択されていることを確認します。 まだお持ちでない場合は、[ **新しい追加**] を選択します。 クレジット カード、デビット カード、または [請求書の請求](#invoice-billing)で支払うオプションがあります。 課金プロファイルでは、後で注文を識別する発注書番号を追加することもできます。 課金プロファイルの詳細については、「 [課金プロファイルについて](/microsoft-365/commerce/billing-and-payments/manage-billing-profiles)」を参照してください。

1. [ **注文] を選択します**。

1. [ **設定** ] を選択して、発行元の Web サイトでサブスクリプションをアクティブ化します。 購入後にサブスクリプションを設定していない場合は、後で [ **ライセンスの管理**] を選択して行うことができます。

Teams アプリに関連付けられている SaaS オファーを購入したら、アプリの詳細ページの [ **プランと価格** ] タブで次の購入の詳細を表示できます。

* **ライセンスのアクティブ化日**: ライセンスがアクティブ化された日付。 アカウントがまだ設定されていない場合は、 **アクティブ化が保留中のサブスクリプション** として表示されます。
* **ライセンス**: 購入したライセンスの数。

:::image type="content" source="media/purchase-third-party-apps-details-page.png" alt-text="Teams 管理センターのアプリの詳細ページにある [プランと価格] タブのスクリーンショット。":::

購入したライセンスを表示および管理するには、[**ライセンスの管理**] を選択してMicrosoft 365 管理センターにアクセスします。

グローバル管理者は、組織内のすべてのユーザーが行った購入に対して、ライセンスの追加、ライセンスの削除、サブスクリプションの取り消しを行うことができます。 Teams サービス管理者は、自分で行った購入に対して同じアクションを実行できます。 ただし、Teams サービス管理者にも課金管理者ロールがある場合は、組織内のすべてのユーザーが購入した購入を管理できます。

> [!NOTE]
> グローバル 管理が別のグローバル 管理で購入したサブスクリプションを管理する場合は、同じ課金アカウントに含める必要があります。 Microsoft 365 管理センターでアプリを選択すると、購入したサブスクリプションに別のグローバル [管理](https://admin.microsoft.com) アクセス権を付与できます。 そこから、[課金プロファイル > の **表示] に移動し****、[課金アカウント** > **の割り当てロール** > の選択]**他のグローバル管理者を追加します**。

### <a name="invoice-billing"></a>請求書の請求

* 請求書の請求は、一部のトランザクションの支払いオプションとして使用できます。
* 請求書の請求を初めて使用するときは、クレジット レビューが必要です。承認には最大 24 ~ 48 時間かかる場合があります。 請求書の請求は、クレジット チェックが完了するまで利用できません。 クレジット カードを使用して注文を行うか、クレジット レビューが承認された後でもう一度お試しください。
* 請求書の請求は、グローバル管理者または Teams サービス管理者と課金管理者の両方のアクセス許可を持つ管理者にのみ使用できます。
* 30 日間の無料試用版でプランを購入する場合、請求書の請求は利用できません。

## <a name="list-and-sell-a-saas-offer-for-a-teams-app"></a>Teams アプリの SaaS オファーを一覧表示して販売する

開発者は、Teams アプリに関連付けられた SaaS オファーを作成できます。 これらのオファーは [パートナー センター](https://partner.microsoft.com) を通じて発行され、組織は [AppSource](https://appsource.microsoft.com/) と Microsoft Teams 管理センターを通じて購入できます。

サード パーティのアプリ開発者向けの詳細については、「 [SaaS オファーの作成](/azure/marketplace/partner-center-portal/create-new-saas-offer)」を参照してください。

## <a name="related-articles"></a>関連記事

* [Microsoft Teams 管理センターで、Teams アプリの組織向けアプリを管理します。](manage-apps.md)
* [SaaS オファーを作成する](/azure/marketplace/partner-center-portal/create-new-saas-offer)
* [Azure Active Directory 組み込みロール](/azure/active-directory/roles/permissions-reference)
* [Microsoft 365 管理者ロール](/microsoft-365/admin/add-users/about-admin-roles)
