---
title: 'Lync Server 2013: 監視の計画'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for monitoring
ms:assetid: 26cead5a-183c-42f1-a4b0-0e8d61c6159d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204752(v=OCS.15)
ms:contentKeyID: 48183671
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 54d5af3506eccd9cccfd3771d0e983f62bfaad15
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48497644"
---
# <a name="planning-for-monitoring-in-lync-server-2013"></a><span data-ttu-id="4924d-102">Lync Server 2013 での監視の計画</span><span class="sxs-lookup"><span data-stu-id="4924d-102">Planning for monitoring in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4924d-103">_**トピックの最終更新日:** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="4924d-103">_**Topic Last Modified:** 2012-09-05_</span></span>

<span data-ttu-id="4924d-104">Microsoft Lync Server 2013 の監視サービスを使用すると、管理者は組織内で発生する通信セッションの利用状況、傾向、およびサービスの品質データを収集することができます。</span><span class="sxs-lookup"><span data-stu-id="4924d-104">The monitoring service in Microsoft Lync Server 2013 provides a way for administrators to collect usage, trend, and quality of service data for the communication sessions that take place in their organization.</span></span> <span data-ttu-id="4924d-105">Lync Server 2013 での監視では、別のサーバーの役割は不要になりました。代わりに、監視サービスは各フロントエンドサーバーに組み込まれます。</span><span class="sxs-lookup"><span data-stu-id="4924d-105">Monitoring in Lync Server 2013 no longer requires a separate server role; instead, the monitoring service is built into each Front End server.</span></span> <span data-ttu-id="4924d-106">ただし、Lync Server 2013 では既定の監視が有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="4924d-106">However, by default monitoring is not enabled in Lync Server 2013.</span></span> <span data-ttu-id="4924d-107">このドキュメントは、組織で監視を有効にする必要があるかどうかを判断するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="4924d-107">This document will help you determine whether or not monitoring should be enabled in your organization.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="4924d-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="4924d-108">In This Section</span></span>

  - [<span data-ttu-id="4924d-109">Lync Server 2013 での監視の概要</span><span class="sxs-lookup"><span data-stu-id="4924d-109">Overview of monitoring in Lync Server 2013</span></span>](lync-server-2013-overview-of-monitoring.md)

  - [<span data-ttu-id="4924d-110">Lync Server 2013 での監視要件の定義</span><span class="sxs-lookup"><span data-stu-id="4924d-110">Defining your requirements for monitoring in Lync Server 2013</span></span>](lync-server-2013-defining-your-requirements-for-monitoring.md)

  - [<span data-ttu-id="4924d-111">Lync Server 2013 での監視の有効化</span><span class="sxs-lookup"><span data-stu-id="4924d-111">Enabling monitoring in Lync Server 2013</span></span>](lync-server-2013-enabling-monitoring.md)

  - [<span data-ttu-id="4924d-112">Lync Server 2013 での監視データへのアクセス</span><span class="sxs-lookup"><span data-stu-id="4924d-112">Accessing monitoring data in Lync Server 2013</span></span>](lync-server-2013-accessing-monitoring-data.md)

  - [<span data-ttu-id="4924d-113">Lync Server 2013 で監視するためのコンポーネントとトポロジ</span><span class="sxs-lookup"><span data-stu-id="4924d-113">Components and topologies for monitoring in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-monitoring.md)

  - [<span data-ttu-id="4924d-114">Lync Server 2013 での監視の展開チェックリスト</span><span class="sxs-lookup"><span data-stu-id="4924d-114">Deployment checklist for monitoring in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-monitoring.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

