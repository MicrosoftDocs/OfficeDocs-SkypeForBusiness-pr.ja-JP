---
title: パイロットのエッジ サーバーを展開します。
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: このトピックでは、Skype をビジネス 2019 エッジ サーバーを展開する前に注意する必要があります構成の設定が強調表示されます。 ビジネス サーバー 2019 の Skype の展開と構成のプロセスは、ビジネス サーバー 2015 の Skype に非常に似ています。 のみ、このセクションには、パイロット プール展開の一環として検討する必要がある重要なポイントが強調表示されます。 詳細な手順を参照してください Skype で外部ユーザー アクセスを導入するビジネス サーバー 2019 の展開に関するドキュメントは、展開プロセスについて説明し、外部ユーザー アクセスの構成情報も示されます。
ms.openlocfilehash: 3ae1508c56ac3240cfb9904415090ff1bdf18677
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "25029861"
---
# <a name="deploy-pilot-edge-server"></a><span data-ttu-id="bf271-106">パイロットのエッジ サーバーを展開します。</span><span class="sxs-lookup"><span data-stu-id="bf271-106">Deploy pilot Edge Server</span></span>

<span data-ttu-id="bf271-107">このトピックでは、構成の設定をする必要があります、Skype をビジネス 2019 エッジ サーバーを展開する前に強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="bf271-107">This topic highlights configuration settings you should be aware of before deploying your Skype for Business Server 2019 Edge Server.</span></span> <span data-ttu-id="bf271-108">ビジネス サーバー 2019 の Skype の展開と構成のプロセスは、ビジネス サーバー 2015 の Skype に非常に似ています。</span><span class="sxs-lookup"><span data-stu-id="bf271-108">The deployment and configuration processes for Skype for Business Server 2019 are very similar to Skype for Business Server 2015.</span></span> <span data-ttu-id="bf271-109">のみ、このセクションには、パイロット プール展開の一環として検討する必要がある重要なポイントが強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="bf271-109">This section only highlights key points you should consider as part of your pilot pool deployment.</span></span> <!-- For detailed steps, see 
 [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.  -->
  
<span data-ttu-id="bf271-110">**新しいエッジ プールの定義**ウィザードを使って移動すると、次の手順に示すようにキーの構成設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="bf271-110">As you navigate through the **Define New Edge Pool** wizard, review the key configuration settings shown in the following steps.</span></span> <span data-ttu-id="bf271-111">**新しいエッジ プールの定義**ウィザードのいくつかのページのみが表示されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="bf271-111">Note that only a few pages of the **Define New Edge Pool** wizard are shown.</span></span> 
  
### <a name="to-define-an-edge-pool"></a><span data-ttu-id="bf271-112">エッジのプールを定義するのには</span><span class="sxs-lookup"><span data-stu-id="bf271-112">To define an Edge Pool</span></span>

1. <span data-ttu-id="bf271-113">トポロジ ビルダーがインストールされているコンピューターに、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="bf271-113">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="bf271-114">ビジネス サーバー 2019 ノードの Skype に移動します。</span><span class="sxs-lookup"><span data-stu-id="bf271-114">Navigate to the Skype for Business Server 2019 node.</span></span> <span data-ttu-id="bf271-115">**エッジ プール**を右クリックし、[**新しいエッジ プール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bf271-115">Right-click **Edge pools**, and click **New Edge pool**.</span></span>
    
     ![[新しいエッジ プール] ダイアログ ボックスを定義します。](../media/migration_ocs_topo_edgepool_page1.JPG)
  
3. <span data-ttu-id="bf271-117">エッジ プールは、**複数のコンピューター プール**または**1 台のコンピューターのプール**を使用できます。</span><span class="sxs-lookup"><span data-stu-id="bf271-117">An Edge pool can be a **Multiple computer pool** or **Single computer pool**.</span></span>
    
     ![エッジ プール FQDN] ダイアログ ボックスを定義します。](../media/migration_ocs_topo_edgepool_page2.JPG)
  
4. <span data-ttu-id="bf271-119">[**機能の選択**] ページで、有効にしないでフェデレーションまたは XMPP フェデレーション。</span><span class="sxs-lookup"><span data-stu-id="bf271-119">On the **Select features** page, do not enable federation or XMPP federation.</span></span> <span data-ttu-id="bf271-120">フェデレーションと XMPP フェデレーションは両方とも現在サーバー経由でルーティング レガシー エッジ。</span><span class="sxs-lookup"><span data-stu-id="bf271-120">Federation and XMPP federation are both currently routed through the legacy Edge Server.</span></span> <span data-ttu-id="bf271-121">これらの機能は、移行の以降のフェーズで構成されます。</span><span class="sxs-lookup"><span data-stu-id="bf271-121">These features will be configured in a later phase of migration.</span></span> 

  
5. <span data-ttu-id="bf271-122">完了ウィザード ページを続行:**外部 Fqdn**、**内部の IP アドレスの定義**、および**外部 IP アドレスを定義**します。</span><span class="sxs-lookup"><span data-stu-id="bf271-122">Continue completing the following wizard pages: **External FQDNs**, **Define the internal IP address**, and **Define the external IP address**.</span></span>
    
6. <span data-ttu-id="bf271-123">**次ホップのサーバーの定義**] ページで、従来のエッジ プールの次ホップのためにディレクターを選択します。</span><span class="sxs-lookup"><span data-stu-id="bf271-123">On the **Define the next hop server** page, select the Director for the next hop of the legacy Edge pool.</span></span> 
    
     ![次ホップ] ダイアログ ボックスを定義します。](../media/migration_ocs_topo_edgepool_page7.JPG)
  
