---
title: Microsoft TeamsPSTN ブロックユーザー レポート
author: cichur
ms.author: v-cichur
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
description: Microsoft Teams 管理センターで PSTN ブロックユーザー レポートを使用して、PSTN 通話がブロックされている組織のユーザー Teamsの概要を確認します。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ed775c3796e40a775b3be2b78f22e162a047bf78
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809337"
---
# <a name="microsoft-teams-pstn-blocked-users-report"></a><span data-ttu-id="80b9f-103">Microsoft TeamsPSTN ブロックユーザー レポート</span><span class="sxs-lookup"><span data-stu-id="80b9f-103">Microsoft Teams PSTN blocked users report</span></span>

<span data-ttu-id="80b9f-104">Microsoft Teams 管理センターの PSTN ブロックユーザー レポートには、組織内のユーザーが、TEAMS で PSTN 通話を行うのをブロックされているユーザーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="80b9f-104">The PSTN blocked users report in the Microsoft Teams admin center shows you the users in your organization who are blocked from making PSTN calls in Teams.</span></span> <span data-ttu-id="80b9f-105">割り当てられた電話番号や、通話がブロックされた理由など、ブロックされている各ユーザーの詳細を表示できます。</span><span class="sxs-lookup"><span data-stu-id="80b9f-105">You can view more information about each blocked user, including their assigned phone number and the reason they were blocked from making calls.</span></span>

## <a name="view-the-pstn-blocked-users-report"></a><span data-ttu-id="80b9f-106">PSTN ブロックユーザー レポートを表示する</span><span class="sxs-lookup"><span data-stu-id="80b9f-106">View the PSTN blocked users report</span></span>

