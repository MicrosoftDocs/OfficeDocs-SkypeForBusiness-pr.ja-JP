---
title: 'Lync Server 2013: トポロジの定義と構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining and configuring the topology
ms:assetid: 51d1601e-4f83-48d4-ad08-3b4d5e2003aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398339(v=OCS.15)
ms:contentKeyID: 48184146
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8430ec5cc8b362aa78f97afc24ab0e588c7bc650
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728377"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-and-configuring-the-topology-in-lync-server-2013"></a><span data-ttu-id="d8c96-102">Lync Server 2013 でのトポロジの定義と構成</span><span class="sxs-lookup"><span data-stu-id="d8c96-102">Defining and configuring the topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d8c96-103">_**最終更新日:** 2012-09-14_</span><span class="sxs-lookup"><span data-stu-id="d8c96-103">_**Topic Last Modified:** 2012-09-14_</span></span>

<span data-ttu-id="d8c96-104">トポロジを定義して構成するには、トポロジビルダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="d8c96-104">You define and configure your topology by using Topology Builder.</span></span> <span data-ttu-id="d8c96-105">トポロジビルダーでは、ローカルの管理者グループまたは (Domain Admins など) の権限を持つドメイングループのメンバーである必要はありません。</span><span class="sxs-lookup"><span data-stu-id="d8c96-105">Topology Builder does not require you to be a member of the local Administrators group or a privileged domain group (such as Domain Admins).</span></span> <span data-ttu-id="d8c96-106">トポロジは標準ユーザーとして定義できます。</span><span class="sxs-lookup"><span data-stu-id="d8c96-106">You can define your topology as a standard user.</span></span> <span data-ttu-id="d8c96-107">最初の使用時と後続の編集セッションでトポロジビルダーを起動すると、トポロジビルダーで現在の構成ドキュメントを読み込む場所を確認するメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d8c96-107">When you start Topology Builder on first use and subsequent edit sessions, you are prompted for the location where you want Topology Builder to load the current configuration document.</span></span> <span data-ttu-id="d8c96-108">以下の選択肢があります。</span><span class="sxs-lookup"><span data-stu-id="d8c96-108">The choices are the following:</span></span>

  - <span data-ttu-id="d8c96-109">既存の展開環境からトポロジをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="d8c96-109">Download topology from existing deployment</span></span>

  - <span data-ttu-id="d8c96-110">ローカルファイルからトポロジを開く</span><span class="sxs-lookup"><span data-stu-id="d8c96-110">Open topology from a local file</span></span>

  - <span data-ttu-id="d8c96-111">新しいトポロジ</span><span class="sxs-lookup"><span data-stu-id="d8c96-111">New topology</span></span>

<span data-ttu-id="d8c96-112">トポロジを既に定義していて、全体管理ストアを確立している場合は、既存の展開からトポロジをダウンロードすることを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8c96-112">If you have already defined a topology and have established the Central Management store, you should choose to download a topology from an existing deployment.</span></span> <span data-ttu-id="d8c96-113">トポロジビルダーはデータベースを読み取り、現在の定義を取得します。</span><span class="sxs-lookup"><span data-stu-id="d8c96-113">Topology Builder will read the database and retrieve the current definition.</span></span> <span data-ttu-id="d8c96-114">既存のサーバーの全体管理ストアがある場合は、常にこのオプションを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8c96-114">If you have an existing Central Management store, you should always choose this option.</span></span>

