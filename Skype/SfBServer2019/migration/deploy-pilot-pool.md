---
title: パイロット プールの展開
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype for Business Server 2019 への移行に必要な最初の手順の1つは、パイロットプールを展開することです。 パイロットプールでは、Skype for Business Server 2019 と従来の展開を共存させることができます。 [共存] は、すべてのユーザーとプールを Skype for Business Server 2019 に移動するまで継続して使用できます。
ms.openlocfilehash: dc0e5b984aaa9ed931f3937b253fbe40aef9b051
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36238382"
---
# <a name="deploy-skype-for-business-server-2019-pilot-pool"></a><span data-ttu-id="df19b-105">Skype for Business Server 2019 パイロットプールの展開</span><span class="sxs-lookup"><span data-stu-id="df19b-105">Deploy Skype for Business Server 2019 pilot pool</span></span>

<span data-ttu-id="df19b-106">Skype for Business Server 2019 への移行に必要な最初の手順の1つは、パイロットプールを展開することです。</span><span class="sxs-lookup"><span data-stu-id="df19b-106">One of the first steps required for migration to Skype for Business Server 2019 is to deploy a pilot pool.</span></span> <span data-ttu-id="df19b-107">パイロットプールでは、Skype for Business Server 2019 と従来の展開を共存させることができます。</span><span class="sxs-lookup"><span data-stu-id="df19b-107">The pilot pool is where you test coexistence of Skype for Business Server 2019 with your legacy deployment.</span></span> <span data-ttu-id="df19b-108">[共存] は、すべてのユーザーとプールを Skype for Business Server 2019 に移動するまで継続して使用できます。</span><span class="sxs-lookup"><span data-stu-id="df19b-108">Coexistence is a temporary state that lasts until you have moved all users and pools to Skype for Business Server 2019.</span></span> 
  
<span data-ttu-id="df19b-109">パイロットプールを展開する場合は、[新しいフロントエンドプールの定義] ウィザードを使います。</span><span class="sxs-lookup"><span data-stu-id="df19b-109">When you deploy a pilot pool, you use the Define New Front End Pool wizard.</span></span> <span data-ttu-id="df19b-110">Skype for Business Server 2019 パイロットプールで、従来のプールにあるものと同じ機能とワークロードを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="df19b-110">You should deploy the same features and workloads in your Skype for Business Server 2019 pilot pool that you have in your legacy pool.</span></span> <span data-ttu-id="df19b-111">アーカイブサーバー、監視サーバー、または System Center Operations Manager を展開して従来の環境をアーカイブまたは監視する場合、移行後もアーカイブまたは監視を継続するには、次の機能もに展開する必要があります。パイロット環境。</span><span class="sxs-lookup"><span data-stu-id="df19b-111">If you deployed Archiving Server, Monitoring Server, or System Center Operations Manager for archiving or monitoring your legacy environment, and you want to continue archiving or monitoring throughout the migration, you need to also deploy these features in your pilot environment.</span></span> <span data-ttu-id="df19b-112">従来の環境をアーカイブまたは監視するために展開したバージョンでは、Skype for Business Server 2019 環境のデータは取得されません。</span><span class="sxs-lookup"><span data-stu-id="df19b-112">The version you deployed to archive or monitor your legacy environment will not capture data in your Skype for Business Server 2019 environment.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="df19b-113">次の手順では、パイロットプールの全体的な展開プロセスの一部として考慮する必要がある機能と設定について説明します。</span><span class="sxs-lookup"><span data-stu-id="df19b-113">The following procedure discusses features and settings you should consider as part of your overall pilot pool deployment process.</span></span> <span data-ttu-id="df19b-114">このセクションでは、パイロットプールの展開の一部として考慮する必要がある重要なポイントについて説明します。</span><span class="sxs-lookup"><span data-stu-id="df19b-114">This section only highlights key points you should consider as part of your pilot pool deployment.</span></span> <!-- For detailed steps, refer to the 
 [Deploying Skype for Business Server 2019](../deployment/deploying-lync-server-2013/deploying-lync-server-2013.md) deployment guide.  -->
  
