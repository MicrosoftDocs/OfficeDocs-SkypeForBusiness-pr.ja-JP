---
title: 通話受付制御の要件を収集する例
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Example of gathering your requirements for call admission control
ms:assetid: 3363ac53-b7c4-4a59-aea1-b2f3ee016ae1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425827(v=OCS.15)
ms:contentKeyID: 48183820
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e17d9abb0387f0d77c696487558dec0c915b1651
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833218"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="example-gathering-your-requirements-for-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="4016c-102">例: Lync Server 2013 での通話受付制御の要件の収集</span><span class="sxs-lookup"><span data-stu-id="4016c-102">Example: Gathering your requirements for call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4016c-103">_**最終更新日:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="4016c-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="4016c-p101">この例では、通話受付管理 (CAC) の計画および実装方法を示します。これは大まかに次の作業で構成されます。</span><span class="sxs-lookup"><span data-stu-id="4016c-p101">This example shows you how to plan for and implement call admission control (CAC). At a high level, this consists of the following activities:</span></span>

1.  <span data-ttu-id="4016c-106">すべてのネットワーク ハブおよびバックボーン (*ネットワーク地域*とも呼ばれます) を特定します。</span><span class="sxs-lookup"><span data-stu-id="4016c-106">Identify all of your network hubs and backbones (known as *network regions*).</span></span>

2.  <span data-ttu-id="4016c-107">各ネットワーク領域の CAC を管理する Lync Server セントラルサイトを特定します。</span><span class="sxs-lookup"><span data-stu-id="4016c-107">Identify the Lync Server central site that will manage CAC for each network region.</span></span>

3.  <span data-ttu-id="4016c-108">各ネットワーク地域に接続される*ネットワーク サイト*を特定および定義します。</span><span class="sxs-lookup"><span data-stu-id="4016c-108">Identify and define the *network sites* that are connected to each network region.</span></span>

4.  <span data-ttu-id="4016c-109">WAN への接続に帯域幅の制約がある各ネットワークサイトについては、WAN 接続の帯域幅の容量と、ネットワーク管理者が Lync Server メディアトラフィック用に設定した帯域幅制限 (該当する場合) について説明します。</span><span class="sxs-lookup"><span data-stu-id="4016c-109">For each network site whose connection to the WAN is bandwidth-constrained, describe the bandwidth capacity of the WAN connection and the bandwidth limits that to the network administrator has set for Lync Server media traffic, if applicable.</span></span> <span data-ttu-id="4016c-110">WAN への接続に帯域幅の制限がないサイトは含める必要はありません。</span><span class="sxs-lookup"><span data-stu-id="4016c-110">You do not need to include sites whose connection to the WAN is not bandwidth-constrained.</span></span>

5.  <span data-ttu-id="4016c-111">ネットワークの各サブネットをネットワーク サイトに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="4016c-111">Associate each subnet in your network with a network site.</span></span>

6.  <span data-ttu-id="4016c-112">ネットワーク地域間のリンクをマップします。</span><span class="sxs-lookup"><span data-stu-id="4016c-112">Map the links between the network regions.</span></span> <span data-ttu-id="4016c-113">各リンクについて、帯域幅の容量と、ネットワーク管理者が Lync Server メディアトラフィックに使用した制限事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="4016c-113">For each link, describe its bandwidth capacity and any limits that the network administrator has placed on Lync Server media traffic.</span></span>

7.  <span data-ttu-id="4016c-114">ネットワーク地域のすべてのペア間のルートを定義します。</span><span class="sxs-lookup"><span data-stu-id="4016c-114">Define a route between every pair of network regions.</span></span>

<div>

## <a name="gather-the-required-information"></a><span data-ttu-id="4016c-115">必要な情報の収集</span><span class="sxs-lookup"><span data-stu-id="4016c-115">Gather the Required Information</span></span>

<span data-ttu-id="4016c-116">通話受付管理の準備を行うには、次の手順で示されている情報を収集します。</span><span class="sxs-lookup"><span data-stu-id="4016c-116">To prepare for call admission control, gather the information described in the following steps:</span></span>

1.  <span data-ttu-id="4016c-p104">ネットワーク地域を特定します。ネットワーク地域とは、ネットワーク バックボーンまたはネットワーク ハブを示します。</span><span class="sxs-lookup"><span data-stu-id="4016c-p104">Identify your network regions. A network region represents a network backbone or a network hub.</span></span>
    
    <span data-ttu-id="4016c-p105">ネットワーク バックボーンまたはネットワーク ハブとは、異なる LAN またはサブネット間の情報交換用パスを提供して、ネットワークのさまざまな部分を相互接続するコンピューター ネットワーク インフラストラクチャの一部です。バックボーンは、小規模ロケーションから地理的に広範囲な地域まで、さまざまなネットワークを繋ぐことができます。通常、バックボーンの処理能力はバックボーンに接続するネットワークの処理能力よりも高くなっています。</span><span class="sxs-lookup"><span data-stu-id="4016c-p105">A network backbone or a network hub is a part of computer network infrastructure that interconnects various pieces of network, providing a path for the exchange of information between different LANs or subnets. A backbone can tie together diverse networks, from a small location to a wide geographic area. The backbone's capacity is typically greater than that of the networks connected to it.</span></span>
    
    <span data-ttu-id="4016c-p106">このトポロジ例では、北アメリカ、EMEA、および APAC の 3 つのネットワーク地域が存在します。 ネットワーク地域にはネットワーク サイトのコレクションが含まれます。 ネットワーク管理者と協力して、組織のネットワーク地域を定義します。</span><span class="sxs-lookup"><span data-stu-id="4016c-p106">Our example topology has three network regions: North America, EMEA, and APAC. A network region contains a collection of network sites. Work with your network administrator to define the network regions for your enterprise.</span></span>

