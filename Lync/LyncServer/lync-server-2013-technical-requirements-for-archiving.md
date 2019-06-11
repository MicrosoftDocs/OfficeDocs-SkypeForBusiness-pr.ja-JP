---
title: 'Lync Server 2013: アーカイブの技術要件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Technical requirements for Archiving
ms:assetid: 896d60e2-be4b-462d-8357-4cd307ab7304
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205059(v=OCS.15)
ms:contentKeyID: 48184732
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e4847815f10a48b954d3d83348d95cc137f4b39
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848559"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-archiving-in-lync-server-2013"></a><span data-ttu-id="64866-102">Lync Server 2013 でのアーカイブの技術要件</span><span class="sxs-lookup"><span data-stu-id="64866-102">Technical requirements for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="64866-103">_**最終更新日:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="64866-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="64866-104">Lync Server 2013 の技術要件には、次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="64866-104">Lync Server 2013 technical requirements include the following:</span></span>

  - <span data-ttu-id="64866-105">インフラストラクチャの要件。</span><span class="sxs-lookup"><span data-stu-id="64866-105">Infrastructure requirements.</span></span>

  - <span data-ttu-id="64866-106">アーカイブ用にインストールする必要がある必須ソフトウェア。</span><span class="sxs-lookup"><span data-stu-id="64866-106">Prerequisite software that must be installed for Archiving.</span></span>

  - <span data-ttu-id="64866-107">アーカイブのためのデータストレージ要件。</span><span class="sxs-lookup"><span data-stu-id="64866-107">Data storage requirements for Archiving.</span></span>

  - <span data-ttu-id="64866-108">アーカイブの展開に必要なスケーリングと考慮事項。</span><span class="sxs-lookup"><span data-stu-id="64866-108">Scaling requirements and considerations for your Archiving deployment.</span></span>

  - <span data-ttu-id="64866-109">アーカイブデータベースのパフォーマンス要件と考慮事項。</span><span class="sxs-lookup"><span data-stu-id="64866-109">Performance requirements and considerations for your Archiving databases.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="64866-110">スケーリングとパフォーマンスに関する情報は、この Lync Server 2013 リリースでは利用できません。</span><span class="sxs-lookup"><span data-stu-id="64866-110">Scaling and performance information is not available in this Lync Server 2013 release.</span></span>



</div>

<div>

## <a name="infrastructure-requirements"></a><span data-ttu-id="64866-111">インフラストラクチャの要件</span><span class="sxs-lookup"><span data-stu-id="64866-111">Infrastructure Requirements</span></span>

