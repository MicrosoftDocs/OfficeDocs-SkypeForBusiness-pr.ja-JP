---
title: 'Lync Server 2013: アーカイブの技術要件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for Archiving
ms:assetid: 896d60e2-be4b-462d-8357-4cd307ab7304
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205059(v=OCS.15)
ms:contentKeyID: 48184732
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f12b84149c713ed4684cad7cf9fd3bc33bad8ff
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141873"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-archiving-in-lync-server-2013"></a><span data-ttu-id="29d39-102">Lync Server 2013 でのアーカイブの技術要件</span><span class="sxs-lookup"><span data-stu-id="29d39-102">Technical requirements for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="29d39-103">_**トピックの最終更新日:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="29d39-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="29d39-104">Lync Server 2013 の技術要件は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="29d39-104">Lync Server 2013 technical requirements include the following:</span></span>

  - <span data-ttu-id="29d39-105">インフラストラクチャの要件</span><span class="sxs-lookup"><span data-stu-id="29d39-105">Infrastructure requirements.</span></span>

  - <span data-ttu-id="29d39-106">アーカイブ用にインストールする必要があるソフトウェア</span><span class="sxs-lookup"><span data-stu-id="29d39-106">Prerequisite software that must be installed for Archiving.</span></span>

  - <span data-ttu-id="29d39-107">アーカイブ用のデータ ストレージの要件</span><span class="sxs-lookup"><span data-stu-id="29d39-107">Data storage requirements for Archiving.</span></span>

  - <span data-ttu-id="29d39-108">アーカイブ展開における拡張の要件および考慮事項</span><span class="sxs-lookup"><span data-stu-id="29d39-108">Scaling requirements and considerations for your Archiving deployment.</span></span>

  - <span data-ttu-id="29d39-109">アーカイブ データベースのパフォーマンスの要件および考慮事項</span><span class="sxs-lookup"><span data-stu-id="29d39-109">Performance requirements and considerations for your Archiving databases.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="29d39-110">この Lync Server 2013 リリースでは、スケーリングとパフォーマンス情報は利用できません。</span><span class="sxs-lookup"><span data-stu-id="29d39-110">Scaling and performance information is not available in this Lync Server 2013 release.</span></span>



</div>

<div>

## <a name="infrastructure-requirements"></a><span data-ttu-id="29d39-111">インフラストラクチャの要件</span><span class="sxs-lookup"><span data-stu-id="29d39-111">Infrastructure Requirements</span></span>

