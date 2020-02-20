---
title: 'Lync Server 2013: 応答グループキューの管理'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing Response Group queues
ms:assetid: 1e91720c-ab67-4dfb-b30c-0ef2a8012310
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520960(v=OCS.15)
ms:contentKeyID: 48183576
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a5d8ea969f177a0e7e9400d3c50f61c6fd0aab2a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150114"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-response-group-queues-in-lync-server-2013"></a><span data-ttu-id="3b8a7-102">Lync Server 2013 での応答グループキューの管理</span><span class="sxs-lookup"><span data-stu-id="3b8a7-102">Managing Response Group queues in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3b8a7-103">_**トピックの最終更新日:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="3b8a7-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="3b8a7-104">応答グループに対する通話は、エージェントが通話に応答するまではキューに保持されます。</span><span class="sxs-lookup"><span data-stu-id="3b8a7-104">Queues hold calls to a response group until an agent answers the call.</span></span> <span data-ttu-id="3b8a7-105">キューを管理する場合、1 つ以上のエージェント グループをキューに割り当て、オーバーフロー時の動作の実行に移る前にキューが保持できる通話の数、タイムアウト処理の実行に移るまでに通話がエージェントを待機する時間など、キューの設定値を指定します。</span><span class="sxs-lookup"><span data-stu-id="3b8a7-105">When you manage a queue, you assign one or more agent groups to the queue and specify queue settings, such as the number of calls that the queue can hold before performing an overflow action and the length of time that a call waits for an agent before performing a time-out action.</span></span> <span data-ttu-id="3b8a7-106">応答グループアプリケーションは、利用可能なエージェントを検索するときに、エージェントグループをリストに従って検索します。</span><span class="sxs-lookup"><span data-stu-id="3b8a7-106">When the Response Group application searches for an available agent, it searches agent groups in the order that you list them.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="3b8a7-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="3b8a7-107">In This Section</span></span>

  - [<span data-ttu-id="3b8a7-108">Lync Server 2013 でキューを作成または変更する</span><span class="sxs-lookup"><span data-stu-id="3b8a7-108">Create or modify a queue in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-queue.md)

  - [<span data-ttu-id="3b8a7-109">Lync Server 2013 で応答グループキューを削除する</span><span class="sxs-lookup"><span data-stu-id="3b8a7-109">Delete a Response Group queue in Lync Server 2013</span></span>](lync-server-2013-delete-a-response-group-queue.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

