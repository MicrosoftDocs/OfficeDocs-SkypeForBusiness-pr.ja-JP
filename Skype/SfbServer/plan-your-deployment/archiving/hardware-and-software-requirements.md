---
title: Skype for Business Server 2015 のアーカイブに関するハードウェアおよびソフトウェア要件
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 896d60e2-be4b-462d-8357-4cd307ab7304
description: '概要: ビジネス サーバー 2015 の Skype でアーカイブ用のハードウェアおよびソフトウェアの要件の詳細については、このトピックを読みます。'
ms.openlocfilehash: d8d8039e95a3b578551d0db6ff219fe8f3c1e5c5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="hardware-and-software-requirements-for-archiving-in-skype-for-business-server-2015"></a><span data-ttu-id="41cc9-103">Skype for Business Server 2015 のアーカイブに関するハードウェアおよびソフトウェア要件</span><span class="sxs-lookup"><span data-stu-id="41cc9-103">Hardware and software requirements for archiving in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="41cc9-104">**の概要:**ビジネス サーバー 2015 の Skype でアーカイブ用のハードウェアおよびソフトウェアの要件の詳細については、このトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="41cc9-104">**Summary:** Read this topic to learn about hardware and software requirements for archiving in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="41cc9-105">ビジネス サーバー 2015 のアーカイブのための Skype が、一部のフロント エンドの役割のため、別のサーバーをインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="41cc9-105">Skype for Business Server 2015 archiving is now part of the Front End role, so you do not need to install a separate server.</span></span> <span data-ttu-id="41cc9-106">次の要件を考慮する必要があります、ただし。</span><span class="sxs-lookup"><span data-stu-id="41cc9-106">You do, however, need to consider the following requirements:</span></span>
  
- <span data-ttu-id="41cc9-107">インフラストラクチャの要件</span><span class="sxs-lookup"><span data-stu-id="41cc9-107">Infrastructure requirements</span></span>
    
- <span data-ttu-id="41cc9-108">必要なソフトウェアの要件</span><span class="sxs-lookup"><span data-stu-id="41cc9-108">Prerequisite software requirements</span></span>
    
- <span data-ttu-id="41cc9-109">データ記憶域の要件</span><span class="sxs-lookup"><span data-stu-id="41cc9-109">Data storage requirements</span></span>
    
## <a name="infrastructure-requirements"></a><span data-ttu-id="41cc9-110">インフラストラクチャの要件</span><span class="sxs-lookup"><span data-stu-id="41cc9-110">Infrastructure requirements</span></span>

