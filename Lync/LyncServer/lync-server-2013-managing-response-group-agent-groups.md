---
title: 'Lync Server 2013: 応答グループエージェントグループの管理'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing Response Group agent groups
ms:assetid: 36084cdc-38f1-4c45-922f-f81c7e86210c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520976(v=OCS.15)
ms:contentKeyID: 48183806
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 11e0c0c022b1925831737d70a10c2a193b9732bf
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48497954"
---
# <a name="managing-response-group-agent-groups-in-lync-server-2013"></a><span data-ttu-id="43b48-102">Lync Server 2013 での応答グループエージェントグループの管理</span><span class="sxs-lookup"><span data-stu-id="43b48-102">Managing Response Group agent groups in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="43b48-103">_**トピックの最終更新日:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="43b48-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="43b48-p101">エージェント グループは、応答グループへの通話に応答するように指定されているユーザーのグループから構成されます。エージェント グループを作成するときは、そのグループに割り当てるエージェントを選択し、詳細なグループ設定 (ルーティング方法、エージェントがグループにサインイン/サインアウトするかどうかなど) を指定します。</span><span class="sxs-lookup"><span data-stu-id="43b48-p101">An agent group consists of a group of people who are designated to answer calls to a response group. When you create an agent group, you select the agents who are assigned to the group and specify additional group settings, such as the routing method and whether an agent can sign in to and out of the group.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="43b48-106">ユーザーをエージェントグループに追加するには、事前にエンタープライズ Voip を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="43b48-106">Users must be enabled for Enterprise Voice before you can add them to agent groups.</span></span> <span data-ttu-id="43b48-107">エンタープライズ Voip に対してユーザーを有効にする方法の詳細については、「 <A href="lync-server-2013-enable-users-for-enterprise-voice.md">enable users For Enterprise voice In Lync Server 2013</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="43b48-107">For details about how to enable a user for Enterprise Voice, see <A href="lync-server-2013-enable-users-for-enterprise-voice.md">Enable users for Enterprise Voice in Lync Server 2013</A>.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="43b48-p103">社内ユーザーのみがエージェントであることができます。エージェントが社内からオンラインに移動した場合、応答グループ呼び出しはそのエージェントに送られません。</span><span class="sxs-lookup"><span data-stu-id="43b48-p103">Only on-premises users can be agents. If an agent is moved from on-premises to online, Response Group calls will not be routed to that agent.</span></span>



</div>

<span data-ttu-id="43b48-110">グループにサインインまたは拒否する必要があるエージェント (Lync Server のサインイン時またはログアウト時とは異なる) は、 *正式なエージェント*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="43b48-110">An agent who must sign in and out of the group, which is different from signing in or out of Lync Server, is called a *formal agent*.</span></span> <span data-ttu-id="43b48-111">公式エージェントが、グループにルーティングされた着信を受信するには、そのグループにサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="43b48-111">Formal agents must be signed in to the group before they can receive calls that are routed to the group.</span></span> <span data-ttu-id="43b48-112">これは、パートタイム ベースでグループから通話に応答するエージェントには便利な方法です。</span><span class="sxs-lookup"><span data-stu-id="43b48-112">This can be useful for agents who answer calls from the group on a part-time basis.</span></span> <span data-ttu-id="43b48-113">正式なエージェント Lync 2013 のメニュー項目をクリックして、Windows Internet Explorer の Internet browser を開き、web ページコンソールを表示することによって、グループにサインインおよびサインアウトします。</span><span class="sxs-lookup"><span data-stu-id="43b48-113">Formal agents sign in and out of their groups by clicking a menu item in Lync 2013 to open the Windows Internet Explorer Internet browser and display a webpage console.</span></span>

<span data-ttu-id="43b48-114">グループにサインインしていない、またはグループ外にいるエージェントは、 *非公式なエージェント*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="43b48-114">An agent who does not sign in or out of the group is called an *informal agent*.</span></span> <span data-ttu-id="43b48-115">非公式のエージェントは、Lync Server にサインインするときにグループに自動的にサインインします。グループからサインアウトすることはできません。</span><span class="sxs-lookup"><span data-stu-id="43b48-115">Informal agents are automatically signed in to the group when they sign in to Lync Server, and they cannot sign out of the group.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="43b48-p106">ユーザーを応答グループ エージェントとして割り当てる場合、ユーザーがプライバシー モードを有効にしているのであれば、"RGS Presence Watcher" 連絡先を検索して連絡先リストに追加する必要があることを通知してください。プライバシー モードを有効にしているが連絡先リストに RGS Presence Watcher がないエージェントは、応答グループに対する通話を受信できません。プライバシー モードを有効にしていないエージェントは、影響されません。</span><span class="sxs-lookup"><span data-stu-id="43b48-p106">When you assign users as response group agents, inform them that, if they have Privacy mode enabled, they need to search for "RGS Presence Watcher" contacts and add them to their Contacts list. Agents who have Privacy mode enabled, but who do not have "RGS Presence Watcher" in their Contacts list, cannot receive calls to the response group. Agents who do not have Privacy mode enabled are not affected.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="43b48-119">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="43b48-119">In This Section</span></span>

  - [<span data-ttu-id="43b48-120">Lync Server 2013 でエージェントグループを作成または変更する</span><span class="sxs-lookup"><span data-stu-id="43b48-120">Create or modify an agent group in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-agent-group.md)

  - [<span data-ttu-id="43b48-121">Lync Server 2013 でエージェントグループを削除する</span><span class="sxs-lookup"><span data-stu-id="43b48-121">Delete an agent group in Lync Server 2013</span></span>](lync-server-2013-delete-an-agent-group.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

