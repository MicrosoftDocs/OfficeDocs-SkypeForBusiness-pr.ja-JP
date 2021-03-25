---
title: ユーザーの緊急対応の場所の割り当て、変更
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
description: この記事では、組織内のユーザーに対して緊急対応の場所を割り当てる方法または場所を変更する方法について学習します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ff328f07a69676a4dbaf1c1370d9e225e9d67810
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120829"
---
# <a name="assign-or-change-the-place-for-an-emergency-location-for-a-user"></a><span data-ttu-id="4c807-103">ユーザーの緊急対応の場所を割り当てる、または変更する</span><span class="sxs-lookup"><span data-stu-id="4c807-103">Assign or change the place for an emergency location for a user</span></span>

<span data-ttu-id="4c807-104">ユーザーに電話番号を割り当てると、アクティブな各電話番号に緊急対応の場所が関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c807-104">Each active phone number must have an associated emergency location when you assign the phone number to a user.</span></span> <span data-ttu-id="4c807-105">(Office 365 で電話番号を取得した場合、または電話番号を転送するときに、住所を関連付ける。緊急対応の場所に番号を関連付ける場合は、物理的な場所内のより正確な場所を提供する場所を追加できます。</span><span class="sxs-lookup"><span data-stu-id="4c807-105">(You associate the address when you get a phone number in Office 365 or when you transfer a phone number.) When you associate the number with an emergency location, you can also add a place to provide a more exact location within a physical location.</span></span> <span data-ttu-id="4c807-106">場所には、ユーザーが配置されているフロア、ビルの棟、オフィス番号を指定できます。</span><span class="sxs-lookup"><span data-stu-id="4c807-106">A place can be the floor, building wing, or office number where the user is located.</span></span> <span data-ttu-id="4c807-107">特定の緊急対応の場所の場所の数に制限はありません。また、ユーザーが別のオフィスや建物に移動した場合に場所を変更できます。</span><span class="sxs-lookup"><span data-stu-id="4c807-107">You can have an unlimited number of places for a given emergency location, and you can change the place if the user moves to a different office or building.</span></span> <span data-ttu-id="4c807-108">たとえば、ユーザーが 34 階から 35 階に移動する場合などです。</span><span class="sxs-lookup"><span data-stu-id="4c807-108">For example, if the user moves from floor 34 to floor 35.</span></span>
  
<span data-ttu-id="4c807-109">通話プランを取得する方法と料金については、「Teams アドオン ライセンス [」を参照してください](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="4c807-109">To learn how to get Calling Plans and how much they cost, see [Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
  
<span data-ttu-id="4c807-110">Microsoft Teams 管理センターで、または PowerShell を使用して、ユーザーの緊急対応の場所を割り当てまたは変更できます。</span><span class="sxs-lookup"><span data-stu-id="4c807-110">You can assign or change the place for an emergency location for a user in the Microsoft Teams admin center or by using PowerShell.</span></span>

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="4c807-111">Microsoft Teams 管理センターの使用</span><span class="sxs-lookup"><span data-stu-id="4c807-111">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="4c807-112">Microsoft Teams 管理センターの左側のナビゲーションで、[**音声電話番号]** を  >  **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="4c807-112">In the left navigation of the Microsoft Teams admin center, click **Voice** > **Phone numbers**.</span></span>

2. <span data-ttu-id="4c807-113">[電話番号 **] ページで** 、[番号] タブを **クリック** し、一覧からユーザー番号を選び、[編集] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="4c807-113">On the **Phone numbers** page, click the **Numbers** tab, select a user number in the list, and then click **Edit**.</span></span>

3. <span data-ttu-id="4c807-114">[編集] **ウィンドウの** [緊急対応の **場所] で、** 次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="4c807-114">On the **Edit** pane, under **Emergency location**, do one of the following:</span></span>

    - <span data-ttu-id="4c807-115">場所を割り当てるには、場所または場所を検索し、検索結果で場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="4c807-115">To assign a place, search for the location or place, and then select the place in the search results.</span></span>

    - <span data-ttu-id="4c807-116">ユーザーに既に割り当てられている場所を変更するには **、[X]** をクリックして既存の場所を削除し、割り当てる場所を検索して選択します。</span><span class="sxs-lookup"><span data-stu-id="4c807-116">To change the place that's already assigned to the user, click **X** to remove the existing location and place, search for and then select the place you want to assign.</span></span>

4. <span data-ttu-id="4c807-117">電話番号情報を含むメールをユーザーに送信するかどうかに応じて、電話番号情報を含むメール ユーザーをオフまたは **オンにします**。</span><span class="sxs-lookup"><span data-stu-id="4c807-117">Depending on whether you want to send an email to the user with their phone number information, turn off or turn on **Email user with telephone number information**.</span></span> <span data-ttu-id="4c807-118">既定では、オンになっています。</span><span class="sxs-lookup"><span data-stu-id="4c807-118">By default, this is on.</span></span>

5. <span data-ttu-id="4c807-119">[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4c807-119">Click **Apply**.</span></span>

## <a name="using-powershell"></a><span data-ttu-id="4c807-120">PowerShell の使用</span><span class="sxs-lookup"><span data-stu-id="4c807-120">Using PowerShell</span></span>

<span data-ttu-id="4c807-121">[「Set-CsOnlineLisLocation」を参照してください](/powershell/module/skype/set-csonlinelislocation)。</span><span class="sxs-lookup"><span data-stu-id="4c807-121">See [Set-CsOnlineLisLocation](/powershell/module/skype/set-csonlinelislocation).</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="4c807-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="4c807-122">Related topics</span></span>

- [<span data-ttu-id="4c807-123">緊急通話を管理する</span><span class="sxs-lookup"><span data-stu-id="4c807-123">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="4c807-124">組織の緊急対応の場所を追加、変更、削除する</span><span class="sxs-lookup"><span data-stu-id="4c807-124">Add, change, or remove an emergency location for your organization</span></span>](add-change-remove-emergency-location-organization.md)
- [<span data-ttu-id="4c807-125">組織の緊急対応の場所の位置情報を追加、変更、削除する</span><span class="sxs-lookup"><span data-stu-id="4c807-125">Add, change, or remove a place for an emergency location in your organization</span></span>](add-change-remove-emergency-place-organization.md)
- [<span data-ttu-id="4c807-126">ユーザーの緊急対応の場所を割り当てたり変更したりする</span><span class="sxs-lookup"><span data-stu-id="4c807-126">Assign or change an emergency location for a user</span></span>](assign-change-emergency-location-user.md)
- [<span data-ttu-id="4c807-127">組織の電話番号を管理する</span><span class="sxs-lookup"><span data-stu-id="4c807-127">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)
- [<span data-ttu-id="4c807-128">緊急通話の利用条件</span><span class="sxs-lookup"><span data-stu-id="4c807-128">Emergency calling terms and conditions</span></span>](./emergency-calling-terms-and-conditions.md)