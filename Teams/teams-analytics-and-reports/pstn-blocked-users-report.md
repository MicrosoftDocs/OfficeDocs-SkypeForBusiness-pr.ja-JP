---
title: Microsoft Teams PSTN ブロックユーザーレポート
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: v-rifer
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
MS.collection:
- M365-voice
description: Microsoft Teams 管理センターの PSTN ブロックユーザーレポートを使用して、PSTN 通話の発信をブロックされている組織の Teams ユーザーの概要を把握します。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 511485fa156ba448368809edf54728ada1b80be7
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "43904909"
---
# <a name="microsoft-teams-pstn-blocked-users-report"></a><span data-ttu-id="5009d-103">Microsoft Teams PSTN ブロックユーザーレポート</span><span class="sxs-lookup"><span data-stu-id="5009d-103">Microsoft Teams PSTN blocked users report</span></span>

<span data-ttu-id="5009d-104">Microsoft Teams 管理センターの PSTN ブロックユーザーレポートには、Teams で PSTN 通話の発信をブロックされている組織内のユーザーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5009d-104">The PSTN blocked users report in the Microsoft Teams admin center shows you the users in your organization who are blocked from making PSTN calls in Teams.</span></span> <span data-ttu-id="5009d-105">ブロックされたユーザーについての詳細を表示できます。割り当てられた電話番号や、着信がブロックされた理由などです。</span><span class="sxs-lookup"><span data-stu-id="5009d-105">You can view more information about each blocked user, including their assigned phone number and the reason they were blocked from making calls.</span></span>

## <a name="view-the-pstn-blocked-users-report"></a><span data-ttu-id="5009d-106">PSTN ブロックユーザーレポートを表示する</span><span class="sxs-lookup"><span data-stu-id="5009d-106">View the PSTN blocked users report</span></span>

