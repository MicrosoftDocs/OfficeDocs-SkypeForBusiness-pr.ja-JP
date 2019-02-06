---
title: 割り当てたり、ユーザーのシステムの場所を変更します。
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 2d5d3c87-af1e-487e-b86c-261f2e5a0661
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
description: 'Learn how to change the emergency location for your users. With an unlimited number of locations, you can change emergency locations as employees move floors or buildings. '
ms.openlocfilehash: fc128a8de266bbf5ed6804ea07cc73bb2287a6e5
ms.sourcegitcommit: 31827526894ffb75d64fcb0a7c76ee874ad3c269
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2019
ms.locfileid: "29754844"
---
# <a name="assign-or-change-the-emergency-location-for-a-user"></a><span data-ttu-id="a4353-104">割り当てたり、ユーザーのシステムの場所を変更します。</span><span class="sxs-lookup"><span data-stu-id="a4353-104">Assign or change the emergency location for a user</span></span>

<span data-ttu-id="a4353-105">各作業中の電話番号は、電話番号をユーザーに割り当てると、関連する緊急アドレスにすることが必要です。</span><span class="sxs-lookup"><span data-stu-id="a4353-105">Each active phone number must have an associated emergency address when you assign the phone number to a user.</span></span> <span data-ttu-id="a4353-106">(に関連付けるアドレス Office 365 で、または電話番号を転送するときに電話番号を取得する場合です。)数を関連付けるには、緊急時のアドレスを使用して、ときに、物理的な場所の中でより正確な場所を提供する緊急の場所を追加することも。</span><span class="sxs-lookup"><span data-stu-id="a4353-106">(You associate the address when you get a phone number in Office 365 or when you transfer a phone number.) When you associate the number with an emergency address, you can also add an emergency location to provide a more exact location within a physical location.</span></span> <span data-ttu-id="a4353-107">An emergency location can be the floor, building wing, or office number where the user is located.</span><span class="sxs-lookup"><span data-stu-id="a4353-107">An emergency location can be the floor, building wing, or office number where the user is located.</span></span> <span data-ttu-id="a4353-108">特定の緊急対応の住所に対して無制限の数の緊急対応の場所を指定できます。また、ユーザーが別のオフィスや建物に移動する場合 (例えば、ユーザーが 34 階から 35 階に移動した場合)、緊急対応の場所を変更できます。</span><span class="sxs-lookup"><span data-stu-id="a4353-108">You can have an unlimited number of locations for a given emergency address, and you can change the emergency location if the user moves to a different office or building—for example, if the user moves from floor 34 to floor 35.</span></span>
  
<span data-ttu-id="a4353-109">Office 365 の通話プランの取得方法とかかる費用については、「[Skype for Business と Microsoft Teams アドオン ライセンシング](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a4353-109">To learn how to get Calling Plans in Office 365 and how much they cost, see [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
  
## <a name="assign-or-change-the-emergency-location"></a><span data-ttu-id="a4353-110">割り当てるか、緊急の場所を変更</span><span class="sxs-lookup"><span data-stu-id="a4353-110">Assign or change the emergency location</span></span>

1. <span data-ttu-id="a4353-111">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="a4353-111">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="a4353-112">**マイクロソフトのチーム管理センター**を参照して > **従来のポータル**です。</span><span class="sxs-lookup"><span data-stu-id="a4353-112">Go to the **Microsoft Teams admin center** > **Legacy portal**.</span></span>
    
3. <span data-ttu-id="a4353-113">左側のナビゲーションでは、**音声**に移動 > **音声ユーザー**です。</span><span class="sxs-lookup"><span data-stu-id="a4353-113">In the left navigation go to **Voice** > **Voice users**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="a4353-114">ビジネス管理センターの Skype では、左側のナビゲーションの**音声**オプションを表示するため、まず**E5 のエンタープライズ ライセンス**を少なくとも 1 つ、1 つの**電話システム**のアドオン ライセンスまたはアドオンのライセンスが 1 つの**電話会議**を購入する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a4353-114">For you to see the **Voice** option in the left navigation in the Skype for Business admin center, you must first buy at least one **Enterprise E5 license**, one **Phone System** add-on license, or one **Audio Conferencing** add-on license.</span></span>
    
4. <span data-ttu-id="a4353-115">**音声ユーザー**ページで、緊急対応の場所を変更するユーザーを見つけて、選択します。</span><span class="sxs-lookup"><span data-stu-id="a4353-115">On the **Voice users** page, locate and select the user you want to change the emergency location for.</span></span>
    
5. <span data-ttu-id="a4353-116">操作ウィンドウの [ **緊急対応の場所**] で [ **変更**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a4353-116">In the Action pane, under **Emergency location**, click **Change**.</span></span>
    
6. <span data-ttu-id="a4353-117">**番号の割り当て**] ページで、[**場所の変更**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a4353-117">On the **Assign number** page, click **Change location**.</span></span> 
    
7. <span data-ttu-id="a4353-118">[**緊急時のアドレスの変更**を都市の名前をボックスに入力し、**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a4353-118">Under **Change emergency address to**, enter the name of the city in the box and click **Search**.</span></span>

8. <span data-ttu-id="a4353-119">」ドロップ ダウン リストから**別の場所の検索**を選択して、場所の名前の一部を入力してください (たとえば、**フロア**を入力します)、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a4353-119">Select **Search by location** from the drop-down list, enter a partial name for the location (for example, enter **floor**), and then click **Search**.</span></span> 
    
8. <span data-ttu-id="a4353-120">リストから緊急対応の場所を選択し、[ **保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a4353-120">Select the emergency location from the list, and then click **Save**.</span></span>
    
    <span data-ttu-id="a4353-121">一覧に表示される新しい緊急通報を追加する場合は、[追加、変更、または組織には、緊急時の場所を削除する](add-change-or-remove-an-emergency-location-for-your-organization.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a4353-121">If you want to add a new emergency location that will appear on the list, see [Add, change, or remove an emergency location for your organization](add-change-or-remove-an-emergency-location-for-your-organization.md).</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="a4353-122">関連トピック</span><span class="sxs-lookup"><span data-stu-id="a4353-122">Related topics</span></span>
[<span data-ttu-id="a4353-123">組織の緊急対応の住所を追加または削除する</span><span class="sxs-lookup"><span data-stu-id="a4353-123">Add or remove an emergency address for your organization</span></span>](add-or-remove-an-emergency-address-for-your-organization.md)

[<span data-ttu-id="a4353-124">組織の緊急対応の場所を追加、変更、削除する</span><span class="sxs-lookup"><span data-stu-id="a4353-124">Add, change, or remove an emergency location for your organization</span></span>](add-change-or-remove-an-emergency-location-for-your-organization.md)

[<span data-ttu-id="a4353-125">住所検証について</span><span class="sxs-lookup"><span data-stu-id="a4353-125">What is address validation?</span></span>](what-is-address-validation.md)

<span data-ttu-id="a4353-126">[[[Skype for Business 新しい電話番号の申請](/microsoftteams/manage-phone-numbers-for-your-organization)] に移動することによって、電話番号を取得するために利用できるすべてのフォームを一覧表示してダウンロードすることができます。](/microsoftteams/manage-phone-numbers-for-your-organization)</span><span class="sxs-lookup"><span data-stu-id="a4353-126">[Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization)</span></span>

[<span data-ttu-id="a4353-127">緊急通話の利用条件</span><span class="sxs-lookup"><span data-stu-id="a4353-127">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="a4353-128">[Skype for Business Online: 緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="a4353-128">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 