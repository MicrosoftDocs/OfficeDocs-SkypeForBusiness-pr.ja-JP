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
description: 自動応答で使用するために、Microsoft Teamsの休日を設定する方法について学習します。
ms.openlocfilehash: ff87a3888bc98e1794f8074052aae4c0bbe3545d
ms.sourcegitcommit: 247b2587a60b1609947310ec82d51f47cf829703
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/11/2020
ms.locfileid: "48993473"
---
# <a name="set-up-holidays-in-microsoft-teams"></a><span data-ttu-id="b4472-103">Microsoft Teams で休日を設定する</span><span class="sxs-lookup"><span data-stu-id="b4472-103">Set up holidays in Microsoft Teams</span></span>

<span data-ttu-id="b4472-104">Teams Holidays 機能を使用すると、部門、通話キュー、または組織内のユーザーが異なる勤務時間に従う場合、または利用できない特定の日時に、発信者に代替メッセージとルーティングを提供できます。</span><span class="sxs-lookup"><span data-stu-id="b4472-104">You can use the Teams Holidays feature to provide alternate messages and routing to callers for specific dates and times when departments, call queues or people in your organization will be following different working hours or won't be available.</span></span> <span data-ttu-id="b4472-105">たとえば、組織が閉じている可能性がある新年の祝日を作成できます。</span><span class="sxs-lookup"><span data-stu-id="b4472-105">For example, you might create a holiday for New Year's day when your organization may be closed.</span></span>

<span data-ttu-id="b4472-106">ここで作成する祝日は、自動応答を設定するときに使用 [できます](create-a-phone-system-auto-attendant.md)。それぞれに独自のあいさつ応答と通話ルーティング設定が設定されています。</span><span class="sxs-lookup"><span data-stu-id="b4472-106">The holidays you create here are available when you [set up an auto attendant](create-a-phone-system-auto-attendant.md), each with its own greeting and call routing settings.</span></span>

## <a name="create-a-holiday"></a><span data-ttu-id="b4472-107">休日を作成する</span><span class="sxs-lookup"><span data-stu-id="b4472-107">Create a holiday</span></span>

<span data-ttu-id="b4472-108">休日を作成するには</span><span class="sxs-lookup"><span data-stu-id="b4472-108">To create a holiday</span></span>

1. <span data-ttu-id="b4472-109">管理センター Microsoft Teams、組織全体の **設定 [祝日] に移動**  >  **します**。</span><span class="sxs-lookup"><span data-stu-id="b4472-109">In the Microsoft Teams admin center, go to **Org-wide settings** > **Holidays**.</span></span>

2. <span data-ttu-id="b4472-110">[新 **しい休日] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="b4472-110">Select **New holiday**.</span></span>

3. <span data-ttu-id="b4472-111">休日の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="b4472-111">Enter a name for the holiday.</span></span>

4. <span data-ttu-id="b4472-112">[新しい **日付の追加] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="b4472-112">Select **Add new date**.</span></span>

5. <span data-ttu-id="b4472-113">[ **開始時刻]** でカレンダー アイコンを選択し、休日を開始する日付を選択します。</span><span class="sxs-lookup"><span data-stu-id="b4472-113">Under **Start time**, select the calendar icon and choose the date when you'd like the holiday to begin.</span></span>

6. <span data-ttu-id="b4472-114">ドロップダウン リストを使用して、休日の開始時刻を選択します。</span><span class="sxs-lookup"><span data-stu-id="b4472-114">Use the drop-down list to select a start time for the holiday.</span></span>

7. <span data-ttu-id="b4472-115">[ **終了時刻]** でカレンダー アイコンを選択し、休日を終了する日付を選択します。</span><span class="sxs-lookup"><span data-stu-id="b4472-115">Under **End time**, select the calendar icon and choose the date when you'd like the holiday to end.</span></span>

