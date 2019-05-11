---
title: 常設チャット サーバー トポロジの計画
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 5/17/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6a0a14a0-baad-44e9-b26e-4d192c0a0e70
description: '概要: ビジネス サーバー 2015 の永続的なチャット サーバーのコンポーネントおよびトポロジでは、Skype については、このトピックを読みます。'
ms.openlocfilehash: d004557da9a47a8d5de544af18e74eb7eecc01b0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33926066"
---
# <a name="plan-persistent-chat-server-topology"></a><span data-ttu-id="523c3-103">常設チャット サーバー トポロジの計画</span><span class="sxs-lookup"><span data-stu-id="523c3-103">Plan Persistent Chat Server topology</span></span>
 
<span data-ttu-id="523c3-104">**の概要:** ビジネス サーバー 2015 の永続的なチャット サーバーのコンポーネントおよびトポロジでは、Skype については、このトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="523c3-104">**Summary:** Read this topic to learn about Persistent Chat Server components and topologies in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="523c3-105">永続的なチャット サーバーには、1 台のサーバーと複数サーバーの両方の構成がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="523c3-105">Persistent Chat Server supports both single-server and multiple-server configurations.</span></span> <span data-ttu-id="523c3-106">ビジネス サーバー 2015 の Enterprise Edition または Standard Edition Server のいずれか、Skype で永続的なチャット サーバーをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="523c3-106">You can install Persistent Chat Server on either a Skype for Business Server 2015 Enterprise Edition or Standard Edition Server.</span></span> 

> [!NOTE] 
> <span data-ttu-id="523c3-107">永続的なチャットですがビジネス サーバー 2015 の Skype で利用可能なビジネス サーバー 2019 の Skype でサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="523c3-107">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="523c3-108">同じ機能は、チームで使用できます。</span><span class="sxs-lookup"><span data-stu-id="523c3-108">The same functionality is available in Teams.</span></span> <span data-ttu-id="523c3-109">詳細については、[マイクロソフトのチームにビジネス用の Skype からの旅](/microsoftteams/journey-skypeforbusiness-teams)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="523c3-109">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="523c3-110">永続的なチャットを使用する場合は、選択肢は、いずれかをチームでは、この機能を必要とするユーザーを移行するまたはビジネス サーバー 2015 の Skype を使用し続ける。</span><span class="sxs-lookup"><span data-stu-id="523c3-110">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 
  
## <a name="persistent-chat-server-components"></a><span data-ttu-id="523c3-111">永続的なチャット サーバーのコンポーネント</span><span class="sxs-lookup"><span data-stu-id="523c3-111">Persistent Chat Server components</span></span>

<span data-ttu-id="523c3-112">常設チャット サーバーは、次のコンポーネントで構成されます。</span><span class="sxs-lookup"><span data-stu-id="523c3-112">Persistent Chat Server consists of the following components:</span></span>
  
- <span data-ttu-id="523c3-113">1 つまたは複数のコンピューター永続的なチャット サーバーを実行して、次のサービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="523c3-113">One or more computers running Persistent Chat Server and providing the following services:</span></span>
    
  - <span data-ttu-id="523c3-114">永続的なチャット サービス</span><span class="sxs-lookup"><span data-stu-id="523c3-114">Persistent Chat service</span></span>
    
  - <span data-ttu-id="523c3-115">コンプライアンスが有効な場合にオンになるコンプライアンス サービス</span><span class="sxs-lookup"><span data-stu-id="523c3-115">Compliance service, which is turned on if compliance is enabled</span></span>
    
- <span data-ttu-id="523c3-116">1 つまたは複数のサーバー (1 つ以上のミラーリングを使用する場合)、永続的なチャットのコンテンツ データベースをホストするための SQL Server バックエンド データベースを実行して、チャット ルームの内容、会議室、およびカテゴリが格納されています。</span><span class="sxs-lookup"><span data-stu-id="523c3-116">One or more servers (more than one if mirroring is used) running the SQL Server back-end database for hosting the Persistent Chat content database where chat room content, rooms, and categories are stored.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="523c3-117">バック エンド データベースは、作成される永続的なチャット ルームのカテゴリに関する情報など、チャットの履歴データを格納します。</span><span class="sxs-lookup"><span data-stu-id="523c3-117">The back-end database stores chat history data, including information about categories and Persistent Chat rooms that are created.</span></span> 
  
