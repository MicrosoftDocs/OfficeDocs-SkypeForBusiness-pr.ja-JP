---
title: Skype for Business Server 2015 の常設チャット サーバーのハードウェア要件およびソフトウェア要件
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/19/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 692b7d99-1bc9-4c99-a050-2bc2be8688b2
description: '概要: このトピックでは、Skype for Business Server 2015 の常設チャット サーバーのハードウェア要件とソフトウェア要件について説明します。'
ms.openlocfilehash: 32ba0d94679e6f326fa1821cbe3401d031854037
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834537"
---
# <a name="hardware-and-software-requirements-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="513ee-103">Skype for Business Server 2015 の常設チャット サーバーのハードウェア要件およびソフトウェア要件</span><span class="sxs-lookup"><span data-stu-id="513ee-103">Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="513ee-104">**概要:** このトピックでは、Skype for Business Server 2015 の常設チャット サーバーのハードウェア要件とソフトウェア要件について説明します。</span><span class="sxs-lookup"><span data-stu-id="513ee-104">**Summary:** Read this topic to learn about hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="513ee-105">常設チャット サーバーは、Skype for Business Server 2015 Enterprise Edition または Standard Edition と一緒にインストールできます。</span><span class="sxs-lookup"><span data-stu-id="513ee-105">Persistent Chat Server can be installed with Skype for Business Server 2015 Enterprise Edition or Standard Edition.</span></span> <span data-ttu-id="513ee-106">要件は、インストールした Skype for Business Server 2015 のエディションと、ビジネスのパフォーマンス要件によって異なっています。</span><span class="sxs-lookup"><span data-stu-id="513ee-106">Requirements depend on which edition of Skype for Business Server 2015 you have installed, and the performance requirements of your business.</span></span> <span data-ttu-id="513ee-107">Enterprise Edition は最大 80,000 人の同時ユーザーをサポートできます。Standard Edition では、最大 20,000 人の同時ユーザーをサポートできます。</span><span class="sxs-lookup"><span data-stu-id="513ee-107">Enterprise Edition can support up to 80,000 concurrent users; Standard Edition can support up to 20,000 concurrent users.</span></span> <span data-ttu-id="513ee-108">常設チャットは、フロントエンド コンポーネントと、データベース コンポーネントのSQL構成されます。</span><span class="sxs-lookup"><span data-stu-id="513ee-108">Persistent Chat consists of a front-end component as well as a back-end SQL database component.</span></span>
  
<span data-ttu-id="513ee-109">常設チャット サーバーを展開する前に、次のハードウェア要件とソフトウェア要件を満たしていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="513ee-109">Before you deploy Persistent Chat Server, you must ensure that the following hardware and software requirements are met:</span></span>
  
- <span data-ttu-id="513ee-110">Skype for Business Server 2015、常設チャット サーバー、データベース サーバー、およびファイル サーバーをサポートする最小要件を満たすハードウェア。</span><span class="sxs-lookup"><span data-stu-id="513ee-110">Hardware that meets minimum requirements to support Skype for Business Server 2015, Persistent Chat Server, database servers, and file servers.</span></span> <span data-ttu-id="513ee-111">詳細については [、「Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)のサーバー要件」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="513ee-111">For more information, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span></span>
    
- <span data-ttu-id="513ee-112">サポートされているオペレーティング システムとデータベース ソフトウェア。</span><span class="sxs-lookup"><span data-stu-id="513ee-112">Supported operating system and database software.</span></span>
    
    <span data-ttu-id="513ee-113">サポートされているオペレーティング システムとデータベース ソフトウェア、および Windows 更新プログラムの要件の詳細については [、Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)のサーバー要件を参照してください。</span><span class="sxs-lookup"><span data-stu-id="513ee-113">For details about supported operating systems and database software, and Windows update requirements, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span></span>
    
- <span data-ttu-id="513ee-114">Skype for Business Server 2015 フロントエンド サーバー。</span><span class="sxs-lookup"><span data-stu-id="513ee-114">Skype for Business Server 2015 Front End Server.</span></span> <span data-ttu-id="513ee-115">フロントエンド サーバーは、セッション開始プロトコル (SIP) ルーティングの基盤であり、常設チャット サーバーを実行しているコンピューターと常設チャット機能間の通信を可能にします。</span><span class="sxs-lookup"><span data-stu-id="513ee-115">The Front End Server is the foundation for Session Initiation Protocol (SIP) routing, which makes communication between computers running Persistent Chat Server and the Persistent Chat functionality possible.</span></span> 
    
