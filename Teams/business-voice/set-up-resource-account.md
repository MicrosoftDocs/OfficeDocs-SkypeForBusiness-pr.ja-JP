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
description: 自動応答で使用Microsoft 365 Business Voiceリソース アカウントを設定する方法について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 618f26394f2b4acc44d56b814bd31c20ffe1a370
ms.sourcegitcommit: 32e3bb588abcbeded2d885483384c06706b280eb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2021
ms.locfileid: "52282779"
---
# <a name="step-4-set-up-a-business-voice-resource-account"></a><span data-ttu-id="c8377-103">手順 4: Business Voice リソース アカウントを設定する</span><span class="sxs-lookup"><span data-stu-id="c8377-103">Step 4: Set up a Business Voice resource account</span></span>

<span data-ttu-id="c8377-104">リソース アカウントは、特定のユーザーには割り当てられていない。</span><span class="sxs-lookup"><span data-stu-id="c8377-104">Resource accounts aren't assigned to any specific user.</span></span> <span data-ttu-id="c8377-105">代わりに、無料の仮想ユーザー ライセンスを使用するリソース アカウントは、仮想マシンのデバイスとサービスMicrosoft 365。</span><span class="sxs-lookup"><span data-stu-id="c8377-105">Instead, resource accounts, which use a free virtual user license, are used by devices and services in Microsoft 365.</span></span> <span data-ttu-id="c8377-106">このMicrosoft Teams、リソース アカウントには電話番号が割り当てられた後、自動応答と通話キューに関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="c8377-106">In Microsoft Teams, resource accounts are assigned phone numbers and are then associated with auto attendants and call queues.</span></span>

<span data-ttu-id="c8377-107">リソース アカウントを自動応答と通話キューに関連付け、1 つ以上の有料電話番号または無料電話番号を追加できます。</span><span class="sxs-lookup"><span data-stu-id="c8377-107">By associating resource accounts to auto attendants and call queues, you can add one or more toll or toll-free phone numbers to them.</span></span> <span data-ttu-id="c8377-108">たとえば、あるリソース アカウントを有料電話番号に関連付け、ローカル発信者の自動応答に関連付けできます。</span><span class="sxs-lookup"><span data-stu-id="c8377-108">For example, you could associate one resource account with a toll number to an auto attendant for local callers.</span></span> <span data-ttu-id="c8377-109">遠距離通話の場合は、別のリソース アカウントを無料電話番号と同じ自動応答に関連付けます。</span><span class="sxs-lookup"><span data-stu-id="c8377-109">For long distance calls, you could associate another resource account with a toll-free number to the same auto attendant.</span></span>

<span data-ttu-id="c8377-110">この記事のセクションでは、リソース アカウントを設定し、そのアカウントに電話番号を割り当てる方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c8377-110">The sections in this article show you how to set up a resource account and then assign a phone number to it.</span></span> <span data-ttu-id="c8377-111">後で、リソース アカウントを自動応答に関連付ける予定です。</span><span class="sxs-lookup"><span data-stu-id="c8377-111">Later on, you'll associate the resource account with an auto attendant.</span></span>

## <a name="obtain-virtual-user-licenses"></a><span data-ttu-id="c8377-112">仮想ユーザー ライセンスの取得</span><span class="sxs-lookup"><span data-stu-id="c8377-112">Obtain virtual user licenses</span></span>

<span data-ttu-id="c8377-113">自動応答と通話キューを操作するには、リソース アカウントにライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="c8377-113">Resource accounts require a license in order to work with auto attendants and call queues.</span></span> <span data-ttu-id="c8377-114">無料の仮想マシン Microsoft 365 電話システム *ライセンスを使用* できます。</span><span class="sxs-lookup"><span data-stu-id="c8377-114">You can use a free *Microsoft 365 Phone System - Virtual User* license.</span></span>