- <span data-ttu-id="523c3-118">コンプライアンスを有効にすると、1 つまたは複数のサーバー (1 つ以上のミラーリングを使用する場合)、永続的なチャット コンプライアンス データベースをホストするための SQL Server バックエンド データベースを実行しているコンプライアンスのためのコンプライアンスのイベントやチャットのコンテンツ、保存されます。</span><span class="sxs-lookup"><span data-stu-id="523c3-118">If compliance is enabled, one or more servers (more than one if mirroring is used) running the SQL Server back-end database for hosting the Persistent Chat Compliance database, where compliance events and chat content for the purpose of compliance are stored.</span></span>
    
<span data-ttu-id="523c3-119">永続的なチャット サーバーのハードウェアおよびソフトウェアの要件についての詳細は、[ビジネス サーバー 2015 の Skype のサーバー要件](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)と[ビジネス サーバー 2015 の Skype での永続的なチャット サーバーのハードウェアおよびソフトウェアの要件](hardware-and-software-requirements.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="523c3-119">For details about hardware and software requirements for Persistent Chat Server, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) and [Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015](hardware-and-software-requirements.md).</span></span> 
  
## <a name="persistent-chat-server-topologies"></a><span data-ttu-id="523c3-120">永続的なチャット サーバーのトポロジ</span><span class="sxs-lookup"><span data-stu-id="523c3-120">Persistent Chat Server topologies</span></span>

<span data-ttu-id="523c3-121">永続的なチャット サーバー プールの 1 つまたは複数のプールのトポロジと 1 台のサーバーまたは複数サーバーのプール内に配置できます。</span><span class="sxs-lookup"><span data-stu-id="523c3-121">You can deploy Persistent Chat Server in single-server or multiple-server pools, and with single-pool or multiple-pool topology.</span></span> <span data-ttu-id="523c3-122">永続的なチャット サーバーには、次のトポロジがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="523c3-122">Persistent Chat Server supports the following topologies:</span></span>
  
-  <span data-ttu-id="523c3-123">Standard Edition Server と、フロント エンド サーバーに併置した常設チャット サーバー</span><span class="sxs-lookup"><span data-stu-id="523c3-123">Standard Edition Server with Persistent Chat Server collocated on the Front End Server</span></span>
    
-  <span data-ttu-id="523c3-124">別のサーバー上の永続的なチャット サーバーで標準のエディション サーバー</span><span class="sxs-lookup"><span data-stu-id="523c3-124">Standard Edition Server with Persistent Chat Server on a separate server</span></span>
    
-  <span data-ttu-id="523c3-125">1 つ永続的なチャット サーバーと別のサーバーにエンタープライズ エディションのサーバー</span><span class="sxs-lookup"><span data-stu-id="523c3-125">Enterprise Edition Server with a single Persistent Chat Server on a separate server</span></span>
    
-  <span data-ttu-id="523c3-126">1 つ以上の永続的なチャット サーバーを別々 のサーバーとエンタープライズ エディション サーバー</span><span class="sxs-lookup"><span data-stu-id="523c3-126">Enterprise Edition Server with more than one Persistent Chat Server on separate servers</span></span>
    
<span data-ttu-id="523c3-127">標準エディションのサーバー上の永続的なチャット サーバーを配置できますが、パフォーマンスと拡張性が影響を受けるとなる高可用性は、オプションではありません。</span><span class="sxs-lookup"><span data-stu-id="523c3-127">Although you can deploy Persistent Chat Server on a Standard Edition Server, be aware that performance and scale will be affected, and high availability is not an option.</span></span> <span data-ttu-id="523c3-128">したがって、主の概念と評価のための証拠としての Standard Edition Server 上の永続的なチャットを展開することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="523c3-128">Therefore, it is recommended that you deploy Persistent Chat on a Standard Edition Server primarily for proof of concept and evaluation purposes.</span></span> 
  
