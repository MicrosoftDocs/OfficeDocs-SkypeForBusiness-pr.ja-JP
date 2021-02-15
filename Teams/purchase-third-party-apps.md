---
title: Teams 用のサード パーティ製アプリを購入する
author: cichur
ms.author: v-cichur
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
description: Microsoft Teams 管理センターで Teams 用のサード パーティ製アプリを購入する方法について説明します。
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 3b90af2e0fecba2d6c421a5b26547e93b18df05d
ms.sourcegitcommit: bfada4fd06c5cff12b0eefd3384bb3c10d10787f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/12/2021
ms.locfileid: "50196181"
---
<a name="purchase-third-party-apps-for-teams"></a>Teams 用のサード パーティ製アプリを購入する
======================================================

> [!NOTE]
> 現在、この機能は米国でのみご利用いただけます。

Teams アプリは無料でインストールできます。また、アプリの完全な機能と範囲を体験するには、サービス サブスクリプションの購入が必要な場合があります。 これらのサービス サブスクリプションは、サービスとしてのソフトウェア (SaaS) オファーと呼ばれるサービスであり [、AppSource](https://appsource.microsoft.com/) から購入し、Microsoft Teams 管理センターから利用できます。

Microsoft Teams [管理センターの](manage-apps.md) [アプリの管理] ページは、組織のすべての Teams アプリを表示および管理する場所です。 たとえば、アプリの組織レベルの状態とプロパティの表示、組織のアプリ ストアへの新しいカスタム アプリのアップロード、組織レベルでのアプリのブロックまたは許可、組織全体のアプリ設定の管理を行います。

ここでは、組織内のユーザー向けサード パーティ 製アプリが提供するサービスのライセンスを購入することもできます。 表 **の [** ライセンス] 列は、アプリが SaaS サブスクリプションを購入できるかどうかを示しています。

:::image type="content" source="media/purchase-third-party-apps-list.png" alt-text="SaaS サブスクリプションを持つサード パーティ製アプリを示すスクリーンショット":::

## <a name="search-for-and-purchase-services-for-a-third-party-app"></a>サード パーティ製アプリのサービスを検索して購入する

1. Microsoft Teams 管理センターの左側のナビゲーションで、Teams アプリの [アプリの **管理]**  >  **に移動します**。 ページにアクセスするには、グローバル管理者または Teams サービス管理者である必要があります。
2. 必要なアプリを検索します。 有料 SaaS サブスクリプションを持つアプリを特定するには、[ライセンス] 列を **確認** します。 各アプリには、次のいずれかの値があります。
    - **今すぐ** 購入: アプリは SaaS サブスクリプションを提供し、購入可能です。  
    - **購入:** アプリは SaaS サブスクリプションを提供し、そのライセンスを購入しました。
    - **- -** アプリは SaaS サブスクリプションを提供しない。
3. アプリが見つけたら、[今すぐ購入] をクリックして、アプリの詳細ページの [プランと価格] タブに移動します。 アプリの SaaS プランのプランと価格情報を確認します。 詳細が必要な場合は、詳細リンクをクリックして AppSource のアプリのページに[移動します](https://appsource.microsoft.com/)。  
4. プランを購入するには、[今すぐ購入 **] をクリックします**。 Teams アプリに関連付けられているオファーの購入エクスペリエンスにリダイレクトされます。 ここで、サービスまたは SaaS サービスの購入を完了します。
5. 必要なプランを選択します。 SaaS プランに複数のプランが含まれる場合は、[変更 **]** をクリックして利用可能なプランの一覧を表示します。
6. 請求期間 (月または年)を選択し、購入するユーザー ライセンスの数を入力します。
7. 支払い方法を入力します。
8. 準備ができたら、[注文] を **選択します**。
9. [ **今すぐ構成]** をクリックして、発行元の Web サイトでサブスクリプションをアクティブ化します。

Teams アプリに関連付けられている SaaS プランを購入した後は、アプリの詳細ページの [プランと価格] タブで次の購入の詳細を表示できます。

- **ライセンスのライセンス認証日**: ライセンスがアクティブ化された日付。 アカウントがまだ設定されていない場合は、[サブスクリプションのライセンス認証が保留中 **] と表示されます**。
- **ライセンス**: 購入したライセンスの数。

:::image type="content" source="media/purchase-third-party-apps-details-page.png" alt-text="アプリの詳細ページの [プランと価格] タブのスクリーンショット":::

[ **ライセンスの管理]** を選択して Microsoft 365 管理センターに移動し、購入したライセンスを表示および管理し、ユーザーのライセンス割り当てを管理します。

グローバル管理者は組織内のすべてのユーザーが行った購入を表示できるのに対し、Teams サービス管理者は自分で行った購入のみを表示できます。  

## <a name="have-a-saas-offer-for-a-teams-app-that-you-want-to-list-and-sell-in-the-microsoft-teams-admin-center-and-appsource"></a>Microsoft Teams 管理センターと AppSource でリストと販売を行う Teams アプリの SaaS 特典はありますか?

開発者は、Teams アプリに関連付けられた SaaS オファーを作成できます。 これらのオファーはパートナー [センターを](https://partner.microsoft.com) 通じて公開され、組織は [AppSource](https://appsource.microsoft.com/) と Microsoft Teams 管理センターを通じて購入できます。
 
サード パーティ製アプリの開発者は [、「SaaS](https://docs.microsoft.com/azure/marketplace/partner-center-portal/create-new-saas-offer) サービスを作成する」で詳細を確認できます。

## <a name="related-topics"></a>関連項目

- [Microsoft Teams 管理センターでアプリを管理する](manage-apps.md)
- [SaaS サービスを作成する](https://docs.microsoft.com/azure/marketplace/partner-center-portal/create-new-saas-offer)
