---
title: 通話受付管理の要件の収集例
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Example of gathering your requirements for call admission control
ms:assetid: 3363ac53-b7c4-4a59-aea1-b2f3ee016ae1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425827(v=OCS.15)
ms:contentKeyID: 48183820
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 89983ae54e879bdb55691b33a0512a00e5883735
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528444"
---
# <a name="example-gathering-your-requirements-for-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="d8a58-102">例: Lync Server 2013 での通話受付管理の要件の収集</span><span class="sxs-lookup"><span data-stu-id="d8a58-102">Example: Gathering your requirements for call admission control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d8a58-103">_**トピックの最終更新日:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="d8a58-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="d8a58-p101">この例では、通話受付管理 (CAC) の計画および実装方法を示します。これは大まかに次の作業で構成されます。</span><span class="sxs-lookup"><span data-stu-id="d8a58-p101">This example shows you how to plan for and implement call admission control (CAC). At a high level, this consists of the following activities:</span></span>

1.  <span data-ttu-id="d8a58-106">すべてのネットワーク ハブおよびバックボーン (\*\* ネットワーク地域とも呼ばれます) を特定します。</span><span class="sxs-lookup"><span data-stu-id="d8a58-106">Identify all of your network hubs and backbones (known as *network regions*).</span></span>

2.  <span data-ttu-id="d8a58-107">各ネットワーク地域の CAC を管理する Lync Server 中央サイトを特定します。</span><span class="sxs-lookup"><span data-stu-id="d8a58-107">Identify the Lync Server central site that will manage CAC for each network region.</span></span>

3.  <span data-ttu-id="d8a58-108">各ネットワーク地域に接続される*ネットワーク サイト*を特定および定義します。</span><span class="sxs-lookup"><span data-stu-id="d8a58-108">Identify and define the *network sites* that are connected to each network region.</span></span>

4.  <span data-ttu-id="d8a58-109">WAN への接続が帯域幅に制限されている各ネットワークサイトについて、WAN 接続の帯域幅の容量と、該当する場合は、ネットワーク管理者が Lync Server メディアトラフィックに設定した帯域幅制限を説明します。</span><span class="sxs-lookup"><span data-stu-id="d8a58-109">For each network site whose connection to the WAN is bandwidth-constrained, describe the bandwidth capacity of the WAN connection and the bandwidth limits that to the network administrator has set for Lync Server media traffic, if applicable.</span></span> <span data-ttu-id="d8a58-110">WAN への接続に帯域幅の制限がないサイトは含める必要はありません。</span><span class="sxs-lookup"><span data-stu-id="d8a58-110">You do not need to include sites whose connection to the WAN is not bandwidth-constrained.</span></span>

5.  <span data-ttu-id="d8a58-111">ネットワークの各サブネットをネットワーク サイトに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="d8a58-111">Associate each subnet in your network with a network site.</span></span>

6.  <span data-ttu-id="d8a58-112">ネットワーク地域間のリンクをマップします。</span><span class="sxs-lookup"><span data-stu-id="d8a58-112">Map the links between the network regions.</span></span> <span data-ttu-id="d8a58-113">各リンクについて、帯域幅の容量と、ネットワーク管理者が Lync Server メディアトラフィックに対して行った制限を説明します。</span><span class="sxs-lookup"><span data-stu-id="d8a58-113">For each link, describe its bandwidth capacity and any limits that the network administrator has placed on Lync Server media traffic.</span></span>

7.  <span data-ttu-id="d8a58-114">ネットワーク地域のすべてのペア間のルートを定義します。</span><span class="sxs-lookup"><span data-stu-id="d8a58-114">Define a route between every pair of network regions.</span></span>

<div>

## <a name="gather-the-required-information"></a><span data-ttu-id="d8a58-115">必要な情報の収集</span><span class="sxs-lookup"><span data-stu-id="d8a58-115">Gather the Required Information</span></span>

<span data-ttu-id="d8a58-116">通話受付管理の準備を行うには、次の手順で示されている情報を収集します。</span><span class="sxs-lookup"><span data-stu-id="d8a58-116">To prepare for call admission control, gather the information described in the following steps:</span></span>

1.  <span data-ttu-id="d8a58-p104">ネットワーク地域を特定します。 ネットワーク地域とは、ネットワーク バックボーンまたはネットワーク ハブを示します。</span><span class="sxs-lookup"><span data-stu-id="d8a58-p104">Identify your network regions. A network region represents a network backbone or a network hub.</span></span>
    
    <span data-ttu-id="d8a58-p105">ネットワーク バックボーンまたはネットワーク ハブとは、異なる LAN またはサブネット間の情報交換用パスを提供して、ネットワークの様々な部分を相互接続するコンピューター ネットワーク インフラストラクチャの一部です。 バックボーンは、小規模ロケーションから地理的に広範囲な地域まで、様々なネットワークを繋ぐことができます。 通常、バックボーンの処理能力はバックボーンに接続するネットワークの処理能力よりも高くなっています。</span><span class="sxs-lookup"><span data-stu-id="d8a58-p105">A network backbone or a network hub is a part of computer network infrastructure that interconnects various pieces of network, providing a path for the exchange of information between different LANs or subnets. A backbone can tie together diverse networks, from a small location to a wide geographic area. The backbone's capacity is typically greater than that of the networks connected to it.</span></span>
    
    <span data-ttu-id="d8a58-p106">このトポロジ例では、3 つのネットワーク地域が存在します。 北アメリカ、EMEA、および APAC。 ネットワーク地域にはネットワーク サイトのコレクションが含まれます。 ネットワーク管理者と協力して、組織のネットワーク地域を定義します。</span><span class="sxs-lookup"><span data-stu-id="d8a58-p106">Our example topology has three network regions: North America, EMEA, and APAC. A network region contains a collection of network sites. Work with your network administrator to define the network regions for your enterprise.</span></span>