<span data-ttu-id="523c3-129">ビジネス サーバー 2015 の Skype をサポートしているコロケーション シナリオでは、1 台のサーバー (小規模な組織の場合)、複数のコンポーネントを実行して、ハードウェアのコストを削減する、または別のサーバー (上の個々 のコンポーネントを実行する柔軟性を提供します。ある場合のスケーラビリティとパフォーマンスを必要とする大規模な組織)。</span><span class="sxs-lookup"><span data-stu-id="523c3-129">Skype for Business Server 2015 supports a variety of collocation scenarios, providing you the flexibility to save hardware costs by running multiple components on one server (if you have a small organization), or to run individual components on different servers (if you have a larger organization that needs scalability and performance).</span></span> <span data-ttu-id="523c3-130">コンポーネントを併置するかどうかを決定する前に、スケーラビリティの要因を検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="523c3-130">You should consider scalability factors before deciding whether to collocate components.</span></span> <span data-ttu-id="523c3-131">コロケーションのシナリオでは、ビジネス サーバー 2015 の Enterprise Edition と Standard Edition サーバーの Skype で異なります。</span><span class="sxs-lookup"><span data-stu-id="523c3-131">Collocation scenarios differ for Skype for Business Server 2015 Enterprise Edition and Standard Edition servers.</span></span> 
  
<span data-ttu-id="523c3-132">以降のセクションでは、バックエンド データベース サーバーの併置シナリオやオプションなど、トポロジについてより詳細に説明します。</span><span class="sxs-lookup"><span data-stu-id="523c3-132">The following sections describe the topologies in more detail, including collocation scenarios and options for the back-end database servers.</span></span> <span data-ttu-id="523c3-133">コロケーションをすべてのサーバー ロールおよびデータベースの詳細については、[ビジネス サーバー 2015 の Skype のトポロジーの基本事項](../../plan-your-deployment/topology-basics/topology-basics.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="523c3-133">For details about collocation of all server roles and databases, see [Topology Basics for Skype for Business Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md).</span></span>
  
### <a name="standard-edition-server-with-persistent-chat-server-collocated-on-the-front-end-server"></a><span data-ttu-id="523c3-134">Standard Edition Server と、フロント エンド サーバーに併置した常設チャット サーバー</span><span class="sxs-lookup"><span data-stu-id="523c3-134">Standard Edition Server with Persistent Chat Server collocated on the Front End Server</span></span>

<span data-ttu-id="523c3-135">Standard Edition では、常設チャットをフロントエンド サーバーに併置できます。</span><span class="sxs-lookup"><span data-stu-id="523c3-135">With Standard Edition, you can collocate Persistent Chat on the Front End Server.</span></span> <span data-ttu-id="523c3-136">これは最もシンプルで最も基本的な構成です。</span><span class="sxs-lookup"><span data-stu-id="523c3-136">This is the simplest and most basic configuration.</span></span> <span data-ttu-id="523c3-137">既存のフロント エンド サーバーに物理リソースの不足のための容量があることを確認する必要があります: CPU、メモリ、ディスク領域、およびようにします。</span><span class="sxs-lookup"><span data-stu-id="523c3-137">You must make sure that the existing Front End Server has enough capacity in terms of physical resources: CPU, memory, disk space, and so on.</span></span>
  
<span data-ttu-id="523c3-138">さらに、集約できます永続的なチャット サーバーのバックエンド サーバーと永続的なチャット コンプライアンス データベース (有効な場合) ローカルの SQL Server Express のバックエンド サーバーにします。</span><span class="sxs-lookup"><span data-stu-id="523c3-138">In addition, you can collocate the Persistent Chat Server back-end server and the Persistent Chat Compliance database (if enabled) on the local SQL Server Express back-end server.</span></span> <span data-ttu-id="523c3-139">また、別々の SQL Server を専用のインスタンスで使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="523c3-139">You can also choose to use a separate SQL Server with a dedicated instance.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="523c3-140">最初の永続的なチャット サーバーが標準的な Edition フロント エンド サーバーに併設されている場合は、永続的なチャット サーバー プールにサーバーを追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="523c3-140">You cannot add additional servers to a Persistent Chat Server pool if the first Persistent Chat Server is collocated with a Standard Edition Front End Server.</span></span> <span data-ttu-id="523c3-141">としてインストールすることの最初のサーバー、スタンドアロン インスタンス以降より多くのサーバーを追加できるように、必要な場合をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="523c3-141">It is recommended that you install the first server as a standalone instance so that you can add more servers later, if needed.</span></span> 
  
### <a name="standard-edition-server-with-persistent-chat-server-installed-on-a-separate-server"></a><span data-ttu-id="523c3-142">Standard Edition サーバーと、別々のサーバーにインストールした常設チャット サーバー</span><span class="sxs-lookup"><span data-stu-id="523c3-142">Standard Edition Server with Persistent Chat Server installed on a separate server</span></span>

<span data-ttu-id="523c3-143">Standard Edition では、常設チャット サーバーをスタンドアロン インスタンスとしてインストールし、後で必要に応じてサーバーをさらに追加できます。  </span><span class="sxs-lookup"><span data-stu-id="523c3-143">With Standard Edition, you can install Persistent Chat Server as a standalone instance and add more servers later if needed.</span></span> 
  
<span data-ttu-id="523c3-144">集約できます永続的なチャット サーバーのバックエンド サーバーと永続的なチャット コンプライアンス データベースが有効な場合) ローカルの SQL Server Express のバックエンド サーバーにします。</span><span class="sxs-lookup"><span data-stu-id="523c3-144">You can collocate the Persistent Chat Server back-end server and the Persistent Chat Compliance database (if enabled) on the local SQL Server Express back-end server.</span></span> <span data-ttu-id="523c3-145">また、別々の SQL Server を専用のインスタンスで使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="523c3-145">You can also choose to use a separate SQL Server with a dedicated instance.</span></span> 
  
