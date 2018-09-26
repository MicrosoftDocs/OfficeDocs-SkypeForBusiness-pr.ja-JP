---
title: パイロット プールを展開します。
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: パイロット プールを展開するビジネス サーバー 2019 の Skype への移行に必要な最初の手順のいずれかです。 パイロットのプールとは、従来の展開とビジネス サーバー 2019 の Skype の共存をテストします。 共存とは、移動したすべてのユーザーとプール Skype のビジネス サーバー 2019 まで存続する一時的な状態です。
ms.openlocfilehash: 9a713a567d33121449ca83516bed35b574e0da01
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "25027852"
---
# <a name="deploy-skype-for-business-server-2019-pilot-pool"></a><span data-ttu-id="23f77-105">ビジネス サーバー 2019 パイロット プールに Skype を導入します。</span><span class="sxs-lookup"><span data-stu-id="23f77-105">Deploy Skype for Business Server 2019 pilot pool</span></span>

<span data-ttu-id="23f77-106">パイロット プールを展開するビジネス サーバー 2019 の Skype への移行に必要な最初の手順のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="23f77-106">One of the first steps required for migration to Skype for Business Server 2019 is to deploy a pilot pool.</span></span> <span data-ttu-id="23f77-107">パイロットのプールとは、従来の展開とビジネス サーバー 2019 の Skype の共存をテストします。</span><span class="sxs-lookup"><span data-stu-id="23f77-107">The pilot pool is where you test coexistence of Skype for Business Server 2019 with your legacy deployment.</span></span> <span data-ttu-id="23f77-108">共存とは、移動したすべてのユーザーとプール Skype のビジネス サーバー 2019 まで存続する一時的な状態です。</span><span class="sxs-lookup"><span data-stu-id="23f77-108">Coexistence is a temporary state that lasts until you have moved all users and pools to Skype for Business Server 2019.</span></span> 
  
<span data-ttu-id="23f77-109">パイロット プールを展開するときは、新しいフロント エンド プールの定義ウィザードを使用します。</span><span class="sxs-lookup"><span data-stu-id="23f77-109">When you deploy a pilot pool, you use the Define New Front End Pool wizard.</span></span> <span data-ttu-id="23f77-110">レガシ プール内にあるビジネス サーバー 2019 パイロット プールのため、Skype で同じ機能とワークロードを配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="23f77-110">You should deploy the same features and workloads in your Skype for Business Server 2019 pilot pool that you have in your legacy pool.</span></span> <span data-ttu-id="23f77-111">アーカイブや、従来の環境を監視するためのアーカイブ サーバー、監視サーバー、または System Center Operations Manager を展開して、アーカイブまたは移行中の監視を継続する場合もこれらの機能を配置する必要があります、パイロット環境です。</span><span class="sxs-lookup"><span data-stu-id="23f77-111">If you deployed Archiving Server, Monitoring Server, or System Center Operations Manager for archiving or monitoring your legacy environment, and you want to continue archiving or monitoring throughout the migration, you need to also deploy these features in your pilot environment.</span></span> <span data-ttu-id="23f77-112">アーカイブまたはレガシを監視するバージョンを展開した環境はサーバー 2019 のビジネス環境について、Skype でデータをキャプチャしていません。</span><span class="sxs-lookup"><span data-stu-id="23f77-112">The version you deployed to archive or monitor your legacy environment will not capture data in your Skype for Business Server 2019 environment.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="23f77-113">次の手順では、機能と、プールの全体的なパイロット展開プロセスの一部として考慮する必要があります設定について説明します。</span><span class="sxs-lookup"><span data-stu-id="23f77-113">The following procedure discusses features and settings you should consider as part of your overall pilot pool deployment process.</span></span> <span data-ttu-id="23f77-114">のみ、このセクションには、パイロット プール展開の一環として検討する必要がある重要なポイントが強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="23f77-114">This section only highlights key points you should consider as part of your pilot pool deployment.</span></span> <!-- For detailed steps, refer to the 
 [Deploying Skype for Business Server 2019](../deployment/deploying-lync-server-2013/deploying-lync-server-2013.md) deployment guide.  -->
  
