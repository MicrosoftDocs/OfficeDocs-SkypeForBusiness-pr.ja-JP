---
title: 'Lync Server 2013: 通話受付制御の概要'
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
ms.openlocfilehash: f5b38fbb1ae1e209e5b5332e896d806d1ca24975
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755621"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="b7c42-102">Lync Server 2013 の通話受付制御の概要</span><span class="sxs-lookup"><span data-stu-id="b7c42-102">Overview of call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b7c42-103">_**最終更新日:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="b7c42-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="b7c42-104">リアルタイム通信は、混雑したネットワークで発生する可能性のある待ち時間とパケット損失に敏感に対応します。</span><span class="sxs-lookup"><span data-stu-id="b7c42-104">Real-time communications are sensitive to the latency and packet loss that can occur on congested networks.</span></span> <span data-ttu-id="b7c42-105">通話受付管理 (CAC) では、利用可能なネットワーク帯域幅に基づいて、音声通話やビデオ通話などのリアルタイム コミュニケーションのセッションの確立を許可するかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="b7c42-105">Call admission control (CAC) determines, based on available network bandwidth, whether to allow real-time communications sessions such as voice or video calls to be established.</span></span> <span data-ttu-id="b7c42-106">Lync Server 2013 での CAC 設計では、次の4つの主要な属性が提供されます。</span><span class="sxs-lookup"><span data-stu-id="b7c42-106">The CAC design in Lync Server 2013 offers four main attributes:</span></span>

  - <span data-ttu-id="b7c42-107">展開と管理が簡単であり、特別に構成されたルーターなど、追加の機器は不要です。</span><span class="sxs-lookup"><span data-stu-id="b7c42-107">It is simple to deploy and manage without requiring additional equipment, such as specially configured routers.</span></span>

  - <span data-ttu-id="b7c42-p102">移動ユーザーや複数の Multiple Point of Presence など、ユニファイド コミュニケーションの重要なユース ケースに対処します。CAC ポリシーは、ユーザーが所属する場所ではなく、エンドポイントが配置されている場所に基づいて適用されます。</span><span class="sxs-lookup"><span data-stu-id="b7c42-p102">It addresses critical unified communications use cases, such as roaming users and multiple points of presence. CAC policies are enforced according to where the endpoint is located, not where the user is homed.</span></span>

  - <span data-ttu-id="b7c42-110">音声通話に加えて、ビデオ通話や音声ビデオ会議セッションなどの、他のトラフィックにも適用できます。</span><span class="sxs-lookup"><span data-stu-id="b7c42-110">In addition to voice calls, it can be applied to other traffic, such as video calls and audio/video conferencing sessions.</span></span>

  - <span data-ttu-id="b7c42-111">各種のネットワーク トポロジを柔軟に表示できます。</span><span class="sxs-lookup"><span data-stu-id="b7c42-111">Provides the flexibility to enable representation of various kinds of network topologies.</span></span> <span data-ttu-id="b7c42-112">例については、「 [Lync Server 2013 での CAC のコンポーネントとトポロジ](lync-server-2013-components-and-topologies-for-cac.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b7c42-112">For examples, see [Components and topologies for CAC in Lync Server 2013](lync-server-2013-components-and-topologies-for-cac.md).</span></span>

<span data-ttu-id="b7c42-113">新しい音声セッションまたはビデオ セッションが WAN リンクに設定されている帯域幅制限を超えた場合、セッションはブロックされるか、(電話での通話のみ) PSTN に再ルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="b7c42-113">If a new voice or video session exceeds the bandwidth limits that you have set on a WAN link, the session is either blocked or (for phone calls only) rerouted to the PSTN.</span></span>

<span data-ttu-id="b7c42-p104">CAC では、音声とビデオのリアルタイムのトラフィックのみ制御します。データ トラフィックは制御しません。</span><span class="sxs-lookup"><span data-stu-id="b7c42-p104">CAC controls real-time traffic for voice and video only. It does not control data traffic.</span></span>

<span data-ttu-id="b7c42-116">管理者は、各フロントエンドプールと共にインストールされる帯域幅ポリシーサービスによって適用される CAC ポリシーを定義します。</span><span class="sxs-lookup"><span data-stu-id="b7c42-116">Administrators define CAC policies, which are enforced by the Bandwidth Policy Service that is installed with every Front End pool.</span></span> <span data-ttu-id="b7c42-117">CAC の設定は、ネットワーク内のすべての Lync Server フロントエンドサーバーに自動的に伝達されます。</span><span class="sxs-lookup"><span data-stu-id="b7c42-117">CAC settings are automatically propagated to all Lync Server Front End Servers in your network.</span></span>

<span data-ttu-id="b7c42-118">CAC ポリシーのために失敗した通話では、通話を再ルーティングする優先順位は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="b7c42-118">For calls that fail because of CAC policies, the order of precedence for rerouting the call is as follows:</span></span>

1.  <span data-ttu-id="b7c42-119">インターネット</span><span class="sxs-lookup"><span data-stu-id="b7c42-119">Internet</span></span>

2.  <span data-ttu-id="b7c42-120">PSTN</span><span class="sxs-lookup"><span data-stu-id="b7c42-120">PSTN</span></span>

3.  <span data-ttu-id="b7c42-121">ボイス メール</span><span class="sxs-lookup"><span data-stu-id="b7c42-121">Voice mail</span></span>

<span data-ttu-id="b7c42-p106">通話詳細記録 (CDR) では、PSTN またはボイス メールに再ルーティングされた通話に関する情報を収集します。 CDR では、インターネットは 2 番目のオプションではなく代替パスとして扱われるため、インターネットに再ルーティングされた通話に関する情報は収集されません。</span><span class="sxs-lookup"><span data-stu-id="b7c42-p106">Call detail recording (CDR) captures information about calls that are rerouted to the PSTN or to voice mail. CDR does not capture information about calls that are rerouted to the Internet, because the Internet is treated as an alternate path rather than a secondary option.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b7c42-124">ボイス メール デポジットは、帯域幅制限のために拒否されることはありません。</span><span class="sxs-lookup"><span data-stu-id="b7c42-124">Voice mail deposits will not be denied because of bandwidth constraints.</span></span>



</div>

<span data-ttu-id="b7c42-p107">帯域幅ポリシー サービスは、CSV (コンマ区切り値) 形式で 2 種類のログ ファイルを生成します。[**チェックの失敗**] ログ ファイルには、帯域幅要求が拒否されたときの情報が収集されます。 [**リンクの使用率**] ログ ファイルには、ネットワーク トポロジのスナップショットと WAN リンクの帯域幅使用率が収集されます。これらの両方のログ ファイルは、使用率に基づいて CAC ポリシーを細かく調整するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="b7c42-p107">The Bandwidth Policy Service generates two types of log files in comma separated values (CSV) format. The **check failures** log file captures information when bandwidth requests are denied. The **link utilization** log file captures a snapshot of the network topology and the WAN link bandwidth utilization. Both of these log files can assist you in fine-tuning your CAC policies based on utilization.</span></span>

<div>

## <a name="call-admission-control-considerations"></a><span data-ttu-id="b7c42-129">通話受付管理に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="b7c42-129">Call Admission Control Considerations</span></span>

<span data-ttu-id="b7c42-130">管理者は、セントラルサイトで構成されている最初のプールに帯域幅ポリシーサービスをインストールすることを選択します。</span><span class="sxs-lookup"><span data-stu-id="b7c42-130">The administrator selects to install the Bandwidth Policy Service on the first pool configured in the central site.</span></span> <span data-ttu-id="b7c42-131">ネットワーク領域ごとに1つのセントラルサイトがあるため、1つのネットワーク地域につき1つの帯域幅ポリシーサービスしかありません。このサービスは、その地域の帯域幅ポリシー、関連サイト、それらのサイトへのリンクを管理します。</span><span class="sxs-lookup"><span data-stu-id="b7c42-131">Since there is a single central site per network region, there is only one Bandwidth Policy Service per network region, which manages bandwidth policy for that region, its associated sites and the links to those sites.</span></span> <span data-ttu-id="b7c42-132">帯域幅ポリシーサービスはフロントエンドサーバーの一部として実行されるため、高可用性はそのプール内に組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="b7c42-132">The Bandwidth Policy Service runs as part of the Front End Servers, and therefore high availability is built-in within that pool.</span></span> <span data-ttu-id="b7c42-133">各フロントエンドサーバー上で実行されている帯域幅ポリシーサービスは、15秒ごとに同期されます。</span><span class="sxs-lookup"><span data-stu-id="b7c42-133">The Bandwidth Policy Service running on each Front End Server synchronizes every 15 seconds.</span></span> <span data-ttu-id="b7c42-134">フロントエンドプールに障害が発生した場合、そのサイトに対して CAC ポリシーは適用されません。これは、フロントエンドプールとその結果、帯域幅ポリシーサービスが再び動作することになります。</span><span class="sxs-lookup"><span data-stu-id="b7c42-134">If the Front End pool fails, CAC policies are no longer enforced for that site until the Front End pool and consequently the Bandwidth Policy Service becomes operational again.</span></span> <span data-ttu-id="b7c42-135">これは、帯域幅ポリシーサービスが機能しなくなるまで、すべての通話が継続することを意味します。</span><span class="sxs-lookup"><span data-stu-id="b7c42-135">This implies that all calls will go through for the duration the Bandwidth Policy Service is out of service.</span></span> <span data-ttu-id="b7c42-136">そのため、この期間中、お客さまのリンクの帯域幅オーバーサブスクリプションの可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b7c42-136">Therefore there is the possibility of bandwidth oversubscription of your links during this period</span></span>

<span data-ttu-id="b7c42-137">帯域幅ポリシーサービスは、フロントエンドプール内で高可用性を実現します。ただし、フロントエンドプール間の冗長性は提供しません。</span><span class="sxs-lookup"><span data-stu-id="b7c42-137">The Bandwidth Policy Service provides high availability within a Front End pool; however, it does not provide redundancy across Front End pools.</span></span> <span data-ttu-id="b7c42-138">帯域幅ポリシーサービスは、1つのフロントエンドプールへのフェールオーバーを行うことができません。</span><span class="sxs-lookup"><span data-stu-id="b7c42-138">The Bandwidth Policy Service cannot failover from one Front End pool to another.</span></span> <span data-ttu-id="b7c42-139">フロントエンドプールへのサービスが復元されると、帯域幅ポリシーサービスは再開され、帯域幅ポリシーのチェックをもう一度適用することができます。</span><span class="sxs-lookup"><span data-stu-id="b7c42-139">Once service to the Front End pool is restored, the Bandwidth Policy Service is resumed and can enforce bandwidth policy checks again.</span></span>

<div>

## <a name="network-considerations"></a><span data-ttu-id="b7c42-140">ネットワークに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="b7c42-140">Network Considerations</span></span>

<span data-ttu-id="b7c42-141">オーディオおよびビデオの帯域幅制限は、Lync Server 2013 の帯域幅ポリシーサービスによって適用されますが、この制限はネットワークルーター (レイヤー2と 3) では適用されません。</span><span class="sxs-lookup"><span data-stu-id="b7c42-141">Although bandwidth restriction for audio and video is enforced by the Bandwidth Policy Service in Lync Server 2013, this restriction is not enforced at the network router (layer 2 and 3).</span></span> <span data-ttu-id="b7c42-142">Lync Server 2010 の CAC では、データアプリケーション (たとえば、CAC ポリシーによってオーディオとビデオのために予約されている帯域幅を含む) を使用して、WAN リンク上のネットワーク帯域幅全体を消費することはできません。</span><span class="sxs-lookup"><span data-stu-id="b7c42-142">Lync Server 2010 CAC cannot prevent a data application, for example, from consuming the entire network bandwidth on a WAN link, including the bandwidth that is reserved for audio and video by your CAC policy.</span></span> <span data-ttu-id="b7c42-143">ネットワーク上の必要な帯域幅を保護するために、Differentiated Services (DiffServ) などのサービスの品質 (QoS) プロトコルを展開できます。</span><span class="sxs-lookup"><span data-stu-id="b7c42-143">To protect the necessary bandwidth on your network, you can deploy a Quality of Service (QoS) protocol such as Differentiated Services (DiffServ).</span></span> <span data-ttu-id="b7c42-144">そのため、定義する CAC 帯域幅ポリシーと展開する QoS 設定を調整することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b7c42-144">Therefore, a best practice is to coordinate the CAC bandwidth policies you define with any QoS settings that you might deploy.</span></span>

</div>

<div>

## <a name="media-and-signaling-paths-over-vpn"></a><span data-ttu-id="b7c42-145">VPN 経由のメディア パスと信号パス</span><span class="sxs-lookup"><span data-stu-id="b7c42-145">Media and Signaling Paths over VPN</span></span>

<span data-ttu-id="b7c42-p111">企業が VPN 経由のメディアをサポートする場合、メディア ストリームと信号ストリームの両方が VPN を通過するのか、または両方がインターネット経由でルーティングされるのかを確認します。 既定では、メディア ストリームと信号ストリームは VPN トンネルを通過します。</span><span class="sxs-lookup"><span data-stu-id="b7c42-p111">If your enterprise supports media through VPN, ensure that either both the media stream and the signaling stream go through the VPN or both are routed through the internet. By default, the media and signaling streams go through the VPN tunnel.</span></span>

</div>

<div>

## <a name="call-admission-control-of-outside-users"></a><span data-ttu-id="b7c42-148">外部ユーザーの通話受付管理</span><span class="sxs-lookup"><span data-stu-id="b7c42-148">Call Admission Control of Outside Users</span></span>

<span data-ttu-id="b7c42-149">通話受付制御は、ネットワークトラフィックがインターネット経由で流れるリモートユーザーに対しては強制されません。</span><span class="sxs-lookup"><span data-stu-id="b7c42-149">Call admission control is not enforced for remote users where the network traffic flows through the Internet.</span></span> <span data-ttu-id="b7c42-150">メディアトラフィックはインターネットに移動しているため、Lync Server で管理されていないため、CAC を適用することはできません。</span><span class="sxs-lookup"><span data-stu-id="b7c42-150">Because the media traffic is traversing the Internet, which is not managed by Lync Server, CAC cannot be applied.</span></span> <span data-ttu-id="b7c42-151">ただし、会社のネットワーク経由で流れる通話の部分で、CAC のチェックが実行されます。</span><span class="sxs-lookup"><span data-stu-id="b7c42-151">CAC checks will be performed, however, on the portion of the call that flows through the enterprise network.</span></span>

</div>

<div>

## <a name="call-admission-control-of-pstn-connections"></a><span data-ttu-id="b7c42-152">PSTN 接続の通話受付管理</span><span class="sxs-lookup"><span data-stu-id="b7c42-152">Call Admission Control of PSTN Connections</span></span>

<span data-ttu-id="b7c42-153">着信受付制御は、IP/PBX、PSTN ゲートウェイ、SIP トランクのいずれに接続されているかに関係なく、仲介サーバーで強制されます。</span><span class="sxs-lookup"><span data-stu-id="b7c42-153">Call admission control is enforceable on the Mediation Server regardless of whether it is connected to an IP/PBX, a PSTN gateway, or a SIP trunk.</span></span> <span data-ttu-id="b7c42-154">仲介サーバーはバックツーバックユーザーエージェント (B2BUA) であるため、メディアを終了します。</span><span class="sxs-lookup"><span data-stu-id="b7c42-154">Because the Mediation Server is a back-to-back user agent (B2BUA), it terminates media.</span></span> <span data-ttu-id="b7c42-155">この2つの接続側には、Lync Server に接続されている側と、PSTN ゲートウェイ、IP/Pbx、または SIP trunks に接続されているゲートウェイ側があります。</span><span class="sxs-lookup"><span data-stu-id="b7c42-155">It has two connection sides: a side that is connected to Lync Server and a gateway side, which is connected to PSTN gateways, IP/PBXs, or SIP trunks.</span></span> <span data-ttu-id="b7c42-156">PSTN 接続の詳細については、「 [Lync Server 2013 での pstn 接続の計画](lync-server-2013-planning-for-pstn-connectivity.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b7c42-156">For details about PSTN connections, see [Planning for PSTN connectivity in Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md).</span></span>

<span data-ttu-id="b7c42-157">メディアのバイパスが有効になっていない限り、CAC は仲介サーバーの両面に適用できます。</span><span class="sxs-lookup"><span data-stu-id="b7c42-157">CAC can be enforced on both sides of the Mediation Server unless media bypass is enabled.</span></span> <span data-ttu-id="b7c42-158">メディアのバイパスが有効になっている場合、メディアトラフィックは仲介サーバーをスキャンせず、Lync クライアントとゲートウェイの間で直接フローします。</span><span class="sxs-lookup"><span data-stu-id="b7c42-158">If media bypass is enabled, the media traffic doesn’t traverse the Mediation Server but instead flows directly between the Lync client and the gateway.</span></span> <span data-ttu-id="b7c42-159">この場合、CAC は不要です。</span><span class="sxs-lookup"><span data-stu-id="b7c42-159">In this case, CAC is not needed.</span></span> <span data-ttu-id="b7c42-160">詳細については、「 [Lync Server 2013 でのメディアのバイパスの計画](lync-server-2013-planning-for-media-bypass.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b7c42-160">For details, see [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md).</span></span>

<span data-ttu-id="b7c42-161">次の図は、メディア バイパスが有効な場合と有効でない場合について、PSTN 接続に CAC がどのように適用されるのかを示しています。</span><span class="sxs-lookup"><span data-stu-id="b7c42-161">The following figure illustrates how CAC is enforced on PSTN connections with and without media bypass enabled.</span></span>

<span data-ttu-id="b7c42-162">**PSTN 接続への通話受付管理の適用**</span><span class="sxs-lookup"><span data-stu-id="b7c42-162">**Call admission control enforcement on connections to the PSTN**</span></span>

<span data-ttu-id="b7c42-163">![音声 CAC メディア バイパス接続の適用](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "音声 CAC メディア バイパス接続の適用")</span><span class="sxs-lookup"><span data-stu-id="b7c42-163">![Voice CAC Media Bypass Connection Enforcement](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "Voice CAC Media Bypass Connection Enforcement")</span></span>

</div>

<div>

## <a name="compatibility-of-call-admission-control-with-earlier-versions-of-office-communications-server"></a><span data-ttu-id="b7c42-164">以前のバージョンの Office Communications Server との通話受付制御の互換性</span><span class="sxs-lookup"><span data-stu-id="b7c42-164">Compatibility of Call Admission Control with Earlier Versions of Office Communications Server</span></span>

<span data-ttu-id="b7c42-165">通話受付制御は、Lync Server 2010 以降で有効になっているエンドポイントでのみ有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="b7c42-165">Call admission control can be enabled only on endpoints that are enabled for Lync Server 2010 and later.</span></span>

<span data-ttu-id="b7c42-166">通話受付制御は、Office Communicator 2007 R2 以前を実行しているエンドポイントで有効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="b7c42-166">Call admission control cannot be enabled on endpoints running Office Communicator 2007 R2 or earlier.</span></span>

<span data-ttu-id="b7c42-167">**異なる Lync Server バージョンでの CAC のアプリケーション**</span><span class="sxs-lookup"><span data-stu-id="b7c42-167">**Application of CAC on different Lync Server versions**</span></span>

<span data-ttu-id="b7c42-168">![音声の CAC バージョン比較図](images/Gg398529.fdbfee7e-15fc-445b-949d-8d61e61ac350(OCS.15).jpg "音声の CAC バージョン比較図")</span><span class="sxs-lookup"><span data-stu-id="b7c42-168">![Voice CAC Version Comparison diagram](images/Gg398529.fdbfee7e-15fc-445b-949d-8d61e61ac350(OCS.15).jpg "Voice CAC Version Comparison diagram")</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