### <a name="enterprise-edition-server-with-a-single-persistent-chat-server"></a><span data-ttu-id="523c3-146">Enterprise Edition サーバーと単一の常設チャット サーバー</span><span class="sxs-lookup"><span data-stu-id="523c3-146">Enterprise Edition Server with a single Persistent Chat Server</span></span>

<span data-ttu-id="523c3-147">Enterprise Edition では、常設チャット サーバーを別のコンピューターにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="523c3-147">With Enterprise Edition, you must install the Persistent Chat Server on a separate computer.</span></span> <span data-ttu-id="523c3-148">つまり、常設チャット サーバーを Enterprise Edition フロント エンド サーバーに併置することはできません。</span><span class="sxs-lookup"><span data-stu-id="523c3-148">That is, you cannot collocate the Persistent Chat Server on the Enterprise Edition Front End Server.</span></span> <span data-ttu-id="523c3-149">この展開には、永続的なチャット サーバーとコンプライアンス サービスが有効な場合) を実行する別のサーバーが必要です。</span><span class="sxs-lookup"><span data-stu-id="523c3-149">This deployment requires a separate server that runs Persistent Chat Server and the Compliance service (if enabled).</span></span>
  
<span data-ttu-id="523c3-150">エンタープライズ エディションのフロント エンド プールのバック エンド データベースに永続的なチャット サーバーの SQL Server データベースをまとめてすることができます、ただし、です。</span><span class="sxs-lookup"><span data-stu-id="523c3-150">You can, however, collocate the SQL Server database for Persistent Chat Server on the back-end database of an Enterprise Edition Front End pool.</span></span>
  
> [!NOTE]
> <span data-ttu-id="523c3-151">HA DR に SQL AlwaysOn 可用性グループを使用する場合は、これが常設チャット サーバーのデータベースでサポートされていないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="523c3-151">If you plan to use SQL AlwaysOn Availability Groups for HA DR, note that it is not supported for Persistent Chat Server databases.</span></span> 
  