2.  <span data-ttu-id="d8a58-125">各ネットワーク地域が関連付けられている中央サイトを特定します。</span><span class="sxs-lookup"><span data-stu-id="d8a58-125">Identify each network region’s associated central site.</span></span> <span data-ttu-id="d8a58-126">中央サイトには少なくとも1つのフロントエンドサーバーが含まれており、ネットワーク地域の WAN 接続を通過するすべてのメディアトラフィックについて CAC を管理する Lync Server の展開です。</span><span class="sxs-lookup"><span data-stu-id="d8a58-126">A central site contains at least one Front End Server and is the Lync Server deployment that will manage CAC for all media traffic that passes through the network region’s WAN connection.</span></span>
    
    <span data-ttu-id="d8a58-127">**3 つのネットワーク地域に分けられたエンタープライズ ネットワークの例**</span><span class="sxs-lookup"><span data-stu-id="d8a58-127">**An example enterprise network divided into three network regions**</span></span>
    
    <span data-ttu-id="d8a58-128">![3つのネットワーク地域を含むネットワークトポロジの例](images/Gg425827.08937347-250f-488f-ba5f-c256e6afcd8b(OCS.15).jpg "3つのネットワーク地域を含むネットワークトポロジの例")</span><span class="sxs-lookup"><span data-stu-id="d8a58-128">![Network Topology Example with 3 Network Regions](images/Gg425827.08937347-250f-488f-ba5f-c256e6afcd8b(OCS.15).jpg "Network Topology Example with 3 Network Regions")</span></span>  
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="d8a58-129">Multiprotocol Label Switching (MPLS) ネットワークは、それぞれの地理的な場所が対応するネットワーク サイトを有する、ネットワーク地域として表される必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8a58-129">A Multiprotocol Label Switching (MPLS) network should be represented as a network region in which each geographic location has a corresponding network site.</span></span> <span data-ttu-id="d8a58-130">詳細については、「計画」のドキュメントの「<A href="lync-server-2013-call-admission-control-on-an-mpls-network.md">Lync Server を使用した MPLS ネットワーク上の通話受付管理 (Lync Server 2013 を使用した</A>場合)」トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8a58-130">For details, see the “<A href="lync-server-2013-call-admission-control-on-an-mpls-network.md">Call admission control on an MPLS network with Lync Server 2013</A>” topic in the Planning documentation.</span></span>

    
    </div>
    
    <span data-ttu-id="d8a58-131">前述のネットワークトポロジの例では、3つのネットワーク地域があり、それぞれには CAC を管理する Lync Server 中央サイトがあります。</span><span class="sxs-lookup"><span data-stu-id="d8a58-131">In the preceding example network topology, there are three network regions, each with a Lync Server central site that manages CAC.</span></span> <span data-ttu-id="d8a58-132">ネットワーク地域の適切な中央サイトは、地理的な近さによって選ばれます。</span><span class="sxs-lookup"><span data-stu-id="d8a58-132">The appropriate central site for a network region is chosen by the geographic vicinity.</span></span> <span data-ttu-id="d8a58-133">メディア トラフィックはネットワーク地域内で最も重くなるため、所有権が地理的な近さで決まることで自己完結型となり、その他の中央サイトが使用できなくなった場合でも、機能し続けます。</span><span class="sxs-lookup"><span data-stu-id="d8a58-133">Because media traffic will be heaviest within network regions, the ownership by geographic vicinity makes it self-contained and will continue to be functional even if other central sites become unavailable.</span></span>
    
    <span data-ttu-id="d8a58-134">この例では、シカゴという名前の Lync Server 展開は、北米地域の中央サイトです。</span><span class="sxs-lookup"><span data-stu-id="d8a58-134">In this example, a Lync Server deployment named Chicago is the central site for the North America region.</span></span>
    
    <span data-ttu-id="d8a58-135">北米のすべての Lync ユーザーは、シカゴ展開のサーバーに所属しています。</span><span class="sxs-lookup"><span data-stu-id="d8a58-135">All Lync users in North America are homed on servers in the Chicago deployment.</span></span> <span data-ttu-id="d8a58-136">次の表に 3 つすべてのネットワーク地域の中央サイトを示します。</span><span class="sxs-lookup"><span data-stu-id="d8a58-136">The following table shows central sites for all three network regions.</span></span>
    
    ### <a name="network-regions-and-their-associated-central-sites"></a><span data-ttu-id="d8a58-137">ネットワーク地域と関連付けられた中央サイト</span><span class="sxs-lookup"><span data-stu-id="d8a58-137">Network Regions and their Associated Central Sites</span></span>
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="d8a58-138">ネットワーク地域</span><span class="sxs-lookup"><span data-stu-id="d8a58-138">Network Region</span></span></th>
    <th><span data-ttu-id="d8a58-139">中央サイト</span><span class="sxs-lookup"><span data-stu-id="d8a58-139">Central Site</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="d8a58-140">北アメリカ</span><span class="sxs-lookup"><span data-stu-id="d8a58-140">North America</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-141">Chicago</span><span class="sxs-lookup"><span data-stu-id="d8a58-141">Chicago</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="d8a58-142">EMEA</span><span class="sxs-lookup"><span data-stu-id="d8a58-142">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-143">北海道</span><span class="sxs-lookup"><span data-stu-id="d8a58-143">London</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="d8a58-144">APAC</span><span class="sxs-lookup"><span data-stu-id="d8a58-144">APAC</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-145">北京</span><span class="sxs-lookup"><span data-stu-id="d8a58-145">Beijing</span></span></p></td>
    </tr>
    </tbody>
    </table>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="d8a58-146">Lync Server トポロジに応じて、同じ中央サイトを複数のネットワーク地域に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="d8a58-146">Depending on your Lync Server topology, the same central site can be assigned to multiple network regions.</span></span>

    
    </div>

3.  <span data-ttu-id="d8a58-p111">それぞれのネットワーク地域で、帯域幅に制限がない WAN 接続を有するネットワーク サイト (オフィスまたは場所) すべてを特定します。 これらのサイトは帯域幅の制限がないため、CAC 帯域幅ポリシーを適用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="d8a58-p111">For each network region, identify all of the network sites (offices or locations) whose WAN connections are not bandwidth-constrained. Because these sites are not bandwidth constrained, you do not need to apply CAC bandwidth policies to them.</span></span>
    
    <span data-ttu-id="d8a58-149">次の表に示されている例では、3 つのネットワークサイトには帯域幅の制限がある WAN リンクがありません: ニューヨーク、シカゴ、およびデトロイト。</span><span class="sxs-lookup"><span data-stu-id="d8a58-149">In the example shown in the following table, three network sites do not have bandwidth-constrained WAN links: New York, Chicago, and Detroit.</span></span>
    
    ### <a name="network-sites-not-constrained-by-wan-bandwidth"></a><span data-ttu-id="d8a58-150">WAN 帯域幅による制限がないネットワーク サイト</span><span class="sxs-lookup"><span data-stu-id="d8a58-150">Network Sites not Constrained by WAN Bandwidth</span></span>
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="d8a58-151">ネットワーク サイト</span><span class="sxs-lookup"><span data-stu-id="d8a58-151">Network Site</span></span></th>
    <th><span data-ttu-id="d8a58-152">ネットワーク地域</span><span class="sxs-lookup"><span data-stu-id="d8a58-152">Network Region</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="d8a58-153">ニューヨーク</span><span class="sxs-lookup"><span data-stu-id="d8a58-153">New York</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-154">北アメリカ</span><span class="sxs-lookup"><span data-stu-id="d8a58-154">North America</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="d8a58-155">Chicago</span><span class="sxs-lookup"><span data-stu-id="d8a58-155">Chicago</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-156">北アメリカ</span><span class="sxs-lookup"><span data-stu-id="d8a58-156">North America</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="d8a58-157">市</span><span class="sxs-lookup"><span data-stu-id="d8a58-157">Detroit</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-158">北アメリカ</span><span class="sxs-lookup"><span data-stu-id="d8a58-158">North America</span></span></p></td>
    </tr>
    </tbody>
    </table>


