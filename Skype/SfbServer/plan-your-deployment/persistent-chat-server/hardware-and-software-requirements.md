---
title: Skype for Business Server 2015 の常設チャット サーバーのハードウェアおよびソフトウェア要件
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 692b7d99-1bc9-4c99-a050-2bc2be8688b2
description: '概要: ビジネス サーバー 2015 の Skype での永続的なチャット サーバーのハードウェアおよびソフトウェアの要件の詳細については、このトピックを読みます。'
ms.openlocfilehash: a56f939360edae0da47198e4a3810f70712b6ab8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="hardware-and-software-requirements-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="38b20-103">Skype for Business Server 2015 の常設チャット サーバーのハードウェアおよびソフトウェア要件</span><span class="sxs-lookup"><span data-stu-id="38b20-103">Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="38b20-104">**の概要:**ビジネス サーバー 2015 の Skype での永続的なチャット サーバーのハードウェアおよびソフトウェアの要件の詳細については、このトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="38b20-104">**Summary:** Read this topic to learn about hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="38b20-105">ビジネス サーバー 2015 の Enterprise Edition または Standard Edition は、Skype で永続的なチャット サーバーをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="38b20-105">Persistent Chat Server can be installed with Skype for Business Server 2015 Enterprise Edition or Standard Edition.</span></span> <span data-ttu-id="38b20-106">要件は、ビジネス サーバー 2015 の Skype のエディションをインストールして、ビジネスのパフォーマンスの要件によって異なります。</span><span class="sxs-lookup"><span data-stu-id="38b20-106">Requirements depend on which edition of Skype for Business Server 2015 you have installed, and the performance requirements of your business.</span></span> <span data-ttu-id="38b20-107">Enterprise Edition は 80,000 同時ユーザーまでサポートできます。Standard Edition は、最大 20,000 人のユーザーをサポートできます。</span><span class="sxs-lookup"><span data-stu-id="38b20-107">Enterprise Edition can support up to 80,000 concurrent users; Standard Edition can support up to 20,000 concurrent users.</span></span> <span data-ttu-id="38b20-108">永続的なチャットは、フロント エンド コンポーネントとバック エンド SQL のデータベース コンポーネントで構成されます。</span><span class="sxs-lookup"><span data-stu-id="38b20-108">Persistent Chat consists of a front-end component as well as a back-end SQL database component.</span></span>
  
<span data-ttu-id="38b20-109">永続的なチャット サーバーを展開する前に、次のハードウェアおよびソフトウェアの要件が満たされていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="38b20-109">Before you deploy Persistent Chat Server, you must ensure that the following hardware and software requirements are met:</span></span>
  
