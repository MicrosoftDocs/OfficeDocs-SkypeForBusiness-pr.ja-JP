---
title: 'Lync Server 2013: ワークフローを作成または変更する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a workflow
ms:assetid: 5ac1c0f3-e82f-40ca-b972-91950e38c05b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520997(v=OCS.15)
ms:contentKeyID: 48184225
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9725958a302f50b0d1cdddf399b98fdd47ff6fc2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833773"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-workflow-in-lync-server-2013"></a><span data-ttu-id="0c3f9-102">Lync Server 2013 でワークフローを作成または変更する</span><span class="sxs-lookup"><span data-stu-id="0c3f9-102">Create or modify a workflow in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0c3f9-103">_**最終更新日:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="0c3f9-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="0c3f9-104">Lync Server 2013 は、2種類のワークフローをサポートしています。ハントグループと対話型音声応答 (IVR)。</span><span class="sxs-lookup"><span data-stu-id="0c3f9-104">Lync Server 2013 supports two types of workflows: hunt group and interactive voice response (IVR).</span></span> <span data-ttu-id="0c3f9-105">ワークフローを作成する場合は、応答グループの構成ツールを使用して、ウェルカムメッセージ、保留中の音楽、業務時間、応答グループアプリケーションが発信者に質問するなどのその他の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="0c3f9-105">When you create a workflow, you use the Response Group Configuration Tool to specify the queue to use and other settings, such as a welcome message, music on hold, business hours, and questions that the Response Group application asks the caller.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0c3f9-106">エージェント グループとキューは、これらを使用するワークフローの作成前に作成しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c3f9-106">You must create agent groups and queues before you create a workflow that uses them.</span></span> <span data-ttu-id="0c3f9-107">複数のワークフローに使用できる定義済みの勤務時間と休日を作成する場合は、それらを使用するワークフローを作成する前に、これらの時間と休日も定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c3f9-107">If you want to create predefined business hours and holidays that you can use for multiple workflows, you must also define these hours and holidays before you create a workflow that uses them.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="0c3f9-108">このセクション中</span><span class="sxs-lookup"><span data-stu-id="0c3f9-108">In This Section</span></span>

  - [<span data-ttu-id="0c3f9-109">Lync Server 2013 でハントグループワークフローを作成または変更する</span><span class="sxs-lookup"><span data-stu-id="0c3f9-109">Create or modify a hunt group workflow in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-hunt-group-workflow.md)

  - [<span data-ttu-id="0c3f9-110">Lync Server 2013 での対話ワークフローの作成または変更</span><span class="sxs-lookup"><span data-stu-id="0c3f9-110">Create or modify an interactive workflow in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-interactive-workflow.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0c3f9-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="0c3f9-111">See Also</span></span>


[<span data-ttu-id="0c3f9-112">Lync Server 2013 でエージェントグループを作成または変更する</span><span class="sxs-lookup"><span data-stu-id="0c3f9-112">Create or modify an agent group in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-agent-group.md)  
[<span data-ttu-id="0c3f9-113">Lync Server 2013 でキューを作成または変更する</span><span class="sxs-lookup"><span data-stu-id="0c3f9-113">Create or modify a queue in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-queue.md)  
[<span data-ttu-id="0c3f9-114">省略Lync Server 2013 で回答グループの休日セットを定義する</span><span class="sxs-lookup"><span data-stu-id="0c3f9-114">(Optional) Define Response Group holiday sets in Lync Server 2013</span></span>](lync-server-2013-optional-define-response-group-holiday-sets.md)  


[<span data-ttu-id="0c3f9-115">省略Lync Server 2013 での応答グループの営業時間の定義</span><span class="sxs-lookup"><span data-stu-id="0c3f9-115">(Optional) Define Response Group business hours in Lync Server 2013</span></span>](lync-server-2013-optional-define-response-group-business-hours.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

