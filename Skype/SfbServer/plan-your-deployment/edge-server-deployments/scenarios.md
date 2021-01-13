---
title: Skype for Business Server のエッジ サーバーのシナリオ
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: '概要: これらのシナリオを確認して、Skype for Business Server でエッジ サーバー トポロジを計画します。'
ms.openlocfilehash: cfcc1e8b34576fbec85464fb8d5e35903b47d8ef
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813797"
---
# <a name="edge-server-scenarios-in-skype-for-business-server"></a><span data-ttu-id="d55b9-103">Skype for Business Server のエッジ サーバーのシナリオ</span><span class="sxs-lookup"><span data-stu-id="d55b9-103">Edge Server scenarios in Skype for Business Server</span></span>
 
<span data-ttu-id="d55b9-104">**概要:** これらのシナリオを確認して、Skype for Business Server でエッジ サーバー トポロジを計画します。</span><span class="sxs-lookup"><span data-stu-id="d55b9-104">**Summary:** Review these scenarios to help you plan your Edge Server topology in Skype for Business Server.</span></span>
  
<span data-ttu-id="d55b9-105">実装する Skype for Business Server エッジ サーバー トポロジの視覚化と決定に役立つシナリオ図がいくつか示されています。</span><span class="sxs-lookup"><span data-stu-id="d55b9-105">We have some scenarios diagrams to assist with visualizing and deciding on what Skype for Business Server Edge Server topology you want to implement.</span></span> <span data-ttu-id="d55b9-106">有力候補を選んだら、対処する必要がある環境要件を確認できます。</span><span class="sxs-lookup"><span data-stu-id="d55b9-106">Once you've picked a good candidate, you can go read up on the environmental requirements you'll need to address.</span></span> <span data-ttu-id="d55b9-107">以下は、すべてのシナリオに適用されます。そのため、最初に説明します。</span><span class="sxs-lookup"><span data-stu-id="d55b9-107">The following is applicable to any of the scenarios, so we're mentioning it first.</span></span>
  
<span data-ttu-id="d55b9-108">これらの図は、例としてのみ示されている (そのため、サンプルの IPv4 および IPv6 データが含まれている) ので、実際の通信フローではなく、考えられるトラフィックのハイレベルなビューを表しています。</span><span class="sxs-lookup"><span data-stu-id="d55b9-108">These figures, which are shown for example purposes only (and as such contains sample IPv4 and IPv6 data), don't represent the actual communication flow, but rather a high-level view of your possible traffic.</span></span> <span data-ttu-id="d55b9-109">ポートの詳細は、以下の各シナリオのポート図でも確認できます。</span><span class="sxs-lookup"><span data-stu-id="d55b9-109">Port details can also be seen in the Port diagrams for each scenario below.</span></span>
  
<span data-ttu-id="d55b9-110">図は、外部インターフェイスの .com と内部の .net を示しています。これはサンプル マテリアルです。もちろん、独自の最終的なエッジ プランをまとめる場合は、独自のエントリがかなり異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="d55b9-110">The diagrams show .com for the external interface and .net for the internal, which is also sample material; of course your own entries may be quite different when you're putting together your own final Edge plan.</span></span>
  
<span data-ttu-id="d55b9-111">どの図にもディレクター (オプションのコンポーネント) は含めされていませんが、その詳細については別途お読みください (他の「計画」のトピックに記載されています)。</span><span class="sxs-lookup"><span data-stu-id="d55b9-111">We don't include the Director (which is an optional component) in any of the diagrams, but you can read about that separately (it's mentioned in other Planning topics).</span></span>
  
