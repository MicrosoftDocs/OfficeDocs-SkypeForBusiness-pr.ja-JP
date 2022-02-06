---
title: ファイル共有の高可用性 (Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: b8c8d5ec-9397-4128-8d1e-8ec6c30fade7
description: DFS を使用して、ファイル共有の高可用性をSkype for Business Serverする方法について説明します。
---

# <a name="file-sharing-high-availability-in-skype-for-business-server"></a>ファイル共有の高可用性 (Skype for Business Server
 
DFS を使用して、ファイル共有の高可用性をSkype for Business Serverする方法について説明します。
  
展開でファイル共有の高可用性をSkype for Business Server分散ファイル システム (DFS) を使用できます。 DFS は、同一データ センター内の 1 台のファイル サーバーから別のファイル サーバーへのフェールオーバーをサポートします。 大規模展開に対しては、DFS を使用してペアにした専用ファイル サーバーを使用することをお勧めします。 DFS の詳細については、「Windows Server 2012」を参照してください[https://go.microsoft.com/fwlink/?LinkId=524384](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj127250(v=ws.11))。 サーバー 2008 の DFS のWindowsを参照してください[https://go.microsoft.com/fwlink/p/?LinkId=524385](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753479(v=ws.10))。
  
ネットワークの規模と必要な復元性に応じて、1 組のサーバーを使用してサイト内のすべてのファイル共有をホストするか、フロントエンド プールごとに 1 組のサーバーを使用できます。
  
DFS はベスト エフォート型のファイル レプリケーション メカニズムで、目標復旧時間 (RTO) または目標復旧ポイント (RPO) は公表されていません。 DFS サーバー間のフェールオーバーは迅速に完了する必要がありますが、データ レプリケーションの遅延により、フェールオーバーが発生した場合にユーザーが進行中の作業を続行できない場合があります。
  
DFS を使用し、ファイル共有上のデータ ストアが重要な場合は、4 ~ 8 時間ごとにファイル共有を頻繁にバックアップする必要があります。 1 つのファイル共有がダウンして、レプリケーションが最新ではない場合は、バックアップを使用して、障害が発生したサーバー上のコンテンツを、そのサーバーとペアになっている他のサーバーに復元できます。
