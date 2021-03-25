---
title: パイロット プールの展開
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Skype for Business Server 2019 への移行に必要な最初の手順の 1 つは、パイロット プールの展開です。 パイロット プールは、Skype for Business Server 2019 と従来の展開との共存をテストする場所です。 共存は、すべてのユーザーとプールを Skype for Business Server 2019 に移動するまで続く一時的な状態です。
ms.openlocfilehash: a8d9a1bbe5f629a91721ebe530e6a192e3e65b62
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51113293"
---
# <a name="deploy-skype-for-business-server-2019-pilot-pool"></a><span data-ttu-id="8359b-105">Skype for Business Server 2019 パイロット プールの展開</span><span class="sxs-lookup"><span data-stu-id="8359b-105">Deploy Skype for Business Server 2019 pilot pool</span></span>

<span data-ttu-id="8359b-106">Skype for Business Server 2019 への移行に必要な最初の手順の 1 つは、パイロット プールの展開です。</span><span class="sxs-lookup"><span data-stu-id="8359b-106">One of the first steps required for migration to Skype for Business Server 2019 is to deploy a pilot pool.</span></span> <span data-ttu-id="8359b-107">パイロット プールは、Skype for Business Server 2019 と従来の展開との共存をテストする場所です。</span><span class="sxs-lookup"><span data-stu-id="8359b-107">The pilot pool is where you test coexistence of Skype for Business Server 2019 with your legacy deployment.</span></span> <span data-ttu-id="8359b-108">共存は、すべてのユーザーとプールを Skype for Business Server 2019 に移動するまで続く一時的な状態です。</span><span class="sxs-lookup"><span data-stu-id="8359b-108">Coexistence is a temporary state that lasts until you have moved all users and pools to Skype for Business Server 2019.</span></span> 
  
<span data-ttu-id="8359b-109">パイロット プールを展開するときには、新しいフロントエンド プールの定義ウィザードを使用します。</span><span class="sxs-lookup"><span data-stu-id="8359b-109">When you deploy a pilot pool, you use the Define New Front End Pool wizard.</span></span> <span data-ttu-id="8359b-110">従来のプールにあるのと同じ機能とワークロードを Skype for Business Server 2019 パイロット プールに展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8359b-110">You should deploy the same features and workloads in your Skype for Business Server 2019 pilot pool that you have in your legacy pool.</span></span> <span data-ttu-id="8359b-111">従来の環境をアーカイブまたは監視するためにアーカイブ サーバー、監視サーバー、または System Center Operations Manager を展開し、移行中にアーカイブまたは監視を続行する場合は、パイロット環境にもこれらの機能を展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8359b-111">If you deployed Archiving Server, Monitoring Server, or System Center Operations Manager for archiving or monitoring your legacy environment, and you want to continue archiving or monitoring throughout the migration, you need to also deploy these features in your pilot environment.</span></span> <span data-ttu-id="8359b-112">従来の環境をアーカイブまたは監視するために展開したバージョンでは、Skype for Business Server 2019 環境のデータはキャプチャされません。</span><span class="sxs-lookup"><span data-stu-id="8359b-112">The version you deployed to archive or monitor your legacy environment will not capture data in your Skype for Business Server 2019 environment.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="8359b-113">次の手順では、パイロット プール全体の展開プロセスの中で検討する必要がある機能と設定について説明します。</span><span class="sxs-lookup"><span data-stu-id="8359b-113">The following procedure discusses features and settings you should consider as part of your overall pilot pool deployment process.</span></span> <span data-ttu-id="8359b-114">このセクションで説明するのは、パイロット プールの展開の際に考慮が必要となる主なポイントのみです。</span><span class="sxs-lookup"><span data-stu-id="8359b-114">This section only highlights key points you should consider as part of your pilot pool deployment.</span></span> <!-- For detailed steps, refer to the 
 [Deploying Skype for Business Server 2019](../deployment/deploying-lync-server-2013/deploying-lync-server-2013.md) deployment guide.  -->
  
### <a name="to-deploy-a-skype-for-business-server-2019-pilot-pool"></a><span data-ttu-id="8359b-115">Skype for Business Server 2019 パイロット プールを展開するには</span><span class="sxs-lookup"><span data-stu-id="8359b-115">To deploy a Skype for Business Server 2019 pilot pool</span></span>

