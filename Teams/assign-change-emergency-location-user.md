---
title: ユーザーの緊急対応の場所を割り当てたり変更したりする
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
description: この記事では、組織内のユーザーの緊急対応の場所を割り当てまたは変更する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 096e2dead1ede4f9769dafd85dfac23d6c44f399
ms.sourcegitcommit: 000515147632c6278bcda4505a1038014dda8e2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "44232478"
---
# <a name="assign-or-change-an-emergency-location-for-a-user"></a><span data-ttu-id="a720b-103">ユーザーの緊急対応の場所を割り当てたり変更したりする</span><span class="sxs-lookup"><span data-stu-id="a720b-103">Assign or change an emergency location for a user</span></span>

<span data-ttu-id="a720b-104">通話プランを設定するときは、各電話番号またはユーザーに緊急対応の場所を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="a720b-104">When you're setting up Calling Plans, you need to assign an emergency location to each phone number or user.</span></span> <span data-ttu-id="a720b-105">ヨーロッパの国では、Office 365 から、または電話番号を Office 365 に移行したときに、緊急対応の場所が電話番号と関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="a720b-105">In European countries, the emergency location is associated with the phone number when you get it from Office 365 or when you transfer a phone number over to Office 365.</span></span> <span data-ttu-id="a720b-106">米国では、ユーザーに割り当てられた緊急対応の場所が電話番号と関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="a720b-106">In the United States, the emergency location is associated with the phone number when it's assigned to the user.</span></span> <span data-ttu-id="a720b-107">割り当てられたユーザーが新しい場所に移動した場合は、緊急対応の住所を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="a720b-107">The emergency address can be changed if the user that it's assigned to moves to a new location.</span></span> <span data-ttu-id="a720b-108">緊急対応の住所と場所の詳細については、「[緊急通話を管理](what-are-emergency-locations-addresses-and-call-routing.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a720b-108">For more about emergency addresses and locations, see [Manage emergency calling](what-are-emergency-locations-addresses-and-call-routing.md).</span></span>
  
<span data-ttu-id="a720b-109">通話プランの取得方法とコストについては、「Teams の[アドオンライセンス](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a720b-109">To learn how to get a Calling Plan and how much they cost, see [Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

<span data-ttu-id="a720b-110">Microsoft Teams 管理センターまたは PowerShell を使用して、ユーザーの緊急対応の場所を割り当てたり、変更したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="a720b-110">You can assign or change an emergency location for a user in the Microsoft Teams admin center or by using PowerShell.</span></span>

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="a720b-111">Microsoft Teams 管理センターの使用</span><span class="sxs-lookup"><span data-stu-id="a720b-111">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="a720b-112">Microsoft Teams 管理センターの左のナビゲーションで **、[**  >  **電話番号**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a720b-112">In the left navigation of the Microsoft Teams admin center, click **Voice** > **Phone numbers**.</span></span>

2. <span data-ttu-id="a720b-113">[**電話番号**] ページで、一覧からユーザー番号を選び、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a720b-113">On the **Phone numbers** page, select a user number in the list, and then click **Edit**.</span></span>

3. <span data-ttu-id="a720b-114">[**編集**] ウィンドウの [**緊急**対応の場所] で、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="a720b-114">On the **Edit** pane, under **Emergency location**, do one of the following:</span></span>

   - <span data-ttu-id="a720b-115">緊急対応の場所を割り当てるには、緊急対応の場所を検索して選択します。</span><span class="sxs-lookup"><span data-stu-id="a720b-115">To assign an emergency location, search for, and select an emergency location.</span></span>

   - <span data-ttu-id="a720b-116">既にユーザーに割り当てられている緊急対応の場所を変更するには、[ **X** ] をクリックして既存の場所を削除し、割り当てる場所を検索して選択します。</span><span class="sxs-lookup"><span data-stu-id="a720b-116">To change the emergency location that's already assigned to the user, click **X** to remove the existing location, and then search for and select the location you want to assign.</span></span>

4. <span data-ttu-id="a720b-117">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a720b-117">Click **Save**.</span></span>

## <a name="using-powershell"></a><span data-ttu-id="a720b-118">PowerShell を使用する場合</span><span class="sxs-lookup"><span data-stu-id="a720b-118">Using PowerShell</span></span>

<span data-ttu-id="a720b-119">「 [Set-CsOnlineVoiceUser](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a720b-119">See [Set-CsOnlineVoiceUser](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser).</span></span> 

    
## <a name="related-topics"></a><span data-ttu-id="a720b-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="a720b-120">Related topics</span></span>

- [<span data-ttu-id="a720b-121">緊急通話を管理する</span><span class="sxs-lookup"><span data-stu-id="a720b-121">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="a720b-122">組織の緊急対応の場所を追加、変更、削除する</span><span class="sxs-lookup"><span data-stu-id="a720b-122">Add, change, or remove an emergency location for your organization</span></span>](add-change-remove-emergency-location-organization.md)
- [<span data-ttu-id="a720b-123">組織の緊急対応の場所の位置情報を追加、変更、削除する</span><span class="sxs-lookup"><span data-stu-id="a720b-123">Add, change, or remove a place for an emergency location in your organization</span></span>](add-change-remove-emergency-place-organization.md)
- [<span data-ttu-id="a720b-124">ユーザーの緊急対応の場所の位置情報を割り当てたり変更したりする</span><span class="sxs-lookup"><span data-stu-id="a720b-124">Assign or change a place for an emergency location for a user</span></span>](assign-change-emergency-place-user.md)
- [<span data-ttu-id="a720b-125">組織の電話番号を管理する</span><span class="sxs-lookup"><span data-stu-id="a720b-125">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)
- [<span data-ttu-id="a720b-126">緊急通話の利用条件</span><span class="sxs-lookup"><span data-stu-id="a720b-126">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)
- [<span data-ttu-id="a720b-127">Teams での PowerShell の概要</span><span class="sxs-lookup"><span data-stu-id="a720b-127">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
