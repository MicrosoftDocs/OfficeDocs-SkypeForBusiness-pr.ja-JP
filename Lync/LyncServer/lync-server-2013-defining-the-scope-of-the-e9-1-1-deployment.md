---
title: 'Lync Server 2013: E9-1-1 展開の範囲の定義'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining the scope of the E9-1-1 deployment
ms:assetid: 2c572dfd-e901-471d-b5a0-18bc8d1d5328
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425775(v=OCS.15)
ms:contentKeyID: 48183707
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c84c6519ab561fef034fbe0990854087f22b2e41
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135153"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-the-scope-of-the-e9-1-1-deployment-in-lync-server-2013"></a><span data-ttu-id="52258-102">Lync Server 2013 での E9-1-1 展開の範囲の定義</span><span class="sxs-lookup"><span data-stu-id="52258-102">Defining the scope of the E9-1-1 deployment in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="52258-103">_**トピックの最終更新日:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="52258-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="52258-104">E9-1-1 用に Microsoft Lync Server 2013 を構成する前に、E9-1-1 展開を計画する必要があります。</span><span class="sxs-lookup"><span data-stu-id="52258-104">Before you configure Microsoft Lync Server 2013 for E9-1-1, you need to plan your E9-1-1 deployment.</span></span> <span data-ttu-id="52258-105">次のような点を検討します。</span><span class="sxs-lookup"><span data-stu-id="52258-105">Some of the questions to consider include:</span></span>

  - <span data-ttu-id="52258-106">**E9-1-1 に関して組織にどのようなポリシーと法的義務があるか**</span><span class="sxs-lookup"><span data-stu-id="52258-106">**What are your organization’s policy and legal obligations with regard to E9-1-1?**</span></span>  
    <span data-ttu-id="52258-107">PBX (E9-1-1 用語では複数回線電話システム (MLTS) と呼ばれます) 使用時の E9-1-1 の法的義務は州ごとに異なります。</span><span class="sxs-lookup"><span data-stu-id="52258-107">E9-1-1 legal requirements for PBXs (called Multi-line Telephone Systems, or MLTS, in E9-1-1 parlance) differ from state to state.</span></span> <span data-ttu-id="52258-108">該当する地域での Lync Server の展開に適用される可能性のある義務については、法務チームにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="52258-108">You should consult with your legal team to understand the obligations that may apply to your deployment of Lync Server in your relevant geographies.</span></span>

<!-- end list -->

  - <span data-ttu-id="52258-109">**エンタープライズ内のどの領域で E9-1-1 を有効にする必要があるか**</span><span class="sxs-lookup"><span data-stu-id="52258-109">**What areas within your enterprise need to be enabled for E9-1-1?**</span></span>  
    <span data-ttu-id="52258-p103">E9-1-1 は、エンタープライズ全体で有効にすることも、特定の場所だけで有効にすることもできます。たとえば、オフィスの E9-1-1 の要件が州によって異なる場合や、米国以外のサイトを除外する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="52258-p103">You can enable E9-1-1 for the entire enterprise or for selected locations. For example, you may have varying E9-1-1 requirements for offices in different states, or you may want to exclude sites outside the U.S.</span></span>