2.  <span data-ttu-id="4016c-125">各ネットワーク地域が関連付けられている中央サイトを特定します。</span><span class="sxs-lookup"><span data-stu-id="4016c-125">Identify each network region’s associated central site.</span></span> <span data-ttu-id="4016c-126">セントラルサイトには、少なくとも1つのフロントエンドサーバーが含まれています。また、ネットワーク領域の WAN 接続を通過するすべてのメディアトラフィックで CAC を管理する Lync Server 展開です。</span><span class="sxs-lookup"><span data-stu-id="4016c-126">A central site contains at least one Front End Server and is the Lync Server deployment that will manage CAC for all media traffic that passes through the network region’s WAN connection.</span></span>
    
    <span data-ttu-id="4016c-127">**3 つのネットワーク地域に分けられたエンタープライズ ネットワークの例**</span><span class="sxs-lookup"><span data-stu-id="4016c-127">**An example enterprise network divided into three network regions**</span></span>
    
    <span data-ttu-id="4016c-128">![3 つのネットワークリージョンでのネットワークトポロジの例](images/Gg425827.08937347-250f-488f-ba5f-c256e6afcd8b(OCS.15).jpg "3 つのネットワークリージョンでのネットワークトポロジの例")</span><span class="sxs-lookup"><span data-stu-id="4016c-128">![Network Topology Example with 3 Network Regions](images/Gg425827.08937347-250f-488f-ba5f-c256e6afcd8b(OCS.15).jpg "Network Topology Example with 3 Network Regions")</span></span>  
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="4016c-129">Multiprotocol Label Switching (MPLS) ネットワークは、それぞれの地理的な場所が対応するネットワーク サイトを有する、ネットワーク地域として表される必要があります。</span><span class="sxs-lookup"><span data-stu-id="4016c-129">A Multiprotocol Label Switching (MPLS) network should be represented as a network region in which each geographic location has a corresponding network site.</span></span> <span data-ttu-id="4016c-130">詳細については、計画ドキュメントの「<A href="lync-server-2013-call-admission-control-on-an-mpls-network.md">MPLS ネットワークでの、Lync Server 2013 による通話受付制御</A>」トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4016c-130">For details, see the “<A href="lync-server-2013-call-admission-control-on-an-mpls-network.md">Call admission control on an MPLS network with Lync Server 2013</A>” topic in the Planning documentation.</span></span>

    
    </div>
    
    <span data-ttu-id="4016c-131">上記のネットワークトポロジの例では、3つのネットワーク領域があります。それぞれに、CAC を管理する Lync Server セントラルサイトがあります。</span><span class="sxs-lookup"><span data-stu-id="4016c-131">In the preceding example network topology, there are three network regions, each with a Lync Server central site that manages CAC.</span></span> <span data-ttu-id="4016c-132">ネットワーク地域の適切な中央サイトは、地理的な近さによって選択されます。</span><span class="sxs-lookup"><span data-stu-id="4016c-132">The appropriate central site for a network region is chosen by the geographic vicinity.</span></span> <span data-ttu-id="4016c-133">メディア トラフィックはネットワーク地域内で最も重くなるため、所有権が地理的な近さで決まることで自己完結型となり、その他の中央サイトが使用できなくなった場合でも、機能し続けます。</span><span class="sxs-lookup"><span data-stu-id="4016c-133">Because media traffic will be heaviest within network regions, the ownership by geographic vicinity makes it self-contained and will continue to be functional even if other central sites become unavailable.</span></span>
    
    <span data-ttu-id="4016c-134">この例では、シカゴという名前の Lync Server 展開は北米地域のセントラルサイトです。</span><span class="sxs-lookup"><span data-stu-id="4016c-134">In this example, a Lync Server deployment named Chicago is the central site for the North America region.</span></span>
    
    <span data-ttu-id="4016c-135">北米のすべての Lync ユーザーは、シカゴの展開でサーバーに所属しています。</span><span class="sxs-lookup"><span data-stu-id="4016c-135">All Lync users in North America are homed on servers in the Chicago deployment.</span></span> <span data-ttu-id="4016c-136">次の表に 3 つすべてのネットワーク地域の中央サイトを示します。</span><span class="sxs-lookup"><span data-stu-id="4016c-136">The following table shows central sites for all three network regions.</span></span>
    
    ### <a name="network-regions-and-their-associated-central-sites"></a><span data-ttu-id="4016c-137">ネットワーク地域と関連付けられた中央サイト</span><span class="sxs-lookup"><span data-stu-id="4016c-137">Network Regions and their Associated Central Sites</span></span>
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="4016c-138">ネットワーク地域</span><span class="sxs-lookup"><span data-stu-id="4016c-138">Network Region</span></span></th>
    <th><span data-ttu-id="4016c-139">中央サイト</span><span class="sxs-lookup"><span data-stu-id="4016c-139">Central Site</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="4016c-140">北アメリカ</span><span class="sxs-lookup"><span data-stu-id="4016c-140">North America</span></span></p></td>
    <td><p><span data-ttu-id="4016c-141">シカゴ</span><span class="sxs-lookup"><span data-stu-id="4016c-141">Chicago</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="4016c-142">EMEA</span><span class="sxs-lookup"><span data-stu-id="4016c-142">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="4016c-143">ロンドン</span><span class="sxs-lookup"><span data-stu-id="4016c-143">London</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="4016c-144">APAC</span><span class="sxs-lookup"><span data-stu-id="4016c-144">APAC</span></span></p></td>
    <td><p><span data-ttu-id="4016c-145">北京</span><span class="sxs-lookup"><span data-stu-id="4016c-145">Beijing</span></span></p></td>
    </tr>
    </tbody>
    </table>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="4016c-146">Lync Server のトポロジによっては、同じセントラルサイトを複数のネットワーク領域に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="4016c-146">Depending on your Lync Server topology, the same central site can be assigned to multiple network regions.</span></span>

    
    </div>

3.  <span data-ttu-id="4016c-p111">それぞれのネットワーク地域で、帯域幅に制限がない WAN 接続を有するネットワーク サイト (オフィスまたは場所) すべてを特定します。 これらのサイトは帯域幅の制限がないため、CAC 帯域幅ポリシーを適用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="4016c-p111">For each network region, identify all of the network sites (offices or locations) whose WAN connections are not bandwidth-constrained. Because these sites are not bandwidth constrained, you do not need to apply CAC bandwidth policies to them.</span></span>
    
    <span data-ttu-id="4016c-149">次の表に示されている例では、3 つのネットワーク サイトには帯域幅の制限がある WAN リンクがありません: ニューヨーク、シカゴ、およびデトロイト。</span><span class="sxs-lookup"><span data-stu-id="4016c-149">In the example shown in the following table, three network sites do not have bandwidth-constrained WAN links: New York, Chicago, and Detroit.</span></span>
    
    ### <a name="network-sites-not-constrained-by-wan-bandwidth"></a><span data-ttu-id="4016c-150">WAN 帯域幅による制限がないネットワーク サイト</span><span class="sxs-lookup"><span data-stu-id="4016c-150">Network Sites not Constrained by WAN Bandwidth</span></span>
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="4016c-151">ネットワーク サイト</span><span class="sxs-lookup"><span data-stu-id="4016c-151">Network Site</span></span></th>
    <th><span data-ttu-id="4016c-152">ネットワーク地域</span><span class="sxs-lookup"><span data-stu-id="4016c-152">Network Region</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="4016c-153">ニューヨーク</span><span class="sxs-lookup"><span data-stu-id="4016c-153">New York</span></span></p></td>
    <td><p><span data-ttu-id="4016c-154">北アメリカ</span><span class="sxs-lookup"><span data-stu-id="4016c-154">North America</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="4016c-155">シカゴ</span><span class="sxs-lookup"><span data-stu-id="4016c-155">Chicago</span></span></p></td>
    <td><p><span data-ttu-id="4016c-156">北アメリカ</span><span class="sxs-lookup"><span data-stu-id="4016c-156">North America</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="4016c-157">デトロイト</span><span class="sxs-lookup"><span data-stu-id="4016c-157">Detroit</span></span></p></td>
    <td><p><span data-ttu-id="4016c-158">北アメリカ</span><span class="sxs-lookup"><span data-stu-id="4016c-158">North America</span></span></p></td>
    </tr>
    </tbody>
    </table>


