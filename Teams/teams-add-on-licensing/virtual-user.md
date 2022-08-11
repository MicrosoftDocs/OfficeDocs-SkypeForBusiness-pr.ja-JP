---
title: Microsoft Teams 電話 リソース アカウント ライセンス
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
description: 無料の Teams Phone リソース アカウント ライセンスまたは有料Teams 電話スタンダードユーザー ライセンスを組織内のリソース アカウントに割り当てる方法について説明します。
ms.openlocfilehash: f8aaf7480fc228fc78879ed5905aaaf7092777ab
ms.sourcegitcommit: 6e677c7d0dfe9e380d70adaca748eea88ca95705
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2022
ms.locfileid: "67298297"
---
# <a name="microsoft-teams-phone-resource-account-licenses"></a>Microsoft Teams 電話 リソース アカウント ライセンス

Teams 電話スタンダードまたは Teams Phone の通話プランライセンスユーザーを持つ組織は、リソース アカウントの無料 *ライセンスMicrosoft Teams 電話* または有料 *Teams 電話スタンダード* ユーザー ライセンスのいずれかをリソース アカウントに割り当てることができます。 Microsoft 通話プランは常に必要とは限りません (外部電話番号に通話を転送する場合の前提条件については、「 [Teams 自動応答と通話キューの計画](../plan-auto-attendant-call-queue.md#prerequisites) 」を参照)。

すべての自動応答と呼び出しキューには、関連付けられたリソース アカウントが必要です。 電話番号を必要とするリソース アカウントには、リソース アカウントに電話番号 *を適用する前に、無料のMicrosoft Teams 電話リソース アカウント* ライセンスまたは有料 *Teams 電話スタンダード* ユーザー ライセンスが必要です。

> [!TIP]
> 入れ子になった自動応答または電話番号が割り当てられていない通話キューで使用されるリソース アカウントには、ライセンスは必要ありません。

## <a name="resource-account-license-allocation"></a>リソース アカウントのライセンス割り当て

組織の全体的なサイズに応じて、*リソース アカウント ライセンスMicrosoft Teams 電話* 割り当てられます。 Teams 電話スタンダードと通話プランライセンスを持つ Teams Phone を含む Teams Phone システム機能を持つ少なくとも 1 つのライセンスを持つ組織には、25 個のリソース アカウント ライセンスが無償で使用できます。 組織内の通話プラン ユーザー ライセンスを使用して 10 Teams 電話スタンダードまたは Teams Phone を追加すると、*リソース アカウント ライセンスMicrosoft Teams 電話* もう 1 つ使用できるようになります。

> [!NOTE]
> Teams 電話スタンダードと通話プランを使用した Teams Phone は、すべての Microsoft 365 サブスクライバーが利用できるアドオン ライセンスです。 Teams 電話スタンダード ライセンスは、Microsoft 365 E5 プランの一部としても含まれています。

組織が自動応答ノードまたは通話キュー ノードの作成で無料 *のMicrosoft Teams 電話リソース アカウント* ライセンスを使用している場合でも、有料 *のTeams 電話スタンダード* ライセンスをリソース アカウントで使用できます。 ほとんどの組織は、スケーリング計画に基づいて十分なリソース アカウント ライセンスを持っています。

### <a name="license-allocation-example"></a>ライセンス割り当ての例

Contoso, Inc. は、電話システムを含む 600 ライセンスを購入しました (従業員ごとに 1 つ)。 Contoso には、最初の 25 と 60 *Microsoft Teams 電話リソース アカウント* ライセンスが割り当てられ、合計で 85 が割り当てられている。 組織には、電話番号を持つ 90 の通話キューと自動応答があります。 すべての *Microsoft Teams 電話リソース アカウント* ライセンスを割り当て、通常価格の 5 つの *Teams 電話スタンダード ライセンスを* 取得する必要があります。

Contoso は、自動応答と呼び出しキュー システムの再設計を検討する必要があります。 電話番号が少なく、電話番号を必要としない入れ子になったノードが多い場合は、実装が簡略化され、コストが削減されます。

## <a name="how-to-buy-microsoft-teams-phone-resource-account-licenses"></a>リソース アカウント ライセンスMicrosoft Teams 電話購入する方法

1. Microsoft 365 管理センターにサインインします。
2. **課金** > **購入サービス** > **アドオンに移動します**。
3. スクロールして **、Microsoft Teams 電話リソース アカウント** ライセンスを見つけます。 [ **今すぐ購入]** を選択します。

   > [!NOTE]
   > ライセンスのコストが 0 であっても、ライセンスを **購入** する必要があることに注意してください。

## <a name="change-an-existing-resource-account-to-use-a-microsoft-teams-phone-resource-account-license"></a>Microsoft Teams 電話 リソース アカウント ライセンスを使用するように既存のリソース アカウントを変更する

リソース アカウントのライセンスを *Teams 電話スタンダード* ライセンスから *Microsoft Teams 電話 リソース アカウント* ライセンスに切り替える場合:

1. 新しい *Microsoft Teams 電話リソース アカウント ライセンスを取得します*。
2. Microsoft 365 管理センターのリンクされた手順に従って、[ユーザーを別のサブスクリプションに移動します](/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription)。

> [!WARNING]
> 常に完全な *Teams 電話スタンダード* ライセンスを削除し、Microsoft Teams 電話 *リソース アカウント* ライセンスを同じライセンス アクティビティに割り当てます。 古いライセンスを削除し、アカウントの変更を保存し、新しいライセンスを追加して、アカウント設定をもう一度保存すると、リソース アカウントが期待どおりに機能しなくなる可能性があります。 このような場合は、Microsoft Teams 電話 リソース アカウント ライセンスの新しいリソース アカウントを作成し、破損した *リソース アカウント* を削除することをお勧めします。

## <a name="related-information"></a>関連情報

[自動応答と通話キュー サービスの更新](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521)

[Microsoft Teams のリソースのアカウントの管理](../manage-resource-accounts.md)
