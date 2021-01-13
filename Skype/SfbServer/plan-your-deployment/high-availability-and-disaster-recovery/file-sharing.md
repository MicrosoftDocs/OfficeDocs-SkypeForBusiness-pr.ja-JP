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
# <a name="file-sharing-high-availability-in-skype-for-business-server"></a><span data-ttu-id="b18f1-103">Skype for Business Server でのファイル共有の高可用性</span><span class="sxs-lookup"><span data-stu-id="b18f1-103">File sharing high availability in Skype for Business Server</span></span>
 
<span data-ttu-id="b18f1-104">DFS を使用して、Skype for Business Server でファイル共有の高可用性を確保する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b18f1-104">Learn about ensuring high availability of your file shares in Skype for Business Server, using DFS.</span></span>
  
<span data-ttu-id="b18f1-105">Skype for Business Server 展開でファイル共有の高可用性を確保するには、分散ファイル システム (DFS) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="b18f1-105">To ensure high availability for file sharing in your Skype for Business Server deployment, you can use the Distributed File System (DFS).</span></span> <span data-ttu-id="b18f1-106">DFS は、同一データ センター内の 1 台のファイル サーバーから別のファイル サーバーへのフェールオーバーをサポートします。</span><span class="sxs-lookup"><span data-stu-id="b18f1-106">DFS supports failover from one file server to another within the same data center.</span></span> <span data-ttu-id="b18f1-107">大規模展開に対しては、DFS を使用してペアにした専用ファイル サーバーを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b18f1-107">For a large scale deployment, we recommend that you use dedicated file servers that are paired using DFS.</span></span> <span data-ttu-id="b18f1-108">DFS の詳細については、「Windows Server 2012」を参照してください [https://go.microsoft.com/fwlink/?LinkId=524384](https://go.microsoft.com/fwlink/?LinkId=524384) 。</span><span class="sxs-lookup"><span data-stu-id="b18f1-108">For more information on DFS in Windows Server 2012, see [https://go.microsoft.com/fwlink/?LinkId=524384](https://go.microsoft.com/fwlink/?LinkId=524384).</span></span> <span data-ttu-id="b18f1-109">Windows Server 2008 の DFS の詳細については、以下を参照してください [https://go.microsoft.com/fwlink/p/?LinkId=524385](https://go.microsoft.com/fwlink/p/?LinkId=524385) 。</span><span class="sxs-lookup"><span data-stu-id="b18f1-109">For information on DFS on Windows Server 2008, see [https://go.microsoft.com/fwlink/p/?LinkId=524385](https://go.microsoft.com/fwlink/p/?LinkId=524385).</span></span>
  
<span data-ttu-id="b18f1-110">ネットワークの規模と必要な復元性に応じて、1 組のサーバーを使用してサイト内のすべてのファイル共有をホストするか、フロントエンド プールごとに 1 組のサーバーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="b18f1-110">Depending on your network's size, and the amount of resiliency you want, you can use one pair of servers to host all file shares in a site, or use one pair per Front End pool.</span></span>
  
<span data-ttu-id="b18f1-111">DFS はベスト エフォート型のファイル レプリケーション メカニズムで、目標復旧時間 (RTO) または目標復旧ポイント (RPO) は公表されていません。</span><span class="sxs-lookup"><span data-stu-id="b18f1-111">DFS is a best effort file replication mechanism, with no published recovery time objective (RTO) or recovery point objective (RPO) commitment.</span></span> <span data-ttu-id="b18f1-112">DFS サーバー間のフェールオーバーは迅速に完了する必要がありますが、データ レプリケーションの遅延により、フェールオーバーが発生した場合にユーザーが進行中の作業を続行できない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b18f1-112">A failover between DFS servers should be completed quickly, but data replication delay may prevent users from being able to continue work in progress when the failover happens.</span></span>
  
<span data-ttu-id="b18f1-113">DFS を使用し、ファイル共有上のデータ ストアが重要な場合は、4 ~ 8 時間ごとにファイル共有を頻繁にバックアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b18f1-113">If you use DFS and the data store on the fileshare is critical, you should back up the file shares frequently, such as every 4 to 8 hours.</span></span> <span data-ttu-id="b18f1-114">1 つのファイル共有がダウンして、レプリケーションが最新ではない場合は、バックアップを使用して、障害が発生したサーバー上のコンテンツを、そのサーバーとペアになっている他のサーバーに復元できます。</span><span class="sxs-lookup"><span data-stu-id="b18f1-114">When one file share goes down and replication is not up to date, you can use the backup to restore the content on the failed server to the other server that is paired with the server that is now unavailable.</span></span>
  

