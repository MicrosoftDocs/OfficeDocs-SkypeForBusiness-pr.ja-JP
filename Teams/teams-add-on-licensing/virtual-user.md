---
title: Microsoft 365 電話システム–仮想ユーザーライセンス
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
description: 組織内のリソースアカウントに無料の電話システム (仮想ユーザーライセンスまたは有料電話システムユーザーライセンス) を割り当てる方法について説明します。
ms.openlocfilehash: cd70b4a1d24bf762c5aa1508d29a9ce343cf4b76
ms.sourcegitcommit: 09ff11f8e4f6a93cedc34a5d732a133163df79a0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "44042414"
---
# <a name="microsoft-365-phone-system--virtual-user-license"></a><span data-ttu-id="ef34f-103">Microsoft 365 電話システム–仮想ユーザーライセンス</span><span class="sxs-lookup"><span data-stu-id="ef34f-103">Microsoft 365 Phone System – Virtual User license</span></span>

<span data-ttu-id="ef34f-104">電話システムライセンスを持つ組織では、無料の Microsoft 365 電話システム–仮想ユーザーライセンス、または有料電話システムユーザーライセンスをリソースアカウントに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="ef34f-104">Organizations with Phone System licensed users can assign either a free Microsoft 365 Phone System – Virtual User license or a paid Phone System user license to resource accounts.</span></span> <span data-ttu-id="ef34f-105">通話プランは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="ef34f-105">A Calling Plan isn't required.</span></span> <span data-ttu-id="ef34f-106">すべての自動応答または通話キューには、関連するリソースアカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="ef34f-106">All auto attendants or call queues require an associated resource account.</span></span> <span data-ttu-id="ef34f-107">電話番号が必要なリソースアカウントには、無料の Microsoft 365 電話システム–仮想ユーザーライセンスまたは有料電話システムユーザーライセンスが必要です。その前に電話番号をリソースアカウントに適用することができます。</span><span class="sxs-lookup"><span data-stu-id="ef34f-107">Resource accounts that require a phone number need a free Microsoft 365 Phone System – Virtual User license or a paid Phone System user license before a phone number can be applied to the resource account.</span></span>

> [!TIP]
> <span data-ttu-id="ef34f-108">入れ子になった自動応答または電話番号が割り当てられていない通話キューと共に使用されるリソースアカウントには、ライセンスは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="ef34f-108">No license is needed for resource accounts that will be used with nested auto attendants or call queues that don't have a phone number assigned.</span></span> <span data-ttu-id="ef34f-109">リファレンスについては、次の図を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ef34f-109">See the following diagram for reference:</span></span> 

![仮想ユーザーライセンス](../media/resource-account.png)

## <a name="virtual-user-license-allocation"></a><span data-ttu-id="ef34f-111">仮想ユーザーライセンスの割り当て</span><span class="sxs-lookup"><span data-stu-id="ef34f-111">Virtual User license allocation</span></span>

<span data-ttu-id="ef34f-112">組織では、全体のサイズに応じて、Microsoft 365 電話システム–仮想ユーザーライセンスが割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="ef34f-112">Your organization is allotted Microsoft 365 Phone System – Virtual User licenses depending on its overall size.</span></span> <span data-ttu-id="ef34f-113">電話システムや電話システムを含む、少なくとも1つのライセンスを持つ組織には、無料で25の仮想ユーザーライセンスが用意されています。</span><span class="sxs-lookup"><span data-stu-id="ef34f-113">Any organization that has at least one license including Phone System or has Phone System added has 25 Virtual User licenses available at no cost.</span></span> <span data-ttu-id="ef34f-114">組織に10個の電話システムユーザーライセンスを追加すると、Microsoft 365 電話システムがさらに1つ増えます。仮想ユーザーライセンスが利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="ef34f-114">When you add 10 Phone System user licenses in your organization, one more Microsoft 365 Phone System – Virtual User license becomes available.</span></span>

