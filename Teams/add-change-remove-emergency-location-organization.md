---
title: 組織の緊急対応の場所を追加、変更、削除する
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
description: 'Microsoft Teams 管理センターで、組織の緊急対応の場所を追加、変更、または削除する方法について説明します。 '
ms.openlocfilehash: e0befb48ce5cc6c896db89d7defbde94d01c9278
ms.sourcegitcommit: 8fb89d6226b02ba8b1f8396eb4d1a37da4608b7c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2019
ms.locfileid: "37396523"
---
# <a name="add-change-or-remove-an-emergency-location-for-your-organization"></a><span data-ttu-id="aba2d-103">組織の緊急対応の場所を追加、変更、削除する</span><span class="sxs-lookup"><span data-stu-id="aba2d-103">Add, change, or remove an emergency location for your organization</span></span>

<span data-ttu-id="aba2d-104">緊急対応の場所は電話番号と関連付けられている必要がありますが、このような状況は国と地域によって異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="aba2d-104">An emergency location must be associated with a phone number, but when this happens can vary between countries and regions.</span></span> <span data-ttu-id="aba2d-105">たとえば、米国では、電話番号をユーザーに割り当てるときに緊急対応の場所を関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="aba2d-105">For example, in the United States, you need to associate an emergency location when you assign the phone number to the user.</span></span> <span data-ttu-id="aba2d-106">英国では、Office 365 から電話番号を取得する場合や、現在のサービスプロバイダーから電話番号を移行する場合に、緊急対応の場所を電話番号に関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="aba2d-106">In the United Kingdom, you need to associate an emergency location to the phone number when you get the phone numbers from Office 365 or transfer phone numbers from your current service provider.</span></span>

<span data-ttu-id="aba2d-107">お住まいの国または地域にかかわらず、緊急対応の場所を追加して、緊急対応の場所を削除することができます。</span><span class="sxs-lookup"><span data-stu-id="aba2d-107">No matter which country or region you are in, you can add a place or places to an emergency location and remove an emergency location.</span></span> <span data-ttu-id="aba2d-108">組織内の物理的な場所の数に応じて、建物、フロア、オフィスの場所を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="aba2d-108">Depending on the number of physical locations in your organization, you can create places for buildings, floors, and offices.</span></span> <span data-ttu-id="aba2d-109">[緊急対応の場所、アドレス、通話ルーティングに](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing)ついて説明します。</span><span class="sxs-lookup"><span data-stu-id="aba2d-109">See [What are emergency locations, addresses and call routing?](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing).</span></span>
  