<span data-ttu-id="d55b9-112">上で説明したように、図にはサンプル IPv6 データがあります。</span><span class="sxs-lookup"><span data-stu-id="d55b9-112">As noted above, there is sample IPv6 data in the diagrams.</span></span> <span data-ttu-id="d55b9-113">[Skype for Business Server](edge-server-deployments.md)でのエッジ サーバー展開の計画に関するドキュメントの大部分は IPv4 を参照しますが、IPv6 を使用する場合は確実にサポートされます。</span><span class="sxs-lookup"><span data-stu-id="d55b9-113">Most of the documentation in [Plan for Edge Server deployments in Skype for Business Server](edge-server-deployments.md) will refer to IPv4, but you are certainly supported if you want to use IPv6.</span></span> <span data-ttu-id="d55b9-114">割り当てられたアドレス スペースには IPv6 アドレスが必要であり、IPv4 IP と同様に、内部および外部のアドレス指定で動作する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d55b9-114">Note that you'll need IPv6 addresses in your assigned address space, and they'll need to work with internal and external addressing, as with IPv4 IPs.</span></span> <span data-ttu-id="d55b9-115">Windows により、デュアル スタック機能を使用できます。デュアル スタック機能は、IPv4 と IPv6 用の独立した個別のネットワーク スタックです。</span><span class="sxs-lookup"><span data-stu-id="d55b9-115">You can, thanks to Windows, employ the dual stack feature, which is a separate and distinct network stack for IPv4 and IPv6.</span></span> <span data-ttu-id="d55b9-116">これにより、必要に応じて、IPv4 アドレスと IPv6 アドレスを同時に割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="d55b9-116">This will, if you need, allow you to assign IPv4 and IPv6 addresses concurrently.</span></span>
  
<span data-ttu-id="d55b9-117">NAT64 (IPv6 ~ IPv4) と NAT66 (IPv6 ~ IPv6) を許可する NAT デバイスがあります。これは Skype for Business Server で使用する場合に有効です。</span><span class="sxs-lookup"><span data-stu-id="d55b9-117">There are NAT devices that allow for NAT64 (IPv6 to IPv4) and NAT66 (IPv6 to IPv6)), and this is valid for use with Skype for Business Server.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="d55b9-118">通話受付管理 (CAC) を使用している場合は、内部インターフェイスで IPv4 を使用して動作する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d55b9-118">If you're using Call Admission Control (CAC) you do have to use IPv4 on the internal interface for it to work.</span></span> 
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-private-ip-addresses-and-nat"></a><span data-ttu-id="d55b9-119">プライベート IP アドレスと NAT を使用する単一統合 Skype for Business Server エッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="d55b9-119">Single consolidated Skype for Business Server Edge Server with private IP addresses and NAT</span></span>

<span data-ttu-id="d55b9-120">このシナリオでは、高可用性のオプションはありません。</span><span class="sxs-lookup"><span data-stu-id="d55b9-120">With this scenario, there is no option for high availability.</span></span> <span data-ttu-id="d55b9-121">つまり、ハードウェアの使用が少なく、展開が簡単になります。</span><span class="sxs-lookup"><span data-stu-id="d55b9-121">This will mean you spend less on hardware and have a simpler deployment.</span></span> <span data-ttu-id="d55b9-122">高可用性が必要な場合は、以下の拡張統合シナリオを確認してください。</span><span class="sxs-lookup"><span data-stu-id="d55b9-122">If high availability is a must, check out the Scaled consolidated scenarios below.</span></span>
  