- <span data-ttu-id="38b20-110">ビジネス サーバー 2015、永続的なチャット サーバー、データベース サーバー、およびファイル ・ サーバの Skype をサポートするために最低限の要件を満たしているハードウェアです。</span><span class="sxs-lookup"><span data-stu-id="38b20-110">Hardware that meets minimum requirements to support Skype for Business Server 2015, Persistent Chat Server, database servers, and file servers.</span></span> <span data-ttu-id="38b20-111">詳細については、[ビジネス サーバー 2015 の Skype のサーバーの要件](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="38b20-111">For more information, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span></span>
    
- <span data-ttu-id="38b20-112">サポートされているオペレーティング システムおよびデータベース ソフトウェア。</span><span class="sxs-lookup"><span data-stu-id="38b20-112">Supported operating system and database software.</span></span>
    
    <span data-ttu-id="38b20-113">詳細についてはサポートされているオペレーティング システムおよびデータベース ソフトウェア、および Windows の更新の必要性、[ビジネス サーバー 2015 の Skype のサーバーの要件](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="38b20-113">For details about supported operating systems and database software, and Windows update requirements, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span></span>
    
- <span data-ttu-id="38b20-114">ビジネス 2015 のフロント エンド サーバーの Skype です。</span><span class="sxs-lookup"><span data-stu-id="38b20-114">Skype for Business Server 2015 Front End Server.</span></span> <span data-ttu-id="38b20-115">フロント エンド サーバーは、のセッション開始プロトコル (SIP) ルーティングでは、永続的なチャット サーバーとの永続的なチャット機能を実行しているコンピューター間の通信を実現する基盤です。</span><span class="sxs-lookup"><span data-stu-id="38b20-115">The Front End Server is the foundation for Session Initiation Protocol (SIP) routing, which makes communication between computers running Persistent Chat Server and the Persistent Chat functionality possible.</span></span> 
    
- <span data-ttu-id="38b20-116">メッセージ キュー ソフトウェア。</span><span class="sxs-lookup"><span data-stu-id="38b20-116">Message Queuing software.</span></span> <span data-ttu-id="38b20-117">展開されている場合は、永続的なチャット サーバーと永続的なチャット コンプライアンス サービスで使用されます。</span><span class="sxs-lookup"><span data-stu-id="38b20-117">Used by the Persistent Chat Server and Persistent Chat Compliance service, if deployed.</span></span>
    
<span data-ttu-id="38b20-118">次のセクションでは、永続的なチャット サーバーと永続的なチャット データを格納しているデータベースの特定の要件について説明します。</span><span class="sxs-lookup"><span data-stu-id="38b20-118">The following sections describe the specific requirements for Persistent Chat Server and the database that stores the Persistent Chat data.</span></span>
  
## <a name="front-end-server-requirements"></a><span data-ttu-id="38b20-119">フロント エンド サーバーの要件</span><span class="sxs-lookup"><span data-stu-id="38b20-119">Front End Server requirements</span></span>

<span data-ttu-id="38b20-120">フロント エンド サーバーの要件は、Skype でチャットのサーバーが永続的なビジネス サーバー 2015 の Enterprise Edition または Standard Edition を展開するかどうかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="38b20-120">Front End Server requirements depend on whether you are deploying Persistent Chat Server with Skype for Business Server 2015 Enterprise Edition or Standard Edition.</span></span>
  
- <span data-ttu-id="38b20-121">ビジネス サーバー 2015 エンタープライズ エディションの Skype での永続的なチャット サーバーを展開する場合、永続的なチャット サーバー フロント エンド サーバー Enterprise Edition プール内の 1 つまたは複数のスタンドアロン コンピューターに展開できます。</span><span class="sxs-lookup"><span data-stu-id="38b20-121">If you are deploying Persistent Chat Server with Skype for Business Server 2015 Enterprise Edition, you can deploy the Persistent Chat Server Front End Server on one or more standalone computers in the Enterprise Edition pool.</span></span> <span data-ttu-id="38b20-122">永続的なチャット フロント エンド サーバー上、Skype を連結できない場合は、ビジネス 2015 フロント エンド サーバーにします。</span><span class="sxs-lookup"><span data-stu-id="38b20-122">You cannot collocate the Persistent Chat Front End Servers on the Skype for Business Server 2015 Front End Server.</span></span> 
    
    <span data-ttu-id="38b20-123">1 つ永続的なチャット サーバー フロント エンド サーバーでは、20,000 のアクティブなユーザーをサポートできます。</span><span class="sxs-lookup"><span data-stu-id="38b20-123">A single Persistent Chat Server Front End Server can support 20,000 active users.</span></span> <span data-ttu-id="38b20-124">80,000 の同時接続ユーザーの合計をサポートできるため、最大 4 つのアクティブなフロント エンドを持つ永続的なチャット サーバー プールを持つことができます。</span><span class="sxs-lookup"><span data-stu-id="38b20-124">You can have a Persistent Chat Server pool with up to 4 active front ends thereby supporting a total of 80,000 concurrent users.</span></span> 
    
- <span data-ttu-id="38b20-125">ビジネス サーバー 2015 の Standard Edition の Skype での永続的なチャット サーバーを展開する場合は、フロント エンド サーバーとの永続的なチャットを集約できます。</span><span class="sxs-lookup"><span data-stu-id="38b20-125">If you are deploying Persistent Chat Server with Skype for Business Server 2015 Standard Edition, you can collocate Persistent Chat with the Front End Server.</span></span> <span data-ttu-id="38b20-126">このシングル サーバー配置では、最大 20,000 ユーザーをサポートできます。</span><span class="sxs-lookup"><span data-stu-id="38b20-126">This single server deployment can support up to 20,000 users.</span></span> 
    
## <a name="persistent-chat-server-database-requirements"></a><span data-ttu-id="38b20-127">永続的なチャット サーバーのデータベースの要件</span><span class="sxs-lookup"><span data-stu-id="38b20-127">Persistent Chat Server database requirements</span></span>

<span data-ttu-id="38b20-128">永続的なチャット サーバーには、チャットの履歴とコンテンツ、構成データ、ユーザー プロビジョニング データ、およびその他の関連するメタデータを格納する SQL Server データベースのソフトウェアが必要です。</span><span class="sxs-lookup"><span data-stu-id="38b20-128">Persistent Chat Server requires SQL Server database software to store chat room history and content, configuration data, user provisioning data, and other relevant metadata.</span></span> <span data-ttu-id="38b20-129">必要に応じて、コンプライアンス データを格納するのに永続的なチャット コンプライアンス データベースを使用します。</span><span class="sxs-lookup"><span data-stu-id="38b20-129">Optionally, it uses the Persistent Chat Compliance database to store compliance data.</span></span> <span data-ttu-id="38b20-130">同一の SQL Server、または、同じ SQL インスタンスも、バックエンド データベースとの永続的なチャット データベースを共存させることができます。</span><span class="sxs-lookup"><span data-stu-id="38b20-130">Persistent Chat databases can be collocated on the same SQL Server, or even the same SQL instance, as the back-end databases.</span></span> 
  
- <span data-ttu-id="38b20-131">ビジネス サーバー 2015 エンタープライズ エディションの Skype で永続的なチャット サーバーをインストールする場合、最適なパフォーマンスを確実にお勧め、永続的なチャットのファイル ストアをインストールすることです。</span><span class="sxs-lookup"><span data-stu-id="38b20-131">If you are installing Persistent Chat Server with Skype for Business Server 2015 Enterprise Edition, to ensure optimum performance, it is recommended that you install the Persistent Chat file store.</span></span>
    
- <span data-ttu-id="38b20-132">ビジネス サーバー 2015 Standard edition は、Skype で永続的なチャット サーバーをインストールする場合、永続的なチャット ストア バック エンド サーバーのローカルの SQL Server Express インスタンスに配置できます。</span><span class="sxs-lookup"><span data-stu-id="38b20-132">If you are installing Persistent Chat Server with Skype for Business Server 2015 Standard edition, you can deploy the Persistent Chat Store Back End Server on the local SQL Server Express instance.</span></span>
    
- <span data-ttu-id="38b20-133">(Mgc) 永続的なチャット データベースとコンプライアンス データベース (mgccomp) は、別の SQL サーバーまたは SQL Server の同じインスタンスに配置できます。</span><span class="sxs-lookup"><span data-stu-id="38b20-133">The Persistent Chat database (mgc) and the compliance database (mgccomp) can be located in the same instance of SQL Server or on different SQL Servers.</span></span>
    
<span data-ttu-id="38b20-134">データベース サーバー プラットフォームを準備するには、各コンピューターがハードウェア要件を満たしていることを確認した後、必要なソフトウェアをインストールします。</span><span class="sxs-lookup"><span data-stu-id="38b20-134">To prepare a database server platform, be sure that each computer meets the hardware requirements, and then install the prerequisite software.</span></span> <span data-ttu-id="38b20-135">データベースの永続的なチャット サーバーのサーバー プラットフォームでは、ビジネス サーバー 2015 のバックエンド データベース サーバーに、Skype と同じハードウェアが必要です。</span><span class="sxs-lookup"><span data-stu-id="38b20-135">The server platform for the Persistent Chat database servers requires the same hardware as the Skype for Business Server 2015 back-end database server.</span></span> <span data-ttu-id="38b20-136">詳細については、[ビジネス サーバー 2015 の Skype のサーバーの要件](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="38b20-136">For details, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span></span>
  
<span data-ttu-id="38b20-137">次のどちらかのソフトウェア アプリケーションがデータベース サーバーにインストールされていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="38b20-137">On the database server, be sure that one of the following software applications is installed:</span></span>
  
- <span data-ttu-id="38b20-138">Microsoft SQL Server 2012。</span><span class="sxs-lookup"><span data-stu-id="38b20-138">Microsoft SQL Server 2012.</span></span> <span data-ttu-id="38b20-139">Microsoft SQL Server 2012 をインストールする方法の詳細については、 [SQL Server 2012 のインストール](https://go.microsoft.com/fwlink/p/?LinkID=248559)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="38b20-139">For details about how to install Microsoft SQL Server 2012, see [Install SQL Server 2012](https://go.microsoft.com/fwlink/p/?LinkID=248559).</span></span>
    
- <span data-ttu-id="38b20-140">Microsoft SQL Server 2008 R2。</span><span class="sxs-lookup"><span data-stu-id="38b20-140">Microsoft SQL Server 2008 R2.</span></span> <span data-ttu-id="38b20-141">Microsoft SQL Server の 2008 R2 をインストールする方法の詳細については、 [SQL Server のインストール (SQL Server 2008 R2)](https://go.microsoft.com/fwlink/p/?LinkId=275702)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="38b20-141">For details about how to install Microsoft SQL Server 2008 R2, see [SQL Server Installation (SQL Server 2008 R2)](https://go.microsoft.com/fwlink/p/?LinkId=275702).</span></span>
    
## <a name="persistent-chat-server-certificate-requirements"></a><span data-ttu-id="38b20-142">永続的なチャット サーバーの証明書の要件</span><span class="sxs-lookup"><span data-stu-id="38b20-142">Persistent Chat Server certificate requirements</span></span>

<span data-ttu-id="38b20-143">詳細証明書の取得については、SQL Server データベースを作成して、ファイル ストアを作成する[ビジネス サーバー 2015 の Skype の導入](../../deploy/deploy.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="38b20-143">For details about acquiring certificates, creating the SQL Server database, and creating file stores, see [Deploy Skype for Business Server 2015](../../deploy/deploy.md).</span></span> 
  
## <a name="for-more-information"></a><span data-ttu-id="38b20-144">関連情報</span><span class="sxs-lookup"><span data-stu-id="38b20-144">For more information</span></span>

<span data-ttu-id="38b20-145">ハードウェアおよびソフトウェアの要件の詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="38b20-145">For more information about hardware and software requirements, see the following topics:</span></span>
  
- [<span data-ttu-id="38b20-146">ビジネス サーバー 2015 の Skype のサーバーの要件</span><span class="sxs-lookup"><span data-stu-id="38b20-146">Server requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
    
- [<span data-ttu-id="38b20-147">ビジネス サーバー 2015 の Skype の環境の要件</span><span class="sxs-lookup"><span data-stu-id="38b20-147">Environmental requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)
    