7. <span data-ttu-id="bf271-125">**フロント エンドを関連付けるまたは仲介プール**] ページで、関連づけられていないプールこのエッジ プールをこの時点で。</span><span class="sxs-lookup"><span data-stu-id="bf271-125">On the **Associate Front End or Mediation pools** page, do not associate a pool with this Edge pool at this time.</span></span> <span data-ttu-id="bf271-126">外部メディア現在トラフィックが従来のエッジ サーバーを経由します。</span><span class="sxs-lookup"><span data-stu-id="bf271-126">External media traffic is currently routed through the legacy Edge Server.</span></span> <span data-ttu-id="bf271-127">この設定は、移行の以降のフェーズで構成されます。</span><span class="sxs-lookup"><span data-stu-id="bf271-127">This setting will be configured in a later phase of migration.</span></span> 
    
     ![関連付けるフロント エンド プール] ダイアログ ボックス](../media/migration_ocs_topo_edgepool_page8.JPG)
  
8. <span data-ttu-id="bf271-129">**完了**し、トポロジの**発行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bf271-129">Click **Finish**, and then **Publish** the topology.</span></span> 
    
9. <span data-ttu-id="bf271-130">新しいエッジ サーバー上のファイルをインストール、構成、証明書およびサービスを開始する導入マニュアルの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="bf271-130">Follow the steps in the Deployment documentation to install the files on the new Edge Server, configure certificates, and start the services.</span></span> 
<!-- [Install Edge Servers for Skype for Business Server 2019](../deployment/deploying-external-user-access/install-edge-servers.md) in -->
    
<span data-ttu-id="bf271-131">展開に関するドキュメントのトピックのガイドラインに従うことが非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="bf271-131">It's very important that you follow the guidelines in the topics in the Deployment documentation.</span></span> <span data-ttu-id="bf271-132">このセクションが表示されるだけのガイダンス構成の設定にこれらのサーバー ロールをインストールするとき。</span><span class="sxs-lookup"><span data-stu-id="bf271-132">This section merely provided some guidance on configuration settings when installing these server roles.</span></span> 
<!-- [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) -->
  
<span data-ttu-id="bf271-133">これで、Skype のビジネス サーバー 2019 エッジ サーバーの展開と並行して、展開、レガシ エッジ サーバーが必要です。</span><span class="sxs-lookup"><span data-stu-id="bf271-133">You should now have a legacy Edge Server deployed in parallel with a Skype for Business Server 2019 Edge server deployment.</span></span> <span data-ttu-id="bf271-134">確認両方の展開が正常に動作して、サービスが開始されると、次の段階に進む前にそれぞれの展開を管理することができます。</span><span class="sxs-lookup"><span data-stu-id="bf271-134">Verify that both deployments are running properly, services are started, and you can administer each deployment prior to moving to the next phase.</span></span> 
  

