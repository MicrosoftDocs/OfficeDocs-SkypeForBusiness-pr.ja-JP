---
title: 'Lync Server 2013: 通話受付管理の概要'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of call admission control
ms:assetid: 6fda0195-4c89-4dea-82e8-624f03e3d062
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398529(v=OCS.15)
ms:contentKeyID: 48184474
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a4ad2be78d3e2af4c5b016b02e152ba0430d2a1d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034367"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="d29e2-102">Lync Server 2013 での通話受付管理の概要</span><span class="sxs-lookup"><span data-stu-id="d29e2-102">Overview of call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d29e2-103">_**トピックの最終更新日:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="d29e2-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="d29e2-104">リアルタイム コミュニケーションは、混雑したネットワークで発生しやすい遅延やパケット損失からの影響を受けやすくなっています。</span><span class="sxs-lookup"><span data-stu-id="d29e2-104">Real-time communications are sensitive to the latency and packet loss that can occur on congested networks.</span></span> <span data-ttu-id="d29e2-105">通話受付管理 (CAC) では、利用可能なネットワーク帯域幅に基づいて、音声通話やビデオ通話のようなリアルタイム通信セッションの確立を許可するかどうかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="d29e2-105">Call admission control (CAC) determines, based on available network bandwidth, whether to allow real-time communications sessions such as voice or video calls to be established.</span></span> <span data-ttu-id="d29e2-106">Lync Server 2013 の CAC 設計では、次の4つの主要な属性を提供します。</span><span class="sxs-lookup"><span data-stu-id="d29e2-106">The CAC design in Lync Server 2013 offers four main attributes:</span></span>

  - <span data-ttu-id="d29e2-107">特別に構成されたルーターなど、追加の機器を必要とせずに展開と管理を簡単に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="d29e2-107">It is simple to deploy and manage without requiring additional equipment, such as specially configured routers.</span></span>

  - <span data-ttu-id="d29e2-108">これは、ローミングユーザーや複数のプレゼンスポイントなど、重要な統合コミュニケーションのユースケースに対処します。</span><span class="sxs-lookup"><span data-stu-id="d29e2-108">It addresses critical unified communications use cases, such as roaming users and multiple points of presence.</span></span> <span data-ttu-id="d29e2-109">CAC ポリシーは、エンドポイントが配置されている場所に従って適用されます。ユーザーが所属している場所は対象外です。</span><span class="sxs-lookup"><span data-stu-id="d29e2-109">CAC policies are enforced according to where the endpoint is located, not where the user is homed.</span></span>

  - <span data-ttu-id="d29e2-110">音声通話に加えて、ビデオ通話や音声ビデオ会議セッションなどの他のトラフィックにも適用できます。</span><span class="sxs-lookup"><span data-stu-id="d29e2-110">In addition to voice calls, it can be applied to other traffic, such as video calls and audio/video conferencing sessions.</span></span>

  - <span data-ttu-id="d29e2-111">さまざまな種類のネットワークトポロジを柔軟に表現できるようにします。</span><span class="sxs-lookup"><span data-stu-id="d29e2-111">Provides the flexibility to enable representation of various kinds of network topologies.</span></span> <span data-ttu-id="d29e2-112">例については、「 [Lync Server 2013 の CAC のコンポーネントとトポロジ](lync-server-2013-components-and-topologies-for-cac.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d29e2-112">For examples, see [Components and topologies for CAC in Lync Server 2013](lync-server-2013-components-and-topologies-for-cac.md).</span></span>

<span data-ttu-id="d29e2-113">新しい音声またはビデオセッションが WAN リンクに設定した帯域幅制限を超えた場合、セッションはブロックされるか、(電話での通話に対してのみ) PSTN に再ルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="d29e2-113">If a new voice or video session exceeds the bandwidth limits that you have set on a WAN link, the session is either blocked or (for phone calls only) rerouted to the PSTN.</span></span>

<span data-ttu-id="d29e2-114">CAC は、音声とビデオのリアルタイムトラフィックのみを制御します。</span><span class="sxs-lookup"><span data-stu-id="d29e2-114">CAC controls real-time traffic for voice and video only.</span></span> <span data-ttu-id="d29e2-115">データトラフィックは制御しません。</span><span class="sxs-lookup"><span data-stu-id="d29e2-115">It does not control data traffic.</span></span>

<span data-ttu-id="d29e2-116">管理者は、すべてのフロントエンドプールと共にインストールされる帯域幅ポリシーサービスによって適用される CAC ポリシーを定義します。</span><span class="sxs-lookup"><span data-stu-id="d29e2-116">Administrators define CAC policies, which are enforced by the Bandwidth Policy Service that is installed with every Front End pool.</span></span> <span data-ttu-id="d29e2-117">CAC の設定は、ネットワーク内のすべての Lync Server フロントエンドサーバーに自動的に伝達されます。</span><span class="sxs-lookup"><span data-stu-id="d29e2-117">CAC settings are automatically propagated to all Lync Server Front End Servers in your network.</span></span>

<span data-ttu-id="d29e2-118">CAC ポリシーのために失敗した呼び出しの場合、通話を再ルーティングする優先順位は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="d29e2-118">For calls that fail because of CAC policies, the order of precedence for rerouting the call is as follows:</span></span>

1.  <span data-ttu-id="d29e2-119">インターネット</span><span class="sxs-lookup"><span data-stu-id="d29e2-119">Internet</span></span>

2.  <span data-ttu-id="d29e2-120">PSTN</span><span class="sxs-lookup"><span data-stu-id="d29e2-120">PSTN</span></span>

3.  <span data-ttu-id="d29e2-121">ボイス メール</span><span class="sxs-lookup"><span data-stu-id="d29e2-121">Voice mail</span></span>

<span data-ttu-id="d29e2-122">通話詳細記録 (CDR) PSTN またはボイスメールに再ルーティングされた通話に関する情報をキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="d29e2-122">Call detail recording (CDR) captures information about calls that are rerouted to the PSTN or to voice mail.</span></span> <span data-ttu-id="d29e2-123">CDR はインターネットに再ルーティングされた通話に関する情報を取得しません。インターネットは、2番目のオプションではなく代替パスとして扱われるためです。</span><span class="sxs-lookup"><span data-stu-id="d29e2-123">CDR does not capture information about calls that are rerouted to the Internet, because the Internet is treated as an alternate path rather than a secondary option.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d29e2-124">ボイスメールデポジットは、帯域幅制限のために拒否されません。</span><span class="sxs-lookup"><span data-stu-id="d29e2-124">Voice mail deposits will not be denied because of bandwidth constraints.</span></span>



</div>

<span data-ttu-id="d29e2-125">帯域幅ポリシーサービスでは、2種類のログファイルがコンマ区切り値 (CSV) 形式で生成されます。</span><span class="sxs-lookup"><span data-stu-id="d29e2-125">The Bandwidth Policy Service generates two types of log files in comma separated values (CSV) format.</span></span> <span data-ttu-id="d29e2-126">帯域幅要求が拒否されたときに、**チェックエラー**ログファイルに情報が取り込まれます。</span><span class="sxs-lookup"><span data-stu-id="d29e2-126">The **check failures** log file captures information when bandwidth requests are denied.</span></span> <span data-ttu-id="d29e2-127">**リンク使用状況**ログファイルは、ネットワークトポロジと WAN リンクの帯域幅の使用率のスナップショットをキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="d29e2-127">The **link utilization** log file captures a snapshot of the network topology and the WAN link bandwidth utilization.</span></span> <span data-ttu-id="d29e2-128">これらの両方のログファイルは、使用率に基づいて CAC ポリシーを微調整するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d29e2-128">Both of these log files can assist you in fine-tuning your CAC policies based on utilization.</span></span>

<div>

## <a name="call-admission-control-considerations"></a><span data-ttu-id="d29e2-129">通話受付管理に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="d29e2-129">Call Admission Control Considerations</span></span>

<span data-ttu-id="d29e2-130">管理者は、中央サイトに構成されている最初のプールに帯域幅ポリシーサービスをインストールすることを選択します。</span><span class="sxs-lookup"><span data-stu-id="d29e2-130">The administrator selects to install the Bandwidth Policy Service on the first pool configured in the central site.</span></span> <span data-ttu-id="d29e2-131">ネットワーク地域ごとに1つの中央サイトが存在するため、ネットワーク地域ごとに1つの帯域幅ポリシーサービスがあり、その地域の帯域幅ポリシー、関連付けられたサイト、およびそれらのサイトへのリンクを管理します。</span><span class="sxs-lookup"><span data-stu-id="d29e2-131">Since there is a single central site per network region, there is only one Bandwidth Policy Service per network region, which manages bandwidth policy for that region, its associated sites and the links to those sites.</span></span> <span data-ttu-id="d29e2-132">帯域幅ポリシーサービスはフロントエンドサーバーの一部として実行されるため、そのプール内に高可用性が組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="d29e2-132">The Bandwidth Policy Service runs as part of the Front End Servers, and therefore high availability is built-in within that pool.</span></span> <span data-ttu-id="d29e2-133">各フロントエンドサーバーで実行されている帯域幅ポリシーサービスは、15秒ごとに同期します。</span><span class="sxs-lookup"><span data-stu-id="d29e2-133">The Bandwidth Policy Service running on each Front End Server synchronizes every 15 seconds.</span></span> <span data-ttu-id="d29e2-134">フロントエンドプールに障害が発生した場合、フロントエンドプールとその結果として帯域幅ポリシーサービスが再び機能するまで、そのサイトに対して CAC ポリシーは適用されなくなります。</span><span class="sxs-lookup"><span data-stu-id="d29e2-134">If the Front End pool fails, CAC policies are no longer enforced for that site until the Front End pool and consequently the Bandwidth Policy Service becomes operational again.</span></span> <span data-ttu-id="d29e2-135">これは、帯域幅ポリシーサービスがサービス停止状態になるまで、すべての通話が終了することを意味します。</span><span class="sxs-lookup"><span data-stu-id="d29e2-135">This implies that all calls will go through for the duration the Bandwidth Policy Service is out of service.</span></span> <span data-ttu-id="d29e2-136">そのため、この期間中はリンクの帯域幅オーバーサブスクリプションが存在する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d29e2-136">Therefore there is the possibility of bandwidth oversubscription of your links during this period</span></span>

<span data-ttu-id="d29e2-137">帯域幅ポリシーサービスは、フロントエンドプール内に高可用性を提供します。ただし、フロントエンドプール間で冗長性は提供されません。</span><span class="sxs-lookup"><span data-stu-id="d29e2-137">The Bandwidth Policy Service provides high availability within a Front End pool; however, it does not provide redundancy across Front End pools.</span></span> <span data-ttu-id="d29e2-138">帯域幅ポリシーサービスは、1つのフロントエンドプールから別のフロントエンドプールにフェールオーバーできません。</span><span class="sxs-lookup"><span data-stu-id="d29e2-138">The Bandwidth Policy Service cannot failover from one Front End pool to another.</span></span> <span data-ttu-id="d29e2-139">フロントエンドプールへのサービスが復元されると、帯域幅ポリシーサービスが再開され、帯域幅ポリシーのチェックを再度適用することができます。</span><span class="sxs-lookup"><span data-stu-id="d29e2-139">Once service to the Front End pool is restored, the Bandwidth Policy Service is resumed and can enforce bandwidth policy checks again.</span></span>

<div>

## <a name="network-considerations"></a><span data-ttu-id="d29e2-140">ネットワークに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="d29e2-140">Network Considerations</span></span>

<span data-ttu-id="d29e2-141">オーディオおよびビデオの帯域幅制限は、Lync Server 2013 の帯域幅ポリシーサービスによって適用されますが、この制限はネットワークルーター (レイヤー2および 3) では適用されません。</span><span class="sxs-lookup"><span data-stu-id="d29e2-141">Although bandwidth restriction for audio and video is enforced by the Bandwidth Policy Service in Lync Server 2013, this restriction is not enforced at the network router (layer 2 and 3).</span></span> <span data-ttu-id="d29e2-142">Lync Server 2010 CAC は、データアプリケーションを阻止できません。たとえば、CAC ポリシーによって音声およびビデオに予約されている帯域幅を含む、WAN リンク上のネットワーク帯域幅全体を消費することがあります。</span><span class="sxs-lookup"><span data-stu-id="d29e2-142">Lync Server 2010 CAC cannot prevent a data application, for example, from consuming the entire network bandwidth on a WAN link, including the bandwidth that is reserved for audio and video by your CAC policy.</span></span> <span data-ttu-id="d29e2-143">ネットワーク上で必要な帯域幅を保護するために、差別化サービス (DiffServ) などのサービスの品質 (QoS) プロトコルを展開することができます。</span><span class="sxs-lookup"><span data-stu-id="d29e2-143">To protect the necessary bandwidth on your network, you can deploy a Quality of Service (QoS) protocol such as Differentiated Services (DiffServ).</span></span> <span data-ttu-id="d29e2-144">そのため、定義する CAC 帯域幅ポリシーを、展開する可能性のある QoS 設定で調整することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d29e2-144">Therefore, a best practice is to coordinate the CAC bandwidth policies you define with any QoS settings that you might deploy.</span></span>

</div>

<div>

## <a name="media-and-signaling-paths-over-vpn"></a><span data-ttu-id="d29e2-145">VPN 経由のメディアと信号パス</span><span class="sxs-lookup"><span data-stu-id="d29e2-145">Media and Signaling Paths over VPN</span></span>

<span data-ttu-id="d29e2-146">エンタープライズが VPN 経由のメディアをサポートしている場合は、メディアストリームと信号ストリームの両方が VPN 経由で送信されるか、両方がインターネット経由でルーティングされるかを確認します。</span><span class="sxs-lookup"><span data-stu-id="d29e2-146">If your enterprise supports media through VPN, ensure that either both the media stream and the signaling stream go through the VPN or both are routed through the internet.</span></span> <span data-ttu-id="d29e2-147">既定では、メディアと信号ストリームは VPN トンネルを経由します。</span><span class="sxs-lookup"><span data-stu-id="d29e2-147">By default, the media and signaling streams go through the VPN tunnel.</span></span>

</div>

<div>

## <a name="call-admission-control-of-outside-users"></a><span data-ttu-id="d29e2-148">外部ユーザーの通話受付管理</span><span class="sxs-lookup"><span data-stu-id="d29e2-148">Call Admission Control of Outside Users</span></span>

<span data-ttu-id="d29e2-149">ネットワークトラフィックがインターネットを通過するリモートユーザーには、通話受付管理が強制されません。</span><span class="sxs-lookup"><span data-stu-id="d29e2-149">Call admission control is not enforced for remote users where the network traffic flows through the Internet.</span></span> <span data-ttu-id="d29e2-150">メディアトラフィックは、Lync Server で管理されていないインターネットをスキャンするため、CAC を適用することはできません。</span><span class="sxs-lookup"><span data-stu-id="d29e2-150">Because the media traffic is traversing the Internet, which is not managed by Lync Server, CAC cannot be applied.</span></span> <span data-ttu-id="d29e2-151">ただし、CAC のチェックは、エンタープライズネットワークを経由する呼び出しの部分で実行されます。</span><span class="sxs-lookup"><span data-stu-id="d29e2-151">CAC checks will be performed, however, on the portion of the call that flows through the enterprise network.</span></span>

</div>

<div>

## <a name="call-admission-control-of-pstn-connections"></a><span data-ttu-id="d29e2-152">PSTN 接続の通話受付管理</span><span class="sxs-lookup"><span data-stu-id="d29e2-152">Call Admission Control of PSTN Connections</span></span>

<span data-ttu-id="d29e2-153">IP/PBX、PSTN ゲートウェイ、または SIP トランクに接続されているかどうかに関係なく、仲介サーバーで通話受付管理が可能です。</span><span class="sxs-lookup"><span data-stu-id="d29e2-153">Call admission control is enforceable on the Mediation Server regardless of whether it is connected to an IP/PBX, a PSTN gateway, or a SIP trunk.</span></span> <span data-ttu-id="d29e2-154">仲介サーバーはバックツーバックのユーザーエージェント (B2BUA) なので、メディアを終了します。</span><span class="sxs-lookup"><span data-stu-id="d29e2-154">Because the Mediation Server is a back-to-back user agent (B2BUA), it terminates media.</span></span> <span data-ttu-id="d29e2-155">これには2つの接続側があります。つまり、Lync Server に接続されているサイドと、PSTN ゲートウェイ、IP/Pbx、または SIP トランクに接続されているゲートウェイ側があります。</span><span class="sxs-lookup"><span data-stu-id="d29e2-155">It has two connection sides: a side that is connected to Lync Server and a gateway side, which is connected to PSTN gateways, IP/PBXs, or SIP trunks.</span></span> <span data-ttu-id="d29e2-156">PSTN 接続の詳細については、「 [Lync Server 2013 での pstn 接続の計画](lync-server-2013-planning-for-pstn-connectivity.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d29e2-156">For details about PSTN connections, see [Planning for PSTN connectivity in Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md).</span></span>

<span data-ttu-id="d29e2-157">メディアバイパスが有効になっていない場合は、仲介サーバーの両側に CAC を適用できます。</span><span class="sxs-lookup"><span data-stu-id="d29e2-157">CAC can be enforced on both sides of the Mediation Server unless media bypass is enabled.</span></span> <span data-ttu-id="d29e2-158">メディアバイパスが有効になっている場合、メディアトラフィックは仲介サーバーを通過しませんが、代わりに Lync クライアントとゲートウェイの間で直接フローします。</span><span class="sxs-lookup"><span data-stu-id="d29e2-158">If media bypass is enabled, the media traffic doesn’t traverse the Mediation Server but instead flows directly between the Lync client and the gateway.</span></span> <span data-ttu-id="d29e2-159">この場合、CAC は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="d29e2-159">In this case, CAC is not needed.</span></span> <span data-ttu-id="d29e2-160">詳細については、「 [Lync Server 2013 でのメディアバイパスの計画](lync-server-2013-planning-for-media-bypass.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d29e2-160">For details, see [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md).</span></span>

<span data-ttu-id="d29e2-161">次の図は、メディアバイパスが有効であるかどうかにかかわらず、PSTN 接続での CAC の適用方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="d29e2-161">The following figure illustrates how CAC is enforced on PSTN connections with and without media bypass enabled.</span></span>

<span data-ttu-id="d29e2-162">**PSTN への接続に対する通話受付管理の適用**</span><span class="sxs-lookup"><span data-stu-id="d29e2-162">**Call admission control enforcement on connections to the PSTN**</span></span>

<span data-ttu-id="d29e2-163">![音声 CAC メディアバイパス接続の強制](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "音声 CAC メディアバイパス接続の強制")</span><span class="sxs-lookup"><span data-stu-id="d29e2-163">![Voice CAC Media Bypass Connection Enforcement](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "Voice CAC Media Bypass Connection Enforcement")</span></span>

</div>

<div>

## <a name="compatibility-of-call-admission-control-with-earlier-versions-of-office-communications-server"></a><span data-ttu-id="d29e2-164">以前のバージョンの Office Communications Server との通話受付管理の互換性</span><span class="sxs-lookup"><span data-stu-id="d29e2-164">Compatibility of Call Admission Control with Earlier Versions of Office Communications Server</span></span>

<span data-ttu-id="d29e2-165">通話受付管理は、Lync Server 2010 以降で有効になっているエンドポイントでのみ有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="d29e2-165">Call admission control can be enabled only on endpoints that are enabled for Lync Server 2010 and later.</span></span>

<span data-ttu-id="d29e2-166">Office Communicator 2007 R2 以前を実行しているエンドポイントでは、通話受付管理を有効にできません。</span><span class="sxs-lookup"><span data-stu-id="d29e2-166">Call admission control cannot be enabled on endpoints running Office Communicator 2007 R2 or earlier.</span></span>

<span data-ttu-id="d29e2-167">**さまざまな Lync Server バージョンでの CAC の適用**</span><span class="sxs-lookup"><span data-stu-id="d29e2-167">**Application of CAC on different Lync Server versions**</span></span>

<span data-ttu-id="d29e2-168">![音声 CAC バージョン比較図](images/Gg398529.fdbfee7e-15fc-445b-949d-8d61e61ac350(OCS.15).jpg "音声 CAC バージョン比較図")</span><span class="sxs-lookup"><span data-stu-id="d29e2-168">![Voice CAC Version Comparison diagram](images/Gg398529.fdbfee7e-15fc-445b-949d-8d61e61ac350(OCS.15).jpg "Voice CAC Version Comparison diagram")</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

