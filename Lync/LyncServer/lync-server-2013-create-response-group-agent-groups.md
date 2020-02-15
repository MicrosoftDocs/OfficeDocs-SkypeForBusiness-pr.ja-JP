---
title: 'Lync Server 2013: 応答グループエージェントグループの作成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create Response Group agent groups
ms:assetid: 2a80de17-ead0-46e8-8a27-7a4e233dbde0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520969(v=OCS.15)
ms:contentKeyID: 48183688
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 48b4f97ad93ecdbfef9e8e170c999f8c9860f830
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42009420"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-response-group-agent-groups-lync-server-2013"></a><span data-ttu-id="33835-102">応答グループエージェントグループの作成 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="33835-102">Create Response Group agent groups Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="33835-103">_**トピックの最終更新日:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="33835-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="33835-104">エージェントグループを作成するときは、グループに割り当てられているエージェントを選択し、ルーティング方法や、エージェントがグループに対して送受信できるかどうかなど、追加のグループ設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="33835-104">When you create an agent group, you select the agents that are assigned to the group and specify additional group settings, such as the routing method and whether an agent can sign in to and out of the group.</span></span>

<span data-ttu-id="33835-105">グループにサインインまたは拒否する必要があるエージェント (Lync Server のサインイン時またはログアウト時とは異なる) は、*正式なエージェント*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="33835-105">An agent who must sign in and out of the group, which is different from signing in or out of Lync Server, is called a *formal agent*.</span></span> <span data-ttu-id="33835-106">正式なエージェントは、グループにルーティングされる通話を受信する前に、グループにサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="33835-106">Formal agents must be signed in to the group before they can receive calls routed to the group.</span></span> <span data-ttu-id="33835-107">これは、パートタイム ベースでグループから通話に応答するエージェントには便利な方法です。</span><span class="sxs-lookup"><span data-stu-id="33835-107">This can be useful for agents who answer calls from the group on a part-time basis.</span></span> <span data-ttu-id="33835-108">正式なエージェント Lync 2013 のメニュー項目をクリックして、Windows Internet Explorer の Internet browser を開き、web ページコンソールを表示することによって、グループにサインインおよびサインアウトします。</span><span class="sxs-lookup"><span data-stu-id="33835-108">Formal agents sign in and out of their groups by clicking a menu item in Lync 2013 to open the Windows Internet Explorer Internet browser and display a webpage console.</span></span>

<span data-ttu-id="33835-109">グループにサインインしていない、またはグループ外にいるエージェントは、*非公式なエージェント*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="33835-109">An agent who does not sign in or out of the group is called an *informal agent*.</span></span> <span data-ttu-id="33835-110">非公式のエージェントは、Lync Server にサインインするときにグループに自動的にサインインします。グループからサインアウトすることはできません。</span><span class="sxs-lookup"><span data-stu-id="33835-110">Informal agents are automatically signed in to the group when they sign in to Lync Server, and they cannot sign out of the group.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="33835-p103">社内ユーザーのみがエージェントであることができます。エージェントが社内からオンラインに移動した場合、応答グループ呼び出しはそのエージェントに送られません。</span><span class="sxs-lookup"><span data-stu-id="33835-p103">Only on-premises users can be agents. If an agent is moved from on-premises to online, Response Group calls will not be routed to that agent.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="33835-113">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="33835-113">In This Section</span></span>

[<span data-ttu-id="33835-114">Lync Server 2013 でエージェントグループを作成または変更する</span><span class="sxs-lookup"><span data-stu-id="33835-114">Create or modify an agent group in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-agent-group.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