4.  <span data-ttu-id="d8a58-159">それぞれのネットワーク地域で、帯域幅の制限がある WAN リンクを介してネットワーク地域に接続しているすべてのネットワーク サイトを特定します。</span><span class="sxs-lookup"><span data-stu-id="d8a58-159">For each network region, identify all of the network sites that connect to the network region through bandwidth-constrained WAN links.</span></span>
    
    <span data-ttu-id="d8a58-160">音声およびビデオの品質を確実なものにできるように、これらの帯域幅の制限があるネットワーク サイトは、WAN を監視し、ネットワーク地域への、およびネットワーク地域からのメディア (音声またはビデオ) トラフィック フローを制限する CAC 帯域幅ポリシーを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d8a58-160">To help ensure audio and video quality, we recommend that these bandwidth-constrained network sites have their WANs monitored and CAC bandwidth policies that limit media (voice or video) traffic flow to and from the network region.</span></span>
    
    <span data-ttu-id="d8a58-161">次の表に示されている例では、WAN 帯域幅による制限がある 3 つのネットワーク サイトが存在します。 ポートランド、リノ、およびアルバカーキ。</span><span class="sxs-lookup"><span data-stu-id="d8a58-161">In the example shown in the following table, there are three network sites that are constrained by WAN bandwidth: Portland, Reno and Albuquerque.</span></span>
    
    ### <a name="network-sites-constrained-by-wan-bandwidth"></a><span data-ttu-id="d8a58-162">WAN 帯域幅による制限があるネットワーク サイト</span><span class="sxs-lookup"><span data-stu-id="d8a58-162">Network Sites Constrained by WAN Bandwidth</span></span>
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="d8a58-163">ネットワーク サイト</span><span class="sxs-lookup"><span data-stu-id="d8a58-163">Network Site</span></span></th>
    <th><span data-ttu-id="d8a58-164">ネットワーク地域</span><span class="sxs-lookup"><span data-stu-id="d8a58-164">Network Region</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="d8a58-165">アルバカーキ</span><span class="sxs-lookup"><span data-stu-id="d8a58-165">Albuquerque</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-166">北アメリカ</span><span class="sxs-lookup"><span data-stu-id="d8a58-166">North America</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="d8a58-167">リノ</span><span class="sxs-lookup"><span data-stu-id="d8a58-167">Reno</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-168">北アメリカ</span><span class="sxs-lookup"><span data-stu-id="d8a58-168">North America</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="d8a58-169">支店</span><span class="sxs-lookup"><span data-stu-id="d8a58-169">Portland</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-170">北アメリカ</span><span class="sxs-lookup"><span data-stu-id="d8a58-170">North America</span></span></p></td>
    </tr>
    </tbody>
    </table>
    
    <span data-ttu-id="d8a58-171">**帯域幅の制限がない 3 つのネットワーク サイト (シカゴ、ニューヨーク、デトロイト) および WAN 帯域幅の制限がある 3 つのネットワーク サイト (ポートランド、リノ、アルバカーキ) を持つ CAC ネットワーク地域、北アメリカ**</span><span class="sxs-lookup"><span data-stu-id="d8a58-171">**CAC network region North America with three network sites that are unconstrained by bandwidth (Chicago, New York, and Detroit) and three network sites that are constrained by WAN bandwidth (Portland, Reno, and Albuquerque)**</span></span>
    
    <span data-ttu-id="d8a58-172">![WAN 帯域幅による制限があるネットワークサイトの例](images/Gg425827.d9d1f231-db4d-4dd7-8fbc-eb0b6d1e705d(OCS.15).jpg "WAN 帯域幅による制限があるネットワークサイトの例")</span><span class="sxs-lookup"><span data-stu-id="d8a58-172">![Example network sites constrained by WAN bandwidth](images/Gg425827.d9d1f231-db4d-4dd7-8fbc-eb0b6d1e705d(OCS.15).jpg "Example network sites constrained by WAN bandwidth")</span></span>  