<span data-ttu-id="41cc9-111">ビジネス ・ サーバのアーカイブのインフラストラクチャ要件の Skype は、Skype のビジネス サーバーの展開の場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="41cc9-111">Skype for Business Server Archiving infrastructure requirements are the same as for deployment of Skype for Business Server.</span></span> <span data-ttu-id="41cc9-112">詳細については、[ビジネス環境に、Skype の要件](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="41cc9-112">For details, see [Requirements for your Skype for Business environment](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md).</span></span> 
  
## <a name="prerequisite-software-requirements"></a><span data-ttu-id="41cc9-113">必要なソフトウェアの要件</span><span class="sxs-lookup"><span data-stu-id="41cc9-113">Prerequisite software requirements</span></span>

<span data-ttu-id="41cc9-114">Skype ビジネス サーバーのためのアーカイブの前提条件は次の理由により、Lync Server の以前のバージョンよりも簡単です。</span><span class="sxs-lookup"><span data-stu-id="41cc9-114">Archiving prerequisites for Skype for Business Server are simpler than earlier versions of Lync Server because of the following:</span></span> 
  
- <span data-ttu-id="41cc9-115">アーカイブ不要になったサーバーの役割であるために、アーカイブのための別のサーバーをインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="41cc9-115">Because archiving is no longer a server role, you do not need to install a separate server for archiving.</span></span> <span data-ttu-id="41cc9-116">代わりに、すべての Enterprise Edition フロントエンド プールとすべての Standard Edition サーバーで、統合データ収集エージェントが自動的にインストールされ、有効になります。</span><span class="sxs-lookup"><span data-stu-id="41cc9-116">Instead, Unified Data Collection Agents are installed and activated automatically on every Enterprise Edition Front End pool and every Standard Edition Server.</span></span> <span data-ttu-id="41cc9-117">トポロジ ビルダーを使用して、アーカイブ トポロジを有効にして発行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="41cc9-117">You will need to enable and publish your archiving topology by using Topology Builder.</span></span>
    
- <span data-ttu-id="41cc9-118">アーカイブ アーカイブのための別のファイル ストアを設定しないために、コンテンツ ファイルを満たすための一時的な記憶域のビジネス サーバー ファイルの記憶域、Skype を使用します。</span><span class="sxs-lookup"><span data-stu-id="41cc9-118">Archiving uses the Skype for Business Server file storage for temporary storage of meeting content files, so you do not set up a separate file store for archiving.</span></span>
    
- <span data-ttu-id="41cc9-119">ビジネス サーバーの Skype で Microsoft メッセージ キューは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="41cc9-119">In Skype for Business Server, Microsoft Message Queuing is not required.</span></span>
    
## <a name="data-storage-requirements"></a><span data-ttu-id="41cc9-120">データ記憶域の要件</span><span class="sxs-lookup"><span data-stu-id="41cc9-120">Data Storage requirements</span></span>

<span data-ttu-id="41cc9-p104">アーカイブ ストレージ用のインフラストラクチャを設定する必要があります。これを行うには、次のどちらか、または両方を選択します。</span><span class="sxs-lookup"><span data-stu-id="41cc9-p104">You will need to set up the infrastructure for archiving storage. This includes choosing one or both of the following options:</span></span>
  
- <span data-ttu-id="41cc9-123">**Microsoft Exchange の記憶域**です。</span><span class="sxs-lookup"><span data-stu-id="41cc9-123">**Microsoft Exchange storage**.</span></span> <span data-ttu-id="41cc9-124">PowerPoint プレゼンテーションなどの会議コンテンツ ファイルは、添付ファイルとしてアーカイブされます。</span><span class="sxs-lookup"><span data-stu-id="41cc9-124">Meeting content files, such as PowerPoint presentations, are archived as attachments.</span></span> <span data-ttu-id="41cc9-125">Exchange 対応のデータのアーカイブ データをビジネス用の Skype を格納する場合は、Exchange を使用して、Exchange を展開するため、記憶域の最大サイズがミーティングのコンテンツ ファイルのストレージをサポートしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="41cc9-125">If you want to store Skype for Business archive data with Exchange compliance data, you must use Exchange for your Exchange deployment and ensure that the maximum storage size supports storage of the meeting content files.</span></span> <span data-ttu-id="41cc9-126">展開して、Microsoft Exchange の統合オプションを使用してアーカイブを有効にする前に Exchange を展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="41cc9-126">You must deploy Exchange prior to deploying and enabling archiving using the Microsoft Exchange integration option.</span></span> 
    
    <span data-ttu-id="41cc9-127">Exchange の記憶域を使用する場合は、する必要はありません、アーカイブの別の SQL Server データベースを展開する Exchange サーバー上にはないビジネス ユーザーに Skype がない限り。</span><span class="sxs-lookup"><span data-stu-id="41cc9-127">If you choose to use Exchange storage, you do not need to deploy separate SQL Server databases for archiving, unless you have Skype for Business users who are not homed on your Exchange servers.</span></span> <span data-ttu-id="41cc9-128">Microsoft Exchange の統合オプションを使用してアーカイブを展開する場合、Exchange サーバーが置かれているユーザー専用の Exchange 対応のデータと Skype ビジネス アーカイブ ・ データが格納されます。</span><span class="sxs-lookup"><span data-stu-id="41cc9-128">If you deploy archiving using the Microsoft Exchange integration option, Skype for Business archive data is stored with Exchange compliance data only for the users who are homed on your Exchange servers.</span></span> 
    
- <span data-ttu-id="41cc9-129">**Skype ビジネス サーバー ・ アーカイブ ・ ストレージ**です。</span><span class="sxs-lookup"><span data-stu-id="41cc9-129">**Skype for Business Server archiving storage**.</span></span> <span data-ttu-id="41cc9-130">Exchange サーバーではないユーザーをサポートする Microsoft Exchange の統合オプションを使用しない場合は、SQL Server データベースを使用して、アーカイブ ・ ストレージに配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="41cc9-130">To support users who are not homed on Exchange servers, or if you do not want to use the Microsoft Exchange integration option, you must deploy archiving storage using a SQL Server database.</span></span> <span data-ttu-id="41cc9-131">Skype ビジネス サーバー用には、次の 64 ビット バージョンの SQL Server がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="41cc9-131">Skype for Business Server supports the following 64-bit versions of SQL Server:</span></span>
    
  - <span data-ttu-id="41cc9-132">Microsoft SQL Server 2008 R2 エンタープライズ</span><span class="sxs-lookup"><span data-stu-id="41cc9-132">Microsoft SQL Server 2008 R2 Enterprise</span></span>
    
  - <span data-ttu-id="41cc9-133">Microsoft SQL Server 2008 R2 の標準</span><span class="sxs-lookup"><span data-stu-id="41cc9-133">Microsoft SQL Server 2008 R2 Standard</span></span>
    
  - <span data-ttu-id="41cc9-134">Microsoft SQL Server 2012 のエンタープライズ</span><span class="sxs-lookup"><span data-stu-id="41cc9-134">Microsoft SQL Server 2012 Enterprise</span></span>
    
  - <span data-ttu-id="41cc9-135">Microsoft SQL Server 2012 の標準</span><span class="sxs-lookup"><span data-stu-id="41cc9-135">Microsoft SQL Server 2012 Standard</span></span>
    
  - <span data-ttu-id="41cc9-136">2014 企業の Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="41cc9-136">Microsoft SQL Server 2014 Enterprise</span></span>
    
  - <span data-ttu-id="41cc9-137">2014 標準の Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="41cc9-137">Microsoft SQL Server 2014 Standard</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="41cc9-138">アーカイブには、Microsoft SQL Server の高速バージョンはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="41cc9-138">Microsoft SQL Server Express versions are not supported for archiving.</span></span> <span data-ttu-id="41cc9-139">SQL Server の 32 ビット バージョンはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="41cc9-139">32-bit versions of SQL Server are not supported.</span></span> <span data-ttu-id="41cc9-140">追加の SQL Server の要件と制限は、[ビジネス環境に、Skype の要件](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="41cc9-140">For additional SQL Server requirements and restrictions, see [Requirements for your Skype for Business environment](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md).</span></span> 
  
    <span data-ttu-id="41cc9-141">展開とアーカイブを有効にする前に SQL Server プラットフォームを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="41cc9-141">You must set up the SQL Server platforms prior to deploying and enabling archiving.</span></span> <span data-ttu-id="41cc9-142">トポロジの公開に使用するアカウントに適切な管理権限とアクセス許可がある場合、トポロジを公開するときにアーカイブ データベース (LcsLog) を作成できます。</span><span class="sxs-lookup"><span data-stu-id="41cc9-142">If the account to be used to publish the topology has the appropriate administrator rights and permissions, you can create the Archiving database (LcsLog) when you publish your topology.</span></span> <span data-ttu-id="41cc9-143">インストール手順の一部を含め、データベースを後で作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="41cc9-143">You can also create the database later, included as part of the installation procedure.</span></span> <span data-ttu-id="41cc9-144">詳細については、SQL Server は、 [SQL Server TechCenter](https://go.microsoft.com/fwlink/p/?linkID=129045)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="41cc9-144">For details about SQL Server, see the [SQL Server TechCenter](https://go.microsoft.com/fwlink/p/?linkID=129045).</span></span>
    
    <span data-ttu-id="41cc9-145">アーカイブに関する負荷の増加は、重大な問題になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="41cc9-145">The load increase for archiving can be significant.</span></span> <span data-ttu-id="41cc9-146">そのため、ディスク領域は十分にフロント エンド サーバーがアーカイブを有効にすることを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="41cc9-146">Therefore, you should ensure that disk space is adequate for Front End Servers on which archiving is enabled.</span></span>
    