- <span data-ttu-id="513ee-116">メッセージ キュー ソフトウェア。</span><span class="sxs-lookup"><span data-stu-id="513ee-116">Message Queuing software.</span></span> <span data-ttu-id="513ee-117">常設チャット サーバーおよび常設チャット コンプライアンス サービスによって使用されます (展開されている場合)。</span><span class="sxs-lookup"><span data-stu-id="513ee-117">Used by the Persistent Chat Server and Persistent Chat Compliance service, if deployed.</span></span>
    
<span data-ttu-id="513ee-118">以下のセクションでは、常設チャット サーバーおよび常設チャット データを格納するデータベースの特定の要件について説明します。</span><span class="sxs-lookup"><span data-stu-id="513ee-118">The following sections describe the specific requirements for Persistent Chat Server and the database that stores the Persistent Chat data.</span></span>

> [!NOTE] 
> <span data-ttu-id="513ee-119">常設チャットは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="513ee-119">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="513ee-120">Teams でも同じ機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="513ee-120">The same functionality is available in Teams.</span></span> <span data-ttu-id="513ee-121">詳細については、「Microsoft Teams のアップグレード [の開始」を参照してください](/microsoftteams/upgrade-start-here)。</span><span class="sxs-lookup"><span data-stu-id="513ee-121">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="513ee-122">常設チャットを使用する必要がある場合は、この機能を必要とするユーザーを Teams に移行するか、Skype for Business Server 2015 を引き続き使用するかのどちらかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="513ee-122">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 
  
## <a name="front-end-server-requirements"></a><span data-ttu-id="513ee-123">フロントエンド サーバーの要件</span><span class="sxs-lookup"><span data-stu-id="513ee-123">Front End Server requirements</span></span>

<span data-ttu-id="513ee-124">フロントエンド サーバーの要件は、Skype for Business Server 2015 Enterprise Edition と Standard Edition の組み合わされた常設チャット サーバーを展開するかどうかによって異なっています。</span><span class="sxs-lookup"><span data-stu-id="513ee-124">Front End Server requirements depend on whether you are deploying Persistent Chat Server with Skype for Business Server 2015 Enterprise Edition or Standard Edition.</span></span>
  
- <span data-ttu-id="513ee-125">Skype for Business Server 2015 Enterprise Edition を使用して常設チャット サーバーを展開する場合は、Enterprise Edition プール内の 1 つ以上のスタンドアロン コンピューターに常設チャット サーバー フロントエンド サーバーを展開できます。</span><span class="sxs-lookup"><span data-stu-id="513ee-125">If you are deploying Persistent Chat Server with Skype for Business Server 2015 Enterprise Edition, you can deploy the Persistent Chat Server Front End Server on one or more standalone computers in the Enterprise Edition pool.</span></span> <span data-ttu-id="513ee-126">常設チャット フロントエンド サーバーを Skype for Business Server 2015 フロント エンド サーバーに共に使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="513ee-126">You cannot collocate the Persistent Chat Front End Servers on the Skype for Business Server 2015 Front End Server.</span></span> 
    
    <span data-ttu-id="513ee-127">1 つの常設チャット サーバー フロントエンド サーバーで、20,000 人のアクティブ ユーザーをサポートできます。</span><span class="sxs-lookup"><span data-stu-id="513ee-127">A single Persistent Chat Server Front End Server can support 20,000 active users.</span></span> <span data-ttu-id="513ee-128">最大 4 つのアクティブなフロントエンドを持つ常設チャット サーバー プールを使用して、合計 80,000 人の同時ユーザーをサポートできます。</span><span class="sxs-lookup"><span data-stu-id="513ee-128">You can have a Persistent Chat Server pool with up to 4 active front ends thereby supporting a total of 80,000 concurrent users.</span></span> 
    
