---
title: 応答グループのワークフロー
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
- ms.lync.lscp.RgsWorkFlowMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e4ee8abb-e1e5-413c-919d-cd3fb7193840
description: 応答グループは、エージェント グループ、キュー、ワークフローで構成されます。 応答グループ のワークフローは、応答グループ アプリケーションが電話を受け取った場合に実行されるアクションを定義します。
ms.openlocfilehash: d5ab0f197817a5905df54e236db10a3d526685bd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122531"
---
# <a name="response-groups-workflow"></a><span data-ttu-id="4a114-104">応答グループのワークフロー</span><span class="sxs-lookup"><span data-stu-id="4a114-104">Response Groups Workflow</span></span>

<span data-ttu-id="4a114-105">応答グループは、エージェント グループ、キュー、ワークフローで構成されます。</span><span class="sxs-lookup"><span data-stu-id="4a114-105">Response groups consist of agent groups, queues, and workflows.</span></span> <span data-ttu-id="4a114-106">応答グループ のワークフローは、応答グループ アプリケーションが電話を受け取った場合に実行されるアクションを定義します。</span><span class="sxs-lookup"><span data-stu-id="4a114-106">Response Group workflows define the actions that are taken when the Response Group application receives a phone call.</span></span>

<span data-ttu-id="4a114-107">[**応答グループのワークフロー**] ページには、組織に対して定義されているすべての応答グループ  -  ワークフローの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4a114-107">The **Response Groups** - **Workflow** page displays a list of all the Response Group workflows that are defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="4a114-108">実行できるタスク</span><span class="sxs-lookup"><span data-stu-id="4a114-108">Tasks you can perform</span></span>

<span data-ttu-id="4a114-109">[応答グループのワークフロー] ページから次 **のタスク**  -  **を実行** できます。</span><span class="sxs-lookup"><span data-stu-id="4a114-109">You can perform the following tasks from the **Response Groups** - **Workflow** page:</span></span>

- <span data-ttu-id="4a114-110">ハント グループ ワークフローの作成または変更</span><span class="sxs-lookup"><span data-stu-id="4a114-110">Create or change a hunt group workflow</span></span>

- <span data-ttu-id="4a114-111">対話ワークフローの作成または変更</span><span class="sxs-lookup"><span data-stu-id="4a114-111">Create or change an interactive workflow</span></span>

## <a name="ui-reference"></a><span data-ttu-id="4a114-112">UI リファレンス</span><span class="sxs-lookup"><span data-stu-id="4a114-112">UI Reference</span></span>

<span data-ttu-id="4a114-113">次の一覧に、このページのコマンドを示します。</span><span class="sxs-lookup"><span data-stu-id="4a114-113">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="4a114-114">**ワークフローを作成または編集する** ワークフローを作成または編集するための応答グループ構成ツールを開きます。</span><span class="sxs-lookup"><span data-stu-id="4a114-114">**Create or edit a workflow** Opens the Response Group Configuration Tool for creating or editing a workflow.</span></span>

- <span data-ttu-id="4a114-115">**更新** ワークフローの一覧を更新します。</span><span class="sxs-lookup"><span data-stu-id="4a114-115">**Refresh** Refreshes the list of workflows.</span></span>

<span data-ttu-id="4a114-116">次の一覧に、このページのフィールドを示します。</span><span class="sxs-lookup"><span data-stu-id="4a114-116">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="4a114-117">**名前** ワークフローに割り当てられている一意の名前。</span><span class="sxs-lookup"><span data-stu-id="4a114-117">**Name** The unique name that is assigned to the workflow.</span></span>

- <span data-ttu-id="4a114-118">**サービス** ワークフロー **をホストする ApplicationServer** サービス。</span><span class="sxs-lookup"><span data-stu-id="4a114-118">**Service** The **ApplicationServer** service that hosts the workflow.</span></span>

- <span data-ttu-id="4a114-119">**SIP アドレス** ワークフローへの呼び出しに応答するグループの SIP アドレス。</span><span class="sxs-lookup"><span data-stu-id="4a114-119">**SIP address** The SIP address of the group that will answer calls to the workflow.</span></span>

- <span data-ttu-id="4a114-120">**電話** この応答グループに到達するために呼び出される電話番号。</span><span class="sxs-lookup"><span data-stu-id="4a114-120">**Telephone** The phone number that is called to reach this response group.</span></span>

- <span data-ttu-id="4a114-121">**言語** 音声認識と音声合成に使用される言語。</span><span class="sxs-lookup"><span data-stu-id="4a114-121">**Language** The language that is used for speech recognition and text-to-speech.</span></span>

- <span data-ttu-id="4a114-122">**IVR** ワークフローがハント グループか対話型ワークフローかを示します。</span><span class="sxs-lookup"><span data-stu-id="4a114-122">**IVR** Indicates whether the workflow is a hunt group or an interactive workflow.</span></span>

- <span data-ttu-id="4a114-123">**有効** ワークフローがアクティブ化され、呼び出しを受信するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="4a114-123">**Enabled** Indicates whether the workflow is activated to receive calls.</span></span>

<span data-ttu-id="4a114-124">応答グループの機能の詳細については、「計画」のドキュメントの「Plan for the Response Group application [in Skype for Business Server 2015」](../../plan-your-deployment/enterprise-voice-solution/response-group.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a114-124">For details about Response Group features and capabilities, see [Plan for the Response Group application in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/response-group.md) in the Planning documentation.</span></span> <span data-ttu-id="4a114-125">応答グループ ワークフローの操作の詳細については、「操作」のドキュメントの「 [応答グループ ワークフロー](/previous-versions/office/lync-server-2013/lync-server-2013-managing-response-group-workflows) の管理」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a114-125">For details about working with Response Group workflows, see [Managing Response Group Workflows](/previous-versions/office/lync-server-2013/lync-server-2013-managing-response-group-workflows) in the Operations documentation.</span></span>