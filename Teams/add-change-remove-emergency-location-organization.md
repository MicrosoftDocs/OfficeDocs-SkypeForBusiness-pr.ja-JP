---
title: 緊急対応の場所を追加、変更、削除する
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
description: 'Microsoft Teams 管理センターで、組織の緊急対応の場所を追加、変更、または削除する方法について説明します。 '
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ae3a224b38fba412b9c0dc4ec0bfde5028440a79
ms.sourcegitcommit: fa567451f8f7af6d915e33809d88f26b415db54c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "44610326"
---
# <a name="add-change-or-remove-an-emergency-location-for-your-organization"></a><span data-ttu-id="beb61-103">組織の緊急対応の場所を追加、変更、削除する</span><span class="sxs-lookup"><span data-stu-id="beb61-103">Add, change, or remove an emergency location for your organization</span></span>

<span data-ttu-id="beb61-104">緊急対応の場所は電話番号と関連付けられている必要がありますが、このような状況は国と地域によって異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="beb61-104">An emergency location must be associated with a phone number, but when this happens can vary between countries and regions.</span></span> <span data-ttu-id="beb61-105">たとえば、米国では、電話番号をユーザーに割り当てるときに緊急対応の場所を関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="beb61-105">For example, in the United States, you need to associate an emergency location when you assign the phone number to the user.</span></span> <span data-ttu-id="beb61-106">英国では、Microsoft 365 または Office 365 から電話番号を取得する場合、または現在のサービスプロバイダーから電話番号を転送する場合、その電話番号に緊急対応の場所を関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="beb61-106">In the United Kingdom, you need to associate an emergency location to the phone number when you get the phone numbers from Microsoft 365 or Office 365 or transfer phone numbers from your current service provider.</span></span>

<span data-ttu-id="beb61-107">お住まいの国または地域にかかわらず、緊急対応の場所を追加して、緊急対応の場所を削除することができます。</span><span class="sxs-lookup"><span data-stu-id="beb61-107">No matter which country or region you are in, you can add a place or places to an emergency location and remove an emergency location.</span></span> <span data-ttu-id="beb61-108">組織内の物理的な場所の数に応じて、建物、フロア、オフィスの場所を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="beb61-108">Depending on the number of physical locations in your organization, you can create places for buildings, floors, and offices.</span></span> <span data-ttu-id="beb61-109">「[緊急通話を管理](what-are-emergency-locations-addresses-and-call-routing.md)する」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="beb61-109">See [Manage emergency calling](what-are-emergency-locations-addresses-and-call-routing.md).</span></span>
  
