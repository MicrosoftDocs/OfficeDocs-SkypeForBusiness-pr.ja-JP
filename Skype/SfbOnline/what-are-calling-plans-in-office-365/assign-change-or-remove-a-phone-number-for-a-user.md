---
title: ユーザーの電話番号の割り当て、変更、削除を行う
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 91089761-cb87-4119-885b-3713840dd9f7
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: 外部のビジネスやクライアントがコールインできるように、勤務先電話番号を Skype for Business ユーザーに割り当てる、変更する、または削除する方法を学びます。
ms.openlocfilehash: 4e0189f29b2e7f8324e378c4ad314f8a55a8fa0b
ms.sourcegitcommit: 31827526894ffb75d64fcb0a7c76ee874ad3c269
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2019
ms.locfileid: "29754870"
---
# <a name="assign-change-or-remove-a-phone-number-for-a-user"></a><span data-ttu-id="c8e29-103">ユーザーの電話番号の割り当て、変更、削除を行う</span><span class="sxs-lookup"><span data-stu-id="c8e29-103">Assign, change, or remove a phone number for a user</span></span>

<span data-ttu-id="c8e29-104">Office 365 のプランの呼び出しを設定すると、ユーザーに電話番号を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="c8e29-104">When you set up Calling Plans in Office 365, you assign phone numbers to your users.</span></span> 

<span data-ttu-id="c8e29-105">Microsoft Teams クライアントで、[**呼び出し**] をクリックすると、割り当てる電話番号が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="c8e29-105">In the Microsoft Teams client, the phone number you assign will be listed when they click **Calls**.</span></span>

![ユーザーの電話番号が Microsoft Teams に表示されます。](../images/teams-phone-number.png)

<span data-ttu-id="c8e29-107">Skype for Business クライアントで、割り当てる電話番号が [ **勤務先電話番号** ] ボックスに一覧にされますが、ユーザーが電話番号を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="c8e29-107">In the Skype for Business client, the phone number you assign will be listed in the **Work Phone** box and can't be changed by a user.</span></span>
  
![勤務先電話番号は、グレー表示されます。](../images/5212fa64-b55c-4398-9709-a334f3ffa749.png)
  