> [!NOTE]
> <span data-ttu-id="ef34f-115">電話システムは、Microsoft 365 および Office 365 E1 および E3 で利用可能なアドオンライセンスです。</span><span class="sxs-lookup"><span data-stu-id="ef34f-115">Phone System is an add-on license available with Microsoft 365 and Office 365 E1 and E3.</span></span> <span data-ttu-id="ef34f-116">電話システムは、Microsoft 365 E5、Office 365 E5、および Microsoft 365 ビジネス Voip ライセンスの一部としても含まれています。</span><span class="sxs-lookup"><span data-stu-id="ef34f-116">Phone System is also included as part of Microsoft 365 E5, Office 365 E5, and Microsoft 365 Business Voice licenses.</span></span>

<span data-ttu-id="ef34f-117">組織で利用可能な無料の Microsoft 365 電話システム–自動応答または通話キューノードを作成するための仮想ユーザーライセンスを使用している場合は、リソースアカウントを使って、有料電話システムのライセンスを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="ef34f-117">If your organization uses up the available free Microsoft 365 Phone System – Virtual User licenses in creating auto attendant or call queue nodes, you can still use the paid Phone system licenses with a resource account.</span></span> <span data-ttu-id="ef34f-118">ほとんどの組織には、スケーリングプランに基づいて十分な仮想ユーザーライセンスがあります。</span><span class="sxs-lookup"><span data-stu-id="ef34f-118">Most organizations will have enough Virtual User licenses based on the scaling plan.</span></span> 

### <a name="license-allocation-example"></a><span data-ttu-id="ef34f-119">ライセンスの割り当ての例</span><span class="sxs-lookup"><span data-stu-id="ef34f-119">License allocation example</span></span>

<span data-ttu-id="ef34f-120">Contoso、Inc. は、電話システム (各従業員に1つ) が含まれている600ライセンスを購入しました。</span><span class="sxs-lookup"><span data-stu-id="ef34f-120">Contoso, Inc. purchased 600 licenses that included Phone System (one for each employee).</span></span> <span data-ttu-id="ef34f-121">Contoso には、最初の 25 plus 60 Microsoft 365 電話システム–仮想ユーザーライセンス、85の合計が割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="ef34f-121">Contoso is allotted an initial 25 plus 60 Microsoft 365 Phone System – Virtual User licenses, 85 in total.</span></span> <span data-ttu-id="ef34f-122">組織には、電話番号を持つ90の通話キューと自動応答があります。</span><span class="sxs-lookup"><span data-stu-id="ef34f-122">Their organization has 90 call queues and auto attendants that have phone numbers.</span></span> <span data-ttu-id="ef34f-123">Microsoft 365 のすべての電話システムを割り当てる必要があります。仮想ユーザーライセンスを取得し、5つの標準価格の電話システムライセンスを取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef34f-123">They need to assign all the Microsoft 365 Phone System – Virtual User licenses and obtain five regular-priced Phone System licenses.</span></span> 

<span data-ttu-id="ef34f-124">Contoso は、自動応答と通話キューシステムを再設計することを検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef34f-124">Contoso should consider redesigning the auto attendant and call queue system.</span></span> <span data-ttu-id="ef34f-125">使用する電話番号の数が少なく、電話番号を必要としない下位ノードを使用している場合、実装が簡素化され、コストが削減されます。</span><span class="sxs-lookup"><span data-stu-id="ef34f-125">If they use fewer phone numbers and more nested nodes that don't need a phone number, they simplify the implementation and reduce costs.</span></span> 

## <a name="how-to-buy-microsoft-365-phone-system--virtual-user-licenses"></a><span data-ttu-id="ef34f-126">Microsoft 365 電話システムの購入方法–仮想ユーザーライセンス</span><span class="sxs-lookup"><span data-stu-id="ef34f-126">How to buy Microsoft 365 Phone System – Virtual User licenses</span></span> 

