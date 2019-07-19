---
title: ユーザーの電話番号を割り当て、変更、または削除する
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 91089761-cb87-4119-885b-3713840dd9f7
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Strat_SB_PSTN
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: 組織外の企業やクライアントが電話をかけられるように、チームユーザーの勤務先電話番号を割り当て、変更、または削除する方法について説明します。
ms.openlocfilehash: ccc8e723b1f4915781c47d416fa05d4cfb9c871d
ms.sourcegitcommit: 4c041e8a7c39bd6517605ed7fc9aab18cf466596
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/18/2019
ms.locfileid: "35792931"
---
# <a name="assign-change-or-remove-a-phone-number-for-a-user"></a><span data-ttu-id="2e7f2-103">ユーザーの電話番号を割り当て、変更、または削除する</span><span class="sxs-lookup"><span data-stu-id="2e7f2-103">Assign, change, or remove a phone number for a user</span></span>

<span data-ttu-id="2e7f2-104">通話プランを設定すると、ユーザーに電話番号が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="2e7f2-104">When you set up Calling Plans, you assign phone numbers to your users.</span></span> <span data-ttu-id="2e7f2-105">Microsoft Teams では、ユーザーが [**通話**] をクリックすると、割り当てた電話番号が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="2e7f2-105">In Microsoft Teams, the phone number you assign is listed when a user clicks **Calls**.</span></span>

![Teams に表示されるユーザーの電話番号。](media/teams-phone-number.png)

<span data-ttu-id="2e7f2-107">ユーザーが電話を発信および受信できるようにセットアップする場合は、最初に Microsoft Teams 管理センターを使用し、電話番号を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e7f2-107">When you're setting up users so they can make and receive phone calls, you must first use the Microsoft Teams admin center and assign a phone number.</span></span> <span data-ttu-id="2e7f2-108">必要に応じて、電話番号を変更または削除できます。</span><span class="sxs-lookup"><span data-stu-id="2e7f2-108">You can change or remove the phone number if you need to.</span></span>
  
