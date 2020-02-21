---
title: Skype for Business Server 2015 の常設チャットサーバーのハードウェアおよびソフトウェア要件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/19/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 692b7d99-1bc9-4c99-a050-2bc2be8688b2
description: '概要: このトピックでは、Skype for Business Server 2015 の常設チャットサーバーのハードウェア要件およびソフトウェア要件について説明します。'
ms.openlocfilehash: 39204b675feff78fef56ee02e1c7e381eb36f65f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213233"
---
# <a name="hardware-and-software-requirements-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="91bed-103">Skype for Business Server 2015 の常設チャットサーバーのハードウェアおよびソフトウェア要件</span><span class="sxs-lookup"><span data-stu-id="91bed-103">Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="91bed-104">**概要:** このトピックでは、Skype for Business Server 2015 の常設チャットサーバーのハードウェアとソフトウェアの要件について説明します。</span><span class="sxs-lookup"><span data-stu-id="91bed-104">**Summary:** Read this topic to learn about hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="91bed-105">常設チャットサーバーは、Skype for Business Server 2015 Enterprise Edition または Standard Edition と共にインストールできます。</span><span class="sxs-lookup"><span data-stu-id="91bed-105">Persistent Chat Server can be installed with Skype for Business Server 2015 Enterprise Edition or Standard Edition.</span></span> <span data-ttu-id="91bed-106">要件は、インストールされている Skype for Business Server 2015 のエディションと、ビジネスのパフォーマンス要件によって異なります。</span><span class="sxs-lookup"><span data-stu-id="91bed-106">Requirements depend on which edition of Skype for Business Server 2015 you have installed, and the performance requirements of your business.</span></span> <span data-ttu-id="91bed-107">Enterprise Edition では、最大8万の同時ユーザーをサポートできます。Standard Edition は、最大2万の同時ユーザーをサポートできます。</span><span class="sxs-lookup"><span data-stu-id="91bed-107">Enterprise Edition can support up to 80,000 concurrent users; Standard Edition can support up to 20,000 concurrent users.</span></span> <span data-ttu-id="91bed-108">常設チャットは、フロントエンドコンポーネントおよびバックエンド SQL データベースコンポーネントで構成されます。</span><span class="sxs-lookup"><span data-stu-id="91bed-108">Persistent Chat consists of a front-end component as well as a back-end SQL database component.</span></span>
  
<span data-ttu-id="91bed-109">常設チャットサーバーを展開する前に、次のハードウェアとソフトウェアの要件を満たしていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="91bed-109">Before you deploy Persistent Chat Server, you must ensure that the following hardware and software requirements are met:</span></span>
  
