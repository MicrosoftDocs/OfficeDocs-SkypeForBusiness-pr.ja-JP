---
title: Microsoft Teams 管理センターのアクティビティログでポリシーの割り当てを表示する
author: LanaChin
ms.author: v-lanac
ms.reviewer: jastark
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Microsoft Teams 管理センターのアクティビティログでポリシーの割り当てアクティビティを表示する方法について説明します。
localization_priority: Normal
f1.keywords:
- CSH
- ms.teamsadmincenter.dashboard.activitylog.overview
ms.custom: ''
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5f85899869a8578df59516d0e0d702f8e36bd951
ms.sourcegitcommit: 47637ed816b471fe689e7bdac27b73e6efced60c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "44374295"
---
# <a name="view-your-policy-assignments-in-the-activity-log"></a><span data-ttu-id="d34e1-103">アクティビティログでポリシーの割り当てを表示する</span><span class="sxs-lookup"><span data-stu-id="d34e1-103">View your policy assignments in the Activity log</span></span>

<span data-ttu-id="d34e1-104">Microsoft Teams 管理センターでユーザーにポリシーを割り当てると、それらのポリシー割り当ての状態をアクティビティログで確認できます。</span><span class="sxs-lookup"><span data-stu-id="d34e1-104">When you assign policies to users in the Microsoft Teams admin center, you can view the status of those policy assignments in the Activity log.</span></span> <span data-ttu-id="d34e1-105">アクティビティログには、過去30日間の Microsoft Teams 管理センターを通じて、20人を超えるユーザーのバッチに対するポリシーの割り当てが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d34e1-105">The Activity log shows policy assignments to batches of more than 20 users through the Microsoft Teams admin center from the last 30 days.</span></span> <span data-ttu-id="d34e1-106">アクティビティログには、Microsoft Teams 管理センターを通じて、または PowerShell を使用したポリシーの割り当てによって、ポリシーパッケージの割り当て、ポリシーの割り当てが表示されないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="d34e1-106">Keep in mind that the Activity log doesn't show policy package assignments, policy assignments to batches of less than 20 users through the Microsoft Teams admin center, or policy assignments through PowerShell.</span></span>

![[アクティビティログ] ページのスクリーンショット](media/activity-log.png)

## <a name="view-your-policy-assignment-activities-in-the-activity-log"></a><span data-ttu-id="d34e1-108">アクティビティログでポリシーの割り当てアクティビティを表示する</span><span class="sxs-lookup"><span data-stu-id="d34e1-108">View your policy assignment activities in the Activity log</span></span>

<span data-ttu-id="d34e1-109">アクティビティログでポリシーの割り当てを表示するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="d34e1-109">To view your policy assignments in the Activity log:</span></span>

1. <span data-ttu-id="d34e1-110">Microsoft Teams 管理センターの左のナビゲーションで、[**ダッシュボード**] に移動し、[**アクティビティログ**] で [**詳細の表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d34e1-110">In the left navigation of the Microsoft Teams admin center, go to **Dashboard**, and then under **Activity Log**, select **View details**.</span></span>
2. <span data-ttu-id="d34e1-111">すべてのポリシーの割り当てを表示したり、状態別にリストにフィルターを適用したりして、**未開始**、**進行中**、または**完了**した割り当てだけを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="d34e1-111">You can view all policy assignments or filter the list by status to show only assignments that are **Not started**, **In progress**, or **Completed**.</span></span> <span data-ttu-id="d34e1-112">各課題について次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d34e1-112">You'll see the following information about each assignment:</span></span>
    - <span data-ttu-id="d34e1-113">**Name**: ポリシーの割り当ての名前。</span><span class="sxs-lookup"><span data-stu-id="d34e1-113">**Name**: The name of the policy assignment.</span></span> <span data-ttu-id="d34e1-114">詳細を表示するには、リンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d34e1-114">Click the link to view more details.</span></span> <span data-ttu-id="d34e1-115">これには、ポリシーが割り当てられたユーザーの数と、完了した、進行中で、まだ開始していない課題の数が含まれます。</span><span class="sxs-lookup"><span data-stu-id="d34e1-115">This includes the number of users the policy was assigned to and the number of assignments completed, in progress, and not started.</span></span> <span data-ttu-id="d34e1-116">また、バッチ内のユーザーの一覧と、各ユーザーの状態と結果も表示されます。</span><span class="sxs-lookup"><span data-stu-id="d34e1-116">You'll also see the list of users in the batch, and the status and result for each user.</span></span> <span data-ttu-id="d34e1-117">以下は、実行例です。</span><span class="sxs-lookup"><span data-stu-id="d34e1-117">Here's an example:</span></span>

        ![のスクリーンショット](media/activity-log-policy-assignment-detail.png)

    - <span data-ttu-id="d34e1-119">[**送信**日時]: ポリシーの割り当てが送信された日時。</span><span class="sxs-lookup"><span data-stu-id="d34e1-119">**Submitted**: Date and time the policy assignment was submitted.</span></span>
    - <span data-ttu-id="d34e1-120">**完了時刻**: ポリシーの割り当てが完了した日時。</span><span class="sxs-lookup"><span data-stu-id="d34e1-120">**Completion time**: Date and time the policy assignment was completed.</span></span>
    - <span data-ttu-id="d34e1-121">**影響度**: バッチ内のユーザーの数。</span><span class="sxs-lookup"><span data-stu-id="d34e1-121">**Impact on**: Number of users in the batch.</span></span>
    - <span data-ttu-id="d34e1-122">**全般的な状態**: ポリシー割り当ての状態。</span><span class="sxs-lookup"><span data-stu-id="d34e1-122">**Overall status**: Status of the policy assignment.</span></span>

> [!NOTE]
> <span data-ttu-id="d34e1-123">[**ユーザー** ] ページからアクティビティログにアクセスすることもできます。</span><span class="sxs-lookup"><span data-stu-id="d34e1-123">You can also get to the Activity log from the **Users** page.</span></span> <span data-ttu-id="d34e1-124">[**適用**] をクリックして一括ポリシーの割り当てを送信すると、ページの上部にバナーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d34e1-124">After you click **Apply** to submit a bulk policy assignment, you'll see a banner at the top of the page.</span></span> <span data-ttu-id="d34e1-125">バナーの [**アクティビティログ**] リンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d34e1-125">Click the **Activity log** link in the banner.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d34e1-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="d34e1-126">Related topics</span></span>

- [<span data-ttu-id="d34e1-127">ユーザーにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="d34e1-127">Assign policies to users</span></span>](assign-policies.md)
