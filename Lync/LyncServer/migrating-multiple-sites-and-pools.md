---
title: 複数のサイトとプールの移行
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrating multiple sites and pools
ms:assetid: a6d726d2-564d-4b39-a97c-5656a673292a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205165(v=OCS.15)
ms:contentKeyID: 48185079
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d95f38ab0adc1457abee7cdd90e8f385f7176ce3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527364"
---
# <a name="migrating-multiple-sites-and-pools"></a><span data-ttu-id="3223c-102">複数のサイトとプールの移行</span><span class="sxs-lookup"><span data-stu-id="3223c-102">Migrating multiple sites and pools</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3223c-103">_**トピックの最終更新日:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="3223c-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="3223c-104">Lync Server 2013 では、複数サイトと複数プールの展開がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="3223c-104">Lync Server 2013 supports multi-site and multi-pool deployments.</span></span> <span data-ttu-id="3223c-105">Lync Server 2010 から Lync Server 2013 に複数のプールを移行するプロセスには、以下の点を考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3223c-105">The process of migrating multiple pools from Lync Server 2010 to Lync Server 2013 requires the following considerations:</span></span>

1.  <span data-ttu-id="3223c-106">Lync Server 2013 パイロットプールを展開した後は、Lync Server 2013 プールに移動するパイロットユーザーのサブセットと、ユーザーの機能を検証するための方法を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3223c-106">After deploying a Lync Server 2013 pilot pool, you need to define a subset of pilot users that will be moved to the Lync Server 2013 pool, and a methodology for validating the functionality of the users.</span></span> <span data-ttu-id="3223c-107">たとえば、ユーザーをパイロットプールに移動した後、ユーザーの会議ポリシーが Lync Server 2013 に移動されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="3223c-107">For example, after moving a user to the pilot pool, verify the user’s conference policy has moved to Lync Server 2013.</span></span>

2.  <span data-ttu-id="3223c-108">パイロットプールにエッジサーバーを展開した後、外部ユーザーが Lync Server 2013 プールと通信できることを検証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3223c-108">After deploying an Edge Server in the pilot pool, you need to validate that external users can communicate with the Lync Server 2013 pool.</span></span>

3.  <span data-ttu-id="3223c-109">Lync server 2010 エッジサーバーから lync Server 2013 エッジサーバーへのフェデレーションルートを移行した後、フェデレーションユーザーが Lync Server 2013 プールと通信できることを検証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3223c-109">After transitioning the federated routes from Lync Server 2010 Edge Servers to the pilot Lync Server 2013 Edge Servers, you need to validate that federated users can communicate with the Lync Server 2013 pool.</span></span>

4.  <span data-ttu-id="3223c-110">ユーザーおよびユーザー以外のすべての連絡先オブジェクトを移動した後、Lync Server 2010 プールが空であることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3223c-110">After moving all the users and non-user contact objects, you need to validate that the Lync Server 2010 pool is empty.</span></span>

5.  <span data-ttu-id="3223c-111">Lync Server 2010 プールが空であることを確認した後、プールを非アクティブ化することができます。</span><span class="sxs-lookup"><span data-stu-id="3223c-111">After verifying that the Lync Server 2010 pool is empty, you can then deactivate the pool.</span></span>
    
    <span data-ttu-id="3223c-112">従来の Lync Server 2010 プールおよびサーバーを非アクティブ化する方法の詳細については、「 [フェーズ 8: 従来のプール](phase-8-decommission-legacy-pools.md)を使用停止にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3223c-112">For details about how to deactivate the legacy Lync Server 2010 pool and servers, see [Phase 8: Decommission legacy pools](phase-8-decommission-legacy-pools.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