5.  <span data-ttu-id="d8a58-173">帯域幅の制限がある WAN リンクに対して、次の項目を決定します。</span><span class="sxs-lookup"><span data-stu-id="d8a58-173">For each bandwidth-constrained WAN link, determine the following:</span></span>
    
      - <span data-ttu-id="d8a58-174">すべての同時音声セッションに対して設定したい全体的な帯域幅制限。</span><span class="sxs-lookup"><span data-stu-id="d8a58-174">Overall bandwidth limit that you want to set for all concurrent audio sessions.</span></span> <span data-ttu-id="d8a58-175">新しいオーディオセッションでこの制限を超過すると、Lync Server ではセッションの開始が許可されなくなります。</span><span class="sxs-lookup"><span data-stu-id="d8a58-175">If a new audio session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="d8a58-p113">それぞれ個別の音声セッションに対して設定したい帯域幅制限。既定の CAC 帯域幅制限は 175 kbps ですが、管理者はこれを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="d8a58-p113">Bandwidth limit that you want to set for each individual audio session. The default CAC bandwidth limit is 175 kbps, but it can be modified by the administrator.</span></span>
    
      - <span data-ttu-id="d8a58-178">すべての同時ビデオ セッションに対して設定したい全体的な帯域幅制限。</span><span class="sxs-lookup"><span data-stu-id="d8a58-178">Overall bandwidth limit that you want to set for all concurrent video sessions.</span></span> <span data-ttu-id="d8a58-179">新しいビデオセッションでこの制限を超過した場合、Lync Server ではセッションの開始が許可されません。</span><span class="sxs-lookup"><span data-stu-id="d8a58-179">If a new video session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="d8a58-p115">それぞれ個別のビデオ セッションに対して設定したい帯域幅制限。 既定の CAC 帯域幅制限は 700 kbps ですが、管理者はこれを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="d8a58-p115">Bandwidth limit that you want to set for each individual video session. The default CAC bandwidth limit is 700 kbps, but it can be modified by the administrator.</span></span>
    
    ### <a name="network-sites-with-wan-bandwidth-constraint-information-bandwidth-in-kbps"></a><span data-ttu-id="d8a58-182">WAN 帯域幅制限情報 (帯域幅は kbps で表示) とネットワーク サイト</span><span class="sxs-lookup"><span data-stu-id="d8a58-182">Network Sites with WAN Bandwidth Constraint Information (Bandwidth in kbps)</span></span>
    
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
    <th><span data-ttu-id="d8a58-183">ネットワーク サイト</span><span class="sxs-lookup"><span data-stu-id="d8a58-183">Network Site</span></span></th>
    <th><span data-ttu-id="d8a58-184">ネットワーク地域</span><span class="sxs-lookup"><span data-stu-id="d8a58-184">Network Region</span></span></th>
    <th><span data-ttu-id="d8a58-185">BW 制限</span><span class="sxs-lookup"><span data-stu-id="d8a58-185">BW Limit</span></span></th>
    <th><span data-ttu-id="d8a58-186">音声制限</span><span class="sxs-lookup"><span data-stu-id="d8a58-186">Audio Limit</span></span></th>
    <th><span data-ttu-id="d8a58-187">音声セッション制限</span><span class="sxs-lookup"><span data-stu-id="d8a58-187">Audio Session Limit</span></span></th>
    <th><span data-ttu-id="d8a58-188">ビデオ制限</span><span class="sxs-lookup"><span data-stu-id="d8a58-188">Video Limit</span></span></th>
    <th><span data-ttu-id="d8a58-189">ビデオ セッション制限</span><span class="sxs-lookup"><span data-stu-id="d8a58-189">Video Session Limit</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="d8a58-190">アルバカーキ</span><span class="sxs-lookup"><span data-stu-id="d8a58-190">Albuquerque</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-191">北アメリカ</span><span class="sxs-lookup"><span data-stu-id="d8a58-191">North America</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-192">5,000</span><span class="sxs-lookup"><span data-stu-id="d8a58-192">5,000</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-193">2,000</span><span class="sxs-lookup"><span data-stu-id="d8a58-193">2,000</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-194">175</span><span class="sxs-lookup"><span data-stu-id="d8a58-194">175</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-195">1400</span><span class="sxs-lookup"><span data-stu-id="d8a58-195">1,400</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-196">700</span><span class="sxs-lookup"><span data-stu-id="d8a58-196">700</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="d8a58-197">リノ</span><span class="sxs-lookup"><span data-stu-id="d8a58-197">Reno</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-198">北アメリカ</span><span class="sxs-lookup"><span data-stu-id="d8a58-198">North America</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-199">10,000</span><span class="sxs-lookup"><span data-stu-id="d8a58-199">10,000</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-200">4000</span><span class="sxs-lookup"><span data-stu-id="d8a58-200">4,000</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-201">175</span><span class="sxs-lookup"><span data-stu-id="d8a58-201">175</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-202">2800</span><span class="sxs-lookup"><span data-stu-id="d8a58-202">2,800</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-203">700</span><span class="sxs-lookup"><span data-stu-id="d8a58-203">700</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="d8a58-204">支店</span><span class="sxs-lookup"><span data-stu-id="d8a58-204">Portland</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-205">北アメリカ</span><span class="sxs-lookup"><span data-stu-id="d8a58-205">North America</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-206">5,000</span><span class="sxs-lookup"><span data-stu-id="d8a58-206">5,000</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-207">4000</span><span class="sxs-lookup"><span data-stu-id="d8a58-207">4,000</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-208">175</span><span class="sxs-lookup"><span data-stu-id="d8a58-208">175</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-209">2800</span><span class="sxs-lookup"><span data-stu-id="d8a58-209">2,800</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-210">700</span><span class="sxs-lookup"><span data-stu-id="d8a58-210">700</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="d8a58-211">ニューヨーク</span><span class="sxs-lookup"><span data-stu-id="d8a58-211">New York</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-212">北アメリカ</span><span class="sxs-lookup"><span data-stu-id="d8a58-212">North America</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-213">(制限なし)</span><span class="sxs-lookup"><span data-stu-id="d8a58-213">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-214">(制限なし)</span><span class="sxs-lookup"><span data-stu-id="d8a58-214">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-215">(制限なし)</span><span class="sxs-lookup"><span data-stu-id="d8a58-215">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-216">(制限なし)</span><span class="sxs-lookup"><span data-stu-id="d8a58-216">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-217">(制限なし)</span><span class="sxs-lookup"><span data-stu-id="d8a58-217">(no limit)</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="d8a58-218">Chicago</span><span class="sxs-lookup"><span data-stu-id="d8a58-218">Chicago</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-219">北アメリカ</span><span class="sxs-lookup"><span data-stu-id="d8a58-219">North America</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-220">(制限なし)</span><span class="sxs-lookup"><span data-stu-id="d8a58-220">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-221">(制限なし)</span><span class="sxs-lookup"><span data-stu-id="d8a58-221">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-222">(制限なし)</span><span class="sxs-lookup"><span data-stu-id="d8a58-222">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-223">(制限なし)</span><span class="sxs-lookup"><span data-stu-id="d8a58-223">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-224">(制限なし)</span><span class="sxs-lookup"><span data-stu-id="d8a58-224">(no limit)</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="d8a58-225">市</span><span class="sxs-lookup"><span data-stu-id="d8a58-225">Detroit</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-226">北アメリカ</span><span class="sxs-lookup"><span data-stu-id="d8a58-226">North America</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-227">(制限なし)</span><span class="sxs-lookup"><span data-stu-id="d8a58-227">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-228">(制限なし)</span><span class="sxs-lookup"><span data-stu-id="d8a58-228">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-229">(制限なし)</span><span class="sxs-lookup"><span data-stu-id="d8a58-229">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-230">(制限なし)</span><span class="sxs-lookup"><span data-stu-id="d8a58-230">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-231">(制限なし)</span><span class="sxs-lookup"><span data-stu-id="d8a58-231">(no limit)</span></span></p></td>
    </tr>
    </tbody>
    </table>


