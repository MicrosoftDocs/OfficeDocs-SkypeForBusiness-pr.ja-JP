---
title: Shifts for Teams
description: チームでスケジュール管理ツールのシフトのセットアップと管理を行うために必要な管理ガイダンスを取得します。
ms.topic: conceptual
author: lanachin
ms.author: v-lanac
audience: admin
manager: serdars
f1.keywords:
- NOCSH
ms.date: 03/29/2019
ms.service: msteams
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 58b08faf39613d22747c16d04ead292e4242933b
ms.sourcegitcommit: b14ad0a6c454b20f34fccbd1d312de24379faef0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "46572307"
---
# <a name="shifts-for-teams"></a><span data-ttu-id="1bfc0-103">Shifts for Teams</span><span class="sxs-lookup"><span data-stu-id="1bfc0-103">Shifts for Teams</span></span>

<span data-ttu-id="1bfc0-104">チームは、組織内の最初のラインワーカーに、効率的にコミュニケーションや共同作業を行い、最善の作業を実行するために必要なツールを提供します。</span><span class="sxs-lookup"><span data-stu-id="1bfc0-104">Teams gives Firstline Workers in your organization the tools they need to communicate and collaborate effectively and do their best work.</span></span> <span data-ttu-id="1bfc0-105">ここでは、チームのスケジュール管理ツールであるシフトのセットアップと管理に必要な管理ガイダンスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="1bfc0-105">Here you'll find the admin guidance you need to set up and manage Shifts, the schedule management tool, in Teams.</span></span>

### <a name="set-up-and-manage-shifts-for-your-organization"></a><span data-ttu-id="1bfc0-106">組織のシフトを設定および管理する</span><span class="sxs-lookup"><span data-stu-id="1bfc0-106">Set up and manage Shifts for your organization</span></span>

|               |               |               |               |
| ------------- | ------------- | ------------- | ------------- |
|![タスク-チェックリスト-チームの計画](../media/task-checklist-planning-teams-small.svg) | <span data-ttu-id="1bfc0-108">**[組織内のシフトを管理する](/microsoftteams/expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams)**</span><span class="sxs-lookup"><span data-stu-id="1bfc0-108">**[Manage Shifts in your organization](/microsoftteams/expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams)**</span></span> |![design](../media/Help-small.svg)  | <span data-ttu-id="1bfc0-110">**[Firstline Worker のヘルプをシフトする](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b#PickTab=Specific_apps)**</span><span class="sxs-lookup"><span data-stu-id="1bfc0-110">**[Shifts Help for Firstline Workers](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b#PickTab=Specific_apps)**</span></span> |

### <a name="shifts-extensions"></a><span data-ttu-id="1bfc0-111">拡張機能のシフト</span><span class="sxs-lookup"><span data-stu-id="1bfc0-111">Shifts extensions</span></span>

|               |               |
| ------------- | ------------- |
| ![api](../media/api-small.svg) | <span data-ttu-id="1bfc0-113">**[シフトグラフ api](/graph/api/resources/shift?view=graph-rest-1.0)** グラフ Api をシフトすると、外部の労働力管理システムにシフトデータを統合し、バックエンドでカスタムシフトエクスペリエンスを柔軟に構築できるだけでなく、チームでの充実したフロントエンドエクスペリエンスをユーザーに提供できます。</span><span class="sxs-lookup"><span data-stu-id="1bfc0-113">**[Shift Graph APIs](/graph/api/resources/shift?view=graph-rest-1.0)** Shifts Graph APIs allow you to integrate Shifts data with external workforce management systems, providing you the flexibility to build custom Shifts experiences in the back end, while giving users a rich, front-end experience in Teams.</span></span>             |
| ![api](../media/api-small.svg) | <span data-ttu-id="1bfc0-115">**[労働力管理の統合](https://github.com/OfficeDev/Microsoft-Teams-Shifts-WFM-Connectors)** Kronos や JDA などのサードパーティの労働力管理システムを使っている場合、スケジュール、時刻、および出席については、オープンソースの統合を使用してシフトグラフ Api と SDK を使用して直接統合できます。</span><span class="sxs-lookup"><span data-stu-id="1bfc0-115">**[Workforce management integrations](https://github.com/OfficeDev/Microsoft-Teams-Shifts-WFM-Connectors)** If you're using third-party workforce management systems, such as Kronos and JDA, for scheduling, time, and attendance, you can integrate directly with Shifts through Shifts Graph APIs and SDK with open source integrations.</span></span> |
| ![api](../media/process-flow-teams-small.svg) | <span data-ttu-id="1bfc0-117">**[シフト + Power オートメーション](https://github.com/OfficeDev/Microsoft-Teams-Shifts-Power-Automate-Templates)** シフト + Power オートメーションを使うと、シフトから情報を取得したり、他のアプリと共にカスタムワークフローを作成したり、スケールで操作を実行したりできます。</span><span class="sxs-lookup"><span data-stu-id="1bfc0-117">**[Shifts + Power Automate](https://github.com/OfficeDev/Microsoft-Teams-Shifts-Power-Automate-Templates)** Shifts + Power Automate lets you take info from Shifts and create custom workflows with other apps and perform operations at scale.</span></span> <span data-ttu-id="1bfc0-118">わずかなコードを使わなくても、重要なプロセスを自動化できます。</span><span class="sxs-lookup"><span data-stu-id="1bfc0-118">Automate key processes with little to no code.</span></span> <span data-ttu-id="1bfc0-119">トリガーとテンプレートでは、管理者の承認が必要な場合に、シフト要求の自動承認を有効にするなど、さまざまなシナリオをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="1bfc0-119">The triggers and templates support a variety of scenarios such as enabling auto-approvals for shift requests when a manager’s approval isn't needed.</span></span> |

## <a name="featured-training"></a><span data-ttu-id="1bfc0-120">おすすめのトレーニング</span><span class="sxs-lookup"><span data-stu-id="1bfc0-120">Featured training</span></span>

|               |               |               |               |               |               |
| ------------- | ------------- | ------------- | ------------- | ------------- | ------------- |
| ![矢印-右 2-チーム](../media/arrow-right-2-teams-small.svg)  |  [<span data-ttu-id="1bfc0-122">ビデオ: シフトとは</span><span class="sxs-lookup"><span data-stu-id="1bfc0-122">Video: What is Shifts?</span></span>](https://support.office.com/article/what-is-shifts-f8efe6e4-ddb3-4d23-b81b-bb812296b821) |![出勤-チーム](../media/clock-teams-small.svg)  |  [<span data-ttu-id="1bfc0-124">ビデオ: シフトとは</span><span class="sxs-lookup"><span data-stu-id="1bfc0-124">Video: What is Shifts?</span></span>](https://support.office.com/article/create-a-shifts-schedule-2b94ca38-36db-4a1c-8fee-f8f0fec9a984) |![ブロック-teams](../media/blocks-teams-small.svg)  |  [<span data-ttu-id="1bfc0-126">ビデオ: シフトのスケジュールを管理する</span><span class="sxs-lookup"><span data-stu-id="1bfc0-126">Video: Manage a Shifts schedule</span></span>](https://support.office.com/article/manage-a-shifts-schedule-63acda7b-ea39-441a-b1c6-c404a72e79f7) |
