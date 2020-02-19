---
title: 'Lync Server 2013: 通話受付管理の要件の定義'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your organization's requirements for call admission control
ms:assetid: 5122171a-a5b0-4059-b033-846caec10d1e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398334(v=OCS.15)
ms:contentKeyID: 48184104
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: adc067156647a748aaccffeafa97b932e123fbfe
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137828"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="3f418-102">Lync Server 2013 での通話受付管理の要件の定義</span><span class="sxs-lookup"><span data-stu-id="3f418-102">Defining your requirements for call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3f418-103">_**トピックの最終更新日:** 2013-10-28_</span><span class="sxs-lookup"><span data-stu-id="3f418-103">_**Topic Last Modified:** 2013-10-28_</span></span>

<span data-ttu-id="3f418-p101">通話受付管理 (CAC) を計画するには、エンタープライズ ネットワーク トポロジに関する詳細な情報が必要です。 通話受付管理ポリシーの計画を容易にするために、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="3f418-p101">Planning for call admission control (CAC) requires detailed information about your enterprise network topology. To help plan your call admission control policies, follow these steps.</span></span>

1.  <span data-ttu-id="3f418-106">エンタープライズ ネットワーク内のハブ/バックボーン (\*\* ネットワーク地域) を特定します。</span><span class="sxs-lookup"><span data-stu-id="3f418-106">Identify the hubs/backbones (called *network regions*) within your enterprise network.</span></span>

2.  <span data-ttu-id="3f418-107">各ネットワーク地域内のオフィスまたは拠点 (\*\* ネットワーク サイト) を特定します。</span><span class="sxs-lookup"><span data-stu-id="3f418-107">Identify the offices or locations (called *network sites*) within each network region.</span></span>

3.  <span data-ttu-id="3f418-108">ネットワーク地域の各ペア間のネットワーク ルートを決定します。</span><span class="sxs-lookup"><span data-stu-id="3f418-108">Determine the network route between every pair of network regions.</span></span>

4.  <span data-ttu-id="3f418-109">各 WAN リンクの帯域幅制限を決定します。</span><span class="sxs-lookup"><span data-stu-id="3f418-109">Determine the bandwidth limits for each WAN link.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3f418-110">帯域幅制限は、エンタープライズ Voip および音声/ビデオトラフィックに対して WAN リンクの帯域幅をどの程度割り当てるかを表します。</span><span class="sxs-lookup"><span data-stu-id="3f418-110">Bandwidth limits refer to how much of the bandwidth on a WAN link is allocated to Enterprise Voice and audio/video traffic.</span></span> <span data-ttu-id="3f418-111">帯域幅の上限が予測ピーク トラフィックよりも少ない場合、その WAN リンクは "帯域幅が制限された" WAN リンクと表現されています。</span><span class="sxs-lookup"><span data-stu-id="3f418-111">When a WAN link is described as “bandwidth-constrained,” the WAN link has a bandwidth limit that is lower than the expected peak traffic over the link.</span></span>

    
    </div>

5.  <span data-ttu-id="3f418-112">各ネットワーク サイトに割り当てる IP サブネットを特定します。</span><span class="sxs-lookup"><span data-stu-id="3f418-112">Identify the IP subnets that are assigned to each network site.</span></span>

<span data-ttu-id="3f418-113">これらの概念を説明するために、次の図に示すネットワーク トポロジの例を使用します。</span><span class="sxs-lookup"><span data-stu-id="3f418-113">To explain these concepts, we’ll use the example network topology shown in the following figure.</span></span>

<span data-ttu-id="3f418-114">**通話受付管理のトポロジの例**</span><span class="sxs-lookup"><span data-stu-id="3f418-114">**Example topology for call admission control**</span></span>

<span data-ttu-id="3f418-115">![Litware-sql Inc ネットワークトポロジの例](images/Gg398334.477f3b52-2973-4026-9bc0-b1c6bf9f4803(OCS.15).jpg "Litware-sql Inc ネットワークトポロジの例")</span><span class="sxs-lookup"><span data-stu-id="3f418-115">![Litware Inc. Network Topology Example](images/Gg398334.477f3b52-2973-4026-9bc0-b1c6bf9f4803(OCS.15).jpg "Litware Inc. Network Topology Example")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3f418-p103">すべてのネットワーク サイトはネットワーク地域に関連付けられています。たとえば、ポートランド、リノ、およびアルバカーキは北アメリカ地域に含まれています。この図には、帯域幅制限があり、CAC ポリシーが適用されている WAN リンクのみが示されています。シカゴ、ニューヨーク、デトロイトの各ネットワーク サイトは北アメリカ地域の楕円内に示されています。これらは帯域幅が制限されていないので、CAC ポリシーが不要であるためです。</span><span class="sxs-lookup"><span data-stu-id="3f418-p103">All network sites are associated with a network region. For example, Portland, Reno, and Albuquerque are included in the North America region. In this figure, only WAN links that have CAC policies applied are shown, with bandwidth limits. The network sites of Chicago, New York, and Detroit are shown inside the North America region oval because they are not bandwidth-constrained, and therefore do not require CAC policies.</span></span>