6.  <span data-ttu-id="d8a58-232">ネットワークのすべてのサブネットに対し、関連付けられるネットワーク サイトを指定します。</span><span class="sxs-lookup"><span data-stu-id="d8a58-232">For every subnet in your network, specify its associated network site.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="d8a58-p116">すべてのサブネットは、たとえネットワーク サイトに帯域幅の制限がない場合でも、ネットワーク サイトに関連付けられる必要があります。 これは、通話受付管理はサブネット情報を使用してエンドポイントがどのネットワーク サイトに配置されているかを判断するためです。 セッションにおける両者の場所が決定した時、通話受付管理は通話を確立するのに十分な帯域幅があるかどうかを判断します。 帯域幅の制限がないリンクを介してセッションが確立した時、通知が生成されます。</span><span class="sxs-lookup"><span data-stu-id="d8a58-p116">Every subnet in your network must be associated with a network site, even if the network site is not bandwidth constrained. This is because call admission control uses subnet information to determine at which network site an endpoint is located. When the locations of both parties in the session are determined, call admission control can determine if there is sufficient bandwidth to establish a call. When a session is established over a link that has no bandwidth limits, an alert is generated.</span></span><BR><span data-ttu-id="d8a58-237">音声ビデオエッジサーバーを展開する場合は、エッジサーバーが展開されているネットワークサイトに各エッジサーバーのパブリック IP アドレスが関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8a58-237">If you deploy Audio/Video Edge Servers, the public IP addresses of each Edge Server must be associated with the network site where the Edge Server is deployed.</span></span> <span data-ttu-id="d8a58-238">音声ビデオエッジサーバーの各パブリック IP アドレスは、サブネットマスク32のサブネットとして、ネットワーク構成設定に追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8a58-238">Each public IP address of the A/V Edge Server must be added to your network configuration settings as a subnet with a subnet mask of 32.</span></span> <span data-ttu-id="d8a58-239">たとえば、をシカゴに展開する場合は、これらのサーバーの外部 IP アドレスごとに、サブネットマスク32を持つサブネットを作成し、ネットワークサイトシカゴとそのサブネットを関連付けます。</span><span class="sxs-lookup"><span data-stu-id="d8a58-239">For example, if you deploy A/V Edge Servers in Chicago, then for each external IP address of those servers create a subnet with a subnet mask of 32 and associate network site Chicago with those subnets.</span></span> <span data-ttu-id="d8a58-240">パブリック IP アドレスの詳細については、「計画」のドキュメントの「 <A href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">Lync Server 2013 の外部の音声ビデオファイアウォールおよびポート要件を決定</A> する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8a58-240">For details about public IP addresses, see <A href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">Determine external A/V firewall and port requirements for Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="d8a58-p118">主要状態インジケーター (KHI) 通知が発行され、ネットワークに存在している IP アドレスの一覧を指定します。ここで指定される一覧は、サブネットと関連付けられていないか、IP アドレスを含むサブネットがネットワーク サイトと関連付けられていません。 この通知は 8 時間に 1 回しか発行されません。 関連する通知の情報および例は以下の通りです。</span><span class="sxs-lookup"><span data-stu-id="d8a58-p118">A Key Health Indicator (KHI) alert is raised, specifying a list of IP addresses that are present in your network but are either not associated with a subnet, or the subnet that includes the IP addresses is not associated with a network site. This alert will not be raised more than once within an 8 hour period. The relevant alert information and an example are as follows:</span></span><BR><span data-ttu-id="d8a58-244"><STRONG>ソース:</STRONG> CS 帯域幅ポリシーサービス (コア)</span><span class="sxs-lookup"><span data-stu-id="d8a58-244"><STRONG>Source:</STRONG> CS Bandwidth Policy Service (Core)</span></span><BR><span data-ttu-id="d8a58-245"><STRONG>イベント番号:</STRONG> 36034</span><span class="sxs-lookup"><span data-stu-id="d8a58-245"><STRONG>Event number:</STRONG> 36034</span></span><BR><span data-ttu-id="d8a58-246"><STRONG>レベル:</STRONG> 2</span><span class="sxs-lookup"><span data-stu-id="d8a58-246"><STRONG>Level:</STRONG> 2</span></span><BR><span data-ttu-id="d8a58-247"><STRONG>説明:</STRONG> 次の IP アドレスのサブネット: &lt; Ip アドレスの一覧 &gt; が構成されていないか、またはサブネットがネットワークサイトに関連付けられていません。</span><span class="sxs-lookup"><span data-stu-id="d8a58-247"><STRONG>Description:</STRONG> The subnets for the following IP Addresses: &lt;List of IP Addresses&gt; are either not configured or the subnets are not associated to a network site.</span></span><BR><span data-ttu-id="d8a58-248"><STRONG>原因:</STRONG> 対応する IP アドレスのサブネットがネットワーク構成設定にないか、またはサブネットがネットワークサイトに関連付けられていません。</span><span class="sxs-lookup"><span data-stu-id="d8a58-248"><STRONG>Cause:</STRONG> The subnets for the corresponding IP addresses are missing from the network configuration settings or the subnets are not associated to a network site.</span></span><BR><span data-ttu-id="d8a58-249"><STRONG>解決策:</STRONG> 前述の IP アドレスリストに対応するサブネットをネットワーク構成設定に追加し、すべてのサブネットをネットワークサイトに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="d8a58-249"><STRONG>Resolution:</STRONG> Add subnets corresponding to the preceding list of IP addresses into the network configuration settings and associate every subnet to a network site.</span></span><BR><span data-ttu-id="d8a58-p119">たとえば、通知に表示された IP アドレス リストが 10.121.248.226 および 10.121.249.20 であった場合、これらの IP アドレスがサブネットに関連付けられていないか、または関連付けられているサブネットがネットワーク サイトに属していないかのどちらかになります。10.121.248.0/24 および 10.121.249.0/24 がこれらのアドレスに対応するサブネットである場合、次の手順でこの問題を解決することができます。</span><span class="sxs-lookup"><span data-stu-id="d8a58-p119">For example, if the IP address list in the alert specifies 10.121.248.226 and 10.121.249.20, either these IP addresses are not associated with a subnet, or the subnet that they are associated with does not belong to a network site. If 10.121.248.0/24 and 10.121.249.0/24 are the corresponding subnets for these addresses, you can resolve this issue as follows:</span></span> 
    > <OL>
    > <LI>
    > <P><span data-ttu-id="d8a58-252">IP アドレス 10.121.248.226 が 10.121.248.0/24 サブネットに関連付けられていること、および IP アドレス 10.121.249.20 が 10.121.249.0/24 サブネットに関連付けられていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d8a58-252">Be sure that IP address 10.121.248.226 is associated with the 10.121.248.0/24 subnet and IP address 10.121.249.20 is associated with the 10.121.249.0/24 subnet.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="d8a58-253">10.121.248.0/24 および 10.121.249.0/24 サブネットがそれぞれネットワーク サイトに関連付けられていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d8a58-253">Be sure that the 10.121.248.0/24 and 10.121.249.0/24 subnets are each associated with a network site.</span></span></P></LI></OL>

    
    </div>
    
    ### <a name="network-sites-and-associated-subnets-bandwidth-in-kbps"></a><span data-ttu-id="d8a58-254">ネットワーク サイトと関連付けられたサブネット (帯域幅は kbps で表示)</span><span class="sxs-lookup"><span data-stu-id="d8a58-254">Network Sites and Associated Subnets (Bandwidth in kbps)</span></span>
    
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
    <th><span data-ttu-id="d8a58-255">ネットワーク サイト</span><span class="sxs-lookup"><span data-stu-id="d8a58-255">Network Site</span></span></th>
    <th><span data-ttu-id="d8a58-256">ネットワーク地域</span><span class="sxs-lookup"><span data-stu-id="d8a58-256">Network Region</span></span></th>
    <th><span data-ttu-id="d8a58-257">BW 制限</span><span class="sxs-lookup"><span data-stu-id="d8a58-257">BW Limit</span></span></th>
    <th><span data-ttu-id="d8a58-258">音声制限</span><span class="sxs-lookup"><span data-stu-id="d8a58-258">Audio Limit</span></span></th>
    <th><span data-ttu-id="d8a58-259">音声セッション制限</span><span class="sxs-lookup"><span data-stu-id="d8a58-259">Audio Session Limit</span></span></th>
    <th><span data-ttu-id="d8a58-260">ビデオ制限</span><span class="sxs-lookup"><span data-stu-id="d8a58-260">Video Limit</span></span></th>
    <th><span data-ttu-id="d8a58-261">ビデオ セッション制限</span><span class="sxs-lookup"><span data-stu-id="d8a58-261">Video Session Limit</span></span></th>
    <th><span data-ttu-id="d8a58-262">サブネット</span><span class="sxs-lookup"><span data-stu-id="d8a58-262">Subnets</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="d8a58-263">アルバカーキ</span><span class="sxs-lookup"><span data-stu-id="d8a58-263">Albuquerque</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-264">北アメリカ</span><span class="sxs-lookup"><span data-stu-id="d8a58-264">North America</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-265">5,000</span><span class="sxs-lookup"><span data-stu-id="d8a58-265">5,000</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-266">2,000</span><span class="sxs-lookup"><span data-stu-id="d8a58-266">2,000</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-267">175</span><span class="sxs-lookup"><span data-stu-id="d8a58-267">175</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-268">1400</span><span class="sxs-lookup"><span data-stu-id="d8a58-268">1,400</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-269">700</span><span class="sxs-lookup"><span data-stu-id="d8a58-269">700</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-270">172.29.79.0/23、157.57.215.0/25、172.29.90.0/23、172.29.80.0/24</span><span class="sxs-lookup"><span data-stu-id="d8a58-270">172.29.79.0/23, 157.57.215.0/25, 172.29.90.0/23, 172.29.80.0/24</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="d8a58-271">リノ</span><span class="sxs-lookup"><span data-stu-id="d8a58-271">Reno</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-272">北アメリカ</span><span class="sxs-lookup"><span data-stu-id="d8a58-272">North America</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-273">10,000</span><span class="sxs-lookup"><span data-stu-id="d8a58-273">10,000</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-274">4000</span><span class="sxs-lookup"><span data-stu-id="d8a58-274">4,000</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-275">175</span><span class="sxs-lookup"><span data-stu-id="d8a58-275">175</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-276">2800</span><span class="sxs-lookup"><span data-stu-id="d8a58-276">2,800</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-277">700</span><span class="sxs-lookup"><span data-stu-id="d8a58-277">700</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-278">157.57.210.0/23、172.28.151.128/25</span><span class="sxs-lookup"><span data-stu-id="d8a58-278">157.57.210.0/23, 172.28.151.128/25</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="d8a58-279">支店</span><span class="sxs-lookup"><span data-stu-id="d8a58-279">Portland</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-280">北アメリカ</span><span class="sxs-lookup"><span data-stu-id="d8a58-280">North America</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-281">5,000</span><span class="sxs-lookup"><span data-stu-id="d8a58-281">5,000</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-282">4000</span><span class="sxs-lookup"><span data-stu-id="d8a58-282">4,000</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-283">175</span><span class="sxs-lookup"><span data-stu-id="d8a58-283">175</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-284">2800</span><span class="sxs-lookup"><span data-stu-id="d8a58-284">2,800</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-285">700</span><span class="sxs-lookup"><span data-stu-id="d8a58-285">700</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-286">172.29.77.0/24 10.71.108.0/24、157.57.208.0/23</span><span class="sxs-lookup"><span data-stu-id="d8a58-286">172.29.77.0/24 10.71.108.0/24, 157.57.208.0/23</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="d8a58-287">ニューヨーク</span><span class="sxs-lookup"><span data-stu-id="d8a58-287">New York</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-288">北アメリカ</span><span class="sxs-lookup"><span data-stu-id="d8a58-288">North America</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-289">(制限なし)</span><span class="sxs-lookup"><span data-stu-id="d8a58-289">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-290">(制限なし)</span><span class="sxs-lookup"><span data-stu-id="d8a58-290">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-291">(制限なし)</span><span class="sxs-lookup"><span data-stu-id="d8a58-291">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-292">(制限なし)</span><span class="sxs-lookup"><span data-stu-id="d8a58-292">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-293">(制限なし)</span><span class="sxs-lookup"><span data-stu-id="d8a58-293">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-294">172.29.80.0/23、157.57.216.0/25、172.29.91.0/23、172.29.81.0/24</span><span class="sxs-lookup"><span data-stu-id="d8a58-294">172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="d8a58-295">Chicago</span><span class="sxs-lookup"><span data-stu-id="d8a58-295">Chicago</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-296">北アメリカ</span><span class="sxs-lookup"><span data-stu-id="d8a58-296">North America</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-297">(制限なし)</span><span class="sxs-lookup"><span data-stu-id="d8a58-297">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-298">(制限なし)</span><span class="sxs-lookup"><span data-stu-id="d8a58-298">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-299">(制限なし)</span><span class="sxs-lookup"><span data-stu-id="d8a58-299">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-300">(制限なし)</span><span class="sxs-lookup"><span data-stu-id="d8a58-300">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-301">(制限なし)</span><span class="sxs-lookup"><span data-stu-id="d8a58-301">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-302">157.57.211.0/23、172.28.152.128/25</span><span class="sxs-lookup"><span data-stu-id="d8a58-302">157.57.211.0/23, 172.28.152.128/25</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="d8a58-303">市</span><span class="sxs-lookup"><span data-stu-id="d8a58-303">Detroit</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-304">北アメリカ</span><span class="sxs-lookup"><span data-stu-id="d8a58-304">North America</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-305">(制限なし)</span><span class="sxs-lookup"><span data-stu-id="d8a58-305">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-306">(制限なし)</span><span class="sxs-lookup"><span data-stu-id="d8a58-306">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-307">(制限なし)</span><span class="sxs-lookup"><span data-stu-id="d8a58-307">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-308">(制限なし)</span><span class="sxs-lookup"><span data-stu-id="d8a58-308">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-309">(制限なし)</span><span class="sxs-lookup"><span data-stu-id="d8a58-309">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-310">172.29.78.0/24 10.71.109.0/24、157.57.209.0/23</span><span class="sxs-lookup"><span data-stu-id="d8a58-310">172.29.78.0/24 10.71.109.0/24, 157.57.209.0/23</span></span></p></td>
    </tr>
    </tbody>
    </table>