<span data-ttu-id="aba2d-110">通話プランの取得方法とコストについては、「Teams の[アドオンライセンス](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aba2d-110">To learn how to get a Calling Plan and how much they cost, see [Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
  
## <a name="add-an-emergency-location"></a><span data-ttu-id="aba2d-111">緊急対応の場所を追加する</span><span class="sxs-lookup"><span data-stu-id="aba2d-111">Add an emergency location</span></span>

1. <span data-ttu-id="aba2d-112">Microsoft Teams 管理センターの左のナビゲーションで、[**地域** > の**緊急対応の住所**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aba2d-112">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="aba2d-113">[**場所の追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aba2d-113">Click **Add Location**.</span></span>
3. <span data-ttu-id="aba2d-114">場所の名前と説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="aba2d-114">Enter a name and description for the location.</span></span>
4. <span data-ttu-id="aba2d-115">国または地域を選択して、住所を入力します。</span><span class="sxs-lookup"><span data-stu-id="aba2d-115">Select the country or region, and then enter the address.</span></span>

   > [!NOTE]
   > <span data-ttu-id="aba2d-116">ベルギー、フランス、ドイツ、アイルランド、オランダ、スペインでは、Office 365 で電話番号を正常にアクティブ化するために、緊急対応の場所にある住所の設定 (番号を取得するために使用される os) が電話番号の領域と一致する必要があることを理解しておくことが重要です。プログラム.</span><span class="sxs-lookup"><span data-stu-id="aba2d-116">In Belgium, France, Germany, Ireland, Netherlands, and Spain i's important to understand that  to successfully activate a phone number in Office 365, the address setup in the emergency location, which os used to acquire the number, must match the phone number’s area code.</span></span>
5. <span data-ttu-id="aba2d-117">アドレスが見つからず、手動で住所を編集したい場合は、**選択した住所が見つからない場合は、[アドレスフォームを手動で編集**する] をオンにします。</span><span class="sxs-lookup"><span data-stu-id="aba2d-117">If the address isn't found and you want to manually edit the address, turn on **Let me edit the address form manually if the address selected can't be found**.</span></span>
6. <span data-ttu-id="aba2d-118">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aba2d-118">Click **Save**.</span></span>
    
## <a name="change-an-emergency-location"></a><span data-ttu-id="aba2d-119">緊急対応の場所を変更する</span><span class="sxs-lookup"><span data-stu-id="aba2d-119">Change an emergency location</span></span>

1. <span data-ttu-id="aba2d-120">Microsoft Teams 管理センターの左のナビゲーションで、[**地域** > の**緊急対応の住所**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aba2d-120">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="aba2d-121">一覧で、変更する場所を選択し、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aba2d-121">In the list, select the location that you want to change, and then click **Edit**.</span></span>
3. <span data-ttu-id="aba2d-122">必要な変更を加えます。</span><span class="sxs-lookup"><span data-stu-id="aba2d-122">Make the changes you want.</span></span>
4. <span data-ttu-id="aba2d-123">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aba2d-123">Click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="aba2d-124">住所が検証されていない場合にのみ、場所の住所情報を変更できます。</span><span class="sxs-lookup"><span data-stu-id="aba2d-124">You can change the address information for a location only if the address isn't validated.</span></span> <span data-ttu-id="aba2d-125">住所が既に検証されていて、住所を変更する必要がある場合は、場所を削除して、正しい住所を含む新しい場所を作成します。</span><span class="sxs-lookup"><span data-stu-id="aba2d-125">If the address is already validated, and you need to change the address, delete the location, and then create a new location with the correct address.</span></span>
    
## <a name="remove-an-emergency-location"></a><span data-ttu-id="aba2d-126">緊急対応の場所を削除する</span><span class="sxs-lookup"><span data-stu-id="aba2d-126">Remove an emergency location</span></span>

1. <span data-ttu-id="aba2d-127">Microsoft Teams 管理センターの左のナビゲーションで、[**地域** > の**緊急対応の住所**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aba2d-127">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="aba2d-128">一覧で、削除する場所を選択し、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aba2d-128">In the list, select the location that you want to remove, and then click **Delete**</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="aba2d-129">関連トピック</span><span class="sxs-lookup"><span data-stu-id="aba2d-129">Related topics</span></span>

<span data-ttu-id="aba2d-130">-[緊急対応の場所、場所、通話ルーティングとは何ですか?](what-are-emergency-locations-addresses-and-call-routing.md)</span><span class="sxs-lookup"><span data-stu-id="aba2d-130">-[What are emergency locations, places, and call routing?](what-are-emergency-locations-addresses-and-call-routing.md)</span></span>
- [<span data-ttu-id="aba2d-131">組織の緊急対応の場所を追加、変更、または削除する</span><span class="sxs-lookup"><span data-stu-id="aba2d-131">Add, change, or remove a place for an emergency location in your organization</span></span>](add-change-remove-emergency-place-organization.md)
- <span data-ttu-id="aba2d-132">[[[Skype for Business 新しい電話番号の申請](/microsoftteams/manage-phone-numbers-for-your-organization)] に移動することによって、電話番号を取得するために利用できるすべてのフォームを一覧表示してダウンロードすることができます。](/microsoftteams/manage-phone-numbers-for-your-organization)</span><span class="sxs-lookup"><span data-stu-id="aba2d-132">[Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization)</span></span>
- [<span data-ttu-id="aba2d-133">緊急通話の利用条件</span><span class="sxs-lookup"><span data-stu-id="aba2d-133">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)