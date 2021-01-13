---
title: 応答グループのワークフロー
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.RgsWorkFlowMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: e4ee8abb-e1e5-413c-919d-cd3fb7193840
ROBOTS: NOINDEX, NOFOLLOW
description: 応答グループは、エージェント グループ、キュー、ワークフローで構成されます。 応答グループ ワークフローは、応答グループ アプリケーションが電話を受信するときに実行されるアクションを定義します。
ms.openlocfilehash: b4f9a80be55e00d5874c79cf426e331a464d0e2c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820267"
---
# <a name="response-groups-workflow"></a><span data-ttu-id="b1fd9-104">応答グループのワークフロー</span><span class="sxs-lookup"><span data-stu-id="b1fd9-104">Response Groups Workflow</span></span>

<span data-ttu-id="b1fd9-105">応答グループは、エージェント グループ、キュー、ワークフローで構成されます。</span><span class="sxs-lookup"><span data-stu-id="b1fd9-105">Response groups consist of agent groups, queues, and workflows.</span></span> <span data-ttu-id="b1fd9-106">応答グループ ワークフローは、応答グループ アプリケーションが電話を受信するときに実行されるアクションを定義します。</span><span class="sxs-lookup"><span data-stu-id="b1fd9-106">Response Group workflows define the actions that are taken when the Response Group application receives a phone call.</span></span>

<span data-ttu-id="b1fd9-107">[**応答グループ**  -  **のワークフロー]** ページには、組織に対して定義されている応答グループ ワークフローの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b1fd9-107">The **Response Groups** - **Workflow** page displays a list of all the Response Group workflows that are defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="b1fd9-108">実行できるタスク</span><span class="sxs-lookup"><span data-stu-id="b1fd9-108">Tasks you can perform</span></span>

<span data-ttu-id="b1fd9-109">[応答グループのワークフロー] ページから次 **のタスク**  -  **を実行** できます。</span><span class="sxs-lookup"><span data-stu-id="b1fd9-109">You can perform the following tasks from the **Response Groups** - **Workflow** page:</span></span>

- <span data-ttu-id="b1fd9-110">ハント グループ ワークフローの作成または変更</span><span class="sxs-lookup"><span data-stu-id="b1fd9-110">Create or change a hunt group workflow</span></span>

- <span data-ttu-id="b1fd9-111">対話ワークフローの作成または変更</span><span class="sxs-lookup"><span data-stu-id="b1fd9-111">Create or change an interactive workflow</span></span>

## <a name="ui-reference"></a><span data-ttu-id="b1fd9-112">UI リファレンス</span><span class="sxs-lookup"><span data-stu-id="b1fd9-112">UI Reference</span></span>

<span data-ttu-id="b1fd9-113">次の一覧に、このページのコマンドを示します。</span><span class="sxs-lookup"><span data-stu-id="b1fd9-113">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="b1fd9-114">**ワークフローを作成または編集する** ワークフローを作成または編集するための応答グループ構成ツールを開きます。</span><span class="sxs-lookup"><span data-stu-id="b1fd9-114">**Create or edit a workflow** Opens the Response Group Configuration Tool for creating or editing a workflow.</span></span>

- <span data-ttu-id="b1fd9-115">**更新** ワークフローの一覧を更新します。</span><span class="sxs-lookup"><span data-stu-id="b1fd9-115">**Refresh** Refreshes the list of workflows.</span></span>

<span data-ttu-id="b1fd9-116">次の一覧に、このページのフィールドを示します。</span><span class="sxs-lookup"><span data-stu-id="b1fd9-116">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="b1fd9-117">**名前** ワークフローに割り当てられる一意の名前。</span><span class="sxs-lookup"><span data-stu-id="b1fd9-117">**Name** The unique name that is assigned to the workflow.</span></span>

- <span data-ttu-id="b1fd9-118">**サービス** ワークフロー **をホストする ApplicationServer** サービス。</span><span class="sxs-lookup"><span data-stu-id="b1fd9-118">**Service** The **ApplicationServer** service that hosts the workflow.</span></span>

- <span data-ttu-id="b1fd9-119">**SIP アドレス** ワークフローへの呼び出しに応答するグループの SIP アドレス。</span><span class="sxs-lookup"><span data-stu-id="b1fd9-119">**SIP address** The SIP address of the group that will answer calls to the workflow.</span></span>

- <span data-ttu-id="b1fd9-120">**電話** この応答グループに到達するために呼び出される電話番号。</span><span class="sxs-lookup"><span data-stu-id="b1fd9-120">**Telephone** The phone number that is called to reach this response group.</span></span>

- <span data-ttu-id="b1fd9-121">**言語** 音声認識と音声合成に使用する言語。</span><span class="sxs-lookup"><span data-stu-id="b1fd9-121">**Language** The language that is used for speech recognition and text-to-speech.</span></span>

- <span data-ttu-id="b1fd9-122">**IVR** ワークフローがハント グループか対話型ワークフローかを示します。</span><span class="sxs-lookup"><span data-stu-id="b1fd9-122">**IVR** Indicates whether the workflow is a hunt group or an interactive workflow.</span></span>

- <span data-ttu-id="b1fd9-123">**有効** ワークフローが呼び出しを受信するためにアクティブ化されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="b1fd9-123">**Enabled** Indicates whether the workflow is activated to receive calls.</span></span>

<span data-ttu-id="b1fd9-124">応答グループの機能の詳細については、「計画」のドキュメントの [「Plan for the Response Group application in Skype for Business Server」](../../../plan-your-deployment/enterprise-voice-solution/response-group.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1fd9-124">For details about Response Group features and capabilities, see [Plan for the Response Group application in Skype for Business Server](../../../plan-your-deployment/enterprise-voice-solution/response-group.md) in the Planning documentation.</span></span> <span data-ttu-id="b1fd9-125">応答グループ ワークフローの操作の詳細については、「操作」のドキュメントの [「Managing Response Group Workflows」](https://technet.microsoft.com/library/42cfccdd-2844-4875-b4e3-813e1df15f08.aspx) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1fd9-125">For details about working with Response Group workflows, see [Managing Response Group Workflows](https://technet.microsoft.com/library/42cfccdd-2844-4875-b4e3-813e1df15f08.aspx) in the Operations documentation.</span></span>