![NAT を使用するプライベート IP を使用する単一統合エッジのエッジ シナリオ](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePrivateIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="d55b9-124">ポート図</span><span class="sxs-lookup"><span data-stu-id="d55b9-124">Port diagram</span></span>

<span data-ttu-id="d55b9-125">また、単一統合エッジ サーバーのポートの図も示します。</span><span class="sxs-lookup"><span data-stu-id="d55b9-125">We also have a diagram for ports for single consolidated Edge Servers.</span></span>
  
![エッジ シナリオの単一統合エッジのネットワーク境界](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-public-ip-addresses"></a><span data-ttu-id="d55b9-127">パブリック IP アドレスを使用する単一統合 Skype for Business Server エッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="d55b9-127">Single consolidated Skype for Business Server Edge Server with public IP addresses</span></span>

<span data-ttu-id="d55b9-128">このシナリオでは、高可用性のオプションはありません。</span><span class="sxs-lookup"><span data-stu-id="d55b9-128">With this scenario, there is no option for high availability.</span></span> <span data-ttu-id="d55b9-129">つまり、ハードウェアの使用が少なく、展開が簡単になります。</span><span class="sxs-lookup"><span data-stu-id="d55b9-129">This will mean you spend less on hardware and have a simpler deployment.</span></span> <span data-ttu-id="d55b9-130">高可用性が必要な場合は、以下の拡張統合シナリオを確認してください。</span><span class="sxs-lookup"><span data-stu-id="d55b9-130">If high availability is a must, check out the Scaled consolidated scenarios below.</span></span>
  
![パブリック IP を使用する単一統合エッジのエッジ シナリオ](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePublicIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="d55b9-132">ポート図</span><span class="sxs-lookup"><span data-stu-id="d55b9-132">Port diagram</span></span>

<span data-ttu-id="d55b9-133">また、単一統合エッジ サーバーのポートの図も示します。</span><span class="sxs-lookup"><span data-stu-id="d55b9-133">We also have a diagram for ports for single consolidated Edge Servers.</span></span>
  
![エッジ シナリオの単一統合エッジのネットワーク境界](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-private-ip-addresses-and-nat"></a><span data-ttu-id="d55b9-135">拡張統合 Skype for Business Server エッジ プール (DNS 負荷分散、プライベート IP アドレスと NAT を使用)</span><span class="sxs-lookup"><span data-stu-id="d55b9-135">Scaled consolidated Skype for Business Server Edge pool, with DNS load balancing, and private IP addresses and NAT</span></span>

<span data-ttu-id="d55b9-136">このシナリオでは、エッジ展開で高可用性を実現できます。これにより、スケーラビリティとフェールオーバーのサポートの利点が得されます。</span><span class="sxs-lookup"><span data-stu-id="d55b9-136">With this scenario, you are able to have high availability in your Edge deployment, which gives you the advantages of scalability and failover support.</span></span>
  
![拡張統合エッジのエッジ シナリオ、NAT を使用するプライベート IP を使用する DNS LB](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPrivateIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="d55b9-138">ポート図</span><span class="sxs-lookup"><span data-stu-id="d55b9-138">Port diagram</span></span>

<span data-ttu-id="d55b9-139">また、DNS 負荷分散を使用した拡張統合エッジ プールの図も示します。</span><span class="sxs-lookup"><span data-stu-id="d55b9-139">We also have a diagram for scaled consolidated Edge pools with DNS load balancing.</span></span>
  
![DNS LB を使用したエッジ シナリオ拡張統合エッジのネットワーク境界](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-public-ip-addresses"></a><span data-ttu-id="d55b9-141">拡張統合 Skype for Business Server エッジ プール (DNS 負荷分散とパブリック IP アドレスを使用)</span><span class="sxs-lookup"><span data-stu-id="d55b9-141">Scaled consolidated Skype for Business Server Edge pool, with DNS load balancing and public IP addresses</span></span>

<span data-ttu-id="d55b9-142">このシナリオでは、エッジ展開で高可用性を実現できます。これにより、スケーラビリティとフェールオーバーのサポートの利点が得されます。</span><span class="sxs-lookup"><span data-stu-id="d55b9-142">With this scenario, you are able to have high availability in your Edge deployment, which gives you the advantages of scalability and failover support.</span></span>
  
![拡張統合エッジ、パブリック IP を使用した DNS LB のエッジ シナリオ](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPublicIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="d55b9-144">ポート図</span><span class="sxs-lookup"><span data-stu-id="d55b9-144">Port diagram</span></span>

<span data-ttu-id="d55b9-145">また、DNS 負荷分散を使用した拡張統合エッジ プールの図も示します。</span><span class="sxs-lookup"><span data-stu-id="d55b9-145">We also have a diagram for scaled consolidated Edge pools with DNS load balancing.</span></span>
  
![DNS LB を使用したエッジ シナリオ拡張統合エッジのネットワーク境界](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-hardware-load-balancing"></a><span data-ttu-id="d55b9-147">拡張統合 Skype for Business Server エッジ プール (ハードウェア負荷分散を使用)</span><span class="sxs-lookup"><span data-stu-id="d55b9-147">Scaled consolidated Skype for Business Server Edge pool, with hardware load balancing</span></span>

<span data-ttu-id="d55b9-148">このシナリオでは、エッジ展開で高可用性を実現できます。これにより、スケーラビリティとフェールオーバーのサポートの利点が得されます。</span><span class="sxs-lookup"><span data-stu-id="d55b9-148">With this scenario, you are able to have high availability in your Edge deployment, which gives you the advantages of scalability and failover support.</span></span>
  
![HLB を使用した拡張統合エッジのエッジ シナリオ](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeHLB.jpg)
 
