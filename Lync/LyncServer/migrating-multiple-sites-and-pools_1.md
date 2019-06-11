---
title: 複数のサイトとプールの移行
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrating multiple sites and pools
ms:assetid: 3bf677d4-a5af-4f73-8fad-1abf5b668cc1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688025(v=OCS.15)
ms:contentKeyID: 49733615
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7412d0ffb1a5d24c2f30b76b987a16903253bfb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848063"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-multiple-sites-and-pools"></a><span data-ttu-id="3b212-102">複数のサイトとプールの移行</span><span class="sxs-lookup"><span data-stu-id="3b212-102">Migrating multiple sites and pools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3b212-103">_**最終更新日:** 2012-08-26_</span><span class="sxs-lookup"><span data-stu-id="3b212-103">_**Topic Last Modified:** 2012-08-26_</span></span>

<span data-ttu-id="3b212-104">Lync Server 2013 は、複数サイトと複数プールの展開をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="3b212-104">Lync Server 2013 supports multi-site and multi-pool deployments.</span></span> <span data-ttu-id="3b212-105">複数のプールを Office Communications Server 2007 R2 から Lync Server 2013 に移行するには、次の点を考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3b212-105">The process of migrating multiple pools from Office Communications Server 2007 R2 to Lync Server 2013 requires the following considerations:</span></span>

1.  <span data-ttu-id="3b212-106">Lync Server 2013 パイロットプールを展開した後、Lync Server 2013 プールに移動されるパイロットユーザーのサブセットと、ユーザーの機能を検証するための方法を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3b212-106">After deploying a Lync Server 2013 pilot pool, you need to define a subset of pilot users that will be moved to the Lync Server 2013 pool, and a methodology for validating the functionality of the users.</span></span>

2.  <span data-ttu-id="3b212-107">パイロットプールにエッジサーバーを展開した後、外部ユーザーが Lync Server 2013 プールと通信できることを検証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3b212-107">After deploying an Edge Server in the pilot pool, you need to validate that external users can communicate with the Lync Server 2013 pool.</span></span>

3.  <span data-ttu-id="3b212-108">Office Communications Server 2007 R2 Edge サーバーからのフェデレーションルートを試験的な Lync Server 2013 エッジサーバーに移行した後、フェデレーションされたユーザーが Lync Server 2013 プールと通信できることを検証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3b212-108">After transitioning the federated routes from Office Communications Server 2007 R2 Edge Servers to the pilot Lync Server 2013 Edge Servers, you need to validate that federated users can communicate with the Lync Server 2013 pool.</span></span>

4.  <span data-ttu-id="3b212-109">すべてのユーザーと非ユーザーの連絡先オブジェクトを移動した後、Office Communications Server 2007 R2 プールが空であることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3b212-109">After moving all the users and non-user contact objects, you need to validate that the Office Communications Server 2007 R2 pool is empty.</span></span>

5.  <span data-ttu-id="3b212-110">Office Communications Server 2007 R2 プールが空であることを確認した後、プールを非アクティブ化することができます。</span><span class="sxs-lookup"><span data-stu-id="3b212-110">After verifying that the Office Communications Server 2007 R2 pool is empty, you can then deactivate the pool.</span></span>
    
    <span data-ttu-id="3b212-111">従来の Office Communications Server 2007 R2 プールおよびサーバーを非アクティブ化する方法について詳しくは、「[フェーズ 10: レガシサイトの廃止](phase-10-decommission-legacy-site.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3b212-111">For details about how to deactivate the legacy Office Communications Server 2007 R2 pool and servers, see [Phase 10: Decommission legacy site](phase-10-decommission-legacy-site.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

