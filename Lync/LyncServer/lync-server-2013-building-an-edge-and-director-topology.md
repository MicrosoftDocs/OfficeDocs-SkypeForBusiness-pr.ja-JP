---
title: 'Lync Server 2013: エッジおよびディレクターのトポロジの作成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Building an edge and Director topology
ms:assetid: 11e5759e-d69f-4c39-8994-f467c279c558
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398202(v=OCS.15)
ms:contentKeyID: 48183451
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ae45053e8d9c01cd484da8a052304712f04a06fa
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840719"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="building-an-edge-and-director-topology-in-lync-server-2013"></a><span data-ttu-id="0e14b-102">Lync Server 2013 でのエッジおよびディレクターのトポロジの作成</span><span class="sxs-lookup"><span data-stu-id="0e14b-102">Building an edge and Director topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0e14b-103">_**最終更新日:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="0e14b-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="0e14b-104">トポロジを構築するには、次の計画と展開のタスクが必要です。</span><span class="sxs-lookup"><span data-stu-id="0e14b-104">Building the topology involves the following planning and deployment tasks:</span></span>

  - <span data-ttu-id="0e14b-105">**計画**   組織の適切なトポロジを定義し、展開に必要なコンポーネントを特定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0e14b-105">**Planning**   You need to define an appropriate topology for your organization and identify the components required to deploy it.</span></span> <span data-ttu-id="0e14b-106">これは、計画プロセスの標準的な手順です。</span><span class="sxs-lookup"><span data-stu-id="0e14b-106">These are standard steps in the planning process.</span></span> <span data-ttu-id="0e14b-107">Lync Server 2013 と共に提供される Microsoft Lync Server 2013、計画ツールを使用すると、計画プロセスを簡単に開始したり、要件や計画が完了したときに簡単に変更を加えることができます。</span><span class="sxs-lookup"><span data-stu-id="0e14b-107">The Microsoft Lync Server 2013, Planning Tool provided with Lync Server 2013 makes it easy to start the planning process, as well as including the ability to easily make changes as your requirements and plans are finalized.</span></span>

  - <span data-ttu-id="0e14b-108">**展開**   トポロジビルダーを使用して定義したトポロジは、Lync Server 2013 サーバーの展開に不可欠です。</span><span class="sxs-lookup"><span data-stu-id="0e14b-108">**Deployment**   The topology that you define using Topology Builder is essential to the deployment of any Lync Server 2013 server.</span></span> <span data-ttu-id="0e14b-109">計画作業の一環としてトポロジビルダーを使用してトポロジの定義と発行が完了しない場合は、Edge サーバーを展開する前にトポロジを完成させて発行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0e14b-109">If you do not finish defining and publishing your topology by using Topology Builder as part of your planning efforts, you must complete it and publish the topology before you deploy your Edge Servers.</span></span>

<span data-ttu-id="0e14b-110">少なくとも1つの内部プールを展開してから、内部プールを展開するには、トポロジビルダーをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0e14b-110">You cannot deploy Edge Server components until you have deployed at least one internal pool, and you must install Topology Builder to deploy an internal pool.</span></span> <span data-ttu-id="0e14b-111">このセクションでは、内部プールのインストールプロセスの一部であるトポロジビルダーのインストールについては説明しません。</span><span class="sxs-lookup"><span data-stu-id="0e14b-111">This section does not cover installation of Topology Builder because that is part of the installation process for the internal pool.</span></span>

<span data-ttu-id="0e14b-112">これらのツールについて詳しくは、「 [Lync Server 2013 での外部ユーザーアクセスの展開チェックリスト](lync-server-2013-deployment-checklist-for-external-user-access.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0e14b-112">For details about these tools, see [Deployment checklist for external user access in Lync Server 2013](lync-server-2013-deployment-checklist-for-external-user-access.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0e14b-113">以前にトポロジビルダーを使用して、エッジトポロジを含む完全なトポロジを定義した場合は、「 <A href="lync-server-2013-define-your-edge-topology.md">Lync server 2013 で edge トポロジを定義</A>する」をスキップして、このセクションの「 <A href="lync-server-2013-publish-your-topology.md">lync server 2013 タスクでトポロジを公開</A>する」を参照してください。「 <A href="lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md">Lync Server 2013 トポロジをエクスポートして、edge インストールタスク用の外部メディアにコピー</A>する」を完了します。</span><span class="sxs-lookup"><span data-stu-id="0e14b-113">If you previously used Topology Builder to define a complete topology, including the edge topology, you do can skip the <A href="lync-server-2013-define-your-edge-topology.md">Define your edge topology in Lync Server 2013</A> and <A href="lync-server-2013-publish-your-topology.md">Publish your topology in Lync Server 2013</A> tasks in this section, but you do need to complete the <A href="lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md">Export your Lync Server 2013 topology and copy it to external media for edge installation</A> task.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="0e14b-114">このセクション中</span><span class="sxs-lookup"><span data-stu-id="0e14b-114">In This Section</span></span>

  - [<span data-ttu-id="0e14b-115">Lync Server 2013 でエッジ トポロジを定義する</span><span class="sxs-lookup"><span data-stu-id="0e14b-115">Define your edge topology in Lync Server 2013</span></span>](lync-server-2013-define-your-edge-topology.md)

  - [<span data-ttu-id="0e14b-116">Lync Server 2013 のトポロジにオプションのディレクター トポロジを定義する</span><span class="sxs-lookup"><span data-stu-id="0e14b-116">Define optional Director topologies in your topology for Lync Server 2013</span></span>](lync-server-2013-define-optional-director-topologies-in-your-topology.md)

  - [<span data-ttu-id="0e14b-117">Lync Server 2013 でのトポロジの公開</span><span class="sxs-lookup"><span data-stu-id="0e14b-117">Publish your topology in Lync Server 2013</span></span>](lync-server-2013-publish-your-topology.md)

  - [<span data-ttu-id="0e14b-118">エッジ インストール用の Lync Server 2013 のトポロジをエクスポートして外部メディアにコピーする</span><span class="sxs-lookup"><span data-stu-id="0e14b-118">Export your Lync Server 2013 topology and copy it to external media for edge installation</span></span>](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

