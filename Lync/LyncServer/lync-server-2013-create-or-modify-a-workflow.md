---
title: 'Lync Server 2013: ワークフローを作成または変更する'
description: 'Lync Server 2013: ワークフローを作成または変更します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a workflow
ms:assetid: 5ac1c0f3-e82f-40ca-b972-91950e38c05b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520997(v=OCS.15)
ms:contentKeyID: 48184225
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 053b80e313e497313e613a5f8b16bd5beeabf7ac
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574473"
---
# <a name="create-or-modify-a-workflow-in-lync-server-2013"></a><span data-ttu-id="48c3b-103">Lync Server 2013 でのワークフローの作成または変更</span><span class="sxs-lookup"><span data-stu-id="48c3b-103">Create or modify a workflow in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="48c3b-104">_**トピックの最終更新日:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="48c3b-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="48c3b-105">Lync Server 2013 は、ハントグループと対話型音声応答 (IVR) の2種類のワークフローをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="48c3b-105">Lync Server 2013 supports two types of workflows: hunt group and interactive voice response (IVR).</span></span> <span data-ttu-id="48c3b-106">ワークフローを作成するときは、応答グループ構成ツールを使用して、使用するキューおよび開始メッセージ、保留音、営業時間、質問などの設定を指定します。これには、応答グループアプリケーションが発信者に要求します。</span><span class="sxs-lookup"><span data-stu-id="48c3b-106">When you create a workflow, you use the Response Group Configuration Tool to specify the queue to use and other settings, such as a welcome message, music on hold, business hours, and questions that the Response Group application asks the caller.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="48c3b-p102">エージェント グループとキューは、これらを使用するワークフローの作成前に作成しておく必要があります。複数のワークフローに使用できる事前定義された営業時間と休日を作成する場合は、これらを使用するワークフローの作成前に、この営業時間と休日も定義しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="48c3b-p102">You must create agent groups and queues before you create a workflow that uses them. If you want to create predefined business hours and holidays that you can use for multiple workflows, you must also define these hours and holidays before you create a workflow that uses them.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="48c3b-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="48c3b-109">In This Section</span></span>

  - [<span data-ttu-id="48c3b-110">Lync Server 2013 でハントグループワークフローを作成または変更する</span><span class="sxs-lookup"><span data-stu-id="48c3b-110">Create or modify a hunt group workflow in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-hunt-group-workflow.md)

  - [<span data-ttu-id="48c3b-111">Lync Server 2013 での対話ワークフローの作成または変更</span><span class="sxs-lookup"><span data-stu-id="48c3b-111">Create or modify an interactive workflow in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-interactive-workflow.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="48c3b-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="48c3b-112">See Also</span></span>


[<span data-ttu-id="48c3b-113">Lync Server 2013 でエージェントグループを作成または変更する</span><span class="sxs-lookup"><span data-stu-id="48c3b-113">Create or modify an agent group in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-agent-group.md)  
[<span data-ttu-id="48c3b-114">Lync Server 2013 でキューを作成または変更する</span><span class="sxs-lookup"><span data-stu-id="48c3b-114">Create or modify a queue in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-queue.md)  
[<span data-ttu-id="48c3b-115">オプションLync Server 2013 で応答グループの休日セットを定義する</span><span class="sxs-lookup"><span data-stu-id="48c3b-115">(Optional) Define Response Group holiday sets in Lync Server 2013</span></span>](lync-server-2013-optional-define-response-group-holiday-sets.md)  


[<span data-ttu-id="48c3b-116">オプションLync Server 2013 で応答グループの営業時間を定義する</span><span class="sxs-lookup"><span data-stu-id="48c3b-116">(Optional) Define Response Group business hours in Lync Server 2013</span></span>](lync-server-2013-optional-define-response-group-business-hours.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

