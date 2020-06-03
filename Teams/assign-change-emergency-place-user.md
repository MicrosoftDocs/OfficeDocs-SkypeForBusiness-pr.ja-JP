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
ms.openlocfilehash: 35f7dfe6572b7ef3dc76b6c224d206e2ee4f23a2
ms.sourcegitcommit: d8e05e66311725f8ff6d28011355129baeb305b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/03/2020
ms.locfileid: "44539514"
---
# <a name="assign-or-change-the-place-for-an-emergency-location-for-a-user"></a><span data-ttu-id="4801f-103">ユーザーの緊急対応の場所を割り当てまたは変更する</span><span class="sxs-lookup"><span data-stu-id="4801f-103">Assign or change the place for an emergency location for a user</span></span>

<span data-ttu-id="4801f-104">電話番号をユーザーに割り当てるときは、有効な電話番号ごとに対応する緊急対応の場所が必要です。</span><span class="sxs-lookup"><span data-stu-id="4801f-104">Each active phone number must have an associated emergency location when you assign the phone number to a user.</span></span> <span data-ttu-id="4801f-105">(住所は、Office 365 で電話番号を取得する場合、または電話番号を移行する場合に関連付けます)。緊急対応の場所に番号を関連付ける場合は、場所を追加して、物理的な場所に正確な位置情報を提供することもできます。</span><span class="sxs-lookup"><span data-stu-id="4801f-105">(You associate the address when you get a phone number in Office 365 or when you transfer a phone number.) When you associate the number with an emergency location, you can also add a place to provide a more exact location within a physical location.</span></span> <span data-ttu-id="4801f-106">場所には、ユーザーが配置されているフロア、建物、またはオフィスの番号を指定できます。</span><span class="sxs-lookup"><span data-stu-id="4801f-106">A place can be the floor, building wing, or office number where the user is located.</span></span> <span data-ttu-id="4801f-107">特定の緊急対応の場所には無制限の場所を含めることができます。また、ユーザーが別の office または建物に移動すると、その場所を変更できます。</span><span class="sxs-lookup"><span data-stu-id="4801f-107">You can have an unlimited number of places for a given emergency location, and you can change the place if the user moves to a different office or building.</span></span> <span data-ttu-id="4801f-108">たとえば、ユーザーがフロア34から床35に移動した場合です。</span><span class="sxs-lookup"><span data-stu-id="4801f-108">For example, if the user moves from floor 34 to floor 35.</span></span>
  
<span data-ttu-id="4801f-109">通話プランの取得方法と料金については、「 [Teams アドオンライセンス](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4801f-109">To learn how to get Calling Plans and how much they cost, see [Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
  
<span data-ttu-id="4801f-110">Microsoft Teams 管理センターまたは PowerShell を使用して、ユーザーの緊急対応の場所を割り当てたり、変更したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="4801f-110">You can assign or change the place for an emergency location for a user in the Microsoft Teams admin center or by using PowerShell.</span></span>

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="4801f-111">Microsoft Teams 管理センターの使用</span><span class="sxs-lookup"><span data-stu-id="4801f-111">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="4801f-112">Microsoft Teams 管理センターの左のナビゲーションで **、[**  >  **電話番号**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4801f-112">In the left navigation of the Microsoft Teams admin center, click **Voice** > **Phone numbers**.</span></span>

2. <span data-ttu-id="4801f-113">[**電話番号**] ページで、[**数値**] タブをクリックし、一覧でユーザー番号を選択し、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4801f-113">On the **Phone numbers** page, click the **Numbers** tab, select a user number in the list, and then click **Edit**.</span></span>

3. <span data-ttu-id="4801f-114">[**編集**] ウィンドウの [**緊急**対応の場所] で、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="4801f-114">On the **Edit** pane, under **Emergency location**, do one of the following:</span></span>

    - <span data-ttu-id="4801f-115">場所を割り当てるには、場所または場所を検索して、検索結果内の場所を選びます。</span><span class="sxs-lookup"><span data-stu-id="4801f-115">To assign a place, search for the location or place, and then select the place in the search results.</span></span>

    - <span data-ttu-id="4801f-116">ユーザーに既に割り当てられている場所を変更するには、[ **X** ] をクリックして、既存の場所を削除してから、割り当てる場所を検索して選択します。</span><span class="sxs-lookup"><span data-stu-id="4801f-116">To change the place that's already assigned to the user, click **X** to remove the existing location and place, search for and then select the place you want to assign.</span></span>

4. <span data-ttu-id="4801f-117">電話番号情報を使用してユーザーにメールを送信するかどうかに応じて、**電話番号情報を含むメールユーザー**を無効にするか、有効にします。</span><span class="sxs-lookup"><span data-stu-id="4801f-117">Depending on whether you want to send an email to the user with their phone number information, turn off or turn on **Email user with telephone number information**.</span></span> <span data-ttu-id="4801f-118">既定では、これはオンになっています。</span><span class="sxs-lookup"><span data-stu-id="4801f-118">By default, this is on.</span></span>

5. <span data-ttu-id="4801f-119">[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4801f-119">Click **Apply**.</span></span>

## <a name="using-powershell"></a><span data-ttu-id="4801f-120">PowerShell を使用する場合</span><span class="sxs-lookup"><span data-stu-id="4801f-120">Using PowerShell</span></span>

<span data-ttu-id="4801f-121">「 [Set-Csonlin¥ location](https://docs.microsoft.com/powershell/module/skype/set-csonlinelislocation)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4801f-121">See [Set-CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/set-csonlinelislocation).</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="4801f-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="4801f-122">Related topics</span></span>

- [<span data-ttu-id="4801f-123">緊急通話を管理する</span><span class="sxs-lookup"><span data-stu-id="4801f-123">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="4801f-124">組織の緊急対応の場所を追加、変更、削除する</span><span class="sxs-lookup"><span data-stu-id="4801f-124">Add, change, or remove an emergency location for your organization</span></span>](add-change-remove-emergency-location-organization.md)
- [<span data-ttu-id="4801f-125">組織の緊急対応の場所の位置情報を追加、変更、削除する</span><span class="sxs-lookup"><span data-stu-id="4801f-125">Add, change, or remove a place for an emergency location in your organization</span></span>](add-change-remove-emergency-place-organization.md)
- [<span data-ttu-id="4801f-126">ユーザーの緊急対応の場所を割り当てたり変更したりする</span><span class="sxs-lookup"><span data-stu-id="4801f-126">Assign or change an emergency location for a user</span></span>](assign-change-emergency-location-user.md)
- [<span data-ttu-id="4801f-127">組織の電話番号を管理する</span><span class="sxs-lookup"><span data-stu-id="4801f-127">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)
- [<span data-ttu-id="4801f-128">緊急通話の利用条件</span><span class="sxs-lookup"><span data-stu-id="4801f-128">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)
