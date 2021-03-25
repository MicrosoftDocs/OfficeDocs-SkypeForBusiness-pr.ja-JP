---
title: Skype for Business での通話受付管理のコンポーネントとトポロジ
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0beec6be-2431-4255-a3d2-512dd030e66a
description: MPLS ネットワーク、SIP トランク、またはサード パーティの PSTN ゲートウェイまたは PBX がある場合の通話受付管理 (CAC) の計画。 Skype for Business Server エンタープライズ VoIP。
ms.openlocfilehash: 771b98e10c28248bc917bff2b8128b6258c140c5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109193"
---
# <a name="components-and-topologies-for-call-admission-control-in-skype-for-business"></a><span data-ttu-id="80049-104">Skype for Business での通話受付管理のコンポーネントとトポロジ</span><span class="sxs-lookup"><span data-stu-id="80049-104">Components and topologies for call admission control in Skype for Business</span></span>

<span data-ttu-id="80049-105">MPLS ネットワーク、SIP トランク、またはサード パーティの PSTN ゲートウェイまたは PBX がある場合の通話受付管理 (CAC) の計画。</span><span class="sxs-lookup"><span data-stu-id="80049-105">Planning for call admission control (CAC) if you have an MPLS network, a SIP trunk, or a third-party PSTN gateway or PBX.</span></span> <span data-ttu-id="80049-106">Skype for Business Server エンタープライズ VoIP。</span><span class="sxs-lookup"><span data-stu-id="80049-106">Applies to Skype for Business Server Enterprise Voice.</span></span>

<span data-ttu-id="80049-107">このセクションのトピックでは、通話受付管理 (CAC) をさまざまな種類のネットワーク トポロジで展開する際に特に考慮する点について説明します。</span><span class="sxs-lookup"><span data-stu-id="80049-107">The topics in this section provide information about special considerations for deploying call admission control (CAC) with various types of network topologies.</span></span>

## <a name="call-admission-control-on-an-mpls-network"></a><span data-ttu-id="80049-108">MPLS ネットワークでの通話受付管理</span><span class="sxs-lookup"><span data-stu-id="80049-108">Call admission control on an MPLS network</span></span>

<span data-ttu-id="80049-p103">Multiprotocol Label Switching (MPLS) では、すべてのサイトがフル メッシュで接続されます。つまり、すべてのサイトがインターネット サービス プロバイダーの MPLS バックボーンに直接接続され、各サイトが WAN リンクから MPLS にかけて使用されるプロビジョニングされた帯域幅であるということです。IP ルーティングを制御するネットワーク ハブやセントラル サイトはありません。次の図に、MPLS トポロジに基づく簡単なネットワークを示します。</span><span class="sxs-lookup"><span data-stu-id="80049-p103">In a Multiprotocol Label Switching (MPLS) network, all sites are connected by a full-mesh. That is, all sites are connected directly to the MPLS backbone of the Internet service provider, and each site is provisioned bandwidth to be used across a WAN link to the MPLS cloud. There is no network hub or central site to control IP routing. The following figure shows a simple network based on MPLS technology.</span></span>

<span data-ttu-id="80049-113">**MPLS ネットワークの例**</span><span class="sxs-lookup"><span data-stu-id="80049-113">**Example MPLS network**</span></span>

![MPLS を使用した CAC](../../media/CAC_MPLS_1.jpg)

<span data-ttu-id="80049-p104">MPLS ネットワークで通話受付管理 (CAC) を展開するには、MPLS クラウドを表すネットワーク地域を作成し、MPLS の各サテライト サイトを表すネットワーク サイトを作成します。 次の図で、前の図の MPLS ネットワークの例を表すための、ネットワーク地域およびネットワーク サイトの構成方法について説明します。 全体的な帯域幅および帯域幅セッションの制限は、各ネットワーク サイトから MPLS クラウドを表すネットワーク地域までの WAN リンクの容量に基づきます。</span><span class="sxs-lookup"><span data-stu-id="80049-p104">To deploy call admission control (CAC) in an MPLS network, you create a network region to represent the MPLS cloud, and create a network site to represent each MPLS satellite site. The following figure illustrates how the network region and network sites should be configured to represent the example MPLS network in the previous figure. The overall bandwidth limits and bandwidth session limits are then based on the capacity of the WAN link from each network site to the network region that represents the MPLS cloud.</span></span>

