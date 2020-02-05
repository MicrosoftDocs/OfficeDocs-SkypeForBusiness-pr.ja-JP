---
title: Skype for Business Server のエッジサーバーのシナリオ
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 7b9c211b-deb0-479d-b184-973f08b96d07
description: '概要: これらのシナリオを確認して、Skype for Business Server で Edge Server トポロジを計画するのに役立ちます。'
ms.openlocfilehash: 64d38b5c9b4a32991bf87bd6ba8af87c92db115f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41754167"
---
# <a name="edge-server-scenarios-in-skype-for-business-server"></a>Skype for Business Server のエッジサーバーのシナリオ
 
**概要:** これらのシナリオを確認して、Skype for Business Server で Edge Server のトポロジを計画するのに役立ちます。
  
実装する Skype for Business Server Edge Server のトポロジを視覚化して決定するためのシナリオ図がいくつか用意されています。 適切な候補を選択すれば、対処する必要がある環境の要件を調査できます。 次に示す図はすべてのシナリオに適用されるため、最初に説明します。
  
以下の図は例示のみを目的として示されている (つまり、サンプルの IPv4 および IPv6 データが含まれている) ため、実際の通信の流れではなく、可能なトラフィックの概要を表しています。ポートの詳細は、以下の各シナリオのポートの図でも確認できます。
  
図に示す .com は外部インターフェイス用で、.net は内部インターフェイス用ですが、これらもサンプル情報です。もちろん、最終的なエッジの計画を策定する際には、独自のエントリはまったく異なるものである可能性があります。
  
いずれの図面にもディレクター (オプションのコンポーネント) は含まれていませんが、別の方法で確認できます (他の計画トピックで説明しています)。
  
上で説明したように、サンプルの IPv6 データがダイアグラムにあります。 [Skype For Business server の Edge server 展開の計画](edge-server-deployments.md)に含まれているドキュメントのほとんどは IPv4 を参照していますが、IPv6 を使用する場合は、確実にサポートされます。 IPv6 アドレスが割り当てられたアドレススペースに必要になることに注意してください。 IPv4 Ip と同様に、内部および外部のアドレス管理機能が必要になります。 Windows のおかげで、デュアルスタック機能が採用されました。これは、IPv4 と IPv6 用の独立した個別のネットワークスタックです。 必要に応じて、IPv4 アドレスと IPv6 アドレスを同時に割り当てることができます。
  
NAT64 (IPv6 から IPv4) と NAT66 (ipv6 から IPv6) を許可する NAT デバイスはありますが、これは Skype for Business Server で使用する場合に有効です。
  
> [!IMPORTANT]
> 通話受付管理 (CAC) を使用している場合、CAC が機能するためには、内部インターフェイスで IPv4 を使用する必要があります。 
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-private-ip-addresses-and-nat"></a>プライベート IP アドレスと NAT を備えた単一の統合 Skype for business Server エッジサーバー

このシナリオでは、高可用性のオプションがありません。これは、ハードウェアへの出費が少なく、よりシンプルな展開を使用することを意味します。高可用性が必須である場合は、下記の拡張統合のシナリオを参照してください。
  
![NAT を使用するプライベート IP を持つ単一統合エッジのエッジ シナリオ](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePrivateIP.jpg)
  
### <a name="port-diagram"></a>ポートの図

また、単一の統合エッジサーバー用のポートの図も用意されています。
  
![エッジ シナリオのネットワーク境界、単一統合エッジ](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-public-ip-addresses"></a>パブリック IP アドレスを備えた単一の統合 Skype for business Server エッジサーバー

このシナリオでは、高可用性のオプションがありません。これは、ハードウェアへの出費が少なく、よりシンプルな展開を使用することを意味します。高可用性が必須である場合は、下記の拡張統合のシナリオを参照してください。
  
![パブリック IP を持つ単一統合エッジのエッジ シナリオ](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePublicIP.jpg)
  
### <a name="port-diagram"></a>ポートの図

また、単一の統合エッジサーバー用のポートの図も用意されています。
  
![エッジ シナリオのネットワーク境界、単一統合エッジ](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-private-ip-addresses-and-nat"></a>拡張された Skype for Business Server Edge プール、DNS の負荷分散、プライベート IP アドレスと NAT

このシナリオではエッジ展開で高可用性を実現でき、スケーラビリティとフェールオーバー サポートのメリットが得られます。
  
![拡張統合エッジのエッジ シナリオ、NAT を使用するプライベート IP を持つ DNS LB](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPrivateIP.jpg)
  
### <a name="port-diagram"></a>ポートの図

また、統合されたエッジプールを拡張して、DNS の負荷分散を行うこともできます。
  
![エッジ シナリオのネットワーク境界、DNS LB を使用する拡張統合エッジ](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-public-ip-addresses"></a>拡張された Skype for Business Server Edge プール、DNS の負荷分散およびパブリック IP アドレス

このシナリオではエッジ展開で高可用性を実現でき、スケーラビリティとフェールオーバー サポートのメリットが得られます。
  
![拡張統合エッジのエッジ シナリオ、パブリック IP を持つ DNS LB](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPublicIP.jpg)
  
### <a name="port-diagram"></a>ポートの図

また、統合されたエッジプールを拡張して、DNS の負荷分散を行うこともできます。
  
![エッジ シナリオのネットワーク境界、DNS LB を使用する拡張統合エッジ](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-hardware-load-balancing"></a>統合された Skype for Business Server Edge プール、ハードウェア負荷分散

このシナリオではエッジ展開で高可用性を実現でき、スケーラビリティとフェールオーバー サポートのメリットが得られます。
  
![HLB を持つ拡張統合エッジのエッジ シナリオ](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeHLB.jpg)
 
