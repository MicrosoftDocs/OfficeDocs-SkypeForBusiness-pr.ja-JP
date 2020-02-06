---
title: Skype for Business Server のエッジサーバーのシナリオ
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 7b9c211b-deb0-479d-b184-973f08b96d07
description: '概要: これらのシナリオを確認して、Skype for Business Server で Edge Server トポロジを計画するのに役立ちます。'
ms.openlocfilehash: a1d721ffabb78985d90848784cd587bda96300d5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803357"
---
# <a name="edge-server-scenarios-in-skype-for-business-server"></a><span data-ttu-id="14650-103">Skype for Business Server のエッジサーバーのシナリオ</span><span class="sxs-lookup"><span data-stu-id="14650-103">Edge Server scenarios in Skype for Business Server</span></span>
 
<span data-ttu-id="14650-104">**概要:** これらのシナリオを確認して、Skype for Business Server で Edge Server のトポロジを計画するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="14650-104">**Summary:** Review these scenarios to help you plan your Edge Server topology in Skype for Business Server.</span></span>
  
<span data-ttu-id="14650-105">実装する Skype for Business Server Edge Server のトポロジを視覚化して決定するためのシナリオ図がいくつか用意されています。</span><span class="sxs-lookup"><span data-stu-id="14650-105">We have some scenarios diagrams to assist with visualizing and deciding on what Skype for Business Server Edge Server topology you want to implement.</span></span> <span data-ttu-id="14650-106">適切な候補を選択すれば、対処する必要がある環境の要件を調査できます。</span><span class="sxs-lookup"><span data-stu-id="14650-106">Once you've picked a good candidate, you can go read up on the environmental requirements you'll need to address.</span></span> <span data-ttu-id="14650-107">次に示す図はすべてのシナリオに適用されるため、最初に説明します。</span><span class="sxs-lookup"><span data-stu-id="14650-107">The following is applicable to any of the scenarios, so we're mentioning it first.</span></span>
  
<span data-ttu-id="14650-p102">以下の図は例示のみを目的として示されている (つまり、サンプルの IPv4 および IPv6 データが含まれている) ため、実際の通信の流れではなく、可能なトラフィックの概要を表しています。ポートの詳細は、以下の各シナリオのポートの図でも確認できます。</span><span class="sxs-lookup"><span data-stu-id="14650-p102">These figures, which are shown for example purposes only (and as such contains sample IPv4 and IPv6 data), don't represent the actual communication flow, but rather a high-level view of your possible traffic. Port details can also be seen in the Port diagrams for each scenario below.</span></span>
  
<span data-ttu-id="14650-110">図に示す .com は外部インターフェイス用で、.net は内部インターフェイス用ですが、これらもサンプル情報です。もちろん、最終的なエッジの計画を策定する際には、独自のエントリはまったく異なるものである可能性があります。</span><span class="sxs-lookup"><span data-stu-id="14650-110">The diagrams show .com for the external interface and .net for the internal, which is also sample material; of course your own entries may be quite different when you're putting together your own final Edge plan.</span></span>
  
<span data-ttu-id="14650-111">いずれの図面にもディレクター (オプションのコンポーネント) は含まれていませんが、別の方法で確認できます (他の計画トピックで説明しています)。</span><span class="sxs-lookup"><span data-stu-id="14650-111">We don't include the Director (which is an optional component) in any of the diagrams, but you can read about that separately (it's mentioned in other Planning topics).</span></span>
  
