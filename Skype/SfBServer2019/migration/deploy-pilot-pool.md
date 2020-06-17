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
description: Skype for Business Server 2019 への移行に必要な最初の手順の1つは、パイロットプールを展開することです。 パイロットプールは、従来の展開と Skype for Business Server 2019 の共存をテストする場所です。 共存は、すべてのユーザーとプールを Skype for Business Server 2019 に移動するまで、一時的な状態になります。
ms.openlocfilehash: 46d8b6fd6cefa2894f67a1c24732ace01ca65785
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752859"
---
# <a name="deploy-skype-for-business-server-2019-pilot-pool"></a><span data-ttu-id="c5f8f-105">Skype for Business Server 2019 パイロットプールの展開</span><span class="sxs-lookup"><span data-stu-id="c5f8f-105">Deploy Skype for Business Server 2019 pilot pool</span></span>

<span data-ttu-id="c5f8f-106">Skype for Business Server 2019 への移行に必要な最初の手順の1つは、パイロットプールを展開することです。</span><span class="sxs-lookup"><span data-stu-id="c5f8f-106">One of the first steps required for migration to Skype for Business Server 2019 is to deploy a pilot pool.</span></span> <span data-ttu-id="c5f8f-107">パイロットプールは、従来の展開と Skype for Business Server 2019 の共存をテストする場所です。</span><span class="sxs-lookup"><span data-stu-id="c5f8f-107">The pilot pool is where you test coexistence of Skype for Business Server 2019 with your legacy deployment.</span></span> <span data-ttu-id="c5f8f-108">共存は、すべてのユーザーとプールを Skype for Business Server 2019 に移動するまで、一時的な状態になります。</span><span class="sxs-lookup"><span data-stu-id="c5f8f-108">Coexistence is a temporary state that lasts until you have moved all users and pools to Skype for Business Server 2019.</span></span> 
  
<span data-ttu-id="c5f8f-109">パイロット プールを展開するときには、新しいフロントエンド プールの定義ウィザードを使用します。</span><span class="sxs-lookup"><span data-stu-id="c5f8f-109">When you deploy a pilot pool, you use the Define New Front End Pool wizard.</span></span> <span data-ttu-id="c5f8f-110">従来のプールにある、Skype for Business Server 2019 パイロットプールと同じ機能とワークロードを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c5f8f-110">You should deploy the same features and workloads in your Skype for Business Server 2019 pilot pool that you have in your legacy pool.</span></span> <span data-ttu-id="c5f8f-111">アーカイブサーバー、監視サーバー、または System Center Operations Manager を展開して従来の環境をアーカイブまたは監視している場合に、移行全体を通してアーカイブまたは監視を続行するには、これらの機能をパイロット環境に展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c5f8f-111">If you deployed Archiving Server, Monitoring Server, or System Center Operations Manager for archiving or monitoring your legacy environment, and you want to continue archiving or monitoring throughout the migration, you need to also deploy these features in your pilot environment.</span></span> <span data-ttu-id="c5f8f-112">従来の環境をアーカイブまたは監視するために展開したバージョンでは、Skype for Business Server 2019 環境のデータはキャプチャされません。</span><span class="sxs-lookup"><span data-stu-id="c5f8f-112">The version you deployed to archive or monitor your legacy environment will not capture data in your Skype for Business Server 2019 environment.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="c5f8f-113">次の手順では、パイロット プール全体の展開プロセスの中で検討する必要がある機能と設定について説明します。</span><span class="sxs-lookup"><span data-stu-id="c5f8f-113">The following procedure discusses features and settings you should consider as part of your overall pilot pool deployment process.</span></span> <span data-ttu-id="c5f8f-114">このセクションで説明するのは、パイロット プールの展開の際に考慮が必要となる主なポイントのみです。</span><span class="sxs-lookup"><span data-stu-id="c5f8f-114">This section only highlights key points you should consider as part of your pilot pool deployment.</span></span> <!-- For detailed steps, refer to the 
 [Deploying Skype for Business Server 2019](../deployment/deploying-lync-server-2013/deploying-lync-server-2013.md) deployment guide.  -->
  