4.  <span data-ttu-id="4016c-159">それぞれのネットワーク地域で、帯域幅の制限がある WAN リンクを介してネットワーク地域に接続しているすべてのネットワーク サイトを特定します。</span><span class="sxs-lookup"><span data-stu-id="4016c-159">For each network region, identify all of the network sites that connect to the network region through bandwidth-constrained WAN links.</span></span>
    
    <span data-ttu-id="4016c-160">音声およびビデオの品質を確実なものにできるように、これらの帯域幅の制限があるネットワーク サイトは、WAN を監視し、ネットワーク地域への、およびネットワーク地域からのメディア (音声またはビデオ) トラフィック フローを制限する CAC 帯域幅ポリシーを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4016c-160">To help ensure audio and video quality, we recommend that these bandwidth-constrained network sites have their WANs monitored and CAC bandwidth policies that limit media (voice or video) traffic flow to and from the network region.</span></span>
    
    <span data-ttu-id="4016c-161">次の表に示されている例では、WAN 帯域幅による制限がある 3 つのネットワーク サイトが存在します。 ポートランド、リノ、およびアルバカーキ。</span><span class="sxs-lookup"><span data-stu-id="4016c-161">In the example shown in the following table, there are three network sites that are constrained by WAN bandwidth: Portland, Reno and Albuquerque.</span></span>
    
    ### <a name="network-sites-constrained-by-wan-bandwidth"></a><span data-ttu-id="4016c-162">WAN 帯域幅による制限があるネットワーク サイト</span><span class="sxs-lookup"><span data-stu-id="4016c-162">Network Sites Constrained by WAN Bandwidth</span></span>
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="4016c-163">ネットワーク サイト</span><span class="sxs-lookup"><span data-stu-id="4016c-163">Network Site</span></span></th>
    <th><span data-ttu-id="4016c-164">ネットワーク地域</span><span class="sxs-lookup"><span data-stu-id="4016c-164">Network Region</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="4016c-165">アルバカーキ</span><span class="sxs-lookup"><span data-stu-id="4016c-165">Albuquerque</span></span></p></td>
    <td><p><span data-ttu-id="4016c-166">北アメリカ</span><span class="sxs-lookup"><span data-stu-id="4016c-166">North America</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="4016c-167">リノ</span><span class="sxs-lookup"><span data-stu-id="4016c-167">Reno</span></span></p></td>
    <td><p><span data-ttu-id="4016c-168">北アメリカ</span><span class="sxs-lookup"><span data-stu-id="4016c-168">North America</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="4016c-169">ポートランド</span><span class="sxs-lookup"><span data-stu-id="4016c-169">Portland</span></span></p></td>
    <td><p><span data-ttu-id="4016c-170">北アメリカ</span><span class="sxs-lookup"><span data-stu-id="4016c-170">North America</span></span></p></td>
    </tr>
    </tbody>
    </table>
    
    <span data-ttu-id="4016c-171">**帯域幅の制限がない 3 つのネットワーク サイト (シカゴ、ニューヨーク、デトロイト) および WAN 帯域幅の制限がある 3 つのネットワーク サイト (ポートランド、リノ、アルバカーキ) を持つ CAC ネットワーク地域、北アメリカ**</span><span class="sxs-lookup"><span data-stu-id="4016c-171">**CAC network region North America with three network sites that are unconstrained by bandwidth (Chicago, New York, and Detroit) and three network sites that are constrained by WAN bandwidth (Portland, Reno, and Albuquerque)**</span></span>
    
    <span data-ttu-id="4016c-172">![WAN の帯域幅によって制約]されたネットワークサイトの例(images/Gg425827.d9d1f231-db4d-4dd7-8fbc-eb0b6d1e705d(OCS.15).jpg "WAN の帯域幅によって制約")されたネットワークサイトの例</span><span class="sxs-lookup"><span data-stu-id="4016c-172">![Example network sites constrained by WAN bandwidth](images/Gg425827.d9d1f231-db4d-4dd7-8fbc-eb0b6d1e705d(OCS.15).jpg "Example network sites constrained by WAN bandwidth")</span></span>  

5.  <span data-ttu-id="4016c-173">帯域幅の制限がある WAN リンクに対して、次の項目を決定します。</span><span class="sxs-lookup"><span data-stu-id="4016c-173">For each bandwidth-constrained WAN link, determine the following:</span></span>
    
      - <span data-ttu-id="4016c-174">すべての同時音声セッションに対して設定する全体的な帯域幅制限。</span><span class="sxs-lookup"><span data-stu-id="4016c-174">Overall bandwidth limit that you want to set for all concurrent audio sessions.</span></span> <span data-ttu-id="4016c-175">新しいオーディオセッションによってこの制限を超過すると、Lync Server ではセッションの開始が許可されません。</span><span class="sxs-lookup"><span data-stu-id="4016c-175">If a new audio session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="4016c-176">個々のオーディオセッションごとに設定する帯域幅の制限。</span><span class="sxs-lookup"><span data-stu-id="4016c-176">Bandwidth limit that you want to set for each individual audio session.</span></span> <span data-ttu-id="4016c-177">既定の CAC 帯域幅制限は 175 kbps ですが、管理者が変更することができます。</span><span class="sxs-lookup"><span data-stu-id="4016c-177">The default CAC bandwidth limit is 175 kbps, but it can be modified by the administrator.</span></span>
    
      - <span data-ttu-id="4016c-178">すべての同時ビデオセッションに対して設定する全体的な帯域幅制限。</span><span class="sxs-lookup"><span data-stu-id="4016c-178">Overall bandwidth limit that you want to set for all concurrent video sessions.</span></span> <span data-ttu-id="4016c-179">新しいビデオセッションによってこの制限を超過する場合、Lync Server ではセッションの開始が許可されません。</span><span class="sxs-lookup"><span data-stu-id="4016c-179">If a new video session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="4016c-180">個々のビデオセッションに対して設定する帯域幅の制限。</span><span class="sxs-lookup"><span data-stu-id="4016c-180">Bandwidth limit that you want to set for each individual video session.</span></span> <span data-ttu-id="4016c-181">既定の CAC 帯域幅制限は 700 kbps ですが、管理者が変更することができます。</span><span class="sxs-lookup"><span data-stu-id="4016c-181">The default CAC bandwidth limit is 700 kbps, but it can be modified by the administrator.</span></span>
    
    ### <a name="network-sites-with-wan-bandwidth-constraint-information-bandwidth-in-kbps"></a><span data-ttu-id="4016c-182">WAN 帯域幅の制約情報 (kbps の帯域幅) を備えたネットワークサイト</span><span class="sxs-lookup"><span data-stu-id="4016c-182">Network Sites with WAN Bandwidth Constraint Information (Bandwidth in kbps)</span></span>
    
    <table style="width:100%;">
    <colgroup>
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="4016c-183">ネットワーク サイト</span><span class="sxs-lookup"><span data-stu-id="4016c-183">Network Site</span></span></th>
    <th><span data-ttu-id="4016c-184">ネットワーク地域</span><span class="sxs-lookup"><span data-stu-id="4016c-184">Network Region</span></span></th>
    <th><span data-ttu-id="4016c-185">BW Limit</span><span class="sxs-lookup"><span data-stu-id="4016c-185">BW Limit</span></span></th>
    <th><span data-ttu-id="4016c-186">オーディオ制限</span><span class="sxs-lookup"><span data-stu-id="4016c-186">Audio Limit</span></span></th>
    <th><span data-ttu-id="4016c-187">オーディオセッションの制限</span><span class="sxs-lookup"><span data-stu-id="4016c-187">Audio Session Limit</span></span></th>
    <th><span data-ttu-id="4016c-188">ビデオの制限</span><span class="sxs-lookup"><span data-stu-id="4016c-188">Video Limit</span></span></th>
    <th><span data-ttu-id="4016c-189">ビデオセッションの制限</span><span class="sxs-lookup"><span data-stu-id="4016c-189">Video Session Limit</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="4016c-190">アルバカーキ</span><span class="sxs-lookup"><span data-stu-id="4016c-190">Albuquerque</span></span></p></td>
    <td><p><span data-ttu-id="4016c-191">北アメリカ</span><span class="sxs-lookup"><span data-stu-id="4016c-191">North America</span></span></p></td>
    <td><p><span data-ttu-id="4016c-192">5,000</span><span class="sxs-lookup"><span data-stu-id="4016c-192">5,000</span></span></p></td>
    <td><p><span data-ttu-id="4016c-193">2000</span><span class="sxs-lookup"><span data-stu-id="4016c-193">2,000</span></span></p></td>
    <td><p><span data-ttu-id="4016c-194">175</span><span class="sxs-lookup"><span data-stu-id="4016c-194">175</span></span></p></td>
    <td><p><span data-ttu-id="4016c-195">1400</span><span class="sxs-lookup"><span data-stu-id="4016c-195">1,400</span></span></p></td>
    <td><p><span data-ttu-id="4016c-196">700</span><span class="sxs-lookup"><span data-stu-id="4016c-196">700</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="4016c-197">リノ</span><span class="sxs-lookup"><span data-stu-id="4016c-197">Reno</span></span></p></td>
    <td><p><span data-ttu-id="4016c-198">北アメリカ</span><span class="sxs-lookup"><span data-stu-id="4016c-198">North America</span></span></p></td>
    <td><p><span data-ttu-id="4016c-199">1万</span><span class="sxs-lookup"><span data-stu-id="4016c-199">10,000</span></span></p></td>
    <td><p><span data-ttu-id="4016c-200">4000</span><span class="sxs-lookup"><span data-stu-id="4016c-200">4,000</span></span></p></td>
    <td><p><span data-ttu-id="4016c-201">175</span><span class="sxs-lookup"><span data-stu-id="4016c-201">175</span></span></p></td>
    <td><p><span data-ttu-id="4016c-202">2800</span><span class="sxs-lookup"><span data-stu-id="4016c-202">2,800</span></span></p></td>
    <td><p><span data-ttu-id="4016c-203">700</span><span class="sxs-lookup"><span data-stu-id="4016c-203">700</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="4016c-204">ポートランド</span><span class="sxs-lookup"><span data-stu-id="4016c-204">Portland</span></span></p></td>
    <td><p><span data-ttu-id="4016c-205">北アメリカ</span><span class="sxs-lookup"><span data-stu-id="4016c-205">North America</span></span></p></td>
    <td><p><span data-ttu-id="4016c-206">5,000</span><span class="sxs-lookup"><span data-stu-id="4016c-206">5,000</span></span></p></td>
    <td><p><span data-ttu-id="4016c-207">4000</span><span class="sxs-lookup"><span data-stu-id="4016c-207">4,000</span></span></p></td>
    <td><p><span data-ttu-id="4016c-208">175</span><span class="sxs-lookup"><span data-stu-id="4016c-208">175</span></span></p></td>
    <td><p><span data-ttu-id="4016c-209">2800</span><span class="sxs-lookup"><span data-stu-id="4016c-209">2,800</span></span></p></td>
    <td><p><span data-ttu-id="4016c-210">700</span><span class="sxs-lookup"><span data-stu-id="4016c-210">700</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="4016c-211">ニューヨーク</span><span class="sxs-lookup"><span data-stu-id="4016c-211">New York</span></span></p></td>
    <td><p><span data-ttu-id="4016c-212">北アメリカ</span><span class="sxs-lookup"><span data-stu-id="4016c-212">North America</span></span></p></td>
    <td><p><span data-ttu-id="4016c-213">(制限なし)</span><span class="sxs-lookup"><span data-stu-id="4016c-213">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="4016c-214">(制限なし)</span><span class="sxs-lookup"><span data-stu-id="4016c-214">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="4016c-215">(制限なし)</span><span class="sxs-lookup"><span data-stu-id="4016c-215">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="4016c-216">(制限なし)</span><span class="sxs-lookup"><span data-stu-id="4016c-216">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="4016c-217">(制限なし)</span><span class="sxs-lookup"><span data-stu-id="4016c-217">(no limit)</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="4016c-218">シカゴ</span><span class="sxs-lookup"><span data-stu-id="4016c-218">Chicago</span></span></p></td>
    <td><p><span data-ttu-id="4016c-219">北アメリカ</span><span class="sxs-lookup"><span data-stu-id="4016c-219">North America</span></span></p></td>
    <td><p><span data-ttu-id="4016c-220">(制限なし)</span><span class="sxs-lookup"><span data-stu-id="4016c-220">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="4016c-221">(制限なし)</span><span class="sxs-lookup"><span data-stu-id="4016c-221">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="4016c-222">(制限なし)</span><span class="sxs-lookup"><span data-stu-id="4016c-222">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="4016c-223">(制限なし)</span><span class="sxs-lookup"><span data-stu-id="4016c-223">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="4016c-224">(制限なし)</span><span class="sxs-lookup"><span data-stu-id="4016c-224">(no limit)</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="4016c-225">デトロイト</span><span class="sxs-lookup"><span data-stu-id="4016c-225">Detroit</span></span></p></td>
    <td><p><span data-ttu-id="4016c-226">北アメリカ</span><span class="sxs-lookup"><span data-stu-id="4016c-226">North America</span></span></p></td>
    <td><p><span data-ttu-id="4016c-227">(制限なし)</span><span class="sxs-lookup"><span data-stu-id="4016c-227">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="4016c-228">(制限なし)</span><span class="sxs-lookup"><span data-stu-id="4016c-228">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="4016c-229">(制限なし)</span><span class="sxs-lookup"><span data-stu-id="4016c-229">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="4016c-230">(制限なし)</span><span class="sxs-lookup"><span data-stu-id="4016c-230">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="4016c-231">(制限なし)</span><span class="sxs-lookup"><span data-stu-id="4016c-231">(no limit)</span></span></p></td>
    </tr>
    </tbody>
    </table>


