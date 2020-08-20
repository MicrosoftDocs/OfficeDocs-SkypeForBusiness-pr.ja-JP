---
title: Microsoft Teams 管理センターで Teams サードパーティ アプリのサービスを購入する
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: chhavib, vaibhava
search.appverid: MET150
f1keywords: ''
description: Microsoft Teams 管理センターの [アプリの管理] ページで、Teams サードパーティ アプリのサービスを購入する方法について説明します。
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: aeff6f363c1ae594a4a122055204d98b43d246e8
ms.sourcegitcommit: e0e089f0ab217d920e128377af653f7dbfdedacf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46818156"
---
<a name="purchase-services-for-teams-third-party-apps-in-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターで Teams サードパーティ アプリのサービスを購入する
======================================================

> [!NOTE]
> 現在、この機能は米国でのみご利用いただけます。

Teams アプリは無料でインストールできます。また、アプリの完全な機能とスコープを体験するため、サービス サブスクリプションの購入が必要になる場合があります。 これらのサービス サブスクリプションは [、AppSource](https://appsource.microsoft.com/) を通じて購入可能で Microsoft Teams 管理センターを通じて、サービスとしてのソフトウェアと呼びます。

Microsoft Teams [管理センター](manage-apps.md) の [アプリの管理] ページでは、組織のすべての Teams アプリを表示して管理することができます。 たとえば、アプリのプロパティの表示、新しいカスタム アプリの組織のアプリ ストアへのアップロード、組織レベルでのアプリのブロックまたは許可、組織全体のアプリ設定の管理などを行うことができます。

ここでは、サードパーティ アプリによってサービスのライセンスを購入することもできます。 表 **の [** ライセンス] 列は、アプリが購入する SaaS サブスクリプションをサービスで用語を与えるかどうかを示します。

:::image type="content" source="media/purchase-third-party-apps-list.png" alt-text="SaaS サブスクリプションを持つサードパーティのアプリを示すスクリーンショット":::

## <a name="search-for-and-purchase-services-for-a-third-party-app"></a>サードパーティのアプリのサービスを検索して購入する

1. Microsoft Teams 管理センターの左側のナビゲーションで、Teams アプリの管理**アプリ**  >  **に移動します**。 ページにアクセスするには、グローバル管理者または Teams のサービス管理者である必要があります。
2. 必要なアプリを検索します。 SaaS サブスクリプションがあるアプリを識別するには、[ライセンス] **列を確認** します。 各アプリには次のいずれかの値があります。
    - **今すぐ**購入: アプリには SaaS サブスクリプションが用い、購入できます。  
    - **購入**済み : アプリには SaaS サブスクリプションが用い、そのためのライセンスを購入済み。
    - **-**- アプリで SaaS サブスクリプションは利用できません。
3. アプリが見つかったら、[今すぐ**購入]** をクリックして、アプリの詳細ページの [プランと価格設定] タブに移動します。 **Plans and pricing** アプリの SaaS プランのプランと価格情報を確認します。 詳細情報が必要な場合は、詳細リンク **を** クリックして AppSource のアプリのページに [移動してください](https://appsource.microsoft.com/)。  
4. プランを購入するには、[今すぐ **購入] をクリックします**。 Teams アプリに関連付けられているオフデベロッパーの購入エクスペリエンスにリダイレクトされます。 ここで、サービスや SaaS プランの購入を完了します。
5. 目的のプランを選択します。 SaaS プランに複数のプランが含まれる場合は、[変更] **をクリック** して利用可能なプランのリストを表示します。
6. 請求条件 (月間または**年**単位**Monthly**) を選び、購入するユーザー ライセンスの数を入力します。
7. お支払い方法を入力します。
8. 準備ができたら、[注文] **を選択します**。
9. [ **今すぐ構成** ] をクリックして、発行元の Web サイトでサブスクリプションをアクティブ化します。

Teams アプリに関連付けられている SaaS プランを購入すると、アプリの詳細ページの **[プラン** と価格] タブで次の購入の詳細を確認できます。

- **ライセンス認証の日付**: ライセンスがライセンス認証された日付。 アカウントがまだ設定されない場合は、サブスクリプションの保留中 **のライセンス認証が保留中として表示されます**。
- **ライセンス**: 購入したライセンス数。

:::image type="content" source="media/purchase-third-party-apps-details-page.png" alt-text="アプリ詳細ページの [プランと価格] タブのスクリーンショット":::

[ **ライセンスの管理** ] を選択して、Microsoft 365 管理センターに移動し、購入したライセンスを表示および管理し、ユーザーのライセンス割り当てを管理します。

全体管理者は、組織内のユーザーが行った購入を表示できます。この場合、Teams サービス管理者は自分で行った購入の表示のみを行うことができます。  

## <a name="have-a-saas-offer-for-a-teams-app-that-you-want-to-list-and-sell-in-the-microsoft-teams-admin-center-and-appsource"></a>Microsoft Teams 管理センターと AppSource でリストアップして表示する Teams アプリ用の SaaS プランをお持びですか?

開発者は、Teams アプリに関連付けられている SaaS プランを作成できます。 これらのプランはパートナー [センターを](https://partner.microsoft.com) 通じて公開され、組織は [AppSource](https://appsource.microsoft.com/) と Microsoft Teams 管理センターを通じて購入できます。
 
サードパーティ アプリの開発者は [、SaaS プランを作成して](https://docs.microsoft.com/azure/marketplace/partner-center-portal/create-new-saas-offer) 詳細を確認してください。

## <a name="related-topics"></a>関連項目

- [Microsoft Teams 管理センターでアプリを管理する](manage-apps.md)
- [SaaS プランを作成する](https://docs.microsoft.com/azure/marketplace/partner-center-portal/create-new-saas-offer)
