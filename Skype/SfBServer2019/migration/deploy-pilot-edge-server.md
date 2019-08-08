---
title: パイロット エッジ サーバーの展開
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: このトピックでは、Skype for Business Server 2019 Edge サーバーを展開する前に知っておく必要がある構成設定について説明します。 Skype for Business Server 2019 の展開と構成のプロセスは、Skype for Business Server 2015 とよく似ています。 このセクションでは、パイロットプールの展開の一部として考慮する必要がある重要なポイントについて説明します。 詳細な手順については、展開プロセスについて説明し、外部ユーザーアクセスの構成情報も提供する展開ドキュメントで、「Skype for Business Server 2019 への外部ユーザーアクセスの展開」を参照してください。
ms.openlocfilehash: b416ba38646d05f3d10a7d2643c01924fe57020a
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36238389"
---
# <a name="deploy-pilot-edge-server"></a><span data-ttu-id="8aa3c-106">パイロット エッジ サーバーの展開</span><span class="sxs-lookup"><span data-stu-id="8aa3c-106">Deploy pilot Edge Server</span></span>

<span data-ttu-id="8aa3c-107">このトピックでは、Skype for Business Server 2019 エッジサーバーを展開する前に知っておく必要がある構成設定について説明します。</span><span class="sxs-lookup"><span data-stu-id="8aa3c-107">This topic highlights configuration settings you should be aware of before deploying your Skype for Business Server 2019 Edge Server.</span></span> <span data-ttu-id="8aa3c-108">Skype for Business Server 2019 の展開と構成のプロセスは、Skype for Business Server 2015 とよく似ています。</span><span class="sxs-lookup"><span data-stu-id="8aa3c-108">The deployment and configuration processes for Skype for Business Server 2019 are very similar to Skype for Business Server 2015.</span></span> <span data-ttu-id="8aa3c-109">このセクションでは、パイロットプールの展開の一部として考慮する必要がある重要なポイントについて説明します。</span><span class="sxs-lookup"><span data-stu-id="8aa3c-109">This section only highlights key points you should consider as part of your pilot pool deployment.</span></span> <!-- For detailed steps, see 
 [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.  -->
  
<span data-ttu-id="8aa3c-110">[**新しいエッジプールの定義**] ウィザードを実行するときに、次の手順に示されているキー構成の設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="8aa3c-110">As you navigate through the **Define New Edge Pool** wizard, review the key configuration settings shown in the following steps.</span></span> <span data-ttu-id="8aa3c-111">[**新しいエッジプールの定義**] ウィザードの一部のページのみが表示されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="8aa3c-111">Note that only a few pages of the **Define New Edge Pool** wizard are shown.</span></span> 
  
### <a name="to-define-an-edge-pool"></a><span data-ttu-id="8aa3c-112">エッジプールを定義するには</span><span class="sxs-lookup"><span data-stu-id="8aa3c-112">To define an Edge Pool</span></span>

1. <span data-ttu-id="8aa3c-113">トポロジ ビルダーがインストールされているコンピューターに、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="8aa3c-113">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="8aa3c-114">Skype for Business Server 2019 ノードに移動します。</span><span class="sxs-lookup"><span data-stu-id="8aa3c-114">Navigate to the Skype for Business Server 2019 node.</span></span> <span data-ttu-id="8aa3c-115">[**エッジプール**] を右クリックし、[**新しいエッジプール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8aa3c-115">Right-click **Edge pools**, and click **New Edge pool**.</span></span>
    
     ![[新しいエッジプールの定義] ダイアログボックス](../media/migration_ocs_topo_edgepool_page1.JPG)
  
3. <span data-ttu-id="8aa3c-117">エッジプールには、**複数のコンピュータプール**または**単一のコンピュータプール**を使用できます。</span><span class="sxs-lookup"><span data-stu-id="8aa3c-117">An Edge pool can be a **Multiple computer pool** or **Single computer pool**.</span></span>
    
     ![エッジプールの FQDN ダイアログボックスの定義](../media/migration_ocs_topo_edgepool_page2.JPG)
  
4. <span data-ttu-id="8aa3c-119">**[機能の選択**] ページで、フェデレーションまたは xmpp フェデレーションを有効にしないようにします。</span><span class="sxs-lookup"><span data-stu-id="8aa3c-119">On the **Select features** page, do not enable federation or XMPP federation.</span></span> <span data-ttu-id="8aa3c-120">フェデレーションと XMPP フェデレーションは、現在、従来のエッジサーバーを介してルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="8aa3c-120">Federation and XMPP federation are both currently routed through the legacy Edge Server.</span></span> <span data-ttu-id="8aa3c-121">これらの機能は、移行の後のフェーズで構成されます。</span><span class="sxs-lookup"><span data-stu-id="8aa3c-121">These features will be configured in a later phase of migration.</span></span> 

  
5. <span data-ttu-id="8aa3c-122">次のウィザードページに進んでください。**外部 fqdn**、**内部 ip アドレスの定義**、**外部 ip アドレスの定義**を続行します。</span><span class="sxs-lookup"><span data-stu-id="8aa3c-122">Continue completing the following wizard pages: **External FQDNs**, **Define the internal IP address**, and **Define the external IP address**.</span></span>
    
6. <span data-ttu-id="8aa3c-123">[ **Next ホップサーバーの定義**] ページで、従来の Edge プールの次ホップのディレクターを選択します。</span><span class="sxs-lookup"><span data-stu-id="8aa3c-123">On the **Define the next hop server** page, select the Director for the next hop of the legacy Edge pool.</span></span> 
    
     ![[次ホップの定義] ダイアログボックス](../media/migration_ocs_topo_edgepool_page7.JPG)
  
7. <span data-ttu-id="8aa3c-125">[**フロントエンドまたは仲介プールの関連付け**] ページで、この時点ではプールをこのエッジプールに関連付けないでください。</span><span class="sxs-lookup"><span data-stu-id="8aa3c-125">On the **Associate Front End or Mediation pools** page, do not associate a pool with this Edge pool at this time.</span></span> <span data-ttu-id="8aa3c-126">外部メディアトラフィックは、現在、従来のエッジサーバーを介してルーティングされています。</span><span class="sxs-lookup"><span data-stu-id="8aa3c-126">External media traffic is currently routed through the legacy Edge Server.</span></span> <span data-ttu-id="8aa3c-127">この設定は、移行の後のフェーズで構成されます。</span><span class="sxs-lookup"><span data-stu-id="8aa3c-127">This setting will be configured in a later phase of migration.</span></span> 
    
     ![[フロントエンドプールの関連付け] ダイアログボックス](../media/migration_ocs_topo_edgepool_page8.JPG)
  
8. <span data-ttu-id="8aa3c-129">[**完了**] をクリックして、トポロジを**公開**します。</span><span class="sxs-lookup"><span data-stu-id="8aa3c-129">Click **Finish**, and then **Publish** the topology.</span></span> 
    
9. <span data-ttu-id="8aa3c-130">展開ドキュメントの手順に従って、新しいエッジサーバーにファイルをインストールし、証明書を構成して、サービスを開始します。</span><span class="sxs-lookup"><span data-stu-id="8aa3c-130">Follow the steps in the Deployment documentation to install the files on the new Edge Server, configure certificates, and start the services.</span></span> 
<!-- [Install Edge Servers for Skype for Business Server 2019](../deployment/deploying-external-user-access/install-edge-servers.md) in -->
    
<span data-ttu-id="8aa3c-131">展開ドキュメントのトピックのガイドラインに従うことが非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="8aa3c-131">It's very important that you follow the guidelines in the topics in the Deployment documentation.</span></span> <span data-ttu-id="8aa3c-132">このセクションでは、これらのサーバーの役割をインストールするときの構成設定について、いくつかのガイダンスを示しました。</span><span class="sxs-lookup"><span data-stu-id="8aa3c-132">This section merely provided some guidance on configuration settings when installing these server roles.</span></span> 
<!-- [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) -->
  
<span data-ttu-id="8aa3c-133">これで、Skype for Business Server 2019 Edge server の展開と並行してレガシエッジサーバーを展開することができます。</span><span class="sxs-lookup"><span data-stu-id="8aa3c-133">You should now have a legacy Edge Server deployed in parallel with a Skype for Business Server 2019 Edge server deployment.</span></span> <span data-ttu-id="8aa3c-134">両方の展開が適切に実行されていることを確認し、サービスが開始されていることを確認します。次のフェーズに移行する前に、各展開を管理することができます。</span><span class="sxs-lookup"><span data-stu-id="8aa3c-134">Verify that both deployments are running properly, services are started, and you can administer each deployment prior to moving to the next phase.</span></span> 
  

