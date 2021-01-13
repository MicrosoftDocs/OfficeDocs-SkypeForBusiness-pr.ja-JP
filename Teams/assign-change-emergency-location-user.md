---
title: ユーザーの緊急対応の場所を割り当てたり変更したりする
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
description: この記事では、組織内のユーザーの緊急対応の場所を割り当てる方法または変更する方法について学習します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8352c702d2c6d32b6384599499aa326def49fa4e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809567"
---
# <a name="assign-or-change-an-emergency-location-for-a-user"></a><span data-ttu-id="a33fb-103">ユーザーの緊急対応の場所を割り当てたり変更したりする</span><span class="sxs-lookup"><span data-stu-id="a33fb-103">Assign or change an emergency location for a user</span></span>

<span data-ttu-id="a33fb-104">通話プランを設定する場合は、電話番号またはユーザーごとに緊急対応の場所を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="a33fb-104">When you're setting up Calling Plans, you need to assign an emergency location to each phone number or user.</span></span> <span data-ttu-id="a33fb-105">ヨーロッパの国では、緊急対応の場所は、Microsoft 365 または Office 365 から電話番号を取得した場合、または電話番号を Microsoft 365 または Office 365 に転送した場合に関連付けされます。</span><span class="sxs-lookup"><span data-stu-id="a33fb-105">In European countries, the emergency location is associated with the phone number when you get it from Microsoft 365 or Office 365 or when you transfer a phone number over to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="a33fb-106">米国では、緊急対応の場所はユーザーに割り当てられた電話番号に関連付けされます。</span><span class="sxs-lookup"><span data-stu-id="a33fb-106">In the United States, the emergency location is associated with the phone number when it's assigned to the user.</span></span> <span data-ttu-id="a33fb-107">緊急対応の住所は、割り当てられているユーザーが新しい場所に移動した場合に変更できます。</span><span class="sxs-lookup"><span data-stu-id="a33fb-107">The emergency address can be changed if the user that it's assigned to moves to a new location.</span></span> <span data-ttu-id="a33fb-108">緊急対応の住所と場所の詳細については、「緊急対応の場所、場所、通話ルーティングとは [何か」を参照してください](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing)。</span><span class="sxs-lookup"><span data-stu-id="a33fb-108">For more about emergency addresses and locations, see [What are emergency locations, places, and call routing?](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing).</span></span>
  
<span data-ttu-id="a33fb-109">通話プランを取得する方法と料金については、「Teams アドオン ライセンス [」を参照してください](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)。</span><span class="sxs-lookup"><span data-stu-id="a33fb-109">To learn how to get a Calling Plans and how much they cost, see [Teams add-on licensing](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing).</span></span>
  
<span data-ttu-id="a33fb-110">Microsoft Teams 管理センターまたは PowerShell を使用して、ユーザーの緊急対応の場所を割り当てまたは変更できます。</span><span class="sxs-lookup"><span data-stu-id="a33fb-110">You can assign or change an emergency location for a user in the Microsoft Teams admin center or by using PowerShell.</span></span>

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="a33fb-111">Microsoft Teams 管理センターの使用</span><span class="sxs-lookup"><span data-stu-id="a33fb-111">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="a33fb-112">Microsoft Teams 管理センターの左側のナビゲーションで、[**音声電話番号]** を  >  **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="a33fb-112">In the left navigation of the Microsoft Teams admin center, click **Voice** > **Phone numbers**.</span></span>

2. <span data-ttu-id="a33fb-113">[電話番号 **] ページで** 、[番号] タブを **クリック** し、一覧からユーザー番号を選び、[編集] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="a33fb-113">On the **Phone numbers** page, click the **Numbers** tab, select a user number in the list, and then click **Edit**.</span></span>

3. <span data-ttu-id="a33fb-114">[編集] **ウィンドウの** [緊急対応の **場所] で、** 次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="a33fb-114">On the **Edit** pane, under **Emergency location**, do one of the following:</span></span>

   - <span data-ttu-id="a33fb-115">緊急対応の場所を割り当てるには、緊急対応の場所を検索して選択します。</span><span class="sxs-lookup"><span data-stu-id="a33fb-115">To assign an emergency location, search for, and select an emergency location.</span></span>

   - <span data-ttu-id="a33fb-116">ユーザーに既に割り当てられている緊急対応の場所を変更するには **、[X]** をクリックして既存の場所を削除し、割り当てる場所を検索して選択します。</span><span class="sxs-lookup"><span data-stu-id="a33fb-116">To change the emergency location that's already assigned to the user, click **X** to remove the existing location, and then search for and select the location you want to assign.</span></span>

4. <span data-ttu-id="a33fb-117">電話番号情報を含むメールをユーザーに送信するかどうかに応じて、電話番号情報を含むメール ユーザーをオフまたは **オンにします**。</span><span class="sxs-lookup"><span data-stu-id="a33fb-117">Depending on whether you want to send an email to the user with their phone number information, turn off or turn on **Email user with telephone number information**.</span></span> <span data-ttu-id="a33fb-118">既定では、オンになっています。</span><span class="sxs-lookup"><span data-stu-id="a33fb-118">By default, this is on.</span></span>

5. <span data-ttu-id="a33fb-119">[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a33fb-119">Click **Apply**.</span></span>

## <a name="using-powershell"></a><span data-ttu-id="a33fb-120">PowerShell の使用</span><span class="sxs-lookup"><span data-stu-id="a33fb-120">Using PowerShell</span></span>

<span data-ttu-id="a33fb-121">[「Set-CsOnlineVoiceUser」を参照してください](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser)。</span><span class="sxs-lookup"><span data-stu-id="a33fb-121">See [Set-CsOnlineVoiceUser](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser).</span></span> 

    
## <a name="related-topics"></a><span data-ttu-id="a33fb-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="a33fb-122">Related topics</span></span>

- [<span data-ttu-id="a33fb-123">緊急通話を管理する</span><span class="sxs-lookup"><span data-stu-id="a33fb-123">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="a33fb-124">組織の緊急対応の場所を追加、変更、削除する</span><span class="sxs-lookup"><span data-stu-id="a33fb-124">Add, change, or remove an emergency location for your organization</span></span>](add-change-remove-emergency-location-organization.md)
- [<span data-ttu-id="a33fb-125">組織の緊急対応の場所の位置情報を追加、変更、削除する</span><span class="sxs-lookup"><span data-stu-id="a33fb-125">Add, change, or remove a place for an emergency location in your organization</span></span>](add-change-remove-emergency-place-organization.md)
- [<span data-ttu-id="a33fb-126">ユーザーの緊急対応の場所の位置情報を割り当てたり変更したりする</span><span class="sxs-lookup"><span data-stu-id="a33fb-126">Assign or change a place for an emergency location for a user</span></span>](assign-change-emergency-place-user.md)
- [<span data-ttu-id="a33fb-127">組織の電話番号を管理する</span><span class="sxs-lookup"><span data-stu-id="a33fb-127">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)
- [<span data-ttu-id="a33fb-128">緊急通話の利用条件</span><span class="sxs-lookup"><span data-stu-id="a33fb-128">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)
- [<span data-ttu-id="a33fb-129">Teams での PowerShell の概要</span><span class="sxs-lookup"><span data-stu-id="a33fb-129">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
