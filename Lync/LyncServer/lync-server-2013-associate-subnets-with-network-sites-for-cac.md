---
title: 'Lync Server 2013: サブネットと CAC のネットワークサイトの関連付け'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Associate subnets with network sites for CAC
ms:assetid: a749c9b3-15f3-4e74-9f43-1507d3c2c940
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412786(v=OCS.15)
ms:contentKeyID: 48185017
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e431998ebb3836564dc73c7dc5a4d6b496653df1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044799"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="associate-subnets-with-network-sites-for-cac-in-lync-server-2013"></a><span data-ttu-id="95151-102">Lync Server 2013 での CAC のネットワークサイトへのサブネットの関連付け</span><span class="sxs-lookup"><span data-stu-id="95151-102">Associate subnets with network sites for CAC in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="95151-103">_**トピックの最終更新日:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="95151-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="95151-104">ネットワーク内のすべてのサブネットが、特定のネットワーク サイトに関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="95151-104">Every subnet in your network must be associated with a specific network site.</span></span> <span data-ttu-id="95151-105">これは、サブネット情報を使用して、エンドポイントが存在するネットワーク サイトを判断するためです。</span><span class="sxs-lookup"><span data-stu-id="95151-105">This is because subnet information is used to determine the network site on which an endpoint is located.</span></span> <span data-ttu-id="95151-106">セッション内の両方の当事者の場所がわかっている場合は、通話受付管理 (CAC) を使用して、通話を確立するのに十分な帯域幅があるかどうかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="95151-106">When the locations of both parties in a session are known, call admission control (CAC) can determine if there is sufficient bandwidth to establish a call.</span></span>

<span data-ttu-id="95151-107">通話受付管理には、サブネットをネットワークサイトに関連付けるための特別な要件はありません。</span><span class="sxs-lookup"><span data-stu-id="95151-107">Call admission control does not have any special requirements for associating subnets with network sites.</span></span> <span data-ttu-id="95151-108">トポロジ内のサブネットとネットワークサイトの間の関連付けを作成するには、「 [Lync Server 2013 のネットワークサイトにサブネットを関連付ける](lync-server-2013-associate-a-subnet-with-a-network-site.md)」の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="95151-108">To create an association between the subnets and network sites in your topology, follow the procedures in [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span></span> <span data-ttu-id="95151-109">通話受付管理のネットワークトポロジの例にあるネットワークサイト (およびそれぞれのサブネット) を表示するには、「計画」のドキュメントの「[例: Lync Server 2013 での通話受付管理の要件の収集](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95151-109">To view the network sites (and their respective subnets) in the example network topology for call admission control, see [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

