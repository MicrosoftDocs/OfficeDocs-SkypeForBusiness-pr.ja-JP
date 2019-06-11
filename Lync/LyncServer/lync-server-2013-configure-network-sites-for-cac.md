---
title: 'Lync Server 2013: CAC 用のネットワークサイトを構成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure network sites for CAC
ms:assetid: afcea38f-5789-45ec-97af-c6e38364950c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412840(v=OCS.15)
ms:contentKeyID: 48185144
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 528ed67243fb0ab0451abf504a458afc420d94ea
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840341"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-network-sites-for-cac-in-lync-server-2013"></a><span data-ttu-id="b6e50-102">Lync Server 2013 での CAC 用のネットワークサイトの構成</span><span class="sxs-lookup"><span data-stu-id="b6e50-102">Configure network sites for CAC in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b6e50-103">_**最終更新日:** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="b6e50-103">_**Topic Last Modified:** 2012-09-05_</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="b6e50-104">E9-1 または media バイパス用のネットワークサイトを既に作成している場合は、 <STRONG>Set-CsNetworkSite</STRONG>コマンドレットを使用して、既存のネットワークサイトを変更して帯域幅ポリシープロファイルを適用することができます。</span><span class="sxs-lookup"><span data-stu-id="b6e50-104">If you have already created network sites for E9-1-1 or media bypass, you can modify the existing network sites to apply a bandwidth policy profile by using the <STRONG>Set-CsNetworkSite</STRONG> cmdlet.</span></span> <span data-ttu-id="b6e50-105">ネットワークサイトを変更する方法の例については、「 <A href="lync-server-2013-create-or-modify-a-network-site.md">Lync Server 2013 でネットワークサイトを作成または変更</A>する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6e50-105">For an example of how to modify a network site, see <A href="lync-server-2013-create-or-modify-a-network-site.md">Create or modify a network site in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="b6e50-106">[*ネットワークサイト*] は、通話受付制御 (CAC)、E9、および media バイパスの展開の各ネットワーク領域内の事業所または場所です。</span><span class="sxs-lookup"><span data-stu-id="b6e50-106">*Network sites* are the offices or locations within each network region of call admission control (CAC), E9-1-1, and media bypass deployments.</span></span> <span data-ttu-id="b6e50-107">次の手順を使用して、CAC のネットワークトポロジの例でネットワークサイトに合わせてネットワークサイトを作成します。</span><span class="sxs-lookup"><span data-stu-id="b6e50-107">Use the following procedures to create network sites that align to network sites in the example network topology for CAC.</span></span> <span data-ttu-id="b6e50-108">次の手順では、WAN の帯域幅に制約があるネットワークサイトを作成して構成する方法について説明します。そのため、リアルタイムの音声またはビデオのトラフィックフローを制限する帯域幅ポリシーが必要です。</span><span class="sxs-lookup"><span data-stu-id="b6e50-108">These procedures show how to create and configure network sites that are constrained by WAN bandwidth and therefore require bandwidth policies that limit real-time audio or video traffic flow.</span></span>

<span data-ttu-id="b6e50-109">CAC の展開例では、北米地域には6つのサイトがあります。</span><span class="sxs-lookup"><span data-stu-id="b6e50-109">In the example CAC deployment, the North America region has six sites.</span></span> <span data-ttu-id="b6e50-110">これら3つのサイトは、WAN の帯域幅 (Reno、ポートランド、およびアルバカーキ) によって制限されています。</span><span class="sxs-lookup"><span data-stu-id="b6e50-110">Three of these sites are constrained by WAN bandwidth: Reno, Portland, and Albuquerque.</span></span> <span data-ttu-id="b6e50-111">他の3つのサイトは、WAN の帯域幅によって制約されることは*ありません*。ニューヨーク、シカゴ、デトロイト。</span><span class="sxs-lookup"><span data-stu-id="b6e50-111">The other three sites, which are *not* constrained by WAN bandwidth: New York, Chicago, and Detroit.</span></span> <span data-ttu-id="b6e50-112">他のネットワークサイトを作成または変更する方法の例については、「 [Lync Server 2013 でネットワークサイトを作成または変更](lync-server-2013-create-or-modify-a-network-site.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6e50-112">For an example of how to create or modify those other network sites, see [Create or modify a network site in Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md).</span></span>

<span data-ttu-id="b6e50-113">ネットワークトポロジの例については、「例: 計画ドキュメントで[Lync Server 2013 の通話受付制御の要件を収集](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6e50-113">To view the example network topology, see [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) in the Planning documentation.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="b6e50-114">次の手順では、Lync Server 管理シェルを使ってネットワークサイトを作成します。</span><span class="sxs-lookup"><span data-stu-id="b6e50-114">In the following procedure, Lync Server Management Shell is used to create a network site.</span></span> <span data-ttu-id="b6e50-115">Lync Server コントロールパネルを使用してネットワークサイトを作成する方法について詳しくは、「 <A href="lync-server-2013-create-or-modify-a-network-site.md">Lync server 2013 でネットワークサイトを作成または変更</A>する」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b6e50-115">For details about using Lync Server Control Panel to create a network site, see <A href="lync-server-2013-create-or-modify-a-network-site.md">Create or modify a network site in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-create-network-sites-for-call-admission-control"></a><span data-ttu-id="b6e50-116">通話受付制御用のネットワークサイトを作成するには</span><span class="sxs-lookup"><span data-stu-id="b6e50-116">To create network sites for call admission control</span></span>

1.  <span data-ttu-id="b6e50-117">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="b6e50-117">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="b6e50-118">**新しい-CsNetworkSite**コマンドレットを実行して、ネットワークサイトを作成し、各サイトに適切な帯域幅ポリシープロファイルを適用します。</span><span class="sxs-lookup"><span data-stu-id="b6e50-118">Run the **New-CsNetworkSite** cmdlet to create network sites and apply an appropriate bandwidth policy profile to each site.</span></span> <span data-ttu-id="b6e50-119">たとえば、以下を実行します。</span><span class="sxs-lookup"><span data-stu-id="b6e50-119">For example, run:</span></span>
    
       ```
        New-CsNetworkSite -NetworkSiteID Reno -Description "NA:Branch office for sales force" -NetworkRegionID NorthAmerica -BWPolicyProfileID 10MB_Link
       ```
    
       ```
        New-CsNetworkSite -NetworkSiteID Portland -Description "NA:Branch office for marketing force" -NetworkRegionID NorthAmerica -BWPolicyProfileID 5MB_Link
       ```
    
       ```
        New-CsNetworkSite -NetworkSiteID Albuquerque -Description "NA:Branch office for SouthWest sales" -NetworkRegionID EMEA -BWPolicyProfileID 10MB_Link
       ```

3.  <span data-ttu-id="b6e50-120">トポロジ全体のネットワークサイトの作成を完了するには、EMEA と APAC 地域の帯域幅制約のあるネットワークサイトについて、手順2を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="b6e50-120">To finish creating network sites for the entire example topology, repeat step 2 for the bandwidth-constrained network sites in the EMEA and APAC regions.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

