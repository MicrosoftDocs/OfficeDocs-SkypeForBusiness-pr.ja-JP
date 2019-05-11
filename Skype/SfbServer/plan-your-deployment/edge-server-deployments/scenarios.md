---
title: Skype のビジネス サーバーのサーバーのシナリオをエッジします。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 7b9c211b-deb0-479d-b184-973f08b96d07
description: '概要: ビジネス サーバーの Skype で、エッジ サーバーのトポロジを計画するためのこれらのシナリオを確認します。'
ms.openlocfilehash: 6072417fabeafe330a65887bc3f96d445c970541
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33885069"
---
# <a name="edge-server-scenarios-in-skype-for-business-server"></a>Skype のビジネス サーバーのサーバーのシナリオをエッジします。
 
**の概要:** ビジネス サーバーの Skype で、エッジ サーバーのトポロジを計画するためのこれらのシナリオを確認します。
  
視覚化して、ビジネス エッジ サーバーのトポロジを実装するためには、どのような Skype の決定を支援するいくつかのシナリオの図があります。 適切な候補を選択すれば、対処する必要がある環境の要件を調査できます。 次に示す図はすべてのシナリオに適用されるため、最初に説明します。
  
以下の図は例示のみを目的として示されている (つまり、サンプルの IPv4 および IPv6 データが含まれている) ため、実際の通信の流れではなく、可能なトラフィックの概要を表しています。ポートの詳細は、以下の各シナリオのポートの図でも確認できます。
  
図に示す .com は外部インターフェイス用で、.net は内部インターフェイス用ですが、これらもサンプル情報です。もちろん、最終的なエッジの計画を策定する際には、独自のエントリはまったく異なるものである可能性があります。
  
ダイアグラムのいずれかのダイレクタは、省略可能なコンポーネント) を含めません。 ですが、これについて個別に読み取ることができます (これは、他の計画のトピックに記載されて)。
  
前述したように、IPv6 のサンプル データには、図です。 [Skype ビジネス サーバー用にエッジ サーバーの展開計画](edge-server-deployments.md)のドキュメントのほとんどは、IPv4 を参照してください。 ですが、IPv6 を使用する場合に確実にサポートされています。 割り当てられたアドレス空間内の IPv6 アドレスを必要があり、IPv4 の ip アドレスと内部と外部のアドレスを使用する必要があります、ことに注意してください。 、、Windows のおかげで使用できるデュアル ・ スタック機能は、IPv4 と IPv6 のとは別のネットワーク スタックします。 これはする必要がある場合、IPv4 を割り当てるには、IPv6 のアドレスを同時にします。
  
NAT64 を許可する NAT デバイス (IPv4 を IPv6) と NAT66 (ipv6 IPv6))、これは、Skype のビジネス サーバーで使用するために有効なと。
  
> [!IMPORTANT]
> 通話受付管理 (CAC) を使用している場合、CAC が機能するためには、内部インターフェイスで IPv4 を使用する必要があります。 
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-private-ip-addresses-and-nat"></a>シングルは、ビジネス エッジ サーバーのプライベート IP アドレスと NAT で Skype を統合します。

このシナリオでは、高可用性のオプションがありません。これは、ハードウェアへの出費が少なく、よりシンプルな展開を使用することを意味します。高可用性が必須である場合は、下記の拡張統合のシナリオを参照してください。
  
![NAT を使用するプライベート IP を持つ単一統合エッジのエッジ シナリオ](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePrivateIP.jpg)
  
### <a name="port-diagram"></a>ポートの図

単一の統合エッジ サーバーのポートの図もあります。
  
![エッジ シナリオのネットワーク境界、単一統合エッジ](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-public-ip-addresses"></a>シングルは、ビジネス エッジ サーバーのパブリック IP アドレスを使用して Skype を統合します。

このシナリオでは、高可用性のオプションがありません。これは、ハードウェアへの出費が少なく、よりシンプルな展開を使用することを意味します。高可用性が必須である場合は、下記の拡張統合のシナリオを参照してください。
  
![パブリック IP を持つ単一統合エッジのエッジ シナリオ](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePublicIP.jpg)
  
### <a name="port-diagram"></a>ポートの図

単一の統合エッジ サーバーのポートの図もあります。
  
![エッジ シナリオのネットワーク境界、単一統合エッジ](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-private-ip-addresses-and-nat"></a>ビジネス サーバー エッジ プールでは、DNS の統合 Skype を拡大/縮小された負荷の分散、およびプライベート IP アドレスと NAT

このシナリオではエッジ展開で高可用性を実現でき、スケーラビリティとフェールオーバー サポートのメリットが得られます。
  
![拡張統合エッジのエッジ シナリオ、NAT を使用するプライベート IP を持つ DNS LB](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPrivateIP.jpg)
  
### <a name="port-diagram"></a>ポートの図

DNS の負荷分散と統合のスケールのエッジ プールの図もあります。
  
![エッジ シナリオのネットワーク境界、DNS LB を使用する拡張統合エッジ](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-public-ip-addresses"></a>ビジネス サーバー エッジ プールでは、DNS の統合 Skype を拡大/縮小された負荷の分散とパブリックの IP アドレス

このシナリオではエッジ展開で高可用性を実現でき、スケーラビリティとフェールオーバー サポートのメリットが得られます。
  
![拡張統合エッジのエッジ シナリオ、パブリック IP を持つ DNS LB](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPublicIP.jpg)
  
### <a name="port-diagram"></a>ポートの図

DNS の負荷分散と統合のスケールのエッジ プールの図もあります。
  
![エッジ シナリオのネットワーク境界、DNS LB を使用する拡張統合エッジ](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-hardware-load-balancing"></a>ビジネス サーバー エッジ プールには、ハードウェア負荷分散と統合の Skype を拡大または縮小

このシナリオではエッジ展開で高可用性を実現でき、スケーラビリティとフェールオーバー サポートのメリットが得られます。
  
![HLB を持つ拡張統合エッジのエッジ シナリオ](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeHLB.jpg)
  
### <a name="port-diagram"></a>ポートの図

ハードウェア負荷分散と統合されたエッジ プールを拡大/縮小された図もあります。
  
![エッジ サーバー境界ネットワークのポートおよびプロトコル](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeHLB.jpg)
  

