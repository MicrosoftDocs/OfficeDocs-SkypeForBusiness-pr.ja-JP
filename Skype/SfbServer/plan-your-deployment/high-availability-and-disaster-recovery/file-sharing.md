---
title: Skype で高可用性をビジネス サーバーの共有ファイル
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b8c8d5ec-9397-4128-8d1e-8ec6c30fade7
description: ビジネス サーバーは、DFS を使用して Skype でファイル共有の可用性を確認する方法について説明します。
ms.openlocfilehash: 0b5d2f577775635b95add15dd7b7576ca24c883f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32214069"
---
# <a name="file-sharing-high-availability-in-skype-for-business-server"></a>Skype で高可用性をビジネス サーバーの共有ファイル
 
ビジネス サーバーは、DFS を使用して Skype でファイル共有の可用性を確認する方法について説明します。
  
ビジネス サーバーの展開について、Skype でのファイル共有の高可用性を確保するには、分散ファイル システム (DFS) を使用することができます。 DFS は、同一データ センター内の 1 台のファイル サーバーから別のファイル サーバーへのフェールオーバーをサポートします。 大規模展開に対しては、DFS を使用してペアにした専用ファイル サーバーを使用することをお勧めします。 Windows Server 2012 での DFS の詳細についてを参照してください[https://go.microsoft.com/fwlink/?LinkId=524384](https://go.microsoft.com/fwlink/?LinkId=524384)。 Windows Server 2008 の DFS の詳細についてを参照してください[https://go.microsoft.com/fwlink/p/?LinkId=524385](https://go.microsoft.com/fwlink/p/?LinkId=524385)。
  
によっては、ネットワークのサイズ、弾力性が必要なの量、サイト内のすべてのファイル共有をホストするサーバーの 1 つのペアを使用したり、フロント エンド プールごとに 1 つのペアを使用できます。
  
DFS はベスト エフォート型のファイル レプリケーション メカニズムで、目標復旧時間 (RTO) または目標復旧ポイント (RPO) は公表されていません。 DFS サーバ間でフェイル オーバーを迅速に完了する必要がありますが、データのレプリケーションの遅延がありますように、フェールオーバーが発生する場合は、進行中の作業を続行することができません。
  
ファイル共有上での DFS およびデータ ストアの使用が不可欠な場合は、4 ～ 8 時間ごとなど、頻繁にファイル共有をバックアップする必要があります。1 つのファイル共有がダウンして、レプリケーションが最新ではない場合は、バックアップを使用して、障害が発生したサーバー上のコンテンツを、そのサーバーとペアになっている他のサーバーに復元できます。
  

