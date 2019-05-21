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
# <a name="file-sharing-high-availability-in-skype-for-business-server"></a><span data-ttu-id="01859-103">Skype for Business Server でのファイル共有の高可用性</span><span class="sxs-lookup"><span data-stu-id="01859-103">File sharing high availability in Skype for Business Server</span></span>
 
<span data-ttu-id="01859-104">ここでは、DFS を使用して、Skype for Business Server でファイル共有の高可用性を実現する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="01859-104">Learn about ensuring high availability of your file shares in Skype for Business Server, using DFS.</span></span>
  
<span data-ttu-id="01859-105">Skype for Business Server の展開でファイル共有の高可用性を確保するために、分散ファイルシステム (DFS) を使うことができます。</span><span class="sxs-lookup"><span data-stu-id="01859-105">To ensure high availability for file sharing in your Skype for Business Server deployment, you can use the Distributed File System (DFS).</span></span> <span data-ttu-id="01859-106">DFS は、同一データ センター内の 1 台のファイル サーバーから別のファイル サーバーへのフェールオーバーをサポートします。</span><span class="sxs-lookup"><span data-stu-id="01859-106">DFS supports failover from one file server to another within the same data center.</span></span> <span data-ttu-id="01859-107">大規模展開に対しては、DFS を使用してペアにした専用ファイル サーバーを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="01859-107">For a large scale deployment, we recommend that you use dedicated file servers that are paired using DFS.</span></span> <span data-ttu-id="01859-108">Windows Server 2012 の DFS の詳細については[https://go.microsoft.com/fwlink/?LinkId=524384](https://go.microsoft.com/fwlink/?LinkId=524384)、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="01859-108">For more information on DFS in Windows Server 2012, see [https://go.microsoft.com/fwlink/?LinkId=524384](https://go.microsoft.com/fwlink/?LinkId=524384).</span></span> <span data-ttu-id="01859-109">Windows Server 2008 上の DFS の詳細につい[https://go.microsoft.com/fwlink/p/?LinkId=524385](https://go.microsoft.com/fwlink/p/?LinkId=524385)ては、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="01859-109">For information on DFS on Windows Server 2008, see [https://go.microsoft.com/fwlink/p/?LinkId=524385](https://go.microsoft.com/fwlink/p/?LinkId=524385).</span></span>
  
<span data-ttu-id="01859-110">使用しているネットワークのサイズと回復性の量に応じて、1組のサーバーを使用して、サイト内のすべてのファイル共有をホストするか、フロントエンドプールごとに1つのペアを使うことができます。</span><span class="sxs-lookup"><span data-stu-id="01859-110">Depending on your network's size, and the amount of resiliency you want, you can use one pair of servers to host all file shares in a site, or use one pair per Front End pool.</span></span>
  
<span data-ttu-id="01859-111">DFS はベスト エフォート型のファイル レプリケーション メカニズムで、目標復旧時間 (RTO) または目標復旧ポイント (RPO) は公表されていません。</span><span class="sxs-lookup"><span data-stu-id="01859-111">DFS is a best effort file replication mechanism, with no published recovery time objective (RTO) or recovery point objective (RPO) commitment.</span></span> <span data-ttu-id="01859-112">DFS サーバー間のフェールオーバーはすぐに完了する必要がありますが、データレプリケーションの遅延によって、フェールオーバーの発生時に進行中の作業を続行することができなくなる場合があります。</span><span class="sxs-lookup"><span data-stu-id="01859-112">A failover between DFS servers should be completed quickly, but data replication delay may prevent users from being able to continue work in progress when the failover happens.</span></span>
  
<span data-ttu-id="01859-p103">ファイル共有上での DFS およびデータ ストアの使用が不可欠な場合は、4 ～ 8 時間ごとなど、頻繁にファイル共有をバックアップする必要があります。1 つのファイル共有がダウンして、レプリケーションが最新ではない場合は、バックアップを使用して、障害が発生したサーバー上のコンテンツを、そのサーバーとペアになっている他のサーバーに復元できます。</span><span class="sxs-lookup"><span data-stu-id="01859-p103">If you use DFS and the data store on the fileshare is critical, you should back up the file shares frequently, such as every 4 to 8 hours. When one file share goes down and replication is not up to date, you can use the backup to restore the content on the failed server to the other server that is paired with the server that is now unavailable.</span></span>
  

