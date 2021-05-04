---
title: リソース アカウントMicrosoft 365 Business Voice設定する
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: 自動応答で使用するためにMicrosoft 365 Business Voiceリソース アカウントを設定する方法について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 76e91a650e9e72c21a39d292e32fe5ff8ecbf80b
ms.sourcegitcommit: 49cdcf344c63c805bcb6365804c6f5d1393e926a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2021
ms.locfileid: "52130438"
---
# <a name="step-4-set-up-a-business-voice-resource-account"></a><span data-ttu-id="dc9b2-103">手順 4: Business Voice リソース アカウントを設定する</span><span class="sxs-lookup"><span data-stu-id="dc9b2-103">Step 4: Set up a Business Voice resource account</span></span>

<span data-ttu-id="dc9b2-104">このMicrosoft Teams、自動応答キューまたは通話キューごとにリソース アカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="dc9b2-104">In Microsoft Teams, a resource account is required for each auto attendant or call queue.</span></span> <span data-ttu-id="dc9b2-105">リソース アカウントには、サービスの電話番号も割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="dc9b2-105">Resource accounts may also be assigned service telephone numbers.</span></span> <span data-ttu-id="dc9b2-106">次に、自動応答と通話キューに電話番号を割り当て、外部の発信者が自動応答または通話キュー Teamsに到達できるようにします。</span><span class="sxs-lookup"><span data-stu-id="dc9b2-106">This is how you assign phone numbers to auto attendants and call queues allowing callers from outside Teams to reach the auto attendant or call queue.</span></span>

## <a name="obtain-virtual-user-licenses"></a><span data-ttu-id="dc9b2-107">仮想ユーザー ライセンスを取得する</span><span class="sxs-lookup"><span data-stu-id="dc9b2-107">Obtain virtual user licenses</span></span>

<span data-ttu-id="dc9b2-108">リソース アカウントでは、自動応答と呼び出しキューを操作するためにライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="dc9b2-108">Resource accounts require a license in order to work with auto attendants and call queues.</span></span> <span data-ttu-id="dc9b2-109">無料の仮想ユーザー ライセンス *Microsoft 365 電話システム使用* できます。</span><span class="sxs-lookup"><span data-stu-id="dc9b2-109">You can use a free *Microsoft 365 Phone System - Virtual User* license.</span></span>

1. <span data-ttu-id="dc9b2-110">Microsoft 365 管理センターにサインインします。</span><span class="sxs-lookup"><span data-stu-id="dc9b2-110">Sign in to the Microsoft 365 admin center.</span></span>
2. <span data-ttu-id="dc9b2-111">[課金購入  >  **サービスの**  >  **アドオン] に移動すべての**  >  **アドオン製品を表示する**</span><span class="sxs-lookup"><span data-stu-id="dc9b2-111">Go to **Billing** > **Purchase services** > **Add-ons** > **See all Add-ons products**</span></span>
3. <span data-ttu-id="dc9b2-112">最後までスクロールして、仮想ユーザー ライセンスMicrosoft 365 電話システム **を見** つける。</span><span class="sxs-lookup"><span data-stu-id="dc9b2-112">Scroll to the end to find the **Microsoft 365 Phone System – Virtual User** license.</span></span> <span data-ttu-id="dc9b2-113">[詳細 **] を選択** し、[購入] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="dc9b2-113">Select **Details**, then **Buy**.</span></span>
4. <span data-ttu-id="dc9b2-114">[ライセンス購入] ページで、必要な仮想ユーザー ライセンスの数を選択します。</span><span class="sxs-lookup"><span data-stu-id="dc9b2-114">On the license purchase page, select the number of virtual user licenses you want.</span></span> <span data-ttu-id="dc9b2-115">セットアップする予定の自動応答キューと通話キューごとに 1 つの仮想ライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="dc9b2-115">You need one virtual license for each auto attendant and call queue you plan to set up.</span></span> <span data-ttu-id="dc9b2-116">少なくとも 5 つのライセンスを選択することをお勧めします。今後は、より多くのライセンスを購入することなく、より多くの自動応答と通話キューを簡単に設定できます。</span><span class="sxs-lookup"><span data-stu-id="dc9b2-116">We recommend selecting at least five licenses so you can easily set up more auto attendants and call queues in the future without having to purchase more licenses right away.</span></span>
5. <span data-ttu-id="dc9b2-117">[ライセンス **を持つすべてのユーザーに自動的に割り当てる] をオフにします**。</span><span class="sxs-lookup"><span data-stu-id="dc9b2-117">Uncheck **Automatically assign to all of your users with no licenses**.</span></span>
6. <span data-ttu-id="dc9b2-118">[今 **すぐチェックアウト] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="dc9b2-118">Select **Check out now**.</span></span>
7. <span data-ttu-id="dc9b2-119">注文を確認し、[次へ] **を選択** し、[注文 **を行う] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="dc9b2-119">Confirm your order, select **Next**, and then **Place order**.</span></span>

> [!NOTE]
> <span data-ttu-id="dc9b2-120">コストが 0 の  **場合でも、** ライセンスを購入する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc9b2-120">Keep in mind you must still  **Buy** the license even though it has a cost of zero.</span></span>

## <a name="create-a-resource-account"></a><span data-ttu-id="dc9b2-121">リソース アカウントを作成する</span><span class="sxs-lookup"><span data-stu-id="dc9b2-121">Create a resource account</span></span>

<span data-ttu-id="dc9b2-122">仮想ユーザー ライセンス - 仮想Microsoft 365 電話システム *を受け* 取った後、リソース アカウントを作成できます。</span><span class="sxs-lookup"><span data-stu-id="dc9b2-122">After you've received your *Microsoft 365 Phone System - Virtual User* license, you can create your resource account.</span></span>