### <a name="to-deploy-a-skype-for-business-server-2019-pilot-pool"></a><span data-ttu-id="c5f8f-115">Skype for Business Server 2019 パイロットプールを展開するには</span><span class="sxs-lookup"><span data-stu-id="c5f8f-115">To deploy a Skype for Business Server 2019 pilot pool</span></span>

1. <span data-ttu-id="c5f8f-116">トポロジ ビルダーがインストールされているコンピューターに、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="c5f8f-116">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="c5f8f-117">[ **Skype for business Server 2019**  >  **Enterprise Edition フロントエンドプール**] に到達するまでツリーを展開します。</span><span class="sxs-lookup"><span data-stu-id="c5f8f-117">Expand the tree until you reach **Skype for Business Server 2019** > **Enterprise Edition Front End pools**.</span></span>
    
3. <span data-ttu-id="c5f8f-118">[ **Enterprise Edition フロントエンドプール**] を右クリックし、[**新しいフロントエンドプール**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c5f8f-118">Right-click **Enterprise Edition Front End pools** and select **New Front End Pool**.</span></span>
  
4. <span data-ttu-id="c5f8f-119">プールの完全修飾ドメイン名 (FQDN) を入力します。</span><span class="sxs-lookup"><span data-stu-id="c5f8f-119">Enter the pool fully qualified domain name (FQDN).</span></span> <span data-ttu-id="c5f8f-120">パイロットプールを定義するときは、Enterprise Edition フロントエンドプールまたは Standard Edition サーバーを展開することを選択できます。</span><span class="sxs-lookup"><span data-stu-id="c5f8f-120">When you define your pilot pool, you can choose to deploy an Enterprise Edition Front End pool or a Standard Edition server.</span></span> <span data-ttu-id="c5f8f-121">Skype for Business Server 2019 では、パイロットプールの機能が従来のプールに展開されたものと一致している必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c5f8f-121">Skype for Business Server 2019 does not require that your pilot pool features match what was deployed in your legacy pool.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="c5f8f-122">パイロットプールに対して定義するプールまたはサーバーの FQDN は一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="c5f8f-122">The pool or server FQDN that you define for the pilot pool must be unique.</span></span> <span data-ttu-id="c5f8f-123">現在展開されている従来のプールの名前、または現在展開されている他のすべてのサーバーの名前と一致することはできません。</span><span class="sxs-lookup"><span data-stu-id="c5f8f-123">It cannot match the name of the currently deployed legacy pool or any other servers currently deployed.</span></span> 
  
5. <span data-ttu-id="c5f8f-124">**[機能の選択]** ページで、このフロント エンド プールで必要な機能のチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="c5f8f-124">On the **Select features** page, select the check boxes for the features that you want on this Front End pool.</span></span> <span data-ttu-id="c5f8f-125">たとえば、インスタントメッセージング (IM) とプレゼンス機能のみを展開する場合は、[会議] チェックボックスをオンにしてマルチパーティ IM を許可しますが、ダイヤルイン (PSTN) 会議、エンタープライズ Voip、または通話受付管理の各チェックボックスは、音声、ビデオ、および共同作業の会議機能を表すものであるため、選択しません。</span><span class="sxs-lookup"><span data-stu-id="c5f8f-125">For example, if you are deploying only instant messaging (IM) and presence features, you would select the Conferencing check box to allow multiparty IM, but you would not select the Dial-in (PSTN) conferencing, Enterprise Voice, or Call Admission Control check boxes, because they represent voice, video, and collaborative conferencing features.</span></span> <!-- For additional information on selecting features, see 
 [Define and configure a Front End pool or Standard Edition server in Skype for Business Server 2019](../deployment/deploying-lync-server-2013/define-and-configure-a-front-end-pool-or-standard-edition-server.md) in the Deployment documentation.  -->
  
6. <span data-ttu-id="c5f8f-126">[併置された**サーバーの役割の選択**] ページで、仲介サーバーを Skype For business server 2019 で併置することを選択することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c5f8f-126">On the **Select collocated server roles** page, we recommend that you choose to collocate the Mediation Server in Skype for Business Server 2019.</span></span> <span data-ttu-id="c5f8f-127">従来のトポロジを Skype for Business Server 2019 と統合する場合は、最初に従来の仲介サーバーを併置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c5f8f-127">When merging a legacy topology with Skype for Business Server 2019, we require that you first collocate the legacy Mediation Server.</span></span> <span data-ttu-id="c5f8f-128">トポロジをマージして、Skype for Business Server 2019 仲介サーバーを構成した後、展開プロセスで仲介サーバーの役割を Skype for Business Server 2019 に移動するときに、併置された仲介サーバーを保持するか、スタンドアロンサーバーに変更するかを決定することができます。</span><span class="sxs-lookup"><span data-stu-id="c5f8f-128">After merging the topologies and configuring the Skype for Business Server 2019 Mediation Server, you can decide whether to keep the collocated Mediation Server, or change it to a stand-alone server when you move the Mediation Server role to Skype for Business Server 2019 later in the deployment process.</span></span> 
   
7. <span data-ttu-id="c5f8f-129">[**サーバーの役割とこのフロントエンドプールの関連付け**] ページで、パイロットプールの展開時に [**このフロントエンドプールのメディアコンポーネントが使用するエッジプールを有効**にする] オプションを選択し*ません*。</span><span class="sxs-lookup"><span data-stu-id="c5f8f-129">On the **Associate server roles with this Front End pool** page, during pilot pool deployment, *do not* choose the **Enable an Edge pool to be used by the media component of this Front End pool** option.</span></span> <span data-ttu-id="c5f8f-130">これは、移行のフェーズが進んだ段階で有効にしてオンラインにする機能です。</span><span class="sxs-lookup"><span data-stu-id="c5f8f-130">This is a feature you will enable and bring online in a later phase of migration.</span></span> <span data-ttu-id="c5f8f-131">現時点ではこの設定はオフのままにしてください。</span><span class="sxs-lookup"><span data-stu-id="c5f8f-131">Keep this setting cleared for now.</span></span> 
  
8. <span data-ttu-id="c5f8f-132">[**Office Web Apps Server の選択**] ページで [**新規作成**] をクリックし、アプリケーション サーバーの FQDN を指定します。</span><span class="sxs-lookup"><span data-stu-id="c5f8f-132">On the **Select an Office Web Apps Server** page, click **New**, and specify the FQDN of the application server.</span></span>
  
9. <span data-ttu-id="c5f8f-133">[**アーカイブ Sql server ストアの定義**] ページで、skype For business Server のアーカイブと監視の両方のために sql server ストアを定義する場合は、前の手順で skype For business server 2019 用に作成した sql server インスタンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="c5f8f-133">On the **Define the Archiving SQL Server store** page, when defining the SQL Server store for both Skype for Business Server Archiving and Monitoring, select the SQL Server instance created earlier for Skype for Business Server 2019.</span></span> 
  
10. <span data-ttu-id="c5f8f-134">トポロジを公開するには、[ **Skype For Business Server** ] ノードを右クリックし、[**トポロジの公開**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c5f8f-134">To publish your topology, right-click the **Skype for Business Server** node, and then click **Publish Topology**.</span></span>
  
11. <span data-ttu-id="c5f8f-135">公開プロセスが完了したら、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c5f8f-135">When the publish process has completed, click **Finish**.</span></span>

12. <span data-ttu-id="c5f8f-136">「パイロットプールとレガシプールの共存を確認する」という名前の次のセクションに進む前に、「Skype for Business Server の新しいフロントエンドパイロットプールをインストールする必要があります。」で説明されている手順に従って、「[トポロジ内のサーバーに skype For Business server をインストール](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c5f8f-136">Before moving to the next section called "Verify pilot pool coexistence with legacy pool" you need to install the Skype for Business Server new Front End pilot pool we just defined in the published topology, follow the procedures outlined here [Install Skype for Business Server on servers in the topology](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server)</span></span>

13. <span data-ttu-id="c5f8f-137">前の手順が完了したら、次のセクションに移動して、従来のプールとパイロットプールが共存していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c5f8f-137">Once previous step is complete, move to the next section to Verify pilot pool coexistence with legacy pool.</span></span>
    
<!-- To install a local copy of the configuration store and start the required services, see 
[Setting up Front End Servers and Front End pools for Skype for Business Server 2019](../deployment/deploying-lync-server-2013/setting-up-front-end-servers-and-front-end-pools.md) in the Deployment documentation.  -->
  