### <a name="to-deploy-a-skype-for-business-server-2019-pilot-pool"></a><span data-ttu-id="23f77-115">Skype のビジネス サーバー 2019 パイロット プールを展開するには</span><span class="sxs-lookup"><span data-stu-id="23f77-115">To deploy a Skype for Business Server 2019 pilot pool</span></span>

1. <span data-ttu-id="23f77-116">トポロジ ビルダーがインストールされているコンピューターに、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="23f77-116">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="23f77-117">**ビジネス サーバー 2019 の Skype**に到達するまでツリーを展開し > **エンタープライズ エディションのフロント エンド プール**です。</span><span class="sxs-lookup"><span data-stu-id="23f77-117">Expand the tree until you reach **Skype for Business Server 2019** > **Enterprise Edition Front End pools**.</span></span>
    
3. <span data-ttu-id="23f77-118">**エンタープライズ エディションのフロント エンド プール**を右クリックし、**新しいフロント エンド プール**を選択します。</span><span class="sxs-lookup"><span data-stu-id="23f77-118">Right-click **Enterprise Edition Front End pools** and select **New Front End Pool**.</span></span>
  
4. <span data-ttu-id="23f77-119">プールの完全修飾ドメイン名 (FQDN) を入力します。</span><span class="sxs-lookup"><span data-stu-id="23f77-119">Enter the pool fully qualified domain name (FQDN).</span></span> <span data-ttu-id="23f77-120">パイロット プールを定義するとき、エンタープライズ エディションのフロント エンド プールまたは Standard Edition サーバーを展開することができます。</span><span class="sxs-lookup"><span data-stu-id="23f77-120">When you define your pilot pool, you can choose to deploy an Enterprise Edition Front End pool or a Standard Edition server.</span></span> <span data-ttu-id="23f77-121">ビジネス サーバー 2019 の Skype では、レガシ プールに展開するとどのようなパイロットのプールの機能に一致する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="23f77-121">Skype for Business Server 2019 does not require that your pilot pool features match what was deployed in your legacy pool.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="23f77-122">プールまたはサーバーの FQDN のパイロットのプールを定義することは、一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="23f77-122">The pool or server FQDN that you define for the pilot pool must be unique.</span></span> <span data-ttu-id="23f77-123">展開済みの従来のプールまたは現在展開されているその他のサーバーの名前に対応します。</span><span class="sxs-lookup"><span data-stu-id="23f77-123">It cannot match the name of the currently deployed legacy pool or any other servers currently deployed.</span></span> 
  
5. <span data-ttu-id="23f77-124">[**機能の選択**] ページで、このフロント エンド プールで必要な機能のチェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="23f77-124">On the **Select features** page, select the check boxes for the features that you want on this Front End pool.</span></span> <span data-ttu-id="23f77-125">インスタント メッセージング (IM) とプレゼンスの機能のみを配置する場合は、マルチパーティ IM を許可するのには、[会議] チェック ボックスを選択ですが、ダイヤルイン (PSTN) 会議、エンタープライズ VoIP を選択しないなど、受付制御の呼び出しをチェックボックス、音声、ビデオ、および共同作業の会議機能を表しているためです。</span><span class="sxs-lookup"><span data-stu-id="23f77-125">For example, if you are deploying only instant messaging (IM) and presence features, you would select the Conferencing check box to allow multiparty IM, but you would not select the Dial-in (PSTN) conferencing, Enterprise Voice, or Call Admission Control check boxes, because they represent voice, video, and collaborative conferencing features.</span></span> <!-- For additional information on selecting features, see 
 [Define and configure a Front End pool or Standard Edition server in Skype for Business Server 2019](../deployment/deploying-lync-server-2013/define-and-configure-a-front-end-pool-or-standard-edition-server.md) in the Deployment documentation.  -->
  