- <span data-ttu-id="513ee-129">Skype for Business Server 2015 Standard Edition と共に常設チャット サーバーを展開する場合は、常設チャットをフロント エンド サーバーと共に使用できます。</span><span class="sxs-lookup"><span data-stu-id="513ee-129">If you are deploying Persistent Chat Server with Skype for Business Server 2015 Standard Edition, you can collocate Persistent Chat with the Front End Server.</span></span> <span data-ttu-id="513ee-130">この単一サーバー展開では、最大 20,000 ユーザーをサポートできます。</span><span class="sxs-lookup"><span data-stu-id="513ee-130">This single server deployment can support up to 20,000 users.</span></span> 
    
## <a name="persistent-chat-server-database-requirements"></a><span data-ttu-id="513ee-131">常設チャット サーバー データベースの要件</span><span class="sxs-lookup"><span data-stu-id="513ee-131">Persistent Chat Server database requirements</span></span>

<span data-ttu-id="513ee-132">常設チャット サーバーでは、SQL Server履歴とコンテンツ、構成データ、ユーザー プロビジョニング データ、その他の関連するメタデータを格納するために、データベース ソフトウェアを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="513ee-132">Persistent Chat Server requires SQL Server database software to store chat room history and content, configuration data, user provisioning data, and other relevant metadata.</span></span> <span data-ttu-id="513ee-133">必要に応じて、常設チャット コンプライアンス データベースを使用してコンプライアンス データを格納します。</span><span class="sxs-lookup"><span data-stu-id="513ee-133">Optionally, it uses the Persistent Chat Compliance database to store compliance data.</span></span> <span data-ttu-id="513ee-134">常設チャット データベースは、バック エンド データベースと同じSQL Server、または同じ SQL インスタンスに同時に展開できます。</span><span class="sxs-lookup"><span data-stu-id="513ee-134">Persistent Chat databases can be collocated on the same SQL Server, or even the same SQL instance, as the back-end databases.</span></span> 
  
- <span data-ttu-id="513ee-135">Skype for Business Server 2015 Enterprise Edition と一緒に常設チャット サーバーをインストールする場合は、最適なパフォーマンスを確保するために、常設チャット ファイル ストアをインストールしてください。</span><span class="sxs-lookup"><span data-stu-id="513ee-135">If you are installing Persistent Chat Server with Skype for Business Server 2015 Enterprise Edition, to ensure optimum performance, it is recommended that you install the Persistent Chat file store.</span></span>
    
- <span data-ttu-id="513ee-136">Skype for Business Server 2015 Standard エディションを使用して常設チャット サーバーをインストールする場合は、ローカルの SQL Server Express インスタンスに常設チャット ストアのバック エンド サーバーを展開できます。</span><span class="sxs-lookup"><span data-stu-id="513ee-136">If you are installing Persistent Chat Server with Skype for Business Server 2015 Standard edition, you can deploy the Persistent Chat Store Back End Server on the local SQL Server Express instance.</span></span>
    
- <span data-ttu-id="513ee-137">常設チャット データベース (mgc) とコンプライアンス データベース (mgccomp) は、SQL Server の同じインスタンス、または別の SQL サーバーに保存できます。</span><span class="sxs-lookup"><span data-stu-id="513ee-137">The Persistent Chat database (mgc) and the compliance database (mgccomp) can be located in the same instance of SQL Server or on different SQL Servers.</span></span>
    
<span data-ttu-id="513ee-138">データベース サーバー プラットフォームを準備するには、各コンピューターがハードウェア要件を満たしていることを確認してから、必要なソフトウェアをインストールします。</span><span class="sxs-lookup"><span data-stu-id="513ee-138">To prepare a database server platform, be sure that each computer meets the hardware requirements, and then install the prerequisite software.</span></span> <span data-ttu-id="513ee-139">常設チャット データベース サーバーのサーバー プラットフォームには、Skype for Business Server 2015 のバック エンド データベース サーバーと同じハードウェアが必要です。</span><span class="sxs-lookup"><span data-stu-id="513ee-139">The server platform for the Persistent Chat database servers requires the same hardware as the Skype for Business Server 2015 back-end database server.</span></span> <span data-ttu-id="513ee-140">詳細については [、Skype for Business Server 2015 のサーバー要件を参照](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)してください。</span><span class="sxs-lookup"><span data-stu-id="513ee-140">For details, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span></span>
  
<span data-ttu-id="513ee-141">データベース サーバーで、次のいずれかのソフトウェア アプリケーションがインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="513ee-141">On the database server, be sure that one of the following software applications is installed:</span></span>

