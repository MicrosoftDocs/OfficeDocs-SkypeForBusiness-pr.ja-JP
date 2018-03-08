---
title: "割り当て、変更、またはユーザーの電話番号を削除します。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 91089761-cb87-4119-885b-3713840dd9f7
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
- Strat_SB_PSTN
description: "割り当て、変更、または Skype for Business ユーザー企業とクライアント外通話できるように、勤務先の電話番号を削除する方法について説明します。"
ms.openlocfilehash: 34d60b9a032cbf3de472eb0f99c1027aea619217
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="assign-change-or-remove-a-phone-number-for-a-user"></a><span data-ttu-id="8fe8a-103">割り当て、変更、またはユーザーの電話番号を削除します。</span><span class="sxs-lookup"><span data-stu-id="8fe8a-103">Assign, change, or remove a phone number for a user</span></span>

<span data-ttu-id="8fe8a-104">Office 365 のプランの呼び出しを設定すると、電話番号をユーザーに割り当ています。</span><span class="sxs-lookup"><span data-stu-id="8fe8a-104">When you set up Calling Plans in Office 365, you assign phone numbers to your users.</span></span> 

<span data-ttu-id="8fe8a-105">Microsoft チーム クライアントでは、**通話**をクリックしたときに、電話番号を割り当てることが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8fe8a-105">In the Microsoft Teams client, the phone number you assign will be listed when they click **Calls**.</span></span>

![ユーザーの電話番号が Microsoft チームに表示されます。](../images/teams-phone-number.png)

<span data-ttu-id="8fe8a-107">Skype for Business クライアントでは、電話番号を割り当てることは、**勤務先**] ボックスに表示され、ユーザーが変更できないです。</span><span class="sxs-lookup"><span data-stu-id="8fe8a-107">In the Skype for Business client, the phone number you assign will be listed in the **Work Phone** box and can't be changed by a user.</span></span>
  
![勤務先の電話番号がない灰色表示します。](../images/5212fa64-b55c-4398-9709-a334f3ffa749.png)
  