> [!NOTE]
> <span data-ttu-id="c8377-115">Business Voice の試用期間にサインアップした場合にのみ、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8377-115">You should only need to perform the following steps if you've signed up for a Business Voice trial period.</span></span> <span data-ttu-id="c8377-116">Business Voice ライセンスを購入した場合は、仮想ライセンスが既にアカウントに適用されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8377-116">If you purchased Business Voice licenses, virtual licenses should already be applied to your account.</span></span> 
>
> <span data-ttu-id="c8377-117">仮想ライセンスが既にある場合は、グローバル管理者アクセス許可Microsoft 365アカウントを使用してログインします。</span><span class="sxs-lookup"><span data-stu-id="c8377-117">To see if you already have virtual licenses, log into Microsoft 365 using an account with Global admin permissions.</span></span> <span data-ttu-id="c8377-118">次に、[製品の課金> [に移動します](https://admin.microsoft.com/Adminportal/Home#/subscriptions)。</span><span class="sxs-lookup"><span data-stu-id="c8377-118">Then go to Billing > [Your products](https://admin.microsoft.com/Adminportal/Home#/subscriptions).</span></span> <span data-ttu-id="c8377-119">仮想ライセンスがある場合は、[仮想ユーザー] **Microsoft 365 電話システム として表示されます**。</span><span class="sxs-lookup"><span data-stu-id="c8377-119">If you have virtual licenses, they'll appear as **Microsoft 365 Phone System - Virtual User**.</span></span>

1. <span data-ttu-id="c8377-120">Microsoft 365 管理センターを開き、グローバル管理者のユーザー (通常は、このアカウントを使用してアカウントにサインアップしたアカウント) でログインMicrosoft 365。</span><span class="sxs-lookup"><span data-stu-id="c8377-120">Open the Microsoft 365 admin center and log in with a user that is a Global admin (this is usually the account you used to sign up for Microsoft 365).</span></span>
2. <span data-ttu-id="c8377-121">左側のナビゲーション ウィンドウで、[課金 <a href="https://admin.microsoft.com/Adminportal/Home#/catalog" target="_blank">  >  購入サービス</a>アドオン] に移動します。すべてのアドオン  >    >  **製品を表示します**。</span><span class="sxs-lookup"><span data-stu-id="c8377-121">In the left navigation pane, go to <a href="https://admin.microsoft.com/Adminportal/Home#/catalog" target="_blank">**Billing** > **Purchase services**</a> > **Add-ons** > **See all Add-ons products**.</span></span>
3. <span data-ttu-id="c8377-122">最後までスクロールして、仮想ユーザー ライセンス **Microsoft 365 電話システムを見** つける。</span><span class="sxs-lookup"><span data-stu-id="c8377-122">Scroll to the end to find the **Microsoft 365 Phone System – Virtual User** license.</span></span> <span data-ttu-id="c8377-123">[詳細 **] を選択** し、[購入] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c8377-123">Select **Details**, then **Buy**.</span></span>
4. <span data-ttu-id="c8377-124">ライセンス購入ページで、必要な仮想ユーザー ライセンスの数を選択します。</span><span class="sxs-lookup"><span data-stu-id="c8377-124">On the license purchase page, select the number of virtual user licenses you want.</span></span> <span data-ttu-id="c8377-125">設定する予定の自動応答と通話キューごとに 1 つの仮想ライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="c8377-125">You need one virtual license for each auto attendant and call queue you plan to set up.</span></span> <span data-ttu-id="c8377-126">少なくとも 5 つのライセンスを選択することをお勧めします。今後、より多くの自動応答と通話キューを簡単にセットアップできます。ライセンスを今すぐ追加購入する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c8377-126">We recommend selecting at least five licenses so you can easily set up more auto attendants and call queues in the future without having to purchase more licenses right away.</span></span>
5. <span data-ttu-id="c8377-127">[ライセンス **がないすべてのユーザーに自動的に割り当てる] をオフにします**。</span><span class="sxs-lookup"><span data-stu-id="c8377-127">Uncheck **Automatically assign to all of your users with no licenses**.</span></span>
6. <span data-ttu-id="c8377-128">[今 **すぐチェックアウト] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c8377-128">Select **Check out now**.</span></span>
7. <span data-ttu-id="c8377-129">ご注文を確認し、[次へ] **を選択** し、[注文] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c8377-129">Confirm your order, select **Next**, and then **Place order**.</span></span>

> [!NOTE]
> <span data-ttu-id="c8377-130">コストが 0 の  **場合でも、** ライセンスを購入する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8377-130">Keep in mind you must still  **Buy** the license even though it has a cost of zero.</span></span>

## <a name="create-a-resource-account"></a><span data-ttu-id="c8377-131">リソース アカウントを作成する</span><span class="sxs-lookup"><span data-stu-id="c8377-131">Create a resource account</span></span>

<span data-ttu-id="c8377-132">仮想ユーザー - 仮想Microsoft 365 電話システムライセンスを受 *け* 取った後、リソース アカウントを作成できます。</span><span class="sxs-lookup"><span data-stu-id="c8377-132">After you've received your *Microsoft 365 Phone System - Virtual User* license, you can create your resource account.</span></span>

![リソース アカウントのユーザー インターフェイスの追加のスクリーンショット](../media/resource-account-add.png)

1. <span data-ttu-id="c8377-134">Microsoft Teams 管理センターを開き、グローバル管理者であるユーザー (通常は、管理者のサインアップに使用したアカウント) でログインMicrosoft 365。</span><span class="sxs-lookup"><span data-stu-id="c8377-134">Open the Microsoft Teams admin center and log in with a user that is a Global admin (this is usually the account you used to sign up for Microsoft 365).</span></span>
2. <span data-ttu-id="c8377-135">左側のナビゲーション ウィンドウで、[組織全体の設定] <a href="https://admin.teams.microsoft.com/company-wide-settings/resource-accounts" target="_blank"> **[リソース アカウント]**  >  **に移動します**</a>。</span><span class="sxs-lookup"><span data-stu-id="c8377-135">In the left navigation pane, go to <a href="https://admin.teams.microsoft.com/company-wide-settings/resource-accounts" target="_blank">**Org-wide settings** > **Resource accounts**</a>.</span></span>
3. <span data-ttu-id="c8377-136">**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c8377-136">Select **Add**.</span></span>
4. <span data-ttu-id="c8377-137">[リソース **アカウントの追加] ウィンドウ** で、[表示名] **に入力** し、[ユーザー名] を **入力します**。</span><span class="sxs-lookup"><span data-stu-id="c8377-137">In the **Add resource account** pane, fill out **Display name**, and then **Username**.</span></span> <span data-ttu-id="c8377-138">リソース アカウントの目的を説明するわかりやすい表示名 ("メイン ライン自動応答" など) を選択します。</span><span class="sxs-lookup"><span data-stu-id="c8377-138">Choose a descriptive display name such as "Main line auto attendant" to describe the purpose of the resource account.</span></span>
5. <span data-ttu-id="c8377-139">[ **リソース アカウントの種類] で、[** 自動応答] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c8377-139">In **Resource account type**, select **Auto attendant**.</span></span>
6. <span data-ttu-id="c8377-140">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c8377-140">Select **Save**.</span></span>

![リソース アカウントの一覧のスクリーンショット](../media/resource-accounts-auto-attendant-only-page.png)

## <a name="assign-a-license"></a><span data-ttu-id="c8377-142">ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="c8377-142">Assign a license</span></span>

<span data-ttu-id="c8377-143">リソース アカウントを作成したら、仮想ユーザー ライセンスまたは仮想ユーザー ライセンスMicrosoft 365 電話システム *割* り当てる *電話システム* があります。</span><span class="sxs-lookup"><span data-stu-id="c8377-143">After you've created your resource account, you need to assign a *Microsoft 365 Phone System - Virtual User* license or *Phone System* license.</span></span>

![管理センターでのライセンスの割り当てユーザー インターフェイスMicrosoft 365スクリーンショット](../media/resource-account-assign-virtual-user-license.png)

1. <span data-ttu-id="c8377-145">Microsoft 365 管理センターを開き、グローバル管理者のユーザー (通常は、このアカウントを使用してアカウントにサインアップしたアカウント) でログインMicrosoft 365。</span><span class="sxs-lookup"><span data-stu-id="c8377-145">Open the Microsoft 365 admin center and log in with a user that is a Global admin (this is usually the account you used to sign up for Microsoft 365).</span></span>
1. <span data-ttu-id="c8377-146">左側のナビゲーション ウィンドウで、[ユーザーアクティブ ユーザー]<a href="https://admin.microsoft.com/Adminportal/Home#/users" target="_blank">  >  **に移動します**</a>。</span><span class="sxs-lookup"><span data-stu-id="c8377-146">In the left navigation pane, go to <a href="https://admin.microsoft.com/Adminportal/Home#/users" target="_blank">**Users** > **Active users**</a>.</span></span>
1. <span data-ttu-id="c8377-147">リソース アカウントを選択します。</span><span class="sxs-lookup"><span data-stu-id="c8377-147">Select your resource account.</span></span>
1. <span data-ttu-id="c8377-148">[ライセンスと **アプリ] タブの**[ライセンス]**で**、[仮想Microsoft 365 電話システム **- 仮想ユーザー] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c8377-148">On the **Licenses and Apps** tab, under **Licenses**, select **Microsoft 365 Phone System - Virtual User**.</span></span>
1. <span data-ttu-id="c8377-149">[変更の **保存] を選択し** 、[閉じる] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c8377-149">Select **Save changes** and then **Close**.</span></span>

## <a name="assign-a-service-number"></a><span data-ttu-id="c8377-150">サービス番号を割り当てる</span><span class="sxs-lookup"><span data-stu-id="c8377-150">Assign a service number</span></span>

![サービス番号の割り当てユーザー インターフェイスのスクリーンショット](../media/resource-account-assign-phone-number.png)

1. <span data-ttu-id="c8377-152">Microsoft Teams 管理センターを開き、グローバル管理者であるユーザー (通常は、管理者のサインアップに使用したアカウント) でログインMicrosoft 365。</span><span class="sxs-lookup"><span data-stu-id="c8377-152">Open the Microsoft Teams admin center and log in with a user that is a Global admin (this is usually the account you used to sign up for Microsoft 365).</span></span>
1. <span data-ttu-id="c8377-153">左側のナビゲーション ウィンドウで、[組織全体の設定] <a href="https://admin.teams.microsoft.com/company-wide-settings/resource-accounts" target="_blank"> **[リソース アカウント]**  >  **に移動します**</a>。</span><span class="sxs-lookup"><span data-stu-id="c8377-153">In the left navigation pane, go to <a href="https://admin.teams.microsoft.com/company-wide-settings/resource-accounts" target="_blank">**Org-wide settings** > **Resource accounts**</a>.</span></span>
1. <span data-ttu-id="c8377-154">作成したリソース アカウントを選択し、[割り当て/割り当て解除] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="c8377-154">Select the resource account you just created, and then click **Assign/unassign**.</span></span>
1. <span data-ttu-id="c8377-155">[電話番号の **電話ボックスで、[オンライン**] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="c8377-155">In the **Phone number type** dropdown, choose **Online**.</span></span>
1. <span data-ttu-id="c8377-156">[割 **り当てられた電話番号]** ボックスで、使用する番号を検索し、[追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="c8377-156">In the **Assigned phone number** box, search for the number you want to use and click **Add**.</span></span> <span data-ttu-id="c8377-157">国コードを必ず含める (例: **+1** 250 555 0012)</span><span class="sxs-lookup"><span data-stu-id="c8377-157">Be sure to include the country code (for example, **+1** 250 555 0012)</span></span>
1. <span data-ttu-id="c8377-158">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8377-158">Click **Save**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="c8377-159">次の手順: ユーザーに電話番号を割り当てる</span><span class="sxs-lookup"><span data-stu-id="c8377-159">Next step: Assign phone numbers to your users</span></span>](set-up-assign-numbers.md)