<span data-ttu-id="29d39-112">Lync Server 2013 のアーカイブインフラストラクチャの要件は、Lync Server 2013 の展開の場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="29d39-112">Lync Server 2013 Archiving infrastructure requirements are the same as for deployment of Lync Server 2013.</span></span> <span data-ttu-id="29d39-113">詳細については、「計画」のドキュメントの「 [Lync Server 2013 のインフラストラクチャ要件の決定](lync-server-2013-determining-your-infrastructure-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29d39-113">For details, see [Determining your infrastructure requirements for Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="archiving-prerequisites"></a><span data-ttu-id="29d39-114">アーカイブの前提条件</span><span class="sxs-lookup"><span data-stu-id="29d39-114">Archiving Prerequisites</span></span>

<span data-ttu-id="29d39-115">Lync Server 2013 は、以下の理由からアーカイブの前提条件を合理化します。</span><span class="sxs-lookup"><span data-stu-id="29d39-115">Lync Server 2013 streamlines prerequisites for Archiving because of the following:</span></span>

  - <span data-ttu-id="29d39-p102">サーバーの役割からアーカイブ サーバーが除外されました。代わりに、統合データ収集エージェントが、プール内のフロントエンド サーバーと Standard Edition サーバーで実行され、アーカイブ用のデータがキャプチャされます。したがって、アーカイブ用に別のシステム プラットフォームを設定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="29d39-p102">Archiving Server is no longer a server role. Instead, Unified Data Collection Agents run on the Front End Servers in a pool and Standard Edition servers to capture data for Archiving, so you do not set up separate system platforms for Archiving.</span></span>

  - <span data-ttu-id="29d39-118">アーカイブは、Lync Server 2013 のファイルストレージを使用して会議コンテンツファイルを一時的に保存するので、アーカイブ用に別のファイルストアを設定することはありません。</span><span class="sxs-lookup"><span data-stu-id="29d39-118">Archiving uses the Lync Server 2013 file storage for temporary storage of meeting content files, so you do not set up a separate file store for archiving.</span></span>

  - <span data-ttu-id="29d39-119">Lync Server 2013 では、メッセージキューは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="29d39-119">In Lync Server 2013, Message Queuing is not required.</span></span>

</div>

<div>

## <a name="data-storage-requirements-for-archiving"></a><span data-ttu-id="29d39-120">アーカイブ用のデータ ストレージの要件</span><span class="sxs-lookup"><span data-stu-id="29d39-120">Data Storage Requirements for Archiving</span></span>

<span data-ttu-id="29d39-p103">また、アーカイブ ストレージ用のインフラストラクチャを設定する必要があります。これには、次のどちらか、または両方があります。</span><span class="sxs-lookup"><span data-stu-id="29d39-p103">Additionally, you need to set up the infrastructure for Archiving storage. This includes one or both of the following:</span></span>

  - <span data-ttu-id="29d39-123">**Microsoft Exchange ストレージ**</span><span class="sxs-lookup"><span data-stu-id="29d39-123">**Microsoft Exchange storage**.</span></span> <span data-ttu-id="29d39-124">PowerPoint プレゼンテーションなどの会議コンテンツ ファイルは、添付ファイルとしてアーカイブされます。</span><span class="sxs-lookup"><span data-stu-id="29d39-124">Meeting content files, such as PowerPoint presentations, are archived as attachments.</span></span> <span data-ttu-id="29d39-125">Microsoft Exchange 統合を使用して、Lync アーカイブデータが Exchange コンプライアンスデータと共に保存されるようにするには、exchange の展開に Exchange 2013 を使用し、会議コンテンツファイルのストレージが最大の記憶域サイズでサポートされるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="29d39-125">If you want to use Microsoft Exchange integration so that Lync archive data is stored with Exchange compliance data, you must use Exchange 2013 for your Exchange deployment and ensure that the maximum storage size supports storage of the meeting content files.</span></span> <span data-ttu-id="29d39-126">Microsoft Exchange 統合オプションを使用してアーカイブを展開する場合、Lync アーカイブデータは exchange 2013 サーバーに所属しているユーザーの Exchange 2013 コンプライアンスデータのみに格納されます。</span><span class="sxs-lookup"><span data-stu-id="29d39-126">If you deploy Archiving using the Microsoft Exchange integration option, Lync archive data is stored with Exchange 2013 compliance data only for the users who are homed on your Exchange 2013 servers.</span></span> <span data-ttu-id="29d39-127">Microsoft Exchange 統合オプションを使用してアーカイブを展開および有効化する前に、Exchange 2013 を展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="29d39-127">You must deploy Exchange 2013 prior to deploying and enabling Archiving using the Microsoft Exchange integration option.</span></span> <span data-ttu-id="29d39-128">Exchange 2013 ストレージを使用することを選択した場合は、Exchange 2013 サーバーに所属していない Lync ユーザーがいない限り、アーカイブ用に個別の SQL Server データベースを展開する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="29d39-128">If you choose to use Exchange 2013 storage, you do not need to deploy separate SQL Server databases for Archiving, unless you have Lync users who are not homed on your Exchange 2013 servers.</span></span>

  - <span data-ttu-id="29d39-129">**アーカイブ用の SQL Server データベースストレージ**。</span><span class="sxs-lookup"><span data-stu-id="29d39-129">**SQL Server database storage for Archiving**.</span></span> <span data-ttu-id="29d39-130">Exchange 2013 サーバーに所属していないユーザーをサポートする場合、または Microsoft Exchange 統合オプションを使用しない場合は、SQL Server データベースを使用してアーカイブストレージを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="29d39-130">To support users who are not homed on Exchange 2013 servers, or if you do not want to use the Microsoft Exchange integration option, you must deploy Archiving storage using a SQL Server database.</span></span> <span data-ttu-id="29d39-131">Lync Server 2013 では、次の64ビットバージョンの SQL Server がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="29d39-131">Lync Server 2013 supports the following 64-bit versions of SQL Server:</span></span>
    
      - <span data-ttu-id="29d39-132">Microsoft SQL Server 2008 R2 Enterprise</span><span class="sxs-lookup"><span data-stu-id="29d39-132">Microsoft SQL Server 2008 R2 Enterprise</span></span>
    
      - <span data-ttu-id="29d39-133">Microsoft SQL Server 2008 R2 Standard</span><span class="sxs-lookup"><span data-stu-id="29d39-133">Microsoft SQL Server 2008 R2 Standard</span></span>
    
      - <span data-ttu-id="29d39-134">Microsoft SQL Server 2012 Enterprise</span><span class="sxs-lookup"><span data-stu-id="29d39-134">Microsoft SQL Server 2012 Enterprise</span></span>
    
      - <span data-ttu-id="29d39-135">Microsoft SQL Server 2012 Standard</span><span class="sxs-lookup"><span data-stu-id="29d39-135">Microsoft SQL Server 2012 Standard</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="29d39-136">Microsoft SQL Server 2008 R2 Express および Microsoft SQL Server 2012 Express はアーカイブに対してサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="29d39-136">Microsoft SQL Server 2008 R2 Express and Microsoft SQL Server 2012 Express are not supported for Archiving.</span></span> <span data-ttu-id="29d39-137">32ビット版の SQL Server はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="29d39-137">32-bit versions of SQL Server are not supported.</span></span> <span data-ttu-id="29d39-138">SQL Server のその他の要件および制限については、「計画」のドキュメントまたは「サポート」のドキュメントの「 <A href="lync-server-2013-database-software-support.md">Lync Server 2013 のデータベースソフトウェアサポート</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29d39-138">For additional SQL Server requirements and restrictions, see <A href="lync-server-2013-database-software-support.md">Database software support in Lync Server 2013</A> in the Planning documentation or in the Supportability documentation.</span></span>

    
    </div>
    
    <span data-ttu-id="29d39-139">アーカイブを展開して有効にする前に、SQL Server プラットフォームをセットアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="29d39-139">You must set up the SQL Server platforms prior to deploying and enabling Archiving.</span></span> <span data-ttu-id="29d39-140">トポロジの公開に使用するアカウントに適切な管理権限とアクセス許可がある場合、トポロジを公開するときにアーカイブ データベース (LcsLog) を作成できます。</span><span class="sxs-lookup"><span data-stu-id="29d39-140">If the account to be used to publish the topology has the appropriate administrator rights and permissions, you can create the Archiving database (LcsLog) when you publish your topology.</span></span> <span data-ttu-id="29d39-141">インストール手順の一部を含め、データベースを後で作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="29d39-141">You can also create the database later, including as part of the installation procedure.</span></span> <span data-ttu-id="29d39-142">SQL Server の詳細については、SQL Server TechCenter [https://go.microsoft.com/fwlink/p/?linkID=129045](https://go.microsoft.com/fwlink/p/?linkid=129045)の「」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29d39-142">For details about SQL Server, see the SQL Server TechCenter at [https://go.microsoft.com/fwlink/p/?linkID=129045](https://go.microsoft.com/fwlink/p/?linkid=129045).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

