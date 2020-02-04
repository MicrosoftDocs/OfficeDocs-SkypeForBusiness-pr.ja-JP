---
title: 'Lync Server 2013: 通話受付制御の管理'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing call admission control
ms:assetid: b0bd4783-6f47-408d-b010-2e30f9bc1770
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721851(v=OCS.15)
ms:contentKeyID: 49733784
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 11cd9e2bb894f5fcb2230d08939d29852fba3fcd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738817"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="7a6d5-102">Lync Server 2013 での通話受付制御の管理</span><span class="sxs-lookup"><span data-stu-id="7a6d5-102">Managing call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7a6d5-103">_**最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="7a6d5-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="7a6d5-104">通話受付管理 (CAC) では、利用可能なネットワーク帯域幅に基づいて、音声通話やビデオ通話などのリアルタイム コミュニケーションのセッションの確立を許可するかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="7a6d5-104">Call admission control (CAC) determines, based on available network bandwidth, whether to allow real-time communications sessions such as voice or video calls to be established.</span></span> <span data-ttu-id="7a6d5-105">次の手順を使用して、Lync Server 2013 環境のさまざまな CAC 機能を管理します。</span><span class="sxs-lookup"><span data-stu-id="7a6d5-105">Use the following procedures to manage different CAC features for your Lync Server 2013 environment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="7a6d5-106">このセクション中</span><span class="sxs-lookup"><span data-stu-id="7a6d5-106">In This Section</span></span>

  - [<span data-ttu-id="7a6d5-107">Lync Server 2013 での通話受付制御の有効化</span><span class="sxs-lookup"><span data-stu-id="7a6d5-107">Enabling call admission control in Lync Server 2013</span></span>](lync-server-2013-enabling-call-admission-control.md)

  - [<span data-ttu-id="7a6d5-108">Lync Server 2013 でのネットワーク帯域幅ポリシープロファイルの管理</span><span class="sxs-lookup"><span data-stu-id="7a6d5-108">Managing network bandwidth policy profiles in Lync Server 2013</span></span>](lync-server-2013-managing-network-bandwidth-policy-profiles.md)

  - [<span data-ttu-id="7a6d5-109">Lync Server 2013 のネットワーク領域</span><span class="sxs-lookup"><span data-stu-id="7a6d5-109">Network regions in Lync Server 2013</span></span>](lync-server-2013-network-regions.md)

  - [<span data-ttu-id="7a6d5-110">Lync Server 2013 のネットワーク領域ルート</span><span class="sxs-lookup"><span data-stu-id="7a6d5-110">Network region routes in Lync Server 2013</span></span>](lync-server-2013-network-region-routes.md)

  - [<span data-ttu-id="7a6d5-111">Lync Server 2013 でのサイトの通話受付制御</span><span class="sxs-lookup"><span data-stu-id="7a6d5-111">Call admission control for sites in Lync Server 2013</span></span>](lync-server-2013-call-admission-control-for-sites.md)

  - [<span data-ttu-id="7a6d5-112">Lync Server 2013 でメディアのバイパスを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="7a6d5-112">Enabling and disabling media bypass in Lync Server 2013</span></span>](lync-server-2013-enabling-and-disabling-media-bypass.md)

  - [<span data-ttu-id="7a6d5-113">Lync Server 2013 でのネットワーク領域のリンク</span><span class="sxs-lookup"><span data-stu-id="7a6d5-113">Linking network regions in Lync Server 2013</span></span>](lync-server-2013-linking-network-regions.md)

  - [<span data-ttu-id="7a6d5-114">Lync Server 2013 でのネットワークサブネットの管理</span><span class="sxs-lookup"><span data-stu-id="7a6d5-114">Managing network subnets in Lync Server 2013</span></span>](lync-server-2013-managing-network-subnets.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7a6d5-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="7a6d5-115">See Also</span></span>


[<span data-ttu-id="7a6d5-116">Lync Server 2013 の通話受付制御の概要</span><span class="sxs-lookup"><span data-stu-id="7a6d5-116">Overview of call admission control in Lync Server 2013</span></span>](lync-server-2013-overview-of-call-admission-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