6.  <span data-ttu-id="4016c-232">ネットワーク内のすべてのサブネットについて、関連付けられたネットワークサイトを指定します。</span><span class="sxs-lookup"><span data-stu-id="4016c-232">For every subnet in your network, specify its associated network site.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="4016c-233">ネットワークサイトが帯域幅の制約を受けていない場合でも、ネットワーク内のすべてのサブネットがネットワークサイトと関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="4016c-233">Every subnet in your network must be associated with a network site, even if the network site is not bandwidth constrained.</span></span> <span data-ttu-id="4016c-234">これは、通話受付制御がサブネット情報を使用して、どのネットワークサイトでエンドポイントが配置されているかを判断するためです。</span><span class="sxs-lookup"><span data-stu-id="4016c-234">This is because call admission control uses subnet information to determine at which network site an endpoint is located.</span></span> <span data-ttu-id="4016c-235">セッションの両方の当事者の場所が決定されると、通話受付制御によって、通話を確立するための十分な帯域幅があるかどうかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="4016c-235">When the locations of both parties in the session are determined, call admission control can determine if there is sufficient bandwidth to establish a call.</span></span> <span data-ttu-id="4016c-236">帯域幅の制限がないリンクを経由してセッションが確立されると、通知が生成されます。</span><span class="sxs-lookup"><span data-stu-id="4016c-236">When a session is established over a link that has no bandwidth limits, an alert is generated.</span></span><BR><span data-ttu-id="4016c-237">オーディオ/ビデオエッジサーバーを展開する場合、各エッジサーバーのパブリック IP アドレスが、エッジサーバーが展開されているネットワークサイトと関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="4016c-237">If you deploy Audio/Video Edge Servers, the public IP addresses of each Edge Server must be associated with the network site where the Edge Server is deployed.</span></span> <span data-ttu-id="4016c-238">A/V エッジサーバーの各パブリック IP アドレスは、サブネットマスクが32のサブネットとして、ネットワーク構成の設定に追加されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="4016c-238">Each public IP address of the A/V Edge Server must be added to your network configuration settings as a subnet with a subnet mask of 32.</span></span> <span data-ttu-id="4016c-239">たとえば、シカゴに A/V エッジサーバーを展開している場合、それらのサーバーの各外部 IP アドレスに対して、サブネットマスク32を持つサブネットを作成し、そのサブネットにネットワークサイトシカゴを関連付けます。</span><span class="sxs-lookup"><span data-stu-id="4016c-239">For example, if you deploy A/V Edge Servers in Chicago, then for each external IP address of those servers create a subnet with a subnet mask of 32 and associate network site Chicago with those subnets.</span></span> <span data-ttu-id="4016c-240">パブリック IP アドレスの詳細については、計画ドキュメントの「 <A href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">Lync Server 2013 の外部の A/V ファイアウォールとポートの要件を確認</A>する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4016c-240">For details about public IP addresses, see <A href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">Determine external A/V firewall and port requirements for Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="4016c-241">ネットワークに存在するが、サブネットに関連付けられていない、または IP アドレスを含むサブネットがネットワークサイトに関連付けられていない IP アドレスのリストを指定して、キー正常性インジケータ (KHI) アラートが発生します。</span><span class="sxs-lookup"><span data-stu-id="4016c-241">A Key Health Indicator (KHI) alert is raised, specifying a list of IP addresses that are present in your network but are either not associated with a subnet, or the subnet that includes the IP addresses is not associated with a network site.</span></span> <span data-ttu-id="4016c-242">このアラートは8時間以内に複数回発生することはありません。</span><span class="sxs-lookup"><span data-stu-id="4016c-242">This alert will not be raised more than once within an 8 hour period.</span></span> <span data-ttu-id="4016c-243">関連する通知情報と例を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="4016c-243">The relevant alert information and an example are as follows:</span></span><BR><span data-ttu-id="4016c-244"><STRONG>ソース:</STRONG>CS 帯域幅ポリシーサービス (コア)</span><span class="sxs-lookup"><span data-stu-id="4016c-244"><STRONG>Source:</STRONG> CS Bandwidth Policy Service (Core)</span></span><BR><span data-ttu-id="4016c-245"><STRONG>イベント番号:</STRONG> 36034</span><span class="sxs-lookup"><span data-stu-id="4016c-245"><STRONG>Event number:</STRONG> 36034</span></span><BR><span data-ttu-id="4016c-246"><STRONG>レベル:</STRONG> 2</span><span class="sxs-lookup"><span data-stu-id="4016c-246"><STRONG>Level:</STRONG> 2</span></span><BR><span data-ttu-id="4016c-247"><STRONG>説明:</STRONG>次の IP アドレスのサブネット: &lt;ip アドレス&gt;の一覧が構成されていないか、サブネットがネットワークサイトに関連付けられていません。</span><span class="sxs-lookup"><span data-stu-id="4016c-247"><STRONG>Description:</STRONG> The subnets for the following IP Addresses: &lt;List of IP Addresses&gt; are either not configured or the subnets are not associated to a network site.</span></span><BR><span data-ttu-id="4016c-248"><STRONG>原因:</STRONG>対応する IP アドレスのサブネットがネットワーク構成の設定で見つからないか、サブネットがネットワークサイトに関連付けられていません。</span><span class="sxs-lookup"><span data-stu-id="4016c-248"><STRONG>Cause:</STRONG> The subnets for the corresponding IP addresses are missing from the network configuration settings or the subnets are not associated to a network site.</span></span><BR><span data-ttu-id="4016c-249"><STRONG>解像度:</STRONG>上記の IP アドレスの一覧に対応するサブネットをネットワーク構成の設定に追加し、すべてのサブネットをネットワークサイトに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="4016c-249"><STRONG>Resolution:</STRONG> Add subnets corresponding to the preceding list of IP addresses into the network configuration settings and associate every subnet to a network site.</span></span><BR><span data-ttu-id="4016c-250">たとえば、アラートの IP アドレス一覧に10.121.248.226 と10.121.249.20 が指定されている場合、これらの IP アドレスはサブネットに関連付けられていないか、または関連付けられているサブネットがネットワークサイトに属していません。</span><span class="sxs-lookup"><span data-stu-id="4016c-250">For example, if the IP address list in the alert specifies 10.121.248.226 and 10.121.249.20, either these IP addresses are not associated with a subnet, or the subnet that they are associated with does not belong to a network site.</span></span> <span data-ttu-id="4016c-251">10.121.248.0/24 および 10.121.249.0/24 がこれらのアドレスに対応するサブネットである場合、次の手順でこの問題を解決することができます。</span><span class="sxs-lookup"><span data-stu-id="4016c-251">If 10.121.248.0/24 and 10.121.249.0/24 are the corresponding subnets for these addresses, you can resolve this issue as follows:</span></span> 
    > <OL>
    > <LI>
    > <P><span data-ttu-id="4016c-252">IP アドレス 10.121.248.226 が 10.121.248.0/24 サブネットに関連付けられていること、および IP アドレス 10.121.249.20 が 10.121.249.0/24 サブネットに関連付けられていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4016c-252">Be sure that IP address 10.121.248.226 is associated with the 10.121.248.0/24 subnet and IP address 10.121.249.20 is associated with the 10.121.249.0/24 subnet.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="4016c-253">10.121.248.0/24 および 10.121.249.0/24 サブネットがそれぞれネットワーク サイトに関連付けられていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4016c-253">Be sure that the 10.121.248.0/24 and 10.121.249.0/24 subnets are each associated with a network site.</span></span></P></LI></OL>

    
    </div>
    
    ### <a name="network-sites-and-associated-subnets-bandwidth-in-kbps"></a><span data-ttu-id="4016c-254">ネットワークサイトと関連サブネット (kbps の帯域幅)</span><span class="sxs-lookup"><span data-stu-id="4016c-254">Network Sites and Associated Subnets (Bandwidth in kbps)</span></span>
    
    <table>
    <colgroup>
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="4016c-255">ネットワーク サイト</span><span class="sxs-lookup"><span data-stu-id="4016c-255">Network Site</span></span></th>
    <th><span data-ttu-id="4016c-256">ネットワーク地域</span><span class="sxs-lookup"><span data-stu-id="4016c-256">Network Region</span></span></th>
    <th><span data-ttu-id="4016c-257">BW Limit</span><span class="sxs-lookup"><span data-stu-id="4016c-257">BW Limit</span></span></th>
    <th><span data-ttu-id="4016c-258">オーディオ制限</span><span class="sxs-lookup"><span data-stu-id="4016c-258">Audio Limit</span></span></th>
    <th><span data-ttu-id="4016c-259">オーディオセッションの制限</span><span class="sxs-lookup"><span data-stu-id="4016c-259">Audio Session Limit</span></span></th>
    <th><span data-ttu-id="4016c-260">ビデオの制限</span><span class="sxs-lookup"><span data-stu-id="4016c-260">Video Limit</span></span></th>
    <th><span data-ttu-id="4016c-261">ビデオセッションの制限</span><span class="sxs-lookup"><span data-stu-id="4016c-261">Video Session Limit</span></span></th>
    <th><span data-ttu-id="4016c-262">サブネット</span><span class="sxs-lookup"><span data-stu-id="4016c-262">Subnets</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="4016c-263">アルバカーキ</span><span class="sxs-lookup"><span data-stu-id="4016c-263">Albuquerque</span></span></p></td>
    <td><p><span data-ttu-id="4016c-264">北アメリカ</span><span class="sxs-lookup"><span data-stu-id="4016c-264">North America</span></span></p></td>
    <td><p><span data-ttu-id="4016c-265">5,000</span><span class="sxs-lookup"><span data-stu-id="4016c-265">5,000</span></span></p></td>
    <td><p><span data-ttu-id="4016c-266">2000</span><span class="sxs-lookup"><span data-stu-id="4016c-266">2,000</span></span></p></td>
    <td><p><span data-ttu-id="4016c-267">175</span><span class="sxs-lookup"><span data-stu-id="4016c-267">175</span></span></p></td>
    <td><p><span data-ttu-id="4016c-268">1400</span><span class="sxs-lookup"><span data-stu-id="4016c-268">1,400</span></span></p></td>
    <td><p><span data-ttu-id="4016c-269">700</span><span class="sxs-lookup"><span data-stu-id="4016c-269">700</span></span></p></td>
    <td><p><span data-ttu-id="4016c-270">172.29.79.0/23、157.57.215.0/25、172.29.90.0/23、172.29.80.0/24</span><span class="sxs-lookup"><span data-stu-id="4016c-270">172.29.79.0/23, 157.57.215.0/25, 172.29.90.0/23, 172.29.80.0/24</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="4016c-271">リノ</span><span class="sxs-lookup"><span data-stu-id="4016c-271">Reno</span></span></p></td>
    <td><p><span data-ttu-id="4016c-272">北アメリカ</span><span class="sxs-lookup"><span data-stu-id="4016c-272">North America</span></span></p></td>
    <td><p><span data-ttu-id="4016c-273">1万</span><span class="sxs-lookup"><span data-stu-id="4016c-273">10,000</span></span></p></td>
    <td><p><span data-ttu-id="4016c-274">4000</span><span class="sxs-lookup"><span data-stu-id="4016c-274">4,000</span></span></p></td>
    <td><p><span data-ttu-id="4016c-275">175</span><span class="sxs-lookup"><span data-stu-id="4016c-275">175</span></span></p></td>
    <td><p><span data-ttu-id="4016c-276">2800</span><span class="sxs-lookup"><span data-stu-id="4016c-276">2,800</span></span></p></td>
    <td><p><span data-ttu-id="4016c-277">700</span><span class="sxs-lookup"><span data-stu-id="4016c-277">700</span></span></p></td>
    <td><p><span data-ttu-id="4016c-278">157.57.210.0/23、172.28.151.128、25</span><span class="sxs-lookup"><span data-stu-id="4016c-278">157.57.210.0/23, 172.28.151.128/25</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="4016c-279">ポートランド</span><span class="sxs-lookup"><span data-stu-id="4016c-279">Portland</span></span></p></td>
    <td><p><span data-ttu-id="4016c-280">北アメリカ</span><span class="sxs-lookup"><span data-stu-id="4016c-280">North America</span></span></p></td>
    <td><p><span data-ttu-id="4016c-281">5,000</span><span class="sxs-lookup"><span data-stu-id="4016c-281">5,000</span></span></p></td>
    <td><p><span data-ttu-id="4016c-282">4000</span><span class="sxs-lookup"><span data-stu-id="4016c-282">4,000</span></span></p></td>
    <td><p><span data-ttu-id="4016c-283">175</span><span class="sxs-lookup"><span data-stu-id="4016c-283">175</span></span></p></td>
    <td><p><span data-ttu-id="4016c-284">2800</span><span class="sxs-lookup"><span data-stu-id="4016c-284">2,800</span></span></p></td>
    <td><p><span data-ttu-id="4016c-285">700</span><span class="sxs-lookup"><span data-stu-id="4016c-285">700</span></span></p></td>
    <td><p><span data-ttu-id="4016c-286">172.29.77.0/24 10.71.108.0/24、157.57.208.0/23</span><span class="sxs-lookup"><span data-stu-id="4016c-286">172.29.77.0/24 10.71.108.0/24, 157.57.208.0/23</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="4016c-287">ニューヨーク</span><span class="sxs-lookup"><span data-stu-id="4016c-287">New York</span></span></p></td>
    <td><p><span data-ttu-id="4016c-288">北アメリカ</span><span class="sxs-lookup"><span data-stu-id="4016c-288">North America</span></span></p></td>
    <td><p><span data-ttu-id="4016c-289">(制限なし)</span><span class="sxs-lookup"><span data-stu-id="4016c-289">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="4016c-290">(制限なし)</span><span class="sxs-lookup"><span data-stu-id="4016c-290">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="4016c-291">(制限なし)</span><span class="sxs-lookup"><span data-stu-id="4016c-291">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="4016c-292">(制限なし)</span><span class="sxs-lookup"><span data-stu-id="4016c-292">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="4016c-293">(制限なし)</span><span class="sxs-lookup"><span data-stu-id="4016c-293">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="4016c-294">172.29.80.0/23、157.57.216.0/25、172.29.91.0/23、172.29.81.0/24</span><span class="sxs-lookup"><span data-stu-id="4016c-294">172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="4016c-295">シカゴ</span><span class="sxs-lookup"><span data-stu-id="4016c-295">Chicago</span></span></p></td>
    <td><p><span data-ttu-id="4016c-296">北アメリカ</span><span class="sxs-lookup"><span data-stu-id="4016c-296">North America</span></span></p></td>
    <td><p><span data-ttu-id="4016c-297">(制限なし)</span><span class="sxs-lookup"><span data-stu-id="4016c-297">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="4016c-298">(制限なし)</span><span class="sxs-lookup"><span data-stu-id="4016c-298">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="4016c-299">(制限なし)</span><span class="sxs-lookup"><span data-stu-id="4016c-299">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="4016c-300">(制限なし)</span><span class="sxs-lookup"><span data-stu-id="4016c-300">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="4016c-301">(制限なし)</span><span class="sxs-lookup"><span data-stu-id="4016c-301">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="4016c-302">157.57.211.0/23、172.28.152.128、25</span><span class="sxs-lookup"><span data-stu-id="4016c-302">157.57.211.0/23, 172.28.152.128/25</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="4016c-303">デトロイト</span><span class="sxs-lookup"><span data-stu-id="4016c-303">Detroit</span></span></p></td>
    <td><p><span data-ttu-id="4016c-304">北アメリカ</span><span class="sxs-lookup"><span data-stu-id="4016c-304">North America</span></span></p></td>
    <td><p><span data-ttu-id="4016c-305">(制限なし)</span><span class="sxs-lookup"><span data-stu-id="4016c-305">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="4016c-306">(制限なし)</span><span class="sxs-lookup"><span data-stu-id="4016c-306">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="4016c-307">(制限なし)</span><span class="sxs-lookup"><span data-stu-id="4016c-307">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="4016c-308">(制限なし)</span><span class="sxs-lookup"><span data-stu-id="4016c-308">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="4016c-309">(制限なし)</span><span class="sxs-lookup"><span data-stu-id="4016c-309">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="4016c-310">172.29.78.0/24 10.71.109.0/24、157.57.209.0/23</span><span class="sxs-lookup"><span data-stu-id="4016c-310">172.29.78.0/24 10.71.109.0/24, 157.57.209.0/23</span></span></p></td>
    </tr>
    </tbody>
    </table>