1. <span data-ttu-id="8359b-116">トポロジ ビルダーがインストールされているコンピューターに、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="8359b-116">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="8359b-117">Skype for Business **Server 2019** Enterprise Edition フロントエンド プールに到達するまで  >  **ツリーを展開します**。</span><span class="sxs-lookup"><span data-stu-id="8359b-117">Expand the tree until you reach **Skype for Business Server 2019** > **Enterprise Edition Front End pools**.</span></span>
    
3. <span data-ttu-id="8359b-118">[Enterprise Edition フロントエンド **プール] を右クリックし、[** 新しい **フロント エンド プール] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="8359b-118">Right-click **Enterprise Edition Front End pools** and select **New Front End Pool**.</span></span>
  
4. <span data-ttu-id="8359b-119">プールの完全修飾ドメイン名 (FQDN) を入力します。</span><span class="sxs-lookup"><span data-stu-id="8359b-119">Enter the pool fully qualified domain name (FQDN).</span></span> <span data-ttu-id="8359b-120">パイロット プールを定義する場合は、Enterprise Edition フロントエンド プールまたは Standard Edition サーバーの展開を選択できます。</span><span class="sxs-lookup"><span data-stu-id="8359b-120">When you define your pilot pool, you can choose to deploy an Enterprise Edition Front End pool or a Standard Edition server.</span></span> <span data-ttu-id="8359b-121">Skype for Business Server 2019 では、パイロット プールの機能が従来のプールに展開された機能と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8359b-121">Skype for Business Server 2019 does not require that your pilot pool features match what was deployed in your legacy pool.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="8359b-122">パイロット プール用に定義するプールまたはサーバーの FQDN は一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="8359b-122">The pool or server FQDN that you define for the pilot pool must be unique.</span></span> <span data-ttu-id="8359b-123">現在展開されているレガシ プールまたは現在展開されている他のサーバーの名前と一致しません。</span><span class="sxs-lookup"><span data-stu-id="8359b-123">It cannot match the name of the currently deployed legacy pool or any other servers currently deployed.</span></span> 
  
5. <span data-ttu-id="8359b-124">**[機能の選択]** ページで、このフロント エンド プールで必要な機能のチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="8359b-124">On the **Select features** page, select the check boxes for the features that you want on this Front End pool.</span></span> <span data-ttu-id="8359b-125">たとえば、インスタント メッセージング (IM) とプレゼンス機能のみを展開する場合は、[会議] チェック ボックスをオンにしてマルチパーティ IM を許可しますが、音声、ビデオ、および共同作業の会議機能を表すダイヤルイン (PSTN) 会議、エンタープライズ VoIP、通話受付管理のチェック ボックスは選択しない場合があります。</span><span class="sxs-lookup"><span data-stu-id="8359b-125">For example, if you are deploying only instant messaging (IM) and presence features, you would select the Conferencing check box to allow multiparty IM, but you would not select the Dial-in (PSTN) conferencing, Enterprise Voice, or Call Admission Control check boxes, because they represent voice, video, and collaborative conferencing features.</span></span> <!-- For additional information on selecting features, see 
 [Define and configure a Front End pool or Standard Edition server in Skype for Business Server 2019](../deployment/deploying-lync-server-2013/define-and-configure-a-front-end-pool-or-standard-edition-server.md) in the Deployment documentation.  -->
  
6. <span data-ttu-id="8359b-126">[サーバー **の役割の選択** ] ページで、Skype for Business Server 2019 で仲介サーバーを照合することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8359b-126">On the **Select collocated server roles** page, we recommend that you choose to collocate the Mediation Server in Skype for Business Server 2019.</span></span> <span data-ttu-id="8359b-127">従来のトポロジを Skype for Business Server 2019 とマージする場合は、まず従来の仲介サーバーを併合する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8359b-127">When merging a legacy topology with Skype for Business Server 2019, we require that you first collocate the legacy Mediation Server.</span></span> <span data-ttu-id="8359b-128">トポロジをマージして Skype for Business Server 2019 仲介サーバーを構成した後、展開プロセスの後半で仲介サーバーの役割を Skype for Business Server 2019 に移動するときに、併置された仲介サーバーを保持するか、スタンドアロン サーバーに変更するかどうかを決定できます。</span><span class="sxs-lookup"><span data-stu-id="8359b-128">After merging the topologies and configuring the Skype for Business Server 2019 Mediation Server, you can decide whether to keep the collocated Mediation Server, or change it to a stand-alone server when you move the Mediation Server role to Skype for Business Server 2019 later in the deployment process.</span></span> 
   
