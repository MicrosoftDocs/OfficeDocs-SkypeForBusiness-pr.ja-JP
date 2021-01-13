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
# <a name="edge-server-scenarios-in-skype-for-business-server"></a>Skype for Business Server のエッジ サーバーのシナリオ
 
**概要:** これらのシナリオを確認して、Skype for Business Server でエッジ サーバー トポロジを計画します。
  
実装する Skype for Business Server エッジ サーバー トポロジの視覚化と決定に役立つシナリオ図がいくつか示されています。 有力候補を選んだら、対処する必要がある環境要件を確認できます。 以下は、すべてのシナリオに適用されます。そのため、最初に説明します。
  
これらの図は、例としてのみ示されている (そのため、サンプルの IPv4 および IPv6 データが含まれている) ので、実際の通信フローではなく、考えられるトラフィックのハイレベルなビューを表しています。 ポートの詳細は、以下の各シナリオのポート図でも確認できます。
  
図は、外部インターフェイスの .com と内部の .net を示しています。これはサンプル マテリアルです。もちろん、独自の最終的なエッジ プランをまとめる場合は、独自のエントリがかなり異なる場合があります。
  
どの図にもディレクター (オプションのコンポーネント) は含めされていませんが、その詳細については別途お読みください (他の「計画」のトピックに記載されています)。
  
上で説明したように、図にはサンプル IPv6 データがあります。 [Skype for Business Server](edge-server-deployments.md)でのエッジ サーバー展開の計画に関するドキュメントの大部分は IPv4 を参照しますが、IPv6 を使用する場合は確実にサポートされます。 割り当てられたアドレス スペースには IPv6 アドレスが必要であり、IPv4 IP と同様に、内部および外部のアドレス指定で動作する必要があります。 Windows により、デュアル スタック機能を使用できます。デュアル スタック機能は、IPv4 と IPv6 用の独立した個別のネットワーク スタックです。 これにより、必要に応じて、IPv4 アドレスと IPv6 アドレスを同時に割り当てできます。
  
NAT64 (IPv6 ~ IPv4) と NAT66 (IPv6 ~ IPv6) を許可する NAT デバイスがあります。これは Skype for Business Server で使用する場合に有効です。
  
> [!IMPORTANT]
> 通話受付管理 (CAC) を使用している場合は、内部インターフェイスで IPv4 を使用して動作する必要があります。 
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-private-ip-addresses-and-nat"></a>プライベート IP アドレスと NAT を使用する単一統合 Skype for Business Server エッジ サーバー

このシナリオでは、高可用性のオプションはありません。 つまり、ハードウェアの使用が少なく、展開が簡単になります。 高可用性が必要な場合は、以下の拡張統合シナリオを確認してください。
  
![NAT を使用するプライベート IP を使用する単一統合エッジのエッジ シナリオ](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePrivateIP.jpg)
  
### <a name="port-diagram"></a>ポート図

また、単一統合エッジ サーバーのポートの図も示します。
  
![エッジ シナリオの単一統合エッジのネットワーク境界](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-public-ip-addresses"></a>パブリック IP アドレスを使用する単一統合 Skype for Business Server エッジ サーバー

このシナリオでは、高可用性のオプションはありません。 つまり、ハードウェアの使用が少なく、展開が簡単になります。 高可用性が必要な場合は、以下の拡張統合シナリオを確認してください。
  
![パブリック IP を使用する単一統合エッジのエッジ シナリオ](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePublicIP.jpg)
  
### <a name="port-diagram"></a>ポート図

また、単一統合エッジ サーバーのポートの図も示します。
  
![エッジ シナリオの単一統合エッジのネットワーク境界](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-private-ip-addresses-and-nat"></a>拡張統合 Skype for Business Server エッジ プール (DNS 負荷分散、プライベート IP アドレスと NAT を使用)

このシナリオでは、エッジ展開で高可用性を実現できます。これにより、スケーラビリティとフェールオーバーのサポートの利点が得されます。
  
![拡張統合エッジのエッジ シナリオ、NAT を使用するプライベート IP を使用する DNS LB](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPrivateIP.jpg)
  
### <a name="port-diagram"></a>ポート図

また、DNS 負荷分散を使用した拡張統合エッジ プールの図も示します。
  
![DNS LB を使用したエッジ シナリオ拡張統合エッジのネットワーク境界](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-public-ip-addresses"></a>拡張統合 Skype for Business Server エッジ プール (DNS 負荷分散とパブリック IP アドレスを使用)

このシナリオでは、エッジ展開で高可用性を実現できます。これにより、スケーラビリティとフェールオーバーのサポートの利点が得されます。
  
![拡張統合エッジ、パブリック IP を使用した DNS LB のエッジ シナリオ](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPublicIP.jpg)
  
### <a name="port-diagram"></a>ポート図

また、DNS 負荷分散を使用した拡張統合エッジ プールの図も示します。
  
![DNS LB を使用したエッジ シナリオ拡張統合エッジのネットワーク境界](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-hardware-load-balancing"></a>拡張統合 Skype for Business Server エッジ プール (ハードウェア負荷分散を使用)

このシナリオでは、エッジ展開で高可用性を実現できます。これにより、スケーラビリティとフェールオーバーのサポートの利点が得されます。
  
![HLB を使用した拡張統合エッジのエッジ シナリオ](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeHLB.jpg)
 
