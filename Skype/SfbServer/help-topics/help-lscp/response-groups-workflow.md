---
title: 応答グループのワークフロー
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 応答グループは、エージェントグループ、キュー、ワークフローで構成されます。 応答グループワークフローは、応答グループアプリケーションが電話を受信したときに実行されるアクションを定義します。
ms.openlocfilehash: c190398d49770037358e9cde879f0e1649330703
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41822360"
---
# <a name="response-groups-workflow"></a><span data-ttu-id="2ab94-104">応答グループのワークフロー</span><span class="sxs-lookup"><span data-stu-id="2ab94-104">Response Groups Workflow</span></span>

<span data-ttu-id="2ab94-105">応答グループは、エージェントグループ、キュー、ワークフローで構成されます。</span><span class="sxs-lookup"><span data-stu-id="2ab94-105">Response groups consist of agent groups, queues, and workflows.</span></span> <span data-ttu-id="2ab94-106">応答グループワークフローは、応答グループアプリケーションが電話を受信したときに実行されるアクションを定義します。</span><span class="sxs-lookup"><span data-stu-id="2ab94-106">Response Group workflows define the actions that are taken when the Response Group application receives a phone call.</span></span>

<span data-ttu-id="2ab94-107">[**返信グループ** - ]**ワークフロー**ページには、組織で定義されているすべての応答グループワークフローの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2ab94-107">The **Response Groups** - **Workflow** page displays a list of all the Response Group workflows that are defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="2ab94-108">実行できるタスク</span><span class="sxs-lookup"><span data-stu-id="2ab94-108">Tasks you can perform</span></span>

<span data-ttu-id="2ab94-109">[**応答グループ** - ]**ワークフロー**ページでは、次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="2ab94-109">You can perform the following tasks from the **Response Groups** - **Workflow** page:</span></span>

- <span data-ttu-id="2ab94-110">ハントグループのワークフローを作成または変更する</span><span class="sxs-lookup"><span data-stu-id="2ab94-110">Create or change a hunt group workflow</span></span>

- <span data-ttu-id="2ab94-111">対話型ワークフローを作成または変更する</span><span class="sxs-lookup"><span data-stu-id="2ab94-111">Create or change an interactive workflow</span></span>

## <a name="ui-reference"></a><span data-ttu-id="2ab94-112">UI リファレンス</span><span class="sxs-lookup"><span data-stu-id="2ab94-112">UI Reference</span></span>

<span data-ttu-id="2ab94-113">次の一覧に、このページのコマンドを示します。</span><span class="sxs-lookup"><span data-stu-id="2ab94-113">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="2ab94-114">**ワークフローを作成または編集する**ワークフローを作成または編集するための応答グループ構成ツールを開きます。</span><span class="sxs-lookup"><span data-stu-id="2ab94-114">**Create or edit a workflow** Opens the Response Group Configuration Tool for creating or editing a workflow.</span></span>

- <span data-ttu-id="2ab94-115">**更新**ワークフローの一覧を更新します。</span><span class="sxs-lookup"><span data-stu-id="2ab94-115">**Refresh** Refreshes the list of workflows.</span></span>

<span data-ttu-id="2ab94-116">次の一覧に、このページのフィールドを示します。</span><span class="sxs-lookup"><span data-stu-id="2ab94-116">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="2ab94-117">**名前**ワークフローに割り当てられている一意の名前。</span><span class="sxs-lookup"><span data-stu-id="2ab94-117">**Name** The unique name that is assigned to the workflow.</span></span>

- <span data-ttu-id="2ab94-118">**サービス**ワークフローをホストしている**ApplicationServer**サービス。</span><span class="sxs-lookup"><span data-stu-id="2ab94-118">**Service** The **ApplicationServer** service that hosts the workflow.</span></span>

- <span data-ttu-id="2ab94-119">**SIP アドレス**ワークフローへの通話に応答するグループの SIP アドレス。</span><span class="sxs-lookup"><span data-stu-id="2ab94-119">**SIP address** The SIP address of the group that will answer calls to the workflow.</span></span>

- <span data-ttu-id="2ab94-120">**電話**この応答グループに到達するために呼び出される電話番号。</span><span class="sxs-lookup"><span data-stu-id="2ab94-120">**Telephone** The phone number that is called to reach this response group.</span></span>

- <span data-ttu-id="2ab94-121">**言語**音声認識と音声合成で使用される言語。</span><span class="sxs-lookup"><span data-stu-id="2ab94-121">**Language** The language that is used for speech recognition and text-to-speech.</span></span>

- <span data-ttu-id="2ab94-122">**IVR**ワークフローがハントグループであるか、対話型ワークフローであるかを示します。</span><span class="sxs-lookup"><span data-stu-id="2ab94-122">**IVR** Indicates whether the workflow is a hunt group or an interactive workflow.</span></span>

- <span data-ttu-id="2ab94-123">**有効**呼び出しを受けるためにワークフローがアクティブ化されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="2ab94-123">**Enabled** Indicates whether the workflow is activated to receive calls.</span></span>

<span data-ttu-id="2ab94-124">回答グループの機能と機能の詳細については、計画ドキュメントの「 [Skype For Business Server 2015 での応答グループアプリケーションの計画](../../plan-your-deployment/enterprise-voice-solution/response-group.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ab94-124">For details about Response Group features and capabilities, see [Plan for the Response Group application in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/response-group.md) in the Planning documentation.</span></span> <span data-ttu-id="2ab94-125">回答グループワークフローの操作の詳細については、「操作のドキュメントで[回答グループのワークフローを管理する](https://technet.microsoft.com/library/42cfccdd-2844-4875-b4e3-813e1df15f08.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ab94-125">For details about working with Response Group workflows, see [Managing Response Group Workflows](https://technet.microsoft.com/library/42cfccdd-2844-4875-b4e3-813e1df15f08.aspx) in the Operations documentation.</span></span>


