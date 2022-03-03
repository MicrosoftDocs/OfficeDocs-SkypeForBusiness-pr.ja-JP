---
title: リソース アカウントMicrosoft Teams 電話システム設定する
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
ms.localizationpriority: medium
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: 自動応答で使用Microsoft Teams 電話システムリソース アカウントを設定する方法について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: a0953ef81ef3128da858733931a43238531e83b6
ms.sourcegitcommit: e86e3824c300c24e022d5cb1848338278a5a96a8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/03/2022
ms.locfileid: "63053246"
---
# <a name="step-4-set-up-a-teams-phone-system-resource-account"></a>手順 4: リソース アカウントTeams 電話システム設定する

リソース アカウントは、特定のユーザーには割り当てられていない。 代わりに、無料の仮想ユーザー ライセンスを使用するリソース アカウントは、仮想マシン内のデバイスとサービスMicrosoft 365。 このMicrosoft Teams、リソース アカウントには電話番号が割り当てられた後、自動応答と通話キューに関連付けられます。

リソース アカウントを自動応答と通話キューに関連付け、1 つ以上の有料電話番号または無料電話番号を追加できます。 たとえば、あるリソース アカウントを有料電話番号に関連付け、ローカル発信者の自動応答に関連付けできます。 遠距離通話の場合は、別のリソース アカウントを無料電話番号と同じ自動応答に関連付けます。

この記事のセクションでは、リソース アカウントを設定し、そのアカウントに電話番号を割り当てる方法について説明します。 後で、リソース アカウントを自動応答に関連付ける予定です。

## <a name="obtain-virtual-user-licenses"></a>仮想ユーザー ライセンスの取得

自動応答と通話キューを操作するには、リソース アカウントにライセンスが必要です。 Standard *- Virtual User ライセンスMicrosoft Teams 電話無料のサービスを使用* できます。

> [!NOTE]
> 通話プラン バンドル ライセンスの試用期間を使用して Teams 電話にサインアップした場合にのみ、次の手順を実行する必要があります。 通話プラン バンドル ライセンスTeams 電話を購入した場合、仮想ライセンスは既にアカウントに適用されている必要があります。
>
> 仮想ライセンスが既にある場合は、グローバル管理者アクセス許可Microsoft 365アカウントを使用してログインします。 次に、[製品の課金> [に移動します](https://admin.microsoft.com/Adminportal/Home#/subscriptions)。 仮想ライセンスがある場合は、Standard - **Virtual User Microsoft Teams 電話として表示されます**。

1. [アカウントMicrosoft 365 管理センター開き、グローバル管理者であるユーザーを使用してログインします。これは通常、アカウントのサインアップに使用したアカウントMicrosoft 365。
2. 左側のナビゲーション ウィンドウで、<a href="https://admin.microsoft.com/Adminportal/Home#/catalog" target="_blank">**BillingPurchase** > </a> **servicesAdd-ons** >  >  **すべてのアドオン製品を表示するに移動します**。
3. 最後までスクロールして、Standard - **Virtual User Microsoft Teams 電話を見** つける。 [詳細 **] を選択** し、[購入] **を選択します**。
4. ライセンス購入ページで、必要な仮想ユーザー ライセンスの数を選択します。 設定する予定の自動応答と通話キューごとに 1 つの仮想ライセンスが必要です。 少なくとも 5 つのライセンスを選択することをお勧めします。今後、より多くの自動応答と通話キューを簡単にセットアップできます。ライセンスを今すぐ追加購入する必要はありません。
5. [ **ライセンスがないすべてのユーザーに自動的に割り当てる] チェック ボックスをオフにします**。
6. [今 **すぐチェックアウト] を選択します**。
7. ご注文を確認し、[次 **へ] を選択** してから、[注文 **] を選択します**。

> [!NOTE]
> コストが 0 の  **場合でも、** ライセンスを購入する必要があります。

## <a name="create-a-resource-account"></a>リソース アカウントを作成する

Microsoft Teams 電話 *Standard - Virtual User* ライセンスを受け取った後、リソース アカウントを作成できます。

1. 管理センター Microsoft Teams開き、グローバル管理者であるユーザーでログインします。これは通常、アカウントのサインアップに使用したアカウントMicrosoft 365。
2. 左側のナビゲーション ウィンドウで、[組織全体の <a href="https://admin.teams.microsoft.com/company-wide-settings/resource-accounts" target="_blank">**設定**][リソース アカウント > ] **に移動します**</a>。
3. **[追加]** を選択します。
4. [リソース **アカウントの追加] ウィンドウで** 、[表示名] **に入力** し、[ユーザー名] を **入力します**。 "メイン ライン 自動応答" などのわかりやすい表示名を選択して、リソース アカウントの目的を説明します。
5. [ **リソース アカウントの種類] で、[** 自動応答 **] を選択します**。
6. **[保存]** を選択します。

## <a name="assign-a-license"></a>ライセンスを割り当てる

リソース アカウントを作成したら、Microsoft Teams 電話 *Standard - Virtual User* ライセンスまたは Teams 電話 *Standard ライセンスを割り当てる必要* があります。

1. [アカウントMicrosoft 365 管理センター開き、グローバル管理者であるユーザーを使用してログインします。これは通常、アカウントのサインアップに使用したアカウントMicrosoft 365。
1. 左側のナビゲーション ウィンドウで、[ユーザー]アクティブ <a href="https://admin.microsoft.com/Adminportal/Home#/users" target="_blank">**ユーザーに** > **移動します**</a>。
1. リソース アカウントを選択します。
1. [ライセンスと **アプリ] タブの** [ライセンス **] で、[Microsoft Teams 電話** **- 仮想ユーザー] を選択します**。
1. [変更の **保存] を選択し** 、[閉じる] **を選択します**。

## <a name="assign-a-service-number"></a>サービス番号を割り当てる

1. 管理センター Microsoft Teams開き、グローバル管理者であるユーザーでログインします。これは通常、アカウントのサインアップに使用したアカウントMicrosoft 365。
1. 左側のナビゲーション ウィンドウで、[組織全体の <a href="https://admin.teams.microsoft.com/company-wide-settings/resource-accounts" target="_blank">**設定**][リソース アカウント > ] **に移動します**</a>。
1. 作成したリソース アカウントを選択し、[割り当て/割り当て解除] **をクリックします**。
1. [電話番号の **電話ボックスで、[オンライン**] を **選択します**。
1. [割 **り当て済み** 電話番号] ボックスで、使用する番号を検索し、[追加] をクリック **します**。 国コードを必ず含める (例: **+1** 250 555 0012)
1. **[保存]** をクリックします。

> [!div class="nextstepaction"]
> [次の手順: ユーザーに電話番号を割り当てる](set-up-assign-numbers.md)