![リソース アカウントのユーザー インターフェイスの追加のスクリーンショット](../media/resource-account-add.png)

1. <span data-ttu-id="dc9b2-124">管理センター Teams、組織全体の設定 **を** 展開し、[リソース アカウント]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="dc9b2-124">In the Teams admin center, expand **Org-wide settings**, and then click **Resource accounts**.</span></span>
2. <span data-ttu-id="dc9b2-125">**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="dc9b2-125">Select **Add**.</span></span>
3. <span data-ttu-id="dc9b2-126">[リソース アカウント **の追加] ウィンドウで** 、[表示名] **と**[ユーザー名] の順に **入力します**。</span><span class="sxs-lookup"><span data-stu-id="dc9b2-126">In the **Add resource account** pane, fill out **Display name**, and then **Username**.</span></span> <span data-ttu-id="dc9b2-127">リソース アカウントの目的を説明するために、"メイン ライン自動応答" などのわかりやすい表示名を選択します。</span><span class="sxs-lookup"><span data-stu-id="dc9b2-127">Choose a descriptive display name such as "Main line auto attendant" to describe the purpose of the resource account.</span></span>
4. <span data-ttu-id="dc9b2-128">[ **リソース アカウントの種類] で、[** 自動応答] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="dc9b2-128">In **Resource account type**, select **Auto attendant**.</span></span>
5. <span data-ttu-id="dc9b2-129">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="dc9b2-129">Select **Save**.</span></span>

![リソース アカウントの一覧のスクリーンショット](../media/resource-accounts-page.png)

## <a name="assign-a-license"></a><span data-ttu-id="dc9b2-131">ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="dc9b2-131">Assign a license</span></span>

<span data-ttu-id="dc9b2-132">リソース アカウントを作成したら、仮想ユーザー ライセンスまたは仮想ユーザー ライセンスMicrosoft 365 電話システム *割* り当てる *電話システムがあります。*</span><span class="sxs-lookup"><span data-stu-id="dc9b2-132">After you've created your resource account, you need to assign a *Microsoft 365 Phone System - Virtual User* license or *Phone System* license.</span></span>

![管理者センターでライセンスを割り当てるユーザー インターフェイスMicrosoft 365スクリーンショット](../media/resource-account-assign-virtual-user-license.png)

1. <span data-ttu-id="dc9b2-134">管理センター Microsoft 365、ユーザーのアクティブな **ユーザーに**  >  **移動します**。</span><span class="sxs-lookup"><span data-stu-id="dc9b2-134">In the Microsoft 365 admin center, go to **Users** > **Active users**.</span></span>
2. <span data-ttu-id="dc9b2-135">リソース アカウントを選択します。</span><span class="sxs-lookup"><span data-stu-id="dc9b2-135">Select your resource account.</span></span>
1. <span data-ttu-id="dc9b2-136">[ライセンスと **アプリ] タブの**[ライセンス **] の下で**、[Microsoft 365 電話システム **- 仮想ユーザー] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="dc9b2-136">On the **Licenses and Apps** tab, under **Licenses**, select **Microsoft 365 Phone System - Virtual User**.</span></span>
1. <span data-ttu-id="dc9b2-137">[変更 **の保存] を選択** し、[閉じる] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="dc9b2-137">Select **Save changes** and then **Close**.</span></span>

## <a name="assign-a-service-number"></a><span data-ttu-id="dc9b2-138">サービス番号を割り当てる</span><span class="sxs-lookup"><span data-stu-id="dc9b2-138">Assign a service number</span></span>

![サービス番号の割り当てユーザー インターフェイスのスクリーンショット](../media/resource-account-assign-phone-number.png)

1. <span data-ttu-id="dc9b2-140">管理センター Teams、組織全体の **設定に** 移動し、[リソース アカウント]**に移動します**。</span><span class="sxs-lookup"><span data-stu-id="dc9b2-140">In the Teams admin center, go to **Org-wide settings** and then **Resource accounts**.</span></span> 
1. <span data-ttu-id="dc9b2-141">作成したリソース アカウントを選択し、[割り当て/割り当て解除] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="dc9b2-141">Select the resource account you just created, and then click **Assign/unassign**.</span></span>
1. <span data-ttu-id="dc9b2-142">[ユーザー番号 **電話] ドロップダウンで、[** オンライン] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="dc9b2-142">In the **Phone number type** dropdown, choose **Online**.</span></span>
1. <span data-ttu-id="dc9b2-143">[割り **当て済み電話番号]** ボックスで、使用する番号を検索し、[追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="dc9b2-143">In the **Assigned phone number** box, search for the number you want to use and click **Add**.</span></span> <span data-ttu-id="dc9b2-144">必ず国コードを含める (たとえば **、+1** 250 555 0012)</span><span class="sxs-lookup"><span data-stu-id="dc9b2-144">Be sure to include the country code (for example, **+1** 250 555 0012)</span></span>
1. <span data-ttu-id="dc9b2-145">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc9b2-145">Click **Save**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="dc9b2-146">番号を追加する自動応答が既に選択されているので、[割り当て] で自動応答を選択する必要はない。</span><span class="sxs-lookup"><span data-stu-id="dc9b2-146">You don't need to select an auto attendant under **Assign to** because the auto attendant you want to add the number to is already selected.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="dc9b2-147">次の手順: ユーザーに電話番号を割り当てる</span><span class="sxs-lookup"><span data-stu-id="dc9b2-147">Next step: Assign phone numbers to your users</span></span>](set-up-assign-numbers.md)