<span data-ttu-id="80049-118">**MPLS ネットワークのネットワーク地域およびネットワーク サイト**</span><span class="sxs-lookup"><span data-stu-id="80049-118">**Network region and network sites for an MPLS network**</span></span>

![MPLS ダイアグラムを使用した通話受付管理 (CAC)](../../media/CAC_MPLS_2.jpg)

## <a name="call-admission-control-on-a-sip-trunk"></a><span data-ttu-id="80049-120">SIP トランクの通話受付管理</span><span class="sxs-lookup"><span data-stu-id="80049-120">Call admission control on a SIP trunk</span></span>

<span data-ttu-id="80049-p105">SIP トランクに通話受付管理 (CAC) を展開するには、インターネット テレフォニー サービス プロバイダー (ITSP) を表すためのネットワーク サイトを作成します。SIP トランクに帯域幅ポリシーの値を適用するには、企業内のネットワーク サイトと ITSP を表すために作成するネットワーク サイトのサイト間ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="80049-p105">To deploy call admission control (CAC) on a SIP trunk, you create a network site to represent the Internet telephony service provider (ITSP). To apply bandwidth policy values on the SIP trunk, you create an inter-site policy between the network site in your enterprise and the network site that you create to represent the ITSP.</span></span>

<span data-ttu-id="80049-123">次の図は、SIP トランクの CAC 展開の例を示しています。</span><span class="sxs-lookup"><span data-stu-id="80049-123">The following figure shows an example CAC deployment on a SIP trunk.</span></span>

<span data-ttu-id="80049-124">**SIP トランクの CAC 構成**</span><span class="sxs-lookup"><span data-stu-id="80049-124">**CAC configuration on a SIP trunk**</span></span>

![通話受付管理 SIP トランキング図](../../media/CAC_SIP_trunk_1.jpg)

<span data-ttu-id="80049-126">SIP トランクに CAC を構成するには、CAC の展開時に次の作業を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="80049-126">To configure CAC on a SIP trunk, you will have to perform the following tasks during CAC deployment:</span></span>

1. <span data-ttu-id="80049-127">ITSP を表すためのネットワーク サイトを作成します。</span><span class="sxs-lookup"><span data-stu-id="80049-127">Create a network site to represent the ITSP.</span></span> <span data-ttu-id="80049-128">ネットワーク サイトを適切なネットワーク地域に関連付けて、このネットワーク サイトの音声とビデオにゼロの帯域幅を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="80049-128">Associate the network site to an appropriate network region, and allocate bandwidth of zero for audio and video for this network site.</span></span> <span data-ttu-id="80049-129">詳細については、「展開」のドキュメントの「[Configure Network Sites for CAC](/previous-versions/office/lync-server-2013/lync-server-2013-configure-network-sites-for-cac)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="80049-129">For details, see [Configure Network Sites for CAC](/previous-versions/office/lync-server-2013/lync-server-2013-configure-network-sites-for-cac) in the Deployment documentation.</span></span>

    > [!NOTE]
    > <span data-ttu-id="80049-130">ITSP では、このネットワーク サイト構成は機能しません。</span><span class="sxs-lookup"><span data-stu-id="80049-130">For the ITSP, this network site configuration is not functional.</span></span> <span data-ttu-id="80049-131">帯域幅ポリシーの値は、手順 2 で実際に適用されます。</span><span class="sxs-lookup"><span data-stu-id="80049-131">Bandwidth policy values are actually applied in step 2.</span></span>

