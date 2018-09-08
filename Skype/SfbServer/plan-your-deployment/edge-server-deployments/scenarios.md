---
title: Skype のビジネス サーバーのサーバーのシナリオをエッジします。
ms.author: heidip
author: microsoftheidi
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 7b9c211b-deb0-479d-b184-973f08b96d07
description: '概要: ビジネス サーバーの Skype で、エッジ サーバーのトポロジを計画するためのこれらのシナリオを確認します。'
ms.openlocfilehash: 6343c69c493992656b17aaadb5e1450baec85560
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23885181"
---
# <a name="edge-server-scenarios-in-skype-for-business-server"></a><span data-ttu-id="f36ea-103">Skype のビジネス サーバーのサーバーのシナリオをエッジします。</span><span class="sxs-lookup"><span data-stu-id="f36ea-103">Edge Server scenarios in Skype for Business Server</span></span>
 
<span data-ttu-id="f36ea-104">**の概要:** ビジネス サーバーの Skype で、エッジ サーバーのトポロジを計画するためのこれらのシナリオを確認します。</span><span class="sxs-lookup"><span data-stu-id="f36ea-104">**Summary:** Review these scenarios to help you plan your Edge Server topology in Skype for Business Server.</span></span>
  
<span data-ttu-id="f36ea-105">視覚化して、ビジネス エッジ サーバーのトポロジを実装するためには、どのような Skype の決定を支援するいくつかのシナリオの図があります。</span><span class="sxs-lookup"><span data-stu-id="f36ea-105">We have some scenarios diagrams to assist with visualizing and deciding on what Skype for Business Server Edge Server topology you want to implement.</span></span> <span data-ttu-id="f36ea-106">適切な候補を選択すれば、対処する必要がある環境の要件を調査できます。</span><span class="sxs-lookup"><span data-stu-id="f36ea-106">Once you've picked a good candidate, you can go read up on the environmental requirements you'll need to address.</span></span> <span data-ttu-id="f36ea-107">次に示す図はすべてのシナリオに適用されるため、最初に説明します。</span><span class="sxs-lookup"><span data-stu-id="f36ea-107">The following is applicable to any of the scenarios, so we're mentioning it first.</span></span>
  
<span data-ttu-id="f36ea-p102">以下の図は例示のみを目的として示されている (つまり、サンプルの IPv4 および IPv6 データが含まれている) ため、実際の通信の流れではなく、可能なトラフィックの概要を表しています。ポートの詳細は、以下の各シナリオのポートの図でも確認できます。</span><span class="sxs-lookup"><span data-stu-id="f36ea-p102">These figures, which are shown for example purposes only (and as such contains sample IPv4 and IPv6 data), don't represent the actual communication flow, but rather a high-level view of your possible traffic. Port details can also be seen in the Port diagrams for each scenario below.</span></span>
  
<span data-ttu-id="f36ea-110">図に示す .com は外部インターフェイス用で、.net は内部インターフェイス用ですが、これらもサンプル情報です。もちろん、最終的なエッジの計画を策定する際には、独自のエントリはまったく異なるものである可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f36ea-110">The diagrams show .com for the external interface and .net for the internal, which is also sample material; of course your own entries may be quite different when you're putting together your own final Edge plan.</span></span>
  
<span data-ttu-id="f36ea-111">ダイアグラムのいずれかのダイレクタは、省略可能なコンポーネント) を含めません。 ですが、これについて個別に読み取ることができます (これは、他の計画のトピックに記載されて)。</span><span class="sxs-lookup"><span data-stu-id="f36ea-111">We don't include the Director (which is an optional component) in any of the diagrams, but you can read about that separately (it's mentioned in other Planning topics).</span></span>
  
