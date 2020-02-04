---
title: 'Lync Server 2013: 応答グループのエージェント グループの作成'
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
ms.openlocfilehash: 8e2a8a41b67818cf1f2aec9ec8daaa46eeff783a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763461"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-response-group-agent-groups-lync-server-2013"></a><span data-ttu-id="ed861-102">Lync Server 2013 での応答グループのエージェント グループの作成</span><span class="sxs-lookup"><span data-stu-id="ed861-102">Create Response Group agent groups Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ed861-103">_**最終更新日:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="ed861-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="ed861-104">エージェント グループを作成するときは、そのグループに割り当てるエージェントを選択し、詳細なグループ設定 (ルーティング方法、グループに対するエージェントの権限など) を指定します。</span><span class="sxs-lookup"><span data-stu-id="ed861-104">When you create an agent group, you select the agents that are assigned to the group and specify additional group settings, such as the routing method and whether an agent can sign in to and out of the group.</span></span>

<span data-ttu-id="ed861-105">グループからサインアウトする必要があるエージェントは、Lync Server のサインインまたはサインアウトとは異なり、*正式なエージェント*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="ed861-105">An agent who must sign in and out of the group, which is different from signing in or out of Lync Server, is called a *formal agent*.</span></span> <span data-ttu-id="ed861-106">公式エージェントが、グループにルーティングされた着信を受信するには、そのグループにサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed861-106">Formal agents must be signed in to the group before they can receive calls routed to the group.</span></span> <span data-ttu-id="ed861-107">これは、パートタイム ベースでグループから通話に応答するエージェントには便利な方法です。</span><span class="sxs-lookup"><span data-stu-id="ed861-107">This can be useful for agents who answer calls from the group on a part-time basis.</span></span> <span data-ttu-id="ed861-108">正式なエージェントは、Lync 2013 のメニュー項目をクリックして、Windows Internet Explorer のインターネットブラウザーを開き、web ページ本体を表示することによって、グループにサインインおよびサインアウトします。</span><span class="sxs-lookup"><span data-stu-id="ed861-108">Formal agents sign in and out of their groups by clicking a menu item in Lync 2013 to open the Windows Internet Explorer Internet browser and display a webpage console.</span></span>

<span data-ttu-id="ed861-109">グループにサインインしていないか、グループからサインアウトしていないエージェントは、"*非公式のエージェント*" と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="ed861-109">An agent who does not sign in or out of the group is called an *informal agent*.</span></span> <span data-ttu-id="ed861-110">非公式のエージェントは、Lync Server へのサインイン時にグループに自動的にサインインされ、グループからサインアウトすることはできません。</span><span class="sxs-lookup"><span data-stu-id="ed861-110">Informal agents are automatically signed in to the group when they sign in to Lync Server, and they cannot sign out of the group.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ed861-111">エージェントにできるのは社内ユーザーのみです。</span><span class="sxs-lookup"><span data-stu-id="ed861-111">Only on-premises users can be agents.</span></span> <span data-ttu-id="ed861-112">エージェントがオンプレミスからオンラインに移行された場合、応答グループの呼び出しはそのエージェントにルーティングされません。</span><span class="sxs-lookup"><span data-stu-id="ed861-112">If an agent is moved from on-premises to online, Response Group calls will not be routed to that agent.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ed861-113">このセクション中</span><span class="sxs-lookup"><span data-stu-id="ed861-113">In This Section</span></span>

[<span data-ttu-id="ed861-114">Lync Server 2013 でエージェントグループを作成または変更する</span><span class="sxs-lookup"><span data-stu-id="ed861-114">Create or modify an agent group in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-agent-group.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

