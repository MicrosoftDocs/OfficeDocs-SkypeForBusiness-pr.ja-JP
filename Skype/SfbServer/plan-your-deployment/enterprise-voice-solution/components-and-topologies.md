---
title: コンポーネントおよびトポロジの受付制御に電話 Skype ビジネス
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0beec6be-2431-4255-a3d2-512dd030e66a
description: MPLS ネットワーク、SIP トランク、またサードパーティの PSTN ゲートウェイまたは PBX を使用している場合の通話受付管理 (CAC) の計画について説明します。 ビジネス サーバーのエンタープライズ VoIP Skype に適用されます。
ms.openlocfilehash: f43b111d0ef3260c34b53e27a903de20fdf676ef
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23887673"
---
# <a name="components-and-topologies-for-call-admission-control-in-skype-for-business"></a><span data-ttu-id="64c45-104">コンポーネントおよびトポロジの受付制御に電話 Skype ビジネス</span><span class="sxs-lookup"><span data-stu-id="64c45-104">Components and topologies for call admission control in Skype for Business</span></span>

<span data-ttu-id="64c45-105">MPLS ネットワーク、SIP トランク、またサードパーティの PSTN ゲートウェイまたは PBX を使用している場合の通話受付管理 (CAC) の計画について説明します。</span><span class="sxs-lookup"><span data-stu-id="64c45-105">Planning for call admission control (CAC) if you have an MPLS network, a SIP trunk, or a third-party PSTN gateway or PBX.</span></span> <span data-ttu-id="64c45-106">ビジネス サーバーのエンタープライズ VoIP Skype に適用されます。</span><span class="sxs-lookup"><span data-stu-id="64c45-106">Applies to Skype for Business Server Enterprise Voice.</span></span>

<span data-ttu-id="64c45-107">このセクションのトピックでは、通話受付管理 (CAC) をさまざまな種類のネットワーク トポロジで展開する際に特に考慮する点について説明します。</span><span class="sxs-lookup"><span data-stu-id="64c45-107">The topics in this section provide information about special considerations for deploying call admission control (CAC) with various types of network topologies.</span></span>

## <a name="call-admission-control-on-an-mpls-network"></a><span data-ttu-id="64c45-108">MPLS ネットワーク上の通話受付管理</span><span class="sxs-lookup"><span data-stu-id="64c45-108">Call admission control on an MPLS network</span></span>

<span data-ttu-id="64c45-p103">Multiprotocol Label Switching (MPLS) では、すべてのサイトがフル メッシュで接続されます。つまり、すべてのサイトがインターネット サービス プロバイダーの MPLS バックボーンに直接接続され、各サイトが WAN リンクから MPLS クラウドにかけて使用されるプロビジョニングされた帯域幅であるということです。IP ルーティングを制御するネットワーク ハブや中央サイトはありません。次の図に、MPLS トポロジに基づく簡単なネットワークを示します。</span><span class="sxs-lookup"><span data-stu-id="64c45-p103">In a Multiprotocol Label Switching (MPLS) network, all sites are connected by a full-mesh. That is, all sites are connected directly to the MPLS backbone of the Internet service provider, and each site is provisioned bandwidth to be used across a WAN link to the MPLS cloud. There is no network hub or central site to control IP routing. The following figure shows a simple network based on MPLS technology.</span></span>

<span data-ttu-id="64c45-113">**MPLS ネットワークの例**</span><span class="sxs-lookup"><span data-stu-id="64c45-113">**Example MPLS network**</span></span>

![MPLS が含まれる CAC](../../media/CAC_MPLS_1.jpg)

