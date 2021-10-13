---
title: Microsoft 365 電話システム – 仮想ユーザー ライセンス
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
description: 組織内のリソース アカウントに無料の 電話システム 仮想ユーザー ライセンスまたは有料のユーザー ライセンス電話システム割り当てる方法について説明します。
ms.openlocfilehash: f0a26c03a5654a3f2df9538fe8bbb74c4a5b58e4
ms.sourcegitcommit: 11882e93618b8d69d21586c7b1f6a4460b96dd7d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2021
ms.locfileid: "60283001"
---
# <a name="microsoft-365-phone-system--virtual-user-license"></a>Microsoft 365 電話システム – 仮想ユーザー ライセンス

ライセンスを電話システムを持つ組織は、無料の Microsoft 365 電話システム – 仮想ユーザー ライセンスまたは有料のユーザー ライセンスをリソース 電話システムに割り当てできます。 通話プランは必ずしも必要とは限らない[](../plan-auto-attendant-call-queue.md#prerequisites)(外部の電話番号に通話を転送する際の前提条件については、「Teams 自動応答と通話キューの計画」を参照してください)。 すべての自動応答または通話キューには、関連付けられているリソース アカウントが必要です。 電話番号を必要とするリソース アカウントには、リソース アカウントに電話番号を適用する前に、無料の Microsoft 365 電話システム – 仮想ユーザー ライセンスまたは有料 電話システム ユーザー ライセンスが必要です。

> [!TIP]
> 入れ子になった自動応答または電話番号が割り当てられていない通話キューで使用されるリソース アカウントのライセンスは必要はありません。 参照については、次の図を参照してください。

:::image type="content" alt-text="仮想ユーザー ライセンス。" source="../media/resource-account.png":::

## <a name="virtual-user-license-allocation"></a>仮想ユーザー ライセンスの割り当て

組織には、全体的なMicrosoft 365 電話システムに応じて仮想ユーザー ライセンスが割り当てされます。 仮想マシンを含む少なくとも 1 つのライセンスを持電話システム追加された電話システム、無料で 25 の仮想ユーザー ライセンスを利用できます。 組織内のユーザー ライセンスを 10 電話システムすると、仮想ユーザー ライセンスMicrosoft 365 電話システムライセンスが利用可能になります。

> [!NOTE]
> 電話システムは、Microsoft 365 および E3 でOffice 365 E1ライセンスです。 電話システムは、Microsoft 365 E5、Office 365 E5、Microsoft 365 Business Voiceの一部としてMicrosoft 365 Business Voiceされます。

組織で利用可能な無料の Microsoft 365 電話システム – 仮想ユーザー ライセンスを使用して自動応答ノードまたは通話キュー ノードを作成している場合でも、リソース アカウントで有料の 電話 システム ライセンスを使用できます。 ほとんどの組織は、スケーリング 計画に基づいて十分な仮想ユーザー ライセンスを持っています。 

### <a name="license-allocation-example"></a>ライセンス割り当ての例

Contoso, Inc. は、従業員ごとに 1 電話システム含む 600 ライセンスを購入しました。 Contoso には、最初の 25 と 60 Microsoft 365 電話システム – 仮想ユーザー ライセンス (合計 85) が割り当てされます。 組織には、電話番号を含む 90 の通話キューと自動応答があります。 すべての仮想ユーザー ライセンスを割り当Microsoft 365 電話システム、通常価格のライセンスを 5 つ取得電話システムがあります。

Contoso は、自動応答と通話キュー システムの再設計を検討する必要があります。 使用する電話番号が少なく、入れ子になったノードが電話番号を必要としない場合は、実装が簡素化され、コストが削減されます。

## <a name="how-to-buy-microsoft-365-phone-system--virtual-user-licenses"></a>仮想ユーザー ライセンスMicrosoft 365 電話システム購入する方法

1. Microsoft 365 管理センターにサインインします。
2. 課金購入  >  **サービスの**  >  **アドオンに移動する**
3. 最後までスクロールして、[仮想ユーザー] **Microsoft 365 電話システムを見** つける。 [今 **すぐ購入] を選択します**。

   > [!NOTE]
   > コストが 0 の **場合でも、** ライセンスを購入する必要があります。

## <a name="change-an-existing-resource-account-to-use-a-microsoft-365-phone-system--virtual-user-license"></a>既存のリソース アカウントを変更して仮想ユーザー ライセンスMicrosoft 365 電話システムを使用する

リソース アカウントのライセンスをリソース アカウントのライセンスから 電話システム – 仮想ユーザー ライセンスMicrosoft 365 電話システム切り替える場合は、次の操作を行います。

1. 新しいライセンスをMicrosoft 365 電話システム – 仮想ユーザー ライセンス。
2. ユーザーを別のサブスクリプションに移動するには、Microsoft 365 管理 センター[のリンクされた手順に従います](/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription)。

> [!WARNING]
> 常に完全なライセンス 電話システム削除し、同じライセンス アクティビティMicrosoft 365 電話システム – 仮想ユーザー ライセンスを割り当てる必要があります。 古いライセンスを削除し、アカウントの変更を保存し、新しいライセンスを追加して、アカウント設定を再度保存すると、リソース アカウントが期待した通り機能しなくなる可能性があります。 このような場合は、新しいリソース アカウントを Microsoft 365 電話システム – Virtual User ライセンス用に作成し、破損したリソース アカウントを削除することをお勧めします。 

## <a name="related-information"></a>関連情報

[自動応答および Call Queues Service Update](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521)

[Microsoft Teams のリソースのアカウントの管理](../manage-resource-accounts.md)