<span data-ttu-id="d8c96-115">一元管理ストアを確立していない場合に、以前に保存した構成を編集するには、ローカルファイルからトポロジを開くように選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8c96-115">If you have not established a Central Management store and want to edit a previously saved configuration, you should choose to open the topology from a local file.</span></span> <span data-ttu-id="d8c96-116">開こうとしているファイルは、以前のセッションで保存された構成ファイルです。</span><span class="sxs-lookup"><span data-stu-id="d8c96-116">The file that you will open would be the configuration file that was saved in a previous session.</span></span> <span data-ttu-id="d8c96-117">このオプションを使用して、以前に保存したトポロジを編集できます。</span><span class="sxs-lookup"><span data-stu-id="d8c96-117">You can use this option to edit the previously saved topology.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="d8c96-118">公開されているトポロジを既に持っている場合は、ローカル構成ファイルを読み込まないでください。</span><span class="sxs-lookup"><span data-stu-id="d8c96-118">If you already have a published topology, you should not load a local configuration file.</span></span> <span data-ttu-id="d8c96-119">既存の展開からトポロジをダウンロードすることを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8c96-119">You should choose to download the topology from an existing deployment.</span></span>



</div>

<span data-ttu-id="d8c96-120">新しいトポロジビルダー構成を作成する場合は、新しいトポロジを作成します。</span><span class="sxs-lookup"><span data-stu-id="d8c96-120">Choose to create a new topology, if you want to create a new Topology Builder configuration.</span></span> <span data-ttu-id="d8c96-121">以前のデザインセッションで作成したのと同じファイルとして保存するように選択しない限り、以前に保存したデザインは上書きされません。</span><span class="sxs-lookup"><span data-stu-id="d8c96-121">A previously saved design is not overwritten unless you choose to save it as the same file that you created in an earlier design session.</span></span>

<span data-ttu-id="d8c96-122">これらの各オプションでは、トポロジビルダー構成ファイルを保存する場所を指定するように求められます。</span><span class="sxs-lookup"><span data-stu-id="d8c96-122">In each of these options, you will be prompted for a location to store the Topology Builder configuration file.</span></span> <span data-ttu-id="d8c96-123">ファイルの場所は、ローカルの場所、確立されたファイル共有上の共有の場所、リムーバブルメディアのいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="d8c96-123">The location for the file could be a local location, a shared location on an established file share, or removable media.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d8c96-124">このセクション中</span><span class="sxs-lookup"><span data-stu-id="d8c96-124">In This Section</span></span>

  - [<span data-ttu-id="d8c96-125">Lync Server 2013 のトポロジ ビルダーでのトポロジの定義と構成</span><span class="sxs-lookup"><span data-stu-id="d8c96-125">Define and configure a topology in Topology Builder for Lync Server 2013</span></span>](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md)

  - [<span data-ttu-id="d8c96-126">Lync Server 2013 でフロントエンド プールまたは Standard Edition サーバーを定義および構成する</span><span class="sxs-lookup"><span data-stu-id="d8c96-126">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</span></span>](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md)

  - [<span data-ttu-id="d8c96-127">Lync Server 2013 での障害復旧用のペアのフロント エンド プールの展開</span><span class="sxs-lookup"><span data-stu-id="d8c96-127">Deploying paired Front End pools for disaster recovery in Lync Server 2013</span></span>](lync-server-2013-deploying-paired-front-end-pools-for-disaster-recovery.md)

  - [<span data-ttu-id="d8c96-128">Lync Server 2013 でのバックエンド サーバーの高可用性を実現するための SQL ミラーリングの展開</span><span class="sxs-lookup"><span data-stu-id="d8c96-128">Deploying SQL mirroring for Back End Server high availability in Lync Server 2013</span></span>](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)

  - [<span data-ttu-id="d8c96-129">Lync Server 2013 での簡単な URL の編集または構成</span><span class="sxs-lookup"><span data-stu-id="d8c96-129">Edit or configure simple URLs in Lync Server 2013</span></span>](lync-server-2013-edit-or-configure-simple-urls.md)

  - [<span data-ttu-id="d8c96-130">Lync Server 2013 での中央管理サーバーの選択</span><span class="sxs-lookup"><span data-stu-id="d8c96-130">Select the Central Management Server in Lync Server 2013</span></span>](lync-server-2013-select-the-central-management-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

