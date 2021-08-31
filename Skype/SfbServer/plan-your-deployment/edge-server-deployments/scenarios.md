---
title: エッジ サーバーのシナリオ (Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 7b9c211b-deb0-479d-b184-973f08b96d07
description: '概要: これらのシナリオを確認して、エッジ サーバー トポロジを計画する場合に役立Skype for Business Server。'
ms.openlocfilehash: 4035418426975b79a35be7ec84c6affac3ab92d5
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2021
ms.locfileid: "58732096"
---
# <a name="edge-server-scenarios-in-skype-for-business-server"></a>エッジ サーバーのシナリオ (Skype for Business Server
 
**概要:** これらのシナリオを確認して、エッジ サーバー トポロジを計画する場合は、Skype for Business Server。
  
実装するエッジ サーバー トポロジの視覚化と決定に役立つSkype for Business Serverシナリオ図があります。 優れた候補者を選んだら、対処する必要がある環境要件を確認できます。 次に示すのは、どのシナリオにも当てはめておき、最初に説明します。
  
これらの図は、たとえば目的でのみ表示されます (たとえば、サンプル IPv4 および IPv6 データが含まれている場合) は、実際の通信フローを表すのではなく、可能なトラフィックの高レベルのビューを表します。 ポートの詳細は、以下の各シナリオのポート図でも確認できます。
  
図は、外部インターフェイスの .com と内部の .net を示しています。これはサンプル マテリアルです。もちろん、独自の最終的な Edge プランをまとめる場合、独自のエントリはかなり異なる場合があります。
  
ディレクター (省略可能なコンポーネント) は、どの図にも含めかけますが、その詳細については別途お読みください (他の計画に関するトピックに記載されています)。
  
上で説明したように、図にはサンプル IPv6 データがあります。 「Plan for [Edge Server deployments in Skype for Business Server」](edge-server-deployments.md)のドキュメントの大部分は IPv4 を参照しますが、IPv6 を使用する場合は確実にサポートされています。 割り当てられたアドレス空間に IPv6 アドレスが必要であり、IPv4 IP と同様に、内部および外部のアドレス指定を使用する必要があります。 IPv4 と IPv6 Windows個別のネットワーク スタックであるデュアル スタック機能を使用できます。 これにより、必要に応じて、IPv4 アドレスと IPv6 アドレスを同時に割り当てできます。
  
NAT64 (IPv6 ~ IPv4) と NAT66 (IPv6 ~ IPv6) を許可する NAT デバイスがあります。これは、Skype for Business Server で使用するために有効です。
  
> [!IMPORTANT]
> 通話受付管理 (CAC) を使用している場合は、内部インターフェイスで IPv4 を使用して動作する必要があります。 
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-private-ip-addresses-and-nat"></a>プライベート IP アドレスSkype for Business Server NAT を持つ単一の統合エッジ サーバー

このシナリオでは、高可用性のオプションはありません。 つまり、ハードウェアへの支出が少なく、展開が簡単になります。 高可用性が必要な場合は、以下の拡張統合シナリオを参照してください。
  
![NAT を使用したプライベート IP を使用した単一統合エッジのエッジ シナリオ。](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePrivateIP.jpg)
  
### <a name="port-diagram"></a>ポート図

また、単一統合エッジ サーバーのポートの図も示しています。
  
![エッジ シナリオ単一統合エッジのネットワーク境界。](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-public-ip-addresses"></a>パブリック IP アドレスSkype for Business Server単一の統合エッジ サーバー

このシナリオでは、高可用性のオプションはありません。 つまり、ハードウェアへの支出が少なく、展開が簡単になります。 高可用性が必要な場合は、以下の拡張統合シナリオを参照してください。
  
![パブリック IP を使用した単一統合エッジのエッジ シナリオ。](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePublicIP.jpg)
  
### <a name="port-diagram"></a>ポート図

また、単一統合エッジ サーバーのポートの図も示しています。
  
![エッジ シナリオ単一統合エッジのネットワーク境界。](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-private-ip-addresses-and-nat"></a>拡張された統合Skype for Business Serverエッジ プール(DNS 負荷分散、プライベート IP アドレスと NAT を使用)

このシナリオでは、エッジ展開で高可用性を実現できます。これにより、スケーラビリティとフェールオーバーのサポートの利点が得されます。
  
![拡張統合エッジのエッジ シナリオ、NAT を使用したプライベート IP を使用した DNS LB。](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPrivateIP.jpg)
  
### <a name="port-diagram"></a>ポート図

また、DNS 負荷分散を使用した拡張統合エッジ プールの図もあります。
  
![エッジ シナリオのネットワーク境界 DNS LB を使用して拡張統合エッジ。](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-public-ip-addresses"></a>拡張された統合Skype for Business Serverエッジ プール(DNS 負荷分散とパブリック IP アドレスを使用)

このシナリオでは、エッジ展開で高可用性を実現できます。これにより、スケーラビリティとフェールオーバーのサポートの利点が得されます。
  
![拡張統合エッジのエッジ シナリオ、パブリック IP を使用した DNS LB。](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPublicIP.jpg)
  
### <a name="port-diagram"></a>ポート図

また、DNS 負荷分散を使用した拡張統合エッジ プールの図もあります。
  
![エッジ シナリオのネットワーク境界 DNS LB を使用して拡張統合エッジ。](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-hardware-load-balancing"></a>ハードウェア負荷分散Skype for Business Server拡張された統合エッジ プール

このシナリオでは、エッジ展開で高可用性を実現できます。これにより、スケーラビリティとフェールオーバーのサポートの利点が得されます。
  
![HLB を使用した拡張統合エッジのエッジ シナリオ。](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeHLB.jpg)
 
