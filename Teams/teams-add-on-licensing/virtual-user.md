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
- admindeeplinkMAC
description: 組織内の自動応答と通話キューのリソース アカウントにMicrosoft Teams 電話リソース アカウント ライセンスを割り当てる方法について説明します。
ms.openlocfilehash: 348317ca659e03a9dacf8eaae603cff52a009912
ms.sourcegitcommit: 7a1fb6e15c21368afa34cd212865437781f721e2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67465985"
---
# <a name="microsoft-teams-phone-resource-account-licenses"></a>Microsoft Teams 電話 リソース アカウント ライセンス

Microsoft Teams では、すべての自動応答と通話キューに、関連付けられたリソース アカウントが必要です。 リソース アカウントに電話番号が割り当てられるかどうかに関係なく、システムによって正しく識別され、正しく機能するように、各リソース アカウントにMicrosoft Teams 電話 *リソース アカウント ライセンスを割り当てる* 必要があります。 Teams Phone を含むサブスクリプションを持つ組織には、追加コストなしで一定量の **Teams Phone リソース アカウント** ライセンスが自動的に割り当てられます。  そのリソース アカウントを使用してダイヤルアウトできるようにする場合を除き、Microsoft 通話プランは必要ありません。 詳細については、「 [Teams の自動応答と通話キューの計画](../plan-auto-attendant-call-queue.md#prerequisites)」を参照してください。

> [!NOTE]
> 以前は、 **Teams Phone リソース アカウント** ライセンス (仮想 **ユーザー** ライセンスと呼ばれていました) は、リソース アカウントに電話番号を割り当てるときにのみ必要でした。 これで、電話番号が割り当てられるかどうかに関係なく、すべてのリソース **アカウントに Teams Phone リソース アカウント** ライセンスを割り当てる必要があります。 また、**Teams 電話スタンダード** ライセンスをリソース アカウントに割り当てないでください。 現在、**Teams 電話スタンダード** ライセンスで構成されているリソース アカウントがある場合は、以下で説明するように **Teams Phone リソース アカウント** ライセンスに切り替える必要があります。
 

## <a name="resource-account-license-allocation"></a>リソース アカウントのライセンス割り当て

組織には、全体のサイズに基づいて **Teams Phone Resource Account** ライセンスが割り当てられている。 通話プランライセンスを持つ **Teams 電話スタンダード** や Teams Phone などの電話システム機能 **を備えた** サブスクリプションを持つすべての組織には、無償で利用できる 25 **個の Teams Phone リソース アカウント** ライセンスが割り当てられます。 

組織内の **通話プランを使用****する Teams 電話スタンダード** または Teams Phone の 10 個のユーザー ライセンスごとに、さらに 1 つの **Teams Phone リソース アカウント** ライセンスが使用できるようになります。  ほとんどの組織は、このスケーリング 計画に基づいて、十分な **Teams Phone リソース アカウント** ライセンスを所有します。 **Teams Phone リソース アカウント** のライセンスが必要な場合は、Microsoft アカウント担当者を通じて、標準割り当てを超える Teams **Phone リソース アカウント** ライセンスを購入できます。

### <a name="license-allocation-example"></a>ライセンス割り当ての例

Contoso, Inc. は、電話システムを含む 600 ライセンスを購入しました (従業員ごとに 1 つ)。 Contoso には、最初の 25 と 60 **個の Teams Phone リソース アカウント** ライセンスが割り当てられ、合計で 85 ライセンスが割り当てられている。 組織には、電話番号を持つ 90 の通話キューと自動応答があります。 **すべての Teams Phone リソース アカウント** ライセンスを割り当て、追加で 5 つの **Teams Phone リソース アカウント ライセンスを購入する** 必要があります。 

## <a name="how-to-obtain-microsoft-teams-phone-resource-account-licenses"></a>Microsoft Teams 電話 リソース アカウント ライセンスを取得する方法

1. Microsoft 365 管理センターにサインイン[します](https://go.microsoft.com/fwlink/p/?linkid=2024339)。
2. **課金** > [**購入サービス**](https://go.microsoft.com/fwlink/p/?linkid=868433) > **アドオンに移動します**。
3. スクロールして **、Microsoft Teams 電話リソース アカウント** ライセンスを見つけます。 [ **今すぐ購入]** を選択します。

   > [!NOTE]
   > 割り当て範囲内であっても、コストがゼロであってもライセンスを **購入** する必要があることに注意してください。

## <a name="change-an-existing-resource-account-to-use-a-microsoft-teams-phone-resource-account-license"></a>Microsoft Teams 電話 リソース アカウント ライセンスを使用するように既存のリソース アカウントを変更する

**Teams 電話スタンダード** ライセンスを使用している既存のリソース アカウントがある場合は、**Teams Phone リソース アカウント** ライセンスへの使用に切り替える必要があります。

1. 新しい **Teams Phone リソース アカウント** ライセンスを取得します。
2. Microsoft 365 管理センターのリンクされた手順に従って、[ユーザーを別のサブスクリプションに移動します](/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription)。

> [!WARNING]
> **常にTeams 電話スタンダード** ライセンスを削除し、同じライセンス アクティビティで **Teams Phone リソース アカウント** のライセンスを割り当てます。 古いライセンスを削除し、アカウントの変更を保存し、新しいライセンスを追加し、アカウント設定をもう一度保存すると、組織の自動応答や通話キューが機能しなくなったなど、リソース アカウントが期待どおりに機能しなくなる可能性があります。
>
> このような場合は、Teams Phone リソース アカウント ライセンスを使用して新しい **リソース アカウント** を作成し、壊れたリソース アカウントを削除することをお勧めします。

## <a name="related-information"></a>関連情報

[自動応答と通話キュー サービスの更新](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521)

[Microsoft Teams のリソースのアカウントの管理](../manage-resource-accounts.md)
