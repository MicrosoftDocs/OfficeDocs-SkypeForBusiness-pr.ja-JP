---
title: 'Lync Server 2013: CAC のネットワーク領域を構成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure network regions for CAC
ms:assetid: ea3ff988-dd5a-4bc4-bec5-39a0fb09793a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399051(v=OCS.15)
ms:contentKeyID: 48185906
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 773bae62596143c0e974ae02f2bd643172a99ac3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840344"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-network-regions-for-cac-in-lync-server-2013"></a><span data-ttu-id="9213f-102">Lync Server 2013 での CAC のネットワーク領域の構成</span><span class="sxs-lookup"><span data-stu-id="9213f-102">Configure network regions for CAC in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9213f-103">_**最終更新日:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="9213f-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="9213f-104">E9-1 または media バイパスのネットワーク領域を既に作成している場合は、 <STRONG>Set-CsNetworkRegion</STRONG>コマンドレットを使用して、通話受付制御 (CAC) に固有の設定を追加して、既存のネットワーク領域を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="9213f-104">If you have already created network regions for E9-1-1 or media bypass, you can modify the existing network regions by adding settings specific to call admission control (CAC) by using the <STRONG>Set-CsNetworkRegion</STRONG> cmdlet.</span></span> <span data-ttu-id="9213f-105">ネットワーク領域を変更する方法の例については、「 <A href="lync-server-2013-create-or-modify-a-network-region.md">Lync Server 2013 でネットワークの領域を作成または変更</A>する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9213f-105">For an example of how to modify a network region, see <A href="lync-server-2013-create-or-modify-a-network-region.md">Create or modify a network region in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="9213f-106">*ネットワーク領域*とは、CAC、E9、および media バイパスを構成するために使用されるネットワークハブまたはバックボーンのことです。</span><span class="sxs-lookup"><span data-stu-id="9213f-106">*Network regions* are the network hubs or backbones that are used in configuring CAC, E9-1-1, and media bypass.</span></span> <span data-ttu-id="9213f-107">次の手順を使用して、CAC のネットワークトポロジ例でネットワーク領域に合わせてネットワーク領域を作成します。</span><span class="sxs-lookup"><span data-stu-id="9213f-107">Use the following procedure to create network regions that align to network regions in the example network topology for CAC.</span></span> <span data-ttu-id="9213f-108">ネットワークトポロジの例については、「例: 計画ドキュメントで[Lync Server 2013 の通話受付制御の要件を収集](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9213f-108">To view the example network topology, see [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) in the Planning documentation.</span></span>

<span data-ttu-id="9213f-109">CAC のネットワークトポロジの例としては、北米、EMEA、APAC の3つの領域があります。</span><span class="sxs-lookup"><span data-stu-id="9213f-109">The example network topology for CAC has three regions: North America, EMEA, and APAC.</span></span> <span data-ttu-id="9213f-110">各地域には、指定したセントラルサイトがあります。</span><span class="sxs-lookup"><span data-stu-id="9213f-110">Each region has a specified central site.</span></span> <span data-ttu-id="9213f-111">北米地域の場合、指定されたセントラルサイトはシカゴという名称になります。</span><span class="sxs-lookup"><span data-stu-id="9213f-111">For the North America region, the designated central site is named CHICAGO.</span></span> <span data-ttu-id="9213f-112">次の手順では、**新しい-CsNetworkRegion**コマンドレットを使用して北米地域を作成する方法の例を示します。</span><span class="sxs-lookup"><span data-stu-id="9213f-112">The following procedure shows an example of how you can use the **New-CsNetworkRegion** cmdlet to create the North America region.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9213f-113">次の手順では、Lync Server 管理シェルを使ってネットワーク領域を作成します。</span><span class="sxs-lookup"><span data-stu-id="9213f-113">In the following procedure, Lync Server Management Shell is used to create a network region.</span></span> <span data-ttu-id="9213f-114">Lync Server コントロールパネルを使用してネットワークの領域を作成する方法について詳しくは、「 <A href="lync-server-2013-create-or-modify-a-network-region.md">Lync server 2013 でネットワークの領域を作成または変更</A>する」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9213f-114">For details about using Lync Server Control Panel to create a network region, see <A href="lync-server-2013-create-or-modify-a-network-region.md">Create or modify a network region in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-create-a-network-region-for-call-admission-control"></a><span data-ttu-id="9213f-115">通話受付制御用のネットワークの領域を作成するには</span><span class="sxs-lookup"><span data-stu-id="9213f-115">To create a network region for call admission control</span></span>

1.  <span data-ttu-id="9213f-116">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="9213f-116">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="9213f-117">作成する必要がある各領域について、**新しい CsNetworkRegion**コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="9213f-117">For each region that you need to create, run the **New-CsNetworkRegion** cmdlet.</span></span> <span data-ttu-id="9213f-118">たとえば、北米地域を作成するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="9213f-118">For example, to create the North America region, run:</span></span>
    
        New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"

3.  <span data-ttu-id="9213f-119">手順2を繰り返して、ネットワーク領域、EMEA、APAC を作成します。</span><span class="sxs-lookup"><span data-stu-id="9213f-119">Repeat step 2 to create the network regions, EMEA and APAC.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

