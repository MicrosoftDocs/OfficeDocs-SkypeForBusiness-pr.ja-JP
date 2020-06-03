---
title: 緊急対応の場所の場所を追加、変更、削除する
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
description: Microsoft Teams 管理センターで、組織の緊急対応の場所を追加、変更、または削除する方法について説明します。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 5ba712602ef2a966343282d4e467365f3c1c3329
ms.sourcegitcommit: d8e05e66311725f8ff6d28011355129baeb305b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/03/2020
ms.locfileid: "44539434"
---
# <a name="add-change-or-remove-a-place-for-an-emergency-location-in-your-organization"></a><span data-ttu-id="00061-103">組織の緊急対応の場所の位置情報を追加、変更、削除する</span><span class="sxs-lookup"><span data-stu-id="00061-103">Add, change, or remove a place for an emergency location in your organization</span></span>

<span data-ttu-id="00061-104">組織内の物理的な場所の数に応じて、建物、フロア、オフィスの場所を追加して、より具体的な緊急対応の場所を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="00061-104">Depending on the number of physical locations in your organization, you can add places for buildings, floors, and offices to create a more specific emergency location.</span></span> <span data-ttu-id="00061-105">詳細については、「[緊急通話を管理](what-are-emergency-locations-addresses-and-call-routing.md)する」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="00061-105">See [Manage emergency calling](what-are-emergency-locations-addresses-and-call-routing.md) for more information.</span></span>
  
<span data-ttu-id="00061-106">通話プランの取得方法とコストについては、「Teams の[アドオンライセンス](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="00061-106">To learn how to get a Calling Plan and how much they cost, see [Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

<span data-ttu-id="00061-107">組織の緊急対応の場所は、Microsoft Teams 管理センターまたは PowerShell を使用して管理します。</span><span class="sxs-lookup"><span data-stu-id="00061-107">You manage emergency locations for your organization in the Microsoft Teams admin center or by using PowerShell.</span></span>
  
## <a name="add-a-place-to-an-emergency-location"></a><span data-ttu-id="00061-108">緊急対応の場所に場所を追加する</span><span class="sxs-lookup"><span data-stu-id="00061-108">Add a place to an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="00061-109">Microsoft Teams 管理センターの使用</span><span class="sxs-lookup"><span data-stu-id="00061-109">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="00061-110">Microsoft Teams 管理センターの左のナビゲーションで、[**地域**の  >  **緊急対応の住所**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="00061-110">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="00061-111">リストで、場所を追加する場所の名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="00061-111">In the list, click the name of the location for which you want to add a place.</span></span>
3. <span data-ttu-id="00061-112">[**場所**] タブの [**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="00061-112">On the **Places** tab, click **Add**.</span></span>
4. <span data-ttu-id="00061-113">プレース名を入力し、[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="00061-113">Enter a place name, and then click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="00061-114">PowerShell を使用する場合</span><span class="sxs-lookup"><span data-stu-id="00061-114">Using PowerShell</span></span>

<span data-ttu-id="00061-115">「[新しい-Csonlin」の場所](https://docs.microsoft.com/powershell/module/skype/new-csonlinelislocation)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="00061-115">See [New-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/new-csonlinelislocation).</span></span>
    
## <a name="change-a-place-for-an-emergency-location"></a><span data-ttu-id="00061-116">緊急対応の場所を変更する</span><span class="sxs-lookup"><span data-stu-id="00061-116">Change a place for an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="00061-117">Microsoft Teams 管理センターの使用</span><span class="sxs-lookup"><span data-stu-id="00061-117">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="00061-118">Microsoft Teams 管理センターの左のナビゲーションで、[**地域**の  >  **緊急対応の住所**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="00061-118">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="00061-119">リストで、場所を変更する場所の名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="00061-119">In the list, click the name of the location for which you want to change a place.</span></span>
3. <span data-ttu-id="00061-120">[**場所**] タブで変更する場所を選択し、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="00061-120">On the **Places** tab, select the place you want to change, and then click **Edit**.</span></span>
4. <span data-ttu-id="00061-121">場所情報を更新して、[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="00061-121">Update the place information, and then click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="00061-122">PowerShell を使用する場合</span><span class="sxs-lookup"><span data-stu-id="00061-122">Using PowerShell</span></span>

<span data-ttu-id="00061-123">「 [Set-Csonlin¥ location](https://docs.microsoft.com/powershell/module/skype/set-csonlinelislocation)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="00061-123">See [Set-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/set-csonlinelislocation).</span></span>
    
## <a name="remove-a-place-from-an-emergency-location"></a><span data-ttu-id="00061-124">緊急対応の場所から場所を削除する</span><span class="sxs-lookup"><span data-stu-id="00061-124">Remove a place from an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="00061-125">Microsoft Teams 管理センターの使用</span><span class="sxs-lookup"><span data-stu-id="00061-125">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="00061-126">Microsoft Teams 管理センターの左のナビゲーションで、[**地域**の  >  **緊急対応の住所**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="00061-126">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="00061-127">リストで、場所を削除する場所の名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="00061-127">In the list, click the name of the location for which you want to remove a place.</span></span>
3. <span data-ttu-id="00061-128">[**場所**] タブで削除する場所を選択し、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="00061-128">On the **Places** tab, select the place you want to remove, and then click **Delete**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="00061-129">PowerShell を使用する場合</span><span class="sxs-lookup"><span data-stu-id="00061-129">Using PowerShell</span></span>

<span data-ttu-id="00061-130">「 [Csonlin¥ location の削除」を](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelislocation)参照してください。</span><span class="sxs-lookup"><span data-stu-id="00061-130">See [Remove-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelislocation).</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="00061-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="00061-131">Related topics</span></span>

- [<span data-ttu-id="00061-132">組織の緊急対応の場所の位置情報を追加、変更、削除する</span><span class="sxs-lookup"><span data-stu-id="00061-132">Add, change, or remove a place for an emergency location in your organization</span></span>](add-change-remove-emergency-place-organization.md)
- [<span data-ttu-id="00061-133">組織の電話番号を管理する</span><span class="sxs-lookup"><span data-stu-id="00061-133">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)
- [<span data-ttu-id="00061-134">緊急通話の利用条件</span><span class="sxs-lookup"><span data-stu-id="00061-134">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)
