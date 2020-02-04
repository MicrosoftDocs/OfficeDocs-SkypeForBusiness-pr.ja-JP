---
title: 応答グループのキュー
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.RgsQueueMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 29bde940-6107-494f-9bee-b6ebfa135e41
description: 応答グループは、エージェントグループ、キュー、ワークフローで構成されます。 応答グループキューは、エージェントが通話に応答するまで、応答グループへの呼び出しを保持します。
ms.openlocfilehash: 0f18c9c69fd78c8b4b3d9a5b667534cc398bc6e8
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41686020"
---
# <a name="response-groups-queue"></a><span data-ttu-id="17e7e-104">応答グループのキュー</span><span class="sxs-lookup"><span data-stu-id="17e7e-104">Response Groups Queue</span></span>

<span data-ttu-id="17e7e-105">応答グループは、エージェントグループ、キュー、ワークフローで構成されます。</span><span class="sxs-lookup"><span data-stu-id="17e7e-105">Response groups consist of agent groups, queues, and workflows.</span></span> <span data-ttu-id="17e7e-106">応答グループキューは、エージェントが通話に応答するまで、応答グループへの呼び出しを保持します。</span><span class="sxs-lookup"><span data-stu-id="17e7e-106">Response Group queues hold calls to a response group until an agent answers the call.</span></span>

<span data-ttu-id="17e7e-107">[**応答グループ** - **キュー** ] ページには、組織で定義されているすべての応答グループキューの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="17e7e-107">The **Response Groups** - **Queue** page displays a list of all the Response Group queues that are defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="17e7e-108">実行できるタスク</span><span class="sxs-lookup"><span data-stu-id="17e7e-108">Tasks you can perform</span></span>

<span data-ttu-id="17e7e-109">[**応答グループ** - ]**キュー**ページでは、次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="17e7e-109">You can perform the following tasks from the **Response Groups** - **Queue** page:</span></span>

- <span data-ttu-id="17e7e-110">新しいキューを作成する</span><span class="sxs-lookup"><span data-stu-id="17e7e-110">Create a new queue</span></span>

- <span data-ttu-id="17e7e-111">既存のキューを変更する</span><span class="sxs-lookup"><span data-stu-id="17e7e-111">Change an existing queue</span></span>

- <span data-ttu-id="17e7e-112">キューを削除する</span><span class="sxs-lookup"><span data-stu-id="17e7e-112">Delete a queue</span></span>

## <a name="ui-reference"></a><span data-ttu-id="17e7e-113">UI リファレンス</span><span class="sxs-lookup"><span data-stu-id="17e7e-113">UI Reference</span></span>

<span data-ttu-id="17e7e-114">次の一覧に、このページのコマンドを示します。</span><span class="sxs-lookup"><span data-stu-id="17e7e-114">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="17e7e-115">**新規**新しいキューを開始します。</span><span class="sxs-lookup"><span data-stu-id="17e7e-115">**New** Starts a new queue.</span></span>

- <span data-ttu-id="17e7e-116">**編集**選択したキューを開いて編集するか、リスト内のすべてのキューを選択するか、選択したキューを削除します。</span><span class="sxs-lookup"><span data-stu-id="17e7e-116">**Edit** Opens the selected queue to edit it, selects all queue in the list, or deletes the selected queue.</span></span>

- <span data-ttu-id="17e7e-117">**更新**キューの一覧を更新します。</span><span class="sxs-lookup"><span data-stu-id="17e7e-117">**Refresh** Refreshes the list of queues.</span></span>

<span data-ttu-id="17e7e-118">次の一覧に、このページのフィールドを示します。</span><span class="sxs-lookup"><span data-stu-id="17e7e-118">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="17e7e-119">**名前**キューを識別する一意の名前。</span><span class="sxs-lookup"><span data-stu-id="17e7e-119">**Name** The unique name that identifies the queue.</span></span>

- <span data-ttu-id="17e7e-120">**サービス**キューをホストしている**ApplicationServer**サービス。</span><span class="sxs-lookup"><span data-stu-id="17e7e-120">**Service** The **ApplicationServer** service that hosts the queue.</span></span>

- <span data-ttu-id="17e7e-121">**説明**キューの説明。</span><span class="sxs-lookup"><span data-stu-id="17e7e-121">**Description** The description for the queue.</span></span>

<span data-ttu-id="17e7e-122">回答グループの機能と機能の詳細については、計画ドキュメントの「 [Skype For Business Server 2015 での応答グループアプリケーションの計画](../../plan-your-deployment/enterprise-voice-solution/response-group.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="17e7e-122">For details about Response Group features and capabilities, see [Plan for the Response Group application in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/response-group.md) in the Planning documentation.</span></span> <span data-ttu-id="17e7e-123">回答グループキューの操作の詳細については、「操作のドキュメントで[回答グループキューを管理する](https://technet.microsoft.com/library/1e91720c-ab67-4dfb-b30c-0ef2a8012310.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="17e7e-123">For details about working with Response Group queues, see [Managing Response Group Queues](https://technet.microsoft.com/library/1e91720c-ab67-4dfb-b30c-0ef2a8012310.aspx) in the Operations documentation.</span></span>


