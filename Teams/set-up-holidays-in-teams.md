---
title: Microsoft Teams で休日を設定する
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.orgwidesettings.holidays.overview
- seo-marvel-apr2020
description: 自動応答で使用するために Microsoft Teams で休日を設定する方法について説明します。
ms.openlocfilehash: ff87a3888bc98e1794f8074052aae4c0bbe3545d
ms.sourcegitcommit: 247b2587a60b1609947310ec82d51f47cf829703
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/11/2020
ms.locfileid: "48993473"
---
# <a name="set-up-holidays-in-microsoft-teams"></a><span data-ttu-id="5153a-103">Microsoft Teams で休日を設定する</span><span class="sxs-lookup"><span data-stu-id="5153a-103">Set up holidays in Microsoft Teams</span></span>

<span data-ttu-id="5153a-104">Teams の休日機能を使用すると、部署、通話キュー、または組織内のユーザーが別の稼働時間に対応しているか、または使用できない場合に、特定の日時に対して、別のメッセージと発信者へのルーティングを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="5153a-104">You can use the Teams Holidays feature to provide alternate messages and routing to callers for specific dates and times when departments, call queues or people in your organization will be following different working hours or won't be available.</span></span> <span data-ttu-id="5153a-105">たとえば、組織が終了している場合は、新しい年の休日を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="5153a-105">For example, you might create a holiday for New Year's day when your organization may be closed.</span></span>

<span data-ttu-id="5153a-106">ここで作成した休日は、 [自動応答を設定](create-a-phone-system-auto-attendant.md)するときに使用できます。それぞれのあいさつ文と通話ルーティング設定が含まれます。</span><span class="sxs-lookup"><span data-stu-id="5153a-106">The holidays you create here are available when you [set up an auto attendant](create-a-phone-system-auto-attendant.md), each with its own greeting and call routing settings.</span></span>

## <a name="create-a-holiday"></a><span data-ttu-id="5153a-107">休日を作成する</span><span class="sxs-lookup"><span data-stu-id="5153a-107">Create a holiday</span></span>

<span data-ttu-id="5153a-108">休日を作成するには</span><span class="sxs-lookup"><span data-stu-id="5153a-108">To create a holiday</span></span>

1. <span data-ttu-id="5153a-109">Microsoft Teams 管理センターで、[ **組織全体の設定**  >  **休日** ] に移動します。</span><span class="sxs-lookup"><span data-stu-id="5153a-109">In the Microsoft Teams admin center, go to **Org-wide settings** > **Holidays**.</span></span>

