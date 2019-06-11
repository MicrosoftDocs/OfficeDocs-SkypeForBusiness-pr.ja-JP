---
title: 'Lync Server 2013: 応答グループエージェントグループを管理する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing Response Group agent groups
ms:assetid: 36084cdc-38f1-4c45-922f-f81c7e86210c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520976(v=OCS.15)
ms:contentKeyID: 48183806
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c6cbea3b1a0d6638206a022ce5aded610dd60f23
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827845"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-response-group-agent-groups-in-lync-server-2013"></a><span data-ttu-id="a22b8-102">Lync Server 2013 での応答グループエージェントグループの管理</span><span class="sxs-lookup"><span data-stu-id="a22b8-102">Managing Response Group agent groups in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a22b8-103">_**最終更新日:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="a22b8-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="a22b8-104">エージェントグループは、応答グループへの通話に応答するように指定されているユーザーのグループで構成されます。</span><span class="sxs-lookup"><span data-stu-id="a22b8-104">An agent group consists of a group of people who are designated to answer calls to a response group.</span></span> <span data-ttu-id="a22b8-105">エージェントグループを作成するときは、グループに割り当てられているエージェントを選択し、ルーティング方法や、エージェントがグループに対してサインインまたはサインアウトできるかどうかなど、その他のグループ設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="a22b8-105">When you create an agent group, you select the agents who are assigned to the group and specify additional group settings, such as the routing method and whether an agent can sign in to and out of the group.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a22b8-106">ユーザーをエージェントグループに追加する前に、ユーザーをエンタープライズ Voip 用に有効にしておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="a22b8-106">Users must be enabled for Enterprise Voice before you can add them to agent groups.</span></span> <span data-ttu-id="a22b8-107">エンタープライズ Voip のユーザーを有効にする方法の詳細については、「 <A href="lync-server-2013-enable-users-for-enterprise-voice.md">Lync Server 2013 でエンタープライズ voip のユーザーを有効</A>にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a22b8-107">For details about how to enable a user for Enterprise Voice, see <A href="lync-server-2013-enable-users-for-enterprise-voice.md">Enable users for Enterprise Voice in Lync Server 2013</A>.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="a22b8-108">エージェントにできるのは社内ユーザーのみです。</span><span class="sxs-lookup"><span data-stu-id="a22b8-108">Only on-premises users can be agents.</span></span> <span data-ttu-id="a22b8-109">エージェントがオンプレミスからオンラインに移行された場合、応答グループの呼び出しはそのエージェントにルーティングされません。</span><span class="sxs-lookup"><span data-stu-id="a22b8-109">If an agent is moved from on-premises to online, Response Group calls will not be routed to that agent.</span></span>



</div>

<span data-ttu-id="a22b8-110">グループからサインアウトする必要があるエージェントは、Lync Server のサインインまたはサインアウトとは異なり、*正式なエージェント*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="a22b8-110">An agent who must sign in and out of the group, which is different from signing in or out of Lync Server, is called a *formal agent*.</span></span> <span data-ttu-id="a22b8-111">正式なエージェントは、グループに転送された通話を受信する前に、グループにサインインしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a22b8-111">Formal agents must be signed in to the group before they can receive calls that are routed to the group.</span></span> <span data-ttu-id="a22b8-112">これは、パートタイム ベースでグループから通話に応答するエージェントには便利な方法です。</span><span class="sxs-lookup"><span data-stu-id="a22b8-112">This can be useful for agents who answer calls from the group on a part-time basis.</span></span> <span data-ttu-id="a22b8-113">正式なエージェントは、Lync 2013 のメニュー項目をクリックして、Windows Internet Explorer のインターネットブラウザーを開き、web ページ本体を表示することによって、グループにサインインおよびサインアウトします。</span><span class="sxs-lookup"><span data-stu-id="a22b8-113">Formal agents sign in and out of their groups by clicking a menu item in Lync 2013 to open the Windows Internet Explorer Internet browser and display a webpage console.</span></span>

<span data-ttu-id="a22b8-114">グループにサインインしていないか、グループからサインアウトしていないエージェントは、"*非公式のエージェント*" と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="a22b8-114">An agent who does not sign in or out of the group is called an *informal agent*.</span></span> <span data-ttu-id="a22b8-115">非公式のエージェントは、Lync Server へのサインイン時にグループに自動的にサインインされ、グループからサインアウトすることはできません。</span><span class="sxs-lookup"><span data-stu-id="a22b8-115">Informal agents are automatically signed in to the group when they sign in to Lync Server, and they cannot sign out of the group.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a22b8-p106">ユーザーを応答グループ エージェントとして割り当てる場合、ユーザーがプライバシー モードを有効にしているのであれば、"RGS Presence Watcher" 連絡先を検索して連絡先リストに追加する必要があることを伝えてください。プライバシー モードを有効にしているが連絡先リストに RGS Presence Watcher がないエージェントは、応答グループに対する通話を受信できません。プライバシー モードを有効にしていないエージェントは、影響されません。</span><span class="sxs-lookup"><span data-stu-id="a22b8-p106">When you assign users as response group agents, inform them that, if they have Privacy mode enabled, they need to search for "RGS Presence Watcher" contacts and add them to their Contacts list. Agents who have Privacy mode enabled, but who do not have "RGS Presence Watcher" in their Contacts list, cannot receive calls to the response group. Agents who do not have Privacy mode enabled are not affected.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a22b8-119">このセクション中</span><span class="sxs-lookup"><span data-stu-id="a22b8-119">In This Section</span></span>

  - [<span data-ttu-id="a22b8-120">Lync Server 2013 でエージェントグループを作成または変更する</span><span class="sxs-lookup"><span data-stu-id="a22b8-120">Create or modify an agent group in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-agent-group.md)

  - [<span data-ttu-id="a22b8-121">Lync Server 2013 でエージェントグループを削除する</span><span class="sxs-lookup"><span data-stu-id="a22b8-121">Delete an agent group in Lync Server 2013</span></span>](lync-server-2013-delete-an-agent-group.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

