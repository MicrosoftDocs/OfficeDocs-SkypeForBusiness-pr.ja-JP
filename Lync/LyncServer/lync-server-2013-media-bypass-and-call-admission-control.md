---
title: 'Lync Server 2013: メディア バイパスと通話受付管理'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Media bypass and call admission control
ms:assetid: 120b2a2b-5f97-4735-a2ee-0f849feb8c1d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398203(v=OCS.15)
ms:contentKeyID: 48183454
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c5e02a57add6b93f1ad5c5efc3ac644e65e97f4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827558"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-bypass-and-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="0155f-102">Lync Server 2013 でのメディア バイパスと通話受付管理</span><span class="sxs-lookup"><span data-stu-id="0155f-102">Media bypass and call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0155f-103">_**最終更新日:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="0155f-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="0155f-p101">メディア バイパスおよび通話受付管理 (CAC) は、通話メディア帯域幅の制御を連携して管理します。メディア バイパスは、うまく接続されたリンクを介したメディアの流れを円滑にします。CAC は、帯域幅の制限があるリンクのトラフィックを管理します。メディア バイパスと CAC は互換性がないため、一方を計画する際には、もう一方の存在にも注意しなければなりません。次の組み合わせがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="0155f-p101">Media bypass and call admission control (CAC) work together to manage bandwidth control for call media. Media bypass facilitates media flow over well-connected links; CAC manages traffic on links with bandwidth constraints. Because Media Bypass and CAC are mutually exclusive, you must be mindful of one when planning for the other. The following combinations are supported:</span></span>

  - <span data-ttu-id="0155f-p102">CAC およびメディア バイパスはどちらも有効です。メディア バイパスは、[**サイトおよび地域情報を使用する**] に設定されていなければなりません。このサイトおよび地域情報は、CAC に使われている情報と同じです。</span><span class="sxs-lookup"><span data-stu-id="0155f-p102">CAC and Media Bypass are both enabled. Media Bypass must be set to **Use Site and Region Information**. This site and region information is the same as that used for CAC.</span></span>
    
    <span data-ttu-id="0155f-p103">CAC を有効にすると [**常にバイパスする**] を選択できず、逆も同様です。なぜなら、2 つの構成は互換性がないためです。つまり、2 つのうちの 1 つだけがいずれの PSTN 通話にも適用されます。最初に、メディア バイパスが通話に適用されるかどうかを定義する確認が行われます。その場合、CAC は使われません。これは当然のことです。バイパスが適している通話の場合は、定義上、CAC を必要としない接続を使っているものだからです。通話にバイパスが適用されない場合 (つまり、クライアントおよびゲートウェイのバイパス ID が一致しない場合)、そのときには CAC が通話に適用されます。</span><span class="sxs-lookup"><span data-stu-id="0155f-p103">If you enable CAC, you cannot select **Always Bypass**, and vice-versa, because the two configurations are mutually exclusive. That is, only one of the two will apply to any given PSTN call. First, a check is made to determine if media bypass applies to the call. If it does, then CAC is not used. This makes sense, because if a call is eligible for bypass, it is by definition using a connection where CAC is not needed. If bypass cannot be applied to the call (that is, if the client’s and gateway’s bypass IDs do not match), then CAC is applied to the call.</span></span>

  - <span data-ttu-id="0155f-117">CAC は無効で、メディア バイパスは [**常にバイパスする**] に設定されています。</span><span class="sxs-lookup"><span data-stu-id="0155f-117">CAC not enabled and Media Bypass set to **Always Bypass**.</span></span>
    
    <span data-ttu-id="0155f-118">この構成では、クライアントおよびトランクの両方のサブネットが、システムによって計算された、唯一のバイパス ID にマップされています。</span><span class="sxs-lookup"><span data-stu-id="0155f-118">In this configuration, both client and trunk subnets are mapped to one and only one bypass ID, which is computed by the system.</span></span>

  - <span data-ttu-id="0155f-119">CAC は無効で、メディア バイパスは [**サイトおよび地域情報を使用する**] に設定されています。</span><span class="sxs-lookup"><span data-stu-id="0155f-119">CAC not enabled and Media Bypass set to **Use Site and Region Information**.</span></span>
    
    <span data-ttu-id="0155f-p104">[**サイトおよび地域情報を使用する**] が有効である場合には、CAC が有効であるかないかにかかわらず、バイパスの決定は基本的に同じ方法で行われます。つまり、いずれの PSTN 通話でも、クライアントのサブネットは特定のサイトにマップされ、サブネットのバイパス ID が抽出されます。同様に、ゲートウェイのサブネットが特定のサイトにマップされ、サブネットのバイパス ID が抽出されます。2 つのバイパス ID が同一である場合のみ、通話にバイパスが発生します。2 つのバイパス ID が同一でない場合、メディア バイパスは発生しません。</span><span class="sxs-lookup"><span data-stu-id="0155f-p104">Where **Use Site and Region Information** is enabled, bypass determination works essentially the same way, regardless of whether CAC is enabled or not. That is, for any given PSTN call, the client’s subnet is mapped to a particular site, and the bypass ID for that subnet is extracted. Similarly, the gateway’s subnet is mapped to a particular site, and the bypass ID for that subnet is extracted. Only if the two bypass IDs are identical will bypass happen for the call. If they are not identical, media bypass will not occur.</span></span>
    
    <span data-ttu-id="0155f-p105">たとえ CAC がグローバルに無効であった場合でも、バイパス決定を制御するのに [サイトおよび地域] 構成を使用したい場合は、帯域幅ポリシーをそれぞれのサイトおよびリンクに定義する必要があります。帯域幅制限または帯域幅モダリティの実際の値は重要ではありません。最大の目標は、システムが、うまく接続されていない異なるロケールと関連付けるため、異なるバイパス ID を自動的に計算できるようにすることです。定義上、帯域幅の制限を定義するということは、リンクがうまく接続されていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="0155f-p105">Even though CAC is disabled globally, bandwidth policy needs to be defined for each site and link if you want to use site-and-region configuration to control the bypass decision. The actual value of the bandwidth constraint or its modality doesn’t matter. The ultimate goal is to have the system automatically calculate different bypass IDs to associate with different locales that are not well connected. Defining a bandwidth constraint by definition means a link is not well connected.</span></span>

  - <span data-ttu-id="0155f-129">CAC は有効ですが、メディア バイパスは有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="0155f-129">CAC is enabled and media bypass is not enabled.</span></span> <span data-ttu-id="0155f-130">これは、すべてのゲートウェイまたは IP-PBX がうまく接続されていない、あるいはメディア バイパスのその他の要件が満たされていない場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="0155f-130">This would apply only where all gateways and IP-PBXs are not well connected or do not meet other requirements for media bypass.</span></span> <span data-ttu-id="0155f-131">メディアバイパスの要件の詳細については、「 [Lync Server 2013 でのメディアのバイパスの技術要件](lync-server-2013-technical-requirements-for-media-bypass.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0155f-131">For details about requirements for media bypass, see [Technical requirements for media bypass in Lync Server 2013](lync-server-2013-technical-requirements-for-media-bypass.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="0155f-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="0155f-132">See Also</span></span>


[<span data-ttu-id="0155f-133">Lync Server 2013 でのメディアのバイパスの概要</span><span class="sxs-lookup"><span data-stu-id="0155f-133">Overview of media bypass in Lync Server 2013</span></span>](lync-server-2013-overview-of-media-bypass.md)  
[<span data-ttu-id="0155f-134">Lync Server 2013 のメディア バイパス モード</span><span class="sxs-lookup"><span data-stu-id="0155f-134">Media bypass modes in Lync Server 2013</span></span>](lync-server-2013-media-bypass-modes.md)  
[<span data-ttu-id="0155f-135">Lync Server 2013 メディア バイパスの技術要件</span><span class="sxs-lookup"><span data-stu-id="0155f-135">Technical requirements for media bypass in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