<span data-ttu-id="2e7f2-109">Teams で通話プランを取得する方法とその費用については、「 [teams アドオンライセンス](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2e7f2-109">To learn how to get Calling Plans in Teams and how much they cost, see [Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="2e7f2-110">ユーザーにライセンスが割り当てられているかどうかを確認する1つの方法は、Microsoft Teams 管理センター >**ユーザー**にアクセスすることです。</span><span class="sxs-lookup"><span data-stu-id="2e7f2-110">One way to see whether a user has a license assigned is by going to the Microsoft Teams admin center > **Users**.</span></span> <span data-ttu-id="2e7f2-111">ライセンスが割り当てられている場合は、ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="2e7f2-111">If a license is assigned, it will be indicated on the page.</span></span>  <span data-ttu-id="2e7f2-112">Microsoft 365 管理センターを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="2e7f2-112">You can also use the Microsoft 365 admin center.</span></span>
  
## <a name="assign-a-phone-number-to-a-user"></a><span data-ttu-id="2e7f2-113">電話番号をユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="2e7f2-113">Assign a phone number to a user</span></span>
 
<span data-ttu-id="2e7f2-114">![Microsoft teams](media/teams-logo-30x30.png) **管理センターを使用し**た microsoft teams ロゴを示すアイコン</span><span class="sxs-lookup"><span data-stu-id="2e7f2-114">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>
    
1. <span data-ttu-id="2e7f2-115">左側のナビゲーションで、[ \*\*\*\* > **電話番号**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2e7f2-115">In the left navigation, click **Voice** > **Phone numbers**.</span></span>
2. <span data-ttu-id="2e7f2-116">[**電話番号**] ページで、リスト内の未使用の番号を選択し、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2e7f2-116">On the **Phone numbers** page, select an unassigned number in the list, and then click **Edit**.</span></span>  
3. <span data-ttu-id="2e7f2-117">[**編集**] ウィンドウの [**割り当て先**] の下で、表示名またはユーザー名でユーザーを検索し、[**割り当て**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2e7f2-117">In the **Edit** pane, under **Assigned to**, search for the user by display name or user name, and then click **Assign**.</span></span>
4. <span data-ttu-id="2e7f2-118">関連する緊急対応の場所を割り当てる、または変更するには、[緊急対応の**場所**] で、場所を検索して選択します。</span><span class="sxs-lookup"><span data-stu-id="2e7f2-118">To assign or change the associated emergency location, under **Emergency location**, search for and then select the location.</span></span>
6. <span data-ttu-id="2e7f2-119">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2e7f2-119">Click **Save**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="2e7f2-120">Office 365 と Teams の間の待機時間のために、ユーザーが有効になるまで最大24時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="2e7f2-120">Because of the latency between Office 365 and Teams, it can possibly take up to 24 hours for users to be enabled.</span></span> <span data-ttu-id="2e7f2-121">24時間後に電話番号が正しく割り当てられていない場合は、 [PSTN サービスデスクに問い合わせてください](manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md)。</span><span class="sxs-lookup"><span data-stu-id="2e7f2-121">If after 24 hours, if the phone number isn't assigned correctly, [contact the PSTN service desk](manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md).</span></span> <span data-ttu-id="2e7f2-122">ここでは、ご意見をお待ちしています。</span><span class="sxs-lookup"><span data-stu-id="2e7f2-122">We're here to help!</span></span>
  
## <a name="change-a-phone-number-for-a-user"></a><span data-ttu-id="2e7f2-123">ユーザーの電話番号を変更する</span><span class="sxs-lookup"><span data-stu-id="2e7f2-123">Change a phone number for a user</span></span>
 
<span data-ttu-id="2e7f2-124">![Microsoft teams](media/teams-logo-30x30.png) **管理センターを使用し**た microsoft teams ロゴを示すアイコン</span><span class="sxs-lookup"><span data-stu-id="2e7f2-124">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>
    
1. <span data-ttu-id="2e7f2-125">左側のナビゲーションで [**ユーザー**] をクリックし、目的のユーザーを見つけてダブルクリックし、[**アカウント**] をクリックし、[**全般情報**] で、ユーザーに割り当てられている電話番号をメモします。</span><span class="sxs-lookup"><span data-stu-id="2e7f2-125">In the left navigation, click **Users**, locate and double-click the user you want, click **Account**, and then under **General information**, make a note of the phone number that's assigned to the user.</span></span>
2. <span data-ttu-id="2e7f2-126">左側のナビゲーションで、[ \*\*\*\* > **電話番号**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2e7f2-126">In the left navigation, click **Voice** > **Phone numbers**.</span></span>
3. <span data-ttu-id="2e7f2-127">[**電話番号**] ページで、手順1で指定した番号を選択し、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2e7f2-127">On the **Phone numbers** page, select the number that you identified in step 1, and then click **Edit**.</span></span>  
4. <span data-ttu-id="2e7f2-128">[**編集**] ウィンドウの [**割り当て先**] で、[ **X** ] をクリックしてユーザーを削除します。</span><span class="sxs-lookup"><span data-stu-id="2e7f2-128">In the **Edit** pane, under **Assigned to**, click the **X** to remove the user.</span></span>
5. <span data-ttu-id="2e7f2-129">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2e7f2-129">Click **Save**.</span></span>
6. <span data-ttu-id="2e7f2-130">[**電話番号**] ページで、リスト内の未使用の番号を選択し、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2e7f2-130">On the **Phone numbers** page, select an unassigned number in the list, and then click **Edit**.</span></span>  
7. <span data-ttu-id="2e7f2-131">[**編集**] ウィンドウの [**割り当て先**] の下で、表示名またはユーザー名でユーザーを検索し、[**割り当て**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2e7f2-131">In the **Edit** pane, under **Assigned to**, search for the user by display name or user name, and then click **Assign**.</span></span>
8. <span data-ttu-id="2e7f2-132">関連する緊急対応の場所を割り当てる、または変更するには、[緊急対応の**場所**] で、場所を検索して選択します。</span><span class="sxs-lookup"><span data-stu-id="2e7f2-132">To assign or change the associated emergency location, under **Emergency location**, search for and then select the location.</span></span>
9. <span data-ttu-id="2e7f2-133">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2e7f2-133">Click **Save**.</span></span>

## <a name="remove-a-phone-number-from-a-user"></a><span data-ttu-id="2e7f2-134">ユーザーの電話番号を削除する</span><span class="sxs-lookup"><span data-stu-id="2e7f2-134">Remove a phone number from a user</span></span>
 
<span data-ttu-id="2e7f2-135">![Microsoft teams](media/teams-logo-30x30.png) **管理センターを使用し**た microsoft teams ロゴを示すアイコン</span><span class="sxs-lookup"><span data-stu-id="2e7f2-135">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="2e7f2-136">左側のナビゲーションで [**ユーザー**] をクリックし、目的のユーザーを見つけてダブルクリックし、[**アカウント**] をクリックし、[**全般情報**] で、ユーザーに割り当てられている電話番号をメモします。</span><span class="sxs-lookup"><span data-stu-id="2e7f2-136">In the left navigation, click **Users**, locate and double-click the user you want, click **Account**, and then under **General information**, make a note of the phone number that's assigned to the user.</span></span>
2. <span data-ttu-id="2e7f2-137">左側のナビゲーションで、[ \*\*\*\* > **電話番号**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2e7f2-137">In the left navigation, click **Voice** > **Phone numbers**.</span></span>
3. <span data-ttu-id="2e7f2-138">[**電話番号**] ページで、手順2で指定した番号を選び、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2e7f2-138">On the **Phone numbers** page, select the number that you identified in step 2, and then click **Edit**.</span></span>  
4. <span data-ttu-id="2e7f2-139">[**編集**] ウィンドウの [**割り当て先**] で、[ **X** ] をクリックしてユーザーを削除します。</span><span class="sxs-lookup"><span data-stu-id="2e7f2-139">In the **Edit** pane, under **Assigned to**, click the **X** to remove the user.</span></span>
5. <span data-ttu-id="2e7f2-140">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2e7f2-140">Click **Save**.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="2e7f2-141">関連トピック</span><span class="sxs-lookup"><span data-stu-id="2e7f2-141">Related topics</span></span>

[<span data-ttu-id="2e7f2-142">住所検証とは何ですか?</span><span class="sxs-lookup"><span data-stu-id="2e7f2-142">What is address validation?</span></span>](/skypeforbusiness/what-are-calling-plans-in-office-365/what-is-address-validation)

<span data-ttu-id="2e7f2-143">[[[Skype for Business 新しい電話番号の申請](/microsoftteams/manage-phone-numbers-for-your-organization)] に移動することによって、電話番号を取得するために利用できるすべてのフォームを一覧表示してダウンロードすることができます。](/microsoftteams/manage-phone-numbers-for-your-organization)</span><span class="sxs-lookup"><span data-stu-id="2e7f2-143">[Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization)</span></span>

[<span data-ttu-id="2e7f2-144">緊急通話の利用条件</span><span class="sxs-lookup"><span data-stu-id="2e7f2-144">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="2e7f2-145">[緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="2e7f2-145">[Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>