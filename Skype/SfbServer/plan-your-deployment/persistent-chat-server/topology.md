---
title: 常設チャット サーバー トポロジを計画する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 5/17/2016
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6a0a14a0-baad-44e9-b26e-4d192c0a0e70
description: '概要: このトピックでは、Skype for Business Server 2015 の常設チャット サーバーのコンポーネントとトポロジについて説明します。'
ms.openlocfilehash: 548fc5ebecb0f123172ee4733346c03cf44aba7f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825507"
---
# <a name="plan-persistent-chat-server-topology"></a><span data-ttu-id="39768-103">常設チャット サーバー トポロジを計画する</span><span class="sxs-lookup"><span data-stu-id="39768-103">Plan Persistent Chat Server topology</span></span>
 
<span data-ttu-id="39768-104">**概要:** このトピックでは、Skype for Business Server 2015 の常設チャット サーバーのコンポーネントとトポロジについて説明します。</span><span class="sxs-lookup"><span data-stu-id="39768-104">**Summary:** Read this topic to learn about Persistent Chat Server components and topologies in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="39768-105">常設チャット サーバーは、単一サーバー構成と複数サーバー構成の両方をサポートします。</span><span class="sxs-lookup"><span data-stu-id="39768-105">Persistent Chat Server supports both single-server and multiple-server configurations.</span></span> <span data-ttu-id="39768-106">常設チャット サーバーは、Skype for Business Server 2015 Enterprise Edition または Standard Edition サーバーにインストールできます。</span><span class="sxs-lookup"><span data-stu-id="39768-106">You can install Persistent Chat Server on either a Skype for Business Server 2015 Enterprise Edition or Standard Edition Server.</span></span> 

> [!NOTE] 
> <span data-ttu-id="39768-107">常設チャットは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="39768-107">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="39768-108">Teams でも同じ機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="39768-108">The same functionality is available in Teams.</span></span> <span data-ttu-id="39768-109">詳細については、「Microsoft Teams のアップグレード [の開始」を参照してください](/microsoftteams/upgrade-start-here)。</span><span class="sxs-lookup"><span data-stu-id="39768-109">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="39768-110">常設チャットを使用する必要がある場合は、この機能を必要とするユーザーを Teams に移行するか、Skype for Business Server 2015 を引き続き使用するかのどちらかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="39768-110">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 
  
## <a name="persistent-chat-server-components"></a><span data-ttu-id="39768-111">常設チャット サーバー のコンポーネント</span><span class="sxs-lookup"><span data-stu-id="39768-111">Persistent Chat Server components</span></span>

<span data-ttu-id="39768-112">常設チャット サーバーは、次のコンポーネントで構成されます。</span><span class="sxs-lookup"><span data-stu-id="39768-112">Persistent Chat Server consists of the following components:</span></span>
  
- <span data-ttu-id="39768-113">常設チャット サーバーを実行し、次のサービスを提供する 1 台以上のコンピューター:</span><span class="sxs-lookup"><span data-stu-id="39768-113">One or more computers running Persistent Chat Server and providing the following services:</span></span>
    
  - <span data-ttu-id="39768-114">Persistent Chat Service</span><span class="sxs-lookup"><span data-stu-id="39768-114">Persistent Chat service</span></span>
    
  - <span data-ttu-id="39768-115">コンプライアンスが有効な場合にオンになるコンプライアンス サービス</span><span class="sxs-lookup"><span data-stu-id="39768-115">Compliance service, which is turned on if compliance is enabled</span></span>
    
- <span data-ttu-id="39768-116">チャット ルームのコンテンツ、ルーム、およびカテゴリが格納されている常設チャット コンテンツ データベースをホストする SQL Server のバック エンド データベースを実行する 1 つ以上のサーバー (ミラーリングを使用する場合は複数)。</span><span class="sxs-lookup"><span data-stu-id="39768-116">One or more servers (more than one if mirroring is used) running the SQL Server back-end database for hosting the Persistent Chat content database where chat room content, rooms, and categories are stored.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="39768-117">バック エンド データベースには、作成されたカテゴリと常設チャット ルームに関する情報を含むチャット履歴データが格納されます。</span><span class="sxs-lookup"><span data-stu-id="39768-117">The back-end database stores chat history data, including information about categories and Persistent Chat rooms that are created.</span></span> 
  