### <a name="to-deploy-a-skype-for-business-server-2019-pilot-pool"></a><span data-ttu-id="df19b-115">Skype for Business Server 2019 パイロットプールを展開するには</span><span class="sxs-lookup"><span data-stu-id="df19b-115">To deploy a Skype for Business Server 2019 pilot pool</span></span>

1. <span data-ttu-id="df19b-116">トポロジ ビルダーがインストールされているコンピューターに、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="df19b-116">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="df19b-117">**Skype for business Server 2019** > **Enterprise Edition のフロントエンドプール**に到達するまでツリーを展開します。</span><span class="sxs-lookup"><span data-stu-id="df19b-117">Expand the tree until you reach **Skype for Business Server 2019** > **Enterprise Edition Front End pools**.</span></span>
    
3. <span data-ttu-id="df19b-118">**Enterprise Edition のフロントエンドプール**を右クリックし、[**新しいフロントエンドプール**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="df19b-118">Right-click **Enterprise Edition Front End pools** and select **New Front End Pool**.</span></span>
  
4. <span data-ttu-id="df19b-119">プールの完全修飾ドメイン名 (FQDN) を入力します。</span><span class="sxs-lookup"><span data-stu-id="df19b-119">Enter the pool fully qualified domain name (FQDN).</span></span> <span data-ttu-id="df19b-120">パイロットプールを定義する場合は、Enterprise Edition のフロントエンドプールまたは Standard Edition サーバーを展開することを選択できます。</span><span class="sxs-lookup"><span data-stu-id="df19b-120">When you define your pilot pool, you can choose to deploy an Enterprise Edition Front End pool or a Standard Edition server.</span></span> <span data-ttu-id="df19b-121">Skype for Business Server 2019 では、パイロットプールの機能が、従来のプールに展開されたものと一致する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="df19b-121">Skype for Business Server 2019 does not require that your pilot pool features match what was deployed in your legacy pool.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="df19b-122">パイロットプールに対して定義するプールまたはサーバーの FQDN は一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="df19b-122">The pool or server FQDN that you define for the pilot pool must be unique.</span></span> <span data-ttu-id="df19b-123">現在展開されているレガシープールまたは現在展開されている他のサーバーの名前と一致させることはできません。</span><span class="sxs-lookup"><span data-stu-id="df19b-123">It cannot match the name of the currently deployed legacy pool or any other servers currently deployed.</span></span> 
  
5. <span data-ttu-id="df19b-124">**[機能の選択**] ページで、このフロントエンドプールに必要な機能のチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="df19b-124">On the **Select features** page, select the check boxes for the features that you want on this Front End pool.</span></span> <span data-ttu-id="df19b-125">たとえば、インスタントメッセージング (IM) とプレゼンス機能のみを展開している場合、[会議] チェックボックスをオンにして、マルチパーティ IM を許可しますが、ダイヤルイン (PSTN) 会議、エンタープライズボイス、または通話受付制御のチェックを選択することはできません。ボックス。音声、ビデオ、および共同作業の会議機能を表します。</span><span class="sxs-lookup"><span data-stu-id="df19b-125">For example, if you are deploying only instant messaging (IM) and presence features, you would select the Conferencing check box to allow multiparty IM, but you would not select the Dial-in (PSTN) conferencing, Enterprise Voice, or Call Admission Control check boxes, because they represent voice, video, and collaborative conferencing features.</span></span> <!-- For additional information on selecting features, see 
 [Define and configure a Front End pool or Standard Edition server in Skype for Business Server 2019](../deployment/deploying-lync-server-2013/define-and-configure-a-front-end-pool-or-standard-edition-server.md) in the Deployment documentation.  -->
  
6. <span data-ttu-id="df19b-126">**[併置**されたサーバーの役割の選択] ページで、Skype For business server 2019 で仲介サーバーを検索することを選択することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="df19b-126">On the **Select collocated server roles** page, we recommend that you choose to collocate the Mediation Server in Skype for Business Server 2019.</span></span> <span data-ttu-id="df19b-127">Skype for Business Server 2019 で従来のトポロジを統合する場合、最初に従来の仲介サーバーを検索する必要があります。</span><span class="sxs-lookup"><span data-stu-id="df19b-127">When merging a legacy topology with Skype for Business Server 2019, we require that you first collocate the legacy Mediation Server.</span></span> <span data-ttu-id="df19b-128">トポロジをマージして、Skype for Business Server 2019 仲介サーバーを構成した後、仲介サーバーの役割を Skype for Business Server に移行するときに、併置された仲介サーバーを保持するか、スタンドアロンサーバーに変更するかを決定することができます。2019は、展開プロセスで後で実行します。</span><span class="sxs-lookup"><span data-stu-id="df19b-128">After merging the topologies and configuring the Skype for Business Server 2019 Mediation Server, you can decide whether to keep the collocated Mediation Server, or change it to a stand-alone server when you move the Mediation Server role to Skype for Business Server 2019 later in the deployment process.</span></span> 
   
7. <span data-ttu-id="df19b-129">パイロットプールの展開中に、[**サーバーの役割をこのフロントエンドプールに関連付ける**] ページで、[**このフロントエンドプールのメディアコンポーネントで使用するエッジプールを有効**にする] オプションを選択しないで*ください*。</span><span class="sxs-lookup"><span data-stu-id="df19b-129">On the **Associate server roles with this Front End pool** page, during pilot pool deployment, *do not* choose the **Enable an Edge pool to be used by the media component of this Front End pool** option.</span></span> <span data-ttu-id="df19b-130">これは、移行の後のフェーズで有効にしてオンラインにする機能です。</span><span class="sxs-lookup"><span data-stu-id="df19b-130">This is a feature you will enable and bring online in a later phase of migration.</span></span> <span data-ttu-id="df19b-131">ここでは、この設定をオフのままにしておきます。</span><span class="sxs-lookup"><span data-stu-id="df19b-131">Keep this setting cleared for now.</span></span> 
  
8. <span data-ttu-id="df19b-132">[ **Office Web Apps サーバーを選択**してください] ページで、[**新規**] をクリックし、アプリケーションサーバーの FQDN を指定します。</span><span class="sxs-lookup"><span data-stu-id="df19b-132">On the **Select an Office Web Apps Server** page, click **New**, and specify the FQDN of the application server.</span></span>
  
9. <span data-ttu-id="df19b-133">[**アーカイブ SQL server ストアの定義**] ページで、skype For business Server のアーカイブと監視の両方のために sql server ストアを定義する場合は、以前に skype For business server 2019 用に作成した sql server インスタンスを選びます。</span><span class="sxs-lookup"><span data-stu-id="df19b-133">On the **Define the Archiving SQL Server store** page, when defining the SQL Server store for both Skype for Business Server Archiving and Monitoring, select the SQL Server instance created earlier for Skype for Business Server 2019.</span></span> 
  
10. <span data-ttu-id="df19b-134">トポロジを公開するには、[ **Skype For Business Server** ] ノードを右クリックし、[**トポロジの公開**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="df19b-134">To publish your topology, right-click the **Skype for Business Server** node, and then click **Publish Topology**.</span></span>
  
11. <span data-ttu-id="df19b-135">発行プロセスが完了したら、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="df19b-135">When the publish process has completed, click **Finish**.</span></span>

12. <span data-ttu-id="df19b-136">"パイロットプールとレガシプールを共存させる" という名前の次のセクションに移動する前に、「Skype for Business Server」で説明している手順に従って、「Skype for business をインストールする」を参照してください。 [トポロジ内のサーバー上のビジネスサーバー](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server)</span><span class="sxs-lookup"><span data-stu-id="df19b-136">Before moving to the next section called "Verify pilot pool coexistence with legacy pool" you need to install the Skype for Business Server new Front End pilot pool we just defined in the published topology, follow the procedures outlined here [Install Skype for Business Server on servers in the topology](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server)</span></span>

13. <span data-ttu-id="df19b-137">前の手順が完了したら、次のセクションに進んで、パイロットプールとレガシプールを共存させることができます。</span><span class="sxs-lookup"><span data-stu-id="df19b-137">Once previous step is complete, move to the next section to Verify pilot pool coexistence with legacy pool.</span></span>
    
<!-- To install a local copy of the configuration store and start the required services, see 
[Setting up Front End Servers and Front End pools for Skype for Business Server 2019](../deployment/deploying-lync-server-2013/setting-up-front-end-servers-and-front-end-pools.md) in the Deployment documentation.  -->
  

