---
title: 'Lync Server 2013: Lync Server 2013 ネットワークインフラストラクチャの管理'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing the Lync Server 2013 network infrastructure
ms:assetid: cb13456a-8f66-4595-be21-8887f30ad4eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182585(v=OCS.15)
ms:contentKeyID: 48185638
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 70f445130cfb9139c799bda789a5618a5983397d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42217743"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-the-lync-server-2013-network-infrastructure"></a><span data-ttu-id="ce750-102">Lync Server 2013 ネットワークインフラストラクチャの管理</span><span class="sxs-lookup"><span data-stu-id="ce750-102">Managing the Lync Server 2013 network infrastructure</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ce750-103">_**トピックの最終更新日:** 2014-02-11_</span><span class="sxs-lookup"><span data-stu-id="ce750-103">_**Topic Last Modified:** 2014-02-11_</span></span>

<span data-ttu-id="ce750-104">Microsoft Lync Server 2013 には、通話受付管理 (CAC) とメディアバイパスのサポートが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ce750-104">Microsoft Lync Server 2013 includes support for call admission control (CAC) and media bypass.</span></span> <span data-ttu-id="ce750-105">これらの機能を実装するには、音声とビデオの送信を規制する必要のある状況で帯域幅を管理できるように、地域、サイト、サブネットなどのネットワークを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ce750-105">To implement these features you must configure a network of regions, sites, subnets, and so on that will allow you to manage bandwidth in situations where audio and video transmissions need to be restricted.</span></span> <span data-ttu-id="ce750-106">サービスの品質 (QoS) ネットワーク テクノロジの使用も、音声およびビデオ通信の最適なエンドユーザー エクスペリエンスを提供するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ce750-106">You can also use the Quality of Service (QoS) networking technology to help provide an optimal end-user experience for audio and video communications.</span></span>

<span data-ttu-id="ce750-107">Lync Server コントロールパネルを使用して、CAC、メディアバイパス、および QoS をセットアップおよび管理できます。</span><span class="sxs-lookup"><span data-stu-id="ce750-107">You can use the Lync Server Control Panel to set up and manage CAC, media bypass, and QoS.</span></span> <span data-ttu-id="ce750-108">次のトピックで、これらの手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="ce750-108">The following topics provide steps for how to do this.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ce750-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="ce750-109">In This Section</span></span>

  - [<span data-ttu-id="ce750-110">Lync Server 2013 でのサービスの品質 (QoS) の管理</span><span class="sxs-lookup"><span data-stu-id="ce750-110">Managing Quality of Service (QoS) in Lync Server 2013</span></span>](lync-server-2013-managing-quality-of-service-qos.md)

  - [<span data-ttu-id="ce750-111">Lync Server 2013 での通話受付管理の管理</span><span class="sxs-lookup"><span data-stu-id="ce750-111">Managing call admission control in Lync Server 2013</span></span>](lync-server-2013-managing-call-admission-control.md)

  - [<span data-ttu-id="ce750-112">Lync Server 2013 ネットワークインターフェイス</span><span class="sxs-lookup"><span data-stu-id="ce750-112">Lync Server 2013 network interfaces</span></span>](lync-server-2013-lync-server-network-interfaces.md)

  - [<span data-ttu-id="ce750-113">サーバーメンテナンスのための Lync Server 2013 への新しい接続を禁止する</span><span class="sxs-lookup"><span data-stu-id="ce750-113">Prevent new connections to Lync Server 2013 for server maintenance</span></span>](lync-server-2013-prevent-new-connections-to-lync-server-for-server-maintenance.md)

  - [<span data-ttu-id="ce750-114">Lync Server 2013 の lync 通話品質の方法論</span><span class="sxs-lookup"><span data-stu-id="ce750-114">Lync Call Quality Methodology in Lync Server 2013</span></span>](lync-server-2013-poster-lync-call-quality-methodology.md)

  - [<span data-ttu-id="ce750-115">Lync Server 2013 の主要な正常性インジケーター</span><span class="sxs-lookup"><span data-stu-id="ce750-115">Key Health Indicators in Lync Server 2013</span></span>](lync-server-2013-poster-key-health-indicators.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

