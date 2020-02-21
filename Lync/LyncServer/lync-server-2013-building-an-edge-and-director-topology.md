---
title: 'Lync Server 2013: エッジおよびディレクターのトポロジの作成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Building an edge and Director topology
ms:assetid: 11e5759e-d69f-4c39-8994-f467c279c558
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398202(v=OCS.15)
ms:contentKeyID: 48183451
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be41eb547589c74b070a55325efcfd05e33f4588
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196530"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="building-an-edge-and-director-topology-in-lync-server-2013"></a><span data-ttu-id="ff53b-102">Lync Server 2013 でのエッジおよびディレクターのトポロジの構築</span><span class="sxs-lookup"><span data-stu-id="ff53b-102">Building an edge and Director topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ff53b-103">_**トピックの最終更新日:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="ff53b-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="ff53b-104">トポロジの構築には、次の計画タスクと展開タスクが含まれます。</span><span class="sxs-lookup"><span data-stu-id="ff53b-104">Building the topology involves the following planning and deployment tasks:</span></span>

  - <span data-ttu-id="ff53b-105">**計画**   組織に適したトポロジを定義し、それを展開するために必要なコンポーネントを特定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff53b-105">**Planning**   You need to define an appropriate topology for your organization and identify the components required to deploy it.</span></span> <span data-ttu-id="ff53b-106">これらは、計画プロセスの標準的なステップです。</span><span class="sxs-lookup"><span data-stu-id="ff53b-106">These are standard steps in the planning process.</span></span> <span data-ttu-id="ff53b-107">Microsoft Lync Server 2013 (Lync Server 2013 で提供される計画ツール) を使用すると、計画プロセスを簡単に開始できます。また、要件やプランが完成すると、簡単に変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="ff53b-107">The Microsoft Lync Server 2013, Planning Tool provided with Lync Server 2013 makes it easy to start the planning process, as well as including the ability to easily make changes as your requirements and plans are finalized.</span></span>

  - <span data-ttu-id="ff53b-108">**展開**   トポロジビルダーを使用して定義したトポロジは、任意の Lync server 2013 サーバーを展開するために不可欠です。</span><span class="sxs-lookup"><span data-stu-id="ff53b-108">**Deployment**   The topology that you define using Topology Builder is essential to the deployment of any Lync Server 2013 server.</span></span> <span data-ttu-id="ff53b-109">計画作業の一部としてトポロジビルダーを使用してトポロジを定義して公開しない場合は、エッジサーバーを展開する前に、トポロジビルダーを実行してトポロジを公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff53b-109">If you do not finish defining and publishing your topology by using Topology Builder as part of your planning efforts, you must complete it and publish the topology before you deploy your Edge Servers.</span></span>

<span data-ttu-id="ff53b-110">少なくとも1つの内部プールを展開するまでエッジサーバーコンポーネントを展開することはできません。また、トポロジビルダーをインストールして内部プールを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff53b-110">You cannot deploy Edge Server components until you have deployed at least one internal pool, and you must install Topology Builder to deploy an internal pool.</span></span> <span data-ttu-id="ff53b-111">このセクションでは、内部プールのインストールプロセスの一部であるトポロジビルダーのインストールについては説明しません。</span><span class="sxs-lookup"><span data-stu-id="ff53b-111">This section does not cover installation of Topology Builder because that is part of the installation process for the internal pool.</span></span>

<span data-ttu-id="ff53b-112">これらのツールの詳細については、「 [Lync Server 2013 の外部ユーザーアクセスの展開チェックリスト](lync-server-2013-deployment-checklist-for-external-user-access.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ff53b-112">For details about these tools, see [Deployment checklist for external user access in Lync Server 2013](lync-server-2013-deployment-checklist-for-external-user-access.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ff53b-113">トポロジビルダーを使用して、エッジトポロジを含む完全なトポロジを定義していた場合は、このセクションの「lync server <A href="lync-server-2013-define-your-edge-topology.md">2013 でのエッジトポロジの定義</A>」および「lync <A href="lync-server-2013-publish-your-topology.md">server 2013</A>のタスクでのトポロジの公開」を省略できます。ただし、「 <A href="lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md">Lync server 2013 トポロジをエクスポートして外部メディアにコピー</A>する」を実行してください。</span><span class="sxs-lookup"><span data-stu-id="ff53b-113">If you previously used Topology Builder to define a complete topology, including the edge topology, you do can skip the <A href="lync-server-2013-define-your-edge-topology.md">Define your edge topology in Lync Server 2013</A> and <A href="lync-server-2013-publish-your-topology.md">Publish your topology in Lync Server 2013</A> tasks in this section, but you do need to complete the <A href="lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md">Export your Lync Server 2013 topology and copy it to external media for edge installation</A> task.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ff53b-114">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="ff53b-114">In This Section</span></span>

  - [<span data-ttu-id="ff53b-115">Lync Server 2013 でエッジトポロジを定義する</span><span class="sxs-lookup"><span data-stu-id="ff53b-115">Define your edge topology in Lync Server 2013</span></span>](lync-server-2013-define-your-edge-topology.md)

  - [<span data-ttu-id="ff53b-116">Lync Server 2013 のトポロジにオプションのディレクタートポロジを定義する</span><span class="sxs-lookup"><span data-stu-id="ff53b-116">Define optional Director topologies in your topology for Lync Server 2013</span></span>](lync-server-2013-define-optional-director-topologies-in-your-topology.md)

  - [<span data-ttu-id="ff53b-117">Lync Server 2013 でのトポロジの公開</span><span class="sxs-lookup"><span data-stu-id="ff53b-117">Publish your topology in Lync Server 2013</span></span>](lync-server-2013-publish-your-topology.md)

  - [<span data-ttu-id="ff53b-118">エッジインストールのために Lync Server 2013 トポロジをエクスポートして外部メディアにコピーする</span><span class="sxs-lookup"><span data-stu-id="ff53b-118">Export your Lync Server 2013 topology and copy it to external media for edge installation</span></span>](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