- <span data-ttu-id="91bed-110">Skype for Business Server 2015、常設チャットサーバー、データベースサーバー、およびファイルサーバーをサポートするための最小要件を満たすハードウェア。</span><span class="sxs-lookup"><span data-stu-id="91bed-110">Hardware that meets minimum requirements to support Skype for Business Server 2015, Persistent Chat Server, database servers, and file servers.</span></span> <span data-ttu-id="91bed-111">詳細については、「 [Skype For Business server 2015 のサーバー要件](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="91bed-111">For more information, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span></span>
    
- <span data-ttu-id="91bed-112">サポートされているオペレーティングシステムとデータベースソフトウェア。</span><span class="sxs-lookup"><span data-stu-id="91bed-112">Supported operating system and database software.</span></span>
    
    <span data-ttu-id="91bed-113">サポートされているオペレーティングシステムとデータベースソフトウェア、および Windows 更新の要件の詳細については、「 [Skype For Business server 2015 のサーバー要件](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="91bed-113">For details about supported operating systems and database software, and Windows update requirements, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span></span>
    
- <span data-ttu-id="91bed-114">Skype for Business Server 2015 フロントエンドサーバー。</span><span class="sxs-lookup"><span data-stu-id="91bed-114">Skype for Business Server 2015 Front End Server.</span></span> <span data-ttu-id="91bed-115">フロントエンドサーバーは、セッション開始プロトコル (SIP) ルーティングの基盤であり、常設チャットサーバーと常設チャット機能を実行しているコンピューター間の通信を可能にします。</span><span class="sxs-lookup"><span data-stu-id="91bed-115">The Front End Server is the foundation for Session Initiation Protocol (SIP) routing, which makes communication between computers running Persistent Chat Server and the Persistent Chat functionality possible.</span></span> 
    
- <span data-ttu-id="91bed-116">メッセージキューソフトウェア。</span><span class="sxs-lookup"><span data-stu-id="91bed-116">Message Queuing software.</span></span> <span data-ttu-id="91bed-117">常設チャットサーバーおよび常設チャットコンプライアンスサービス (展開されている場合) によって使用されます。</span><span class="sxs-lookup"><span data-stu-id="91bed-117">Used by the Persistent Chat Server and Persistent Chat Compliance service, if deployed.</span></span>
    
<span data-ttu-id="91bed-118">次のセクションでは、常設チャットサーバーおよび常設チャットデータを格納するデータベースの特定の要件について説明します。</span><span class="sxs-lookup"><span data-stu-id="91bed-118">The following sections describe the specific requirements for Persistent Chat Server and the database that stores the Persistent Chat data.</span></span>

> [!NOTE] 
> <span data-ttu-id="91bed-119">常設チャットは Skype for business Server 2015 で利用可能ですが、Skype for Business Server 2019 ではサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="91bed-119">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="91bed-120">Teams でも同じ機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="91bed-120">The same functionality is available in Teams.</span></span> <span data-ttu-id="91bed-121">詳細については、「 [Microsoft Teams のアップグレードの概要](/microsoftteams/upgrade-start-here)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="91bed-121">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="91bed-122">常設チャットを使用する必要がある場合は、この機能を必要とするユーザーを Teams に移行するか、Skype for Business Server 2015 を引き続き使用するかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="91bed-122">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 
  
## <a name="front-end-server-requirements"></a><span data-ttu-id="91bed-123">フロントエンドサーバーの要件</span><span class="sxs-lookup"><span data-stu-id="91bed-123">Front End Server requirements</span></span>

<span data-ttu-id="91bed-124">フロントエンドサーバーの要件は、常設チャットサーバーを Skype for Business Server 2015 Enterprise Edition または Standard Edition と共に展開するかどうかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="91bed-124">Front End Server requirements depend on whether you are deploying Persistent Chat Server with Skype for Business Server 2015 Enterprise Edition or Standard Edition.</span></span>
  
- <span data-ttu-id="91bed-125">Skype for Business Server 2015 Enterprise Edition と共に常設チャットサーバーを展開している場合は、Enterprise Edition プール内の1つ以上のスタンドアロンコンピューターに常設チャットサーバーのフロントエンドサーバーを展開することができます。</span><span class="sxs-lookup"><span data-stu-id="91bed-125">If you are deploying Persistent Chat Server with Skype for Business Server 2015 Enterprise Edition, you can deploy the Persistent Chat Server Front End Server on one or more standalone computers in the Enterprise Edition pool.</span></span> <span data-ttu-id="91bed-126">常設チャットフロントエンドサーバーを Skype for Business Server 2015 フロントエンドサーバー上に併置することはできません。</span><span class="sxs-lookup"><span data-stu-id="91bed-126">You cannot collocate the Persistent Chat Front End Servers on the Skype for Business Server 2015 Front End Server.</span></span> 
    
    <span data-ttu-id="91bed-127">1台の常設チャットサーバーフロントエンドサーバーでは、2万アクティブユーザーをサポートできます。</span><span class="sxs-lookup"><span data-stu-id="91bed-127">A single Persistent Chat Server Front End Server can support 20,000 active users.</span></span> <span data-ttu-id="91bed-128">最大4つのアクティブなフロントエンドを持つ常設チャットサーバープールを使用して、合計8万の同時ユーザーをサポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="91bed-128">You can have a Persistent Chat Server pool with up to 4 active front ends thereby supporting a total of 80,000 concurrent users.</span></span> 
    
- <span data-ttu-id="91bed-129">Skype for Business Server 2015 Standard Edition で常設チャットサーバーを展開している場合は、常設チャットをフロントエンドサーバーと併置することができます。</span><span class="sxs-lookup"><span data-stu-id="91bed-129">If you are deploying Persistent Chat Server with Skype for Business Server 2015 Standard Edition, you can collocate Persistent Chat with the Front End Server.</span></span> <span data-ttu-id="91bed-130">この単一サーバーの展開では、最大2万ユーザーをサポートできます。</span><span class="sxs-lookup"><span data-stu-id="91bed-130">This single server deployment can support up to 20,000 users.</span></span> 
    
## <a name="persistent-chat-server-database-requirements"></a><span data-ttu-id="91bed-131">常設チャットサーバーのデータベースの要件</span><span class="sxs-lookup"><span data-stu-id="91bed-131">Persistent Chat Server database requirements</span></span>

<span data-ttu-id="91bed-132">常設チャットサーバーには、チャットルームの履歴とコンテンツ、構成データ、ユーザープロビジョニングデータ、およびその他の関連メタデータを格納するための SQL Server データベースソフトウェアが必要です。</span><span class="sxs-lookup"><span data-stu-id="91bed-132">Persistent Chat Server requires SQL Server database software to store chat room history and content, configuration data, user provisioning data, and other relevant metadata.</span></span> <span data-ttu-id="91bed-133">必要に応じて、常設チャットコンプライアンスデータベースを使用してコンプライアンスデータを保存します。</span><span class="sxs-lookup"><span data-stu-id="91bed-133">Optionally, it uses the Persistent Chat Compliance database to store compliance data.</span></span> <span data-ttu-id="91bed-134">常設チャットデータベースは、バックエンドデータベースと同じ SQL Server、または同じ SQL インスタンスに併置できます。</span><span class="sxs-lookup"><span data-stu-id="91bed-134">Persistent Chat databases can be collocated on the same SQL Server, or even the same SQL instance, as the back-end databases.</span></span> 
  
- <span data-ttu-id="91bed-135">Skype for Business Server 2015 Enterprise Edition と共に常設チャットサーバーをインストールする場合は、最適なパフォーマンスを確保するために、常設チャットのファイルストアをインストールすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="91bed-135">If you are installing Persistent Chat Server with Skype for Business Server 2015 Enterprise Edition, to ensure optimum performance, it is recommended that you install the Persistent Chat file store.</span></span>
    
- <span data-ttu-id="91bed-136">Skype for Business Server 2015 Standard edition で常設チャットサーバーをインストールする場合は、ローカルの SQL Server Express インスタンスに常設チャットストアバックエンドサーバーを展開することができます。</span><span class="sxs-lookup"><span data-stu-id="91bed-136">If you are installing Persistent Chat Server with Skype for Business Server 2015 Standard edition, you can deploy the Persistent Chat Store Back End Server on the local SQL Server Express instance.</span></span>
    
- <span data-ttu-id="91bed-137">常設チャットデータベース (mgc) とコンプライアンスデータベース (メンバーサーバー) は、SQL Server の同じインスタンスまたは別の SQL Server に配置できます。</span><span class="sxs-lookup"><span data-stu-id="91bed-137">The Persistent Chat database (mgc) and the compliance database (mgccomp) can be located in the same instance of SQL Server or on different SQL Servers.</span></span>
    
<span data-ttu-id="91bed-138">データベースサーバープラットフォームを準備するには、各コンピューターがハードウェア要件を満たしていることを確認してから、前提条件となるソフトウェアをインストールします。</span><span class="sxs-lookup"><span data-stu-id="91bed-138">To prepare a database server platform, be sure that each computer meets the hardware requirements, and then install the prerequisite software.</span></span> <span data-ttu-id="91bed-139">常設チャットデータベースサーバーのサーバープラットフォームには、Skype for Business Server 2015 バックエンドデータベースサーバーと同じハードウェアが必要です。</span><span class="sxs-lookup"><span data-stu-id="91bed-139">The server platform for the Persistent Chat database servers requires the same hardware as the Skype for Business Server 2015 back-end database server.</span></span> <span data-ttu-id="91bed-140">詳細については、「 [Skype For Business server 2015 のサーバー要件](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="91bed-140">For details, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span></span>
  
<span data-ttu-id="91bed-141">データベースサーバーで、次のいずれかのソフトウェアアプリケーションがインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="91bed-141">On the database server, be sure that one of the following software applications is installed:</span></span>

- <span data-ttu-id="91bed-142">Microsoft SQL Server 2017 と最新のサービスパック。</span><span class="sxs-lookup"><span data-stu-id="91bed-142">Microsoft SQL Server 2017 with the latest service pack.</span></span>

- <span data-ttu-id="91bed-143">Microsoft SQL Server 2016 Service Pack 1。これは、Skype for Business Server の累積的な更新プログラム7以降のリリースで実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="91bed-143">Microsoft SQL Server 2016 with Service Pack 1, and you must run with Skype for Business Server Cumulative Update 7 or later releases.</span></span> <span data-ttu-id="91bed-144">SQL Server 2016 を最新のサービスパックと共に実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="91bed-144">We recommended running SQL Server 2016 with the latest service pack.</span></span> <span data-ttu-id="91bed-145">Microsoft SQL Server 2016 をインストールする方法の詳細については、「 [INSTALL SQL server 2016](https://docs.microsoft.com/sql/database-engine/install-windows/install-sql-server?view=sql-server-2016)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="91bed-145">For details about how to install Microsoft SQL Server 2016, see [Install SQL Server 2016](https://docs.microsoft.com/sql/database-engine/install-windows/install-sql-server?view=sql-server-2016).</span></span>

- <span data-ttu-id="91bed-146">Microsoft SQL Server 2014 で、Skype for Business Server の累積的な更新プログラム6以降のリリースを使用して実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="91bed-146">Microsoft SQL Server 2014, and you must run with Skype for Business Server Cumulative Update 6 or later releases.</span></span> <span data-ttu-id="91bed-147">SQL Server 2014 を最新のサービスパックと共に実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="91bed-147">We recommended running SQL Server 2014 with the latest service pack.</span></span> <span data-ttu-id="91bed-148">Microsoft SQL Server 2014 をインストールする方法の詳細については、「 [INSTALL SQL server 2014](https://docs.microsoft.com/sql/database-engine/install-windows/install-sql-server?view=sql-server-2014)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="91bed-148">For details about how to install Microsoft SQL Server 2014, see [Install SQL Server 2014](https://docs.microsoft.com/sql/database-engine/install-windows/install-sql-server?view=sql-server-2014).</span></span>

- <span data-ttu-id="91bed-149">Microsoft SQL Server 2012 (64 ビット版)。最新のサービスパックを使用して実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="91bed-149">Microsoft SQL Server 2012 (64-bit edition), and we recommended running with the latest service pack.</span></span> <span data-ttu-id="91bed-150">Microsoft SQL Server 2012 をインストールする方法の詳細については、「 [INSTALL SQL server 2012](https://go.microsoft.com/fwlink/p/?LinkID=248559)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="91bed-150">For details about how to install Microsoft SQL Server 2012, see [Install SQL Server 2012](https://go.microsoft.com/fwlink/p/?LinkID=248559).</span></span>

## <a name="persistent-chat-server-certificate-requirements"></a><span data-ttu-id="91bed-151">常設チャットサーバーの証明書の要件</span><span class="sxs-lookup"><span data-stu-id="91bed-151">Persistent Chat Server certificate requirements</span></span>

<span data-ttu-id="91bed-152">証明書の取得、SQL Server データベースの作成、およびファイルストアの作成の詳細については、「 [Deploy Skype For Business Server 2015](../../deploy/deploy.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="91bed-152">For details about acquiring certificates, creating the SQL Server database, and creating file stores, see [Deploy Skype for Business Server 2015](../../deploy/deploy.md).</span></span> 
  
## <a name="for-more-information"></a><span data-ttu-id="91bed-153">関連情報</span><span class="sxs-lookup"><span data-stu-id="91bed-153">For more information</span></span>

<span data-ttu-id="91bed-154">ハードウェアとソフトウェアの要件の詳細については、以下のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="91bed-154">For more information about hardware and software requirements, see the following topics:</span></span>
  
- [<span data-ttu-id="91bed-155">Skype for Business Server 2015 のサーバー要件</span><span class="sxs-lookup"><span data-stu-id="91bed-155">Server requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
    
- [<span data-ttu-id="91bed-156">Skype for Business Server 2015 の環境要件</span><span class="sxs-lookup"><span data-stu-id="91bed-156">Environmental requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)
    

