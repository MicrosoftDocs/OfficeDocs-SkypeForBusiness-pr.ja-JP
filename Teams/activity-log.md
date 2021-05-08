---
title: ポリシーの割り当てを管理センターのアクティビティ ログMicrosoft Teams表示する
author: cichur
ms.author: v-cichur
ms.reviewer: jastark
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: ポリシー割り当てアクティビティを管理センターのアクティビティ ログで表示Microsoft Teamsします。
localization_priority: Normal
f1.keywords:
- CSH
- ms.teamsadmincenter.dashboard.activitylog.overview
ms.custom: ''
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2a8d1d49d187808b768b4a92c64c4e667ca0ea8f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821317"
---
# <a name="view-your-policy-assignments-in-the-activity-log"></a><span data-ttu-id="d65e8-103">アクティビティ ログでポリシーの割り当てを表示する</span><span class="sxs-lookup"><span data-stu-id="d65e8-103">View your policy assignments in the Activity log</span></span>

<span data-ttu-id="d65e8-104">Microsoft Teams 管理センターでユーザーにポリシーを割り当てると、それらのポリシー割り当ての状態をアクティビティ ログに表示できます。</span><span class="sxs-lookup"><span data-stu-id="d65e8-104">When you assign policies to users in the Microsoft Teams admin center, you can view the status of those policy assignments in the Activity log.</span></span> <span data-ttu-id="d65e8-105">アクティビティ ログには、過去 30 日間の Microsoft Teams 管理センターを通じて、20 人を超えるユーザーのバッチへのポリシー割り当てが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d65e8-105">The Activity log shows policy assignments to batches of more than 20 users through the Microsoft Teams admin center from the last 30 days.</span></span> <span data-ttu-id="d65e8-106">アクティビティ ログには、ポリシー パッケージの割り当て、Microsoft Teams 管理センターを通じて 20 人未満のユーザーのバッチに対するポリシーの割り当て、または PowerShell を使用したポリシー割り当てが表示される点に気を付けます。</span><span class="sxs-lookup"><span data-stu-id="d65e8-106">Keep in mind that the Activity log doesn't show policy package assignments, policy assignments to batches of less than 20 users through the Microsoft Teams admin center, or policy assignments through PowerShell.</span></span>

![[アクティビティ ログ] ページのスクリーンショット](media/activity-log.png)

## <a name="view-your-policy-assignment-activities-in-the-activity-log"></a><span data-ttu-id="d65e8-108">アクティビティ ログでポリシー割り当てアクティビティを表示する</span><span class="sxs-lookup"><span data-stu-id="d65e8-108">View your policy assignment activities in the Activity log</span></span>

<span data-ttu-id="d65e8-109">アクティビティ ログでポリシーの割り当てを表示するには:</span><span class="sxs-lookup"><span data-stu-id="d65e8-109">To view your policy assignments in the Activity log:</span></span>

1. <span data-ttu-id="d65e8-110">管理センターの左側のナビゲーションMicrosoft Teams ダッシュボード に移動し、[アクティビティログ] で[詳細の表示]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="d65e8-110">In the left navigation of the Microsoft Teams admin center, go to **Dashboard**, and then under **Activity Log**, select **View details**.</span></span>
2. <span data-ttu-id="d65e8-111">すべてのポリシー割り当てを表示したり、状態で一覧をフィルター処理して、[開始していない]、[進行中]、または [完了] の割り当てのみを **表示することができます**。</span><span class="sxs-lookup"><span data-stu-id="d65e8-111">You can view all policy assignments or filter the list by status to show only assignments that are **Not started**, **In progress**, or **Completed**.</span></span> <span data-ttu-id="d65e8-112">各課題に関する次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d65e8-112">You'll see the following information about each assignment:</span></span>
    - <span data-ttu-id="d65e8-113">**[** 名前]: ポリシー割り当ての名前。</span><span class="sxs-lookup"><span data-stu-id="d65e8-113">**Name**: The name of the policy assignment.</span></span> <span data-ttu-id="d65e8-114">リンクをクリックすると、詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d65e8-114">Click the link to view more details.</span></span> <span data-ttu-id="d65e8-115">これには、ポリシーが割り当てられたユーザーの数と、完了した割り当て、進行中、開始されていない割り当ての数が含まれます。</span><span class="sxs-lookup"><span data-stu-id="d65e8-115">This includes the number of users the policy was assigned to and the number of assignments completed, in progress, and not started.</span></span> <span data-ttu-id="d65e8-116">バッチ内のユーザーの一覧と、各ユーザーの状態と結果も表示されます。</span><span class="sxs-lookup"><span data-stu-id="d65e8-116">You'll also see the list of users in the batch, and the status and result for each user.</span></span> <span data-ttu-id="d65e8-117">以下は、実行例です。</span><span class="sxs-lookup"><span data-stu-id="d65e8-117">Here's an example:</span></span>

        ![のスクリーンショット](media/activity-log-policy-assignment-detail.png)

    - <span data-ttu-id="d65e8-119">**送信** 済み: ポリシーの割り当てが送信された日付と時刻。</span><span class="sxs-lookup"><span data-stu-id="d65e8-119">**Submitted**: Date and time the policy assignment was submitted.</span></span>
    - <span data-ttu-id="d65e8-120">**完了時刻**: ポリシーの割り当てが完了した日付と時刻。</span><span class="sxs-lookup"><span data-stu-id="d65e8-120">**Completion time**: Date and time the policy assignment was completed.</span></span>
    - <span data-ttu-id="d65e8-121">**影響:** バッチ内のユーザーの数。</span><span class="sxs-lookup"><span data-stu-id="d65e8-121">**Impact on**: Number of users in the batch.</span></span>
    - <span data-ttu-id="d65e8-122">**全体の状態**: ポリシー割り当ての状態。</span><span class="sxs-lookup"><span data-stu-id="d65e8-122">**Overall status**: Status of the policy assignment.</span></span>

> [!NOTE]
> <span data-ttu-id="d65e8-123">[ユーザー] ページからアクティビティ ログに **アクセス** することもできます。</span><span class="sxs-lookup"><span data-stu-id="d65e8-123">You can also get to the Activity log from the **Users** page.</span></span> <span data-ttu-id="d65e8-124">[適用] **を** クリックして一括ポリシーの割り当てを送信すると、ページの上部にバナーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d65e8-124">After you click **Apply** to submit a bulk policy assignment, you'll see a banner at the top of the page.</span></span> <span data-ttu-id="d65e8-125">バナーの **[アクティビティ ログ** ] リンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d65e8-125">Click the **Activity log** link in the banner.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d65e8-126">関連トピック</span><span class="sxs-lookup"><span data-stu-id="d65e8-126">Related topics</span></span>

- [<span data-ttu-id="d65e8-127">ユーザーにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="d65e8-127">Assign policies to users</span></span>](assign-policies.md)