1. <span data-ttu-id="ef34f-127">Microsoft 365 管理センターにサインインします。</span><span class="sxs-lookup"><span data-stu-id="ef34f-127">Sign in to the Microsoft 365 admin center.</span></span>
2. <span data-ttu-id="ef34f-128">**請求** > **書サービス** > **の**アドオンに移動する</span><span class="sxs-lookup"><span data-stu-id="ef34f-128">Go to **Billing** > **Purchase services** > **Add-ons**</span></span>
3. <span data-ttu-id="ef34f-129">最後までスクロールして、 **Microsoft 365 電話システム–仮想ユーザー**ライセンスを探します。</span><span class="sxs-lookup"><span data-stu-id="ef34f-129">Scroll to the end to find the **Microsoft 365 Phone System – Virtual User** license.</span></span> <span data-ttu-id="ef34f-130">[**今すぐ購入**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ef34f-130">Select **Buy now**.</span></span>

> [!NOTE]
> <span data-ttu-id="ef34f-131">ただし、料金がゼロの場合でも、ライセンスを**購入**する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef34f-131">Keep in mind you must still  **Buy** the license even though it has a cost of zero.</span></span> 

## <a name="change-an-existing-resource-account-to-use-a-microsoft-365-phone-system--virtual-user-license"></a><span data-ttu-id="ef34f-132">Microsoft 365 電話システムを使用するように既存のリソースアカウントを変更する–仮想ユーザーライセンス</span><span class="sxs-lookup"><span data-stu-id="ef34f-132">Change an existing resource account to use a Microsoft 365 Phone System – Virtual User license</span></span>

<span data-ttu-id="ef34f-133">リソースアカウントのライセンスを電話システムライセンスから Microsoft 365 電話システムに切り替える場合は、仮想ユーザーライセンス:</span><span class="sxs-lookup"><span data-stu-id="ef34f-133">If you decide to switch the license on your resource account from a Phone System license to a Microsoft 365 Phone System – Virtual User license:</span></span> 

1. <span data-ttu-id="ef34f-134">新しい Microsoft 365 電話システム–仮想ユーザーライセンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="ef34f-134">Get the new Microsoft 365 Phone System – Virtual User license.</span></span> 
2. <span data-ttu-id="ef34f-135">Microsoft 365 管理センターのリンクされた手順に従って、[ユーザーを別のサブスクリプションに移動](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#move-users-to-a-different-subscription)します。</span><span class="sxs-lookup"><span data-stu-id="ef34f-135">Follow the linked steps in the Microsoft 365 Admin center to [Move users to a different subscription](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#move-users-to-a-different-subscription).</span></span> 

> [!WARNING]
> <span data-ttu-id="ef34f-136">常に完全な電話システムのライセンスを削除し、Microsoft 365 電話システム–仮想ユーザーライセンスを同じライセンスアクティビティに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="ef34f-136">Always remove a full Phone System License and assign the Microsoft 365 Phone System – Virtual User license in the same license activity.</span></span> <span data-ttu-id="ef34f-137">古いライセンスを削除した場合は、アカウントの変更を保存し、新しいライセンスを追加してから、アカウント設定をもう一度保存すると、リソースアカウントが予期したとおりに機能しなくなることがあります。</span><span class="sxs-lookup"><span data-stu-id="ef34f-137">If you remove the old license, save the account changes, add the new license, and then save the account settings again, the resource account may no longer function as expected.</span></span> <span data-ttu-id="ef34f-138">この問題が発生した場合は、Microsoft 365 電話システムの新しいリソースアカウントを作成することをお勧めします。仮想ユーザーライセンスは、破損したリソースアカウントを削除することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ef34f-138">If this happens, we recommend you create a new resource account for the Microsoft 365 Phone System – Virtual User license and remove the broken resource account.</span></span> 

## <a name="related-information"></a><span data-ttu-id="ef34f-139">関連情報</span><span class="sxs-lookup"><span data-stu-id="ef34f-139">Related information</span></span>

[<span data-ttu-id="ef34f-140">自動応答と通話キューサービスの更新</span><span class="sxs-lookup"><span data-stu-id="ef34f-140">Auto Attendant and Call Queues Service Update</span></span>](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521)

[<span data-ttu-id="ef34f-141">Microsoft Teams のリソースのアカウントの管理</span><span class="sxs-lookup"><span data-stu-id="ef34f-141">Manage resource accounts in Microsoft Teams</span></span>](../manage-resource-accounts.md)
