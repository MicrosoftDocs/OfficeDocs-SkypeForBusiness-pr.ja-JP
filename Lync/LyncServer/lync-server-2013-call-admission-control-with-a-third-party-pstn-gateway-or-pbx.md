---
title: サードパーティの PSTN ゲートウェイまたは PBX での通話受付管理
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call admission control with a third-party PSTN gateway or PBX
ms:assetid: 95dc4ceb-bcad-48ee-86ec-af911727f853
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398762(v=OCS.15)
ms:contentKeyID: 48184850
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 09aae207844fed12c840918a533fb181ca36634e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743177"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-in-lync-server-2013-with-a-third-party-pstn-gateway-or-pbx"></a><span data-ttu-id="02d2f-102">サードパーティの PSTN ゲートウェイまたは PBX での Lync Server 2013 における通話受付管理</span><span class="sxs-lookup"><span data-stu-id="02d2f-102">Call admission control in Lync Server 2013 with a third-party PSTN gateway or PBX</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="02d2f-103">_**最終更新日:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="02d2f-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="02d2f-104">このトピックでは、仲介サーバーのゲートウェイ インターフェイス、およびサードパーティの公衆交換電話網 (PSTN) ゲートウェイまたは構内交換機 (PBX) の間のリンクに、どのように通話受付管理 (CAC) を配置することができるのかという例を説明します。</span><span class="sxs-lookup"><span data-stu-id="02d2f-104">This topic describes examples of how call admission control (CAC) can be deployed on the link between the Mediation Server’s gateway interface and a third-party public switched telephone network (PSTN) gateway or private branch exchange (PBX).</span></span>

<div>

## <a name="case-1-cac-between-the-mediation-server-and-a-pstn-gateway"></a><span data-ttu-id="02d2f-105">ケース 1: 仲介サーバーおよび PSTN ゲートウェイ間の CAC</span><span class="sxs-lookup"><span data-stu-id="02d2f-105">Case 1: CAC between the Mediation Server and a PSTN gateway</span></span>

<span data-ttu-id="02d2f-106">CAC は、仲介サーバーのゲートウェイ インターフェイスから、サードパーティの PBX または PSTN ゲートウェイへの WAN リンクに展開させることができます。</span><span class="sxs-lookup"><span data-stu-id="02d2f-106">CAC can be deployed on the WAN link from the Mediation Server’s gateway interface to a third-party PBX or PSTN gateway.</span></span>

<span data-ttu-id="02d2f-107">**ケース 1: 仲介サーバーおよび PSTN ゲートウェイ間の CAC**</span><span class="sxs-lookup"><span data-stu-id="02d2f-107">**Case 1: CAC between the Mediation Server and a PSTN gateway**</span></span>

<span data-ttu-id="02d2f-108">![ケース 1: 仲介サーバーと PSTN ゲートウェイ間の CAC](images/Gg398762.4bebf9ee-2732-4ea6-bbe5-0269b2903d8c(OCS.15).jpg "ケース 1: 仲介サーバーと PSTN ゲートウェイ間の CAC")</span><span class="sxs-lookup"><span data-stu-id="02d2f-108">![Case 1: CAC between Mediation Server PSTN Gateway](images/Gg398762.4bebf9ee-2732-4ea6-bbe5-0269b2903d8c(OCS.15).jpg "Case 1: CAC between Mediation Server PSTN Gateway")</span></span>

