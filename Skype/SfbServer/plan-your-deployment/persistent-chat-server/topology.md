---
title: 常設チャット サーバー トポロジの計画
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 5/17/2016
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6a0a14a0-baad-44e9-b26e-4d192c0a0e70
description: '概要: Skype for Business Server 2015 の常設チャットサーバーコンポーネントとトポロジについては、こちらのトピックを参照してください。'
ms.openlocfilehash: afcdf7ed85cca6b54652dcf5170316258a6b5551
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815725"
---
# <a name="plan-persistent-chat-server-topology"></a><span data-ttu-id="cd5b1-103">常設チャット サーバー トポロジの計画</span><span class="sxs-lookup"><span data-stu-id="cd5b1-103">Plan Persistent Chat Server topology</span></span>
 
<span data-ttu-id="cd5b1-104">**概要:** このトピックでは、Skype for Business Server 2015 の常設チャットサーバーコンポーネントとトポロジについて説明します。</span><span class="sxs-lookup"><span data-stu-id="cd5b1-104">**Summary:** Read this topic to learn about Persistent Chat Server components and topologies in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="cd5b1-105">常設チャットサーバーでは、単一サーバー構成と複数サーバー構成の両方がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="cd5b1-105">Persistent Chat Server supports both single-server and multiple-server configurations.</span></span> <span data-ttu-id="cd5b1-106">常設チャットサーバーは、Skype for Business Server 2015 Enterprise Edition か Standard Edition サーバーのいずれかにインストールできます。</span><span class="sxs-lookup"><span data-stu-id="cd5b1-106">You can install Persistent Chat Server on either a Skype for Business Server 2015 Enterprise Edition or Standard Edition Server.</span></span> 

> [!NOTE] 
> <span data-ttu-id="cd5b1-107">常設チャットは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="cd5b1-107">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="cd5b1-108">Teams でも同じ機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="cd5b1-108">The same functionality is available in Teams.</span></span> <span data-ttu-id="cd5b1-109">詳細については、「 [Microsoft Teams のアップグレードの](/microsoftteams/upgrade-start-here)概要」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cd5b1-109">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="cd5b1-110">常設チャットを使用する必要がある場合は、この機能が必要なユーザーをチームに移行するか、Skype for Business Server 2015 を使い続けるかのいずれかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="cd5b1-110">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 
  
## <a name="persistent-chat-server-components"></a><span data-ttu-id="cd5b1-111">常設チャットサーバーコンポーネント</span><span class="sxs-lookup"><span data-stu-id="cd5b1-111">Persistent Chat Server components</span></span>

<span data-ttu-id="cd5b1-112">常設チャット サーバーは、次のコンポーネントで構成されます。</span><span class="sxs-lookup"><span data-stu-id="cd5b1-112">Persistent Chat Server consists of the following components:</span></span>
  
- <span data-ttu-id="cd5b1-113">常設チャットサーバーを実行していて、次のサービスを提供している1台以上のコンピューター。</span><span class="sxs-lookup"><span data-stu-id="cd5b1-113">One or more computers running Persistent Chat Server and providing the following services:</span></span>
    
  - <span data-ttu-id="cd5b1-114">常設チャットサービス</span><span class="sxs-lookup"><span data-stu-id="cd5b1-114">Persistent Chat service</span></span>
    
  - <span data-ttu-id="cd5b1-115">コンプライアンスが有効な場合にオンになるコンプライアンス サービス</span><span class="sxs-lookup"><span data-stu-id="cd5b1-115">Compliance service, which is turned on if compliance is enabled</span></span>
    
- <span data-ttu-id="cd5b1-116">1つ以上のサーバー (ミラーリングが使用されている場合は複数)。チャットルームのコンテンツ、ルーム、カテゴリが保存されている常設チャットコンテンツデータベースをホストするための SQL Server バックエンドデータベースを実行しています。</span><span class="sxs-lookup"><span data-stu-id="cd5b1-116">One or more servers (more than one if mirroring is used) running the SQL Server back-end database for hosting the Persistent Chat content database where chat room content, rooms, and categories are stored.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="cd5b1-117">バックエンドデータベースには、作成されたカテゴリや常設チャットルームに関する情報など、チャット履歴データが格納されます。</span><span class="sxs-lookup"><span data-stu-id="cd5b1-117">The back-end database stores chat history data, including information about categories and Persistent Chat rooms that are created.</span></span> 
  
