---
title: Microsoft Teams 電話 Standard – 仮想ユーザー ライセンス
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: waseemh
ms.topic: reference
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.custom:
- Licensing
- LIL_Placement
- seo-marvel-apr2020
description: Free Teams 電話 Standard – Virtual User ライセンスまたは有料Teams 電話 Standard ユーザー ライセンスを組織内のリソース アカウントに割り当てる方法について説明します。
ms.openlocfilehash: 542d80a8cb463df01e6e232454b2454a939a457b
ms.sourcegitcommit: ff975c21725e1812e6db8fc9fe37de1362f168c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/11/2022
ms.locfileid: "63435731"
---
# <a name="microsoft-teams-phone-standard--virtual-user-licenses"></a>Microsoft Teams 電話 Standard – 仮想ユーザー ライセンス

Teams 電話 Standard または通話プランのライセンスを持つTeams 電話を持つ組織は、無料 *のMicrosoft Teams 電話 Standard - Virtual User* ライセンスまたは有料 *Teams 電話 Standard* ユーザー ライセンスのいずれかをリソース アカウントに割り当てることができます。 Microsoft 通話プランは必ずしも必要ではありません (外部電話番号に通話を転送する場合の前提条件については、「[自動応答と通話キューのTeams計画](../plan-auto-attendant-call-queue.md#prerequisites)」を参照してください)。

すべての自動応答と呼び出しキューには、関連付けられたリソース アカウントが必要です。 電話番号を必要とするリソース アカウントには、無料 *Microsoft Teams 電話の Standard – Virtual User* ライセンスまたは有料 *Teams 電話 Standard* ユーザー ライセンスのいずれかが必要です。その後、電話番号をリソース アカウントに適用できます。

> [!TIP]
> 入れ子になった自動応答または電話番号が割り当てられていない通話キューで使用されるリソース アカウントには、ライセンスは必要ありません。 参照については、次の図を参照してください。

:::image type="content" alt-text="仮想ユーザー ライセンス。" source="../media/resource-account.png":::

## <a name="virtual-user-license-allocation"></a>仮想ユーザー ライセンスの割り当て

組織は、全体のサイズに応じて *Standard – Virtual User ライセンスMicrosoft Teams 電話* 割り当てられます。 Teams 電話システムを持つ少なくとも 1 つのライセンスを持つ組織 (Teams 電話 Standard ライセンスと通話プラン ライセンスを使用したTeams 電話を含む) には、25 個の仮想ユーザー ライセンスが無償で使用できます。 組織内の通話プラン ユーザー ライセンスで 10 Teams 電話 Standard またはTeams 電話を追加すると、Standard *- Virtual User ライセンスMicrosoft Teams 電話* もう 1 つ使用できるようになります。

> [!NOTE]
> 通話プランTeams 電話標準およびTeams 電話は、すべてのMicrosoft 365サブスクライバーが利用できるアドオン ライセンスです。 Teams 電話 Standard ライセンスは、Microsoft 365 E5 プランの一部としても含まれています。

組織が、自動応答ノードの作成またはキュー ノードの呼び出しで無料 *の Standard – Virtual User* ライセンスMicrosoft Teams 電話使用している場合でも、有料 *のTeams 電話 Standard* ライセンスをリソース アカウントで使用できます。 ほとんどの組織は、スケーリング計画に基づいて十分な仮想ユーザー ライセンスを持つことになります。

### <a name="license-allocation-example"></a>ライセンス割り当ての例

Contoso, Inc. は、電話システムを含む 600 ライセンスを購入しました (従業員ごとに 1 つ)。 Contoso には、Standard の最初の 25 と 60 *Microsoft Teams 電話の仮想ユーザー* ライセンスが割り当てられ、合計で 85 が割り当てられている。 組織には、電話番号を持つ 90 の通話キューと自動応答があります。 すべての *Microsoft Teams 電話 Standard – Virtual User* ライセンスを割り当て、標準ライセンスTeams 電話通常価格の 5 *つのライセンスを* 取得する必要があります。

Contoso は、自動応答と呼び出しキュー システムの再設計を検討する必要があります。 電話番号が少なく、電話番号を必要としない入れ子になったノードが多い場合は、実装が簡略化され、コストが削減されます。

## <a name="how-to-buy-microsoft-teams-phone-standard--virtual-user-licenses"></a>Microsoft Teams 電話 Standard – Virtual User ライセンスを購入する方法

1. Microsoft 365 管理センターにサインインします。
2. **BillingPurchase** >  **servicesAdd-ons** >  に移動します。
3. 最後までスクロールして **、Microsoft Teams 電話 Standard – Virtual User ライセンスを** 見つけます。 [ **今すぐ購入]** を選択します。

   > [!NOTE]
   > ライセンスのコストが 0 であっても、ライセンスを **購入** する必要があることに注意してください。

## <a name="change-an-existing-resource-account-to-use-a-microsoft-teams-phone-standard--virtual-user-license"></a>Microsoft Teams 電話 Standard – Virtual User ライセンスを使用するように既存のリソース アカウントを変更する

リソース アカウントのライセンスを *Teams 電話 Standard* ライセンスから *Microsoft Teams 電話 Standard – Virtual User* ライセンスに切り替える場合:

1. 新しい Microsoft Teams 電話 Standard – Virtual User ライセンスを取得します。
2. Microsoft 365 管理 センターのリンクされた手順に従って、[ユーザーを別のサブスクリプションに移動します](/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription)。

> [!WARNING]
> Standard ライセンス *Teams 電話* 完全に削除し、同じライセンス アクティビティ *で standard - Virtual User ライセンスMicrosoft Teams 電話* 割り当てます。 古いライセンスを削除し、アカウントの変更を保存し、新しいライセンスを追加して、アカウント設定をもう一度保存すると、リソース アカウントが期待どおりに機能しなくなる可能性があります。 このような場合は、*Microsoft Teams 電話 Standard – Virtual User* ライセンスの新しいリソース アカウントを作成し、破損したリソース アカウントを削除することをお勧めします。

## <a name="related-information"></a>関連情報

[自動応答と通話キュー サービスの更新](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521)

[Microsoft Teams のリソースのアカウントの管理](../manage-resource-accounts.md)
