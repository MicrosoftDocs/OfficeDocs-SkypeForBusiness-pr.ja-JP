---
title: 'Lync Server 2013: ワークフロー作成のシナリオの概要'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of workflow creation scenarios
ms:assetid: 05e0c175-0f1a-4bb1-b048-c68584d00649
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204646(v=OCS.15)
ms:contentKeyID: 48183309
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 08ecb210ea937184039587d289c5c9c57cb4fa4d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755411"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-workflow-creation-scenarios-in-lync-server-2013"></a><span data-ttu-id="a023b-102">Lync Server 2013 でのワークフロー作成のシナリオの概要</span><span class="sxs-lookup"><span data-stu-id="a023b-102">Overview of workflow creation scenarios in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a023b-103">_**最終更新日:** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="a023b-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="a023b-104">ワークフローを作成する際には、考えられるシナリオとして次の 2 つがあります。</span><span class="sxs-lookup"><span data-stu-id="a023b-104">When you create workflows, there are two possible scenarios:</span></span>

  - <span data-ttu-id="a023b-105">**管理者がワークフローを作成して構成する** - CsResponseGroupAdministrator の役割のメンバー (または同等のメンバー) は、ワークフローおよびワークフローの全要素 (エージェント グループ、キュー、休日と営業時間、保留音など) を作成し、アクティブ化します。</span><span class="sxs-lookup"><span data-stu-id="a023b-105">**The Administrator creates and configures the workflow** — The CsResponseGroupAdministrator role member (or equivalent) creates and activates the workflow and all elements in the workflow, such as the agent groups, queues, holiday and business hours, music on hold, and so on.</span></span>

  - <span data-ttu-id="a023b-p101">**管理者がワークフローを作成してマネージャーがオプションを構成する** - CsResponseGroupAdministrator の役割のメンバー (または同等のメンバー) は、プライマリ SIP URI や表示名を定義し、CsResponseGroupManager の役割のメンバーを割り当て、キューの選択とワークフローのアクティブ化を行います。その後、CsResponseGroupManager は、ログオンしてワークフローの構成を編集できます。具体的には、エージェント グループの作成、キューへのグループの割り当て、電話番号、休日と営業時間、保留音などの構成が実行できます。</span><span class="sxs-lookup"><span data-stu-id="a023b-p101">**The Administrator creates the workflow and the Manager configures options** — The CsResponseGroupAdministrator role member (or equivalent) defines the primary SIP URI, Display Name, assigns a member or members of the CsResponseGroupManager role, and selects a queue and activates the workflow. The CsResponseGroupManager can then log on and edit the configuration of the workflow by creating agent groups and also assigns the group to the queue, configuring the telephone number, holiday and business hours, music on hold, and so on.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a023b-p102">管理ワークフローを作成する際には、そのワークフローをアクティブなものとして作成する必要があります。アクティブな管理ワークフローは、保存後に変更したり非アクティブにしたりできます。</span><span class="sxs-lookup"><span data-stu-id="a023b-p102">When you want to create a managed workflow, you need to create the workflow as active. After you save an active, managed workflow, you can then modify and deactivate the workflow.</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

