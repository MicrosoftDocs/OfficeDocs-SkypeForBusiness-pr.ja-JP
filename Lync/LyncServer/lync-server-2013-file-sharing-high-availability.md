---
title: 'Lync Server 2013: ファイル共有の高可用性'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: File sharing high availability
ms:assetid: b8c8d5ec-9397-4128-8d1e-8ec6c30fade7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205203(v=OCS.15)
ms:contentKeyID: 48185238
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf27a7316494d24127f65309bdef347b558fade5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153699"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="file-sharing-high-availability-in-lync-server-2013"></a><span data-ttu-id="7a0f9-102">Lync Server 2013 でのファイル共有の高可用性</span><span class="sxs-lookup"><span data-stu-id="7a0f9-102">File sharing high availability in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7a0f9-103">_**トピックの最終更新日:** 2012-03-30_</span><span class="sxs-lookup"><span data-stu-id="7a0f9-103">_**Topic Last Modified:** 2012-03-30_</span></span>

<span data-ttu-id="7a0f9-104">単一のデータセンター内で Lync Server ファイル共有の高可用性を確保するために、分散ファイルシステム (DFS) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="7a0f9-104">To ensure high availability for Lync Server file sharing within a single data center, you can use the Distributed File System (DFS).</span></span> <span data-ttu-id="7a0f9-105">DFS は、同一データ センター内の 1 台のファイル サーバーから別のファイル サーバーへのフェールオーバーをサポートします。</span><span class="sxs-lookup"><span data-stu-id="7a0f9-105">DFS supports failover from one file server to another within the same data center.</span></span> <span data-ttu-id="7a0f9-106">大規模展開に対しては、DFS を使用してペアにした専用ファイル サーバーを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7a0f9-106">For a large scale deployment, we recommend that you use dedicated file servers that are paired using DFS.</span></span>

<span data-ttu-id="7a0f9-107">ネットワークの規模と必要な復元性に応じて、1 組のサーバーを使用してサイト内のすべてのファイル共有をホストするか、フロントエンド プールごとに 1 組のサーバーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="7a0f9-107">Depending on your network's size, and the amount of resiliency you want, you can use one pair of servers to host all file shares in a site, or use one pair per Front End pool.</span></span>

<span data-ttu-id="7a0f9-p102">DFS はベスト エフォート型のファイル レプリケーション メカニズムで、目標復旧時間 (RTO) または目標復旧ポイント (RPO) は公表されていません。DFS サーバー間のフェールオーバーは迅速に完了しますが、データ レプリケーションの遅延によって、フェールオーバー発生時に進行中だった作業をユーザーが続行できない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7a0f9-p102">DFS is a best effort file replication mechanism, with no published recovery time objective (RTO) or recovery point objective (RPO) commitment. The failover between the DFS servers should be completed quickly, but data replication delay may prevent users from being able to continue work in progress when the failover happens.</span></span>

<span data-ttu-id="7a0f9-p103">ファイル共有上での DFS およびデータ ストアの使用が不可欠な場合は、4 ～ 8 時間ごとなど、頻繁にファイル共有をバックアップする必要があります。1 つのファイル共有がダウンして、レプリケーションが最新ではない場合は、バックアップを使用して、障害が発生したサーバー上のコンテンツを、そのサーバーとペアになっている他のサーバーに復元できます。</span><span class="sxs-lookup"><span data-stu-id="7a0f9-p103">If you use DFS and data store on the fileshare is critical, you should back up the file shares frequently, such as every 4 to 8 hours. When one file share goes down and replication is not up to date, you can use the backup to restore the content on the failed server to the other server that is paired with the server that is now unavailable.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