7.  <span data-ttu-id="4016c-311">Lync Server の通話受付制御では、ネットワーク領域間の接続は*地域リンク*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="4016c-311">In Lync Server call admission control, the connections between network regions are called *region links*.</span></span> <span data-ttu-id="4016c-312">各地域のリンクについて、ネットワークサイトの場合と同様に、次のことを確認します。</span><span class="sxs-lookup"><span data-stu-id="4016c-312">For each region link, determine the following, just as you did for the network sites:</span></span>
    
      - <span data-ttu-id="4016c-313">すべての同時音声セッションに対して設定する全体的な帯域幅制限。</span><span class="sxs-lookup"><span data-stu-id="4016c-313">Overall bandwidth limit that you want to set for all concurrent audio sessions.</span></span> <span data-ttu-id="4016c-314">新しいオーディオセッションによってこの制限を超過すると、Lync Server ではセッションの開始が許可されません。</span><span class="sxs-lookup"><span data-stu-id="4016c-314">If a new audio session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="4016c-315">個々のオーディオセッションごとに設定する帯域幅の制限。</span><span class="sxs-lookup"><span data-stu-id="4016c-315">Bandwidth limit that you want to set for each individual audio session.</span></span> <span data-ttu-id="4016c-316">既定の CAC 帯域幅制限は 175 kbps ですが、管理者が変更することができます。</span><span class="sxs-lookup"><span data-stu-id="4016c-316">The default CAC bandwidth limit is 175 kbps, but it can be modified by the administrator.</span></span>
    
      - <span data-ttu-id="4016c-317">すべての同時ビデオセッションに対して設定する全体的な帯域幅制限。</span><span class="sxs-lookup"><span data-stu-id="4016c-317">Overall bandwidth limit that you want to set for all concurrent video sessions.</span></span> <span data-ttu-id="4016c-318">新しいビデオセッションによってこの制限を超過する場合、Lync Server ではセッションの開始が許可されません。</span><span class="sxs-lookup"><span data-stu-id="4016c-318">If a new video session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="4016c-319">個々のビデオセッションに対して設定する帯域幅の制限。</span><span class="sxs-lookup"><span data-stu-id="4016c-319">Bandwidth limit that you want to set for each individual video session.</span></span> <span data-ttu-id="4016c-320">既定の CAC 帯域幅制限は 700 kbps ですが、管理者が変更することができます。</span><span class="sxs-lookup"><span data-stu-id="4016c-320">The default CAC bandwidth limit is 700 kbps, but it can be modified by the administrator.</span></span>
    
    <span data-ttu-id="4016c-321">**帯域幅の制限が関連付けられたネットワーク領域のリンク**</span><span class="sxs-lookup"><span data-stu-id="4016c-321">**Network Region links with associated bandwidth limits**</span></span>
    
    <span data-ttu-id="4016c-322">![3 つの地域間の制限の例](images/Gg425827.25259afa-ee7c-4d26-bc41-92ba9cb56dec(OCS.15).jpg "3 つの地域間の制限の例")</span><span class="sxs-lookup"><span data-stu-id="4016c-322">![Example of Limitations between 3 Regions](images/Gg425827.25259afa-ee7c-4d26-bc41-92ba9cb56dec(OCS.15).jpg "Example of Limitations between 3 Regions")</span></span>  
    
    ### <a name="region-link-bandwidth-information-bandwidth-in-kbps"></a><span data-ttu-id="4016c-323">地域リンクの帯域幅情報 (kbps の帯域幅)</span><span class="sxs-lookup"><span data-stu-id="4016c-323">Region Link Bandwidth Information (Bandwidth in kbps)</span></span>
    
    <table>
    <colgroup>
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="4016c-324">地域リンク名</span><span class="sxs-lookup"><span data-stu-id="4016c-324">Region Link Name</span></span></th>
    <th><span data-ttu-id="4016c-325">First Region</span><span class="sxs-lookup"><span data-stu-id="4016c-325">First Region</span></span></th>
    <th><span data-ttu-id="4016c-326">Second Region</span><span class="sxs-lookup"><span data-stu-id="4016c-326">Second Region</span></span></th>
    <th><span data-ttu-id="4016c-327">BW Limit</span><span class="sxs-lookup"><span data-stu-id="4016c-327">BW Limit</span></span></th>
    <th><span data-ttu-id="4016c-328">オーディオ制限</span><span class="sxs-lookup"><span data-stu-id="4016c-328">Audio Limit</span></span></th>
    <th><span data-ttu-id="4016c-329">オーディオセッションの制限</span><span class="sxs-lookup"><span data-stu-id="4016c-329">Audio Session Limit</span></span></th>
    <th><span data-ttu-id="4016c-330">ビデオの制限</span><span class="sxs-lookup"><span data-stu-id="4016c-330">Video Limit</span></span></th>
    <th><span data-ttu-id="4016c-331">ビデオセッションの制限</span><span class="sxs-lookup"><span data-stu-id="4016c-331">Video Session Limit</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="4016c-332">NA-EMEA-リンク</span><span class="sxs-lookup"><span data-stu-id="4016c-332">NA-EMEA-LINK</span></span></p></td>
    <td><p><span data-ttu-id="4016c-333">北アメリカ</span><span class="sxs-lookup"><span data-stu-id="4016c-333">North America</span></span></p></td>
    <td><p><span data-ttu-id="4016c-334">EMEA</span><span class="sxs-lookup"><span data-stu-id="4016c-334">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="4016c-335">5万</span><span class="sxs-lookup"><span data-stu-id="4016c-335">50,000</span></span></p></td>
    <td><p><span data-ttu-id="4016c-336">2万</span><span class="sxs-lookup"><span data-stu-id="4016c-336">20,000</span></span></p></td>
    <td><p><span data-ttu-id="4016c-337">175</span><span class="sxs-lookup"><span data-stu-id="4016c-337">175</span></span></p></td>
    <td><p><span data-ttu-id="4016c-338">14000</span><span class="sxs-lookup"><span data-stu-id="4016c-338">14,000</span></span></p></td>
    <td><p><span data-ttu-id="4016c-339">700</span><span class="sxs-lookup"><span data-stu-id="4016c-339">700</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="4016c-340">EMEA-APAC リンク</span><span class="sxs-lookup"><span data-stu-id="4016c-340">EMEA-APAC-LINK</span></span></p></td>
    <td><p><span data-ttu-id="4016c-341">EMEA</span><span class="sxs-lookup"><span data-stu-id="4016c-341">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="4016c-342">APAC</span><span class="sxs-lookup"><span data-stu-id="4016c-342">APAC</span></span></p></td>
    <td><p><span data-ttu-id="4016c-343">25,000</span><span class="sxs-lookup"><span data-stu-id="4016c-343">25,000</span></span></p></td>
    <td><p><span data-ttu-id="4016c-344">1万</span><span class="sxs-lookup"><span data-stu-id="4016c-344">10,000</span></span></p></td>
    <td><p><span data-ttu-id="4016c-345">175</span><span class="sxs-lookup"><span data-stu-id="4016c-345">175</span></span></p></td>
    <td><p><span data-ttu-id="4016c-346">7000</span><span class="sxs-lookup"><span data-stu-id="4016c-346">7,000</span></span></p></td>
    <td><p><span data-ttu-id="4016c-347">700</span><span class="sxs-lookup"><span data-stu-id="4016c-347">700</span></span></p></td>
    </tr>
    </tbody>
    </table>