<span data-ttu-id="523c3-152">バック エンド データベースに永続的なチャット データベースを連結する場合、データベースの一部またはすべての SQL Server の単一のインスタンスを使用することができますか、または各データベースの SQL Server の別のインスタンスを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="523c3-152">If you collocate the Persistent Chat database with the back-end database, you can either use a single instance of SQL Server for any or all of the databases, or you can use a separate instance of SQL Server for each database.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="523c3-153">永続的なチャットのデータベースをホストするサーバーは、他のデータベースをホストできます。</span><span class="sxs-lookup"><span data-stu-id="523c3-153">The server hosting the Persistent Chat database can host other databases.</span></span> <span data-ttu-id="523c3-154">ただし、他のデータベースに永続的なチャットのデータベースの配置を検討する場合ありますを多くのユーザーのメッセージを格納する場合ディスク領域が必要な永続的なチャットのデータベースでが非常に大ききます。</span><span class="sxs-lookup"><span data-stu-id="523c3-154">However, when you consider collocating the Persistent Chat database with other databases, be aware that if you are storing the messages of more than a few users, the disk space needed by the Persistent Chat database can grow very large.</span></span> <span data-ttu-id="523c3-155">このため、行うこと、永続的なチャットのデータベース バック エンド データベースを配置します。</span><span class="sxs-lookup"><span data-stu-id="523c3-155">For this reason, we do not recommend collocating the Persistent Chat database with the back-end database.</span></span> 
  
<span data-ttu-id="523c3-156">次の図、トポロジのすべてのコンポーネントの 1 つの永続的なチャット サーバー コンプライアンスが有効になっていると (省略可能)。</span><span class="sxs-lookup"><span data-stu-id="523c3-156">The following figure shows all components of a topology for a single Persistent Chat Server with compliance enabled (optional).</span></span>
  
<span data-ttu-id="523c3-157">**単一サーバー トポロジ**</span><span class="sxs-lookup"><span data-stu-id="523c3-157">**Single Server Topology**</span></span>

![常設チャット サーバー - 単一サーバー トポロジ](../../media/e1b39c28-8a4d-4c03-983b-4392889c2d14.png)
  
### <a name="enterprise-edition-server-with-multiple-persistent-chat-servers"></a><span data-ttu-id="523c3-159">Enterprise Edition サーバーと複数の常設チャット サーバー</span><span class="sxs-lookup"><span data-stu-id="523c3-159">Enterprise Edition Server with multiple Persistent Chat Servers</span></span>

<span data-ttu-id="523c3-160">Enterprise Edition では、容量と信頼性を向上するための複数サーバー トポロジを導入できます。</span><span class="sxs-lookup"><span data-stu-id="523c3-160">With Enterprise Edition, you can deploy a multiple-server topology for greater capacity and reliability.</span></span> <span data-ttu-id="523c3-161">複数サーバー トポロジは、複数のサーバーは、永続的なチャット サーバーをホストし、それ以上に拡張できることを除いてシングル サーバー トポロジと同じです。</span><span class="sxs-lookup"><span data-stu-id="523c3-161">A multiple-server topology is the same as the single-server topology except that multiple servers host Persistent Chat Server, and can scale higher.</span></span> <span data-ttu-id="523c3-162">複数サーバー トポロジは、永続的なチャット サーバーを実行して、最大で 4 つのアクティブなコンピューターを含めることができます (8 個まで、高可用性と災害復旧の構成は許可するが、アクティブであり、残りのスタンバイ状態には 4 つを 4 つだけとして使用することができます)。</span><span class="sxs-lookup"><span data-stu-id="523c3-162">The multiple-server topology can include as many as four active computers running Persistent Chat Server (high availability and disaster recovery configurations will allow up to eight, but only four can be active and the remaining four on standby).</span></span> <span data-ttu-id="523c3-163">各サーバーは、合計で 4 台のサーバの永続的なチャット サーバー プールに接続されている 80,000 の同時接続ユーザーの最大 20,000 の同時接続ユーザーをサポートできます。</span><span class="sxs-lookup"><span data-stu-id="523c3-163">Each server can support as many as 20,000 concurrent users, for a total of 80,000 concurrent users connected to a Persistent Chat Server pool with 4 servers.</span></span> <span data-ttu-id="523c3-164">永続的なチャット サーバーを実行している複数のコンピューターは、ビジネス サーバーとコンプライアンス サービスの Skype と同じ Active Directory ドメイン サービス ドメインに存在すべきです。</span><span class="sxs-lookup"><span data-stu-id="523c3-164">Multiple computers running Persistent Chat Server should reside in the same Active Directory Domain Services domain as Skype for Business Server and the Compliance service.</span></span>
  