8. <span data-ttu-id="b4472-116">ドロップダウン リストを使用して、休日の終了時刻を選択します。</span><span class="sxs-lookup"><span data-stu-id="b4472-116">Use the drop-down list to select an end time for the holiday.</span></span> <span data-ttu-id="b4472-117">終了 **時刻は、** 開始時刻 より後 **である必要があります**。</span><span class="sxs-lookup"><span data-stu-id="b4472-117">The **End time** must be after the **Start time**.</span></span>  

   > [!NOTE]
   > <span data-ttu-id="b4472-118">祝日が 1 日の場合 (つまり、24 時間の期間)、終了時刻を翌日に設定し、時刻を午前 12 時に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b4472-118">If the holiday is for one full day (i.e., a 24 hour period), the **End time** should be set to the next day and the time to 12:00 AM.</span></span> <span data-ttu-id="b4472-119">たとえば、組織が 1 月 1 日に正月 1日に閉じている場合は、[開始時刻] を [1月 1 日 12:00 AM] に設定し、[終了時刻] を [1 月 2 日 @ 12:00 AM] に設定します。</span><span class="sxs-lookup"><span data-stu-id="b4472-119">For example, if your organization is closed on January 1 for New Year's day, set the **Start time** to January 1 12:00 AM and set the **End time** to January 2 @ 12:00 AM.</span></span>

9. <span data-ttu-id="b4472-120">必要に応じて、定期的な祝日の日付を追加します。</span><span class="sxs-lookup"><span data-stu-id="b4472-120">Optionally, add more dates for recurring holidays.</span></span>

10. <span data-ttu-id="b4472-121">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b4472-121">Select **Save**.</span></span>

    ![3 年間設定された日付を含む休日のユーザー インターフェイスのスクリーンショット](media/holidays-set-up.png)

## <a name="change-a-holiday"></a><span data-ttu-id="b4472-123">休日を変更する</span><span class="sxs-lookup"><span data-stu-id="b4472-123">Change a holiday</span></span>

<span data-ttu-id="b4472-124">休日を変更するには</span><span class="sxs-lookup"><span data-stu-id="b4472-124">To change a holiday</span></span>

1. <span data-ttu-id="b4472-125">管理センター Microsoft Teams、組織全体の **設定 [祝日] に移動**  >  **します**。</span><span class="sxs-lookup"><span data-stu-id="b4472-125">In the Microsoft Teams admin center, go to **Org-wide settings** > **Holidays**.</span></span>

2. <span data-ttu-id="b4472-126">一覧から休日を選択します。</span><span class="sxs-lookup"><span data-stu-id="b4472-126">Select the holiday from the list.</span></span>

3. <span data-ttu-id="b4472-127">[ **開始時刻]** でカレンダー アイコンを選択し、休日を開始する日付を選択します。</span><span class="sxs-lookup"><span data-stu-id="b4472-127">Under **Start time**, select the calendar icon and choose the date when you'd like the holiday to begin.</span></span>

4. <span data-ttu-id="b4472-128">ドロップダウン リストを使用して、休日の開始時刻を選択します。</span><span class="sxs-lookup"><span data-stu-id="b4472-128">Use the drop-down list to select a start time for the holiday.</span></span>

5. <span data-ttu-id="b4472-129">[ **終了時刻]** でカレンダー アイコンを選択し、休日を終了する日付を選択します。</span><span class="sxs-lookup"><span data-stu-id="b4472-129">Under **End time**, select the calendar icon and choose the date when you'd like the holiday to end.</span></span> 

6. <span data-ttu-id="b4472-130">ドロップダウン リストを使用して、休日の終了時刻を選択します。</span><span class="sxs-lookup"><span data-stu-id="b4472-130">Use the drop-down list to select an end time for the holiday.</span></span> <span data-ttu-id="b4472-131">終了 **時刻は、** 開始時刻 より後 **である必要があります**。</span><span class="sxs-lookup"><span data-stu-id="b4472-131">The **End time** must be after the **Start time**.</span></span>  

7. <span data-ttu-id="b4472-132">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b4472-132">Select **Save**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b4472-133">関連トピック</span><span class="sxs-lookup"><span data-stu-id="b4472-133">Related topics</span></span>

<span data-ttu-id="b4472-134">[自動応答Teams通話キューの計画を立てませんか](plan-auto-attendant-call-queue.md)?</span><span class="sxs-lookup"><span data-stu-id="b4472-134">[Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md)?</span></span>
