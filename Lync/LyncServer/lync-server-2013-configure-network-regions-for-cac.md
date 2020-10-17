---
title: 'Lync Server 2013: CAC のネットワーク地域の構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure network regions for CAC
ms:assetid: ea3ff988-dd5a-4bc4-bec5-39a0fb09793a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399051(v=OCS.15)
ms:contentKeyID: 48185906
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c029de2a7b6296dc81d365978c55d18c817e0894
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520544"
---
# <a name="configure-network-regions-for-cac-in-lync-server-2013"></a><span data-ttu-id="1fe26-102">Lync Server 2013 で CAC のネットワーク地域を構成する</span><span class="sxs-lookup"><span data-stu-id="1fe26-102">Configure network regions for CAC in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1fe26-103">_**トピックの最終更新日:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="1fe26-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1fe26-104">E9-1-1 またはメディア バイパスのネットワーク地域をすでに作成している場合には、<STRONG>Set-CsNetworkRegion</STRONG> コマンドレットを使用して、通話受付管理サービス (CAC) 固有の設定を追加することにより、既存のネットワーク地域を変更します。</span><span class="sxs-lookup"><span data-stu-id="1fe26-104">If you have already created network regions for E9-1-1 or media bypass, you can modify the existing network regions by adding settings specific to call admission control (CAC) by using the <STRONG>Set-CsNetworkRegion</STRONG> cmdlet.</span></span> <span data-ttu-id="1fe26-105">ネットワーク地域の変更方法の例については、「 <A href="lync-server-2013-create-or-modify-a-network-region.md">Lync Server 2013 でネットワーク地域を作成または変更</A>する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1fe26-105">For an example of how to modify a network region, see <A href="lync-server-2013-create-or-modify-a-network-region.md">Create or modify a network region in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="1fe26-106">*ネットワーク地域*は、CAC、E9-1-1、およびメディア バイパスで使用するネットワーク ハブまたはバックボーンです。</span><span class="sxs-lookup"><span data-stu-id="1fe26-106">*Network regions* are the network hubs or backbones that are used in configuring CAC, E9-1-1, and media bypass.</span></span> <span data-ttu-id="1fe26-107">以下の手順に従って、CAC のネットワーク トポロジ例に含まれているネットワーク地域に一致する、ネットワーク地域を作成します。</span><span class="sxs-lookup"><span data-stu-id="1fe26-107">Use the following procedure to create network regions that align to network regions in the example network topology for CAC.</span></span> <span data-ttu-id="1fe26-108">ネットワークトポロジの例を表示するには、「計画」のドキュメントの「 [例: Lync Server 2013 での通話受付管理の要件の収集](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1fe26-108">To view the example network topology, see [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) in the Planning documentation.</span></span>

<span data-ttu-id="1fe26-109">CAC のネットワークトポロジの例には、北アメリカ、EMEA、APAC の3つの地域があります。</span><span class="sxs-lookup"><span data-stu-id="1fe26-109">The example network topology for CAC has three regions: North America, EMEA, and APAC.</span></span> <span data-ttu-id="1fe26-110">各地域には、指定した中央サイトがあります。</span><span class="sxs-lookup"><span data-stu-id="1fe26-110">Each region has a specified central site.</span></span> <span data-ttu-id="1fe26-111">北米地域の場合、指定された中央サイトはシカゴという名前です。</span><span class="sxs-lookup"><span data-stu-id="1fe26-111">For the North America region, the designated central site is named CHICAGO.</span></span> <span data-ttu-id="1fe26-112">次の手順では、 **新しい-CsNetworkRegion** コマンドレットを使用して北米地域を作成する方法の例を示します。</span><span class="sxs-lookup"><span data-stu-id="1fe26-112">The following procedure shows an example of how you can use the **New-CsNetworkRegion** cmdlet to create the North America region.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1fe26-113">次の手順では、Lync Server 管理シェルを使用してネットワーク地域を作成します。</span><span class="sxs-lookup"><span data-stu-id="1fe26-113">In the following procedure, Lync Server Management Shell is used to create a network region.</span></span> <span data-ttu-id="1fe26-114">Lync Server コントロールパネルを使用してネットワーク地域を作成する方法の詳細については、「 <A href="lync-server-2013-create-or-modify-a-network-region.md">Lync server 2013 でネットワーク地域を作成または変更</A>する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1fe26-114">For details about using Lync Server Control Panel to create a network region, see <A href="lync-server-2013-create-or-modify-a-network-region.md">Create or modify a network region in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-create-a-network-region-for-call-admission-control"></a><span data-ttu-id="1fe26-115">通話受付管理用のネットワーク地域を作成するには</span><span class="sxs-lookup"><span data-stu-id="1fe26-115">To create a network region for call admission control</span></span>

1.  <span data-ttu-id="1fe26-116">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="1fe26-116">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="1fe26-117">作成する必要がある地域ごとに **New-CsNetworkRegion** コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="1fe26-117">For each region that you need to create, run the **New-CsNetworkRegion** cmdlet.</span></span> <span data-ttu-id="1fe26-118">たとえば、North America を作成するには、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="1fe26-118">For example, to create the North America region, run:</span></span>
    
        New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"

3.  <span data-ttu-id="1fe26-119">ステップ 2 を繰り返して、EMEA 地域と APAC 地域を作成します。</span><span class="sxs-lookup"><span data-stu-id="1fe26-119">Repeat step 2 to create the network regions, EMEA and APAC.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

