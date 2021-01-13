---
title: 緊急対応の場所を追加、変更、削除する
author: cichur
ms.author: v-cichur
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
ms.openlocfilehash: d390113b30558b94fadab695731b8c08b4c01ace
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806277"
---
# <a name="add-change-or-remove-a-place-for-an-emergency-location-in-your-organization"></a><span data-ttu-id="9610c-103">組織の緊急対応の場所の位置情報を追加、変更、削除する</span><span class="sxs-lookup"><span data-stu-id="9610c-103">Add, change, or remove a place for an emergency location in your organization</span></span>

<span data-ttu-id="9610c-104">組織の物理的な場所の数に応じて、建物、フロア、オフィスの場所を追加して、より具体的な緊急対応の場所を作成できます。</span><span class="sxs-lookup"><span data-stu-id="9610c-104">Depending on the number of physical locations in your organization, you can add places for buildings, floors, and offices to create a more specific emergency location.</span></span> <span data-ttu-id="9610c-105">詳細 [については、「緊急通話を管理する](what-are-emergency-locations-addresses-and-call-routing.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9610c-105">See [Manage emergency calling](what-are-emergency-locations-addresses-and-call-routing.md) for more information.</span></span>
  
<span data-ttu-id="9610c-106">通話プランを取得する方法と料金については、「Teams アドオン ライセンス [」を参照してください](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="9610c-106">To learn how to get a Calling Plan and how much they cost, see [Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

<span data-ttu-id="9610c-107">組織の緊急対応の場所は、Microsoft Teams 管理センターまたは PowerShell を使用して管理します。</span><span class="sxs-lookup"><span data-stu-id="9610c-107">You manage emergency locations for your organization in the Microsoft Teams admin center or by using PowerShell.</span></span>
  
## <a name="add-a-place-to-an-emergency-location"></a><span data-ttu-id="9610c-108">緊急対応の場所に場所を追加する</span><span class="sxs-lookup"><span data-stu-id="9610c-108">Add a place to an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="9610c-109">Microsoft Teams 管理センターの使用</span><span class="sxs-lookup"><span data-stu-id="9610c-109">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="9610c-110">Microsoft Teams 管理センターの左側のナビゲーションで、[場所の緊急対応の住所 **]**  >  **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="9610c-110">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="9610c-111">一覧で、場所を追加する場所の名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9610c-111">In the list, click the name of the location for which you want to add a place.</span></span>
3. <span data-ttu-id="9610c-112">[場所] **タブの [** 追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="9610c-112">On the **Places** tab, click **Add**.</span></span>
4. <span data-ttu-id="9610c-113">場所名を入力し、[適用] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="9610c-113">Enter a place name, and then click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="9610c-114">PowerShell の使用</span><span class="sxs-lookup"><span data-stu-id="9610c-114">Using PowerShell</span></span>

<span data-ttu-id="9610c-115">[New-CsOnlineLisLocation を参照してください](https://docs.microsoft.com/powershell/module/skype/new-csonlinelislocation)。</span><span class="sxs-lookup"><span data-stu-id="9610c-115">See [New-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/new-csonlinelislocation).</span></span>
    
## <a name="change-a-place-for-an-emergency-location"></a><span data-ttu-id="9610c-116">緊急対応の場所を変更する</span><span class="sxs-lookup"><span data-stu-id="9610c-116">Change a place for an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="9610c-117">Microsoft Teams 管理センターの使用</span><span class="sxs-lookup"><span data-stu-id="9610c-117">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="9610c-118">Microsoft Teams 管理センターの左側のナビゲーションで、[場所の緊急対応の住所 **]**  >  **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="9610c-118">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="9610c-119">一覧で、場所を変更する場所の名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9610c-119">In the list, click the name of the location for which you want to change a place.</span></span>
3. <span data-ttu-id="9610c-120">[場所 **] タブ** で、変更する場所を選び、[編集] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="9610c-120">On the **Places** tab, select the place you want to change, and then click **Edit**.</span></span>
4. <span data-ttu-id="9610c-121">場所の情報を更新し、[適用] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="9610c-121">Update the place information, and then click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="9610c-122">PowerShell の使用</span><span class="sxs-lookup"><span data-stu-id="9610c-122">Using PowerShell</span></span>

<span data-ttu-id="9610c-123">[「Set-CsOnlineLisLocation」を参照してください](https://docs.microsoft.com/powershell/module/skype/set-csonlinelislocation)。</span><span class="sxs-lookup"><span data-stu-id="9610c-123">See [Set-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/set-csonlinelislocation).</span></span>
    
## <a name="remove-a-place-from-an-emergency-location"></a><span data-ttu-id="9610c-124">緊急対応の場所から場所を削除する</span><span class="sxs-lookup"><span data-stu-id="9610c-124">Remove a place from an emergency location</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="9610c-125">Microsoft Teams 管理センターの使用</span><span class="sxs-lookup"><span data-stu-id="9610c-125">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="9610c-126">Microsoft Teams 管理センターの左側のナビゲーションで、[場所の緊急対応の住所 **]**  >  **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="9610c-126">In the left navigation of the Microsoft Teams admin center, click **Locations** > **Emergency addresses**.</span></span>
2. <span data-ttu-id="9610c-127">一覧で、場所を削除する場所の名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9610c-127">In the list, click the name of the location for which you want to remove a place.</span></span>
3. <span data-ttu-id="9610c-128">[場所 **] タブ** で、削除する場所を選び、[削除] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="9610c-128">On the **Places** tab, select the place you want to remove, and then click **Delete**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="9610c-129">PowerShell の使用</span><span class="sxs-lookup"><span data-stu-id="9610c-129">Using PowerShell</span></span>

<span data-ttu-id="9610c-130">[Remove-CsOnlineLisLocation を参照してください](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelislocation)。</span><span class="sxs-lookup"><span data-stu-id="9610c-130">See [Remove-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelislocation).</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="9610c-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="9610c-131">Related topics</span></span>

- [<span data-ttu-id="9610c-132">組織の緊急対応の場所の位置情報を追加、変更、削除する</span><span class="sxs-lookup"><span data-stu-id="9610c-132">Add, change, or remove a place for an emergency location in your organization</span></span>](add-change-remove-emergency-place-organization.md)
- [<span data-ttu-id="9610c-133">組織の電話番号を管理する</span><span class="sxs-lookup"><span data-stu-id="9610c-133">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)
- [<span data-ttu-id="9610c-134">緊急通話の利用条件</span><span class="sxs-lookup"><span data-stu-id="9610c-134">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)
