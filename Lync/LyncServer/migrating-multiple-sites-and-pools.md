---
title: 複数のサイトとプールの移行
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrating multiple sites and pools
ms:assetid: a6d726d2-564d-4b39-a97c-5656a673292a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205165(v=OCS.15)
ms:contentKeyID: 48185079
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b2f01303c7fe137253d8e993edb05e9562d963ff
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765255"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-multiple-sites-and-pools"></a><span data-ttu-id="51c94-102">複数のサイトとプールの移行</span><span class="sxs-lookup"><span data-stu-id="51c94-102">Migrating multiple sites and pools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="51c94-103">_**最終更新日:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="51c94-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="51c94-104">Lync Server 2013 は、複数サイトと複数プールの展開をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="51c94-104">Lync Server 2013 supports multi-site and multi-pool deployments.</span></span> <span data-ttu-id="51c94-105">複数のプールを Lync Server 2010 から Lync Server 2013 に移行するには、次の点を考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="51c94-105">The process of migrating multiple pools from Lync Server 2010 to Lync Server 2013 requires the following considerations:</span></span>

1.  <span data-ttu-id="51c94-106">Lync Server 2013 パイロットプールを展開した後、Lync Server 2013 プールに移動されるパイロットユーザーのサブセットと、ユーザーの機能を検証するための方法を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="51c94-106">After deploying a Lync Server 2013 pilot pool, you need to define a subset of pilot users that will be moved to the Lync Server 2013 pool, and a methodology for validating the functionality of the users.</span></span> <span data-ttu-id="51c94-107">たとえば、パイロットプールにユーザーを移動した後、ユーザーの会議ポリシーが Lync Server 2013 に移動されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="51c94-107">For example, after moving a user to the pilot pool, verify the user’s conference policy has moved to Lync Server 2013.</span></span>

2.  <span data-ttu-id="51c94-108">パイロットプールにエッジサーバーを展開した後、外部ユーザーが Lync Server 2013 プールと通信できることを検証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="51c94-108">After deploying an Edge Server in the pilot pool, you need to validate that external users can communicate with the Lync Server 2013 pool.</span></span>

3.  <span data-ttu-id="51c94-109">Lync Server 2010 エッジサーバーからのフェデレーションルートを試験的な Lync Server 2013 エッジサーバーに移行した後、フェデレーションされたユーザーが Lync Server 2013 プールと通信できることを検証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="51c94-109">After transitioning the federated routes from Lync Server 2010 Edge Servers to the pilot Lync Server 2013 Edge Servers, you need to validate that federated users can communicate with the Lync Server 2013 pool.</span></span>

4.  <span data-ttu-id="51c94-110">すべてのユーザーと非ユーザーの連絡先オブジェクトを移動した後、Lync Server 2010 プールが空であることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="51c94-110">After moving all the users and non-user contact objects, you need to validate that the Lync Server 2010 pool is empty.</span></span>

5.  <span data-ttu-id="51c94-111">Lync Server 2010 プールが空であることを確認した後、プールを非アクティブ化することができます。</span><span class="sxs-lookup"><span data-stu-id="51c94-111">After verifying that the Lync Server 2010 pool is empty, you can then deactivate the pool.</span></span>
    
    <span data-ttu-id="51c94-112">従来の Lync Server 2010 プールとサーバーを非アクティブ化する方法について詳しくは、「[フェーズ 8: レガシプールの廃止](phase-8-decommission-legacy-pools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="51c94-112">For details about how to deactivate the legacy Lync Server 2010 pool and servers, see [Phase 8: Decommission legacy pools](phase-8-decommission-legacy-pools.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