<span data-ttu-id="f36ea-112">前述したように、IPv6 のサンプル データには、図です。</span><span class="sxs-lookup"><span data-stu-id="f36ea-112">As noted above, there is sample IPv6 data in the diagrams.</span></span> <span data-ttu-id="f36ea-113">[Skype ビジネス サーバー用にエッジ サーバーの展開計画](edge-server-deployments.md)のドキュメントのほとんどは、IPv4 を参照してください。 ですが、IPv6 を使用する場合に確実にサポートされています。</span><span class="sxs-lookup"><span data-stu-id="f36ea-113">Most of the documentation in [Plan for Edge Server deployments in Skype for Business Server](edge-server-deployments.md) will refer to IPv4, but you are certainly supported if you want to use IPv6.</span></span> <span data-ttu-id="f36ea-114">割り当てられたアドレス空間内の IPv6 アドレスを必要があり、IPv4 の ip アドレスと内部と外部のアドレスを使用する必要があります、ことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="f36ea-114">Note that you'll need IPv6 addresses in your assigned address space, and they'll need to work with internal and external addressing, as with IPv4 IPs.</span></span> <span data-ttu-id="f36ea-115">、、Windows のおかげで使用できるデュアル ・ スタック機能は、IPv4 と IPv6 のとは別のネットワーク スタックします。</span><span class="sxs-lookup"><span data-stu-id="f36ea-115">You can, thanks to Windows, employ the dual stack feature, which is a separate and distinct network stack for IPv4 and IPv6.</span></span> <span data-ttu-id="f36ea-116">これはする必要がある場合、IPv4 を割り当てるには、IPv6 のアドレスを同時にします。</span><span class="sxs-lookup"><span data-stu-id="f36ea-116">This will, if you need, allow you to assign IPv4 and IPv6 addresses concurrently.</span></span>
  
<span data-ttu-id="f36ea-117">NAT64 を許可する NAT デバイス (IPv4 を IPv6) と NAT66 (ipv6 IPv6))、これは、Skype のビジネス サーバーで使用するために有効なと。</span><span class="sxs-lookup"><span data-stu-id="f36ea-117">There are NAT devices that allow for NAT64 (IPv6 to IPv4) and NAT66 (IPv6 to IPv6)), and this is valid for use with Skype for Business Server.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="f36ea-118">通話受付管理 (CAC) を使用している場合、CAC が機能するためには、内部インターフェイスで IPv4 を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f36ea-118">If you're using Call Admission Control (CAC) you do have to use IPv4 on the internal interface for it to work.</span></span> 
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-private-ip-addresses-and-nat"></a><span data-ttu-id="f36ea-119">シングルは、ビジネス エッジ サーバーのプライベート IP アドレスと NAT で Skype を統合します。</span><span class="sxs-lookup"><span data-stu-id="f36ea-119">Single consolidated Skype for Business Server Edge Server with private IP addresses and NAT</span></span>

<span data-ttu-id="f36ea-p104">このシナリオでは、高可用性のオプションがありません。これは、ハードウェアへの出費が少なく、よりシンプルな展開を使用することを意味します。高可用性が必須である場合は、下記の拡張統合のシナリオを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f36ea-p104">With this scenario, there is no option for high availability. This will mean you spend less on hardware and have a simpler deployment. If high availability is a must, check out the Scaled consolidated scenarios below.</span></span>
  
