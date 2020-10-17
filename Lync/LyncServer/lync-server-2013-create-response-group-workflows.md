---
title: 'Lync Server 2013: 応答グループのワークフローの作成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create Response Group workflows
ms:assetid: 41272258-728d-42bd-b4d4-2a499734c720
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425918(v=OCS.15)
ms:contentKeyID: 48183954
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe0ca786aea0f3c6fab0da95700bd6fa9bb5f21e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504724"
---
# <a name="create-response-group-workflows-in-lync-server-2013"></a><span data-ttu-id="fae43-102">Lync Server 2013 で応答グループのワークフローを作成する</span><span class="sxs-lookup"><span data-stu-id="fae43-102">Create Response Group workflows in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fae43-103">_**トピックの最終更新日:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="fae43-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="fae43-p101">ワークフローは、電話への着信から、だれかが呼び出しに応答するまでの通話のビヘイビアーを定義します。ワークフローは、通話の保留に使用されるキューを指定し、ハント グループで使用するルーティング方法や対話型応答グループで使用する質問と回答を指定します。また、ワークフローは、開始メッセージ、保留音、営業時間、休日などの設定も定義します。</span><span class="sxs-lookup"><span data-stu-id="fae43-p101">A workflow defines the behavior of a call from the time that the phone rings to the time that someone answers the call. The workflow specifies the queue to use for holding the call, and specifies the routing method to use for hunt groups or the questions and answers to use for interactive response groups. A workflow also defines settings such as a welcome message, music on hold, business hours, and holidays.</span></span>

<span data-ttu-id="fae43-107">応答グループ構成ツールを使用して、ワークフローを作成します。</span><span class="sxs-lookup"><span data-stu-id="fae43-107">You use the Response Group Configuration Tool to create workflows.</span></span> <span data-ttu-id="fae43-108">応答グループ構成ツールには、Lync Server コントロールパネルの [応答グループ] ページからアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="fae43-108">You can access the Response Group Configuration Tool from the Response Group page of Lync Server Control Panel.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fae43-109">エージェント グループとキューは、これらを使用するワークフローの作成前に作成しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="fae43-109">You must create agent groups and queues before you create a workflow that uses them.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="fae43-110">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="fae43-110">In This Section</span></span>

  - [<span data-ttu-id="fae43-111">Lync Server 2013 でハントグループワークフローを作成または変更する</span><span class="sxs-lookup"><span data-stu-id="fae43-111">Create or modify a hunt group workflow in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-hunt-group-workflow.md)

  - [<span data-ttu-id="fae43-112">Lync Server 2013 での対話型音声応答呼び出しフローの設計</span><span class="sxs-lookup"><span data-stu-id="fae43-112">Design interactive voice response call flows in Lync Server 2013</span></span>](lync-server-2013-design-interactive-voice-response-call-flows.md)

  - [<span data-ttu-id="fae43-113">Lync Server 2013 での対話ワークフローの作成または変更</span><span class="sxs-lookup"><span data-stu-id="fae43-113">Create or modify an interactive workflow in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-interactive-workflow.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="fae43-114">関連情報</span><span class="sxs-lookup"><span data-stu-id="fae43-114">Related Sections</span></span>

  - [<span data-ttu-id="fae43-115">応答グループエージェントグループの作成 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fae43-115">Create Response Group agent groups Lync Server 2013</span></span>](lync-server-2013-create-response-group-agent-groups.md)

  - [<span data-ttu-id="fae43-116">Lync Server 2013 で応答グループキューを作成する</span><span class="sxs-lookup"><span data-stu-id="fae43-116">Create Response Group queues in Lync Server 2013</span></span>](lync-server-2013-create-response-group-queues.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