6. <span data-ttu-id="23f77-126">**ロールの配置されているサーバーの選択]** ページで、ビジネス サーバー 2019 の Skype に仲介サーバーを連結するように選択することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="23f77-126">On the **Select collocated server roles** page, we recommend that you choose to collocate the Mediation Server in Skype for Business Server 2019.</span></span> <span data-ttu-id="23f77-127">ビジネス サーバー 2019 の Skype での従来のトポロジをマージするときに最初に従来の仲介サーバーに集約するが必要です。</span><span class="sxs-lookup"><span data-stu-id="23f77-127">When merging a legacy topology with Skype for Business Server 2019, we require that you first collocate the legacy Mediation Server.</span></span> <span data-ttu-id="23f77-128">トポロジをマージすると、Skype のビジネス 2019 仲介サーバーの構成、配置されている仲介サーバーを維持または Skype をビジネスのサーバーの仲介サーバーの役割を移動するときは、スタンドアロンのサーバーに変更するかどうか決定できます。展開プロセスの後半で 2019。</span><span class="sxs-lookup"><span data-stu-id="23f77-128">After merging the topologies and configuring the Skype for Business Server 2019 Mediation Server, you can decide whether to keep the collocated Mediation Server, or change it to a stand-alone server when you move the Mediation Server role to Skype for Business Server 2019 later in the deployment process.</span></span> 
   
7. <span data-ttu-id="23f77-129">**このフロント エンド プールを使用してサーバー ロールの関連付け**] ページで、パイロットのプールの展開中にしない] を選択\*して\*\*このフロント エンド プールのメディア コンポーネントで使用する、エッジのプールを有効にします\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="23f77-129">On the **Associate server roles with this Front End pool** page, during pilot pool deployment, *do not* choose the **Enable an Edge pool to be used by the media component of this Front End pool** option.</span></span> <span data-ttu-id="23f77-130">これは、機能を有効にしてオンラインに移行の後の段階でです。</span><span class="sxs-lookup"><span data-stu-id="23f77-130">This is a feature you will enable and bring online in a later phase of migration.</span></span> <span data-ttu-id="23f77-131">この設定はオフになって今のところを保持します。</span><span class="sxs-lookup"><span data-stu-id="23f77-131">Keep this setting cleared for now.</span></span> 
  
8. <span data-ttu-id="23f77-132">**Office Web アプリケーション サーバーの選択**] ページで [**新規**作成] をクリックし、アプリケーション サーバーの FQDN を指定します。</span><span class="sxs-lookup"><span data-stu-id="23f77-132">On the **Select an Office Web Apps Server** page, click **New**, and specify the FQDN of the application server.</span></span>
  
9. <span data-ttu-id="23f77-133">**定義する SQL Server のアーカイブ ストア**] ページで、ビジネス ・ サーバのアーカイブと監視の両方の Skype の SQL Server ストアを定義するときに、ビジネス サーバー 2019 の Skype の前に作成する SQL Server のインスタンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="23f77-133">On the **Define the Archiving SQL Server store** page, when defining the SQL Server store for both Skype for Business Server Archiving and Monitoring, select the SQL Server instance created earlier for Skype for Business Server 2019.</span></span> 
  
10. <span data-ttu-id="23f77-134">トポロジを公開、 **Skype**ビジネス サーバーのノードを右クリックし、**トポロジの公開**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="23f77-134">To publish your topology, right-click the **Skype for Business Server** node, and then click **Publish Topology**.</span></span>
  
11. <span data-ttu-id="23f77-135">発行プロセスが完了したら、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="23f77-135">When the publish process has completed, click **Finish**.</span></span>
    
<!-- To install a local copy of the configuration store and start the required services, see 
[Setting up Front End Servers and Front End pools for Skype for Business Server 2019](../deployment/deploying-lync-server-2013/setting-up-front-end-servers-and-front-end-pools.md) in the Deployment documentation.  -->
  

