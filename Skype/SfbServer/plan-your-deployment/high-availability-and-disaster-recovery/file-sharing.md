---
title: Skype for Business Server でのファイル共有の高可用性
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b8c8d5ec-9397-4128-8d1e-8ec6c30fade7
description: DFS を使用して、Skype for Business Server でファイル共有の高可用性を確保する方法について説明します。
ms.openlocfilehash: 4d443425f453d63694511d13c6d3a84893058daa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802897"
---
# <a name="file-sharing-high-availability-in-skype-for-business-server"></a>Skype for Business Server でのファイル共有の高可用性
 
DFS を使用して、Skype for Business Server でファイル共有の高可用性を確保する方法について説明します。
  
Skype for Business Server 展開でファイル共有の高可用性を確保するには、分散ファイル システム (DFS) を使用できます。 DFS は、同一データ センター内の 1 台のファイル サーバーから別のファイル サーバーへのフェールオーバーをサポートします。 大規模展開に対しては、DFS を使用してペアにした専用ファイル サーバーを使用することをお勧めします。 DFS の詳細については、「Windows Server 2012」を参照してください [https://go.microsoft.com/fwlink/?LinkId=524384](https://go.microsoft.com/fwlink/?LinkId=524384) 。 Windows Server 2008 の DFS の詳細については、以下を参照してください [https://go.microsoft.com/fwlink/p/?LinkId=524385](https://go.microsoft.com/fwlink/p/?LinkId=524385) 。
  
ネットワークの規模と必要な復元性に応じて、1 組のサーバーを使用してサイト内のすべてのファイル共有をホストするか、フロントエンド プールごとに 1 組のサーバーを使用できます。
  
DFS はベスト エフォート型のファイル レプリケーション メカニズムで、目標復旧時間 (RTO) または目標復旧ポイント (RPO) は公表されていません。 DFS サーバー間のフェールオーバーは迅速に完了する必要がありますが、データ レプリケーションの遅延により、フェールオーバーが発生した場合にユーザーが進行中の作業を続行できない可能性があります。
  
DFS を使用し、ファイル共有上のデータ ストアが重要な場合は、4 ~ 8 時間ごとにファイル共有を頻繁にバックアップする必要があります。 1 つのファイル共有がダウンして、レプリケーションが最新ではない場合は、バックアップを使用して、障害が発生したサーバー上のコンテンツを、そのサーバーとペアになっている他のサーバーに復元できます。
  