<span data-ttu-id="14650-112">上で説明したように、サンプルの IPv6 データがダイアグラムにあります。</span><span class="sxs-lookup"><span data-stu-id="14650-112">As noted above, there is sample IPv6 data in the diagrams.</span></span> <span data-ttu-id="14650-113">[Skype For Business server の Edge server 展開の計画](edge-server-deployments.md)に含まれているドキュメントのほとんどは IPv4 を参照していますが、IPv6 を使用する場合は、確実にサポートされます。</span><span class="sxs-lookup"><span data-stu-id="14650-113">Most of the documentation in [Plan for Edge Server deployments in Skype for Business Server](edge-server-deployments.md) will refer to IPv4, but you are certainly supported if you want to use IPv6.</span></span> <span data-ttu-id="14650-114">IPv6 アドレスが割り当てられたアドレススペースに必要になることに注意してください。 IPv4 Ip と同様に、内部および外部のアドレス管理機能が必要になります。</span><span class="sxs-lookup"><span data-stu-id="14650-114">Note that you'll need IPv6 addresses in your assigned address space, and they'll need to work with internal and external addressing, as with IPv4 IPs.</span></span> <span data-ttu-id="14650-115">Windows のおかげで、デュアルスタック機能が採用されました。これは、IPv4 と IPv6 用の独立した個別のネットワークスタックです。</span><span class="sxs-lookup"><span data-stu-id="14650-115">You can, thanks to Windows, employ the dual stack feature, which is a separate and distinct network stack for IPv4 and IPv6.</span></span> <span data-ttu-id="14650-116">必要に応じて、IPv4 アドレスと IPv6 アドレスを同時に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="14650-116">This will, if you need, allow you to assign IPv4 and IPv6 addresses concurrently.</span></span>
  
<span data-ttu-id="14650-117">NAT64 (IPv6 から IPv4) と NAT66 (ipv6 から IPv6) を許可する NAT デバイスはありますが、これは Skype for Business Server で使用する場合に有効です。</span><span class="sxs-lookup"><span data-stu-id="14650-117">There are NAT devices that allow for NAT64 (IPv6 to IPv4) and NAT66 (IPv6 to IPv6)), and this is valid for use with Skype for Business Server.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="14650-118">通話受付管理 (CAC) を使用している場合、CAC が機能するためには、内部インターフェイスで IPv4 を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="14650-118">If you're using Call Admission Control (CAC) you do have to use IPv4 on the internal interface for it to work.</span></span> 
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-private-ip-addresses-and-nat"></a><span data-ttu-id="14650-119">プライベート IP アドレスと NAT を備えた単一の統合 Skype for business Server エッジサーバー</span><span class="sxs-lookup"><span data-stu-id="14650-119">Single consolidated Skype for Business Server Edge Server with private IP addresses and NAT</span></span>

<span data-ttu-id="14650-p104">このシナリオでは、高可用性のオプションがありません。これは、ハードウェアへの出費が少なく、よりシンプルな展開を使用することを意味します。高可用性が必須である場合は、下記の拡張統合のシナリオを参照してください。</span><span class="sxs-lookup"><span data-stu-id="14650-p104">With this scenario, there is no option for high availability. This will mean you spend less on hardware and have a simpler deployment. If high availability is a must, check out the Scaled consolidated scenarios below.</span></span>
  