- <span data-ttu-id="513ee-142">Microsoft SQL Server 2017 と最新のサービス パック。</span><span class="sxs-lookup"><span data-stu-id="513ee-142">Microsoft SQL Server 2017 with the latest service pack.</span></span>

- <span data-ttu-id="513ee-143">Microsoft SQL Server 2016 Service Pack 1 を使用し、Skype for Business Server の累積的な更新プログラム 7 以降のリリースで実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="513ee-143">Microsoft SQL Server 2016 with Service Pack 1, and you must run with Skype for Business Server Cumulative Update 7 or later releases.</span></span> <span data-ttu-id="513ee-144">最新のサービス パックSQL Server 2016 年 1 月の実行をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="513ee-144">We recommended running SQL Server 2016 with the latest service pack.</span></span> <span data-ttu-id="513ee-145">Microsoft SQL Server 2016 のインストール方法の詳細については、「Install [SQL Server 2016](https://docs.microsoft.com/sql/database-engine/install-windows/install-sql-server?view=sql-server-2016)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="513ee-145">For details about how to install Microsoft SQL Server 2016, see [Install SQL Server 2016](https://docs.microsoft.com/sql/database-engine/install-windows/install-sql-server?view=sql-server-2016).</span></span>

- <span data-ttu-id="513ee-146">Microsoft SQL Server 2014 では、Skype for Business Server の累積的な更新プログラム 6 以降のリリースで実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="513ee-146">Microsoft SQL Server 2014, and you must run with Skype for Business Server Cumulative Update 6 or later releases.</span></span> <span data-ttu-id="513ee-147">最新のサービス パックSQL Server 2014 を実行してください。</span><span class="sxs-lookup"><span data-stu-id="513ee-147">We recommended running SQL Server 2014 with the latest service pack.</span></span> <span data-ttu-id="513ee-148">Microsoft SQL Server 2014 のインストール方法の詳細については、「Install [SQL Server 2014](https://docs.microsoft.com/sql/database-engine/install-windows/install-sql-server?view=sql-server-2014)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="513ee-148">For details about how to install Microsoft SQL Server 2014, see [Install SQL Server 2014](https://docs.microsoft.com/sql/database-engine/install-windows/install-sql-server?view=sql-server-2014).</span></span>

- <span data-ttu-id="513ee-149">Microsoft SQL Server 2012 (64 ビット版)、最新のサービス パックの実行をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="513ee-149">Microsoft SQL Server 2012 (64-bit edition), and we recommended running with the latest service pack.</span></span> <span data-ttu-id="513ee-150">Microsoft SQL Server 2012 のインストール方法の詳細については、「Install [SQL Server 2012](https://go.microsoft.com/fwlink/p/?LinkID=248559)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="513ee-150">For details about how to install Microsoft SQL Server 2012, see [Install SQL Server 2012](https://go.microsoft.com/fwlink/p/?LinkID=248559).</span></span>

## <a name="persistent-chat-server-certificate-requirements"></a><span data-ttu-id="513ee-151">常設チャット サーバー証明書の要件</span><span class="sxs-lookup"><span data-stu-id="513ee-151">Persistent Chat Server certificate requirements</span></span>

<span data-ttu-id="513ee-152">証明書の取得、SQL Server データベースの作成、およびファイル ストアの作成の詳細については [、「Skype for Business Server 2015](../../deploy/deploy.md)の展開」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="513ee-152">For details about acquiring certificates, creating the SQL Server database, and creating file stores, see [Deploy Skype for Business Server 2015](../../deploy/deploy.md).</span></span> 
  
## <a name="for-more-information"></a><span data-ttu-id="513ee-153">詳細情報</span><span class="sxs-lookup"><span data-stu-id="513ee-153">For more information</span></span>

<span data-ttu-id="513ee-154">ハードウェアおよびソフトウェアの要件の詳細については、以下のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="513ee-154">For more information about hardware and software requirements, see the following topics:</span></span>
  
- [<span data-ttu-id="513ee-155">Skype for Business Server 2015 のサーバー要件</span><span class="sxs-lookup"><span data-stu-id="513ee-155">Server requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
    
- [<span data-ttu-id="513ee-156">Skype for Business Server 2015 の環境要件</span><span class="sxs-lookup"><span data-stu-id="513ee-156">Environmental requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)
    

