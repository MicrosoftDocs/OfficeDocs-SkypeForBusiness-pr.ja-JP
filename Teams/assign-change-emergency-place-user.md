---
title: ユーザー用の緊急対応の場所の場所を割り当てる、変更する
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
description: この記事では、組織内のユーザーの緊急対応の場所を割り当てる、または変更する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d5b13cf5d4b4a0cf22077318e3c2c2196840f66e
ms.sourcegitcommit: 000515147632c6278bcda4505a1038014dda8e2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2020
ms.locfileid: "44232468"
---
# <a name="assign-or-change-the-place-for-an-emergency-location-for-a-user"></a><span data-ttu-id="e931b-103">ユーザーの緊急対応の場所を割り当てまたは変更する</span><span class="sxs-lookup"><span data-stu-id="e931b-103">Assign or change the place for an emergency location for a user</span></span>

<span data-ttu-id="e931b-104">電話番号をユーザーに割り当てるときは、有効な電話番号ごとに対応する緊急対応の場所が必要です。</span><span class="sxs-lookup"><span data-stu-id="e931b-104">Each active phone number must have an associated emergency location when you assign the phone number to a user.</span></span> <span data-ttu-id="e931b-105">(住所は、Office 365 で電話番号を取得する場合、または電話番号を移行する場合に関連付けます)。緊急対応の場所に番号を関連付ける場合は、場所を追加して、物理的な場所に正確な位置情報を提供することもできます。</span><span class="sxs-lookup"><span data-stu-id="e931b-105">(You associate the address when you get a phone number in Office 365 or when you transfer a phone number.) When you associate the number with an emergency location, you can also add a place to provide a more exact location within a physical location.</span></span> <span data-ttu-id="e931b-106">場所には、ユーザーが配置されているフロア、建物、またはオフィスの番号を指定できます。</span><span class="sxs-lookup"><span data-stu-id="e931b-106">A place can be the floor, building wing, or office number where the user is located.</span></span> <span data-ttu-id="e931b-107">特定の緊急対応の場所には無制限の場所を含めることができます。また、ユーザーが別の office または建物に移動すると、その場所を変更できます。</span><span class="sxs-lookup"><span data-stu-id="e931b-107">You can have an unlimited number of places for a given emergency location, and you can change the place if the user moves to a different office or building.</span></span> <span data-ttu-id="e931b-108">たとえば、ユーザーがフロア34から床35に移動した場合です。</span><span class="sxs-lookup"><span data-stu-id="e931b-108">For example, if the user moves from floor 34 to floor 35.</span></span>
  
<span data-ttu-id="e931b-109">通話プランの取得方法と料金については、「 [Teams アドオンライセンス](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e931b-109">To learn how to get Calling Plans and how much they cost, see [Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
  
<span data-ttu-id="e931b-110">Microsoft Teams 管理センターまたは PowerShell を使用して、ユーザーの緊急対応の場所を割り当てたり、変更したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="e931b-110">You can assign or change the place for an emergency location for a user in the Microsoft Teams admin center or by using PowerShell.</span></span>

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="e931b-111">Microsoft Teams 管理センターの使用</span><span class="sxs-lookup"><span data-stu-id="e931b-111">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="e931b-112">Microsoft Teams 管理センターの左のナビゲーションで **、[**  >  **電話番号**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e931b-112">In the left navigation of the Microsoft Teams admin center, click **Voice** > **Phone numbers**.</span></span>

2. <span data-ttu-id="e931b-113">[**電話番号**] ページで、一覧からユーザー番号を選び、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e931b-113">On the **Phone numbers** page, select a user number in the list, and then click **Edit**.</span></span>

3. <span data-ttu-id="e931b-114">[**編集**] ウィンドウの [**緊急**対応の場所] で、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="e931b-114">On the **Edit** pane, under **Emergency location**, do one of the following:</span></span>

    - <span data-ttu-id="e931b-115">場所を割り当てるには、場所または場所を検索して、検索結果内の場所を選びます。</span><span class="sxs-lookup"><span data-stu-id="e931b-115">To assign a place, search for the location or place, and then select the place in the search results.</span></span>

    - <span data-ttu-id="e931b-116">ユーザーに既に割り当てられている場所を変更するには、[ **X** ] をクリックして、既存の場所を削除してから、割り当てる場所を検索して選択します。</span><span class="sxs-lookup"><span data-stu-id="e931b-116">To change the place that's already assigned to the user, click **X** to remove the existing location and place, search for and then select the place you want to assign.</span></span>

4. <span data-ttu-id="e931b-117">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e931b-117">Click **Save**.</span></span>

## <a name="using-powershell"></a><span data-ttu-id="e931b-118">PowerShell を使用する場合</span><span class="sxs-lookup"><span data-stu-id="e931b-118">Using PowerShell</span></span>

<span data-ttu-id="e931b-119">「 [Set-Csonlin¥ location](https://docs.microsoft.com/powershell/module/skype/set-csonlinelislocation)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e931b-119">See [Set-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/set-csonlinelislocation).</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="e931b-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="e931b-120">Related topics</span></span>

- [<span data-ttu-id="e931b-121">緊急通話を管理する</span><span class="sxs-lookup"><span data-stu-id="e931b-121">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="e931b-122">組織の緊急対応の場所を追加、変更、削除する</span><span class="sxs-lookup"><span data-stu-id="e931b-122">Add, change, or remove an emergency location for your organization</span></span>](add-change-remove-emergency-location-organization.md)
- [<span data-ttu-id="e931b-123">組織の緊急対応の場所の位置情報を追加、変更、削除する</span><span class="sxs-lookup"><span data-stu-id="e931b-123">Add, change, or remove a place for an emergency location in your organization</span></span>](add-change-remove-emergency-place-organization.md)
- [<span data-ttu-id="e931b-124">ユーザーの緊急対応の場所を割り当てたり変更したりする</span><span class="sxs-lookup"><span data-stu-id="e931b-124">Assign or change an emergency location for a user</span></span>](assign-change-emergency-location-user.md)
- [<span data-ttu-id="e931b-125">組織の電話番号を管理する</span><span class="sxs-lookup"><span data-stu-id="e931b-125">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)
- [<span data-ttu-id="e931b-126">緊急通話の利用条件</span><span class="sxs-lookup"><span data-stu-id="e931b-126">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)