2. <span data-ttu-id="80049-132">手順 1 で作成したサイトの関連するパラメーター値を使用して、SIP トランクのサイト間リンクを作成します。</span><span class="sxs-lookup"><span data-stu-id="80049-132">Create an inter-site link for the SIP trunk using the relevant parameter values for the site you created in step 1.</span></span> <span data-ttu-id="80049-133">たとえば、企業内のネットワーク サイトの名前を NetworkSiteID1 パラメーターの値として使用し、ITSP ネットワーク サイトの名前を NetworkSiteID2 パラメーターの値として使用します。</span><span class="sxs-lookup"><span data-stu-id="80049-133">For example, use the name of the network site in your enterprise as the value of the NetworkSiteID1 parameter, and the ITSP network site as the value of the NetworkSiteID2 parameter.</span></span> <span data-ttu-id="80049-134">詳細については、「展開」のドキュメントの [「Skype for Business Server](../../deploy/deploy-enterprise-voice/create-network-intersite-policies.md) でネットワーク間サイト ポリシーを作成する」および [「New-CsNetworkInterSitePolicy」を参照してください](/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="80049-134">For details, see [Create network intersite policies in Skype for Business Server](../../deploy/deploy-enterprise-voice/create-network-intersite-policies.md) in the Deployment documentation, and [New-CsNetworkInterSitePolicy](/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps).</span></span>

3. <span data-ttu-id="80049-135">ITSP からセッション ボーダー コントローラー (SCB) メディアターミネーション ポイントの IP アドレスを取得します。</span><span class="sxs-lookup"><span data-stu-id="80049-135">Get the IP address of the Session Border Controller's (SCB) Media Termination Point from your ITSP.</span></span> <span data-ttu-id="80049-136">サブネット マスクが 32 の IP アドレスを、ITSP を表すネットワーク サイトに追加します。</span><span class="sxs-lookup"><span data-stu-id="80049-136">Add that IP address with a subnet mask of 32 to the network site that represents the ITSP.</span></span> <span data-ttu-id="80049-137">詳細については、「[Associate a Subnet with a Network Site](/previous-versions/office/lync-server-2013/lync-server-2013-associate-a-subnet-with-a-network-site)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="80049-137">For details, see [Associate a Subnet with a Network Site](/previous-versions/office/lync-server-2013/lync-server-2013-associate-a-subnet-with-a-network-site).</span></span>

## <a name="call-admission-control-with-a-third-party-pstn-gateway-or-pbx"></a><span data-ttu-id="80049-138">サード パーティの PSTN ゲートウェイまたは PBX を使用した通話受付管理</span><span class="sxs-lookup"><span data-stu-id="80049-138">Call admission control with a third-party PSTN gateway or PBX</span></span>

<span data-ttu-id="80049-139">このトピックでは、仲介サーバーのゲートウェイ インターフェイスとサードパーティの公衆交換電話網 (PSTN) ゲートウェイまたはプライベート ブランチ 交換 (PBX) の間のリンクに通話受付制御 (CAC) を展開する方法の例について説明します。</span><span class="sxs-lookup"><span data-stu-id="80049-139">This topic describes examples of how call admission control (CAC) can be deployed on the link between the Mediation Server's gateway interface and a third-party public switched telephone network (PSTN) gateway or private branch exchange (PBX).</span></span>

### <a name="case-1-cac-between-the-mediation-server-and-a-pstn-gateway"></a><span data-ttu-id="80049-140">ケース 1: 仲介サーバーと PSTN ゲートウェイの間の CAC</span><span class="sxs-lookup"><span data-stu-id="80049-140">Case 1: CAC between the Mediation Server and a PSTN gateway</span></span>

<span data-ttu-id="80049-141">CAC は、仲介サーバーのゲートウェイ インターフェイスからサードパーティ PBX または PSTN ゲートウェイへの WAN リンクに展開できます。</span><span class="sxs-lookup"><span data-stu-id="80049-141">CAC can be deployed on the WAN link from the Mediation Server's gateway interface to a third-party PBX or PSTN gateway.</span></span>

<span data-ttu-id="80049-142">**ケース 1: 仲介サーバーと PSTN ゲートウェイの間の CAC**</span><span class="sxs-lookup"><span data-stu-id="80049-142">**Case 1: CAC between the Mediation Server and a PSTN gateway**</span></span>

![ケース 1: 仲介サーバー PSTN ゲートウェイ間の CAC](../../media/CAC_gateways_1.jpg)

<span data-ttu-id="80049-144">この例では、仲介サーバーと PSTN ゲートウェイの間に CAC が適用されます。</span><span class="sxs-lookup"><span data-stu-id="80049-144">In this example, CAC is applied between the Mediation Server and a PSTN gateway.</span></span> <span data-ttu-id="80049-145">ネットワーク サイト 1 の Skype for Business クライアント ユーザーがネットワーク サイト 2 の PSTN ゲートウェイを介して PSTN 通話を行う場合、メディアは WAN リンクを流れます。</span><span class="sxs-lookup"><span data-stu-id="80049-145">If a Skype for Business client user at Network Site 1 places a PSTN call through the PSTN gateway in Network Site 2, the media flows through the WAN link.</span></span> <span data-ttu-id="80049-146">したがって、PSTN セッションごとに 2 つの CAC チェックが実行されます。</span><span class="sxs-lookup"><span data-stu-id="80049-146">Therefore, two CAC checks are performed for each PSTN session:</span></span>

- <span data-ttu-id="80049-147">Skype for Business クライアント アプリケーションと仲介サーバーの間</span><span class="sxs-lookup"><span data-stu-id="80049-147">Between the Skype for Business client application and the Mediation Server</span></span>

- <span data-ttu-id="80049-148">仲介サーバーと PSTN ゲートウェイの間</span><span class="sxs-lookup"><span data-stu-id="80049-148">Between the Mediation Server and the PSTN gateway</span></span>

<span data-ttu-id="80049-149">これは、ネットワーク サイト 1 のクライアントへの着信 PSTN 呼び出しと、ネットワーク サイト 1 のクライアント アプリケーションから発信される発信 PSTN 通話の両方で機能します。</span><span class="sxs-lookup"><span data-stu-id="80049-149">This works for both incoming PSTN calls to a client in Network Site 1, and for outgoing PSTN calls originating from a client application in Network Site 1.</span></span>

> [!NOTE]
> <span data-ttu-id="80049-150">PSTN ゲートウェイが属する IP サブネットが構成され、ネットワーク サイト 2 に関連付けられているか確認します。</span><span class="sxs-lookup"><span data-stu-id="80049-150">Make sure that the IP subnet that the PSTN gateway belongs to is configured and associated with Network Site 2.</span></span>

> [!NOTE]
> <span data-ttu-id="80049-151">仲介サーバーの両方のインターフェイスが属する IP サブネットが構成され、ネットワーク サイト 1 に関連付けられているか確認します。</span><span class="sxs-lookup"><span data-stu-id="80049-151">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span>

> [!NOTE]
> <span data-ttu-id="80049-152">詳細については、「[Associate a Subnet with a Network Site](/previous-versions/office/lync-server-2013/lync-server-2013-associate-a-subnet-with-a-network-site)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="80049-152">For details, see [Associate a Subnet with a Network Site](/previous-versions/office/lync-server-2013/lync-server-2013-associate-a-subnet-with-a-network-site).</span></span>

### <a name="case-2-cac-between-the-mediation-server-and-a-third-party-pbx-with-media-termination-point"></a><span data-ttu-id="80049-153">ケース 2: 仲介サーバーとメディアターミネーション ポイントを持つサード パーティ製 PBX の間の CAC</span><span class="sxs-lookup"><span data-stu-id="80049-153">Case 2: CAC between the Mediation Server and a third-party PBX with Media Termination Point</span></span>

<span data-ttu-id="80049-154">この構成は、ケース 1 に似ています。</span><span class="sxs-lookup"><span data-stu-id="80049-154">This configuration is similar to Case 1.</span></span> <span data-ttu-id="80049-155">どちらの場合も、仲介サーバーは、WAN リンクの反対側の端でメディアを終了するデバイスを知り、次ホップとして仲介サーバーでメディアターミネーション ポイント (MTP) を使用する PSTN ゲートウェイまたは PBX の IP アドレスが構成されます。</span><span class="sxs-lookup"><span data-stu-id="80049-155">In both the cases, the Mediation Server knows what device terminates media at the opposite end of the WAN link, and the IP address of the PSTN gateway or PBX with Media Termination Point (MTP) is configured on the Mediation Server as the next hop.</span></span>

<span data-ttu-id="80049-156">**ケース 2: 仲介サーバーと MTP を使用するサード パーティ製 PBX の間の CAC**</span><span class="sxs-lookup"><span data-stu-id="80049-156">**Case 2: CAC between the Mediation Server and a third-party PBX with MTP**</span></span>

![ケース 2: 仲介サーバー PBX と MTP の間の CAC](../../media/CAC_gateways_2.jpg)

<span data-ttu-id="80049-158">この例では、仲介サーバーと PBX/MTP の間に CAC が適用されます。</span><span class="sxs-lookup"><span data-stu-id="80049-158">In this example, CAC is applied between the Mediation Server and the PBX/MTP.</span></span> <span data-ttu-id="80049-159">ネットワーク サイト 1 の Skype for Business クライアント ユーザーが、ネットワーク サイト 2 にある PBX/MTP を介して PSTN 通話を行う場合、メディアは WAN リンクを流れます。</span><span class="sxs-lookup"><span data-stu-id="80049-159">If a Skype for Business client user at the Network Site 1 places a PSTN call through the PBX/MTP located in Network Site 2, the media flows through the WAN link.</span></span> <span data-ttu-id="80049-160">したがって、PSTN セッションごとに、次の 2 つの CAC チェックが実行されます。</span><span class="sxs-lookup"><span data-stu-id="80049-160">Therefore, for each PSTN session two CAC checks are performed:</span></span>

- <span data-ttu-id="80049-161">Skype for Business クライアント アプリケーションと仲介サーバーの間</span><span class="sxs-lookup"><span data-stu-id="80049-161">Between the Skype for Business client application and the Mediation Server</span></span>

- <span data-ttu-id="80049-162">仲介サーバーと PBX/MTP の間</span><span class="sxs-lookup"><span data-stu-id="80049-162">Between the Mediation Server and the PBX/MTP</span></span>

<span data-ttu-id="80049-163">これは、ネットワーク サイト 1 のクライアントへの着信 PSTN 呼び出しと、ネットワーク サイト 1 のクライアントから発信される発信 PSTN 通話の両方で機能します。</span><span class="sxs-lookup"><span data-stu-id="80049-163">This works for both incoming PSTN calls to a client in Network Site 1, and outgoing PSTN calls originating from a client in Network Site 1.</span></span>

> [!NOTE]
> <span data-ttu-id="80049-164">MTP が属する IP サブネットが構成され、ネットワーク サイト 2 に関連付けられているか確認します。</span><span class="sxs-lookup"><span data-stu-id="80049-164">Make sure that the IP subnet that the MTP belongs to is configured and associated with Network Site 2.</span></span>

> [!NOTE]
> <span data-ttu-id="80049-165">仲介サーバーの両方のインターフェイスが属する IP サブネットが構成され、ネットワーク サイト 1 に関連付けられているか確認します。</span><span class="sxs-lookup"><span data-stu-id="80049-165">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span>

> [!NOTE]
> <span data-ttu-id="80049-166">詳細については、「[Associate a Subnet with a Network Site](/previous-versions/office/lync-server-2013/lync-server-2013-associate-a-subnet-with-a-network-site)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="80049-166">For details, see [Associate a Subnet with a Network Site](/previous-versions/office/lync-server-2013/lync-server-2013-associate-a-subnet-with-a-network-site).</span></span>

### <a name="case-3-cac-between-the-mediation-server-and-a-third-party-pbx-without-a-media-termination-point"></a><span data-ttu-id="80049-167">ケース 3: メディアターミネーション ポイントのない仲介サーバーとサードパーティ PBX の間の CAC</span><span class="sxs-lookup"><span data-stu-id="80049-167">Case 3: CAC between the Mediation Server and a third-party PBX without a Media Termination Point</span></span>

<span data-ttu-id="80049-168">ケース 3 は、最初の 2 つのケースとは若干異なります。</span><span class="sxs-lookup"><span data-stu-id="80049-168">Case 3 is slightly different from the first two cases.</span></span> <span data-ttu-id="80049-169">サード パーティ PBX に MTP がない場合、サード パーティ PBX への送信セッション要求に対して仲介サーバーは、メディアが PBX 境界でどこで終了するのか分からない。</span><span class="sxs-lookup"><span data-stu-id="80049-169">If there is no MTP on the third-party PBX, for an outgoing session request to the third-party PBX the Mediation Server does not know where media will terminate in the PBX boundary.</span></span> <span data-ttu-id="80049-170">この場合、仲介サーバーとサードパーティのエンドポイント デバイスの間でメディアが直接流れます。</span><span class="sxs-lookup"><span data-stu-id="80049-170">In this case, the media flows directly between the Mediation Server and the third-party endpoint device.</span></span>

<span data-ttu-id="80049-171">**ケース 3: 仲介サーバーと MTP のないサード パーティ製 PBX の間の CAC**</span><span class="sxs-lookup"><span data-stu-id="80049-171">**Case 3: CAC between the Mediation Server and a third-party PBX without MTP**</span></span>

![ケース 3: 仲介サーバー PBX 間の CAC MTP なし](../../media/CAC_gateways_3.jpg)

<span data-ttu-id="80049-173">この例では、ネットワーク サイト 1 の Skype for Business クライアント ユーザーが PBX を介してユーザーに通話を行う場合、仲介サーバーはプロキシ レグ (Skype for Business クライアント アプリケーションと仲介サーバーの間) でのみ CAC チェックを実行できます。</span><span class="sxs-lookup"><span data-stu-id="80049-173">In this example, if a Skype for Business client user at Network Site 1 places a call to a user through the PBX, the Mediation Server is able to perform CAC checks only on the proxy leg (between the Skype for Business client application and Mediation Server).</span></span> <span data-ttu-id="80049-174">セッションが要求されている間、仲介サーバーはエンドポイント デバイスに関する情報を持たないので、呼び出しの確立前に (仲介サーバーとサード パーティエンドポイントの間の) WAN リンクで CAC チェックを実行できません。</span><span class="sxs-lookup"><span data-stu-id="80049-174">Because the Mediation Server does not have information about the endpoint device while the session is being requested, CAC checks cannot be performed on the WAN link (between the Mediation Server and the third-party endpoint) prior to call establishment.</span></span> <span data-ttu-id="80049-175">ただし、セッションが確立されると、仲介サーバーはトランクで使用される帯域幅の会計を容易にします。</span><span class="sxs-lookup"><span data-stu-id="80049-175">After the session is established, however, the Mediation Server facilitates in accounting for the bandwidth used on the trunk.</span></span>

<span data-ttu-id="80049-176">サード パーティエンドポイントから発信される呼び出しの場合、そのエンドポイント デバイスに関する情報はセッション要求時に利用できます。CAC チェックは仲介サーバーの両側で実行できます。</span><span class="sxs-lookup"><span data-stu-id="80049-176">For calls that originate from the third-party endpoint, the information about that endpoint device is available at the time of session request and CAC check can be performed on both the sides of the Mediation Server.</span></span>

> [!NOTE]
> <span data-ttu-id="80049-177">エンドポイント デバイスが属する IP サブネットが構成され、ネットワーク サイト 2 に関連付けられているか確認します。</span><span class="sxs-lookup"><span data-stu-id="80049-177">Make sure that the IP subnet that the endpoint devices belong to is configured and associated with Network Site 2.</span></span>

> [!NOTE]
> <span data-ttu-id="80049-178">仲介サーバーの両方のインターフェイスが属する IP サブネットが構成され、ネットワーク サイト 1 に関連付けられているか確認します。</span><span class="sxs-lookup"><span data-stu-id="80049-178">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span>

> [!NOTE]
> <span data-ttu-id="80049-179">詳細については、「[Associate a Subnet with a Network Site](/previous-versions/office/lync-server-2013/lync-server-2013-associate-a-subnet-with-a-network-site)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="80049-179">For details, see [Associate a Subnet with a Network Site](/previous-versions/office/lync-server-2013/lync-server-2013-associate-a-subnet-with-a-network-site).</span></span>