<span data-ttu-id="80b9f-107">Microsoft Teams 管理センターの左側のナビゲーションで、**[分析 & レポート]** > **[使用状況レポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="80b9f-107">In the left navigation of the Microsoft Teams admin center, click **Analytics & reports** > **Usage reports**.</span></span> <span data-ttu-id="80b9f-108">[レポート **の表示] タブの** [レポート] **で**、[PSTN ブロックユーザー] を **選択し**、[レポートの実行] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="80b9f-108">On the **View reports** tab, under **Report**, select **PSTN blocked users**, and then click **Run report**.</span></span>

<span data-ttu-id="80b9f-109">![管理センターの PSTN ブロックユーザー レポート レポートのスクリーンショット](../media/teams-reports-pstn-blocked-users-with-callouts.png "番号付き吹き出しが表示された Microsoft Teams PSTN ブロック ユーザー レポートのスクリーンショット")</span><span class="sxs-lookup"><span data-stu-id="80b9f-109">![Screenshot of the PSTN blocked users report report in the admin center](../media/teams-reports-pstn-blocked-users-with-callouts.png "Screenshot of the PSTN blocked users report in the Microsoft Teams admin center with numbered callouts")</span></span>

## <a name="interpret-the-report"></a><span data-ttu-id="80b9f-110">レポートを解釈する</span><span class="sxs-lookup"><span data-stu-id="80b9f-110">Interpret the report</span></span>

|<span data-ttu-id="80b9f-111">Callout</span><span class="sxs-lookup"><span data-stu-id="80b9f-111">Callout</span></span> |<span data-ttu-id="80b9f-112">説明</span><span class="sxs-lookup"><span data-stu-id="80b9f-112">Description</span></span>  |
|--------|-------------|
|<span data-ttu-id="80b9f-113">**1**</span><span class="sxs-lookup"><span data-stu-id="80b9f-113">**1**</span></span>   |<span data-ttu-id="80b9f-114">各レポートには、生成された日付があります。</span><span class="sxs-lookup"><span data-stu-id="80b9f-114">Each report has a date for when it was generated.</span></span> <span data-ttu-id="80b9f-115">通常、レポートはアクティビティの時刻から 24 ～ 48 時間の遅延を反映します。</span><span class="sxs-lookup"><span data-stu-id="80b9f-115">The reports usually reflect a 24 to 48 hour latency from time of activity.</span></span> |
|<span data-ttu-id="80b9f-116">**2**</span><span class="sxs-lookup"><span data-stu-id="80b9f-116">**2**</span></span>   |<span data-ttu-id="80b9f-117">X 軸は日付です。</span><span class="sxs-lookup"><span data-stu-id="80b9f-117">The X axis is the date.</span></span> <span data-ttu-id="80b9f-118">Y 軸はユーザー数です。</span><span class="sxs-lookup"><span data-stu-id="80b9f-118">The Y axis is the number of users.</span></span> <br><span data-ttu-id="80b9f-119">特定の日付のドットにマウス ポインターを合わせると、その日付にブロックされたユーザーの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="80b9f-119">Hover over the dot on a given date to see the number of users blocked on that date.</span></span> |
|<span data-ttu-id="80b9f-120">**3**</span><span class="sxs-lookup"><span data-stu-id="80b9f-120">**3**</span></span>   |<span data-ttu-id="80b9f-121">この表は、PSTN 通話をブロックしているすべてのユーザーの内訳を示しています。</span><span class="sxs-lookup"><span data-stu-id="80b9f-121">The table gives a breakdown of all users who are blocked from making PSTN calls.</span></span>  <span data-ttu-id="80b9f-122">このページには、電話会議または電話電話システム割り当てられているすべてのユーザーが表示され、各ユーザーに関する詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="80b9f-122">It shows all users who have Phone System or Audio Conferencing assigned and gives you more information about each user.</span></span> <ul><li><span data-ttu-id="80b9f-123">**表示名** はユーザーの表示名です。</span><span class="sxs-lookup"><span data-stu-id="80b9f-123">**Display name** is the display name of the user.</span></span> <span data-ttu-id="80b9f-124">表示名をクリックして、Microsoft Teams 管理センターのユーザーの設定ページに移動することができます。</span><span class="sxs-lookup"><span data-stu-id="80b9f-124">You can click the display name to go to the user's setting page in the Microsoft Teams admin center.</span></span> </li> <li><span data-ttu-id="80b9f-125">**電話** は、ユーザーに割り当てられている番号です。</span><span class="sxs-lookup"><span data-stu-id="80b9f-125">**Phone** is the number that's assigned to the user.</span></span></li> <li><span data-ttu-id="80b9f-126">**ブロックされる理由** は、ユーザーが呼び出しを行うのをブロックされる理由です。</span><span class="sxs-lookup"><span data-stu-id="80b9f-126">**Blocked reason** is the reason the user is blocked from making calls.</span></span></li><li><span data-ttu-id="80b9f-127">**[ブロック] アクション** は、ユーザーが PSTN 通話を行うのをブロックまたはブロック解除されているかどうかを示Teams。</span><span class="sxs-lookup"><span data-stu-id="80b9f-127">**Blocked action**  tells you whether the user is blocked or unblocked from making PSTN calls in Teams.</span></span></li> <li><span data-ttu-id="80b9f-128">**[ブロックされた時刻** ] は、ユーザーが呼び出しを行うのをブロックされた日時 (UTC) です。</span><span class="sxs-lookup"><span data-stu-id="80b9f-128">**Blocked time** is the date and time (UTC) that the user was blocked from making calls.</span></span></li></li> </ul><span data-ttu-id="80b9f-129">表に希望する情報を表示するには、表に列を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="80b9f-129">To see the information that you want in the table, make sure to add the columns to the table.</span></span> |
|<span data-ttu-id="80b9f-130">**4**</span><span class="sxs-lookup"><span data-stu-id="80b9f-130">**4**</span></span>   |<span data-ttu-id="80b9f-131">[**列の編集**] を選択して表で列を追加または削除します。</span><span class="sxs-lookup"><span data-stu-id="80b9f-131">Select **Edit columns** to add or remove columns in the table.</span></span>|
|<span data-ttu-id="80b9f-132">**5**</span><span class="sxs-lookup"><span data-stu-id="80b9f-132">**5**</span></span>   |<span data-ttu-id="80b9f-133">[ **全画面] を** 選択して、レポートを全画面モードで表示します。</span><span class="sxs-lookup"><span data-stu-id="80b9f-133">Select **Full screen** to view the report in full screen mode.</span></span>|

## <a name="related-topics"></a><span data-ttu-id="80b9f-134">関連トピック</span><span class="sxs-lookup"><span data-stu-id="80b9f-134">Related topics</span></span>

- [<span data-ttu-id="80b9f-135">Teams の分析とレポート</span><span class="sxs-lookup"><span data-stu-id="80b9f-135">Teams analytics and reporting</span></span>](teams-reporting-reference.md)