- <span data-ttu-id="cd5b1-118">コンプライアンスが有効になっている場合は、1つ以上のサーバー (ミラーリングが使用されている場合は複数) サーバーのバックエンドデータベースを実行して、コンプライアンスイベントとコンプライアンスのためのチャットコンテンツが保存されるようにします。</span><span class="sxs-lookup"><span data-stu-id="cd5b1-118">If compliance is enabled, one or more servers (more than one if mirroring is used) running the SQL Server back-end database for hosting the Persistent Chat Compliance database, where compliance events and chat content for the purpose of compliance are stored.</span></span>
    
<span data-ttu-id="cd5b1-119">常設チャットサーバーのハードウェアとソフトウェアの要件の詳細については、「skype for business server [2015 の常設チャットサーバーのハードウェアおよびソフトウェア](hardware-and-software-requirements.md) [2015 の](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)要件」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cd5b1-119">For details about hardware and software requirements for Persistent Chat Server, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) and [Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015](hardware-and-software-requirements.md).</span></span> 
  
## <a name="persistent-chat-server-topologies"></a><span data-ttu-id="cd5b1-120">常設チャットサーバーのトポロジ</span><span class="sxs-lookup"><span data-stu-id="cd5b1-120">Persistent Chat Server topologies</span></span>

<span data-ttu-id="cd5b1-121">常設チャットサーバーは、単一サーバープールまたは複数サーバープール、または単一プールトポロジまたは複数プールトポロジで展開できます。</span><span class="sxs-lookup"><span data-stu-id="cd5b1-121">You can deploy Persistent Chat Server in single-server or multiple-server pools, and with single-pool or multiple-pool topology.</span></span> <span data-ttu-id="cd5b1-122">常設チャットサーバーでは、次のトポロジがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="cd5b1-122">Persistent Chat Server supports the following topologies:</span></span>
  
-  <span data-ttu-id="cd5b1-123">Standard Edition Server と、フロント エンド サーバーに併置した常設チャット サーバー</span><span class="sxs-lookup"><span data-stu-id="cd5b1-123">Standard Edition Server with Persistent Chat Server collocated on the Front End Server</span></span>
    
-  <span data-ttu-id="cd5b1-124">別のサーバー上に常設チャットサーバーがある標準エディションサーバー</span><span class="sxs-lookup"><span data-stu-id="cd5b1-124">Standard Edition Server with Persistent Chat Server on a separate server</span></span>
    
-  <span data-ttu-id="cd5b1-125">別のサーバー上に1つの常設チャットサーバーがある Enterprise Edition Server</span><span class="sxs-lookup"><span data-stu-id="cd5b1-125">Enterprise Edition Server with a single Persistent Chat Server on a separate server</span></span>
    
-  <span data-ttu-id="cd5b1-126">別々のサーバーに複数の常設チャットサーバーがある Enterprise Edition Server</span><span class="sxs-lookup"><span data-stu-id="cd5b1-126">Enterprise Edition Server with more than one Persistent Chat Server on separate servers</span></span>
    
<span data-ttu-id="cd5b1-127">標準エディションのサーバーに常設チャットサーバーを展開することはできますが、パフォーマンスと規模が影響を受けるため、高可用性が適用されるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="cd5b1-127">Although you can deploy Persistent Chat Server on a Standard Edition Server, be aware that performance and scale will be affected, and high availability is not an option.</span></span> <span data-ttu-id="cd5b1-128">したがって、標準エディションのサーバーに永続的なチャットを展開することが推奨されます。</span><span class="sxs-lookup"><span data-stu-id="cd5b1-128">Therefore, it is recommended that you deploy Persistent Chat on a Standard Edition Server primarily for proof of concept and evaluation purposes.</span></span> 
  