<span data-ttu-id="02d2f-109">この例では、仲介サーバーと PSTN ゲートウェイの間で CAC が適用されています。</span><span class="sxs-lookup"><span data-stu-id="02d2f-109">In this example, CAC is applied between the Mediation Server and a PSTN gateway.</span></span> <span data-ttu-id="02d2f-110">ネットワークサイト1の Lync クライアントユーザーが、ネットワークサイト2の PSTN ゲートウェイ経由で PSTN 通話を発信した場合、メディアは WAN リンクを通じて流れることになります。</span><span class="sxs-lookup"><span data-stu-id="02d2f-110">If a Lync client user at Network Site 1 places a PSTN call through the PSTN gateway in Network Site 2, the media flows through the WAN link.</span></span> <span data-ttu-id="02d2f-111">そのため、PSTN セッションごとに 2 度の CAC チェックが行われます。</span><span class="sxs-lookup"><span data-stu-id="02d2f-111">Therefore, two CAC checks are performed for each PSTN session:</span></span>

  - <span data-ttu-id="02d2f-112">Lync クライアントアプリケーションと仲介サーバーの間</span><span class="sxs-lookup"><span data-stu-id="02d2f-112">Between the Lync client application and the Mediation Server</span></span>

  - <span data-ttu-id="02d2f-113">仲介サーバーと PSTN ゲートウェイの間</span><span class="sxs-lookup"><span data-stu-id="02d2f-113">Between the Mediation Server and the PSTN gateway</span></span>

<span data-ttu-id="02d2f-114">これは、ネットワーク サイト 1 のクライアントへの PSTN 着信、およびネットワーク サイト 1 のクライアント アプリケーションからの PSTN 発信のどちらでも行われます。</span><span class="sxs-lookup"><span data-stu-id="02d2f-114">This works for both incoming PSTN calls to a client in Network Site 1, and for outgoing PSTN calls originating from a client application in Network Site 1.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="02d2f-115">PSTN ゲートウェイが属する IP サブネットが、確実に構成され、ネットワーク サイト 2 と関連付けられているようにしてください。</span><span class="sxs-lookup"><span data-stu-id="02d2f-115">Make sure that the IP subnet that the PSTN gateway belongs to is configured and associated with Network Site 2.</span></span><BR><span data-ttu-id="02d2f-116">仲介サーバーの両方のインターフェイスが所属する IP サブネットが構成されていて、ネットワークサイト1に関連付けられていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="02d2f-116">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span><BR><span data-ttu-id="02d2f-117">詳細については、「 <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Lync Server 2013 でサブネットとネットワークサイトを関連付ける</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02d2f-117">For details, see <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Associate a subnet with a network site in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="case-2-cac-between-the-mediation-server-and-a-third-party-pbx-with-media-termination-point"></a><span data-ttu-id="02d2f-118">ケース 2: 仲介サーバーとサードパーティ PBX との間の CAC でメディア終了ポイントが使用される</span><span class="sxs-lookup"><span data-stu-id="02d2f-118">Case 2: CAC between the Mediation Server and a third-party PBX with Media Termination Point</span></span>

<span data-ttu-id="02d2f-119">この構成はケース 1 に類似したものです。</span><span class="sxs-lookup"><span data-stu-id="02d2f-119">This configuration is similar to Case 1.</span></span> <span data-ttu-id="02d2f-120">どちらの場合も、仲介サーバーは、WAN リンクの反対側でメディアを終了させるデバイスを認識します。また、PSTN ゲートウェイまたは PBX の IP アドレスは、仲介サーバー上で次ホップとして構成されています。</span><span class="sxs-lookup"><span data-stu-id="02d2f-120">In both the cases, the Mediation Server knows what device terminates media at the opposite end of the WAN link, and the IP address of the PSTN gateway or PBX with Media Termination Point (MTP) is configured on the Mediation Server as the next hop.</span></span>

<span data-ttu-id="02d2f-121">**ケース 2: 仲介サーバーおよび MTP を含むサードパーティ製 PBX 間の CAC**</span><span class="sxs-lookup"><span data-stu-id="02d2f-121">**Case 2: CAC between the Mediation Server and a third-party PBX with MTP**</span></span>

<span data-ttu-id="02d2f-122">![ケース 2: 仲介サーバーと PBX (MTP が含まれる) 間の CAC](images/Gg398762.1c0b5263-c053-4cca-842f-85dd670760c8(OCS.15).jpg "ケース 2: 仲介サーバーと PBX (MTP が含まれる) 間の CAC")</span><span class="sxs-lookup"><span data-stu-id="02d2f-122">![Case 2: CAC between Mediation Server PBX with MTP](images/Gg398762.1c0b5263-c053-4cca-842f-85dd670760c8(OCS.15).jpg "Case 2: CAC between Mediation Server PBX with MTP")</span></span>

