---
title: 高可用性および障害復旧のための常設チャットサーバーの構成
description: 高可用性および障害復旧のために常設チャットサーバーを構成する。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Persistent Chat Server for high availability and disaster recovery
ms:assetid: eebc581c-e3a0-4b69-8a43-80b607b4d8f2
ms:mtpsurl: https://technet.microsoft.com/library/JJ205364(v=OCS.15)
ms:contentKeyID: 48185760
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 13935f2ec690deb7f896c13d185680ce1122a892
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544833"
---
# <a name="configuring-persistent-chat-server-for-high-availability-and-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="9a288-103">Lync Server 2013 での高可用性および障害復旧用の常設チャットサーバーの構成</span><span class="sxs-lookup"><span data-stu-id="9a288-103">Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9a288-104">_**トピックの最終更新日:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="9a288-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="9a288-105">Lync Server 2013、常設チャットサーバーサービスは、障害復旧用に拡張された *プール* 構成を使用します。</span><span class="sxs-lookup"><span data-stu-id="9a288-105">The Lync Server 2013, Persistent Chat Server services use a *stretched pool* configuration for disaster recovery.</span></span> <span data-ttu-id="9a288-106">ストレッチプールは、2つの物理的なデータセンター間に分散されたコンピューターを持つプールですが、1つの論理的な Lync Server サイトに含まれています。</span><span class="sxs-lookup"><span data-stu-id="9a288-106">A stretched pool is a pool that has computers that are distributed between two physical data centers, but are within a single logical Lync Server site.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="9a288-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="9a288-107">In This Section</span></span>

  - [<span data-ttu-id="9a288-108">Lync Server 2013 の常設チャットサーバーに必要なリソース</span><span class="sxs-lookup"><span data-stu-id="9a288-108">Required resources for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-required-resources-for-persistent-chat-server.md)

  - [<span data-ttu-id="9a288-109">トポロジビルダーを使用して Lync Server 2013 での高可用性および障害復旧を構成する</span><span class="sxs-lookup"><span data-stu-id="9a288-109">Using Topology Builder to configure high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-using-topology-builder-to-configure-high-availability-and-disaster-recovery.md)

  - [<span data-ttu-id="9a288-110">Lync Server 2013 での障害復旧のための拡張された常設チャットサーバープールの使用</span><span class="sxs-lookup"><span data-stu-id="9a288-110">Using a stretched Persistent Chat Server pool for disaster recovery in Lync Server 2013</span></span>](lync-server-2013-using-a-stretched-persistent-chat-server-pool-for-disaster-recovery.md)

  - [<span data-ttu-id="9a288-111">Lync Server 2013 での SQL Server のミラーリング</span><span class="sxs-lookup"><span data-stu-id="9a288-111">SQL Server mirroring in Lync Server 2013</span></span>](lync-server-2013-sql-server-mirroring.md)

  - [<span data-ttu-id="9a288-112">常設チャットサーバーのプライマリデータベースのための Lync Server 2013 での SQL Server ログ配布のセットアップ</span><span class="sxs-lookup"><span data-stu-id="9a288-112">Setting up SQL Server Log Shipping in Lync Server 2013 for the Persistent Chat Server primary database</span></span>](lync-server-2013-setting-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database.md)

  - [<span data-ttu-id="9a288-113">Lync Server 2013 のプライマリミラーとログ配布セカンダリデータベース間での SQL Server ログ配布のセットアップ</span><span class="sxs-lookup"><span data-stu-id="9a288-113">Setting up SQL Server Log Shipping between the primary mirror and the Log Shipping secondary database in Lync Server 2013</span></span>](lync-server-2013-set-up-log-shipping-secondary-database.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