<span data-ttu-id="64c45-p104">MPLS ネットワークで通話受付管理 (CAC) を展開するには、MPLS クラウドを表すネットワーク地域を作成し、MPLS の各サテライト サイトを表すネットワーク サイトを作成します。 次の図で、前の図の MPLS ネットワークの例を表すための、ネットワーク地域およびネットワーク サイトの構成方法について説明します。 全体的な帯域幅および帯域幅セッションの制限は、各ネットワーク サイトから MPLS クラウドを表すネットワーク地域までの WAN リンクの容量に基づきます。</span><span class="sxs-lookup"><span data-stu-id="64c45-p104">To deploy call admission control (CAC) in an MPLS network, you create a network region to represent the MPLS cloud, and create a network site to represent each MPLS satellite site. The following figure illustrates how the network region and network sites should be configured to represent the example MPLS network in the previous figure. The overall bandwidth limits and bandwidth session limits are then based on the capacity of the WAN link from each network site to the network region that represents the MPLS cloud.</span></span>

<span data-ttu-id="64c45-118">**MPLS ネットワークのネットワーク地域およびネットワーク サイト**</span><span class="sxs-lookup"><span data-stu-id="64c45-118">**Network region and network sites for an MPLS network**</span></span>

![MPLS が含まれない通話受付管理 (CAC)](../../media/CAC_MPLS_2.jpg)

## <a name="call-admission-control-on-a-sip-trunk"></a><span data-ttu-id="64c45-120">SIP トランク上の通話受付管理</span><span class="sxs-lookup"><span data-stu-id="64c45-120">Call admission control on a SIP trunk</span></span>

<span data-ttu-id="64c45-p105">SIP トランクに通話受付管理 (CAC) を展開するには、インターネット テレフォニー サービス プロバイダー (ITSP) を表すためのネットワーク サイトを作成します。SIP トランクに帯域幅ポリシーの値を適用するには、企業内のネットワーク サイトと ITSP を表すために作成するネットワーク サイトのサイト間ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="64c45-p105">To deploy call admission control (CAC) on a SIP trunk, you create a network site to represent the Internet telephony service provider (ITSP). To apply bandwidth policy values on the SIP trunk, you create an inter-site policy between the network site in your enterprise and the network site that you create to represent the ITSP.</span></span>

<span data-ttu-id="64c45-123">次の図は、SIP トランクの CAC 展開の例を示しています。</span><span class="sxs-lookup"><span data-stu-id="64c45-123">The following figure shows an example CAC deployment on a SIP trunk.</span></span>

<span data-ttu-id="64c45-124">**SIP トランクの CAC 構成**</span><span class="sxs-lookup"><span data-stu-id="64c45-124">**CAC configuration on a SIP trunk**</span></span>

![通話受付管理の SIP トランキングの図](../../media/CAC_SIP_trunk_1.jpg)

<span data-ttu-id="64c45-126">SIP トランクに CAC を構成するには、CAC の展開時に次の作業を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="64c45-126">To configure CAC on a SIP trunk, you will have to perform the following tasks during CAC deployment:</span></span>

