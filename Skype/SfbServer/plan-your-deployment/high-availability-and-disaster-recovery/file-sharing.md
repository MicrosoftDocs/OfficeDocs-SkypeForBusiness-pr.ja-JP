---
title: Skype for Business Server 2015 のファイル共有の高可用性
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b8c8d5ec-9397-4128-8d1e-8ec6c30fade7
description: ビジネス サーバーは、DFS を使用して Skype でファイル共有の可用性を確認する方法について説明します。
ms.openlocfilehash: f96e4aaca70c501425528b12207eeab01027c9a9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="file-sharing-high-availability-in-skype-for-business-server-2015"></a><span data-ttu-id="50fbc-103">Skype for Business Server 2015 のファイル共有の高可用性</span><span class="sxs-lookup"><span data-stu-id="50fbc-103">File sharing high availability in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="50fbc-104">ビジネス サーバーは、DFS を使用して Skype でファイル共有の可用性を確認する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="50fbc-104">Learn about ensuring high availability of your file shares in Skype for Business Server, using DFS.</span></span>
  
<span data-ttu-id="50fbc-105">ビジネス サーバーの展開について、Skype でのファイル共有の高可用性を確保するには、分散ファイル システム (DFS) を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="50fbc-105">To ensure high availability for file sharing in your Skype for Business Server deployment, you can use the Distributed File System (DFS).</span></span> <span data-ttu-id="50fbc-106">DFS は、同一データ センター内の 1 台のファイル サーバーから別のファイル サーバーへのフェールオーバーをサポートします。</span><span class="sxs-lookup"><span data-stu-id="50fbc-106">DFS supports failover from one file server to another within the same data center.</span></span> <span data-ttu-id="50fbc-107">大規模展開に対しては、DFS を使用してペアにした専用ファイル サーバーを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="50fbc-107">For a large scale deployment, we recommend that you use dedicated file servers that are paired using DFS.</span></span> <span data-ttu-id="50fbc-108">Windows Server 2012 での DFS の詳細についてを参照してください[https://go.microsoft.com/fwlink/?LinkId=524384](https://go.microsoft.com/fwlink/?LinkId=524384)。</span><span class="sxs-lookup"><span data-stu-id="50fbc-108">For more information on DFS in Windows Server 2012, see [https://go.microsoft.com/fwlink/?LinkId=524384](https://go.microsoft.com/fwlink/?LinkId=524384).</span></span> <span data-ttu-id="50fbc-109">Windows Server 2008 の DFS の詳細についてを参照してください[https://go.microsoft.com/fwlink/p/?LinkId=524385](https://go.microsoft.com/fwlink/p/?LinkId=524385)。</span><span class="sxs-lookup"><span data-stu-id="50fbc-109">For information on DFS on Windows Server 2008, see [https://go.microsoft.com/fwlink/p/?LinkId=524385](https://go.microsoft.com/fwlink/p/?LinkId=524385).</span></span>
  
<span data-ttu-id="50fbc-110">によっては、ネットワークのサイズ、弾力性が必要なの量、サイト内のすべてのファイル共有をホストするサーバーの 1 つのペアを使用したり、フロント エンド プールごとに 1 つのペアを使用できます。</span><span class="sxs-lookup"><span data-stu-id="50fbc-110">Depending on your network's size, and the amount of resiliency you want, you can use one pair of servers to host all file shares in a site, or use one pair per Front End pool.</span></span>
  
<span data-ttu-id="50fbc-111">DFS はベスト エフォート型のファイル レプリケーション メカニズムで、目標復旧時間 (RTO) または目標復旧ポイント (RPO) は公表されていません。</span><span class="sxs-lookup"><span data-stu-id="50fbc-111">DFS is a best effort file replication mechanism, with no published recovery time objective (RTO) or recovery point objective (RPO) commitment.</span></span> <span data-ttu-id="50fbc-112">DFS サーバ間でフェイル オーバーを迅速に完了する必要がありますが、データのレプリケーションの遅延がありますように、フェールオーバーが発生する場合は、進行中の作業を続行することができません。</span><span class="sxs-lookup"><span data-stu-id="50fbc-112">A failover between DFS servers should be completed quickly, but data replication delay may prevent users from being able to continue work in progress when the failover happens.</span></span>
  
<span data-ttu-id="50fbc-p103">ファイル共有上での DFS およびデータ ストアの使用が不可欠な場合は、4 ～ 8 時間ごとなど、頻繁にファイル共有をバックアップする必要があります。1 つのファイル共有がダウンして、レプリケーションが最新ではない場合は、バックアップを使用して、障害が発生したサーバー上のコンテンツを、そのサーバーとペアになっている他のサーバーに復元できます。</span><span class="sxs-lookup"><span data-stu-id="50fbc-p103">If you use DFS and the data store on the fileshare is critical, you should back up the file shares frequently, such as every 4 to 8 hours. When one file share goes down and replication is not up to date, you can use the backup to restore the content on the failed server to the other server that is paired with the server that is now unavailable.</span></span>
  