<span data-ttu-id="5009d-107">Microsoft Teams 管理センターの左側のナビゲーションで、**[分析およびレポート]** > **[使用状況レポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5009d-107">In the left navigation of the Microsoft Teams admin center, click **Analytics & reports** > **Usage reports**.</span></span> <span data-ttu-id="5009d-108">[レポートの**表示**] タブの [**レポート**] で、[ **PSTN ブロックユーザー**] を選択し、[**レポートの実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5009d-108">On the **View reports** tab, under **Report**, select **PSTN blocked users**, and then click **Run report**.</span></span>

<span data-ttu-id="5009d-109">![管理センターの PSTN ブロックユーザーレポートレポートのスクリーンショット](../media/teams-reports-pstn-blocked-users-with-callouts.png "番号付き吹き出しが含まれる Microsoft Teams 管理センターの PSTN ブロックユーザーレポートのスクリーンショット")</span><span class="sxs-lookup"><span data-stu-id="5009d-109">![Screenshot of the PSTN blocked users report report in the admin center](../media/teams-reports-pstn-blocked-users-with-callouts.png "Screenshot of the PSTN blocked users report in the Microsoft Teams admin center with numbered callouts")</span></span>

## <a name="interpret-the-report"></a><span data-ttu-id="5009d-110">レポートを解釈する</span><span class="sxs-lookup"><span data-stu-id="5009d-110">Interpret the report</span></span>

|<span data-ttu-id="5009d-111">Callout</span><span class="sxs-lookup"><span data-stu-id="5009d-111">Callout</span></span> |<span data-ttu-id="5009d-112">説明</span><span class="sxs-lookup"><span data-stu-id="5009d-112">Description</span></span>  |
|--------|-------------|
|<span data-ttu-id="5009d-113">**1**</span><span class="sxs-lookup"><span data-stu-id="5009d-113">**1**</span></span>   |<span data-ttu-id="5009d-114">各レポートには、生成された日付が含まれています。</span><span class="sxs-lookup"><span data-stu-id="5009d-114">Each report has a date for when it was generated.</span></span> <span data-ttu-id="5009d-115">通常、レポートはアクティビティの時刻から 24 ～ 48 時間の遅延を反映します。</span><span class="sxs-lookup"><span data-stu-id="5009d-115">The reports usually reflect a 24 to 48 hour latency from time of activity.</span></span> |
|<span data-ttu-id="5009d-116">**2**</span><span class="sxs-lookup"><span data-stu-id="5009d-116">**2**</span></span>   |<span data-ttu-id="5009d-117">X 軸は日付です。</span><span class="sxs-lookup"><span data-stu-id="5009d-117">The X axis is the date.</span></span> <span data-ttu-id="5009d-118">Y 軸はユーザーの数です。</span><span class="sxs-lookup"><span data-stu-id="5009d-118">The Y axis is the number of users.</span></span> <br><span data-ttu-id="5009d-119">特定の日付のドットの上にマウスポインターを移動すると、その日付でブロックされたユーザーの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5009d-119">Hover over the dot on a given date to see the number of users blocked on that date.</span></span> |
|<span data-ttu-id="5009d-120">**3**</span><span class="sxs-lookup"><span data-stu-id="5009d-120">**3**</span></span>   |<span data-ttu-id="5009d-121">この表は、PSTN 通話の発信をブロックされているすべてのユーザーの内訳を示しています。</span><span class="sxs-lookup"><span data-stu-id="5009d-121">The table gives a breakdown of all users who are blocked from making PSTN calls.</span></span>  <span data-ttu-id="5009d-122">電話システムまたは電話会議が割り当てられているすべてのユーザーが表示され、各ユーザーについての情報が提供されます。</span><span class="sxs-lookup"><span data-stu-id="5009d-122">It shows all users who have Phone System or Audio Conferencing assigned and gives you more information about each user.</span></span> <ul><li><span data-ttu-id="5009d-123">**表示名**はユーザーの表示名です。</span><span class="sxs-lookup"><span data-stu-id="5009d-123">**Display name** is the display name of the user.</span></span> <span data-ttu-id="5009d-124">表示名をクリックして、Microsoft Teams 管理センターのユーザーの設定ページに移動することができます。</span><span class="sxs-lookup"><span data-stu-id="5009d-124">You can click the display name to go to the user's setting page in the Microsoft Teams admin center.</span></span> </li> <li><span data-ttu-id="5009d-125">[**電話**番号」は、ユーザーに割り当てられている番号です。</span><span class="sxs-lookup"><span data-stu-id="5009d-125">**Phone** is the number that's assigned to the user.</span></span></li> <li><span data-ttu-id="5009d-126">**ブロック**された理由は、ユーザーが通話を発信できない理由です。</span><span class="sxs-lookup"><span data-stu-id="5009d-126">**Blocked reason** is the reason the user is blocked from making calls.</span></span></li><li><span data-ttu-id="5009d-127">**ブロック**されたアクションは、チームで PSTN 通話を発信またはブロック解除するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="5009d-127">**Blocked action**  tells you whether the user is blocked or unblocked from making PSTN calls in Teams.</span></span></li> <li><span data-ttu-id="5009d-128">[ブロックされた**時間**] は、ユーザーが発信をブロックされた日付と時刻 (UTC) です。</span><span class="sxs-lookup"><span data-stu-id="5009d-128">**Blocked time** is the date and time (UTC) that the user was blocked from making calls.</span></span></li></li> </ul><span data-ttu-id="5009d-129">表に希望する情報を表示するには、表に列を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5009d-129">To see the information that you want in the table, make sure to add the columns to the table.</span></span> |
|<span data-ttu-id="5009d-130">**4**</span><span class="sxs-lookup"><span data-stu-id="5009d-130">**4**</span></span>   |<span data-ttu-id="5009d-131">[**列の編集**] を選択して表で列を追加または削除します。</span><span class="sxs-lookup"><span data-stu-id="5009d-131">Select **Edit columns** to add or remove columns in the table.</span></span>|
|<span data-ttu-id="5009d-132">**5**</span><span class="sxs-lookup"><span data-stu-id="5009d-132">**5**</span></span>   |<span data-ttu-id="5009d-133">全画面表示モードでレポートを表示するには、[**全画面**表示] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5009d-133">Select **Full screen** to view the report in full screen mode.</span></span>|

## <a name="related-topics"></a><span data-ttu-id="5009d-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="5009d-134">Related topics</span></span>

- [<span data-ttu-id="5009d-135">Teams の分析とレポート</span><span class="sxs-lookup"><span data-stu-id="5009d-135">Teams analytics and reporting</span></span>](teams-reporting-reference.md)