8.  <span data-ttu-id="4016c-348">ネットワーク地域のすべてのペア間のルートを定義します。</span><span class="sxs-lookup"><span data-stu-id="4016c-348">Define a route between every pair of network regions.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="4016c-349">北アメリカと APAC の地域間のルートには、直接接続する地域のリンクがないため、2つのリンクが必要です。</span><span class="sxs-lookup"><span data-stu-id="4016c-349">Two links are required for the route between the North America and APAC regions because there is no region link that directly connects them.</span></span>

    
    </div>
    
    ### <a name="region-routes"></a><span data-ttu-id="4016c-350">地域ルート</span><span class="sxs-lookup"><span data-stu-id="4016c-350">Region Routes</span></span>
    
    <table>
    <colgroup>
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="4016c-351">地域ルート名</span><span class="sxs-lookup"><span data-stu-id="4016c-351">Region Route Name</span></span></th>
    <th><span data-ttu-id="4016c-352">First Region</span><span class="sxs-lookup"><span data-stu-id="4016c-352">First Region</span></span></th>
    <th><span data-ttu-id="4016c-353">Second Region</span><span class="sxs-lookup"><span data-stu-id="4016c-353">Second Region</span></span></th>
    <th><span data-ttu-id="4016c-354">地域リンク</span><span class="sxs-lookup"><span data-stu-id="4016c-354">Region Links</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="4016c-355">NA-EMEA-ルート</span><span class="sxs-lookup"><span data-stu-id="4016c-355">NA-EMEA-ROUTE</span></span></p></td>
    <td><p><span data-ttu-id="4016c-356">北アメリカ</span><span class="sxs-lookup"><span data-stu-id="4016c-356">North America</span></span></p></td>
    <td><p><span data-ttu-id="4016c-357">EMEA</span><span class="sxs-lookup"><span data-stu-id="4016c-357">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="4016c-358">NA-EMEA-リンク</span><span class="sxs-lookup"><span data-stu-id="4016c-358">NA-EMEA-LINK</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="4016c-359">EMEA-APAC-ルート</span><span class="sxs-lookup"><span data-stu-id="4016c-359">EMEA-APAC-ROUTE</span></span></p></td>
    <td><p><span data-ttu-id="4016c-360">EMEA</span><span class="sxs-lookup"><span data-stu-id="4016c-360">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="4016c-361">APAC</span><span class="sxs-lookup"><span data-stu-id="4016c-361">APAC</span></span></p></td>
    <td><p><span data-ttu-id="4016c-362">EMEA-APAC リンク</span><span class="sxs-lookup"><span data-stu-id="4016c-362">EMEA-APAC-LINK</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="4016c-363">NA-APAC-ルート</span><span class="sxs-lookup"><span data-stu-id="4016c-363">NA-APAC-ROUTE</span></span></p></td>
    <td><p><span data-ttu-id="4016c-364">北アメリカ</span><span class="sxs-lookup"><span data-stu-id="4016c-364">North America</span></span></p></td>
    <td><p><span data-ttu-id="4016c-365">APAC</span><span class="sxs-lookup"><span data-stu-id="4016c-365">APAC</span></span></p></td>
    <td><p><span data-ttu-id="4016c-366">NA-EMEA-リンク、EMEA-APAC リンク</span><span class="sxs-lookup"><span data-stu-id="4016c-366">NA-EMEA-LINK, EMEA-APAC-LINK</span></span></p></td>
    </tr>
    </tbody>
    </table>