<span data-ttu-id="02d2f-123">この例では、仲介サーバーと PBX/MTP の間で CAC が適用されています。</span><span class="sxs-lookup"><span data-stu-id="02d2f-123">In this example, CAC is applied between the Mediation Server and the PBX/MTP.</span></span> <span data-ttu-id="02d2f-124">ネットワークサイト1の Lync クライアントユーザーが、ネットワークサイト2にある PBX/MTP 経由で PSTN 通話を発信した場合、メディアは WAN リンクを通じて流れることになります。</span><span class="sxs-lookup"><span data-stu-id="02d2f-124">If a Lync client user at the Network Site 1 places a PSTN call through the PBX/MTP located in Network Site 2, the media flows through the WAN link.</span></span> <span data-ttu-id="02d2f-125">そのため、それぞれの PSTN セッションごとに 2 度の CAC チェックが行われます。</span><span class="sxs-lookup"><span data-stu-id="02d2f-125">Therefore, for each PSTN session two CAC checks are performed:</span></span>

  - <span data-ttu-id="02d2f-126">Lync クライアントアプリケーションと仲介サーバーの間</span><span class="sxs-lookup"><span data-stu-id="02d2f-126">Between the Lync client application and the Mediation Server</span></span>

  - <span data-ttu-id="02d2f-127">仲介サーバーと PBX/MTP の間</span><span class="sxs-lookup"><span data-stu-id="02d2f-127">Between the Mediation Server and the PBX/MTP</span></span>

<span data-ttu-id="02d2f-128">これは、ネットワーク サイト 1 のクライアントへの PSTN 着信、およびネットワーク サイト 1 のクライアントからの PSTN 発信のどちらでも行われます。</span><span class="sxs-lookup"><span data-stu-id="02d2f-128">This works for both incoming PSTN calls to a client in Network Site 1, and outgoing PSTN calls originating from a client in Network Site 1.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="02d2f-129">MTP が属する IP サブネットが、確実に構成され、ネットワーク サイト 2 と関連付けられているようにしてください。</span><span class="sxs-lookup"><span data-stu-id="02d2f-129">Make sure that the IP subnet that the MTP belongs to is configured and associated with Network Site 2.</span></span><BR><span data-ttu-id="02d2f-130">仲介サーバーの両方のインターフェイスが所属する IP サブネットが構成されていて、ネットワークサイト1に関連付けられていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="02d2f-130">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span><BR><span data-ttu-id="02d2f-131">詳細については、「 <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Lync Server 2013 でサブネットとネットワークサイトを関連付ける</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02d2f-131">For details, see <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Associate a subnet with a network site in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="case-3-cac-between-the-mediation-server-and-a-third-party-pbx-without-a-media-termination-point"></a><span data-ttu-id="02d2f-132">ケース 3: メディア終了ポイントのない仲介サーバーとサードパーティ PBX 間の CAC</span><span class="sxs-lookup"><span data-stu-id="02d2f-132">Case 3: CAC between the Mediation Server and a third-party PBX without a Media Termination Point</span></span>

<span data-ttu-id="02d2f-133">ケース 3 は、最初の 2 つのケースとは少し異なります。</span><span class="sxs-lookup"><span data-stu-id="02d2f-133">Case 3 is slightly different from the first two cases.</span></span> <span data-ttu-id="02d2f-134">サードパーティ PBX 上に MTP がない場合、サードパーティ PBX への送信セッション要求については、仲介サーバーが PBX 境界でメディアを終了させる場所を把握していません。</span><span class="sxs-lookup"><span data-stu-id="02d2f-134">If there is no MTP on the third-party PBX, for an outgoing session request to the third-party PBX the Mediation Server does not know where media will terminate in the PBX boundary.</span></span> <span data-ttu-id="02d2f-135">この場合、メディアは、仲介サーバーとサードパーティエンドポイントデバイスの間で直接フローします。</span><span class="sxs-lookup"><span data-stu-id="02d2f-135">In this case, the media flows directly between the Mediation Server and the third-party endpoint device.</span></span>

