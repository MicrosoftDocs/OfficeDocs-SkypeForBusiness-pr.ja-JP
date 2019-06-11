---
title: 'Lync Server 2013: ネットワーク領域、サイト、およびサブネットの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: About network regions, sites, and subnets
ms:assetid: 6662123a-d011-408c-a290-92b2a8589943
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398467(v=OCS.15)
ms:contentKeyID: 48184335
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef6601a0baafd1226f4e283d62a8cbdb410064ff
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840979"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="about-network-regions-sites-and-subnets-in-lync-server-2013"></a><span data-ttu-id="9946f-102">Lync Server 2013 ネットワーク領域、サイト、およびサブネットの構成</span><span class="sxs-lookup"><span data-stu-id="9946f-102">About network regions, sites, and subnets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9946f-103">_**最終更新日:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="9946f-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="9946f-104">このセクションで説明されている高度なエンタープライズ Voip 機能は、ネットワーク領域、ネットワークサイト、サブネットの特定の構成要件を共有します。</span><span class="sxs-lookup"><span data-stu-id="9946f-104">The advanced Enterprise Voice features described in this section share certain configuration requirements for network regions, network sites, and subnets.</span></span> <span data-ttu-id="9946f-105">たとえば、3つの高度な機能を使用するには、トポロジの各サブネットが特定の*ネットワークサイト*と関連付けられ、各ネットワークサイトが*ネットワーク領域*に関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="9946f-105">For example, all three advanced features require that each subnet in your topology be associated with a specific *network site*, and each network site must be associated with a *network region*.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="9946f-106">通話受付制御、E9、またはメディアバイパスのネットワーク構成を始める前に、 <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">「Lync Server 2013 の高度なエンタープライズ voip 機能のネットワーク設定</A>」のネットワーク設定に関する追加情報を確認したことを確認してください。計画ドキュメントのトピックです。</span><span class="sxs-lookup"><span data-stu-id="9946f-106">Before you begin network configuration for call admission control, E9-1-1, or media bypass, make sure that you reviewed additional information about network settings in the <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">Network settings for the advanced Enterprise Voice features in Lync Server 2013</A> topic in the Planning documentation.</span></span> <span data-ttu-id="9946f-107">ネットワーク構成の詳細については、主に通話受付制御について詳しくは、「計画ドキュメントの<A href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Lync Server 2013 での通話受付制御の要件の定義</A>」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9946f-107">For details about network configuration primarily about call admission control, also see <A href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Defining your requirements for call admission control in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<span data-ttu-id="9946f-108">通話受付管理および E9-1-1 には、ネットワーク サイトの追加構成要件があります。</span><span class="sxs-lookup"><span data-stu-id="9946f-108">Call admission control and E9-1-1 have additional configuration requirements for network sites:</span></span>

  - <span data-ttu-id="9946f-109">通話受付管理では、WAN の帯域幅が制限されているサイトごとに*帯域幅ポリシー プロファイル*を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9946f-109">Call admission control requires that a *bandwidth policy profile* be specified for each site that is constrained by WAN bandwidth limitations.</span></span> <span data-ttu-id="9946f-110">通話受付制御の展開を計画している場合は、ネットワークサイトを構成する前に、 [Lync Server 2013 で帯域幅ポリシープロファイルを作成](lync-server-2013-create-bandwidth-policy-profiles.md)する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9946f-110">If you plan to deploy call admission control, you must [Create bandwidth policy profiles in Lync Server 2013](lync-server-2013-create-bandwidth-policy-profiles.md) before you configure your network sites.</span></span>

  - <span data-ttu-id="9946f-111">E9-1-1 では、サイトごとに *場所のポリシー*を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9946f-111">E9-1-1 requires that a *location policy* be specified for each site.</span></span> <span data-ttu-id="9946f-112">E9 の展開を計画している場合は、ネットワークサイトを構成する前に、 [Lync Server 2013 で位置情報ポリシーを作成](lync-server-2013-create-location-policies.md)する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9946f-112">If you plan to deploy E9-1-1, you must [Create location policies in Lync Server 2013](lync-server-2013-create-location-policies.md) before you configure your network sites.</span></span>

<div>

## <a name="create-or-modify-network-regions-network-sites-and-subnets"></a><span data-ttu-id="9946f-113">ネットワーク領域、ネットワークサイト、サブネットを作成または変更する</span><span class="sxs-lookup"><span data-stu-id="9946f-113">Create or Modify Network Regions, Network Sites, and Subnets</span></span>

<span data-ttu-id="9946f-114">次のトピックでは、ネットワーク領域とネットワークサイトを作成または変更し、サブネットをネットワークサイトに関連付ける手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="9946f-114">The following topics provide steps to create or modify network regions and network sites, and to associate subnets with network sites.</span></span> <span data-ttu-id="9946f-115">これらのトピックは、特定の高度なエンタープライズ Voip 機能に固有のものではありません。</span><span class="sxs-lookup"><span data-stu-id="9946f-115">These topics are not specific to any particular advanced Enterprise Voice feature.</span></span>

  - [<span data-ttu-id="9946f-116">Lync Server 2013 でネットワークの領域を作成または変更する</span><span class="sxs-lookup"><span data-stu-id="9946f-116">Create or modify a network region in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-region.md)

  - [<span data-ttu-id="9946f-117">Lync Server 2013 でのネットワーク サイトの作成または変更</span><span class="sxs-lookup"><span data-stu-id="9946f-117">Create or modify a network site in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-site.md)

  - [<span data-ttu-id="9946f-118">Lync Server 2013 でのネットワーク サイトとサブネットの関連付け</span><span class="sxs-lookup"><span data-stu-id="9946f-118">Associate a subnet with a network site in Lync Server 2013</span></span>](lync-server-2013-associate-a-subnet-with-a-network-site.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

