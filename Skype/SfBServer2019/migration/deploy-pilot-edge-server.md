---
title: パイロット エッジ サーバーを展開する
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
description: このトピックでは、Skype for Business Server 2019 エッジサーバーを展開する前に認識しておく必要がある構成設定について説明します。 Skype for Business Server 2019 の展開および構成プロセスは、Skype for business Server 2015 によく似ています。 このセクションで説明するのは、パイロット プールの展開の際に考慮が必要となる主なポイントのみです。 詳細な手順については、「展開」のドキュメントの「Deployment external user access in Skype for Business Server 2019」 (展開プロセスについて説明し、外部ユーザーアクセスの構成情報も提供します) を参照してください。
ms.openlocfilehash: 00c371b917f2649dba9011fbbce6162b153822d1
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752869"
---
# <a name="deploy-pilot-edge-server"></a><span data-ttu-id="3e724-106">パイロット エッジ サーバーを展開する</span><span class="sxs-lookup"><span data-stu-id="3e724-106">Deploy pilot Edge Server</span></span>

<span data-ttu-id="3e724-107">このトピックでは、Skype for Business Server 2019 エッジサーバーを展開する前に知っておく必要がある構成設定について説明します。</span><span class="sxs-lookup"><span data-stu-id="3e724-107">This topic highlights configuration settings you should be aware of before deploying your Skype for Business Server 2019 Edge Server.</span></span> <span data-ttu-id="3e724-108">Skype for Business Server 2019 の展開および構成プロセスは、Skype for business Server 2015 によく似ています。</span><span class="sxs-lookup"><span data-stu-id="3e724-108">The deployment and configuration processes for Skype for Business Server 2019 are very similar to Skype for Business Server 2015.</span></span> <span data-ttu-id="3e724-109">このセクションで説明するのは、パイロット プールの展開の際に考慮が必要となる主なポイントのみです。</span><span class="sxs-lookup"><span data-stu-id="3e724-109">This section only highlights key points you should consider as part of your pilot pool deployment.</span></span> <!-- For detailed steps, see 
 [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.  -->
  
<span data-ttu-id="3e724-p103">**新しいエッジ プールの定義**ウィザードでは、以下の手順に示すキー構成の設定を確認してください。ただし、**新しいエッジ プールの定義**ウィザードのごく一部のページのみが示されています。</span><span class="sxs-lookup"><span data-stu-id="3e724-p103">As you navigate through the **Define New Edge Pool** wizard, review the key configuration settings shown in the following steps. Note that only a few pages of the **Define New Edge Pool** wizard are shown.</span></span> 
  
### <a name="to-define-an-edge-pool"></a><span data-ttu-id="3e724-112">エッジプールを定義するには</span><span class="sxs-lookup"><span data-stu-id="3e724-112">To define an Edge Pool</span></span>

1. <span data-ttu-id="3e724-113">トポロジ ビルダーがインストールされているコンピューターに、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="3e724-113">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="3e724-114">[Skype for Business Server 2019 ノードに移動します。</span><span class="sxs-lookup"><span data-stu-id="3e724-114">Navigate to the Skype for Business Server 2019 node.</span></span> <span data-ttu-id="3e724-115">[**エッジ プール**] を右クリックし、[**新しいエッジ プール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e724-115">Right-click **Edge pools**, and click **New Edge pool**.</span></span>
    
     ![[新しいエッジプールの定義] ダイアログボックス](../media/migration_ocs_topo_edgepool_page1.JPG)
  
3. <span data-ttu-id="3e724-117">エッジ プールは、[**複数のコンピューター プール**] または [**単一コンピューター プール**] のどちらかになります。</span><span class="sxs-lookup"><span data-stu-id="3e724-117">An Edge pool can be a **Multiple computer pool** or **Single computer pool**.</span></span>
    
     ![[エッジプールの FQDN の定義] ダイアログボックス](../media/migration_ocs_topo_edgepool_page2.JPG)
  
4. <span data-ttu-id="3e724-119">[**機能の選択**] ページでは、フェデレーションまたは XMPP フェデレーションを有効にしないでください。</span><span class="sxs-lookup"><span data-stu-id="3e724-119">On the **Select features** page, do not enable federation or XMPP federation.</span></span> <span data-ttu-id="3e724-120">フェデレーションと XMPP フェデレーションは、現在、従来のエッジサーバーを経由してルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="3e724-120">Federation and XMPP federation are both currently routed through the legacy Edge Server.</span></span> <span data-ttu-id="3e724-121">この機能は、後ほど移行のフェーズで構成されます。</span><span class="sxs-lookup"><span data-stu-id="3e724-121">These features will be configured in a later phase of migration.</span></span> 

  
5. <span data-ttu-id="3e724-122">引き続き、[**外部 fqdn**]、[**内部 ip アドレスの定義**]、および [**外部 ip アドレスの定義**] の各ウィザードページを完了します。</span><span class="sxs-lookup"><span data-stu-id="3e724-122">Continue completing the following wizard pages: **External FQDNs**, **Define the internal IP address**, and **Define the external IP address**.</span></span>
    
6. <span data-ttu-id="3e724-123">[**次ホップサーバーの定義**] ページで、従来のエッジプールの次ホップのディレクターを選択します。</span><span class="sxs-lookup"><span data-stu-id="3e724-123">On the **Define the next hop server** page, select the Director for the next hop of the legacy Edge pool.</span></span> 
    
     ![[次ホップの定義] ダイアログボックス](../media/migration_ocs_topo_edgepool_page7.JPG)
  
7. <span data-ttu-id="3e724-125">[**フロントエンドまたは仲介プールの関連付け**] ページで、現時点ではプールをこのエッジプールに関連付けないでください。</span><span class="sxs-lookup"><span data-stu-id="3e724-125">On the **Associate Front End or Mediation pools** page, do not associate a pool with this Edge pool at this time.</span></span> <span data-ttu-id="3e724-126">外部メディアトラフィックは、現在、従来のエッジサーバーを経由してルーティングされています。</span><span class="sxs-lookup"><span data-stu-id="3e724-126">External media traffic is currently routed through the legacy Edge Server.</span></span> <span data-ttu-id="3e724-127">この設定は、後ほど移行のフェーズで構成されます。</span><span class="sxs-lookup"><span data-stu-id="3e724-127">This setting will be configured in a later phase of migration.</span></span> 
    
     ![[フロントエンドプールの関連付け] ダイアログボックス](../media/migration_ocs_topo_edgepool_page8.JPG)
  
8. <span data-ttu-id="3e724-129">[**完了**] をクリックしてトポロジを**公開**します。</span><span class="sxs-lookup"><span data-stu-id="3e724-129">Click **Finish**, and then **Publish** the topology.</span></span> 
    
9. <span data-ttu-id="3e724-130">「展開」のドキュメントの手順に従って、新しいエッジサーバーにファイルをインストールし、証明書を構成して、サービスを開始します。</span><span class="sxs-lookup"><span data-stu-id="3e724-130">Follow the steps in the Deployment documentation to install the files on the new Edge Server, configure certificates, and start the services.</span></span> 
<!-- [Install Edge Servers for Skype for Business Server 2019](../deployment/deploying-external-user-access/install-edge-servers.md) in -->
    
<span data-ttu-id="3e724-131">「展開」のドキュメントのトピックのガイドラインに従うことが非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="3e724-131">It's very important that you follow the guidelines in the topics in the Deployment documentation.</span></span> <span data-ttu-id="3e724-132">このセクションでは、これらのサーバーの役割をインストールする際の構成設定に関するガイドラインの一部を提供したにすぎません。</span><span class="sxs-lookup"><span data-stu-id="3e724-132">This section merely provided some guidance on configuration settings when installing these server roles.</span></span> 
<!-- [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) -->
  
<span data-ttu-id="3e724-133">これで、Skype for Business Server 2019 エッジサーバー展開と並行して展開された従来のエッジサーバーを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="3e724-133">You should now have a legacy Edge Server deployed in parallel with a Skype for Business Server 2019 Edge server deployment.</span></span> <span data-ttu-id="3e724-134">次のフェーズに進む前に、双方の展開が適切に動作していること、サービスが開始されていること、および各展開を管理できることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="3e724-134">Verify that both deployments are running properly, services are started, and you can administer each deployment prior to moving to the next phase.</span></span> 
  

