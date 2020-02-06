---
title: Skype for Business Server でのファイル共有の高可用性
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b8c8d5ec-9397-4128-8d1e-8ec6c30fade7
description: ここでは、DFS を使用して、Skype for Business Server でファイル共有の高可用性を実現する方法について説明します。
ms.openlocfilehash: c04c3acd009dd59a3894a62d08395db19c6d2368
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815935"
---
# <a name="file-sharing-high-availability-in-skype-for-business-server"></a>Skype for Business Server でのファイル共有の高可用性
 
ここでは、DFS を使用して、Skype for Business Server でファイル共有の高可用性を実現する方法について説明します。
  
Skype for Business Server の展開でファイル共有の高可用性を確保するために、分散ファイルシステム (DFS) を使うことができます。 DFS は、同一データ センター内の 1 台のファイル サーバーから別のファイル サーバーへのフェールオーバーをサポートします。 大規模展開に対しては、DFS を使用してペアにした専用ファイル サーバーを使用することをお勧めします。 Windows Server 2012 の DFS の詳細については[https://go.microsoft.com/fwlink/?LinkId=524384](https://go.microsoft.com/fwlink/?LinkId=524384)、を参照してください。 Windows Server 2008 上の DFS の詳細につい[https://go.microsoft.com/fwlink/p/?LinkId=524385](https://go.microsoft.com/fwlink/p/?LinkId=524385)ては、を参照してください。
  
使用しているネットワークのサイズと回復性の量に応じて、1組のサーバーを使用して、サイト内のすべてのファイル共有をホストするか、フロントエンドプールごとに1つのペアを使うことができます。
  
DFS はベスト エフォート型のファイル レプリケーション メカニズムで、目標復旧時間 (RTO) または目標復旧ポイント (RPO) は公表されていません。 DFS サーバー間のフェールオーバーはすぐに完了する必要がありますが、データレプリケーションの遅延によって、フェールオーバーの発生時に進行中の作業を続行することができなくなる場合があります。
  
ファイル共有上での DFS およびデータ ストアの使用が不可欠な場合は、4 ～ 8 時間ごとなど、頻繁にファイル共有をバックアップする必要があります。1 つのファイル共有がダウンして、レプリケーションが最新ではない場合は、バックアップを使用して、障害が発生したサーバー上のコンテンツを、そのサーバーとペアになっている他のサーバーに復元できます。
  

