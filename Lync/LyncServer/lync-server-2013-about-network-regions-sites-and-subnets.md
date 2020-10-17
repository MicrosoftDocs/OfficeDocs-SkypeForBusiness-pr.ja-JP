---
title: 'Lync Server 2013: ネットワーク地域、サイト、およびサブネットについて'
description: 'Lync Server 2013: ネットワーク地域、サイト、およびサブネットについて。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: About network regions, sites, and subnets
ms:assetid: 6662123a-d011-408c-a290-92b2a8589943
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398467(v=OCS.15)
ms:contentKeyID: 48184335
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a3c7f660f3c72003527e0721c3f9702865e9b9b4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568933"
---
# <a name="about-network-regions-sites-and-subnets-in-lync-server-2013"></a><span data-ttu-id="e0f3a-103">Lync Server 2013 のネットワーク地域、サイト、およびサブネットについて</span><span class="sxs-lookup"><span data-stu-id="e0f3a-103">About network regions, sites, and subnets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e0f3a-104">_**トピックの最終更新日:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="e0f3a-104">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="e0f3a-p101">このセクションで説明する高度なエンタープライズ VoIP の各機能は、ネットワーク地域、ネットワーク サイト、およびサブネットの特定の構成要件を共有します。 たとえば、3 つの高度な機能のいずれでも、トポロジの各サブネットが特定の*ネットワーク サイト*に関連付けられていて、各ネットワーク サイトは*ネットワーク地域*に関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0f3a-p101">The advanced Enterprise Voice features described in this section share certain configuration requirements for network regions, network sites, and subnets. For example, all three advanced features require that each subnet in your topology be associated with a specific *network site*, and each network site must be associated with a *network region*.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e0f3a-107">通話受付管理、E9-1-1、またはメディアバイパスのネットワーク構成を開始する前に、「計画」のドキュメントの「 <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">Lync Server 2013 の高度なエンタープライズ voip 機能のネットワーク</A> 設定に関するその他の情報を確認してください。</span><span class="sxs-lookup"><span data-stu-id="e0f3a-107">Before you begin network configuration for call admission control, E9-1-1, or media bypass, make sure that you reviewed additional information about network settings in the <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">Network settings for the advanced Enterprise Voice features in Lync Server 2013</A> topic in the Planning documentation.</span></span> <span data-ttu-id="e0f3a-108">通話受付管理に関する基本的なネットワーク構成の詳細については、「計画」のドキュメントの「 <A href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Lync Server 2013 での通話受付管理の要件の定義</A> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0f3a-108">For details about network configuration primarily about call admission control, also see <A href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Defining your requirements for call admission control in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<span data-ttu-id="e0f3a-109">通話受付管理および E9-1-1 には、ネットワーク サイトの追加構成要件があります。</span><span class="sxs-lookup"><span data-stu-id="e0f3a-109">Call admission control and E9-1-1 have additional configuration requirements for network sites:</span></span>

  - <span data-ttu-id="e0f3a-110">通話受付管理では、WAN の帯域幅が制限されているサイトごとに*帯域幅ポリシー プロファイル*を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0f3a-110">Call admission control requires that a *bandwidth policy profile* be specified for each site that is constrained by WAN bandwidth limitations.</span></span> <span data-ttu-id="e0f3a-111">通話受付管理を展開することを計画している場合は、ネットワークサイトを構成する前に、 [Lync Server 2013 で帯域幅ポリシープロファイルを作成](lync-server-2013-create-bandwidth-policy-profiles.md) する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0f3a-111">If you plan to deploy call admission control, you must [Create bandwidth policy profiles in Lync Server 2013](lync-server-2013-create-bandwidth-policy-profiles.md) before you configure your network sites.</span></span>

  - <span data-ttu-id="e0f3a-112">E9-1-1 では、サイトごとに*場所のポリシー*を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0f3a-112">E9-1-1 requires that a *location policy* be specified for each site.</span></span> <span data-ttu-id="e0f3a-113">E9-1-1 の展開を計画している場合は、ネットワークサイトを構成する前に、 [Lync Server 2013 で場所のポリシーを作成](lync-server-2013-create-location-policies.md) する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0f3a-113">If you plan to deploy E9-1-1, you must [Create location policies in Lync Server 2013](lync-server-2013-create-location-policies.md) before you configure your network sites.</span></span>

<div>

## <a name="create-or-modify-network-regions-network-sites-and-subnets"></a><span data-ttu-id="e0f3a-114">ネットワーク地域、ネットワーク サイト、サブネットの作成または変更</span><span class="sxs-lookup"><span data-stu-id="e0f3a-114">Create or Modify Network Regions, Network Sites, and Subnets</span></span>

<span data-ttu-id="e0f3a-p105">次のトピックには、ネットワーク地域およびネットワーク サイトを作成または変更するステップや、サブネットをネットワーク サイトに関連付けるステップが記載されています。 これらは、特定の高度なエンタープライズ VoIP 機能に固有のトピックではありません。</span><span class="sxs-lookup"><span data-stu-id="e0f3a-p105">The following topics provide steps to create or modify network regions and network sites, and to associate subnets with network sites. These topics are not specific to any particular advanced Enterprise Voice feature.</span></span>

  - [<span data-ttu-id="e0f3a-117">Lync Server 2013 でネットワーク地域を作成または変更する</span><span class="sxs-lookup"><span data-stu-id="e0f3a-117">Create or modify a network region in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-region.md)

  - [<span data-ttu-id="e0f3a-118">Lync Server 2013 でのネットワークサイトの作成または変更</span><span class="sxs-lookup"><span data-stu-id="e0f3a-118">Create or modify a network site in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-site.md)

  - [<span data-ttu-id="e0f3a-119">Lync Server 2013 でのサブネットとネットワークサイトの関連付け</span><span class="sxs-lookup"><span data-stu-id="e0f3a-119">Associate a subnet with a network site in Lync Server 2013</span></span>](lync-server-2013-associate-a-subnet-with-a-network-site.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