> [!IMPORTANT]
> <span data-ttu-id="8fe8a-109">ユーザーが[Skype for Business の自分の電話番号を変更して](https://support.office.com/article/20e03cc1-c023-4e5d-bafd-064ddb59ed5e)、電話番号にするか、Skype for Business アプリは変更できませんが使えない、管理者が設定では、そのことを意味して変更できないことします。</span><span class="sxs-lookup"><span data-stu-id="8fe8a-109">If a user wants to [change his or her phone number for Skype for Business](https://support.office.com/article/20e03cc1-c023-4e5d-bafd-064ddb59ed5e) and the phone number in the Skype for Business app can't be changed or is grayed out, that means an admin has set it for them and it can't be changed by them.</span></span>
  
## <a name="assigning-a-number"></a><span data-ttu-id="8fe8a-110">番号を割り当てる</span><span class="sxs-lookup"><span data-stu-id="8fe8a-110">Assigning a number</span></span>

<span data-ttu-id="8fe8a-111">ときにセットアップしているユーザー電話を受けるを行うことができます、最初に Business 管理センターの Skype を使用し、電話番号を割り当てる必要がありますが、変更したりする必要がある場合は、電話番号を削除するようにします。</span><span class="sxs-lookup"><span data-stu-id="8fe8a-111">When you are setting up users so they can make and receive phone calls, you must first use the Skype for Business admin center and assign a phone number, but you can change or remove the phone number if you need to.</span></span>
  
<span data-ttu-id="8fe8a-112">Office 365 のプランの呼び出しを取得する方法、およびいくらかかりますについては、 [Skype for Business や Microsoft チーム アドオンのライセンス](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8fe8a-112">To learn how to get Calling Plans in Office 365 and how much they cost, see [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="8fe8a-p101">ユーザーが割り当てられているライセンスを持っているかどうかを表示する方法の 1 つは**Skype for Business 管理センター**に移動して、 > **音声** > **音声のユーザー**とユーザーを選択します。ライセンスが割り当てられた場合は、**割り当て済みのライセンス**の下で表示されます。また、Office 365 管理センターを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="8fe8a-p101">One way to see whether a user has a license assigned is by going to **Skype for Business admin center** > **Voice** > **Voice users** and selecting the user. If a license is assigned, it will be noted under **Assigned license**. You also can use the Office 365 admin center.</span></span> 
  
 <span data-ttu-id="8fe8a-116">**電話番号をユーザーに割り当てる**</span><span class="sxs-lookup"><span data-stu-id="8fe8a-116">**Assign a phone number to a user**</span></span>
  
1. <span data-ttu-id="8fe8a-117">職場または学校のアカウントで Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="8fe8a-117">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="8fe8a-118">**Office 365 管理センター**に移動 > **管理センター** > **Skype for Business**します。</span><span class="sxs-lookup"><span data-stu-id="8fe8a-118">Go to **Office 365 admin center** > **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="8fe8a-119">左のナビゲーションで [**音声**] をクリックして > **ボイス ユーザー**。</span><span class="sxs-lookup"><span data-stu-id="8fe8a-119">In the left navigation, click **Voice** > **Voice users**.</span></span>
    
    <span data-ttu-id="8fe8a-120">**重要**: が Skype for Business 管理センターの左のナビゲーションでの**音声**オプションを表示するには、必要があります最初の購入に少なくとも 1 つの**エンタープライズ E5 ライセンス**、1 つの**電話システムで**アドオン ライセンスまたはいずれかの**電話会議**アドオン ライセンスします。</span><span class="sxs-lookup"><span data-stu-id="8fe8a-120">**IMPORTANT**: For you to see the **Voice** option in the left navigation in the Skype for Business admin center, you must first buy at least one **Enterprise E5 license**, one **Phone System** add-on license, or one **Audio Conferencing** add-on license.</span></span>
    
4. <span data-ttu-id="8fe8a-121">[**音声ユーザー** ] ページを見つけて、または電話番号を割り当てるユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="8fe8a-121">On the **Voice users** page, locate and select the user or users that you want to assign a phone number to.</span></span>
    
5. <span data-ttu-id="8fe8a-122">操作ウィンドウで、**番号を割り当てる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8fe8a-122">In the Action pane, click **Assign number**.</span></span>
    
6. <span data-ttu-id="8fe8a-123">[**割り当てる番号の選択**] の一覧で [**番号の割り当て**] ページで、ユーザーの電話番号を選択します。</span><span class="sxs-lookup"><span data-stu-id="8fe8a-123">On the **Assign number** page in the **Select number to assign** list, select the phone number for the user.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="8fe8a-p102">を記載されている任意の電話番号が表示されない場合[、ユーザーの電話番号を取得](getting-phone-numbers-for-your-users.md)する最初します。**Skype for Business 管理センター**を使用している場合や、 > **音声** > **電話番号**] ページの**追加**] をクリックし、[**ユーザーの新しい番号**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8fe8a-p102">If you don't see any phone numbers listed, you need to [Getting phone numbers for your users](getting-phone-numbers-for-your-users.md) first. Or, if you use the **Skype for Business admin center** > **Voice** > **Phone numbers** page, click **Add**, and then click **New user numbers**.</span></span> 
  
7. <span data-ttu-id="8fe8a-126">割り当てを行う**選択緊急の場所を検証する**には、[関連する緊急アドレスを変更、リストから場所を選択するか、定義されている多くの場所を使っている場合、検索ボックスに市区町村の名前を入力し、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8fe8a-126">To assign or change the associated emergency address, under **Select validated emergency location**, either select the location from the list or, if you have many locations defined, enter the name of the city in the search box and click **Search**.</span></span>
    
8. <span data-ttu-id="8fe8a-127">電話番号と緊急の場所を選択した後に [**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8fe8a-127">After you pick the phone number and emergency location, click **Save**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="8fe8a-p103">理由により、Office 365 と Skype for Business Online の間、待機時間かかることが可能性のあるまで 24 時間を有効にするユーザー。24 時間、電話番号が正しく割り当てられていない場合は後の場合は、[ビジネス製品 - 管理者向けヘルプのサポートに問い合わせてください](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)をしてください。ここでは解消ためです。</span><span class="sxs-lookup"><span data-stu-id="8fe8a-p103">Because of the latency between Office 365 and Skype for Business Online, it can possibly take up to 24 hours for users to be enabled. If after 24 hours, if the phone number isn't assigned correctly, please [Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b). We're here to help!</span></span> 
  
## <a name="changing-a-number"></a><span data-ttu-id="8fe8a-131">番号を変更します。</span><span class="sxs-lookup"><span data-stu-id="8fe8a-131">Changing a number</span></span>

 <span data-ttu-id="8fe8a-132">**ユーザーの電話番号を変更するのには**</span><span class="sxs-lookup"><span data-stu-id="8fe8a-132">**To change a phone number for a user**</span></span>
  
1. <span data-ttu-id="8fe8a-133">職場または学校のアカウントで Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="8fe8a-133">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="8fe8a-134">**Office 365 管理センター**に移動 > **管理センター** > **Skype for Business**します。</span><span class="sxs-lookup"><span data-stu-id="8fe8a-134">Go to **Office 365 admin center** > **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="8fe8a-135">左のナビゲーションで [**音声**] をクリックして > **ボイス ユーザー**。</span><span class="sxs-lookup"><span data-stu-id="8fe8a-135">In the left navigation, click **Voice** > **Voice users**.</span></span>
    
4. <span data-ttu-id="8fe8a-136">[**音声ユーザー** ] ページを見つけての電話番号を変更するユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="8fe8a-136">On the **Voice users** page, locate and select the user or users that you want to change a phone number for.</span></span>
    
5. <span data-ttu-id="8fe8a-137">操作ウィンドウ] の [**割り当てられた番号**] で [**変更**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8fe8a-137">In the Action pane, under **Assigned number**, click **Change**.</span></span> 
    
6. <span data-ttu-id="8fe8a-138">[**番号の割り当て**] ページの**番号を変更**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8fe8a-138">On the **Assign number** page, click **Change number**.</span></span>
    
7. <span data-ttu-id="8fe8a-139">[**番号を割り当てる**] ページで、**割り当てる番号を選択する**には、[新しい電話番号を選択するのにリストを使用します。</span><span class="sxs-lookup"><span data-stu-id="8fe8a-139">On the **Assign number** page, under **Select number to assign**, use the list to select the new phone number.</span></span> 
    
8. <span data-ttu-id="8fe8a-140">関連付けられた緊急アドレスを変更するには、**場所を変更**するには、をクリックしてください**緊急のアドレスを変更**するには、[のか、一覧から場所を選択したり、定義されている多くの場所を使っている場合、検索ボックスに、市区町村の名前を入力し、] をクリックしてください**検索**します。</span><span class="sxs-lookup"><span data-stu-id="8fe8a-140">To change the associated emergency address, click **Change location**, and then under **Change emergency address to**, either select the location from the list or, if you have many locations defined, enter the name of the city in the search box and click **Search**.</span></span>
    
9. <span data-ttu-id="8fe8a-141">{[**保存**] をクリックします。}</span><span class="sxs-lookup"><span data-stu-id="8fe8a-141">Click **Save**.</span></span>
    
## <a name="removing-a-number"></a><span data-ttu-id="8fe8a-142">番号を削除します。</span><span class="sxs-lookup"><span data-stu-id="8fe8a-142">Removing a number</span></span>

 <span data-ttu-id="8fe8a-143">**ユーザーからの電話番号を削除するのには**</span><span class="sxs-lookup"><span data-stu-id="8fe8a-143">**To remove a phone number from a user**</span></span>
  
1. <span data-ttu-id="8fe8a-144">職場または学校のアカウントで Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="8fe8a-144">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="8fe8a-145">**Office 365 管理センター**に移動 > **管理センター** > **Skype for Business**します。</span><span class="sxs-lookup"><span data-stu-id="8fe8a-145">Go to **Office 365 admin center** > **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="8fe8a-146">左のナビゲーションで [**音声**] をクリックして > **ボイス ユーザー**。</span><span class="sxs-lookup"><span data-stu-id="8fe8a-146">In the left navigation, click **Voice** > **Voice users**.</span></span>
    
4. <span data-ttu-id="8fe8a-147">[**音声ユーザー** ] ページを見つけて、電話番号を削除するユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="8fe8a-147">On the **Voice users** page, locate and select the user or users that you want to remove the phone number for.</span></span>
    
5. <span data-ttu-id="8fe8a-148">操作ウィンドウで、[**割り当てられた番号**] で [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8fe8a-148">In the Action pane, under **Assigned number**, click **Remove**.</span></span> 
    
6. <span data-ttu-id="8fe8a-149">[**削除が選択されている番号が割り当てられますか?** ] ページで、[**はい**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8fe8a-149">On the **Remove selected assigned number?** page, click **Yes**.</span></span>
    

## <a name="related-topics"></a><span data-ttu-id="8fe8a-150">関連トピック</span><span class="sxs-lookup"><span data-stu-id="8fe8a-150">Related topics</span></span>
[<span data-ttu-id="8fe8a-151">アドレスの入力規則とは何ですか。</span><span class="sxs-lookup"><span data-stu-id="8fe8a-151">What is address validation?</span></span>](what-is-address-validation.md)

[<span data-ttu-id="8fe8a-152">組織の電話番号を管理します。</span><span class="sxs-lookup"><span data-stu-id="8fe8a-152">Manage phone numbers for your organization</span></span>](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[<span data-ttu-id="8fe8a-153">緊急の呼び出し元の条項および条件</span><span class="sxs-lookup"><span data-stu-id="8fe8a-153">Emergency calling terms and conditions</span></span>](emergency-calling-terms-and-conditions.md)

[<span data-ttu-id="8fe8a-154">Skype for Business Online: 緊急発信免責事項のラベル</span><span class="sxs-lookup"><span data-stu-id="8fe8a-154">Skype for Business Online: Emergency Calling disclaimer label</span></span>](https://go.microsoft.com/fwlink/?LinkID=692099)