<span data-ttu-id="523c3-165">次の図は、永続的なチャット サーバー、オプションのコンプライアンス サービスと独立したコンプライアンス データベースを実行する複数のコンピューターで、複数サーバー トポロジのすべてのコンポーネントを示しています。</span><span class="sxs-lookup"><span data-stu-id="523c3-165">The following figure shows all the components of a multiple-server topology with multiple computers running Persistent Chat Server, the optional Compliance service, and a separate compliance database.</span></span>
  
<span data-ttu-id="523c3-166">**複数サーバー トポロジ**</span><span class="sxs-lookup"><span data-stu-id="523c3-166">**Multiple Server Topology**</span></span>

![常設チャット サーバー - 複数サーバー トポロジ](../../media/8fc20997-7acc-46ea-8dea-11239ffd9458.png)
  
<span data-ttu-id="523c3-168">複数サーバー トポロジでは、サーバー機能をプールできます。</span><span class="sxs-lookup"><span data-stu-id="523c3-168">Multiple-server topologies provide pooling of server functionality.</span></span> <span data-ttu-id="523c3-169">サーバー プールには、永続的なチャット サービスは通信やデータ共有します。</span><span class="sxs-lookup"><span data-stu-id="523c3-169">In a server pool, the Persistent Chat services communicate and share data.</span></span> <span data-ttu-id="523c3-170">たとえば、1 つの永続的なチャット サービスにポストされた最初のチャットの履歴の永続的なチャット サービスから利用可能なシステムでは。</span><span class="sxs-lookup"><span data-stu-id="523c3-170">For example, chat history that was originally posted to one Persistent Chat service is available from any Persistent Chat service in the system.</span></span> <span data-ttu-id="523c3-171">1 つの永続的なチャット サービスを介してアップロードされたファイルは、すべての永続的なチャット サービスでアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="523c3-171">A file that is uploaded through one Persistent Chat service can be accessed by any Persistent Chat service.</span></span> <span data-ttu-id="523c3-172">ユーザーは、さまざまな永続的なチャット サーバー フロント エンド サーバーに接続することし、相互に通信することができます。</span><span class="sxs-lookup"><span data-stu-id="523c3-172">Users can be connected to different Persistent Chat Server Front End Servers and can be communicating with each other.</span></span> <span data-ttu-id="523c3-173">TCP の既定ポート 8011 では、サーバーをサーバー プールに接続され、間で、または管理目的のために通信するために永続的なチャット サービスで使用されます。</span><span class="sxs-lookup"><span data-stu-id="523c3-173">The default port of TCP 8011 connects a server to a server pool, and is used by the Persistent Chat services to communicate between themselves, or for administrative purposes.</span></span>
  
<span data-ttu-id="523c3-174">などの 80,000 ユーザーに同時に署名できる永続的なチャットするのには、4 台のサーバー上の永続的なチャット サーバー展開で、負荷が均等に分散サーバーあたり 20,000 ユーザーで。</span><span class="sxs-lookup"><span data-stu-id="523c3-174">For example, in a four-server Persistent Chat Server deployment, where 80,000 users can be simultaneously signed in to Persistent Chat, the load is distributed evenly at 20,000 users per server.</span></span> <span data-ttu-id="523c3-175">1 台のサーバーが使用できなくなった場合、そのサーバーに接続しているユーザーは、永続的なチャット サーバーへのアクセスをできなくなります。</span><span class="sxs-lookup"><span data-stu-id="523c3-175">If one server becomes unavailable, the users who are connected to that server will lose their access to Persistent Chat Server.</span></span> <span data-ttu-id="523c3-176">切断されたユーザーは、利用できなくなったサーバーが復元されるまでは、残りのサーバーに自動的に転送されます。</span><span class="sxs-lookup"><span data-stu-id="523c3-176">The disconnected users will be automatically transferred to the remaining servers until the unavailable server is restored.</span></span> 
  

