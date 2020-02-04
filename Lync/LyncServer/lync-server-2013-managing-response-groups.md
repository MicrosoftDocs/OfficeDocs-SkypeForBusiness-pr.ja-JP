---
title: 'Lync Server 2013: 応答グループの管理'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing response groups
ms:assetid: 5a804d7d-3c1a-4647-a0e0-d5c4c8c23b73
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520996(v=OCS.15)
ms:contentKeyID: 48184222
ms.date: 02/01/2018
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 210debb3c3879d6895b127b960139970bf73d020
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756071"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-response-groups-in-lync-server-2013"></a><span data-ttu-id="7c652-102">Lync Server 2013 での応答グループの管理</span><span class="sxs-lookup"><span data-stu-id="7c652-102">Managing response groups in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7c652-103">_**最終更新日:** 2018-02-01_</span><span class="sxs-lookup"><span data-stu-id="7c652-103">_**Topic Last Modified:** 2018-02-01_</span></span>

<span data-ttu-id="7c652-104">応答グループは、ヘルプデスクなどの特定の領域に発信された通話をキューに追加して、その通話を*エージェント*と呼ばれる指定したユーザーのグループにルーティングすることを可能にする、通話管理機能です。</span><span class="sxs-lookup"><span data-stu-id="7c652-104">Response groups are a call management feature that enables you to queue calls that are made to a specific area, such as a Help Desk, and then route the calls to a designated group of people, called *agents*.</span></span>

<span data-ttu-id="7c652-105">応答グループを管理するには、エージェントグループ、キュー、ワークフローを構成します。これは、エージェントが応答するまでの間に発信された通話に対する処理を定義します。</span><span class="sxs-lookup"><span data-stu-id="7c652-105">To manage response groups, you configure agent groups, queues, and workflows, which define what happens to a call from the time it is placed until an agent answers it.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7c652-106">応答グループの展開で300ワークフローが1つのプールに含まれている場合は、Lync Server Management Shell コマンドレットを使用してワークフローを作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7c652-106">If you have more than 300 workflows in a single pool in your Response Group deployment, it is better to use Lync Server Management Shell cmdlets to create the workflows.</span></span> <span data-ttu-id="7c652-107">[応答グループ] 構成ツールを使用して、300ワークフローを超えるプールのワークフローを作成すると、web ページの読み込みに時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="7c652-107">If you use the Response Group Configuration Tool to create workflows for a pool that has more than 300 workflows, the webpage takes a long time to load.</span></span> <span data-ttu-id="7c652-108">キュー経由でワークフローに間接的に関連付けられているエージェントの数にも、ページの読み込みに比例した効果があります。</span><span class="sxs-lookup"><span data-stu-id="7c652-108">The number of agents that are indirectly associated with workflows through the queues also has a proportional effect on page loading.</span></span>



</div>

<span data-ttu-id="7c652-109">このセクションのトピックでは、展開で応答グループアプリケーションをカスタマイズして維持するために実行できるタスクのステップバイステップの手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="7c652-109">Topics in this section provide step-by-step procedures for tasks that you can perform to customize and maintain the Response Group application in your deployment</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="7c652-110">このセクション中</span><span class="sxs-lookup"><span data-stu-id="7c652-110">In This Section</span></span>

  - [<span data-ttu-id="7c652-111">Lync Server 2013 での応答グループエージェントグループの管理</span><span class="sxs-lookup"><span data-stu-id="7c652-111">Managing Response Group agent groups in Lync Server 2013</span></span>](lync-server-2013-managing-response-group-agent-groups.md)

  - [<span data-ttu-id="7c652-112">Lync Server 2013 での応答グループキューの管理</span><span class="sxs-lookup"><span data-stu-id="7c652-112">Managing Response Group queues in Lync Server 2013</span></span>](lync-server-2013-managing-response-group-queues.md)

  - [<span data-ttu-id="7c652-113">Lync Server 2013 での応答グループワークフローの管理</span><span class="sxs-lookup"><span data-stu-id="7c652-113">Managing Response Group workflows in Lync Server 2013</span></span>](lync-server-2013-managing-response-group-workflows.md)

  - [<span data-ttu-id="7c652-114">Lync Server 2013 でのアプリケーションレベルの応答グループの設定の管理</span><span class="sxs-lookup"><span data-stu-id="7c652-114">Managing application-level Response Group settings in Lync Server 2013</span></span>](lync-server-2013-managing-application-level-response-group-settings.md)

  - [<span data-ttu-id="7c652-115">Lync Server 2013 の新しいプールへの応答グループの移動</span><span class="sxs-lookup"><span data-stu-id="7c652-115">Moving response groups to a new pool in Lync Server 2013</span></span>](lync-server-2013-moving-response-groups-to-a-new-pool.md)

  - [<span data-ttu-id="7c652-116">障害時の Lync Server 2013 での応答グループの管理</span><span class="sxs-lookup"><span data-stu-id="7c652-116">Managing response groups in Lync Server 2013 during a disaster</span></span>](lync-server-2013-managing-response-groups-during-a-disaster.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