1. <span data-ttu-id="64c45-127">ITSP を表すためのネットワーク サイトを作成します。</span><span class="sxs-lookup"><span data-stu-id="64c45-127">Create a network site to represent the ITSP.</span></span> <span data-ttu-id="64c45-128">ネットワーク サイトを適切なネットワーク地域に関連付けて、このネットワーク サイトの音声とビデオにゼロの帯域幅を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="64c45-128">Associate the network site to an appropriate network region, and allocate bandwidth of zero for audio and video for this network site.</span></span> <span data-ttu-id="64c45-129">詳細については、展開に関するドキュメントの[CAC のネットワーク サイトの構成](https://technet.microsoft.com/library/afcea38f-5789-45ec-97af-c6e38364950c.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64c45-129">For details, see [Configure Network Sites for CAC](https://technet.microsoft.com/library/afcea38f-5789-45ec-97af-c6e38364950c.aspx) in the Deployment documentation.</span></span>

    > [!NOTE]
    > <span data-ttu-id="64c45-p107">ITSP では、このネットワーク サイト構成は機能しません。 帯域幅ポリシーの値は、手順 2 で実際に適用されます。</span><span class="sxs-lookup"><span data-stu-id="64c45-p107">For the ITSP, this network site configuration is not functional. Bandwidth policy values are actually applied in step 2.</span></span>

2. <span data-ttu-id="64c45-132">手順 1 で作成したサイトの関連するパラメーター値を使用して、SIP トランクのサイト間リンクを作成します。</span><span class="sxs-lookup"><span data-stu-id="64c45-132">Create an inter-site link for the SIP trunk using the relevant parameter values for the site you created in step 1.</span></span> <span data-ttu-id="64c45-133">たとえば、企業内のネットワーク サイトの名前を NetworkSiteID1 パラメーターの値として使用し、ITSP ネットワーク サイトの名前を NetworkSiteID2 パラメーターの値として使用します。</span><span class="sxs-lookup"><span data-stu-id="64c45-133">For example, use the name of the network site in your enterprise as the value of the NetworkSiteID1 parameter, and the ITSP network site as the value of the NetworkSiteID2 parameter.</span></span> <span data-ttu-id="64c45-134">詳細については、展開に関するドキュメント、および[新規 CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps) [Skype ビジネス サーバー用のネットワーク サイト間ポリシーの作成](../../deploy/deploy-enterprise-voice/create-network-intersite-policies.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64c45-134">For details, see [Create network intersite policies in Skype for Business Server](../../deploy/deploy-enterprise-voice/create-network-intersite-policies.md) in the Deployment documentation, and [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps).</span></span>

3. <span data-ttu-id="64c45-135">セッション ボーダー コント ローラー (SCB) の IP アドレスを取得、ITSP からメディアの終了点です。</span><span class="sxs-lookup"><span data-stu-id="64c45-135">Get the IP address of the Session Border Controller's (SCB) Media Termination Point from your ITSP.</span></span> <span data-ttu-id="64c45-136">サブネット マスクが 32 の IP アドレスを、ITSP を表すネットワーク サイトに追加します。</span><span class="sxs-lookup"><span data-stu-id="64c45-136">Add that IP address with a subnet mask of 32 to the network site that represents the ITSP.</span></span> <span data-ttu-id="64c45-137">詳細については、[ネットワーク サイトとサブネットを関連付ける](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64c45-137">For details, see [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).</span></span>

## <a name="call-admission-control-with-a-third-party-pstn-gateway-or-pbx"></a><span data-ttu-id="64c45-138">サードパーティの PSTN ゲートウェイまたは PBX での通話受付管理</span><span class="sxs-lookup"><span data-stu-id="64c45-138">Call admission control with a third-party PSTN gateway or PBX</span></span>

<span data-ttu-id="64c45-139">このトピックでは、仲介サーバーのゲートウェイ インターフェイス、およびサードパーティ製の公衆交換電話網 (PSTN) ゲートウェイまたは構内交換 (機 PBX) の間のリンクの呼受付制御 (CAC) を展開する方法の例について説明します。</span><span class="sxs-lookup"><span data-stu-id="64c45-139">This topic describes examples of how call admission control (CAC) can be deployed on the link between the Mediation Server's gateway interface and a third-party public switched telephone network (PSTN) gateway or private branch exchange (PBX).</span></span>

### <a name="case-1-cac-between-the-mediation-server-and-a-pstn-gateway"></a><span data-ttu-id="64c45-140">ケース 1: 仲介サーバーおよび PSTN ゲートウェイ間の CAC</span><span class="sxs-lookup"><span data-stu-id="64c45-140">Case 1: CAC between the Mediation Server and a PSTN gateway</span></span>

<span data-ttu-id="64c45-141">CAC は、WAN で展開できるサード パーティの PBX または PSTN ゲートウェイに仲介サーバーのゲートウェイ インターフェイスからリンクします。</span><span class="sxs-lookup"><span data-stu-id="64c45-141">CAC can be deployed on the WAN link from the Mediation Server's gateway interface to a third-party PBX or PSTN gateway.</span></span>

<span data-ttu-id="64c45-142">**ケース 1: 仲介サーバーおよび PSTN ゲートウェイ間の CAC**</span><span class="sxs-lookup"><span data-stu-id="64c45-142">**Case 1: CAC between the Mediation Server and a PSTN gateway**</span></span>

![ケース 1: 仲介サーバーと PSTN ゲートウェイ間の CAC](../../media/CAC_gateways_1.jpg)

<span data-ttu-id="64c45-144">この例では、CAC は、仲介サーバーと PSTN ゲートウェイとの間に適用されます。</span><span class="sxs-lookup"><span data-stu-id="64c45-144">In this example, CAC is applied between the Mediation Server and a PSTN gateway.</span></span> <span data-ttu-id="64c45-145">ビジネス ネットワーク サイト 1 のクライアントのユーザーは、Skype では、ネットワーク サイト 2 の PSTN ゲートウェイ経由の PSTN 通話を配置する場合、メディアは WAN リンクを介して送られます。</span><span class="sxs-lookup"><span data-stu-id="64c45-145">If a Skype for Business client user at Network Site 1 places a PSTN call through the PSTN gateway in Network Site 2, the media flows through the WAN link.</span></span> <span data-ttu-id="64c45-146">そのため、PSTN セッションごとに 2 度の CAC チェックが行われます。</span><span class="sxs-lookup"><span data-stu-id="64c45-146">Therefore, two CAC checks are performed for each PSTN session:</span></span>

- <span data-ttu-id="64c45-147">ビジネス ・ クライアント ・ アプリケーションの Skype と仲介サーバーとの間</span><span class="sxs-lookup"><span data-stu-id="64c45-147">Between the Skype for Business client application and the Mediation Server</span></span>

- <span data-ttu-id="64c45-148">仲介サーバーと PSTN ゲートウェイ間</span><span class="sxs-lookup"><span data-stu-id="64c45-148">Between the Mediation Server and the PSTN gateway</span></span>

<span data-ttu-id="64c45-149">これは、ネットワーク サイト 1 のクライアントへの PSTN 着信、およびネットワーク サイト 1 のクライアント アプリケーションからの PSTN 発信のどちらでも行われます。</span><span class="sxs-lookup"><span data-stu-id="64c45-149">This works for both incoming PSTN calls to a client in Network Site 1, and for outgoing PSTN calls originating from a client application in Network Site 1.</span></span>

> [!NOTE]
> <span data-ttu-id="64c45-150">PSTN ゲートウェイが属する IP サブネットが、確実に構成され、ネットワーク サイト 2 と関連付けられているようにしてください。</span><span class="sxs-lookup"><span data-stu-id="64c45-150">Make sure that the IP subnet that the PSTN gateway belongs to is configured and associated with Network Site 2.</span></span>

> [!NOTE]
> <span data-ttu-id="64c45-151">仲介サーバーの両方のインターフェイスが属する IP サブネットが構成され、ネットワーク サイト 1 に関連付けられていることを確認ください。</span><span class="sxs-lookup"><span data-stu-id="64c45-151">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span>

> [!NOTE]
> <span data-ttu-id="64c45-152">詳細については、[ネットワーク サイトとサブネットを関連付ける](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64c45-152">For details, see [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).</span></span>

### <a name="case-2-cac-between-the-mediation-server-and-a-third-party-pbx-with-media-termination-point"></a><span data-ttu-id="64c45-153">ケース 2: CAC を仲介サーバーおよびメディア終端ポイントでサード パーティの PBX との間</span><span class="sxs-lookup"><span data-stu-id="64c45-153">Case 2: CAC between the Mediation Server and a third-party PBX with Media Termination Point</span></span>

<span data-ttu-id="64c45-154">この構成はケース 1 に類似したものです。</span><span class="sxs-lookup"><span data-stu-id="64c45-154">This configuration is similar to Case 1.</span></span> <span data-ttu-id="64c45-155">どちらの場合で、仲介サーバーは、どのようなデバイスは、WAN リンクの反対側の端にあるメディアを終了するを知っているし、次ホップとして仲介サーバー、PSTN ゲートウェイまたは PBX メディア終端ポイント (MTP) の IP アドレスが構成されています。</span><span class="sxs-lookup"><span data-stu-id="64c45-155">In both the cases, the Mediation Server knows what device terminates media at the opposite end of the WAN link, and the IP address of the PSTN gateway or PBX with Media Termination Point (MTP) is configured on the Mediation Server as the next hop.</span></span>

<span data-ttu-id="64c45-156">**ケース 2: 仲介サーバーおよび MTP を含むサードパーティ製 PBX 間の CAC**</span><span class="sxs-lookup"><span data-stu-id="64c45-156">**Case 2: CAC between the Mediation Server and a third-party PBX with MTP**</span></span>

![ケース 2: 仲介サーバーと PBX (MTP が含まれる) 間の CAC](../../media/CAC_gateways_2.jpg)

<span data-ttu-id="64c45-158">この例では、CAC は、仲介サーバーと PBX と MTP との間に適用されます。</span><span class="sxs-lookup"><span data-stu-id="64c45-158">In this example, CAC is applied between the Mediation Server and the PBX/MTP.</span></span> <span data-ttu-id="64c45-159">ビジネス ネットワーク サイト 1 のクライアントのユーザーは、Skype では、ネットワーク サイト 2 にある PBX と MTP を PSTN の呼び出しを配置する場合、メディアは WAN リンクを通じてフローします。</span><span class="sxs-lookup"><span data-stu-id="64c45-159">If a Skype for Business client user at the Network Site 1 places a PSTN call through the PBX/MTP located in Network Site 2, the media flows through the WAN link.</span></span> <span data-ttu-id="64c45-160">そのため、それぞれの PSTN セッションごとに 2 度の CAC チェックが行われます。</span><span class="sxs-lookup"><span data-stu-id="64c45-160">Therefore, for each PSTN session two CAC checks are performed:</span></span>

- <span data-ttu-id="64c45-161">ビジネス ・ クライアント ・ アプリケーションの Skype と仲介サーバーとの間</span><span class="sxs-lookup"><span data-stu-id="64c45-161">Between the Skype for Business client application and the Mediation Server</span></span>

- <span data-ttu-id="64c45-162">仲介サーバーと PBX と MTP との間</span><span class="sxs-lookup"><span data-stu-id="64c45-162">Between the Mediation Server and the PBX/MTP</span></span>

<span data-ttu-id="64c45-163">これは、ネットワーク サイト 1 のクライアントへの PSTN 着信、およびネットワーク サイト 1 のクライアントからの PSTN 発信のどちらでも行われます。</span><span class="sxs-lookup"><span data-stu-id="64c45-163">This works for both incoming PSTN calls to a client in Network Site 1, and outgoing PSTN calls originating from a client in Network Site 1.</span></span>

> [!NOTE]
> <span data-ttu-id="64c45-164">MTP が属する IP サブネットが、確実に構成され、ネットワーク サイト 2 と関連付けられているようにしてください。</span><span class="sxs-lookup"><span data-stu-id="64c45-164">Make sure that the IP subnet that the MTP belongs to is configured and associated with Network Site 2.</span></span>

> [!NOTE]
> <span data-ttu-id="64c45-165">仲介サーバーの両方のインターフェイスが属する IP サブネットが構成され、ネットワーク サイト 1 に関連付けられていることを確認ください。</span><span class="sxs-lookup"><span data-stu-id="64c45-165">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span>

> [!NOTE]
> <span data-ttu-id="64c45-166">詳細については、[ネットワーク サイトとサブネットを関連付ける](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64c45-166">For details, see [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).</span></span>

### <a name="case-3-cac-between-the-mediation-server-and-a-third-party-pbx-without-a-media-termination-point"></a><span data-ttu-id="64c45-167">ケース 3: CAC を仲介サーバーとメディアの終了ポイントのないサード パーティの PBX との間</span><span class="sxs-lookup"><span data-stu-id="64c45-167">Case 3: CAC between the Mediation Server and a third-party PBX without a Media Termination Point</span></span>

<span data-ttu-id="64c45-168">ケース 3 は、最初の 2 つのケースとは少し異なります。</span><span class="sxs-lookup"><span data-stu-id="64c45-168">Case 3 is slightly different from the first two cases.</span></span> <span data-ttu-id="64c45-169">サード パーティの PBX に MTP がない場合は、送信セッションのサード ・ パーティ製 PBX、仲介サーバーへの要求を認識しません、メディアが PBX の境界で終了。</span><span class="sxs-lookup"><span data-stu-id="64c45-169">If there is no MTP on the third-party PBX, for an outgoing session request to the third-party PBX the Mediation Server does not know where media will terminate in the PBX boundary.</span></span> <span data-ttu-id="64c45-170">この例では、メディアは仲介サーバーおよびサードパーティ製エンドポイント デバイスの間で直接フローします。</span><span class="sxs-lookup"><span data-stu-id="64c45-170">In this case, the media flows directly between the Mediation Server and the third-party endpoint device.</span></span>

<span data-ttu-id="64c45-171">**ケース 3: 仲介サーバーおよび MTP が含まれないサードパーティ製 PBX 間の CAC**</span><span class="sxs-lookup"><span data-stu-id="64c45-171">**Case 3: CAC between the Mediation Server and a third-party PBX without MTP**</span></span>

![ケース 3: 仲介サーバーと PBX (MTP が含まれない) 間の CAC](../../media/CAC_gateways_3.jpg)

<span data-ttu-id="64c45-173">この例では、ビジネス ネットワーク サイト 1 のクライアントのユーザーは、Skype、PBX を使用してユーザーへの呼び出しを配置する場合、仲介サーバーが (ビジネス ・ クライアント ・ アプリケーションの Skype) と仲介サーバー間のプロキシの区間でのみ CAC チェックを実行します。</span><span class="sxs-lookup"><span data-stu-id="64c45-173">In this example, if a Skype for Business client user at Network Site 1 places a call to a user through the PBX, the Mediation Server is able to perform CAC checks only on the proxy leg (between the Skype for Business client application and Mediation Server).</span></span> <span data-ttu-id="64c45-174">WAN の CAC チェックを実行できないため、仲介サーバーにはエンドポイント デバイスに関する情報はありません、セッションを要求されているときに、呼び出しを確立する前に (仲介サーバーおよびサードパーティ製エンドポイント) 間のリンクです。</span><span class="sxs-lookup"><span data-stu-id="64c45-174">Because the Mediation Server does not have information about the endpoint device while the session is being requested, CAC checks cannot be performed on the WAN link (between the Mediation Server and the third-party endpoint) prior to call establishment.</span></span> <span data-ttu-id="64c45-175">セッションが確立されると、ただし、仲介サーバーはトランクで使用される帯域幅の計算で容易にします。</span><span class="sxs-lookup"><span data-stu-id="64c45-175">After the session is established, however, the Mediation Server facilitates in accounting for the bandwidth used on the trunk.</span></span>

<span data-ttu-id="64c45-176">サードパーティのエンドポイントから発信された通話にセッション要求時にそのエンドポイント デバイスに関する情報があるし、仲介サーバーの両側で CAC チェックを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="64c45-176">For calls that originate from the third-party endpoint, the information about that endpoint device is available at the time of session request and CAC check can be performed on both the sides of the Mediation Server.</span></span>

> [!NOTE]
> <span data-ttu-id="64c45-177">エンドポイント デバイスが属する IP サブネットが、確実に構成され、ネットワーク サイト 2 と関連付けられているようにしてください。</span><span class="sxs-lookup"><span data-stu-id="64c45-177">Make sure that the IP subnet that the endpoint devices belong to is configured and associated with Network Site 2.</span></span>

> [!NOTE]
> <span data-ttu-id="64c45-178">仲介サーバーの両方のインターフェイスが属する IP サブネットが構成され、ネットワーク サイト 1 に関連付けられていることを確認ください。</span><span class="sxs-lookup"><span data-stu-id="64c45-178">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span>

> [!NOTE]
> <span data-ttu-id="64c45-179">詳細については、[ネットワーク サイトとサブネットを関連付ける](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64c45-179">For details, see [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).</span></span>


