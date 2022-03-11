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
description: 組織内のリソース アカウントに無料の Teams 電話 Standard – 仮想ユーザー ライセンスまたは有料 Teams 電話 Standard ユーザー ライセンスを割り当てる方法について説明します。
ms.openlocfilehash: 542d80a8cb463df01e6e232454b2454a939a457b
ms.sourcegitcommit: ff975c21725e1812e6db8fc9fe37de1362f168c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/11/2022
ms.locfileid: "63435731"
---
# <a name="microsoft-teams-phone-standard--virtual-user-licenses"></a>Microsoft Teams 電話 Standard – 仮想ユーザー ライセンス

Teams 電話 Standard または Teams 電話 で通話プランのライセンスを持つ組織は、無料の *Microsoft Teams 電話 Standard –* 仮想ユーザー ライセンスまたは *有料 Teams 電話 Standard* ユーザー ライセンスをリソース アカウントに割り当てできます。 Microsoft 通話プランは必ずしも必要とは限らない (外部の電話番号に通話を転送する際の前提条件については、「[Teams 自動](../plan-auto-attendant-call-queue.md#prerequisites)応答と通話キューの計画」を参照してください)。

すべての自動応答と通話キューには、関連付けられたリソース アカウントが必要です。 電話番号を必要とするリソース アカウントには、リソース アカウントに電話番号を適用する前に、無料の *Microsoft Teams 電話 Standard –* 仮想ユーザー ライセンスまたは *有料 Teams 電話 Standard* ユーザー ライセンスが必要です。

> [!TIP]
> 入れ子になった自動応答または電話番号が割り当てられていない通話キューで使用されるリソース アカウントのライセンスは必要はありません。 参照については、次の図を参照してください。

:::image type="content" alt-text="仮想ユーザー ライセンス。" source="../media/resource-account.png":::

## <a name="virtual-user-license-allocation"></a>仮想ユーザー ライセンスの割り当て

組織は、全体的なMicrosoft Teams 電話に応じて *Standard – Virtual User* ライセンスに割り当てされます。 Teams 電話システム で少なくとも 1 つのライセンスを持つ組織 (通話プランのライセンスを持つ Teams 電話 Standard と Teams 電話 を含む) には、25 の仮想ユーザー ライセンスが無料で利用できます。 組織内の通話プランのユーザー ライセンスTeams 電話 10 Teams 電話 または Teams 電話 を追加すると、*Microsoft Teams 電話 Standard – Virtual User* ライセンスが 1 つ追加されます。

> [!NOTE]
> Teams 電話プランを使用Teams 電話 Standard と通話プランは、すべてのサブスクライバーが利用できるアドオン Microsoft 365です。 Teams 電話 Standard ライセンスは、プランの一部Microsoft 365 E5されます。

組織で自動応答ノードまたは通話キュー ノードの作成で *無料の Microsoft Teams 電話 Standard – Virtual User* ライセンスを使用している場合でも、リソース アカウントで *有料の Teams 電話 Standard* ライセンスを使用できます。 ほとんどの組織は、スケーリング 計画に基づいて十分な仮想ユーザー ライセンスを持っています。

### <a name="license-allocation-example"></a>ライセンス割り当ての例

Contoso, Inc. は、600 ライセンスを購入しました。このライセンスには電話システム (従業員ごとに 1 つ) が含まれています。 Contoso には、最初の 25 ライセンスと 60 Microsoft Teams 電話 *Standard – Virtual User* ライセンス (合計 85 ライセンス) が割り当てされます。 組織には、電話番号を含む 90 の通話キューと自動応答があります。 Standard - Virtual User ライセンスMicrosoft Teams 電話 *割* り当て、Standard ライセンスで通常価格の *5 Teams 電話取得する必要* があります。

Contoso は、自動応答と通話キュー システムの再設計を検討する必要があります。 使用する電話番号が少なく、入れ子になったノードが電話番号を必要としない場合は、実装が簡素化され、コストが削減されます。

## <a name="how-to-buy-microsoft-teams-phone-standard--virtual-user-licenses"></a>Standard – 仮想Microsoft Teams 電話ライセンスを購入する方法

1. Microsoft 365 管理センターにサインインします。
2.  > **BillingPurchase servicesAdd-ons** >  **に移動します**。
3. 最後までスクロールして、Standard - **Virtual User Microsoft Teams 電話を見** つける。 [今すぐ **購入] を選択します**。

   > [!NOTE]
   > コストが 0 の **場合でも、** ライセンスを購入する必要があります。

## <a name="change-an-existing-resource-account-to-use-a-microsoft-teams-phone-standard--virtual-user-license"></a>既存のリソース アカウントを変更して、Microsoft Teams 電話 Standard – Virtual User ライセンスを使用する

リソース アカウントのライセンスを Teams 電話 Standard ライセンスから *Microsoft Teams 電話 Standard* *– Virtual User* ライセンスに切り替える場合:

1. 新しい Microsoft Teams 電話 Standard – Virtual User ライセンスを取得します。
2. ユーザーを別のサブスクリプションに移動Microsoft 365 管理センターの[リンクされた手順に従います](/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription)。

> [!WARNING]
> Standard ライセンスの完全Teams 電話 *削除* し、同じライセンス アクティビティMicrosoft Teams 電話 *Standard - Virtual User* ライセンスを割り当てる必要があります。 古いライセンスを削除し、アカウントの変更を保存し、新しいライセンスを追加して、アカウント設定を再度保存すると、リソース アカウントが期待した通り機能しなくなる可能性があります。 このような場合は、Microsoft Teams 電話 *Standard – Virtual User* ライセンスの新しいリソース アカウントを作成し、破損したリソース アカウントを削除することをお勧めします。

## <a name="related-information"></a>関連情報

[自動応答および Call Queues Service Update](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521)

[Microsoft Teams のリソースのアカウントの管理](../manage-resource-accounts.md)
