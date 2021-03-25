---
title: 応答グループのキュー
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.RgsQueueMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 29bde940-6107-494f-9bee-b6ebfa135e41
description: 応答グループは、エージェント グループ、キュー、ワークフローで構成されます。 応答グループ キューは、エージェントが通話に応答するまで、応答グループへの呼び出しを保持します。
ms.openlocfilehash: 4b0b4e4f34c8297702b110fea2c8aae55bb39d2a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122541"
---
# <a name="response-groups-queue"></a><span data-ttu-id="bf2c6-104">応答グループのキュー</span><span class="sxs-lookup"><span data-stu-id="bf2c6-104">Response Groups Queue</span></span>

<span data-ttu-id="bf2c6-105">応答グループは、エージェント グループ、キュー、ワークフローで構成されます。</span><span class="sxs-lookup"><span data-stu-id="bf2c6-105">Response groups consist of agent groups, queues, and workflows.</span></span> <span data-ttu-id="bf2c6-106">応答グループ キューは、エージェントが通話に応答するまで、応答グループへの呼び出しを保持します。</span><span class="sxs-lookup"><span data-stu-id="bf2c6-106">Response Group queues hold calls to a response group until an agent answers the call.</span></span>

<span data-ttu-id="bf2c6-107">[**応答グループ キュー**] ページには、組織に対して定義されているすべての応答グループ  -  キューの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="bf2c6-107">The **Response Groups** - **Queue** page displays a list of all the Response Group queues that are defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="bf2c6-108">実行できるタスク</span><span class="sxs-lookup"><span data-stu-id="bf2c6-108">Tasks you can perform</span></span>

<span data-ttu-id="bf2c6-109">[応答グループ キュー] ページから次の **タスク**  -  **を実行** できます。</span><span class="sxs-lookup"><span data-stu-id="bf2c6-109">You can perform the following tasks from the **Response Groups** - **Queue** page:</span></span>

- <span data-ttu-id="bf2c6-110">新しいキューを作成する</span><span class="sxs-lookup"><span data-stu-id="bf2c6-110">Create a new queue</span></span>

- <span data-ttu-id="bf2c6-111">既存のキューを変更する</span><span class="sxs-lookup"><span data-stu-id="bf2c6-111">Change an existing queue</span></span>

- <span data-ttu-id="bf2c6-112">キューを削除する</span><span class="sxs-lookup"><span data-stu-id="bf2c6-112">Delete a queue</span></span>

## <a name="ui-reference"></a><span data-ttu-id="bf2c6-113">UI リファレンス</span><span class="sxs-lookup"><span data-stu-id="bf2c6-113">UI Reference</span></span>

<span data-ttu-id="bf2c6-114">次の一覧に、このページのコマンドを示します。</span><span class="sxs-lookup"><span data-stu-id="bf2c6-114">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="bf2c6-115">**New** 新しいキューを開始します。</span><span class="sxs-lookup"><span data-stu-id="bf2c6-115">**New** Starts a new queue.</span></span>

- <span data-ttu-id="bf2c6-116">**編集** 選択したキューを開き、それを編集するか、リスト内のすべてのキューを選択するか、選択したキューを削除します。</span><span class="sxs-lookup"><span data-stu-id="bf2c6-116">**Edit** Opens the selected queue to edit it, selects all queue in the list, or deletes the selected queue.</span></span>

- <span data-ttu-id="bf2c6-117">**更新** キューの一覧を更新します。</span><span class="sxs-lookup"><span data-stu-id="bf2c6-117">**Refresh** Refreshes the list of queues.</span></span>

<span data-ttu-id="bf2c6-118">次の一覧に、このページのフィールドを示します。</span><span class="sxs-lookup"><span data-stu-id="bf2c6-118">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="bf2c6-119">**名前** キューを識別する一意の名前。</span><span class="sxs-lookup"><span data-stu-id="bf2c6-119">**Name** The unique name that identifies the queue.</span></span>

- <span data-ttu-id="bf2c6-120">**サービス** キュー **をホストする ApplicationServer** サービス。</span><span class="sxs-lookup"><span data-stu-id="bf2c6-120">**Service** The **ApplicationServer** service that hosts the queue.</span></span>

- <span data-ttu-id="bf2c6-121">**説明** キューの説明。</span><span class="sxs-lookup"><span data-stu-id="bf2c6-121">**Description** The description for the queue.</span></span>

<span data-ttu-id="bf2c6-122">応答グループの機能の詳細については、「計画」のドキュメントの「Plan for the Response Group application [in Skype for Business Server 2015」](../../plan-your-deployment/enterprise-voice-solution/response-group.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bf2c6-122">For details about Response Group features and capabilities, see [Plan for the Response Group application in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/response-group.md) in the Planning documentation.</span></span> <span data-ttu-id="bf2c6-123">応答グループ キューの操作の詳細については、「操作」のドキュメントの「 [応答グループ キューの管理](/previous-versions/office/lync-server-2013/lync-server-2013-managing-response-group-queues) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bf2c6-123">For details about working with Response Group queues, see [Managing Response Group Queues](/previous-versions/office/lync-server-2013/lync-server-2013-managing-response-group-queues) in the Operations documentation.</span></span>