---
title: Skype for Business Server でのファイル共有の高可用性
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b8c8d5ec-9397-4128-8d1e-8ec6c30fade7
description: ここでは、DFS を使用して、Skype for Business Server でファイル共有の高可用性を実現する方法について説明します。
ms.openlocfilehash: 56a6e1008935bc0d38d65e2355826634709aed27
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297478"
---
# <a name="file-sharing-high-availability-in-skype-for-business-server"></a>Skype for Business Server でのファイル共有の高可用性
 
ここでは、DFS を使用して、Skype for Business Server でファイル共有の高可用性を実現する方法について説明します。
  
Skype for Business Server の展開でファイル共有の高可用性を確保するために、分散ファイルシステム (DFS) を使うことができます。 DFS は、同一データ センター内の 1 台のファイル サーバーから別のファイル サーバーへのフェールオーバーをサポートします。 大規模展開に対しては、DFS を使用してペアにした専用ファイル サーバーを使用することをお勧めします。 Windows Server 2012 の DFS の詳細については[https://go.microsoft.com/fwlink/?LinkId=524384](https://go.microsoft.com/fwlink/?LinkId=524384)、を参照してください。 Windows Server 2008 上の DFS の詳細につい[https://go.microsoft.com/fwlink/p/?LinkId=524385](https://go.microsoft.com/fwlink/p/?LinkId=524385)ては、を参照してください。
  
使用しているネットワークのサイズと回復性の量に応じて、1組のサーバーを使用して、サイト内のすべてのファイル共有をホストするか、フロントエンドプールごとに1つのペアを使うことができます。
  
DFS はベスト エフォート型のファイル レプリケーション メカニズムで、目標復旧時間 (RTO) または目標復旧ポイント (RPO) は公表されていません。 DFS サーバー間のフェールオーバーはすぐに完了する必要がありますが、データレプリケーションの遅延によって、フェールオーバーの発生時に進行中の作業を続行することができなくなる場合があります。
  
ファイル共有上での DFS およびデータ ストアの使用が不可欠な場合は、4 ～ 8 時間ごとなど、頻繁にファイル共有をバックアップする必要があります。1 つのファイル共有がダウンして、レプリケーションが最新ではない場合は、バックアップを使用して、障害が発生したサーバー上のコンテンツを、そのサーバーとペアになっている他のサーバーに復元できます。
  