<!-- end list -->

  - <span data-ttu-id="52258-112">**E9-1-1 をブランチ サイトにどのように展開するか**</span><span class="sxs-lookup"><span data-stu-id="52258-112">**How will you deploy E9-1-1 to branch sites?**</span></span>  
    <span data-ttu-id="52258-113">E9-1-1 をブランチ サイトに展開するときは、音声の復元の概念を理解することが重要です。</span><span class="sxs-lookup"><span data-stu-id="52258-113">Voice resiliency is an important concept to understand when deploying E9-1-1 at a branch site.</span></span> <span data-ttu-id="52258-114">集中管理された電子 9-1-1 SIP トランクを使用していて、WAN の障害が発生した場合、サインインしているクライアントが場所情報サービスからの場所を取得したり、緊急サービスサービスプロバイダーに接続したりすることができない場合があります。</span><span class="sxs-lookup"><span data-stu-id="52258-114">If you have centralized E-9-1-1 SIP trunks and a WAN outage occurs, clients signing in may not be able to obtain a location from Location Information service or to connect to the emergency services service provider.</span></span> <span data-ttu-id="52258-115">Lync Server には、回復可能なデータネットワークがある場合、各ブランチに SIP トランクを展開する場合、停止時にローカルゲートウェイに緊急電話をかける場合など、ブランチオフィスの音声の復元を処理するためのいくつかの戦略が用意されています。</span><span class="sxs-lookup"><span data-stu-id="52258-115">Lync Server provides several strategies for handling voice resiliency in branch offices, including: having resilient data networks, deploying a SIP trunk at each branch, or pushing emergency calls out to the local gateway during outages.</span></span> <span data-ttu-id="52258-116">詳細については、「 [Lync Server 2013 でのブランチサイトの音声の復元の計画](lync-server-2013-planning-for-branch-site-voice-resiliency.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="52258-116">For details, see [Planning for branch-site voice resiliency in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md).</span></span>

<!-- end list -->

  - <span data-ttu-id="52258-117">**ネットワーク外のユーザーに対し、E9-1-1 を有効にするかどうか**</span><span class="sxs-lookup"><span data-stu-id="52258-117">**Will you enable E9-1-1 for users working outside the network?**</span></span>  
    <span data-ttu-id="52258-p105">自動的な位置情報の取得に対応しているのは、組織のネットワークの内部にあるクライアントだけです。このため、社外にある Lync クライアントからの E9-1-1 通話をサポートするかどうかを組織で決定する必要があります。たとえば、自宅や顧客サイトで作業をしているユーザーが緊急通話を行えるようにするかどうかを決定します。クライアントがエンタープライズ ネットワークの外部にある場合に、ユーザーに位置情報の入力を求めるようにクライアントを構成することはできます。しかし、ユーザーが入力する場所は事前に主要道路住所案内 (MSAG) と照合できないので、緊急サービスのサービス プロバイダー ディスパッチャーは通話を緊急情報受信センター (PSAP) にルーティングする前に、場所の有効性を発信者と口頭で確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="52258-p105">Automatic location acquisition is available only for clients located inside the organization’s network, so your organization needs to decide whether it will support E9-1-1 calls made from Lync clients while off-premises. For example, will you enable users to place emergency calls if they are working from home or from a customer site? If a client is located outside the enterprise network, the client can be configured to prompt the user for a location. However, because these user-provided locations cannot be prevalidated against the Master Street Address Guide (MSAG), the emergency services service provider dispatcher will need to confirm the validity of the location verbally with the caller before routing the call to the Public Safety Answering Point (PSAP).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="52258-122">VPN を使用して組織のネットワークに接続するユーザーの Lync クライアントは内部 IP アドレス情報を取得できますが、これらのアドレスを使用してユーザーの実際の場所を識別することは重要ではありません。 VPN サブネットは、場所情報サービス。</span><span class="sxs-lookup"><span data-stu-id="52258-122">Lync clients of users who connect to your organization’s network by using VPN can pick up internal IP address information, but because these addresses cannot be used to identify the user’s actual location, it is essential that VPN subnets are excluded from the Location Information service.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="52258-123">**米国以外のサイトに緊急通話のルーティングを提供するかどうか**</span><span class="sxs-lookup"><span data-stu-id="52258-123">**Do you want to provide emergency call routing to sites outside the U.S.?**</span></span>  
    <span data-ttu-id="52258-p106">緊急サービスのサービス プロバイダーのサービス対象範囲外 (国外の場所など) にある会社の領域に緊急通話のルーティングを提供したい場合があります。この場合は、新しいサイトを作成し、ローカル PSTN ゲートウェイ経由で通話をルーティングする PSTN 使用法を参照する音声ポリシーをサイトに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="52258-p106">You may want to provide emergency routing to areas of your company not served by an emergency services service provider (for example, international locations). To do this, create a new site, and then assign voice policies to the sites that refer to a PSTN usage that routes the call through the local PSTN gateway.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