9.  <span data-ttu-id="4016c-367">1つのリンク (*サイト間*リンクと呼ばれます) によって直接接続されているネットワークサイトのペアごとに、次のことを確認します。</span><span class="sxs-lookup"><span data-stu-id="4016c-367">For every pair of network sites that are directly connected by a single link (called an *inter-site* link), determine the following:</span></span>
    
      - <span data-ttu-id="4016c-368">すべての同時音声セッションに対して設定する全体的な帯域幅制限。</span><span class="sxs-lookup"><span data-stu-id="4016c-368">Overall bandwidth limit that you want to set for all concurrent audio sessions.</span></span> <span data-ttu-id="4016c-369">新しいオーディオセッションによってこの制限を超過すると、Lync Server ではセッションの開始が許可されません。</span><span class="sxs-lookup"><span data-stu-id="4016c-369">If a new audio session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="4016c-370">個々のオーディオセッションごとに設定する帯域幅の制限。</span><span class="sxs-lookup"><span data-stu-id="4016c-370">Bandwidth limit that you want to set for each individual audio session.</span></span> <span data-ttu-id="4016c-371">既定の CAC 帯域幅制限は 175 kbps ですが、管理者が変更することができます。</span><span class="sxs-lookup"><span data-stu-id="4016c-371">The default CAC bandwidth limit is 175 kbps, but it can be modified by the administrator.</span></span>
    
      - <span data-ttu-id="4016c-372">すべての同時ビデオセッションに対して設定する全体的な帯域幅制限。</span><span class="sxs-lookup"><span data-stu-id="4016c-372">Overall bandwidth limit that you want to set for all concurrent video sessions.</span></span> <span data-ttu-id="4016c-373">新しいビデオセッションによってこの制限を超過する場合、Lync Server ではセッションの開始が許可されません。</span><span class="sxs-lookup"><span data-stu-id="4016c-373">If a new video session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="4016c-374">個々のビデオセッションに対して設定する帯域幅の制限。</span><span class="sxs-lookup"><span data-stu-id="4016c-374">Bandwidth limit that you want to set for each individual video session.</span></span> <span data-ttu-id="4016c-375">既定の CAC 帯域幅制限は 700 kbps ですが、管理者が変更することができます。</span><span class="sxs-lookup"><span data-stu-id="4016c-375">The default CAC bandwidth limit is 700 kbps, but it can be modified by the administrator.</span></span>
    
    <span data-ttu-id="4016c-376">**Reno とアルバカーキの間にあるサイト間リンクの帯域幅と帯域幅の制限を示す CAC ネットワークの地域 (北アメリカ)**</span><span class="sxs-lookup"><span data-stu-id="4016c-376">**CAC network region North America showing the bandwidth capacities and bandwidth limits for the inter-site link between Reno and Albuquerque**</span></span>
    
    <span data-ttu-id="4016c-377">![WAN の帯域幅の例によって制約]されたネットワークサイト(images/Gg425827.063e5e1d-b6c8-4e8c-98db-c227c78f671d(OCS.15).jpg "WAN の帯域幅の例によって制約")されたネットワークサイト</span><span class="sxs-lookup"><span data-stu-id="4016c-377">![Network Sites Constrained by WAN Bandwidth example](images/Gg425827.063e5e1d-b6c8-4e8c-98db-c227c78f671d(OCS.15).jpg "Network Sites Constrained by WAN Bandwidth example")</span></span>  
    
    ### <a name="bandwidth-information-for-an-inter-site-link-between-two-network-sites-bandwidth-in-kbps"></a><span data-ttu-id="4016c-378">2つのネットワークサイト間のサイト間リンクの帯域幅情報 (kbps 単位の帯域幅)</span><span class="sxs-lookup"><span data-stu-id="4016c-378">Bandwidth Information for an Inter-Site Link between Two Network Sites (Bandwidth in kbps)</span></span>
    
    <table>
    <colgroup>
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="4016c-379">サイト間リンク名</span><span class="sxs-lookup"><span data-stu-id="4016c-379">Inter-Site Link Name</span></span></th>
    <th><span data-ttu-id="4016c-380">第1のサイト</span><span class="sxs-lookup"><span data-stu-id="4016c-380">First Site</span></span></th>
    <th><span data-ttu-id="4016c-381">第2のサイト</span><span class="sxs-lookup"><span data-stu-id="4016c-381">Second Site</span></span></th>
    <th><span data-ttu-id="4016c-382">BW Limit</span><span class="sxs-lookup"><span data-stu-id="4016c-382">BW Limit</span></span></th>
    <th><span data-ttu-id="4016c-383">オーディオ制限</span><span class="sxs-lookup"><span data-stu-id="4016c-383">Audio Limit</span></span></th>
    <th><span data-ttu-id="4016c-384">オーディオセッションの制限</span><span class="sxs-lookup"><span data-stu-id="4016c-384">Audio Session Limit</span></span></th>
    <th><span data-ttu-id="4016c-385">ビデオの制限</span><span class="sxs-lookup"><span data-stu-id="4016c-385">Video Limit</span></span></th>
    <th><span data-ttu-id="4016c-386">ビデオセッションの制限</span><span class="sxs-lookup"><span data-stu-id="4016c-386">Video Session Limit</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="4016c-387">Reno-Albu-サイト間リンク</span><span class="sxs-lookup"><span data-stu-id="4016c-387">Reno-Albu-Intersite-Link</span></span></p></td>
    <td><p><span data-ttu-id="4016c-388">リノ</span><span class="sxs-lookup"><span data-stu-id="4016c-388">Reno</span></span></p></td>
    <td><p><span data-ttu-id="4016c-389">アルバカーキ</span><span class="sxs-lookup"><span data-stu-id="4016c-389">Albuquerque</span></span></p></td>
    <td><p><span data-ttu-id="4016c-390">2万</span><span class="sxs-lookup"><span data-stu-id="4016c-390">20,000</span></span></p></td>
    <td><p><span data-ttu-id="4016c-391">12000</span><span class="sxs-lookup"><span data-stu-id="4016c-391">12,000</span></span></p></td>
    <td><p><span data-ttu-id="4016c-392">175</span><span class="sxs-lookup"><span data-stu-id="4016c-392">175</span></span></p></td>
    <td><p><span data-ttu-id="4016c-393">5,000</span><span class="sxs-lookup"><span data-stu-id="4016c-393">5,000</span></span></p></td>
    <td><p><span data-ttu-id="4016c-394">700</span><span class="sxs-lookup"><span data-stu-id="4016c-394">700</span></span></p></td>
    </tr>
    </tbody>
    </table>