<span data-ttu-id="02d2f-136">**ケース 3: 仲介サーバーおよび MTP が含まれないサードパーティ製 PBX 間の CAC**</span><span class="sxs-lookup"><span data-stu-id="02d2f-136">**Case 3: CAC between the Mediation Server and a third-party PBX without MTP**</span></span>

<span data-ttu-id="02d2f-137">![ケース 3: 仲介サーバーと PBX (MTP が含まれない) 間の CAC](images/Gg398762.f4bcf800-3a68-4037-bb3f-adb2fdf50d32(OCS.15).jpg "ケース 3: 仲介サーバーと PBX (MTP が含まれない) 間の CAC")</span><span class="sxs-lookup"><span data-stu-id="02d2f-137">![Case 3: CAC between Mediation Server PBX no MTP](images/Gg398762.f4bcf800-3a68-4037-bb3f-adb2fdf50d32(OCS.15).jpg "Case 3: CAC between Mediation Server PBX no MTP")</span></span>

<span data-ttu-id="02d2f-138">この例では、ネットワークサイト1の Lync クライアントユーザーが PBX を通じてユーザーに通話を発信した場合、仲介サーバーはプロキシレグ上 (Lync クライアントアプリケーションと仲介サーバーの間) でのみ CAC チェックを実行できます。</span><span class="sxs-lookup"><span data-stu-id="02d2f-138">In this example, if a Lync client user at Network Site 1 places a call to a user through the PBX, the Mediation Server is able to perform CAC checks only on the proxy leg (between the Lync client application and Mediation Server).</span></span> <span data-ttu-id="02d2f-139">仲介サーバーには、セッションが要求されている間、エンドポイントデバイスに関する情報が含まれていないため、発信する前に、(仲介サーバーとサードパーティのエンドポイント間の) WAN リンクで CAC チェックを実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="02d2f-139">Because the Mediation Server does not have information about the endpoint device while the session is being requested, CAC checks cannot be performed on the WAN link (between the Mediation Server and the third-party endpoint) prior to call establishment.</span></span> <span data-ttu-id="02d2f-140">ただし、セッションが確立されると、仲介サーバーによって、トランクで使用される帯域幅のアカウンティングが容易になります。</span><span class="sxs-lookup"><span data-stu-id="02d2f-140">After the session is established, however, the Mediation Server facilitates in accounting for the bandwidth used on the trunk.</span></span>

<span data-ttu-id="02d2f-141">サードパーティのエンドポイントから発信された通話の場合、そのエンドポイントデバイスに関する情報はセッション要求の時点で利用できます。 CAC のチェックは、仲介サーバーの両方の側で実行できます。</span><span class="sxs-lookup"><span data-stu-id="02d2f-141">For calls that originate from the third-party endpoint, the information about that endpoint device is available at the time of session request and CAC check can be performed on both the sides of the Mediation Server.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="02d2f-142">エンドポイント デバイスが属する IP サブネットが、確実に構成され、ネットワーク サイト 2 と関連付けられているようにしてください。</span><span class="sxs-lookup"><span data-stu-id="02d2f-142">Make sure that the IP subnet that the endpoint devices belong to is configured and associated with Network Site 2.</span></span><BR><span data-ttu-id="02d2f-143">仲介サーバーの両方のインターフェイスが所属する IP サブネットが構成されていて、ネットワークサイト1に関連付けられていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="02d2f-143">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span><BR><span data-ttu-id="02d2f-144">詳細については、「 <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Lync Server 2013 でサブネットとネットワークサイトを関連付ける</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02d2f-144">For details, see <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Associate a subnet with a network site in Lync Server 2013</A>.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