7.  <span data-ttu-id="d8a58-311">Lync Server の通話受付管理では、ネットワーク地域間の接続は *地域リンク*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="d8a58-311">In Lync Server call admission control, the connections between network regions are called *region links*.</span></span> <span data-ttu-id="d8a58-312">各地域リンクに対し、ネットワーク サイトでしたように、次の項目を決定します。</span><span class="sxs-lookup"><span data-stu-id="d8a58-312">For each region link, determine the following, just as you did for the network sites:</span></span>
    
      - <span data-ttu-id="d8a58-313">すべての同時音声セッションに対して設定したい全体的な帯域幅制限。</span><span class="sxs-lookup"><span data-stu-id="d8a58-313">Overall bandwidth limit that you want to set for all concurrent audio sessions.</span></span> <span data-ttu-id="d8a58-314">新しいオーディオセッションでこの制限を超過すると、Lync Server ではセッションの開始が許可されなくなります。</span><span class="sxs-lookup"><span data-stu-id="d8a58-314">If a new audio session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="d8a58-p122">それぞれ個別の音声セッションに対して設定したい帯域幅制限。既定の CAC 帯域幅制限は 175 kbps ですが、管理者はこれを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="d8a58-p122">Bandwidth limit that you want to set for each individual audio session. The default CAC bandwidth limit is 175 kbps, but it can be modified by the administrator.</span></span>
    
      - <span data-ttu-id="d8a58-317">すべての同時ビデオ セッションに対して設定したい全体的な帯域幅制限。</span><span class="sxs-lookup"><span data-stu-id="d8a58-317">Overall bandwidth limit that you want to set for all concurrent video sessions.</span></span> <span data-ttu-id="d8a58-318">新しいビデオセッションでこの制限を超過した場合、Lync Server ではセッションの開始が許可されません。</span><span class="sxs-lookup"><span data-stu-id="d8a58-318">If a new video session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="d8a58-p124">それぞれ個別のビデオ セッションに対して設定したい帯域幅制限。 既定の CAC 帯域幅制限は 700 kbps ですが、管理者はこれを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="d8a58-p124">Bandwidth limit that you want to set for each individual video session. The default CAC bandwidth limit is 700 kbps, but it can be modified by the administrator.</span></span>
    
    <span data-ttu-id="d8a58-321">**関連付けられた帯域幅制限とネットワーク地域リンク**</span><span class="sxs-lookup"><span data-stu-id="d8a58-321">**Network Region links with associated bandwidth limits**</span></span>
    
    <span data-ttu-id="d8a58-322">![3つの地域間の制限の例](images/Gg425827.25259afa-ee7c-4d26-bc41-92ba9cb56dec(OCS.15).jpg "3つの地域間の制限の例")</span><span class="sxs-lookup"><span data-stu-id="d8a58-322">![Example of Limitations between 3 Regions](images/Gg425827.25259afa-ee7c-4d26-bc41-92ba9cb56dec(OCS.15).jpg "Example of Limitations between 3 Regions")</span></span>  
    
    ### <a name="region-link-bandwidth-information-bandwidth-in-kbps"></a><span data-ttu-id="d8a58-323">地域リンク帯域幅情報 (帯域幅は kbps で表示)</span><span class="sxs-lookup"><span data-stu-id="d8a58-323">Region Link Bandwidth Information (Bandwidth in kbps)</span></span>
    
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
    <th><span data-ttu-id="d8a58-324">地域リンク名</span><span class="sxs-lookup"><span data-stu-id="d8a58-324">Region Link Name</span></span></th>
    <th><span data-ttu-id="d8a58-325">第 1 の地域</span><span class="sxs-lookup"><span data-stu-id="d8a58-325">First Region</span></span></th>
    <th><span data-ttu-id="d8a58-326">第 2 の地域</span><span class="sxs-lookup"><span data-stu-id="d8a58-326">Second Region</span></span></th>
    <th><span data-ttu-id="d8a58-327">BW 制限</span><span class="sxs-lookup"><span data-stu-id="d8a58-327">BW Limit</span></span></th>
    <th><span data-ttu-id="d8a58-328">音声制限</span><span class="sxs-lookup"><span data-stu-id="d8a58-328">Audio Limit</span></span></th>
    <th><span data-ttu-id="d8a58-329">音声セッション制限</span><span class="sxs-lookup"><span data-stu-id="d8a58-329">Audio Session Limit</span></span></th>
    <th><span data-ttu-id="d8a58-330">ビデオ制限</span><span class="sxs-lookup"><span data-stu-id="d8a58-330">Video Limit</span></span></th>
    <th><span data-ttu-id="d8a58-331">ビデオ セッション制限</span><span class="sxs-lookup"><span data-stu-id="d8a58-331">Video Session Limit</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="d8a58-332">NA-EMEA-リンク</span><span class="sxs-lookup"><span data-stu-id="d8a58-332">NA-EMEA-LINK</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-333">北アメリカ</span><span class="sxs-lookup"><span data-stu-id="d8a58-333">North America</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-334">EMEA</span><span class="sxs-lookup"><span data-stu-id="d8a58-334">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-335">50,000</span><span class="sxs-lookup"><span data-stu-id="d8a58-335">50,000</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-336">20,000</span><span class="sxs-lookup"><span data-stu-id="d8a58-336">20,000</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-337">175</span><span class="sxs-lookup"><span data-stu-id="d8a58-337">175</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-338">14000</span><span class="sxs-lookup"><span data-stu-id="d8a58-338">14,000</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-339">700</span><span class="sxs-lookup"><span data-stu-id="d8a58-339">700</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="d8a58-340">EMEA-APAC リンク</span><span class="sxs-lookup"><span data-stu-id="d8a58-340">EMEA-APAC-LINK</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-341">EMEA</span><span class="sxs-lookup"><span data-stu-id="d8a58-341">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-342">APAC</span><span class="sxs-lookup"><span data-stu-id="d8a58-342">APAC</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-343">25,000</span><span class="sxs-lookup"><span data-stu-id="d8a58-343">25,000</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-344">10,000</span><span class="sxs-lookup"><span data-stu-id="d8a58-344">10,000</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-345">175</span><span class="sxs-lookup"><span data-stu-id="d8a58-345">175</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-346">7000</span><span class="sxs-lookup"><span data-stu-id="d8a58-346">7,000</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-347">700</span><span class="sxs-lookup"><span data-stu-id="d8a58-347">700</span></span></p></td>
    </tr>
    </tbody>
    </table>