2. <span data-ttu-id="5153a-110">[ **新しい休日** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5153a-110">Select **New holiday**.</span></span>

3. <span data-ttu-id="5153a-111">休日の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="5153a-111">Enter a name for the holiday.</span></span>

4. <span data-ttu-id="5153a-112">[ **Add new date** ] を選びます。</span><span class="sxs-lookup"><span data-stu-id="5153a-112">Select **Add new date**.</span></span>

5. <span data-ttu-id="5153a-113">[ **開始時刻** ] で、予定表アイコンを選択し、休日の開始日を選択します。</span><span class="sxs-lookup"><span data-stu-id="5153a-113">Under **Start time** , select the calendar icon and choose the date when you'd like the holiday to begin.</span></span>

6. <span data-ttu-id="5153a-114">ドロップダウンリストを使用して、休日の開始時刻を選択します。</span><span class="sxs-lookup"><span data-stu-id="5153a-114">Use the drop-down list to select a start time for the holiday.</span></span>

7. <span data-ttu-id="5153a-115">[ **終了時刻** ] で、予定表アイコンを選択し、休日の終了日を選択します。</span><span class="sxs-lookup"><span data-stu-id="5153a-115">Under **End time** , select the calendar icon and choose the date when you'd like the holiday to end.</span></span>

8. <span data-ttu-id="5153a-116">ドロップダウンリストを使用して、休日の終了時刻を選択します。</span><span class="sxs-lookup"><span data-stu-id="5153a-116">Use the drop-down list to select an end time for the holiday.</span></span> <span data-ttu-id="5153a-117">**終了時刻** は **開始時刻** より後でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="5153a-117">The **End time** must be after the **Start time**.</span></span>  

   > [!NOTE]
   > <span data-ttu-id="5153a-118">休日の1日を1日に設定する場合 (つまり、24時間の期間)、 **終了時刻** は翌日と 12:00 AM の時刻に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5153a-118">If the holiday is for one full day (i.e., a 24 hour period), the **End time** should be set to the next day and the time to 12:00 AM.</span></span> <span data-ttu-id="5153a-119">たとえば、新しい年の1月1日に組織が終了した場合は、[ **開始時刻** ] を [午前 1 12:00 時] に設定し、 **終了時刻** を1月2日の @ 12:00 am に設定します。</span><span class="sxs-lookup"><span data-stu-id="5153a-119">For example, if your organization is closed on January 1 for New Year's day, set the **Start time** to January 1 12:00 AM and set the **End time** to January 2 @ 12:00 AM.</span></span>

9. <span data-ttu-id="5153a-120">必要に応じて、定期休日の日付を追加します。</span><span class="sxs-lookup"><span data-stu-id="5153a-120">Optionally, add more dates for recurring holidays.</span></span>

10. <span data-ttu-id="5153a-121">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5153a-121">Select **Save**.</span></span>

    ![3年の日付を設定した休日のユーザーインターフェイスのスクリーンショット](media/holidays-set-up.png)

## <a name="change-a-holiday"></a><span data-ttu-id="5153a-123">休日を変更する</span><span class="sxs-lookup"><span data-stu-id="5153a-123">Change a holiday</span></span>

<span data-ttu-id="5153a-124">休日を変更するには</span><span class="sxs-lookup"><span data-stu-id="5153a-124">To change a holiday</span></span>

1. <span data-ttu-id="5153a-125">Microsoft Teams 管理センターで、[ **組織全体の設定**  >  **休日** ] に移動します。</span><span class="sxs-lookup"><span data-stu-id="5153a-125">In the Microsoft Teams admin center, go to **Org-wide settings** > **Holidays**.</span></span>

2. <span data-ttu-id="5153a-126">リストから休日を選択します。</span><span class="sxs-lookup"><span data-stu-id="5153a-126">Select the holiday from the list.</span></span>

3. <span data-ttu-id="5153a-127">[ **開始時刻** ] で、予定表アイコンを選択し、休日の開始日を選択します。</span><span class="sxs-lookup"><span data-stu-id="5153a-127">Under **Start time** , select the calendar icon and choose the date when you'd like the holiday to begin.</span></span>

4. <span data-ttu-id="5153a-128">ドロップダウンリストを使用して、休日の開始時刻を選択します。</span><span class="sxs-lookup"><span data-stu-id="5153a-128">Use the drop-down list to select a start time for the holiday.</span></span>

5. <span data-ttu-id="5153a-129">[ **終了時刻** ] で、予定表アイコンを選択し、休日の終了日を選択します。</span><span class="sxs-lookup"><span data-stu-id="5153a-129">Under **End time** , select the calendar icon and choose the date when you'd like the holiday to end.</span></span> 

6. <span data-ttu-id="5153a-130">ドロップダウンリストを使用して、休日の終了時刻を選択します。</span><span class="sxs-lookup"><span data-stu-id="5153a-130">Use the drop-down list to select an end time for the holiday.</span></span> <span data-ttu-id="5153a-131">**終了時刻** は **開始時刻** より後でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="5153a-131">The **End time** must be after the **Start time**.</span></span>  

7. <span data-ttu-id="5153a-132">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5153a-132">Select **Save**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="5153a-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="5153a-133">Related topics</span></span>

<span data-ttu-id="5153a-134">[Teams の自動応答と通話キューを計画し](plan-auto-attendant-call-queue.md)ますか?</span><span class="sxs-lookup"><span data-stu-id="5153a-134">[Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md)?</span></span>
