---
title: 高可用性と障害復旧に対応した常設チャット サーバーの構成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Persistent Chat Server for high availability and disaster recovery
ms:assetid: eebc581c-e3a0-4b69-8a43-80b607b4d8f2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205364(v=OCS.15)
ms:contentKeyID: 48185760
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c42edb14102b9bbf91b06804c365980a6e19345
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840191"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-persistent-chat-server-for-high-availability-and-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="117e7-102">Lync Server 2013 の高可用性と障害復旧に対応した常設チャット サーバーの構成</span><span class="sxs-lookup"><span data-stu-id="117e7-102">Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="117e7-103">_**最終更新日:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="117e7-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="117e7-104">Lync Server 2013 の常設チャットサーバーサービスは、障害回復のために*拡張プール*構成を使います。</span><span class="sxs-lookup"><span data-stu-id="117e7-104">The Lync Server 2013, Persistent Chat Server services use a *stretched pool* configuration for disaster recovery.</span></span> <span data-ttu-id="117e7-105">ストレッチプールは、2つの物理データセンターの間で配布され、1つの論理的な Lync Server サイト内にあるコンピューターを含むプールです。</span><span class="sxs-lookup"><span data-stu-id="117e7-105">A stretched pool is a pool that has computers that are distributed between two physical data centers, but are within a single logical Lync Server site.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="117e7-106">このセクション中</span><span class="sxs-lookup"><span data-stu-id="117e7-106">In This Section</span></span>

  - [<span data-ttu-id="117e7-107">Lync Server 2013 の常設チャット サーバーに必要なリソース</span><span class="sxs-lookup"><span data-stu-id="117e7-107">Required resources for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-required-resources-for-persistent-chat-server.md)

  - [<span data-ttu-id="117e7-108">Lync Server 2013 でトポロジ ビルダーを使用して高可用性と障害回復を構成する</span><span class="sxs-lookup"><span data-stu-id="117e7-108">Using Topology Builder to configure high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-using-topology-builder-to-configure-high-availability-and-disaster-recovery.md)

  - [<span data-ttu-id="117e7-109">Lync Server 2013 における障害回復のための拡張型の常設チャット サーバー プールの使用</span><span class="sxs-lookup"><span data-stu-id="117e7-109">Using a stretched Persistent Chat Server pool for disaster recovery in Lync Server 2013</span></span>](lync-server-2013-using-a-stretched-persistent-chat-server-pool-for-disaster-recovery.md)

  - [<span data-ttu-id="117e7-110">Lync Server 2013 での SQL Server のミラーリング</span><span class="sxs-lookup"><span data-stu-id="117e7-110">SQL Server mirroring in Lync Server 2013</span></span>](lync-server-2013-sql-server-mirroring.md)

  - [<span data-ttu-id="117e7-111">Lync Server 2013 で常設チャット サーバーのプライマリ データベースの SQL Server ログ配布を設定する</span><span class="sxs-lookup"><span data-stu-id="117e7-111">Setting up SQL Server Log Shipping in Lync Server 2013 for the Persistent Chat Server primary database</span></span>](lync-server-2013-setting-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database.md)

  - [<span data-ttu-id="117e7-112">Lync Server 2013 でのプライマリ ミラーとログ配布セカンダリ データベース間での SQL Server ログ配布のセットアップ</span><span class="sxs-lookup"><span data-stu-id="117e7-112">Setting up SQL Server Log Shipping between the primary mirror and the Log Shipping secondary database in Lync Server 2013</span></span>](lync-server-2013-setting-up-sql-server-log-shipping-between-the-primary-mirror-and-the-log-shipping-secondary-database.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