![NAT を使用するプライベート IP を持つ単一統合エッジのエッジ シナリオ](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePrivateIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="14650-124">ポートの図</span><span class="sxs-lookup"><span data-stu-id="14650-124">Port diagram</span></span>

<span data-ttu-id="14650-125">また、単一の統合エッジサーバー用のポートの図も用意されています。</span><span class="sxs-lookup"><span data-stu-id="14650-125">We also have a diagram for ports for single consolidated Edge Servers.</span></span>
  
![エッジ シナリオのネットワーク境界、単一統合エッジ](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-public-ip-addresses"></a><span data-ttu-id="14650-127">パブリック IP アドレスを備えた単一の統合 Skype for business Server エッジサーバー</span><span class="sxs-lookup"><span data-stu-id="14650-127">Single consolidated Skype for Business Server Edge Server with public IP addresses</span></span>

<span data-ttu-id="14650-p105">このシナリオでは、高可用性のオプションがありません。これは、ハードウェアへの出費が少なく、よりシンプルな展開を使用することを意味します。高可用性が必須である場合は、下記の拡張統合のシナリオを参照してください。</span><span class="sxs-lookup"><span data-stu-id="14650-p105">With this scenario, there is no option for high availability. This will mean you spend less on hardware and have a simpler deployment. If high availability is a must, check out the Scaled consolidated scenarios below.</span></span>
  
![パブリック IP を持つ単一統合エッジのエッジ シナリオ](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePublicIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="14650-132">ポートの図</span><span class="sxs-lookup"><span data-stu-id="14650-132">Port diagram</span></span>

<span data-ttu-id="14650-133">また、単一の統合エッジサーバー用のポートの図も用意されています。</span><span class="sxs-lookup"><span data-stu-id="14650-133">We also have a diagram for ports for single consolidated Edge Servers.</span></span>
  
![エッジ シナリオのネットワーク境界、単一統合エッジ](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-private-ip-addresses-and-nat"></a><span data-ttu-id="14650-135">拡張された Skype for Business Server Edge プール、DNS の負荷分散、プライベート IP アドレスと NAT</span><span class="sxs-lookup"><span data-stu-id="14650-135">Scaled consolidated Skype for Business Server Edge pool, with DNS load balancing, and private IP addresses and NAT</span></span>

<span data-ttu-id="14650-136">このシナリオではエッジ展開で高可用性を実現でき、スケーラビリティとフェールオーバー サポートのメリットが得られます。</span><span class="sxs-lookup"><span data-stu-id="14650-136">With this scenario, you are able to have high availability in your Edge deployment, which gives you the advantages of scalability and failover support.</span></span>
  
![拡張統合エッジのエッジ シナリオ、NAT を使用するプライベート IP を持つ DNS LB](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPrivateIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="14650-138">ポートの図</span><span class="sxs-lookup"><span data-stu-id="14650-138">Port diagram</span></span>

<span data-ttu-id="14650-139">また、統合されたエッジプールを拡張して、DNS の負荷分散を行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="14650-139">We also have a diagram for scaled consolidated Edge pools with DNS load balancing.</span></span>
  
![エッジ シナリオのネットワーク境界、DNS LB を使用する拡張統合エッジ](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-public-ip-addresses"></a><span data-ttu-id="14650-141">拡張された Skype for Business Server Edge プール、DNS の負荷分散およびパブリック IP アドレス</span><span class="sxs-lookup"><span data-stu-id="14650-141">Scaled consolidated Skype for Business Server Edge pool, with DNS load balancing and public IP addresses</span></span>

<span data-ttu-id="14650-142">このシナリオではエッジ展開で高可用性を実現でき、スケーラビリティとフェールオーバー サポートのメリットが得られます。</span><span class="sxs-lookup"><span data-stu-id="14650-142">With this scenario, you are able to have high availability in your Edge deployment, which gives you the advantages of scalability and failover support.</span></span>
  
![拡張統合エッジのエッジ シナリオ、パブリック IP を持つ DNS LB](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPublicIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="14650-144">ポートの図</span><span class="sxs-lookup"><span data-stu-id="14650-144">Port diagram</span></span>

<span data-ttu-id="14650-145">また、統合されたエッジプールを拡張して、DNS の負荷分散を行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="14650-145">We also have a diagram for scaled consolidated Edge pools with DNS load balancing.</span></span>
  
![エッジ シナリオのネットワーク境界、DNS LB を使用する拡張統合エッジ](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-hardware-load-balancing"></a><span data-ttu-id="14650-147">統合された Skype for Business Server Edge プール、ハードウェア負荷分散</span><span class="sxs-lookup"><span data-stu-id="14650-147">Scaled consolidated Skype for Business Server Edge pool, with hardware load balancing</span></span>

<span data-ttu-id="14650-148">このシナリオではエッジ展開で高可用性を実現でき、スケーラビリティとフェールオーバー サポートのメリットが得られます。</span><span class="sxs-lookup"><span data-stu-id="14650-148">With this scenario, you are able to have high availability in your Edge deployment, which gives you the advantages of scalability and failover support.</span></span>
  
![HLB を持つ拡張統合エッジのエッジ シナリオ](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeHLB.jpg)
 
