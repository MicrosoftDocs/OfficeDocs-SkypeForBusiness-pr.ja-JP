---
title: Shifts for Teams
description: スケジュール管理ツールである Shifts を設定および管理するために必要な管理者ガイダンスをTeams。
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
ms.openlocfilehash: 889c3f4149489f6bcea44acde93d897a7f2e50e1
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092555"
---
# <a name="shifts-for-teams"></a><span data-ttu-id="606f9-103">Shifts for Teams</span><span class="sxs-lookup"><span data-stu-id="606f9-103">Shifts for Teams</span></span>

<span data-ttu-id="606f9-104">Teams、組織内の Frontline Worker に、効果的にコミュニケーションと共同作業を行う必要があるツールを提供します。</span><span class="sxs-lookup"><span data-stu-id="606f9-104">Teams gives Frontline Workers in your organization the tools they need to communicate and collaborate effectively.</span></span> <span data-ttu-id="606f9-105">この記事では、設定と管理の方法について示します。</span><span class="sxs-lookup"><span data-stu-id="606f9-105">This article shows you how to set up and manage.</span></span> <span data-ttu-id="606f9-106">シフトして、スケジュール管理ツールを使用Teams。</span><span class="sxs-lookup"><span data-stu-id="606f9-106">Shifts and use the schedule management tool in Teams.</span></span>

### <a name="set-up-and-manage-shifts-for-your-organization"></a><span data-ttu-id="606f9-107">組織のシフトを設定して管理する</span><span class="sxs-lookup"><span data-stu-id="606f9-107">Set up and manage Shifts for your organization</span></span>

|               |               |               |               |
| ------------- | ------------- | ------------- | ------------- |
|![task-checklist-planning-teams](../media/task-checklist-planning-teams-small.svg) | <span data-ttu-id="606f9-109">**[組織内のシフトを管理する](./shifts/manage-the-shifts-app-for-your-organization-in-teams.md)**</span><span class="sxs-lookup"><span data-stu-id="606f9-109">**[Manage Shifts in your organization](./shifts/manage-the-shifts-app-for-your-organization-in-teams.md)**</span></span> |![デザイン](../media/Help-small.svg)  | <span data-ttu-id="606f9-111">**[現場担当者向けのシフトのヘルプ](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b#PickTab=Specific_apps)**</span><span class="sxs-lookup"><span data-stu-id="606f9-111">**[Shifts Help for Frontline Workers](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b#PickTab=Specific_apps)**</span></span> |

### <a name="shifts-extensions"></a><span data-ttu-id="606f9-112">拡張機能をシフトする</span><span class="sxs-lookup"><span data-stu-id="606f9-112">Shifts extensions</span></span>

|               |               |
| ------------- | ------------- |
| ![api](../media/api-small.svg) | <span data-ttu-id="606f9-114">**[Shift Graph API](/graph/api/resources/shift?view=graph-rest-1.0)** Shifts Graph API を使用すると、Shifts データを外部の従業員管理システムと統合できます。</span><span class="sxs-lookup"><span data-stu-id="606f9-114">**[Shift Graph APIs](/graph/api/resources/shift?view=graph-rest-1.0)** Shifts Graph APIs allow you to integrate Shifts data with external workforce management systems.</span></span> <span data-ttu-id="606f9-115">ユーザーは、カスタムの Shifts エクスペリエンスをバック エンドで柔軟に構築できる一方で、Teams で豊富なフロントエンド エクスペリエンスをユーザーに提供できます。</span><span class="sxs-lookup"><span data-stu-id="606f9-115">You'll have the flexibility to build custom Shifts experiences in the back end, while giving users a rich, front-end experience in Teams.</span></span>             |
| ![api](../media/api-small.svg) | <span data-ttu-id="606f9-117">**[従業員管理の統合](https://github.com/OfficeDev/Microsoft-Teams-Shifts-WFM-Connectors)** スケジュール、時間、出席に Kronos や JDA などのサード パーティの従業員管理システムを使用している場合は、Shifts Graph API と SDK を使用してオープン ソース統合を使用して、Shifts と直接統合できます。</span><span class="sxs-lookup"><span data-stu-id="606f9-117">**[Workforce management integrations](https://github.com/OfficeDev/Microsoft-Teams-Shifts-WFM-Connectors)** If you're using third-party workforce management systems, such as Kronos and JDA, for scheduling, time, and attendance, you can integrate directly with Shifts through Shifts Graph APIs and SDK with open source integrations.</span></span> |
| ![api](../media/process-flow-teams-small.svg) | <span data-ttu-id="606f9-119">**[Shifts + Power Automate](https://github.com/OfficeDev/Microsoft-Teams-Shifts-Power-Automate-Templates)** Shift + Power Automateを使用すると、Shifts から情報を取得し、他のアプリとカスタム ワークフローを作成し、大規模な操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="606f9-119">**[Shifts + Power Automate](https://github.com/OfficeDev/Microsoft-Teams-Shifts-Power-Automate-Templates)** Shifts + Power Automate lets you take info from Shifts and create custom workflows with other apps and perform operations at scale.</span></span> <span data-ttu-id="606f9-120">コードをほとんどまたは一緒に使用して、主要なプロセスを自動化します。</span><span class="sxs-lookup"><span data-stu-id="606f9-120">Automate key processes with little to no code.</span></span> <span data-ttu-id="606f9-121">トリガーとテンプレートは、マネージャーの承認が不要な場合にシフト要求の自動承認を有効にするなど、さまざまなシナリオをサポートします。</span><span class="sxs-lookup"><span data-stu-id="606f9-121">The triggers and templates support a variety of scenarios such as enabling auto-approvals for shift requests when a manager’s approval isn't needed.</span></span> |

## <a name="featured-training"></a><span data-ttu-id="606f9-122">おすすめのトレーニング</span><span class="sxs-lookup"><span data-stu-id="606f9-122">Featured training</span></span>

|               |               |               |               |               |               |
| ------------- | ------------- | ------------- | ------------- | ------------- | ------------- |
| ![arrow-right-2-teams](../media/arrow-right-2-teams-small.svg)  |  [<span data-ttu-id="606f9-124">ビデオ: Shifts とは</span><span class="sxs-lookup"><span data-stu-id="606f9-124">Video: What is Shifts?</span></span>](https://support.office.com/article/what-is-shifts-f8efe6e4-ddb3-4d23-b81b-bb812296b821) |![clock-teams](../media/clock-teams-small.svg)  |  [<span data-ttu-id="606f9-126">ビデオ: Shifts とは</span><span class="sxs-lookup"><span data-stu-id="606f9-126">Video: What is Shifts?</span></span>](https://support.office.com/article/create-a-shifts-schedule-2b94ca38-36db-4a1c-8fee-f8f0fec9a984) |![blocks-teams](../media/blocks-teams-small.svg)  |  [<span data-ttu-id="606f9-128">ビデオ: シフト スケジュールを管理する</span><span class="sxs-lookup"><span data-stu-id="606f9-128">Video: Manage a Shifts schedule</span></span>](https://support.office.com/article/manage-a-shifts-schedule-63acda7b-ea39-441a-b1c6-c404a72e79f7) |