8.  <span data-ttu-id="d8a58-348">ネットワーク地域のすべてのペア間のルートを定義します。</span><span class="sxs-lookup"><span data-stu-id="d8a58-348">Define a route between every pair of network regions.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="d8a58-349">北アメリカと APAC の間のルートには、両者を直接接続する地域リンクがないため、2 つのリンクが必要になります。</span><span class="sxs-lookup"><span data-stu-id="d8a58-349">Two links are required for the route between the North America and APAC regions because there is no region link that directly connects them.</span></span>

    
    </div>
    
    ### <a name="region-routes"></a><span data-ttu-id="d8a58-350">地域ルート</span><span class="sxs-lookup"><span data-stu-id="d8a58-350">Region Routes</span></span>
    
    <table>
    <colgroup>
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="d8a58-351">地域ルート名</span><span class="sxs-lookup"><span data-stu-id="d8a58-351">Region Route Name</span></span></th>
    <th><span data-ttu-id="d8a58-352">第 1 の地域</span><span class="sxs-lookup"><span data-stu-id="d8a58-352">First Region</span></span></th>
    <th><span data-ttu-id="d8a58-353">第 2 の地域</span><span class="sxs-lookup"><span data-stu-id="d8a58-353">Second Region</span></span></th>
    <th><span data-ttu-id="d8a58-354">地域リンク</span><span class="sxs-lookup"><span data-stu-id="d8a58-354">Region Links</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="d8a58-355">NA-EMEA-ルート</span><span class="sxs-lookup"><span data-stu-id="d8a58-355">NA-EMEA-ROUTE</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-356">北アメリカ</span><span class="sxs-lookup"><span data-stu-id="d8a58-356">North America</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-357">EMEA</span><span class="sxs-lookup"><span data-stu-id="d8a58-357">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-358">NA-EMEA-リンク</span><span class="sxs-lookup"><span data-stu-id="d8a58-358">NA-EMEA-LINK</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="d8a58-359">EMEA-APAC-ルート</span><span class="sxs-lookup"><span data-stu-id="d8a58-359">EMEA-APAC-ROUTE</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-360">EMEA</span><span class="sxs-lookup"><span data-stu-id="d8a58-360">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-361">APAC</span><span class="sxs-lookup"><span data-stu-id="d8a58-361">APAC</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-362">EMEA-APAC リンク</span><span class="sxs-lookup"><span data-stu-id="d8a58-362">EMEA-APAC-LINK</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="d8a58-363">NA-APAC-ルート</span><span class="sxs-lookup"><span data-stu-id="d8a58-363">NA-APAC-ROUTE</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-364">北アメリカ</span><span class="sxs-lookup"><span data-stu-id="d8a58-364">North America</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-365">APAC</span><span class="sxs-lookup"><span data-stu-id="d8a58-365">APAC</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-366">NA-EMEA-LINK, EMEA-APAC-LINK</span><span class="sxs-lookup"><span data-stu-id="d8a58-366">NA-EMEA-LINK, EMEA-APAC-LINK</span></span></p></td>
    </tr>
    </tbody>
    </table>


