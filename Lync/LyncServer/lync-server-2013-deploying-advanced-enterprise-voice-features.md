---
title: 'Lync Server 2013: 高度なエンタープライズ Voip 機能の展開'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying advanced Enterprise Voice features
ms:assetid: 286d9c0b-9442-448f-a6e5-95b3034278fe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425753(v=OCS.15)
ms:contentKeyID: 48183675
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7fff128d98f82745e471f39e8f172c6ddb7a8a52
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833567"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-advanced-enterprise-voice-features-in-lync-server-2013"></a><span data-ttu-id="0cace-102">Lync Server 2013 での高度なエンタープライズ Voip 機能の展開</span><span class="sxs-lookup"><span data-stu-id="0cace-102">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0cace-103">_**最終更新日:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="0cace-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="0cace-104">組織に基本的なエンタープライズ VoIP 機能を構成した後は、このセクションの手順に従い、オプションで 1 つ以上の高度なエンタープライズ VoIP 機能を展開することができます。</span><span class="sxs-lookup"><span data-stu-id="0cace-104">After you have configured basic Enterprise Voice functionality for your organization, you can optionally deploy one or more advanced Enterprise Voice features by following the procedures in this section.</span></span>

<span data-ttu-id="0cace-105">高度なエンタープライズ Voip 機能の詳細については、「 [Lync Server 2013 の計画](lync-server-2013-planning.md)のドキュメント」の次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0cace-105">For details about the advanced Enterprise Voice features, see the following sections of the [Planning for Lync Server 2013](lync-server-2013-planning.md) documentation:</span></span>

  - [<span data-ttu-id="0cace-106">Lync Server 2013 での通話受付管理の計画</span><span class="sxs-lookup"><span data-stu-id="0cace-106">Planning for call admission control in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-admission-control.md)

  - [<span data-ttu-id="0cace-107">Lync Server 2013 での緊急サービス (E9-1-1) の計画</span><span class="sxs-lookup"><span data-stu-id="0cace-107">Planning for emergency services (E9-1-1) in Lync Server 2013</span></span>](lync-server-2013-planning-for-emergency-services-e9-1-1.md)

  - [<span data-ttu-id="0cace-108">Lync Server 2013 でのメディア バイパスの計画</span><span class="sxs-lookup"><span data-stu-id="0cace-108">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)

<div>

## <a name="in-this-section"></a><span data-ttu-id="0cace-109">このセクション中</span><span class="sxs-lookup"><span data-stu-id="0cace-109">In This Section</span></span>

  - [<span data-ttu-id="0cace-110">Lync Server 2013 ネットワーク領域、サイト、およびサブネットの構成</span><span class="sxs-lookup"><span data-stu-id="0cace-110">About network regions, sites, and subnets in Lync Server 2013</span></span>](lync-server-2013-about-network-regions-sites-and-subnets.md)

  - [<span data-ttu-id="0cace-111">Lync Server 2013 でネットワークの領域を作成または変更する</span><span class="sxs-lookup"><span data-stu-id="0cace-111">Create or modify a network region in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-region.md)

  - [<span data-ttu-id="0cace-112">Lync Server 2013 でのネットワーク サイトの作成または変更</span><span class="sxs-lookup"><span data-stu-id="0cace-112">Create or modify a network site in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-site.md)

  - [<span data-ttu-id="0cace-113">Lync Server 2013 でのネットワーク サイトとサブネットの関連付け</span><span class="sxs-lookup"><span data-stu-id="0cace-113">Associate a subnet with a network site in Lync Server 2013</span></span>](lync-server-2013-associate-a-subnet-with-a-network-site.md)

  - [<span data-ttu-id="0cace-114">Lync Server 2013 での通話受付制御の構成</span><span class="sxs-lookup"><span data-stu-id="0cace-114">Configure call admission control in Lync Server 2013</span></span>](lync-server-2013-configure-call-admission-control.md)

  - [<span data-ttu-id="0cace-115">Lync Server 2013 での Enhanced 9-1-1 の構成</span><span class="sxs-lookup"><span data-stu-id="0cace-115">Configure Enhanced 9-1-1 in Lync Server 2013</span></span>](lync-server-2013-configure-enhanced-9-1-1.md)

  - [<span data-ttu-id="0cace-116">Lync Server 2013 メディア バイパスの構成</span><span class="sxs-lookup"><span data-stu-id="0cace-116">Configure media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-media-bypass.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