<span data-ttu-id="64866-112">Lync Server 2013 アーカイブインフラストラクチャの要件は、Lync Server 2013 の展開の場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="64866-112">Lync Server 2013 Archiving infrastructure requirements are the same as for deployment of Lync Server 2013.</span></span> <span data-ttu-id="64866-113">詳細については、計画ドキュメントで「 [Lync Server 2013 のインフラストラクチャ要件を決定](lync-server-2013-determining-your-infrastructure-requirements.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64866-113">For details, see [Determining your infrastructure requirements for Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="archiving-prerequisites"></a><span data-ttu-id="64866-114">アーカイブの前提条件</span><span class="sxs-lookup"><span data-stu-id="64866-114">Archiving Prerequisites</span></span>

<span data-ttu-id="64866-115">Lync Server 2013 は、次の理由によりアーカイブの前提条件を合理化します。</span><span class="sxs-lookup"><span data-stu-id="64866-115">Lync Server 2013 streamlines prerequisites for Archiving because of the following:</span></span>

  - <span data-ttu-id="64866-116">アーカイブサーバーは、サーバーの役割ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="64866-116">Archiving Server is no longer a server role.</span></span> <span data-ttu-id="64866-117">代わりに、統合されたデータ収集エージェントは、アーカイブ用のデータをキャプチャするために、プールのフロントエンドサーバーと標準エディションのサーバーで実行されるため、アーカイブ用に個別のシステムプラットフォームを設定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="64866-117">Instead, Unified Data Collection Agents run on the Front End Servers in a pool and Standard Edition servers to capture data for Archiving, so you do not set up separate system platforms for Archiving.</span></span>

  - <span data-ttu-id="64866-118">アーカイブでは、会議コンテンツファイルの一時的なストレージとして Lync Server 2013 ファイルストレージが使用されるため、アーカイブ用に別のファイルストアを設定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="64866-118">Archiving uses the Lync Server 2013 file storage for temporary storage of meeting content files, so you do not set up a separate file store for archiving.</span></span>

  - <span data-ttu-id="64866-119">Lync Server 2013 では、メッセージキューは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="64866-119">In Lync Server 2013, Message Queuing is not required.</span></span>

</div>

<div>

## <a name="data-storage-requirements-for-archiving"></a><span data-ttu-id="64866-120">アーカイブのためのデータストレージ要件</span><span class="sxs-lookup"><span data-stu-id="64866-120">Data Storage Requirements for Archiving</span></span>

<span data-ttu-id="64866-121">さらに、アーカイブストレージ用のインフラストラクチャを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="64866-121">Additionally, you need to set up the infrastructure for Archiving storage.</span></span> <span data-ttu-id="64866-122">これには、次のいずれかまたは両方が含まれます。</span><span class="sxs-lookup"><span data-stu-id="64866-122">This includes one or both of the following:</span></span>

  - <span data-ttu-id="64866-123">**Microsoft Exchange ストレージ**。</span><span class="sxs-lookup"><span data-stu-id="64866-123">**Microsoft Exchange storage**.</span></span> <span data-ttu-id="64866-124">Meeting content files, such as PowerPoint presentations, are archived as attachments.</span><span class="sxs-lookup"><span data-stu-id="64866-124">Meeting content files, such as PowerPoint presentations, are archived as attachments.</span></span> <span data-ttu-id="64866-125">Microsoft Exchange の統合を使用して、Lync アーカイブデータが Exchange のコンプライアンスデータと共に保存されるようにするには、exchange 2013 を Exchange の展開に使用し、最大記憶域サイズが会議コンテンツファイルの記憶域をサポートしていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="64866-125">If you want to use Microsoft Exchange integration so that Lync archive data is stored with Exchange compliance data, you must use Exchange 2013 for your Exchange deployment and ensure that the maximum storage size supports storage of the meeting content files.</span></span> <span data-ttu-id="64866-126">[Microsoft Exchange 統合] オプションを使用してアーカイブを展開する場合、Lync アーカイブデータは exchange 2013 サーバーをホームとしているユーザーに対してのみ Exchange 2013 のコンプライアンスデータと共に保存されます。</span><span class="sxs-lookup"><span data-stu-id="64866-126">If you deploy Archiving using the Microsoft Exchange integration option, Lync archive data is stored with Exchange 2013 compliance data only for the users who are homed on your Exchange 2013 servers.</span></span> <span data-ttu-id="64866-127">Microsoft Exchange 統合オプションを使用してアーカイブを展開して有効にする前に、Exchange 2013 を展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="64866-127">You must deploy Exchange 2013 prior to deploying and enabling Archiving using the Microsoft Exchange integration option.</span></span> <span data-ttu-id="64866-128">Exchange 2013 ストレージを使用する場合は、Exchange 2013 サーバーをホームにしていない Lync ユーザーがいない限り、アーカイブ用に個別の SQL Server データベースを展開する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="64866-128">If you choose to use Exchange 2013 storage, you do not need to deploy separate SQL Server databases for Archiving, unless you have Lync users who are not homed on your Exchange 2013 servers.</span></span>

  - <span data-ttu-id="64866-129">**アーカイブ用の SQL Server データベースストレージ**。</span><span class="sxs-lookup"><span data-stu-id="64866-129">**SQL Server database storage for Archiving**.</span></span> <span data-ttu-id="64866-130">Exchange 2013 サーバーを使っていないユーザーをサポートする場合、または Microsoft Exchange の統合オプションを使用しない場合は、SQL Server データベースを使ってアーカイブストレージを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="64866-130">To support users who are not homed on Exchange 2013 servers, or if you do not want to use the Microsoft Exchange integration option, you must deploy Archiving storage using a SQL Server database.</span></span> <span data-ttu-id="64866-131">Lync Server 2013 では、次の64ビットバージョンの SQL Server がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="64866-131">Lync Server 2013 supports the following 64-bit versions of SQL Server:</span></span>
    
      - <span data-ttu-id="64866-132">Microsoft SQL Server 2008 R2 Enterprise</span><span class="sxs-lookup"><span data-stu-id="64866-132">Microsoft SQL Server 2008 R2 Enterprise</span></span>
    
      - <span data-ttu-id="64866-133">Microsoft SQL Server 2008 R2 Standard</span><span class="sxs-lookup"><span data-stu-id="64866-133">Microsoft SQL Server 2008 R2 Standard</span></span>
    
      - <span data-ttu-id="64866-134">Microsoft SQL Server 2012 Enterprise</span><span class="sxs-lookup"><span data-stu-id="64866-134">Microsoft SQL Server 2012 Enterprise</span></span>
    
      - <span data-ttu-id="64866-135">Microsoft SQL Server 2012 標準</span><span class="sxs-lookup"><span data-stu-id="64866-135">Microsoft SQL Server 2012 Standard</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="64866-136">Microsoft SQL Server 2008 R2 Express および Microsoft SQL Server 2012 Express はアーカイブに対応していません。</span><span class="sxs-lookup"><span data-stu-id="64866-136">Microsoft SQL Server 2008 R2 Express and Microsoft SQL Server 2012 Express are not supported for Archiving.</span></span> <span data-ttu-id="64866-137">32ビット版の SQL Server はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="64866-137">32-bit versions of SQL Server are not supported.</span></span> <span data-ttu-id="64866-138">SQL Server のその他の要件と制限については、計画ドキュメントまたはサポートサポートドキュメントの「 <A href="lync-server-2013-database-software-support.md">Lync Server 2013 でのデータベースソフトウェアのサポート</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64866-138">For additional SQL Server requirements and restrictions, see <A href="lync-server-2013-database-software-support.md">Database software support in Lync Server 2013</A> in the Planning documentation or in the Supportability documentation.</span></span>

    
    </div>
    
    <span data-ttu-id="64866-139">アーカイブを展開して有効にする前に、SQL Server プラットフォームをセットアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="64866-139">You must set up the SQL Server platforms prior to deploying and enabling Archiving.</span></span> <span data-ttu-id="64866-140">トポロジの公開に使用するアカウントに適切な管理権限とアクセス許可がある場合、トポロジを公開するときにアーカイブ データベース (LcsLog) を作成できます。</span><span class="sxs-lookup"><span data-stu-id="64866-140">If the account to be used to publish the topology has the appropriate administrator rights and permissions, you can create the Archiving database (LcsLog) when you publish your topology.</span></span> <span data-ttu-id="64866-141">また、インストール手順の一部として、後でデータベースを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="64866-141">You can also create the database later, including as part of the installation procedure.</span></span> <span data-ttu-id="64866-142">SQL Server の詳細については、SQL Server の[http://go.microsoft.com/fwlink/p/?linkID=129045](http://go.microsoft.com/fwlink/p/?linkid=129045)TechCenter を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64866-142">For details about SQL Server, see the SQL Server TechCenter at [http://go.microsoft.com/fwlink/p/?linkID=129045](http://go.microsoft.com/fwlink/p/?linkid=129045).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