![NAT を使用するプライベート IP を持つ単一統合エッジのエッジ シナリオ](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePrivateIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="f36ea-124">ポートの図</span><span class="sxs-lookup"><span data-stu-id="f36ea-124">Port diagram</span></span>

<span data-ttu-id="f36ea-125">単一の統合エッジ サーバーのポートの図もあります。</span><span class="sxs-lookup"><span data-stu-id="f36ea-125">We also have a diagram for ports for single consolidated Edge Servers.</span></span>
  
![エッジ シナリオのネットワーク境界、単一統合エッジ](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-public-ip-addresses"></a><span data-ttu-id="f36ea-127">シングルは、ビジネス エッジ サーバーのパブリック IP アドレスを使用して Skype を統合します。</span><span class="sxs-lookup"><span data-stu-id="f36ea-127">Single consolidated Skype for Business Server Edge Server with public IP addresses</span></span>

<span data-ttu-id="f36ea-p105">このシナリオでは、高可用性のオプションがありません。これは、ハードウェアへの出費が少なく、よりシンプルな展開を使用することを意味します。高可用性が必須である場合は、下記の拡張統合のシナリオを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f36ea-p105">With this scenario, there is no option for high availability. This will mean you spend less on hardware and have a simpler deployment. If high availability is a must, check out the Scaled consolidated scenarios below.</span></span>
  
![パブリック IP を持つ単一統合エッジのエッジ シナリオ](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePublicIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="f36ea-132">ポートの図</span><span class="sxs-lookup"><span data-stu-id="f36ea-132">Port diagram</span></span>

<span data-ttu-id="f36ea-133">単一の統合エッジ サーバーのポートの図もあります。</span><span class="sxs-lookup"><span data-stu-id="f36ea-133">We also have a diagram for ports for single consolidated Edge Servers.</span></span>
  
![エッジ シナリオのネットワーク境界、単一統合エッジ](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-private-ip-addresses-and-nat"></a><span data-ttu-id="f36ea-135">ビジネス サーバー エッジ プールでは、DNS の統合 Skype を拡大/縮小された負荷の分散、およびプライベート IP アドレスと NAT</span><span class="sxs-lookup"><span data-stu-id="f36ea-135">Scaled consolidated Skype for Business Server Edge pool, with DNS load balancing, and private IP addresses and NAT</span></span>

<span data-ttu-id="f36ea-136">このシナリオではエッジ展開で高可用性を実現でき、スケーラビリティとフェールオーバー サポートのメリットが得られます。</span><span class="sxs-lookup"><span data-stu-id="f36ea-136">With this scenario, you are able to have high availability in your Edge deployment, which gives you the advantages of scalability and failover support.</span></span>
  
![拡張統合エッジのエッジ シナリオ、NAT を使用するプライベート IP を持つ DNS LB](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPrivateIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="f36ea-138">ポートの図</span><span class="sxs-lookup"><span data-stu-id="f36ea-138">Port diagram</span></span>

<span data-ttu-id="f36ea-139">DNS の負荷分散と統合のスケールのエッジ プールの図もあります。</span><span class="sxs-lookup"><span data-stu-id="f36ea-139">We also have a diagram for scaled consolidated Edge pools with DNS load balancing.</span></span>
  
![エッジ シナリオのネットワーク境界、DNS LB を使用する拡張統合エッジ](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-public-ip-addresses"></a><span data-ttu-id="f36ea-141">ビジネス サーバー エッジ プールでは、DNS の統合 Skype を拡大/縮小された負荷の分散とパブリックの IP アドレス</span><span class="sxs-lookup"><span data-stu-id="f36ea-141">Scaled consolidated Skype for Business Server Edge pool, with DNS load balancing and public IP addresses</span></span>

<span data-ttu-id="f36ea-142">このシナリオではエッジ展開で高可用性を実現でき、スケーラビリティとフェールオーバー サポートのメリットが得られます。</span><span class="sxs-lookup"><span data-stu-id="f36ea-142">With this scenario, you are able to have high availability in your Edge deployment, which gives you the advantages of scalability and failover support.</span></span>
  
![拡張統合エッジのエッジ シナリオ、パブリック IP を持つ DNS LB](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPublicIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="f36ea-144">ポートの図</span><span class="sxs-lookup"><span data-stu-id="f36ea-144">Port diagram</span></span>

<span data-ttu-id="f36ea-145">DNS の負荷分散と統合のスケールのエッジ プールの図もあります。</span><span class="sxs-lookup"><span data-stu-id="f36ea-145">We also have a diagram for scaled consolidated Edge pools with DNS load balancing.</span></span>
  
![エッジ シナリオのネットワーク境界、DNS LB を使用する拡張統合エッジ](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-hardware-load-balancing"></a><span data-ttu-id="f36ea-147">ビジネス サーバー エッジ プールには、ハードウェア負荷分散と統合の Skype を拡大または縮小</span><span class="sxs-lookup"><span data-stu-id="f36ea-147">Scaled consolidated Skype for Business Server Edge pool, with hardware load balancing</span></span>

<span data-ttu-id="f36ea-148">このシナリオではエッジ展開で高可用性を実現でき、スケーラビリティとフェールオーバー サポートのメリットが得られます。</span><span class="sxs-lookup"><span data-stu-id="f36ea-148">With this scenario, you are able to have high availability in your Edge deployment, which gives you the advantages of scalability and failover support.</span></span>
  
![HLB を持つ拡張統合エッジのエッジ シナリオ](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeHLB.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="f36ea-150">ポートの図</span><span class="sxs-lookup"><span data-stu-id="f36ea-150">Port diagram</span></span>

<span data-ttu-id="f36ea-151">ハードウェア負荷分散と統合されたエッジ プールを拡大/縮小された図もあります。</span><span class="sxs-lookup"><span data-stu-id="f36ea-151">We also have a diagram for scaled consolidated Edge pools with hardware load balancing</span></span>
  
![エッジ サーバー境界ネットワークのポートおよびプロトコル](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeHLB.jpg)
  

