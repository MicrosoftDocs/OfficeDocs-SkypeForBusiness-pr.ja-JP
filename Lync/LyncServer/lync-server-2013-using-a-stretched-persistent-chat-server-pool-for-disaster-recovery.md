---
title: 障害復旧用に拡張常設チャットサーバープールを使用する
description: 障害復旧用に拡張常設チャットサーバープールを使用する。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using a stretched Persistent Chat Server pool for disaster recovery
ms:assetid: 74c5287e-d70d-490a-9adc-ab419917ddd9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205007(v=OCS.15)
ms:contentKeyID: 48184506
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b83a7226f7b9a49a2676b6222505f53247bd5abf
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548543"
---
# <a name="using-a-stretched-persistent-chat-server-pool-for-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="cfc0a-103">Lync Server 2013 での障害復旧のための拡張された常設チャットサーバープールの使用</span><span class="sxs-lookup"><span data-stu-id="cfc0a-103">Using a stretched Persistent Chat Server pool for disaster recovery in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cfc0a-104">_**トピックの最終更新日:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="cfc0a-104">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="cfc0a-105">常設チャットサーバーの障害復旧ソリューションは、拡張された常設チャットサーバープール上に構築されています。</span><span class="sxs-lookup"><span data-stu-id="cfc0a-105">The disaster recovery solution for Persistent Chat Server is built on a stretched Persistent Chat Server pool.</span></span> <span data-ttu-id="cfc0a-106">これは、Lync Server 2010 の大都市サイト復元に似ています。ただし、拡張された仮想ローカルエリアネットワーク (VLAN) は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="cfc0a-106">This is similar to metropolitan site resiliency in Lync Server 2010; however, there is no requirement for a stretched virtual local area network (VLAN).</span></span> <span data-ttu-id="cfc0a-107">常設チャットサーバープールをストレッチすることで、トポロジ内に論理的に1つのプールを構成することができますが、物理的には2つの異なるデータセンターにサーバーをプールに配置します。</span><span class="sxs-lookup"><span data-stu-id="cfc0a-107">By stretching Persistent Chat Server pool, you essentially configure one pool in the topology logically, but you physically place the servers in the pool in two different data centers.</span></span> <span data-ttu-id="cfc0a-108">データベースの SQL Server ミラーリングを同じ方法で構成し、データベースとミラーを同じデータセンターに展開します。</span><span class="sxs-lookup"><span data-stu-id="cfc0a-108">Configure SQL Server mirroring for the database in the same way, and deploy the database and the mirror in the same data center.</span></span> <span data-ttu-id="cfc0a-109">セカンダリデータセンターでバックアップデータベースを構成する必要があります (障害復旧時の高可用性を実現するためのオプションのミラーを備えています)。</span><span class="sxs-lookup"><span data-stu-id="cfc0a-109">You need to configure a backup database in the secondary data center (with an optional mirror to provide high availability during disaster recovery).</span></span> <span data-ttu-id="cfc0a-110">これは、障害復旧時のフェールオーバーに使用されるバックアップデータベースです。</span><span class="sxs-lookup"><span data-stu-id="cfc0a-110">This is the backup database used for failover during disaster recovery.</span></span>

<span data-ttu-id="cfc0a-111">高可用性を確保するために SQL Server ミラーリングを構成する方法の詳細については、「 [Lync server 2013 の Sql server ミラーリング](lync-server-2013-sql-server-mirroring.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cfc0a-111">For details about how to configure SQL Server mirroring for high availability, see [SQL Server mirroring in Lync Server 2013](lync-server-2013-sql-server-mirroring.md).</span></span> <span data-ttu-id="cfc0a-112">障害復旧のためにデータベースをフェールオーバーする詳細については、「 [Lync server 2013 での常設チャットサーバーのプライマリデータベースの Sql Server ログ配布の設定](lync-server-2013-setting-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database.md) 」と「 [プライマリミラーとログ配布のセカンダリデータベース間での Sql server ログ配布のセットアップ (lync server 2013](lync-server-2013-set-up-log-shipping-secondary-database.md))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cfc0a-112">For details about failing over the database for disaster recovery, see [Setting up SQL Server Log Shipping in Lync Server 2013 for the Persistent Chat Server primary database](lync-server-2013-setting-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database.md) and [Setting up SQL Server Log Shipping between the primary mirror and the Log Shipping secondary database in Lync Server 2013](lync-server-2013-set-up-log-shipping-secondary-database.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

