---
title: Shifts for Teams
description: Teams でシフト (スケジュール管理ツール) を設定および管理するために必要な管理者ガイダンスを取得します。
ms.topic: conceptual
author: cichur
ms.author: v-cichur
audience: admin
manager: serdars
f1.keywords:
- NOCSH
ms.date: 03/29/2019
ms.service: msteams
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
- microsoftcloud-healthcare
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-jun2020
ms.openlocfilehash: f699b60bddba6bcf5ffa884760540e5c20378f81
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909221"
---
# <a name="shifts-for-teams"></a><span data-ttu-id="418c1-103">Shifts for Teams</span><span class="sxs-lookup"><span data-stu-id="418c1-103">Shifts for Teams</span></span>

<span data-ttu-id="418c1-104">Teams は、組織内の Frontline Worker に、通信や共同作業に必要なツールを効果的に提供します。</span><span class="sxs-lookup"><span data-stu-id="418c1-104">Teams gives Frontline Workers in your organization the tools they need to communicate and collaborate effectively.</span></span> <span data-ttu-id="418c1-105">この記事では、セットアップと管理の方法について示します。</span><span class="sxs-lookup"><span data-stu-id="418c1-105">This article shows you how to set up and manage.</span></span> <span data-ttu-id="418c1-106">Teams でシフトし、スケジュール管理ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="418c1-106">Shifts and use the schedule management tool in Teams.</span></span>

### <a name="set-up-and-manage-shifts-for-your-organization"></a><span data-ttu-id="418c1-107">組織のシフトを設定および管理する</span><span class="sxs-lookup"><span data-stu-id="418c1-107">Set up and manage Shifts for your organization</span></span>

|               |               |               |               |
| ------------- | ------------- | ------------- | ------------- |
|![task-checklist-planning-teams](../media/task-checklist-planning-teams-small.svg) | <span data-ttu-id="418c1-109">**[組織内のシフトを管理する](/microsoftteams/expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams)**</span><span class="sxs-lookup"><span data-stu-id="418c1-109">**[Manage Shifts in your organization](/microsoftteams/expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams)**</span></span> |![デザイン](../media/Help-small.svg)  | <span data-ttu-id="418c1-111">**[最前線の従業員向けシフト ヘルプ](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b#PickTab=Specific_apps)**</span><span class="sxs-lookup"><span data-stu-id="418c1-111">**[Shifts Help for Frontline Workers](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b#PickTab=Specific_apps)**</span></span> |

### <a name="shifts-extensions"></a><span data-ttu-id="418c1-112">Shifts 拡張機能</span><span class="sxs-lookup"><span data-stu-id="418c1-112">Shifts extensions</span></span>

|               |               |
| ------------- | ------------- |
| ![api](../media/api-small.svg) | <span data-ttu-id="418c1-114">**[Shift Graph API](/graph/api/resources/shift?view=graph-rest-1.0)** Shifts Graph API を使用すると、Shifts データを外部の従業員管理システムと統合できます。</span><span class="sxs-lookup"><span data-stu-id="418c1-114">**[Shift Graph APIs](/graph/api/resources/shift?view=graph-rest-1.0)** Shifts Graph APIs allow you to integrate Shifts data with external workforce management systems.</span></span> <span data-ttu-id="418c1-115">カスタム の Shifts エクスペリエンスをバック エンドで柔軟に構築できる一方で、ユーザーは Teams での豊富なフロントエンド エクスペリエンスを提供できます。</span><span class="sxs-lookup"><span data-stu-id="418c1-115">You'll have the flexibility to build custom Shifts experiences in the back end, while giving users a rich, front-end experience in Teams.</span></span>             |
| ![api](../media/api-small.svg) | <span data-ttu-id="418c1-117">**[従業員管理の統合](https://github.com/OfficeDev/Microsoft-Teams-Shifts-WFM-Connectors)** スケジュール、時間、出席のために、クロノや JDA などのサードパーティの人員管理システムを使用している場合は、Shifts Graph API と SDK を使用して、オープン ソース統合を使用して、Shifts と直接統合できます。</span><span class="sxs-lookup"><span data-stu-id="418c1-117">**[Workforce management integrations](https://github.com/OfficeDev/Microsoft-Teams-Shifts-WFM-Connectors)** If you're using third-party workforce management systems, such as Kronos and JDA, for scheduling, time, and attendance, you can integrate directly with Shifts through Shifts Graph APIs and SDK with open source integrations.</span></span> |
| ![api](../media/process-flow-teams-small.svg) | <span data-ttu-id="418c1-119">**[Shifts + Power Automate](https://github.com/OfficeDev/Microsoft-Teams-Shifts-Power-Automate-Templates)** Shifts + Power Automate を使用すると、Shifts から情報を取得し、他のアプリでカスタム ワークフローを作成し、大規模な操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="418c1-119">**[Shifts + Power Automate](https://github.com/OfficeDev/Microsoft-Teams-Shifts-Power-Automate-Templates)** Shifts + Power Automate lets you take info from Shifts and create custom workflows with other apps and perform operations at scale.</span></span> <span data-ttu-id="418c1-120">主要なプロセスをほとんど、または何もコードを使って自動化する。</span><span class="sxs-lookup"><span data-stu-id="418c1-120">Automate key processes with little to no code.</span></span> <span data-ttu-id="418c1-121">トリガーとテンプレートは、マネージャーの承認が不要な場合にシフト要求の自動承認を有効にするなどのさまざまなシナリオをサポートします。</span><span class="sxs-lookup"><span data-stu-id="418c1-121">The triggers and templates support a variety of scenarios such as enabling auto-approvals for shift requests when a manager’s approval isn't needed.</span></span> |

## <a name="featured-training"></a><span data-ttu-id="418c1-122">おすすめのトレーニング</span><span class="sxs-lookup"><span data-stu-id="418c1-122">Featured training</span></span>

|               |               |               |               |               |               |
| ------------- | ------------- | ------------- | ------------- | ------------- | ------------- |
| ![arrow-right-2-teams](../media/arrow-right-2-teams-small.svg)  |  [<span data-ttu-id="418c1-124">ビデオ: Shifts とは</span><span class="sxs-lookup"><span data-stu-id="418c1-124">Video: What is Shifts?</span></span>](https://support.office.com/article/what-is-shifts-f8efe6e4-ddb3-4d23-b81b-bb812296b821) |![クロック チーム](../media/clock-teams-small.svg)  |  [<span data-ttu-id="418c1-126">ビデオ: Shifts とは</span><span class="sxs-lookup"><span data-stu-id="418c1-126">Video: What is Shifts?</span></span>](https://support.office.com/article/create-a-shifts-schedule-2b94ca38-36db-4a1c-8fee-f8f0fec9a984) |![blocks-teams](../media/blocks-teams-small.svg)  |  [<span data-ttu-id="418c1-128">ビデオ: シフトスケジュールを管理する</span><span class="sxs-lookup"><span data-stu-id="418c1-128">Video: Manage a Shifts schedule</span></span>](https://support.office.com/article/manage-a-shifts-schedule-63acda7b-ea39-441a-b1c6-c404a72e79f7) |
