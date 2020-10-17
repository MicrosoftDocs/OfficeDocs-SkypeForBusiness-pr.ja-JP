---
title: 'Lync Server 2013: CAC のネットワークサイトの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure network sites for CAC
ms:assetid: afcea38f-5789-45ec-97af-c6e38364950c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412840(v=OCS.15)
ms:contentKeyID: 48185144
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e24932b23b1a9168ed64279f98db125f06ad0e2e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520524"
---
# <a name="configure-network-sites-for-cac-in-lync-server-2013"></a><span data-ttu-id="06306-102">Lync Server 2013 で CAC のネットワークサイトを構成する</span><span class="sxs-lookup"><span data-stu-id="06306-102">Configure network sites for CAC in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="06306-103">_**トピックの最終更新日:** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="06306-103">_**Topic Last Modified:** 2012-09-05_</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="06306-104">E9-1-1 またはメディア バイパス用のネットワーク サイトが既に作成されている場合は、既存のネットワーク サイトを変更し、<STRONG>Set-CsNetworkSite</STRONG> コマンドレットを使用して帯域幅ポリシー プロファイルを適用できます。</span><span class="sxs-lookup"><span data-stu-id="06306-104">If you have already created network sites for E9-1-1 or media bypass, you can modify the existing network sites to apply a bandwidth policy profile by using the <STRONG>Set-CsNetworkSite</STRONG> cmdlet.</span></span> <span data-ttu-id="06306-105">ネットワークサイトの変更方法の例については、「 <A href="lync-server-2013-create-or-modify-a-network-site.md">Create or modify a network site In Lync Server 2013</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="06306-105">For an example of how to modify a network site, see <A href="lync-server-2013-create-or-modify-a-network-site.md">Create or modify a network site in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="06306-p102">*ネットワーク サイト*は、通話受付管理 (CAC)、E9-1-1、およびメディア バイパスが展開される各ネットワーク地域内のオフィスまたは拠点です。  次の手順を使用して、CAC のネットワーク トポロジの例におけるネットワーク サイトに合わせたネットワーク サイトを作成してください。 この手順は、WAN の帯域幅により制約があるために、リアルタイムの音声またはビデオのトラフィック フローを制限する帯域幅ポリシーが必要なネットワーク サイトの作成および構成方法を示します。</span><span class="sxs-lookup"><span data-stu-id="06306-p102">*Network sites* are the offices or locations within each network region of call admission control (CAC), E9-1-1, and media bypass deployments. Use the following procedures to create network sites that align to network sites in the example network topology for CAC. These procedures show how to create and configure network sites that are constrained by WAN bandwidth and therefore require bandwidth policies that limit real-time audio or video traffic flow.</span></span>

<span data-ttu-id="06306-109">CAC の展開の例では、北アメリカ地域に 6 つのサイトがあります。</span><span class="sxs-lookup"><span data-stu-id="06306-109">In the example CAC deployment, the North America region has six sites.</span></span> <span data-ttu-id="06306-110">そのうち Reno、Portland、および Albuquerque の 3 つのサイトは、WAN の帯域幅の制約があります。</span><span class="sxs-lookup"><span data-stu-id="06306-110">Three of these sites are constrained by WAN bandwidth: Reno, Portland, and Albuquerque.</span></span> <span data-ttu-id="06306-111">その他次の 3 つのサイトでは、WAN の帯域幅の制約が*ありません*: ニューヨーク、シカゴ、およびデトロイト。</span><span class="sxs-lookup"><span data-stu-id="06306-111">The other three sites, which are *not* constrained by WAN bandwidth: New York, Chicago, and Detroit.</span></span> <span data-ttu-id="06306-112">その他のネットワークサイトを作成または変更する方法の例については、「 [Lync Server 2013 でネットワークサイトを作成または変更](lync-server-2013-create-or-modify-a-network-site.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="06306-112">For an example of how to create or modify those other network sites, see [Create or modify a network site in Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md).</span></span>

<span data-ttu-id="06306-113">ネットワークトポロジの例を表示するには、「計画」のドキュメントの「 [例: Lync Server 2013 での通話受付管理の要件の収集](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="06306-113">To view the example network topology, see [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) in the Planning documentation.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="06306-114">次の手順では、Lync Server 管理シェルを使用してネットワークサイトを作成します。</span><span class="sxs-lookup"><span data-stu-id="06306-114">In the following procedure, Lync Server Management Shell is used to create a network site.</span></span> <span data-ttu-id="06306-115">Lync Server コントロールパネルを使用してネットワークサイトを作成する方法の詳細については、「 <A href="lync-server-2013-create-or-modify-a-network-site.md">create or modify a network site In Lync Server 2013</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="06306-115">For details about using Lync Server Control Panel to create a network site, see <A href="lync-server-2013-create-or-modify-a-network-site.md">Create or modify a network site in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-create-network-sites-for-call-admission-control"></a><span data-ttu-id="06306-116">通話受付管理用のネットワーク サイトを作成するには</span><span class="sxs-lookup"><span data-stu-id="06306-116">To create network sites for call admission control</span></span>

1.  <span data-ttu-id="06306-117">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="06306-117">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="06306-118">**New-CsNetworkSite** コマンドレットを実行してネットワーク サイトを作成し、各サイトに適切な帯域幅ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="06306-118">Run the **New-CsNetworkSite** cmdlet to create network sites and apply an appropriate bandwidth policy profile to each site.</span></span> <span data-ttu-id="06306-119">たとえば、以下を実行します。</span><span class="sxs-lookup"><span data-stu-id="06306-119">For example, run:</span></span>
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Reno -Description "NA:Branch office for sales force" -NetworkRegionID NorthAmerica -BWPolicyProfileID 10MB_Link
       ```
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Portland -Description "NA:Branch office for marketing force" -NetworkRegionID NorthAmerica -BWPolicyProfileID 5MB_Link
       ```
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Albuquerque -Description "NA:Branch office for SouthWest sales" -NetworkRegionID EMEA -BWPolicyProfileID 10MB_Link
       ```

3.  <span data-ttu-id="06306-120">トポロジの例全体のネットワーク サイトの作成を完了するには、帯域幅の制約がある、EMEA および APAC 地域のネットワーク サイトに対してステップ 2 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="06306-120">To finish creating network sites for the entire example topology, repeat step 2 for the bandwidth-constrained network sites in the EMEA and APAC regions.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