<div>

## <a name="next-steps"></a><span data-ttu-id="4016c-395">次のステップ</span><span class="sxs-lookup"><span data-stu-id="4016c-395">Next Steps</span></span>

<span data-ttu-id="4016c-396">必要な情報を収集した後は、Lync Server 管理シェルまたは Lync Server コントロールパネルを使用して、CAC 展開を実行できます。</span><span class="sxs-lookup"><span data-stu-id="4016c-396">After you have gathered the required information, you can perform CAC deployment either by using the Lync Server Management Shell or Lync Server Control Panel.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="4016c-397">Lync Server コントロールパネルを使用して、ほとんどのネットワーク構成タスクを実行できますが、サブネットとサイト間リンクを作成するには、Lync Server 管理シェルを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4016c-397">Although you can perform most network configuration tasks by using Lync Server Control Panel, to create subnets and intersite links, you must use Lync Server Management Shell.</span></span> <span data-ttu-id="4016c-398">詳細については、<STRONG>新しい-CsNetworkSubnet</STRONG>コマンドレットと<STRONG>CsNetworkIntersitePolicy</STRONG>コマンドレットの Lync Server 管理シェルのマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4016c-398">For details, see the Lync Server Management Shell documentation for the <STRONG>New-CsNetworkSubnet</STRONG> cmdlet and the <STRONG>New-CsNetworkIntersitePolicy</STRONG> cmdlet.</span></span>



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

