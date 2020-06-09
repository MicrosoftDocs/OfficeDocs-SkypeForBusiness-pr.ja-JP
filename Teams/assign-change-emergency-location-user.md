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
ms.openlocfilehash: 450fe848052af1e331964da3d7b695daf0f1567a
ms.sourcegitcommit: fa567451f8f7af6d915e33809d88f26b415db54c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "44610996"
---
# <a name="assign-or-change-an-emergency-location-for-a-user"></a><span data-ttu-id="a78a3-103">ユーザーの緊急対応の場所を割り当てたり変更したりする</span><span class="sxs-lookup"><span data-stu-id="a78a3-103">Assign or change an emergency location for a user</span></span>

<span data-ttu-id="a78a3-104">通話プランを設定するときは、各電話番号またはユーザーに緊急対応の場所を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="a78a3-104">When you're setting up Calling Plans, you need to assign an emergency location to each phone number or user.</span></span> <span data-ttu-id="a78a3-105">ヨーロッパの国では、Microsoft 365 または Office 365 から電話番号を取得したとき、または Microsoft 365 または Office 365 に電話番号を移行したときに、緊急対応の場所が電話番号と関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="a78a3-105">In European countries, the emergency location is associated with the phone number when you get it from Microsoft 365 or Office 365 or when you transfer a phone number over to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="a78a3-106">米国では、ユーザーに割り当てられた緊急対応の場所が電話番号と関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="a78a3-106">In the United States, the emergency location is associated with the phone number when it's assigned to the user.</span></span> <span data-ttu-id="a78a3-107">割り当てられたユーザーが新しい場所に移動した場合は、緊急対応の住所を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="a78a3-107">The emergency address can be changed if the user that it's assigned to moves to a new location.</span></span> <span data-ttu-id="a78a3-108">緊急対応の住所と場所の詳細については、「緊急対応の[場所、場所、通話ルーティング](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing)の概要」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a78a3-108">For more about emergency addresses and locations, see [What are emergency locations, places, and call routing?](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing).</span></span>
  
<span data-ttu-id="a78a3-109">通話プランの取得方法とコストについては、「Teams の[アドオンライセンス](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a78a3-109">To learn how to get a Calling Plans and how much they cost, see [Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
  
<span data-ttu-id="a78a3-110">Microsoft Teams 管理センターまたは PowerShell を使用して、ユーザーの緊急対応の場所を割り当てたり、変更したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="a78a3-110">You can assign or change an emergency location for a user in the Microsoft Teams admin center or by using PowerShell.</span></span>

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="a78a3-111">Microsoft Teams 管理センターの使用</span><span class="sxs-lookup"><span data-stu-id="a78a3-111">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="a78a3-112">Microsoft Teams 管理センターの左のナビゲーションで **、[**  >  **電話番号**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a78a3-112">In the left navigation of the Microsoft Teams admin center, click **Voice** > **Phone numbers**.</span></span>

2. <span data-ttu-id="a78a3-113">[**電話番号**] ページで、[**数値**] タブをクリックし、一覧でユーザー番号を選択し、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a78a3-113">On the **Phone numbers** page, click the **Numbers** tab, select a user number in the list, and then click **Edit**.</span></span>

3. <span data-ttu-id="a78a3-114">[**編集**] ウィンドウの [**緊急**対応の場所] で、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="a78a3-114">On the **Edit** pane, under **Emergency location**, do one of the following:</span></span>

   - <span data-ttu-id="a78a3-115">緊急対応の場所を割り当てるには、緊急対応の場所を検索して選択します。</span><span class="sxs-lookup"><span data-stu-id="a78a3-115">To assign an emergency location, search for, and select an emergency location.</span></span>

   - <span data-ttu-id="a78a3-116">既にユーザーに割り当てられている緊急対応の場所を変更するには、[ **X** ] をクリックして既存の場所を削除し、割り当てる場所を検索して選択します。</span><span class="sxs-lookup"><span data-stu-id="a78a3-116">To change the emergency location that's already assigned to the user, click **X** to remove the existing location, and then search for and select the location you want to assign.</span></span>

4. <span data-ttu-id="a78a3-117">電話番号情報を使用してユーザーにメールを送信するかどうかに応じて、**電話番号情報を含むメールユーザー**を無効にするか、有効にします。</span><span class="sxs-lookup"><span data-stu-id="a78a3-117">Depending on whether you want to send an email to the user with their phone number information, turn off or turn on **Email user with telephone number information**.</span></span> <span data-ttu-id="a78a3-118">既定では、これはオンになっています。</span><span class="sxs-lookup"><span data-stu-id="a78a3-118">By default, this is on.</span></span>

5. <span data-ttu-id="a78a3-119">[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a78a3-119">Click **Apply**.</span></span>

## <a name="using-powershell"></a><span data-ttu-id="a78a3-120">PowerShell を使用する場合</span><span class="sxs-lookup"><span data-stu-id="a78a3-120">Using PowerShell</span></span>

<span data-ttu-id="a78a3-121">「 [Set-CsOnlineVoiceUser](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a78a3-121">See [Set-CsOnlineVoiceUser](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser).</span></span> 

    
## <a name="related-topics"></a><span data-ttu-id="a78a3-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="a78a3-122">Related topics</span></span>

- [<span data-ttu-id="a78a3-123">緊急通話を管理する</span><span class="sxs-lookup"><span data-stu-id="a78a3-123">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="a78a3-124">組織の緊急対応の場所を追加、変更、削除する</span><span class="sxs-lookup"><span data-stu-id="a78a3-124">Add, change, or remove an emergency location for your organization</span></span>](add-change-remove-emergency-location-organization.md)
- [<span data-ttu-id="a78a3-125">組織の緊急対応の場所の位置情報を追加、変更、削除する</span><span class="sxs-lookup"><span data-stu-id="a78a3-125">Add, change, or remove a place for an emergency location in your organization</span></span>](add-change-remove-emergency-place-organization.md)
- [<span data-ttu-id="a78a3-126">ユーザーの緊急対応の場所の位置情報を割り当てたり変更したりする</span><span class="sxs-lookup"><span data-stu-id="a78a3-126">Assign or change a place for an emergency location for a user</span></span>](assign-change-emergency-place-user.md)
- [<span data-ttu-id="a78a3-127">組織の電話番号を管理する</span><span class="sxs-lookup"><span data-stu-id="a78a3-127">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)
- [<span data-ttu-id="a78a3-128">緊急通話の利用条件</span><span class="sxs-lookup"><span data-stu-id="a78a3-128">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)
- [<span data-ttu-id="a78a3-129">Teams での PowerShell の概要</span><span class="sxs-lookup"><span data-stu-id="a78a3-129">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