- <span data-ttu-id="39768-118">コンプライアンスが有効な場合は、コンプライアンス イベントとコンプライアンスを目的としてチャット コンテンツが格納される常設チャット コンプライアンス データベースをホストするために SQL Server のバック エンド データベースを実行する 1 つ以上のサーバー (ミラーリングを使用する場合は複数)。</span><span class="sxs-lookup"><span data-stu-id="39768-118">If compliance is enabled, one or more servers (more than one if mirroring is used) running the SQL Server back-end database for hosting the Persistent Chat Compliance database, where compliance events and chat content for the purpose of compliance are stored.</span></span>
    
<span data-ttu-id="39768-119">常設チャット サーバーのハードウェア要件およびソフトウェア要件の詳細については [、「Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) and [Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015](hardware-and-software-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39768-119">For details about hardware and software requirements for Persistent Chat Server, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) and [Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015](hardware-and-software-requirements.md).</span></span> 
  
## <a name="persistent-chat-server-topologies"></a><span data-ttu-id="39768-120">常設チャット サーバーのトポロジ</span><span class="sxs-lookup"><span data-stu-id="39768-120">Persistent Chat Server topologies</span></span>

<span data-ttu-id="39768-121">常設チャット サーバーは、単一サーバープールまたは複数サーバー プール、および単一プールまたは複数プール トポロジで展開できます。</span><span class="sxs-lookup"><span data-stu-id="39768-121">You can deploy Persistent Chat Server in single-server or multiple-server pools, and with single-pool or multiple-pool topology.</span></span> <span data-ttu-id="39768-122">常設チャット サーバーは、次のトポロジをサポートします。</span><span class="sxs-lookup"><span data-stu-id="39768-122">Persistent Chat Server supports the following topologies:</span></span>
  
-  <span data-ttu-id="39768-123">フロントエンド サーバーに常設チャット サーバーが一緒に表示された Standard Edition サーバー</span><span class="sxs-lookup"><span data-stu-id="39768-123">Standard Edition Server with Persistent Chat Server collocated on the Front End Server</span></span>
    
-  <span data-ttu-id="39768-124">別のサーバーに常設チャット サーバーがある Standard Edition サーバー</span><span class="sxs-lookup"><span data-stu-id="39768-124">Standard Edition Server with Persistent Chat Server on a separate server</span></span>
    
-  <span data-ttu-id="39768-125">別のサーバーに単一の常設チャット サーバーがある Enterprise Edition サーバー</span><span class="sxs-lookup"><span data-stu-id="39768-125">Enterprise Edition Server with a single Persistent Chat Server on a separate server</span></span>
    
-  <span data-ttu-id="39768-126">別々のサーバーに複数の常設チャット サーバーがある Enterprise Edition サーバー</span><span class="sxs-lookup"><span data-stu-id="39768-126">Enterprise Edition Server with more than one Persistent Chat Server on separate servers</span></span>
    
<span data-ttu-id="39768-127">Standard Edition サーバーに常設チャット サーバーを展開することもできますが、パフォーマンスと規模に影響を及ぼすので、高可用性はオプションではありません。</span><span class="sxs-lookup"><span data-stu-id="39768-127">Although you can deploy Persistent Chat Server on a Standard Edition Server, be aware that performance and scale will be affected, and high availability is not an option.</span></span> <span data-ttu-id="39768-128">したがって、主に概念実証と評価を目的として、常設チャットを Standard Edition サーバーに展開する方法をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="39768-128">Therefore, it is recommended that you deploy Persistent Chat on a Standard Edition Server primarily for proof of concept and evaluation purposes.</span></span> 
  
<span data-ttu-id="39768-129">Skype for Business Server 2015 は、さまざまなコロケーション シナリオをサポートしています。1 台のサーバーで複数のコンポーネントを実行する (小規模な組織の場合)、個々のコンポーネントを異なるサーバーで実行する (スケーラビリティとパフォーマンスを必要とする大規模な組織の場合) ハードウェア コストを柔軟に節約できます。</span><span class="sxs-lookup"><span data-stu-id="39768-129">Skype for Business Server 2015 supports a variety of collocation scenarios, providing you the flexibility to save hardware costs by running multiple components on one server (if you have a small organization), or to run individual components on different servers (if you have a larger organization that needs scalability and performance).</span></span> <span data-ttu-id="39768-130">コンポーネントを共に使用するかどうかを決定する前に、スケーラビリティ要因を考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="39768-130">You should consider scalability factors before deciding whether to collocate components.</span></span> <span data-ttu-id="39768-131">Skype for Business Server 2015 Enterprise Edition サーバーと Standard Edition サーバーでは、同じ機能のシナリオが異なります。</span><span class="sxs-lookup"><span data-stu-id="39768-131">Collocation scenarios differ for Skype for Business Server 2015 Enterprise Edition and Standard Edition servers.</span></span> 
  
<span data-ttu-id="39768-132">以下のセクションでは、トポロジについて詳しく説明します。このトポロジには、バック エンド データベース サーバーのコロケーション シナリオとオプションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="39768-132">The following sections describe the topologies in more detail, including collocation scenarios and options for the back-end database servers.</span></span> <span data-ttu-id="39768-133">すべてのサーバーの役割とデータベースのコロケーションの詳細については [、「Topology Basics for Skype for Business Server 2015」](../../plan-your-deployment/topology-basics/topology-basics.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39768-133">For details about collocation of all server roles and databases, see [Topology Basics for Skype for Business Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md).</span></span>
  
### <a name="standard-edition-server-with-persistent-chat-server-collocated-on-the-front-end-server"></a><span data-ttu-id="39768-134">フロントエンド サーバーに常設チャット サーバーが一緒に表示された Standard Edition サーバー</span><span class="sxs-lookup"><span data-stu-id="39768-134">Standard Edition Server with Persistent Chat Server collocated on the Front End Server</span></span>

<span data-ttu-id="39768-135">Standard Edition では、フロント エンド サーバーに常設チャットを共に使用できます。</span><span class="sxs-lookup"><span data-stu-id="39768-135">With Standard Edition, you can collocate Persistent Chat on the Front End Server.</span></span> <span data-ttu-id="39768-136">これは最も簡単で最も基本的な構成です。</span><span class="sxs-lookup"><span data-stu-id="39768-136">This is the simplest and most basic configuration.</span></span> <span data-ttu-id="39768-137">物理リソース (CPU、メモリ、ディスク領域など) の観点から、既存のフロントエンド サーバーに十分な容量が備わっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="39768-137">You must make sure that the existing Front End Server has enough capacity in terms of physical resources: CPU, memory, disk space, and so on.</span></span>
  
<span data-ttu-id="39768-138">さらに、常設チャット サーバーのバック エンド サーバーと常設チャット コンプライアンス データベース (有効な場合) をローカル SQL Server Express のバック エンド サーバーに共に作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="39768-138">In addition, you can collocate the Persistent Chat Server back-end server and the Persistent Chat Compliance database (if enabled) on the local SQL Server Express back-end server.</span></span> <span data-ttu-id="39768-139">また、専用インスタンスで個別のSQL Serverを使用する方法を選択できます。</span><span class="sxs-lookup"><span data-stu-id="39768-139">You can also choose to use a separate SQL Server with a dedicated instance.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="39768-140">最初の常設チャット サーバーが Standard Edition フロントエンド サーバーと一緒に展開されている場合、常設チャット サーバー プールにサーバーを追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="39768-140">You cannot add additional servers to a Persistent Chat Server pool if the first Persistent Chat Server is collocated with a Standard Edition Front End Server.</span></span> <span data-ttu-id="39768-141">必要に応じて、後でサーバーを追加できるよう、最初のサーバーをスタンドアロン インスタンスとしてインストールしてください。</span><span class="sxs-lookup"><span data-stu-id="39768-141">It is recommended that you install the first server as a standalone instance so that you can add more servers later, if needed.</span></span> 
  
### <a name="standard-edition-server-with-persistent-chat-server-installed-on-a-separate-server"></a><span data-ttu-id="39768-142">Standard Edition サーバーと常設チャット サーバーが別のサーバーにインストールされている</span><span class="sxs-lookup"><span data-stu-id="39768-142">Standard Edition Server with Persistent Chat Server installed on a separate server</span></span>

<span data-ttu-id="39768-143">Standard Edition では、常設チャット サーバーをスタンドアロン インスタンスとしてインストールし、必要に応じて後でサーバーを追加できます。</span><span class="sxs-lookup"><span data-stu-id="39768-143">With Standard Edition, you can install Persistent Chat Server as a standalone instance and add more servers later if needed.</span></span> 
  
<span data-ttu-id="39768-144">常設チャット サーバーのバック エンド サーバーと常設チャット コンプライアンス データベース (有効な場合) をローカル SQL Server Express のバック エンド サーバーに共に作成できます。</span><span class="sxs-lookup"><span data-stu-id="39768-144">You can collocate the Persistent Chat Server back-end server and the Persistent Chat Compliance database (if enabled) on the local SQL Server Express back-end server.</span></span> <span data-ttu-id="39768-145">また、専用インスタンスで個別のSQL Serverを使用する方法を選択できます。</span><span class="sxs-lookup"><span data-stu-id="39768-145">You can also choose to use a separate SQL Server with a dedicated instance.</span></span> 
  
### <a name="enterprise-edition-server-with-a-single-persistent-chat-server"></a><span data-ttu-id="39768-146">単一の常設チャット サーバーを使用する Enterprise Edition サーバー</span><span class="sxs-lookup"><span data-stu-id="39768-146">Enterprise Edition Server with a single Persistent Chat Server</span></span>

<span data-ttu-id="39768-147">Enterprise Edition では、常設チャット サーバーを別のコンピューターにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="39768-147">With Enterprise Edition, you must install the Persistent Chat Server on a separate computer.</span></span> <span data-ttu-id="39768-148">つまり、常設チャット サーバーを Enterprise Edition フロントエンド サーバーに共に作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="39768-148">That is, you cannot collocate the Persistent Chat Server on the Enterprise Edition Front End Server.</span></span> <span data-ttu-id="39768-149">この展開には、常設チャット サーバーとコンプライアンス サービスを実行する別のサーバー (有効な場合) が必要です。</span><span class="sxs-lookup"><span data-stu-id="39768-149">This deployment requires a separate server that runs Persistent Chat Server and the Compliance service (if enabled).</span></span>
  
<span data-ttu-id="39768-150">ただし、常設チャット サーバーの SQL Server データベースは、Enterprise Edition フロントエンド プールのバック エンド データベースに同一にできます。</span><span class="sxs-lookup"><span data-stu-id="39768-150">You can, however, collocate the SQL Server database for Persistent Chat Server on the back-end database of an Enterprise Edition Front End pool.</span></span>
  
> [!NOTE]
> <span data-ttu-id="39768-151">HA DR の AlwaysOn 可用性SQL使用する予定の場合は、常設チャット サーバー データベースではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="39768-151">If you plan to use SQL AlwaysOn Availability Groups for HA DR, note that it is not supported for Persistent Chat Server databases.</span></span> 
  
<span data-ttu-id="39768-152">常設チャット データベースをバック エンド データベースと共に使用する場合は、一部またはすべてのデータベースに対して SQL Server の 1 つのインスタンスを使用するか、データベースごとに SQL Server の個別のインスタンスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="39768-152">If you collocate the Persistent Chat database with the back-end database, you can either use a single instance of SQL Server for any or all of the databases, or you can use a separate instance of SQL Server for each database.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="39768-153">常設チャット データベースをホストするサーバーは、他のデータベースをホストできます。</span><span class="sxs-lookup"><span data-stu-id="39768-153">The server hosting the Persistent Chat database can host other databases.</span></span> <span data-ttu-id="39768-154">ただし、常設チャット データベースを他のデータベースと共に使用する場合は、数名を超えるユーザーのメッセージを保存する場合、常設チャット データベースに必要なディスク領域が非常に大きくなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="39768-154">However, when you consider collocating the Persistent Chat database with other databases, be aware that if you are storing the messages of more than a few users, the disk space needed by the Persistent Chat database can grow very large.</span></span> <span data-ttu-id="39768-155">このため、常設チャット データベースをバック エンド データベースと共に使用はお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="39768-155">For this reason, we do not recommend collocating the Persistent Chat database with the back-end database.</span></span> 
  
<span data-ttu-id="39768-156">次の図は、コンプライアンスが有効になっている単一の常設チャット サーバーのトポロジのすべてのコンポーネントを示しています (オプション)。</span><span class="sxs-lookup"><span data-stu-id="39768-156">The following figure shows all components of a topology for a single Persistent Chat Server with compliance enabled (optional).</span></span>
  
<span data-ttu-id="39768-157">**単一サーバー トポロジ**</span><span class="sxs-lookup"><span data-stu-id="39768-157">**Single Server Topology**</span></span>

![常設チャット サーバー - 単一サーバー トポロジ](../../media/e1b39c28-8a4d-4c03-983b-4392889c2d14.png)
  
### <a name="enterprise-edition-server-with-multiple-persistent-chat-servers"></a><span data-ttu-id="39768-159">複数の常設チャット サーバーを含む Enterprise Edition サーバー</span><span class="sxs-lookup"><span data-stu-id="39768-159">Enterprise Edition Server with multiple Persistent Chat Servers</span></span>

<span data-ttu-id="39768-160">Enterprise Edition では、容量と信頼性を向上するために複数サーバー トポロジを展開できます。</span><span class="sxs-lookup"><span data-stu-id="39768-160">With Enterprise Edition, you can deploy a multiple-server topology for greater capacity and reliability.</span></span> <span data-ttu-id="39768-161">複数サーバー トポロジは、複数のサーバーが常設チャット サーバーをホストする場合を除き、単一サーバー トポロジと同じであり、より高く拡張できます。</span><span class="sxs-lookup"><span data-stu-id="39768-161">A multiple-server topology is the same as the single-server topology except that multiple servers host Persistent Chat Server, and can scale higher.</span></span> <span data-ttu-id="39768-162">複数サーバー トポロジには、常設チャット サーバーを実行しているアクティブなコンピューターを最大 4 台まで含めできます (高可用性および障害復旧構成では最大 8 台まで使用できますが、アクティブにできるのは 4 台で、残りの 4 台はスタンバイ状態にできます)。</span><span class="sxs-lookup"><span data-stu-id="39768-162">The multiple-server topology can include as many as four active computers running Persistent Chat Server (high availability and disaster recovery configurations will allow up to eight, but only four can be active and the remaining four on standby).</span></span> <span data-ttu-id="39768-163">各サーバーは最大 20,000 人の同時ユーザーをサポートできます。合計 80,000 人の同時ユーザーが 4 台のサーバーを持つ常設チャット サーバー プールに接続しています。</span><span class="sxs-lookup"><span data-stu-id="39768-163">Each server can support as many as 20,000 concurrent users, for a total of 80,000 concurrent users connected to a Persistent Chat Server pool with 4 servers.</span></span> <span data-ttu-id="39768-164">常設チャット サーバーを実行している複数のコンピューターは、Skype for Business Server およびコンプライアンス サービスと同じ Active Directory ドメイン サービス ドメインに存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="39768-164">Multiple computers running Persistent Chat Server should reside in the same Active Directory Domain Services domain as Skype for Business Server and the Compliance service.</span></span>
  
<span data-ttu-id="39768-165">次の図は、常設チャット サーバー、オプションのコンプライアンス サービス、および個別のコンプライアンス データベースを実行する複数のコンピューターを使用する複数サーバー トポロジのすべてのコンポーネントを示しています。</span><span class="sxs-lookup"><span data-stu-id="39768-165">The following figure shows all the components of a multiple-server topology with multiple computers running Persistent Chat Server, the optional Compliance service, and a separate compliance database.</span></span>
  
<span data-ttu-id="39768-166">**複数サーバー トポロジ**</span><span class="sxs-lookup"><span data-stu-id="39768-166">**Multiple Server Topology**</span></span>

![常設チャット サーバー - 複数サーバー トポロジ](../../media/8fc20997-7acc-46ea-8dea-11239ffd9458.png)
  
<span data-ttu-id="39768-168">複数サーバー トポロジでは、サーバー機能をプールできます。</span><span class="sxs-lookup"><span data-stu-id="39768-168">Multiple-server topologies provide pooling of server functionality.</span></span> <span data-ttu-id="39768-169">サーバー プールでは、常設チャット サービスはデータの通信と共有を行います。</span><span class="sxs-lookup"><span data-stu-id="39768-169">In a server pool, the Persistent Chat services communicate and share data.</span></span> <span data-ttu-id="39768-170">たとえば、最初に 1 つの常設チャット サービスに投稿されたチャット履歴は、システム内の任意の常設チャット サービスから使用できます。</span><span class="sxs-lookup"><span data-stu-id="39768-170">For example, chat history that was originally posted to one Persistent Chat service is available from any Persistent Chat service in the system.</span></span> <span data-ttu-id="39768-171">1 つの常設チャット サービスを介してアップロードされたファイルには、任意の常設チャット サービスからアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="39768-171">A file that is uploaded through one Persistent Chat service can be accessed by any Persistent Chat service.</span></span> <span data-ttu-id="39768-172">ユーザーは、異なる常設チャット サーバー フロントエンド サーバーに接続して、互いに通信できます。</span><span class="sxs-lookup"><span data-stu-id="39768-172">Users can be connected to different Persistent Chat Server Front End Servers and can be communicating with each other.</span></span> <span data-ttu-id="39768-173">TCP 8011 の既定のポートは、サーバーをサーバー プールに接続し、常設チャット サービスが自身間または管理上の目的で通信するために使用します。</span><span class="sxs-lookup"><span data-stu-id="39768-173">The default port of TCP 8011 connects a server to a server pool, and is used by the Persistent Chat services to communicate between themselves, or for administrative purposes.</span></span>
  
<span data-ttu-id="39768-174">たとえば、4 台のサーバーで構成される常設チャット サーバーの展開では、80,000 ユーザーが同時に常設チャットにサインインできる場合、負荷はサーバーごとに 20,000 ユーザーに均等に分散されます。</span><span class="sxs-lookup"><span data-stu-id="39768-174">For example, in a four-server Persistent Chat Server deployment, where 80,000 users can be simultaneously signed in to Persistent Chat, the load is distributed evenly at 20,000 users per server.</span></span> <span data-ttu-id="39768-175">1 つのサーバーが使用できなくなった場合、そのサーバーに接続しているユーザーは常設チャット サーバーにアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="39768-175">If one server becomes unavailable, the users who are connected to that server will lose their access to Persistent Chat Server.</span></span> <span data-ttu-id="39768-176">切断されたユーザーは、利用できなくなったサーバーが復元されるまでは、残りのサーバーに自動的に転送されます。</span><span class="sxs-lookup"><span data-stu-id="39768-176">The disconnected users will be automatically transferred to the remaining servers until the unavailable server is restored.</span></span> 
  