> [!IMPORTANT]
> <span data-ttu-id="c8e29-109">ユーザーが [Skype for Business の自分の電話番号を変更](https://support.office.com/article/20e03cc1-c023-4e5d-bafd-064ddb59ed5e) しようとしても、Skype for Business アプリで電話番号を変更できないか、グレー表示されます。つまり、電話番号は管理者がユーザーに対して設定したもので、ユーザーが変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="c8e29-109">If a user wants to [change his or her phone number for Skype for Business](https://support.office.com/article/20e03cc1-c023-4e5d-bafd-064ddb59ed5e) and the phone number in the Skype for Business app can't be changed or is grayed out, that means an admin has set it for them and it can't be changed by them.</span></span>
  


<span data-ttu-id="c8e29-110">ユーザーが電話をかけたり、受けたりできるようにユーザーをセットアップするときは、まず Skype for Business 管理センターを使用して電話番号を割り当てます。このとき、必要に応じて、電話番号を変更したり削除したりできます。</span><span class="sxs-lookup"><span data-stu-id="c8e29-110">When you are setting up users so they can make and receive phone calls, you must first use the Skype for Business admin center and assign a phone number, but you can change or remove the phone number if you need to.</span></span>
  
<span data-ttu-id="c8e29-111">Office 365 の通話プランの取得方法とかかる費用については、[Skype for Business と Microsoft Teams アドオン ライセンシング](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8e29-111">To learn how to get Calling Plans in Office 365 and how much they cost, see [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="c8e29-p101">One way to see whether a user has a license assigned is by going to **Skype for Business admin center** > **Voice** > **Voice users** and selecting the user. If a license is assigned, it will be noted under **Assigned license**. You also can use the Office 365 admin center.</span><span class="sxs-lookup"><span data-stu-id="c8e29-p101">One way to see whether a user has a license assigned is by going to **Skype for Business admin center** > **Voice** > **Voice users** and selecting the user. If a license is assigned, it will be noted under **Assigned license**. You also can use the Office 365 admin center.</span></span> 
  
 ## <a name="assign-a-phone-number-to-a-user"></a><span data-ttu-id="c8e29-115">ユーザーに電話番号を割り当てる</span><span class="sxs-lookup"><span data-stu-id="c8e29-115">Assign a phone number to a user</span></span>
 
<span data-ttu-id="c8e29-116">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Skype for Business の管理センターを使用する**</span><span class="sxs-lookup"><span data-stu-id="c8e29-116">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
 
1. <span data-ttu-id="c8e29-117">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="c8e29-117">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="c8e29-118">**マイクロソフトのチーム管理センター**を参照して > **従来のポータル**です。</span><span class="sxs-lookup"><span data-stu-id="c8e29-118">Go to **Microsoft Teams admin center** > **Legacy portal**.</span></span>
    
3. <span data-ttu-id="c8e29-119">左のナビゲーションで、[ **音声**]  > \*\*[音声ユーザー] \*\*の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8e29-119">In the left navigation, click **Voice** > **Voice users**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="c8e29-120">ビジネス管理センターの Skype では、左側のナビゲーションの**音声**オプションを表示するため、まず**E5 のエンタープライズ ライセンス**を少なくとも 1 つ、1 つの**電話システム**のアドオン ライセンスまたはアドオンのライセンスが 1 つの**電話会議**を購入する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8e29-120">For you to see the **Voice** option in the left navigation in the Skype for Business admin center, you must first buy at least one **Enterprise E5 license**, one **Phone System** add-on license, or one **Audio Conferencing** add-on license.</span></span>
 
   
    
4. <span data-ttu-id="c8e29-121">**ボイス ユーザー** ページで、ユーザー、または電話番号を割り当てるユーザーを見つけて、選択します。</span><span class="sxs-lookup"><span data-stu-id="c8e29-121">On the **Voice users** page, locate and select the user or users that you want to assign a phone number to.</span></span>
    
5. <span data-ttu-id="c8e29-122">[操作] ウィンドウで、 **割り当てる番号** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8e29-122">In the Action pane, click **Assign number**.</span></span>
    
6. <span data-ttu-id="c8e29-123">[**割り当てる番号の選択**] ボックスの一覧で**番号を割り当てる**] ページで、ユーザーの電話番号を選択します。</span><span class="sxs-lookup"><span data-stu-id="c8e29-123">On the **Assign number** page in the **Select number to assign** list, select the phone number for the user.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="c8e29-124">電話番号の一覧が表示されない場合する必要があります[、ユーザーの電話番号を取得](getting-phone-numbers-for-your-users.md)する最初にします。</span><span class="sxs-lookup"><span data-stu-id="c8e29-124">If you don't see any phone numbers listed, you need to [get phone numbers for your users](getting-phone-numbers-for-your-users.md) first.</span></span> <span data-ttu-id="c8e29-125">または、**Skype for Business 管理センター**を使用している場合は、 > **音声** > **電話番号** ページで、[**追加**] をクリックしてから、[ **新しいユーザーの番号**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8e29-125">Or, if you use the **Skype for Business admin center** > **Voice** > **Phone numbers** page, click **Add**, and then click **New user numbers**.</span></span> 
  
7. <span data-ttu-id="c8e29-126">**有効な緊急対応の場所を選択する**の下で、関連付けられている緊急対応の住所を割り当てるまたは変更するには、リストから場所を選択します。定義された場所が多くある場合は、[検索] ボックスに都市の名前を入力して、**[検索]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8e29-126">To assign or change the associated emergency address, under **Select validated emergency location**, either select the location from the list or, if you have many locations defined, enter the name of the city in the search box and click **Search**.</span></span>
    
8. <span data-ttu-id="c8e29-127">電話番号と緊急対応の場所を選択した後、[ **保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8e29-127">After you pick the phone number and emergency location, click **Save**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c8e29-p103">Because of the latency between Office 365 and Skype for Business Online, it can possibly take up to 24 hours for users to be enabled. If after 24 hours, if the phone number isn't assigned correctly, please [Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b). We're here to help!</span><span class="sxs-lookup"><span data-stu-id="c8e29-p103">Because of the latency between Office 365 and Skype for Business Online, it can possibly take up to 24 hours for users to be enabled. If after 24 hours, if the phone number isn't assigned correctly, please [Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b). We're here to help!</span></span> 
  


 ## <a name="change-a-phone-number-for-a-user"></a><span data-ttu-id="c8e29-131">ユーザーの電話番号を変更します。</span><span class="sxs-lookup"><span data-stu-id="c8e29-131">Change a phone number for a user</span></span>
 
<span data-ttu-id="c8e29-132">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Skype for Business の管理センターを使用する**</span><span class="sxs-lookup"><span data-stu-id="c8e29-132">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
 
1. <span data-ttu-id="c8e29-133">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="c8e29-133">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="c8e29-134">**マイクロソフトのチーム管理センター**を参照して > **従来のポータル**です。</span><span class="sxs-lookup"><span data-stu-id="c8e29-134">Go to **Microsoft Teams admin center** > **Legacy portal**.</span></span>
    
3. <span data-ttu-id="c8e29-135">左のナビゲーションで、[ **音声**]  > \*\*[音声ユーザー] \*\*の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8e29-135">In the left navigation, click **Voice** > **Voice users**.</span></span>
    
4. <span data-ttu-id="c8e29-136">**音声ユーザー** ページで、ユーザー、または電話番号を変更するユーザーを見つけて、選択します。</span><span class="sxs-lookup"><span data-stu-id="c8e29-136">On the **Voice users** page, locate and select the user or users that you want to change a phone number for.</span></span>
    
5. <span data-ttu-id="c8e29-137">[操作] ウィンドウで、**割り当て番号**の下の [**変更**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8e29-137">In the Action pane, under **Assigned number**, click **Change**.</span></span> 
    
6. <span data-ttu-id="c8e29-138">**番号の割り当て**] ページで、**変更番号**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8e29-138">On the **Assign number** page, click **Change number**.</span></span>
    
7. <span data-ttu-id="c8e29-139">**番号の割り当て**ページの [ **割り当てる番号を選択する**の下で、リストを使用して、新しい電話番号を選択します。</span><span class="sxs-lookup"><span data-stu-id="c8e29-139">On the **Assign number** page, under **Select number to assign**, use the list to select the new phone number.</span></span> 
    
8. <span data-ttu-id="c8e29-140">関連付けられた緊急対応の住所を変更するには、[**場所を変更**] をクリックして、**緊急対応の住所の変更**の下で、一覧から場所を選択します。または、定義されている場所が多くある場合、[検索] ボックスに都市の名前を入力して、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8e29-140">To change the associated emergency address, click **Change location**, and then under **Change emergency address to**, either select the location from the list or, if you have many locations defined, enter the name of the city in the search box and click **Search**.</span></span>
    
9. <span data-ttu-id="c8e29-141">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8e29-141">Click **Save**.</span></span>
    


 ## <a name="remove-a-phone-number-from-a-user"></a><span data-ttu-id="c8e29-142">ユーザーの電話番号を削除する</span><span class="sxs-lookup"><span data-stu-id="c8e29-142">Remove a phone number from a user</span></span>
 
<span data-ttu-id="c8e29-143">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Skype for Business の管理センターを使用する**</span><span class="sxs-lookup"><span data-stu-id="c8e29-143">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
 
1. <span data-ttu-id="c8e29-144">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="c8e29-144">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="c8e29-145">**マイクロソフトのチーム管理センター**を参照して > **従来のポータル**です。</span><span class="sxs-lookup"><span data-stu-id="c8e29-145">Go to **Microsoft Teams admin center** > **Legacy portal**.</span></span>
    
3. <span data-ttu-id="c8e29-146">左のナビゲーションで、[ **音声**]  > \*\*[音声ユーザー] \*\*の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8e29-146">In the left navigation, click **Voice** > **Voice users**.</span></span>
    
4. <span data-ttu-id="c8e29-147">**音声ユーザー** ページで、ユーザー、または電話番号を削除するユーザーを見つけて、選択します。</span><span class="sxs-lookup"><span data-stu-id="c8e29-147">On the **Voice users** page, locate and select the user or users that you want to remove the phone number for.</span></span>
    
5. <span data-ttu-id="c8e29-148">[操作] ウィンドウで、[**割り当ての数**、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8e29-148">In the Action pane, under **Assigned number**, click **Remove**.</span></span> 
    
6. <span data-ttu-id="c8e29-149">**選択されている割り当て番号を削除しますか？** ページで、[ **はい**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8e29-149">On the **Remove selected assigned number?** page, click **Yes**.</span></span>
    

## <a name="related-topics"></a><span data-ttu-id="c8e29-150">関連トピック</span><span class="sxs-lookup"><span data-stu-id="c8e29-150">Related topics</span></span>
[<span data-ttu-id="c8e29-151">住所検証について</span><span class="sxs-lookup"><span data-stu-id="c8e29-151">What is address validation?</span></span>](what-is-address-validation.md)

<span data-ttu-id="c8e29-152">[[[Skype for Business 新しい電話番号の申請](/microsoftteams/manage-phone-numbers-for-your-organization)] に移動することによって、電話番号を取得するために利用できるすべてのフォームを一覧表示してダウンロードすることができます。](/microsoftteams/manage-phone-numbers-for-your-organization)</span><span class="sxs-lookup"><span data-stu-id="c8e29-152">[Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization)</span></span>

[<span data-ttu-id="c8e29-153">緊急通話の利用条件</span><span class="sxs-lookup"><span data-stu-id="c8e29-153">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="c8e29-154">[Skype for Business Online: 緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="c8e29-154">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 