<span data-ttu-id="beb61-110">通話プランの取得方法とコストについては、「Teams の[アドオンライセンス](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="beb61-110">To learn how to get a Calling Plan and how much they cost, see [Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

<span data-ttu-id="beb61-111">組織の緊急対応の場所は、Microsoft Teams 管理センターまたは PowerShell を使用して管理します。</span><span class="sxs-lookup"><span data-stu-id="beb61-111">You manage emergency locations for your organization in the Microsoft Teams admin center or by using PowerShell.</span></span>
  
## <a name="add-an-emergency-location"></a><span data-ttu-id="beb61-112">緊急対応の場所を追加する</span><span class="sxs-lookup"><span data-stu-id="beb61-112">Add an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="beb61-113">Microsoft Teams 管理センターの使用</span><span class="sxs-lookup"><span data-stu-id="beb61-113">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="beb61-114">Microsoft Teams 管理センターの左のナビゲーションで、[**地域**の  >  **緊急対応の住所**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="beb61-114">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="beb61-115">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="beb61-115">Click **Add**.</span></span>
3. <span data-ttu-id="beb61-116">場所の名前と説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="beb61-116">Enter a name and description for the location.</span></span>
4. <span data-ttu-id="beb61-117">国または地域を選択して、住所を入力します。</span><span class="sxs-lookup"><span data-stu-id="beb61-117">Select the country or region, and then enter the address.</span></span>

   > [!NOTE]
   > <span data-ttu-id="beb61-118">ベルギー、フランス、ドイツ、アイルランド、オランダ、スペインでは、Microsoft 365 または Office 365 で電話番号を正しく有効にすることを理解しておくことが重要です。この番号を取得するために使用する緊急対応の場所で設定された住所は、電話番号の市外局番と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="beb61-118">In Belgium, France, Germany, Ireland, Netherlands, and Spain, it's important to understand that to successfully activate a phone number in Microsoft 365 or Office 365, the address set up in the emergency location, which is used to acquire the number, must match the phone number's area code.</span></span>
5. <span data-ttu-id="beb61-119">住所が見つからず、アドレスを手動で編集する場合は、[**アドレスを手動で編集**する] をオンにします。</span><span class="sxs-lookup"><span data-stu-id="beb61-119">If the address isn't found and you want to manually edit the address, turn on **Edit the address manually**.</span></span>
6. <span data-ttu-id="beb61-120">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="beb61-120">Click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="beb61-121">PowerShell を使用する場合</span><span class="sxs-lookup"><span data-stu-id="beb61-121">Using PowerShell</span></span>

<span data-ttu-id="beb61-122">「[新規-CsOnlineLisCivicAddress」を](https://docs.microsoft.com/powershell/module/skype/new-csonlineliscivicaddress)参照してください。</span><span class="sxs-lookup"><span data-stu-id="beb61-122">See [New-CsOnlineLisCivicAddress](https://docs.microsoft.com/powershell/module/skype/new-csonlineliscivicaddress).</span></span>
    
## <a name="change-an-emergency-location"></a><span data-ttu-id="beb61-123">緊急対応の場所を変更する</span><span class="sxs-lookup"><span data-stu-id="beb61-123">Change an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="beb61-124">Microsoft Teams 管理センターの使用</span><span class="sxs-lookup"><span data-stu-id="beb61-124">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="beb61-125">Microsoft Teams 管理センターの左のナビゲーションで、[**地域**の  >  **緊急対応の住所**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="beb61-125">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="beb61-126">一覧で、変更する場所を選択し、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="beb61-126">In the list, select the location that you want to change, and then click **Edit**.</span></span>
3. <span data-ttu-id="beb61-127">必要な変更を加えます。</span><span class="sxs-lookup"><span data-stu-id="beb61-127">Make the changes you want.</span></span>
4. <span data-ttu-id="beb61-128">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="beb61-128">Click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="beb61-129">住所が検証されていない場合にのみ、場所の住所情報を変更できます。</span><span class="sxs-lookup"><span data-stu-id="beb61-129">You can change the address information for a location only if the address isn't validated.</span></span> <span data-ttu-id="beb61-130">住所が既に検証されていて、住所を変更する必要がある場合は、場所を削除して、正しい住所を含む新しい場所を作成します。</span><span class="sxs-lookup"><span data-stu-id="beb61-130">If the address is already validated, and you need to change the address, delete the location, and then create a new location with the correct address.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="beb61-131">PowerShell を使用する場合</span><span class="sxs-lookup"><span data-stu-id="beb61-131">Using PowerShell</span></span>

<span data-ttu-id="beb61-132">「 [Set-CsOnlineLisCivicAddress](https://docs.microsoft.com/powershell/module/skype/set-csonlineliscivicaddress)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="beb61-132">See [Set-CsOnlineLisCivicAddress](https://docs.microsoft.com/powershell/module/skype/set-csonlineliscivicaddress).</span></span>
    
## <a name="remove-an-emergency-location"></a><span data-ttu-id="beb61-133">緊急対応の場所を削除する</span><span class="sxs-lookup"><span data-stu-id="beb61-133">Remove an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="beb61-134">Microsoft Teams 管理センターの使用</span><span class="sxs-lookup"><span data-stu-id="beb61-134">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="beb61-135">Microsoft Teams 管理センターの左のナビゲーションで、[**地域**の  >  **緊急対応の住所**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="beb61-135">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="beb61-136">一覧で、削除する場所を選択し、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="beb61-136">In the list, select the location that you want to remove, and then click **Delete**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="beb61-137">PowerShell を使用する場合</span><span class="sxs-lookup"><span data-stu-id="beb61-137">Using PowerShell</span></span>

<span data-ttu-id="beb61-138">「 [Remove-CsOnlineLisCivicAddress](https://docs.microsoft.com/powershell/module/skype/remove-csonlineliscivicaddress)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="beb61-138">See [Remove-CsOnlineLisCivicAddress](https://docs.microsoft.com/powershell/module/skype/remove-csonlineliscivicaddress).</span></span>

## <a name="related-topics"></a><span data-ttu-id="beb61-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="beb61-139">Related topics</span></span>

- [<span data-ttu-id="beb61-140">緊急通話を管理する</span><span class="sxs-lookup"><span data-stu-id="beb61-140">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="beb61-141">組織の緊急対応の場所の位置情報を追加、変更、削除する</span><span class="sxs-lookup"><span data-stu-id="beb61-141">Add, change, or remove a place for an emergency location in your organization</span></span>](add-change-remove-emergency-place-organization.md)
- [<span data-ttu-id="beb61-142">組織の電話番号を管理する</span><span class="sxs-lookup"><span data-stu-id="beb61-142">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)
- [<span data-ttu-id="beb61-143">緊急通話の利用条件</span><span class="sxs-lookup"><span data-stu-id="beb61-143">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)