</div>

<span data-ttu-id="3f418-120">このトポロジ例の各コンポーネントについて、以下のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="3f418-120">The components of this example topology are explained in the following sections.</span></span> <span data-ttu-id="3f418-121">このトポロジがどのように計画されたかの詳細については、「[例: Lync Server 2013 での通話受付管理の要件の収集](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3f418-121">For details about how this topology was planned, including the bandwidth limits, see [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md).</span></span>

<div>

## <a name="identify-network-regions"></a><span data-ttu-id="3f418-122">ネットワーク地域の特定</span><span class="sxs-lookup"><span data-stu-id="3f418-122">Identify Network Regions</span></span>

<span data-ttu-id="3f418-123">ネットワーク地域とは、ネットワーク バックボーンまたはネットワーク ハブを示します。</span><span class="sxs-lookup"><span data-stu-id="3f418-123">A network region represents a network backbone or a network hub.</span></span>

<span data-ttu-id="3f418-p105">ネットワークのバックボーンまたはハブは、ネットワークのさまざまな部分を相互接続するコンピューター ネットワーク インフラストラクチャの一部で、異なる LAN またはサブネット間で情報を交換するためのパスを提供します。 バックボーンは、小さな地域から地理的に広範囲な地域までさまざまなネットワークを結合できます。 通常、バックボーンの処理能力はバックボーンに接続するネットワークの処理能力よりも高くなっています。</span><span class="sxs-lookup"><span data-stu-id="3f418-p105">A network backbone or hub is a part of computer network infrastructure that interconnects different parts of the network, providing a path for the exchange of information between different LANs or subnets. A backbone can tie together diverse networks from a small location to a wide geographic area. The backbone's capacity is typically greater than that of the networks that connect to it.</span></span>

<span data-ttu-id="3f418-p106">このトポロジ例には、北アメリカ、EMEA、APAC の 3 つのネットワーク地域があります。ネットワーク地域には、一連のネットワーク サイト (このトピックで後述するネットワーク サイトの定義を参照) が含まれます。ネットワーク運用チームと連携してネットワーク地域を特定します。</span><span class="sxs-lookup"><span data-stu-id="3f418-p106">Our example topology has three network regions: North America, EMEA, and APAC. A network region contains a collection of network sites (see the definition of network sites later in this topic). Work with your network operations team to identify your network regions.</span></span>

</div>

<div>

## <a name="associating-a-central-site-with-each-network-region"></a><span data-ttu-id="3f418-130">中央サイトと各ネットワーク地域の関連付け</span><span class="sxs-lookup"><span data-stu-id="3f418-130">Associating a Central Site with each Network Region</span></span>

<span data-ttu-id="3f418-131">CAC では、各ネットワーク地域に Lync Server central サイトが定義されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f418-131">CAC requires that a Lync Server central site is defined for each network region.</span></span> <span data-ttu-id="3f418-132">中央サイトは、そのネットワーク地域内の他のすべてのサイトへの最適なネットワーク接続と最高帯域幅に基づいて選択されます。</span><span class="sxs-lookup"><span data-stu-id="3f418-132">The central site is selected with the best network connectivity and highest bandwidth to all the other sites within that network region.</span></span> <span data-ttu-id="3f418-133">前のネットワーク トポロジの例には 3 つのネットワーク地域が示されており、それぞれに CAC の決定を管理する中央サイトがあります。</span><span class="sxs-lookup"><span data-stu-id="3f418-133">The preceding example of network topology shows three network regions, each with a central site that manages CAC decisions.</span></span> <span data-ttu-id="3f418-134">前の例の適切な関連付けを次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="3f418-134">From the preceding example, the appropriate association is shown in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3f418-135">中央サイトは、ネットワーク サイトに必ずしも対応しているわけではありません。</span><span class="sxs-lookup"><span data-stu-id="3f418-135">Central sites do not necessarily correspond to network sites.</span></span> <span data-ttu-id="3f418-136">このドキュメントの例では、一部の中央サイト (シカゴ、ロンドン、北京) がネットワーク サイトと同じ名前になっています。</span><span class="sxs-lookup"><span data-stu-id="3f418-136">In the examples in this documentation, some central sites—Chicago, London, and Beijing—share the same name as the network sites.</span></span> <span data-ttu-id="3f418-137">ただし、中央サイトとネットワークサイトが同じ名前を共有している場合でも、セントラルサイトは Lync Server トポロジの要素であるのに対して、ネットワークサイトは Lync Server トポロジが存在するネットワーク全体の一部になります。</span><span class="sxs-lookup"><span data-stu-id="3f418-137">However, even if a central site and network site share the same name, the central site is an element of the Lync Server topology, whereas the network site is a part of the overall network in which the Lync Server topology resides.</span></span>



</div>

### <a name="network-regions-central-sites-and-network-sites"></a><span data-ttu-id="3f418-138">ネットワーク地域、中央サイト、およびネットワーク サイト</span><span class="sxs-lookup"><span data-stu-id="3f418-138">Network regions, central sites, and network sites</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3f418-139">ネットワーク地域</span><span class="sxs-lookup"><span data-stu-id="3f418-139">Network Region</span></span></th>
<th><span data-ttu-id="3f418-140">中央サイト</span><span class="sxs-lookup"><span data-stu-id="3f418-140">Central Site</span></span></th>
<th><span data-ttu-id="3f418-141">ネットワーク サイト</span><span class="sxs-lookup"><span data-stu-id="3f418-141">Network Sites</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3f418-142">北アメリカ</span><span class="sxs-lookup"><span data-stu-id="3f418-142">North America</span></span></p></td>
<td><p><span data-ttu-id="3f418-143">Chicago</span><span class="sxs-lookup"><span data-stu-id="3f418-143">Chicago</span></span></p></td>
<td><p><span data-ttu-id="3f418-144">Chicago</span><span class="sxs-lookup"><span data-stu-id="3f418-144">Chicago</span></span></p>
<p><span data-ttu-id="3f418-145">ニューヨーク</span><span class="sxs-lookup"><span data-stu-id="3f418-145">New York</span></span></p>
<p><span data-ttu-id="3f418-146">市</span><span class="sxs-lookup"><span data-stu-id="3f418-146">Detroit</span></span></p>
<p><span data-ttu-id="3f418-147">支店</span><span class="sxs-lookup"><span data-stu-id="3f418-147">Portland</span></span></p>
<p><span data-ttu-id="3f418-148">リノ</span><span class="sxs-lookup"><span data-stu-id="3f418-148">Reno</span></span></p>
<p><span data-ttu-id="3f418-149">アルバカーキ</span><span class="sxs-lookup"><span data-stu-id="3f418-149">Albuquerque</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f418-150">EMEA</span><span class="sxs-lookup"><span data-stu-id="3f418-150">EMEA</span></span></p></td>
<td><p><span data-ttu-id="3f418-151">北海道</span><span class="sxs-lookup"><span data-stu-id="3f418-151">London</span></span></p></td>
<td><p><span data-ttu-id="3f418-152">北海道</span><span class="sxs-lookup"><span data-stu-id="3f418-152">London</span></span></p>
<p><span data-ttu-id="3f418-153">ケルン</span><span class="sxs-lookup"><span data-stu-id="3f418-153">Cologne</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f418-154">APAC</span><span class="sxs-lookup"><span data-stu-id="3f418-154">APAC</span></span></p></td>
<td><p><span data-ttu-id="3f418-155">北京</span><span class="sxs-lookup"><span data-stu-id="3f418-155">Beijing</span></span></p></td>
<td><p><span data-ttu-id="3f418-156">北京</span><span class="sxs-lookup"><span data-stu-id="3f418-156">Beijing</span></span></p>
<p><span data-ttu-id="3f418-157">マニラ</span><span class="sxs-lookup"><span data-stu-id="3f418-157">Manila</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="identify-network-sites"></a><span data-ttu-id="3f418-158">ネットワーク サイトの特定</span><span class="sxs-lookup"><span data-stu-id="3f418-158">Identify Network Sites</span></span>

<span data-ttu-id="3f418-p109">ネットワーク サイトは、組織の物理的な現場 (オフィス、一連の建物、キャンパスなど) がある場所を表します。LAN 接続を使用し、他のサイトに WAN 接続された物理的な現場は、ネットワーク サイトと見なされます。まず、組織の全オフィスの一覧表を作成します。このトポロジ例では、北アメリカ ネットワーク地域はニューヨーク、シカゴ、デトロイト、ポートランド、リノ、アルバカーキの各ネットワーク サイトで構成されています。</span><span class="sxs-lookup"><span data-stu-id="3f418-p109">A network site represents a location where your organization has a physical venue—for example, offices, a set of buildings, or a campus. A physical venue with a LAN and has WAN connectivity to other sites is considered a network site. Start by inventorying all of your organization’s offices. In our example topology, the North America network region consists of the following network sites: New York, Chicago, Detroit, Portland, Reno, and Albuquerque.</span></span>

<span data-ttu-id="3f418-p110">すべてのネットワーク サイトをネットワーク地域に関連付ける必要があります。ネットワーク サイトの WAN リンクが制限されているかどうかに応じて、帯域幅ポリシーがネットワーク サイトに関連付けられます。CAC ポリシーと、CAC ポリシーを使用して割り当てる帯域幅の詳細については、このトピックで後述する「帯域幅ポリシーの定義」を参照してください。CAC を構成するには、ネットワーク サイトをネットワーク地域に関連付けます。次に、帯域幅割り当てポリシーを作成して、特定のサイトまたは地域間の帯域幅が制限された接続や、サイトと地域間の WAN 接続に適用します。</span><span class="sxs-lookup"><span data-stu-id="3f418-p110">You must associate every network site with a network region. Depending on whether the network site has a constrained WAN link, a bandwidth policy is associated with the network site. For details about CAC policies and the bandwidth that you allocate by using them, see "Define Bandwidth Policies" later in this topic. To configure CAC, you associate network sites with network regions, and then you create bandwidth-allocating policies to apply to the bandwidth-constrained connections between a given site or region and the WAN connections between the sites and regions.</span></span>

</div>

<div>

## <a name="identify-network-links"></a><span data-ttu-id="3f418-167">ネットワーク リンクの特定</span><span class="sxs-lookup"><span data-stu-id="3f418-167">Identify Network Links</span></span>

<span data-ttu-id="3f418-p111">ネットワーク リンクは、異なる地域やサイトにリンクする物理的な WAN への接続を表します。 このトポロジの例には、地域のネットワーク リンクが 2 つ、地域とサイト間のネットワーク リンクが 5 つ、2 つのサイト間のネットワーク リンクが 1 つあります。</span><span class="sxs-lookup"><span data-stu-id="3f418-p111">Network links represent connections to the physical WAN that links different regions and sites. In our example topology, there are two regional network links, five network links between regions and sites, and one network link between two sites.</span></span>

<span data-ttu-id="3f418-170">北アメリカと EMEA 間の地域リンクは NA-EMEA-LINK として、APAC と EMEA 間の地域リンクは EMEA-APAC-LINK として表されています。</span><span class="sxs-lookup"><span data-stu-id="3f418-170">The two regional links are between North America and EMEA, represented as NA-EMEA-LINK, and between APAC and EMEA, represented as EMEA-APAC-LINK.</span></span>

<span data-ttu-id="3f418-p112">サイト リンクは、ポートランド、リノ、アルバカーキと北アメリカ地域、マニラと APAC 地域、およびケルンと EMEA 地域を接続する線で示されています。リノとアルバカーキ間の線は、これら 2 つのサイト間の直接のネットワーク リンクを表しています。</span><span class="sxs-lookup"><span data-stu-id="3f418-p112">The site links are indicated by the lines connecting Portland, Reno, and Albuquerque to the North America region, Manila to the APAC region, and Cologne to the EMEA region. The line between Reno and Albuquerque shows a direct network link between these two sites.</span></span>

</div>

<div>

## <a name="define-bandwidth-policies"></a><span data-ttu-id="3f418-173">帯域幅ポリシーの定義</span><span class="sxs-lookup"><span data-stu-id="3f418-173">Define Bandwidth Policies</span></span>

<span data-ttu-id="3f418-p113">ネットワーク運用チームと連携して、組織の WAN リンクでリアルタイムの音声/ビデオ トラフィックに使用できる WAN 帯域幅量を決定します。通常は、帯域幅使用量が制限される場合 (音声/ビデオ モダリティに割り当てることができる帯域幅よりも帯域幅使用量が多くなると予測される場合) に、帯域幅ポリシーが WAN リンクに適用されます。</span><span class="sxs-lookup"><span data-stu-id="3f418-p113">Work with your network operations team to determine how much WAN bandwidth is available for real-time audio and video traffic across the WAN links in your organization. Bandwidth policies are typically applied to WAN links if the bandwidth usage is constrained; that is, if it expected to be more than the bandwidth that can be allocated for audio and video modalities.</span></span>

<span data-ttu-id="3f418-p114">CAC \*\* 帯域幅ポリシーでは、リアルタイムの音声/ビデオ モダリティ用に予約できる最大帯域幅を定義します。CAC では他のトラフィックの帯域幅を制限しないため、サイズの大きいファイルの転送や音楽のストリーミングなどの他のデータ トラフィックによって、ネットワーク帯域幅がすべて使い果たされるのを防ぐことはできません。</span><span class="sxs-lookup"><span data-stu-id="3f418-p114">CAC *bandwidth policies* define the maximum bandwidth that can be reserved for real-time audio and video modalities. Since CAC does not limit the bandwidth of other traffic, it cannot prevent other data traffic such as a large file transfer, music streaming, from using up all of the network bandwidth.</span></span>

<span data-ttu-id="3f418-178">CAC 帯域幅ポリシーでは、次のいずれかまたはすべてを定義できます。</span><span class="sxs-lookup"><span data-stu-id="3f418-178">CAC bandwidth policies can define any or all of the following:</span></span>

  - <span data-ttu-id="3f418-179">音声に割り当てる最大合計帯域幅</span><span class="sxs-lookup"><span data-stu-id="3f418-179">Maximum total bandwidth allocated for audio.</span></span>

  - <span data-ttu-id="3f418-180">ビデオに割り当てる最大合計帯域幅</span><span class="sxs-lookup"><span data-stu-id="3f418-180">Maximum total bandwidth allocated for video.</span></span>

  - <span data-ttu-id="3f418-181">1 つの音声通話 (セッション) に割り当てる最大帯域幅</span><span class="sxs-lookup"><span data-stu-id="3f418-181">Maximum bandwidth allocated for a single audio call (session).</span></span>

  - <span data-ttu-id="3f418-182">1 つのビデオ通話 (セッション) に割り当てる最大帯域幅</span><span class="sxs-lookup"><span data-stu-id="3f418-182">Maximum bandwidth allocated for a single video call (session).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3f418-183">CAC 帯域幅の値はすべて、<EM>単一方向</EM>の最大帯域幅制限を表しています。</span><span class="sxs-lookup"><span data-stu-id="3f418-183">All CAC bandwidth values represent the maximum <EM>unidirectional</EM> bandwidth limits.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="3f418-184">Lync Server 2013 音声ポリシー機能を使用すると、ユーザーへの着信呼び出しに対して帯域幅ポリシーチェックを上書きすることができます (ユーザーによって送信される発信呼び出しに対しては無効)。</span><span class="sxs-lookup"><span data-stu-id="3f418-184">The Lync Server 2013 Voice Policy features provide the ability to override bandwidth policy checks for incoming calls to the user (not for outgoing calls that are placed by the user).</span></span> <span data-ttu-id="3f418-185">セッションの確立後、使用帯域幅が正確に計上されます。</span><span class="sxs-lookup"><span data-stu-id="3f418-185">After the session is established, the bandwidth consumption will be accurately accounted for.</span></span> <span data-ttu-id="3f418-186">この設定は慎重に使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f418-186">This setting should be used sparingly.</span></span> <span data-ttu-id="3f418-187">詳細については、「展開」のドキュメントの「 <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">Create a voice policy and CONFIGURE pstn usage records In Lync server 2013</A> 」または「 <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">Modify a voice policy」および「configure pstn Usage Records in lync server 2013</A> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3f418-187">For details, see <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">Create a voice policy and configure PSTN usage records in Lync Server 2013</A> or <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">Modify a voice policy and configure PSTN usage records in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="3f418-p116">セッションあたりの帯域幅使用率を最適化するには、使用される音声およびビデオのコーデック タイプを考慮します。特に、頻繁に使用されることが予想されるコーデックの帯域幅の割り当てが不足しないようにしてください。逆に、多くの帯域幅を必要とするコーデックがメディアで使用されないようにする場合は、このようなコーデックを使用できないようにセッションあたりの最大帯域幅を少なく設定する必要があります。音声の場合、状況によっては使用できないコーデックもあります。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="3f418-p116">To optimize bandwidth utilization on a per-session basis, consider the type of audio and video codecs that will be used. In particular, avoid allocating insufficient bandwidth for a codec that you expect to be used frequently. Conversely, if you want to prevent media from using a codec that requires more bandwidth, you should set the maximum bandwidth per session low enough to discourage such use. For audio, not every codec is available for every scenario. For example:</span></span>

  - <span data-ttu-id="3f418-193">コーデックの帯域幅および優先順位付けを考慮した場合、Lync エンドポイント間のピアツーピア音声通話では RTAudio (8kHz) または RTAudio (16kHz) のいずれかが使用されます。</span><span class="sxs-lookup"><span data-stu-id="3f418-193">Peer-to-peer audio calls between Lync endpoints will use either RTAudio (8kHz) or RTAudio (16kHz) when you factor in the bandwidth and prioritization of codecs.</span></span>

  - <span data-ttu-id="3f418-194">Lync エンドポイントと音声ビデオ会議サービスとの間の電話会議は、g.722 または Siren のどちらかを使用します。</span><span class="sxs-lookup"><span data-stu-id="3f418-194">Conference calls between Lync endpoints and the A/V Conferencing service will use either G.722 or Siren.</span></span>

  - <span data-ttu-id="3f418-195">Lync エンドポイントとの間の公衆交換電話網 (PSTN) への通話には、8kHz または RTAudio (8kHz) のいずれかが使用されます。</span><span class="sxs-lookup"><span data-stu-id="3f418-195">Calls to the public switched telephone network (PSTN) either to or from Lync endpoints will use either G.711 or RTAudio (8kHz).</span></span>

<span data-ttu-id="3f418-196">セッションあたりの最大帯域幅設定を最適化するために次の表を使用してください。</span><span class="sxs-lookup"><span data-stu-id="3f418-196">Use the following table to help optimize the maximum per-session bandwidth settings.</span></span>

### <a name="bandwidth-utilization-by-codecs"></a><span data-ttu-id="3f418-197">コーデック別の帯域幅使用率</span><span class="sxs-lookup"><span data-stu-id="3f418-197">Bandwidth utilization by codecs</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3f418-198">コーデック</span><span class="sxs-lookup"><span data-stu-id="3f418-198">Codec</span></span></th>
<th><span data-ttu-id="3f418-199">前方向エラー訂正 (FEC) を行わない場合の帯域幅要件</span><span class="sxs-lookup"><span data-stu-id="3f418-199">Bandwidth requirement with no forward error correction (FEC)</span></span></th>
<th><span data-ttu-id="3f418-200">前方向エラー訂正 (FEC) を行う場合の帯域幅要件</span><span class="sxs-lookup"><span data-stu-id="3f418-200">Bandwidth requirement with forward error correction (FEC)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3f418-201">RTAudio (8kHz)</span><span class="sxs-lookup"><span data-stu-id="3f418-201">RTAudio (8kHz)</span></span></p></td>
<td><p><span data-ttu-id="3f418-202">49.8 kbps</span><span class="sxs-lookup"><span data-stu-id="3f418-202">49.8 kbps</span></span></p></td>
<td><p><span data-ttu-id="3f418-203">61.6 kbps</span><span class="sxs-lookup"><span data-stu-id="3f418-203">61.6 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f418-204">RTAudio (16kHz)</span><span class="sxs-lookup"><span data-stu-id="3f418-204">RTAudio (16kHz)</span></span></p></td>
<td><p><span data-ttu-id="3f418-205">67 kbps</span><span class="sxs-lookup"><span data-stu-id="3f418-205">67 kbps</span></span></p></td>
<td><p><span data-ttu-id="3f418-206">96 kbps</span><span class="sxs-lookup"><span data-stu-id="3f418-206">96 kbps</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f418-207">Siren</span><span class="sxs-lookup"><span data-stu-id="3f418-207">Siren</span></span></p></td>
<td><p><span data-ttu-id="3f418-208">57.6 kbps</span><span class="sxs-lookup"><span data-stu-id="3f418-208">57.6 kbps</span></span></p></td>
<td><p><span data-ttu-id="3f418-209">73.6 kbps</span><span class="sxs-lookup"><span data-stu-id="3f418-209">73.6 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f418-210">G 711</span><span class="sxs-lookup"><span data-stu-id="3f418-210">G.711</span></span></p></td>
<td><p><span data-ttu-id="3f418-211">102 kbps</span><span class="sxs-lookup"><span data-stu-id="3f418-211">102 kbps</span></span></p></td>
<td><p><span data-ttu-id="3f418-212">166 kbps</span><span class="sxs-lookup"><span data-stu-id="3f418-212">166 kbps</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f418-213">G.722</span><span class="sxs-lookup"><span data-stu-id="3f418-213">G.722</span></span></p></td>
<td><p><span data-ttu-id="3f418-214">105.6 kbps</span><span class="sxs-lookup"><span data-stu-id="3f418-214">105.6 kbps</span></span></p></td>
<td><p><span data-ttu-id="3f418-215">169.6 kbps</span><span class="sxs-lookup"><span data-stu-id="3f418-215">169.6 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f418-216">RTVideo (CIF 15 fps)</span><span class="sxs-lookup"><span data-stu-id="3f418-216">RTVideo (CIF 15 fps)</span></span></p></td>
<td><p><span data-ttu-id="3f418-217">260 kbps</span><span class="sxs-lookup"><span data-stu-id="3f418-217">260 kbps</span></span></p></td>
<td><p><span data-ttu-id="3f418-218">該当なし</span><span class="sxs-lookup"><span data-stu-id="3f418-218">Not applicable</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f418-219">RTVideo (VGA 30 fps)</span><span class="sxs-lookup"><span data-stu-id="3f418-219">RTVideo (VGA 30 fps)</span></span></p></td>
<td><p><span data-ttu-id="3f418-220">610 kbps</span><span class="sxs-lookup"><span data-stu-id="3f418-220">610 kbps</span></span></p></td>
<td><p><span data-ttu-id="3f418-221">該当なし</span><span class="sxs-lookup"><span data-stu-id="3f418-221">Not applicable</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="3f418-p117">帯域幅要件では、Ethernet II、IP、UDP (ユーザー データグラム プロトコル)、RTP (リアルタイム転送プロトコル)、および SRTP (セキュア リアルタイム転送プロトコル) のオーバーヘッドが考慮されています。また、RTCP のオーバーヘッドとして 10 kbps が付加されています。</span><span class="sxs-lookup"><span data-stu-id="3f418-p117">Bandwidth requirements take into account overhead for the following: Ethernet II, IP, User Datagram Protocol (UDP), RTP (real-time transport protocol), and SRTP (secure real-time transport protocol). They also include 10 kbps for RTCP overhead.</span></span>



</div>

<span data-ttu-id="3f418-224">G.722.1 と Siren のコーデックは類似していますが、ビット レートが異なります。</span><span class="sxs-lookup"><span data-stu-id="3f418-224">The G.722.1 and Siren codecs are similar, but they offer different bit rates.</span></span>

<span data-ttu-id="3f418-225">G.722、Lync Server 会議の既定のコーデックは、g.722.1 および Siren コーデックとはまったく異なります。</span><span class="sxs-lookup"><span data-stu-id="3f418-225">G.722, the default codec for Lync Server conferencing, is completely different from the G.722.1 and Siren codecs.</span></span>

<span data-ttu-id="3f418-226">Siren コーデックは、以下の状況で Lync Server で使用されます。</span><span class="sxs-lookup"><span data-stu-id="3f418-226">The Siren codec is used in Lync Server in the following situations:</span></span>

  - <span data-ttu-id="3f418-227">帯域幅ポリシーの設定が低すぎて G.722 を使用できない場合</span><span class="sxs-lookup"><span data-stu-id="3f418-227">If the bandwidth policy is set too low for G.722 to be used.</span></span>

  - <span data-ttu-id="3f418-228">Communications Server 2007 または Communications Server 2007 R2 クライアントが Lync Server 会議サービスに接続する場合 (それらのクライアントは g.722 コーデックをサポートしていないため)。</span><span class="sxs-lookup"><span data-stu-id="3f418-228">If a Communications Server 2007 or Communications Server 2007 R2 client connects to a Lync Server conferencing service (because those clients do not support the G.722 codec).</span></span>

### <a name="bandwidth-utilization-by-scenario"></a><span data-ttu-id="3f418-229">シナリオごとの帯域幅使用率</span><span class="sxs-lookup"><span data-stu-id="3f418-229">Bandwidth utilization by scenario</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3f418-230">シナリオ</span><span class="sxs-lookup"><span data-stu-id="3f418-230">Scenario</span></span></th>
<th><span data-ttu-id="3f418-231">量に最適化した場合の帯域幅要件 (kbps)</span><span class="sxs-lookup"><span data-stu-id="3f418-231">Bandwidth requirement optimized for quantity (kbps)</span></span></th>
<th><span data-ttu-id="3f418-232">バランスが取れたモードの帯域幅要件 (kbps)</span><span class="sxs-lookup"><span data-stu-id="3f418-232">Bandwidth requirement for Balanced mode (kbps)</span></span></th>
<th><span data-ttu-id="3f418-233">質に最適化した場合の帯域幅要件 (kbps)</span><span class="sxs-lookup"><span data-stu-id="3f418-233">Bandwidth requirement optimized for quality (kbps)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3f418-234">ピアツーピアの音声通話</span><span class="sxs-lookup"><span data-stu-id="3f418-234">Peer-to-peer audio calls</span></span></p></td>
<td><p><span data-ttu-id="3f418-235">45 kbps</span><span class="sxs-lookup"><span data-stu-id="3f418-235">45 kbps</span></span></p></td>
<td><p><span data-ttu-id="3f418-236">62 kbps</span><span class="sxs-lookup"><span data-stu-id="3f418-236">62 kbps</span></span></p></td>
<td><p><span data-ttu-id="3f418-237">91 kbps</span><span class="sxs-lookup"><span data-stu-id="3f418-237">91 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f418-238">電話会議</span><span class="sxs-lookup"><span data-stu-id="3f418-238">Conference calls</span></span></p></td>
<td><p><span data-ttu-id="3f418-239">53 kbps</span><span class="sxs-lookup"><span data-stu-id="3f418-239">53 kbps</span></span></p></td>
<td><p><span data-ttu-id="3f418-240">101 kbps</span><span class="sxs-lookup"><span data-stu-id="3f418-240">101 kbps</span></span></p></td>
<td><p><span data-ttu-id="3f418-241">165 kbps</span><span class="sxs-lookup"><span data-stu-id="3f418-241">165 kbps</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f418-242">PSTN 通話 (Lync 2013 と PSTN ゲートウェイ間、メディアバイパスを使用)</span><span class="sxs-lookup"><span data-stu-id="3f418-242">PSTN calls (between Lync 2013 and PSTN gateway, with media bypass)</span></span></p></td>
<td><p><span data-ttu-id="3f418-243">97 kbps</span><span class="sxs-lookup"><span data-stu-id="3f418-243">97 kbps</span></span></p></td>
<td><p><span data-ttu-id="3f418-244">97 kbps</span><span class="sxs-lookup"><span data-stu-id="3f418-244">97 kbps</span></span></p></td>
<td><p><span data-ttu-id="3f418-245">161 kbps</span><span class="sxs-lookup"><span data-stu-id="3f418-245">161 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f418-246">PSTN 通話 (Lync 2013 と仲介サーバーの間、メディアバイパスを使用しない)</span><span class="sxs-lookup"><span data-stu-id="3f418-246">PSTN calls (between Lync 2013 and Mediation Server, without media bypass)</span></span></p></td>
<td><p><span data-ttu-id="3f418-247">45 kbps</span><span class="sxs-lookup"><span data-stu-id="3f418-247">45 kbps</span></span></p></td>
<td><p><span data-ttu-id="3f418-248">97 kbps</span><span class="sxs-lookup"><span data-stu-id="3f418-248">97 kbps</span></span></p></td>
<td><p><span data-ttu-id="3f418-249">161 kbps</span><span class="sxs-lookup"><span data-stu-id="3f418-249">161 kbps</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f418-250">PSTN 通話 (仲介サーバーと PSTN ゲートウェイ間、メディアバイパスを使用しない)</span><span class="sxs-lookup"><span data-stu-id="3f418-250">PSTN calls (between Mediation Server and PSTN gateway, without media bypass)</span></span></p></td>
<td><p><span data-ttu-id="3f418-251">97 kbps</span><span class="sxs-lookup"><span data-stu-id="3f418-251">97 kbps</span></span></p></td>
<td><p><span data-ttu-id="3f418-252">97 kbps</span><span class="sxs-lookup"><span data-stu-id="3f418-252">97 kbps</span></span></p></td>
<td><p><span data-ttu-id="3f418-253">161 kbps</span><span class="sxs-lookup"><span data-stu-id="3f418-253">161 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f418-254">Lync-Polycom の通話</span><span class="sxs-lookup"><span data-stu-id="3f418-254">Lync - Polycom calls</span></span></p></td>
<td><p><span data-ttu-id="3f418-255">101 Kbps</span><span class="sxs-lookup"><span data-stu-id="3f418-255">101 Kbps</span></span></p></td>
<td><p><span data-ttu-id="3f418-256">101 Kbps</span><span class="sxs-lookup"><span data-stu-id="3f418-256">101 Kbps</span></span></p></td>
<td><p><span data-ttu-id="3f418-257">101 Kbps</span><span class="sxs-lookup"><span data-stu-id="3f418-257">101 Kbps</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="identify-ip-subnets"></a><span data-ttu-id="3f418-258">IP サブネットの特定</span><span class="sxs-lookup"><span data-stu-id="3f418-258">Identify IP Subnets</span></span>

<span data-ttu-id="3f418-p118">ネットワーク管理者と連携して各ネットワーク サイトに割り当てる IP サブネットを決定する必要があります。 ネットワーク管理者が既に IP サブネットをネットワーク地域およびネットワーク サイトに分類している場合、作業は大幅に簡略化されます。</span><span class="sxs-lookup"><span data-stu-id="3f418-p118">For each network site, you will need to work with your network administrator to determine what IP subnets are assigned to each network site. If your network administrator has already organized the IP subnets into network regions and network sites, then your work is significantly simplified.</span></span>

<span data-ttu-id="3f418-p119">この例では、北アメリカ地域のニューヨーク サイトに 172.29.80.0/23、157.57.216.0/25、172.29.91.0/23、172.29.81.0/24 の IP サブネットが割り当てられています。普段はデトロイトに勤務している Bob が研修でニューヨークのオフィスに行ったとします。コンピューターを起動してネットワークに接続すると、ニューヨーク用に予約されている 4 つの範囲のいずれか (172.29.80.103 など) の IP アドレスが取得されます。</span><span class="sxs-lookup"><span data-stu-id="3f418-p119">In our example, the New York site in the North America region is assigned the following IP subnets: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Suppose Bob, who typically works in Detroit, travels to the New York office for training. When he turns on his computer and connects to the network, his computer will get an IP address in one of the four ranges reserved for New York, for example 172.29.80.103.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="3f418-264">サーバー上のネットワーク構成中に指定された IP サブネットは、メディアバイパスのために適切に使用するために、クライアントコンピューターによって提供される形式と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f418-264">The IP subnets specified during network configuration on the server must match the format provided by client computers in order to be properly used for media bypass.</span></span> <span data-ttu-id="3f418-265">Lync クライアントは、ローカルの IP アドレスを取得し、関連付けられたサブネットマスクを使用して IP アドレスをマスクします。</span><span class="sxs-lookup"><span data-stu-id="3f418-265">A Lync client takes its local IP address and masks the IP address with the associated subnet mask.</span></span> <span data-ttu-id="3f418-266">各クライアントに関連付けられているバイパス ID を決定するときに、レジストラーは各ネットワークサイトに関連付けられた IP サブネットと、完全一致にクライアントによって提供されたサブネットとを比較します。</span><span class="sxs-lookup"><span data-stu-id="3f418-266">When determining the bypass ID associated with each client, the Registrar will compare the list of IP subnets associated with each network site against the subnet provided by the client for an exact match.</span></span> <span data-ttu-id="3f418-267">このため、サーバー上のネットワーク構成中に入力されたサブネットは、仮想サブネットではなく実際のサブネットであることが重要です。</span><span class="sxs-lookup"><span data-stu-id="3f418-267">For this reason, it is important that subnets entered during network configuration on the server are actual subnets instead of virtual subnets.</span></span> <span data-ttu-id="3f418-268">(通話受付管理を展開し、メディアバイパスを展開しない場合、仮想サブネットを構成していても、通話受付管理が適切に機能します。)</span><span class="sxs-lookup"><span data-stu-id="3f418-268">(If you deploy call admission control, but not media bypass, call admission control will function properly even if you configure virtual subnets.)</span></span><BR><span data-ttu-id="3f418-269">たとえば、IP サブネットマスクが255.255.255.0 の172.29.81.57 の IP アドレスを持つコンピューター上でクライアントがサインインすると、Lync 2013 はサブネット172.29.81.0 に関連付けられたバイパス ID を要求します。</span><span class="sxs-lookup"><span data-stu-id="3f418-269">For example, if a client signs in on a computer with an IP address of 172.29.81.57 with an IP subnet mask of 255.255.255.0, Lync 2013 will request the bypass ID associated with subnet 172.29.81.0.</span></span> <span data-ttu-id="3f418-270">クライアントが仮想サブネットに属していても、サブネットが 172.29.0.0/16 として定義される場合、レジストラーは 172.29.81.0 のサブネットのみを検索するため、これを一致とは見なしません。</span><span class="sxs-lookup"><span data-stu-id="3f418-270">If the subnet is defined as 172.29.0.0/16, although the client belongs to the virtual subnet, the Registrar will not consider this a match because the Registrar is specifically looking for subnet 172.29.81.0.</span></span> <span data-ttu-id="3f418-271">そのため、管理者は、Lync クライアントによって提供されるとおりにサブネットを入力することが重要です (静的または DHCP によってネットワーク構成中にサブネットでプロビジョニングされます)。</span><span class="sxs-lookup"><span data-stu-id="3f418-271">Therefore, it is important that the administrator enters subnets exactly as provided by Lync clients (which are provisioned with subnets during network configuration either statically or by DHCP.)</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