<span data-ttu-id="cd5b1-129">Skype for Business Server 2015 は、さまざまな collocation シナリオをサポートしており、1台のサーバーに複数のコンポーネントを実行して (小規模組織の場合)、または異なるサーバーで個別のコンポーネントを実行することにより、ハードウェアコストを節約することができます (スケーラビリティとパフォーマンスが必要な大規模な組織の場合。</span><span class="sxs-lookup"><span data-stu-id="cd5b1-129">Skype for Business Server 2015 supports a variety of collocation scenarios, providing you the flexibility to save hardware costs by running multiple components on one server (if you have a small organization), or to run individual components on different servers (if you have a larger organization that needs scalability and performance).</span></span> <span data-ttu-id="cd5b1-130">コンポーネントを併置するかどうかを決定する前に、スケーラビリティの要因を検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd5b1-130">You should consider scalability factors before deciding whether to collocate components.</span></span> <span data-ttu-id="cd5b1-131">Collocation のシナリオは、Skype for Business Server 2015 Enterprise Edition と Standard Edition サーバーのものとは異なります。</span><span class="sxs-lookup"><span data-stu-id="cd5b1-131">Collocation scenarios differ for Skype for Business Server 2015 Enterprise Edition and Standard Edition servers.</span></span> 
  
<span data-ttu-id="cd5b1-132">以降のセクションでは、バックエンド データベース サーバーの併置シナリオやオプションなど、トポロジについてより詳細に説明します。</span><span class="sxs-lookup"><span data-stu-id="cd5b1-132">The following sections describe the topologies in more detail, including collocation scenarios and options for the back-end database servers.</span></span> <span data-ttu-id="cd5b1-133">すべてのサーバーの役割とデータベースの collocation の詳細については、「 [Skype For Business server 2015 のトポロジの基礎](../../plan-your-deployment/topology-basics/topology-basics.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cd5b1-133">For details about collocation of all server roles and databases, see [Topology Basics for Skype for Business Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md).</span></span>
  
### <a name="standard-edition-server-with-persistent-chat-server-collocated-on-the-front-end-server"></a><span data-ttu-id="cd5b1-134">Standard Edition Server と、フロント エンド サーバーに併置した常設チャット サーバー</span><span class="sxs-lookup"><span data-stu-id="cd5b1-134">Standard Edition Server with Persistent Chat Server collocated on the Front End Server</span></span>

<span data-ttu-id="cd5b1-135">Standard Edition では、常設チャットをフロントエンド サーバーに併置できます。</span><span class="sxs-lookup"><span data-stu-id="cd5b1-135">With Standard Edition, you can collocate Persistent Chat on the Front End Server.</span></span> <span data-ttu-id="cd5b1-136">これは最もシンプルで最も基本的な構成です。</span><span class="sxs-lookup"><span data-stu-id="cd5b1-136">This is the simplest and most basic configuration.</span></span> <span data-ttu-id="cd5b1-137">既存のフロントエンドサーバーの物理リソースに十分な容量があることを確認する必要があります。 CPU、メモリ、ディスク領域などです。</span><span class="sxs-lookup"><span data-stu-id="cd5b1-137">You must make sure that the existing Front End Server has enough capacity in terms of physical resources: CPU, memory, disk space, and so on.</span></span>
  
<span data-ttu-id="cd5b1-138">さらに、ローカルの SQL Server Express バックエンドサーバーで、常設チャットサーバーバックエンドサーバーと常設チャットのコンプライアンスデータベース (有効な場合) を簡単に見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="cd5b1-138">In addition, you can collocate the Persistent Chat Server back-end server and the Persistent Chat Compliance database (if enabled) on the local SQL Server Express back-end server.</span></span> <span data-ttu-id="cd5b1-139">また、別々の SQL Server を専用のインスタンスで使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="cd5b1-139">You can also choose to use a separate SQL Server with a dedicated instance.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="cd5b1-140">第1の常設チャットサーバーが標準エディションのフロントエンドサーバーと関連付けられている場合は、そのサーバーを常設チャットサーバープールに追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="cd5b1-140">You cannot add additional servers to a Persistent Chat Server pool if the first Persistent Chat Server is collocated with a Standard Edition Front End Server.</span></span> <span data-ttu-id="cd5b1-141">後で必要に応じてサーバーを追加できるように、最初のサーバーをスタンドアロンインスタンスとしてインストールすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="cd5b1-141">It is recommended that you install the first server as a standalone instance so that you can add more servers later, if needed.</span></span> 
  
### <a name="standard-edition-server-with-persistent-chat-server-installed-on-a-separate-server"></a><span data-ttu-id="cd5b1-142">Standard Edition サーバーと、別々のサーバーにインストールした常設チャット サーバー</span><span class="sxs-lookup"><span data-stu-id="cd5b1-142">Standard Edition Server with Persistent Chat Server installed on a separate server</span></span>

<span data-ttu-id="cd5b1-143">Standard Edition では、常設チャット サーバーをスタンドアロン インスタンスとしてインストールし、後で必要に応じてサーバーをさらに追加できます。  </span><span class="sxs-lookup"><span data-stu-id="cd5b1-143">With Standard Edition, you can install Persistent Chat Server as a standalone instance and add more servers later if needed.</span></span> 
  
<span data-ttu-id="cd5b1-144">ローカルの SQL Server Express バックエンドサーバーでは、常設チャットサーバーバックエンドサーバーと常設チャットのコンプライアンスデータベース (有効な場合) を簡単に見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="cd5b1-144">You can collocate the Persistent Chat Server back-end server and the Persistent Chat Compliance database (if enabled) on the local SQL Server Express back-end server.</span></span> <span data-ttu-id="cd5b1-145">また、別々の SQL Server を専用のインスタンスで使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="cd5b1-145">You can also choose to use a separate SQL Server with a dedicated instance.</span></span> 
  
### <a name="enterprise-edition-server-with-a-single-persistent-chat-server"></a><span data-ttu-id="cd5b1-146">Enterprise Edition サーバーと単一の常設チャット サーバー</span><span class="sxs-lookup"><span data-stu-id="cd5b1-146">Enterprise Edition Server with a single Persistent Chat Server</span></span>

<span data-ttu-id="cd5b1-147">Enterprise Edition では、常設チャット サーバーを別のコンピューターにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd5b1-147">With Enterprise Edition, you must install the Persistent Chat Server on a separate computer.</span></span> <span data-ttu-id="cd5b1-148">つまり、常設チャット サーバーを Enterprise Edition フロント エンド サーバーに併置することはできません。</span><span class="sxs-lookup"><span data-stu-id="cd5b1-148">That is, you cannot collocate the Persistent Chat Server on the Enterprise Edition Front End Server.</span></span> <span data-ttu-id="cd5b1-149">この展開には、常設チャットサーバーとコンプライアンスサービス (有効な場合) を実行する個別のサーバーが必要です。</span><span class="sxs-lookup"><span data-stu-id="cd5b1-149">This deployment requires a separate server that runs Persistent Chat Server and the Compliance service (if enabled).</span></span>
  
<span data-ttu-id="cd5b1-150">ただし、Enterprise Edition のフロントエンドプールのバックエンドデータベースでは、[SQL Server データベース] を [SQL Server データベース] に配置することができます。</span><span class="sxs-lookup"><span data-stu-id="cd5b1-150">You can, however, collocate the SQL Server database for Persistent Chat Server on the back-end database of an Enterprise Edition Front End pool.</span></span>
  
> [!NOTE]
> <span data-ttu-id="cd5b1-151">HA DR に SQL AlwaysOn 可用性グループを使用する場合は、これが常設チャット サーバーのデータベースでサポートされていないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="cd5b1-151">If you plan to use SQL AlwaysOn Availability Groups for HA DR, note that it is not supported for Persistent Chat Server databases.</span></span> 
  
<span data-ttu-id="cd5b1-152">バックエンドデータベースで永続的なチャットデータベースを作成する場合は、任意のデータベースまたはすべてのデータベースに対して SQL Server の1つのインスタンスを使うか、データベースごとに SQL Server の個別のインスタンスを使うことができます。</span><span class="sxs-lookup"><span data-stu-id="cd5b1-152">If you collocate the Persistent Chat database with the back-end database, you can either use a single instance of SQL Server for any or all of the databases, or you can use a separate instance of SQL Server for each database.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="cd5b1-153">常設チャットデータベースをホストしているサーバーは、他のデータベースをホストできます。</span><span class="sxs-lookup"><span data-stu-id="cd5b1-153">The server hosting the Persistent Chat database can host other databases.</span></span> <span data-ttu-id="cd5b1-154">ただし、他のデータベースとの間で永続的なチャットデータベースを検索することを検討している場合は、常設チャットデータベースに必要なディスク領域が非常に大きくなる可能性があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="cd5b1-154">However, when you consider collocating the Persistent Chat database with other databases, be aware that if you are storing the messages of more than a few users, the disk space needed by the Persistent Chat database can grow very large.</span></span> <span data-ttu-id="cd5b1-155">このため、バックエンドデータベースを使用して常設チャットデータベースを検索することはお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="cd5b1-155">For this reason, we do not recommend collocating the Persistent Chat database with the back-end database.</span></span> 
  
<span data-ttu-id="cd5b1-156">次の図は、コンプライアンスが有効になっている単一の常設チャットサーバーのトポロジのすべてのコンポーネントを示しています (省略可能)。</span><span class="sxs-lookup"><span data-stu-id="cd5b1-156">The following figure shows all components of a topology for a single Persistent Chat Server with compliance enabled (optional).</span></span>
  
<span data-ttu-id="cd5b1-157">**単一サーバー トポロジ**</span><span class="sxs-lookup"><span data-stu-id="cd5b1-157">**Single Server Topology**</span></span>

![常設チャット サーバー - 単一サーバー トポロジ](../../media/e1b39c28-8a4d-4c03-983b-4392889c2d14.png)
  
### <a name="enterprise-edition-server-with-multiple-persistent-chat-servers"></a><span data-ttu-id="cd5b1-159">Enterprise Edition サーバーと複数の常設チャット サーバー</span><span class="sxs-lookup"><span data-stu-id="cd5b1-159">Enterprise Edition Server with multiple Persistent Chat Servers</span></span>

<span data-ttu-id="cd5b1-160">Enterprise Edition では、複数サーバーのトポロジを展開して、容量と信頼性を高めることができます。</span><span class="sxs-lookup"><span data-stu-id="cd5b1-160">With Enterprise Edition, you can deploy a multiple-server topology for greater capacity and reliability.</span></span> <span data-ttu-id="cd5b1-161">複数サーバーのトポロジは、複数のサーバーが常設チャットサーバーをホストしていることを除いて、単一サーバートポロジと同じで、拡大縮小できます。</span><span class="sxs-lookup"><span data-stu-id="cd5b1-161">A multiple-server topology is the same as the single-server topology except that multiple servers host Persistent Chat Server, and can scale higher.</span></span> <span data-ttu-id="cd5b1-162">複数サーバーのトポロジには、常設チャットサーバーを実行しているアクティブなコンピューターを4つまで含めることができます (高可用性および障害回復構成では最大8個まで可能)。ただし、4つはアクティブ、残りの4つはスタンバイ状態になります。</span><span class="sxs-lookup"><span data-stu-id="cd5b1-162">The multiple-server topology can include as many as four active computers running Persistent Chat Server (high availability and disaster recovery configurations will allow up to eight, but only four can be active and the remaining four on standby).</span></span> <span data-ttu-id="cd5b1-163">各サーバーは、最大で2万の同時ユーザーをサポートできます。合計で8万の同時使用ユーザーは、4台のサーバーで常設チャットサーバープールに接続されています。</span><span class="sxs-lookup"><span data-stu-id="cd5b1-163">Each server can support as many as 20,000 concurrent users, for a total of 80,000 concurrent users connected to a Persistent Chat Server pool with 4 servers.</span></span> <span data-ttu-id="cd5b1-164">常設チャットサーバーが実行されている複数のコンピューターは、Skype for Business Server とコンプライアンスサービスと同じ Active Directory ドメインサービスドメインに存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd5b1-164">Multiple computers running Persistent Chat Server should reside in the same Active Directory Domain Services domain as Skype for Business Server and the Compliance service.</span></span>
  
<span data-ttu-id="cd5b1-165">次の図は、常設チャットサーバーを実行している複数のコンピューター、オプションのコンプライアンスサービス、および別のコンプライアンスデータベースの複数サーバートポロジのすべてのコンポーネントを示しています。</span><span class="sxs-lookup"><span data-stu-id="cd5b1-165">The following figure shows all the components of a multiple-server topology with multiple computers running Persistent Chat Server, the optional Compliance service, and a separate compliance database.</span></span>
  
<span data-ttu-id="cd5b1-166">**複数サーバー トポロジ**</span><span class="sxs-lookup"><span data-stu-id="cd5b1-166">**Multiple Server Topology**</span></span>

![常設チャット サーバー - 複数サーバー トポロジ](../../media/8fc20997-7acc-46ea-8dea-11239ffd9458.png)
  
<span data-ttu-id="cd5b1-168">複数サーバー トポロジでは、サーバー機能をプールできます。</span><span class="sxs-lookup"><span data-stu-id="cd5b1-168">Multiple-server topologies provide pooling of server functionality.</span></span> <span data-ttu-id="cd5b1-169">サーバープールでは、常設チャットサービスはデータをやり取りして共有します。</span><span class="sxs-lookup"><span data-stu-id="cd5b1-169">In a server pool, the Persistent Chat services communicate and share data.</span></span> <span data-ttu-id="cd5b1-170">たとえば、1つの常設チャットサービスに最初に投稿されたチャット履歴は、システムの任意の常設チャットサービスから入手できます。</span><span class="sxs-lookup"><span data-stu-id="cd5b1-170">For example, chat history that was originally posted to one Persistent Chat service is available from any Persistent Chat service in the system.</span></span> <span data-ttu-id="cd5b1-171">1つの常設チャットサービスを通じてアップロードされたファイルには、任意の常設チャットサービスからアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="cd5b1-171">A file that is uploaded through one Persistent Chat service can be accessed by any Persistent Chat service.</span></span> <span data-ttu-id="cd5b1-172">ユーザーは、さまざまな常設チャットサーバーフロントエンドサーバーに接続して、相互に通信できます。</span><span class="sxs-lookup"><span data-stu-id="cd5b1-172">Users can be connected to different Persistent Chat Server Front End Servers and can be communicating with each other.</span></span> <span data-ttu-id="cd5b1-173">TCP 8011 の既定のポートはサーバープールにサーバーを接続し、常設チャットサービスで自分との通信や管理目的のために使用されます。</span><span class="sxs-lookup"><span data-stu-id="cd5b1-173">The default port of TCP 8011 connects a server to a server pool, and is used by the Persistent Chat services to communicate between themselves, or for administrative purposes.</span></span>
  
<span data-ttu-id="cd5b1-174">たとえば、4サーバーの常設チャットサーバーを展開している場合、8万ユーザーは永続的なチャットに同時にサインインできるため、負荷はサーバーあたり2万ユーザーに均等に分散されます。</span><span class="sxs-lookup"><span data-stu-id="cd5b1-174">For example, in a four-server Persistent Chat Server deployment, where 80,000 users can be simultaneously signed in to Persistent Chat, the load is distributed evenly at 20,000 users per server.</span></span> <span data-ttu-id="cd5b1-175">1つのサーバーが利用できなくなった場合、そのサーバーに接続されているユーザーは、常設チャットサーバーにアクセスできなくなります。</span><span class="sxs-lookup"><span data-stu-id="cd5b1-175">If one server becomes unavailable, the users who are connected to that server will lose their access to Persistent Chat Server.</span></span> <span data-ttu-id="cd5b1-176">切断されたユーザーは、利用できなくなったサーバーが復元されるまでは、残りのサーバーに自動的に転送されます。</span><span class="sxs-lookup"><span data-stu-id="cd5b1-176">The disconnected users will be automatically transferred to the remaining servers until the unavailable server is restored.</span></span> 
  