9.  <span data-ttu-id="d8a58-367">単一のリンク (*サイト間*リンクと呼ばれます) で直接接続されているネットワーク サイトのペアに対して、次の項目を決定します。</span><span class="sxs-lookup"><span data-stu-id="d8a58-367">For every pair of network sites that are directly connected by a single link (called an *inter-site* link), determine the following:</span></span>
    
      - <span data-ttu-id="d8a58-368">すべての同時音声セッションに対して設定したい全体的な帯域幅制限。</span><span class="sxs-lookup"><span data-stu-id="d8a58-368">Overall bandwidth limit that you want to set for all concurrent audio sessions.</span></span> <span data-ttu-id="d8a58-369">新しいオーディオセッションでこの制限を超過すると、Lync Server ではセッションの開始が許可されなくなります。</span><span class="sxs-lookup"><span data-stu-id="d8a58-369">If a new audio session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="d8a58-p126">それぞれ個別の音声セッションに対して設定したい帯域幅制限。既定の CAC 帯域幅制限は 175 kbps ですが、管理者はこれを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="d8a58-p126">Bandwidth limit that you want to set for each individual audio session. The default CAC bandwidth limit is 175 kbps, but it can be modified by the administrator.</span></span>
    
      - <span data-ttu-id="d8a58-372">すべての同時ビデオ セッションに対して設定したい全体的な帯域幅制限。</span><span class="sxs-lookup"><span data-stu-id="d8a58-372">Overall bandwidth limit that you want to set for all concurrent video sessions.</span></span> <span data-ttu-id="d8a58-373">新しいビデオセッションでこの制限を超過した場合、Lync Server ではセッションの開始が許可されません。</span><span class="sxs-lookup"><span data-stu-id="d8a58-373">If a new video session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="d8a58-p128">それぞれ個別のビデオ セッションに対して設定したい帯域幅制限。 既定の CAC 帯域幅制限は 700 kbps ですが、管理者はこれを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="d8a58-p128">Bandwidth limit that you want to set for each individual video session. The default CAC bandwidth limit is 700 kbps, but it can be modified by the administrator.</span></span>
    
    <span data-ttu-id="d8a58-376">**リノとアルバカーキ間のサイト間リンクに対する帯域幅処理能力および帯域幅制限を示すCAC ネットワーク地域、北アメリカ**</span><span class="sxs-lookup"><span data-stu-id="d8a58-376">**CAC network region North America showing the bandwidth capacities and bandwidth limits for the inter-site link between Reno and Albuquerque**</span></span>
    
    <span data-ttu-id="d8a58-377">![WAN 帯域幅による制限があるネットワークサイトの例](images/Gg425827.063e5e1d-b6c8-4e8c-98db-c227c78f671d(OCS.15).jpg "WAN 帯域幅による制限があるネットワークサイトの例")</span><span class="sxs-lookup"><span data-stu-id="d8a58-377">![Network Sites Constrained by WAN Bandwidth example](images/Gg425827.063e5e1d-b6c8-4e8c-98db-c227c78f671d(OCS.15).jpg "Network Sites Constrained by WAN Bandwidth example")</span></span>  
    
    ### <a name="bandwidth-information-for-an-inter-site-link-between-two-network-sites-bandwidth-in-kbps"></a><span data-ttu-id="d8a58-378">2 つのネットワーク サイト間のサイト間リンクの帯域幅情報 (帯域幅は kbps で表示)</span><span class="sxs-lookup"><span data-stu-id="d8a58-378">Bandwidth Information for an Inter-Site Link between Two Network Sites (Bandwidth in kbps)</span></span>
    
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
    <th><span data-ttu-id="d8a58-379">サイト間リンク名</span><span class="sxs-lookup"><span data-stu-id="d8a58-379">Inter-Site Link Name</span></span></th>
    <th><span data-ttu-id="d8a58-380">第 1 のサイト</span><span class="sxs-lookup"><span data-stu-id="d8a58-380">First Site</span></span></th>
    <th><span data-ttu-id="d8a58-381">第 2 のサイト</span><span class="sxs-lookup"><span data-stu-id="d8a58-381">Second Site</span></span></th>
    <th><span data-ttu-id="d8a58-382">BW 制限</span><span class="sxs-lookup"><span data-stu-id="d8a58-382">BW Limit</span></span></th>
    <th><span data-ttu-id="d8a58-383">音声制限</span><span class="sxs-lookup"><span data-stu-id="d8a58-383">Audio Limit</span></span></th>
    <th><span data-ttu-id="d8a58-384">音声セッション制限</span><span class="sxs-lookup"><span data-stu-id="d8a58-384">Audio Session Limit</span></span></th>
    <th><span data-ttu-id="d8a58-385">ビデオ制限</span><span class="sxs-lookup"><span data-stu-id="d8a58-385">Video Limit</span></span></th>
    <th><span data-ttu-id="d8a58-386">ビデオ セッション制限</span><span class="sxs-lookup"><span data-stu-id="d8a58-386">Video Session Limit</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="d8a58-387">リノ-Albu-リンク</span><span class="sxs-lookup"><span data-stu-id="d8a58-387">Reno-Albu-Intersite-Link</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-388">リノ</span><span class="sxs-lookup"><span data-stu-id="d8a58-388">Reno</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-389">アルバカーキ</span><span class="sxs-lookup"><span data-stu-id="d8a58-389">Albuquerque</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-390">20,000</span><span class="sxs-lookup"><span data-stu-id="d8a58-390">20,000</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-391">12000</span><span class="sxs-lookup"><span data-stu-id="d8a58-391">12,000</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-392">175</span><span class="sxs-lookup"><span data-stu-id="d8a58-392">175</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-393">5,000</span><span class="sxs-lookup"><span data-stu-id="d8a58-393">5,000</span></span></p></td>
    <td><p><span data-ttu-id="d8a58-394">700</span><span class="sxs-lookup"><span data-stu-id="d8a58-394">700</span></span></p></td>
    </tr>
    </tbody>
    </table>


<div>

## <a name="next-steps"></a><span data-ttu-id="d8a58-395">次のステップ</span><span class="sxs-lookup"><span data-stu-id="d8a58-395">Next Steps</span></span>

<span data-ttu-id="d8a58-396">必要な情報を収集した後は、Lync Server 管理シェルまたは Lync Server コントロールパネルを使用して CAC 展開を実行できます。</span><span class="sxs-lookup"><span data-stu-id="d8a58-396">After you have gathered the required information, you can perform CAC deployment either by using the Lync Server Management Shell or Lync Server Control Panel.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="d8a58-397">Lync Server コントロールパネルを使用してほとんどのネットワーク構成タスクを実行できますが、サブネットとサイト間リンクを作成するには、Lync Server 管理シェルを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8a58-397">Although you can perform most network configuration tasks by using Lync Server Control Panel, to create subnets and intersite links, you must use Lync Server Management Shell.</span></span> <span data-ttu-id="d8a58-398">詳細については、「Lync Server Management Shell」のドキュメントを参照してください。 <STRONG>このコマンドレット</STRONG> と <STRONG>get-csnetworkintersitepolicy</STRONG> コマンドレットを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8a58-398">For details, see the Lync Server Management Shell documentation for the <STRONG>New-CsNetworkSubnet</STRONG> cmdlet and the <STRONG>New-CsNetworkIntersitePolicy</STRONG> cmdlet.</span></span>



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

