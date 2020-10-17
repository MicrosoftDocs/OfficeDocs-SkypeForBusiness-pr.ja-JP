---
title: 'Lync Server 2013: トポロジの定義と構成'
description: 'Lync Server 2013: トポロジの定義と構成。'
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
ms.openlocfilehash: ec444a1ddf434c5a80fdc2d56bdba27573da14ab
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542083"
---
# <a name="defining-and-configuring-the-topology-in-lync-server-2013"></a><span data-ttu-id="c1452-103">Lync Server 2013 でのトポロジの定義と構成</span><span class="sxs-lookup"><span data-stu-id="c1452-103">Defining and configuring the topology in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c1452-104">_**トピックの最終更新日:** 2012-09-14_</span><span class="sxs-lookup"><span data-stu-id="c1452-104">_**Topic Last Modified:** 2012-09-14_</span></span>

<span data-ttu-id="c1452-105">トポロジビルダーを使用して、トポロジを定義および構成します。</span><span class="sxs-lookup"><span data-stu-id="c1452-105">You define and configure your topology by using Topology Builder.</span></span> <span data-ttu-id="c1452-106">トポロジビルダーでは、ローカルの Administrators グループまたは権限のあるドメイングループ (Domain Admins など) のメンバーである必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c1452-106">Topology Builder does not require you to be a member of the local Administrators group or a privileged domain group (such as Domain Admins).</span></span> <span data-ttu-id="c1452-107">標準ユーザーでもトポロジを定義できます。</span><span class="sxs-lookup"><span data-stu-id="c1452-107">You can define your topology as a standard user.</span></span> <span data-ttu-id="c1452-108">初めてトポロジ ビルダーを起動して、その後、編集セッションを行う場合、トポロジ ビルダーに現在の構成ドキュメントを読み込ませる場所を指定するようメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c1452-108">When you start Topology Builder on first use and subsequent edit sessions, you are prompted for the location where you want Topology Builder to load the current configuration document.</span></span> <span data-ttu-id="c1452-109">選択肢には以下があります。</span><span class="sxs-lookup"><span data-stu-id="c1452-109">The choices are the following:</span></span>

  - <span data-ttu-id="c1452-110">既存の展開環境からトポロジをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="c1452-110">Download topology from existing deployment</span></span>

  - <span data-ttu-id="c1452-111">ローカル ファイルからトポロジを開く</span><span class="sxs-lookup"><span data-stu-id="c1452-111">Open topology from a local file</span></span>

  - <span data-ttu-id="c1452-112">新しいトポロジ</span><span class="sxs-lookup"><span data-stu-id="c1452-112">New topology</span></span>

<span data-ttu-id="c1452-113">トポロジを既に定義していて、中央管理ストアを設定している場合は、既存の展開からトポロジをダウンロードすることを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c1452-113">If you have already defined a topology and have established the Central Management store, you should choose to download a topology from an existing deployment.</span></span> <span data-ttu-id="c1452-114">トポロジ ビルダーは、データベースを読み取り、現在の定義を取得します。</span><span class="sxs-lookup"><span data-stu-id="c1452-114">Topology Builder will read the database and retrieve the current definition.</span></span> <span data-ttu-id="c1452-115">既存の中央管理ストアがある場合は、常にこのオプションを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c1452-115">If you have an existing Central Management store, you should always choose this option.</span></span>

<span data-ttu-id="c1452-116">中央管理ストアが確立されておらず、以前に保存された構成を編集する場合は、ローカルファイルからトポロジを開くことを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c1452-116">If you have not established a Central Management store and want to edit a previously saved configuration, you should choose to open the topology from a local file.</span></span> <span data-ttu-id="c1452-117">開くファイルは、以前のセッションで保存した構成ファイルになります。</span><span class="sxs-lookup"><span data-stu-id="c1452-117">The file that you will open would be the configuration file that was saved in a previous session.</span></span> <span data-ttu-id="c1452-118">このオプションを使用して、以前保存されたトポロジを編集することができます。</span><span class="sxs-lookup"><span data-stu-id="c1452-118">You can use this option to edit the previously saved topology.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="c1452-p104">トポロジを既に公開している場合は、ローカル構成ファイルを読み込まないでください。 既存の展開環境からトポロジをダウンロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c1452-p104">If you already have a published topology, you should not load a local configuration file. You should choose to download the topology from an existing deployment.</span></span>



</div>

<span data-ttu-id="c1452-121">新しいトポロジビルダー構成を作成する場合は、新しいトポロジを作成することを選択します。</span><span class="sxs-lookup"><span data-stu-id="c1452-121">Choose to create a new topology, if you want to create a new Topology Builder configuration.</span></span> <span data-ttu-id="c1452-122">以前の設計セッションで作成したものと同じファイルとして保存しなければ、以前保存した設計は上書きされません。</span><span class="sxs-lookup"><span data-stu-id="c1452-122">A previously saved design is not overwritten unless you choose to save it as the same file that you created in an earlier design session.</span></span>

<span data-ttu-id="c1452-123">これらの各オプションでは、トポロジビルダー構成ファイルを保存する場所を指定するように求められます。</span><span class="sxs-lookup"><span data-stu-id="c1452-123">In each of these options, you will be prompted for a location to store the Topology Builder configuration file.</span></span> <span data-ttu-id="c1452-124">ファイルの場所は、ローカルの場所、確立されたファイル共有の共有の場所、またはリムーバブル メディアにすることができます。</span><span class="sxs-lookup"><span data-stu-id="c1452-124">The location for the file could be a local location, a shared location on an established file share, or removable media.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c1452-125">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="c1452-125">In This Section</span></span>

  - [<span data-ttu-id="c1452-126">Lync Server 2013 のトポロジビルダーでのトポロジの定義と構成</span><span class="sxs-lookup"><span data-stu-id="c1452-126">Define and configure a topology in Topology Builder for Lync Server 2013</span></span>](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md)

  - [<span data-ttu-id="c1452-127">Lync Server 2013 でのフロントエンドプールまたは Standard Edition サーバーの定義と構成</span><span class="sxs-lookup"><span data-stu-id="c1452-127">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</span></span>](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md)

  - [<span data-ttu-id="c1452-128">Lync Server 2013 での障害復旧用のペアのフロントエンドプールの展開</span><span class="sxs-lookup"><span data-stu-id="c1452-128">Deploying paired Front End pools for disaster recovery in Lync Server 2013</span></span>](lync-server-2013-deploying-paired-front-end-pools-for-disaster-recovery.md)

  - [<span data-ttu-id="c1452-129">Lync Server 2013 でバックエンドサーバーの高可用性を実現するための SQL ミラーリングの展開</span><span class="sxs-lookup"><span data-stu-id="c1452-129">Deploying SQL mirroring for Back End Server high availability in Lync Server 2013</span></span>](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)

  - [<span data-ttu-id="c1452-130">Lync Server 2013 での簡易 Url の編集または構成</span><span class="sxs-lookup"><span data-stu-id="c1452-130">Edit or configure simple URLs in Lync Server 2013</span></span>](lync-server-2013-edit-or-configure-simple-urls.md)

  - [<span data-ttu-id="c1452-131">Lync Server 2013 で中央管理サーバーを選択します。</span><span class="sxs-lookup"><span data-stu-id="c1452-131">Select the Central Management Server in Lync Server 2013</span></span>](lync-server-2013-select-the-central-management-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