7. <span data-ttu-id="8359b-129">[サーバー **の役割を** このフロントエンド プールに関連付ける] ページで、パイロット プールの展開中に、[このフロントエンド プールのメディア コンポーネントで使用するエッジ プールを有効にする] オプション **を選択** しません。</span><span class="sxs-lookup"><span data-stu-id="8359b-129">On the **Associate server roles with this Front End pool** page, during pilot pool deployment, *do not* choose the **Enable an Edge pool to be used by the media component of this Front End pool** option.</span></span> <span data-ttu-id="8359b-130">これは、移行のフェーズが進んだ段階で有効にしてオンラインにする機能です。</span><span class="sxs-lookup"><span data-stu-id="8359b-130">This is a feature you will enable and bring online in a later phase of migration.</span></span> <span data-ttu-id="8359b-131">現時点ではこの設定はオフのままにしてください。</span><span class="sxs-lookup"><span data-stu-id="8359b-131">Keep this setting cleared for now.</span></span> 
  
8. <span data-ttu-id="8359b-132">[**Office Web Apps Server の選択**] ページで [**新規作成**] をクリックし、アプリケーション サーバーの FQDN を指定します。</span><span class="sxs-lookup"><span data-stu-id="8359b-132">On the **Select an Office Web Apps Server** page, click **New**, and specify the FQDN of the application server.</span></span>
  
9. <span data-ttu-id="8359b-133">[アーカイブSQL Server ストアの定義] ページで、Skype for Business Server アーカイブと監視の両方の SQL Server ストアを定義する場合は、Skype for Business Server 2019 用に前に作成した SQL Server インスタンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="8359b-133">On the **Define the Archiving SQL Server store** page, when defining the SQL Server store for both Skype for Business Server Archiving and Monitoring, select the SQL Server instance created earlier for Skype for Business Server 2019.</span></span> 
  
10. <span data-ttu-id="8359b-134">トポロジを発行するには **、Skype for Business Server** ノードを右クリックし、[トポロジの公開] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="8359b-134">To publish your topology, right-click the **Skype for Business Server** node, and then click **Publish Topology**.</span></span>
  
11. <span data-ttu-id="8359b-135">公開プロセスが完了したら、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8359b-135">When the publish process has completed, click **Finish**.</span></span>

12. <span data-ttu-id="8359b-136">"従来のプールとのパイロット プールの共存を確認する" という次のセクションに移動する前に、公開トポロジで定義した Skype for Business Server の新しいフロントエンド パイロット プールをインストールする必要があります。トポロジ内のサーバーに[Skype for Business Server](../../SfbServer/deploy/install/install-skype-for-business-server.md)をインストールする手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="8359b-136">Before moving to the next section called "Verify pilot pool coexistence with legacy pool" you need to install the Skype for Business Server new Front End pilot pool we just defined in the published topology, follow the procedures outlined here [Install Skype for Business Server on servers in the topology](../../SfbServer/deploy/install/install-skype-for-business-server.md)</span></span>

13. <span data-ttu-id="8359b-137">前の手順が完了したら、[パイロット プールとレガシ プールとの共存を確認する] の次のセクションに移動します。</span><span class="sxs-lookup"><span data-stu-id="8359b-137">Once previous step is complete, move to the next section to Verify pilot pool coexistence with legacy pool.</span></span>
    
<!-- To install a local copy of the configuration store and start the required services, see 
[Setting up Front End Servers and Front End pools for Skype for Business Server 2019](../deployment/deploying-lync-server-2013/setting-up-front-end-servers-and-front-end-pools.md) in the Deployment documentation.  -->
