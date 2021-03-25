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
localization_priority: Normal
ms.custom:
- Licensing
- LIL_Placement
- seo-marvel-apr2020
description: 組織内のリソース アカウントに無料の電話システム – 仮想ユーザー ライセンスまたは有料電話システム ユーザー ライセンスを割り当てる方法について説明します。
ms.openlocfilehash: 8e5322ccf7e3e7ad05c499b3dbcfdac65d0dfedb
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116925"
---
# <a name="microsoft-365-phone-system--virtual-user-license"></a>Microsoft 365 電話システム – 仮想ユーザー ライセンス

電話システムのライセンスを取得したユーザーを持つ組織は、無料の Microsoft 365 電話システム – 仮想ユーザー ライセンスまたは有料電話システム ユーザー ライセンスのいずれかをリソース アカウントに割り当てできます。 通話プランは必要ありません。 すべての自動応答または通話キューには、関連付けられたリソース アカウントが必要です。 電話番号を必要とするリソース アカウントでは、電話番号をリソース アカウントに適用するには、無料の Microsoft 365 電話システム ( 仮想ユーザー ライセンスまたは有料の電話システム ユーザー ライセンス) が必要です。

> [!TIP]
> 入れ子になった自動応答または電話番号が割り当てられていない通話キューで使用されるリソース アカウントのライセンスは必要はありません。 参照については、次の図を参照してください。 

![仮想ユーザー ライセンス](../media/resource-account.png)

## <a name="virtual-user-license-allocation"></a>仮想ユーザー ライセンスの割り当て

組織には、全体的なサイズに応じて、Microsoft 365 電話システム – 仮想ユーザー ライセンスが割り当てされています。 電話システムを含む少なくとも 1 つのライセンスを持つ組織、または電話システムが追加された組織には、無料で 25 の仮想ユーザー ライセンスを利用できます。 組織で 10 の電話システム ユーザー ライセンスを追加すると、もう 1 つの Microsoft 365 電話システム – 仮想ユーザー ライセンスが利用可能になります。

> [!NOTE]
> 電話システムは、Microsoft 365 および Office 365 E1 および E3 で利用できるアドオン ライセンスです。 電話システムは、Microsoft 365 E5、Office 365 E5、および Microsoft 365 Business Voice ライセンスの一部として含まれています。

利用可能な無料の Microsoft 365 電話システム – 仮想ユーザー ライセンスを使用して自動応答または通話キュー ノードを作成している場合でも、有料電話システム ライセンスをリソース アカウントで使用できます。 ほとんどの組織は、スケーリング計画に基づいて十分な仮想ユーザー ライセンスを持っています。 

### <a name="license-allocation-example"></a>ライセンス割り当ての例

Contoso, Inc. が電話システムを含む 600 ライセンスを購入しました (従業員ごとに 1 つ)。 Contoso には、最初の 25 ライセンスと 60 台の Microsoft 365 電話システム (仮想ユーザー ライセンス) が割り当て、合計で 85 ライセンスが割り当てされています。 組織には、電話番号を含む 90 の通話キューと自動応答があります。 すべての Microsoft 365 電話システム – 仮想ユーザー ライセンスを割り当て、通常価格の電話システム ライセンスを 5 つ取得する必要があります。

Contoso は、自動応答と通話キュー システムの再設計を検討する必要があります。 電話番号の使用数が少なく、電話番号が不要な入れ子ノードが多い場合は、実装が簡素化され、コストが削減されます。

## <a name="how-to-buy-microsoft-365-phone-system--virtual-user-licenses"></a>Microsoft 365 電話システムの購入方法 – 仮想ユーザー ライセンス

1. Microsoft 365 管理センターにサインインします。
2. 課金購入  >  **サービス**  >  **アドオンに移動する**
3. 最後までスクロールして **、Microsoft 365 電話システム – 仮想ユーザー ライセンスを探** します。 [今すぐ **購入] を選択します**。

> [!NOTE]
> コストが 0  **の場合でも** 、ライセンスを購入する必要があります。

## <a name="change-an-existing-resource-account-to-use-a-microsoft-365-phone-system--virtual-user-license"></a>Microsoft 365 Phone System – 仮想ユーザー ライセンスを使用するために既存のリソース アカウントを変更する

リソース アカウントのライセンスを電話システム ライセンスから Microsoft 365 電話システム – 仮想ユーザー ライセンスに切り替える場合:

1. 新しい Microsoft 365 電話システム – 仮想ユーザー ライセンスを取得します。
2. Microsoft 365 管理センターのリンクされた手順に従って、ユーザーを別の [サブスクリプションに移動します](/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription)。

> [!WARNING]
> 常に完全な電話システム ライセンスを削除し、Microsoft 365 電話システム – 同じライセンス アクティビティの仮想ユーザー ライセンスを割り当てる必要があります。 古いライセンスを削除し、アカウントの変更を保存し、新しいライセンスを追加して、アカウント設定を再び保存すると、リソース アカウントが期待した通り機能しなくなる可能性があります。 このような場合は、Microsoft 365 電話システム – 仮想ユーザー ライセンスの新しいリソース アカウントを作成し、壊れたリソース アカウントを削除することをお勧めします。 

## <a name="related-information"></a>関連情報

[自動応答および通話キュー サービスの更新](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521)

[Microsoft Teams のリソースのアカウントの管理](../manage-resource-accounts.md)