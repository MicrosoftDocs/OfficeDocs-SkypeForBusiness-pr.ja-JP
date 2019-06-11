---
title: 'Lync Server 2013: 応答グループのワークフローの作成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create Response Group workflows
ms:assetid: 41272258-728d-42bd-b4d4-2a499734c720
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425918(v=OCS.15)
ms:contentKeyID: 48183954
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ba7d989d1733645c7055fb64d6b790212e15e16
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833765"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-response-group-workflows-in-lync-server-2013"></a><span data-ttu-id="68f63-102">Lync Server 2013 での応答グループのワークフローの作成</span><span class="sxs-lookup"><span data-stu-id="68f63-102">Create Response Group workflows in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="68f63-103">_**最終更新日:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="68f63-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="68f63-p101">ワークフローは、電話への着信から、だれかが呼び出しに応答するまでの通話のビヘイビアーを定義します。ワークフローは、通話の保留に使用されるキューを指定し、ハント グループで使用するルーティング方法や対話型応答グループで使用する質問と回答を指定します。また、ワークフローは、開始メッセージ、保留音、営業時間、休日などの設定も定義します。</span><span class="sxs-lookup"><span data-stu-id="68f63-p101">A workflow defines the behavior of a call from the time that the phone rings to the time that someone answers the call. The workflow specifies the queue to use for holding the call, and specifies the routing method to use for hunt groups or the questions and answers to use for interactive response groups. A workflow also defines settings such as a welcome message, music on hold, business hours, and holidays.</span></span>

<span data-ttu-id="68f63-107">応答グループ構成ツールを使ってワークフローを作成します。</span><span class="sxs-lookup"><span data-stu-id="68f63-107">You use the Response Group Configuration Tool to create workflows.</span></span> <span data-ttu-id="68f63-108">Lync Server コントロールパネルの [返信グループ] ページから応答グループの構成ツールにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="68f63-108">You can access the Response Group Configuration Tool from the Response Group page of Lync Server Control Panel.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="68f63-109">エージェント グループとキューは、これらを使用するワークフローの作成前に作成しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="68f63-109">You must create agent groups and queues before you create a workflow that uses them.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="68f63-110">このセクション中</span><span class="sxs-lookup"><span data-stu-id="68f63-110">In This Section</span></span>

  - [<span data-ttu-id="68f63-111">Lync Server 2013 でハントグループワークフローを作成または変更する</span><span class="sxs-lookup"><span data-stu-id="68f63-111">Create or modify a hunt group workflow in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-hunt-group-workflow.md)

  - [<span data-ttu-id="68f63-112">Lync Server 2013 での対話型音声応答通話フローの設計</span><span class="sxs-lookup"><span data-stu-id="68f63-112">Design interactive voice response call flows in Lync Server 2013</span></span>](lync-server-2013-design-interactive-voice-response-call-flows.md)

  - [<span data-ttu-id="68f63-113">Lync Server 2013 での対話ワークフローの作成または変更</span><span class="sxs-lookup"><span data-stu-id="68f63-113">Create or modify an interactive workflow in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-interactive-workflow.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="68f63-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="68f63-114">Related Sections</span></span>

  - [<span data-ttu-id="68f63-115">Lync Server 2013 での応答グループのエージェント グループの作成</span><span class="sxs-lookup"><span data-stu-id="68f63-115">Create Response Group agent groups Lync Server 2013</span></span>](lync-server-2013-create-response-group-agent-groups.md)

  - [<span data-ttu-id="68f63-116">Lync Server 2013 での応答グループのキューの作成</span><span class="sxs-lookup"><span data-stu-id="68f63-116">Create Response Group queues in Lync Server 2013</span></span>](lync-server-2013-create-response-group-queues.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

