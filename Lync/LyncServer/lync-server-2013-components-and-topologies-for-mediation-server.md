---
title: 'Lync Server 2013: 仲介サーバーのコンポーネントとトポロジ'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for Mediation Server
ms:assetid: 71397168-36c3-4d21-b8ef-db6a751634ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398537(v=OCS.15)
ms:contentKeyID: 48184487
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9369c7ab74f19b8ccc53ff0c071e0458b21e6e0f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008749"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-mediation-server-in-lync-server-2013"></a><span data-ttu-id="05296-102">Lync Server 2013 の仲介サーバーのコンポーネントとトポロジ</span><span class="sxs-lookup"><span data-stu-id="05296-102">Components and topologies for Mediation Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="05296-103">_**トピックの最終更新日:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="05296-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="05296-104">このトピックでは、仲介サーバーが依存するコンポーネントと、仲介サーバーを展開するためのトポロジについて説明します。</span><span class="sxs-lookup"><span data-stu-id="05296-104">This topic describes the components on which the Mediation Server is dependent and the topologies in which the Mediation Server can be deployed</span></span>

<div>

## <a name="dependencies"></a><span data-ttu-id="05296-105">依存関係</span><span class="sxs-lookup"><span data-stu-id="05296-105">Dependencies</span></span>

<span data-ttu-id="05296-106">仲介サーバーには、次のような依存関係があります。</span><span class="sxs-lookup"><span data-stu-id="05296-106">The Mediation Server has the following dependencies:</span></span>

  - <span data-ttu-id="05296-107">**レジストラー.**</span><span class="sxs-lookup"><span data-stu-id="05296-107">**Registrar.**</span></span> <span data-ttu-id="05296-108">必須です。</span><span class="sxs-lookup"><span data-stu-id="05296-108">Required.</span></span> <span data-ttu-id="05296-109">レジストラーは、仲介サーバーと Lync Server 2013 ネットワークとの通信における通知の次ホップです。</span><span class="sxs-lookup"><span data-stu-id="05296-109">The Registrar is the next hop for signaling in the Mediation Server interactions with the Lync Server 2013 network.</span></span> <span data-ttu-id="05296-110">仲介サーバーは、仲介サーバーのみで構成されるスタンドアロンプールにインストールされるだけでなく、レジストラーと共にフロントエンドサーバーに併置することができます。</span><span class="sxs-lookup"><span data-stu-id="05296-110">Note that Mediation Server can be collocated on a Front End Server along with the Registrar, in addition to being installed in a stand-alone pool consisting only of Mediation Servers.</span></span> <span data-ttu-id="05296-111">レジストラーは、仲介サーバーと、存続可能ブランチアプライアンス上の PSTN ゲートウェイと併置されます。</span><span class="sxs-lookup"><span data-stu-id="05296-111">The Registrar is collocated with a Mediation Server and PSTN gateway on a Survivable Branch Appliance.</span></span>

  - <span data-ttu-id="05296-112">**監視サーバー。**</span><span class="sxs-lookup"><span data-stu-id="05296-112">**Monitoring Server.**</span></span> <span data-ttu-id="05296-113">推奨オプションです。</span><span class="sxs-lookup"><span data-stu-id="05296-113">Optional but highly recommended.</span></span> <span data-ttu-id="05296-114">監視サーバーは、仲介サーバーがメディアセッションに関連付けられている品質指標を記録することを可能にします。</span><span class="sxs-lookup"><span data-stu-id="05296-114">The Monitoring Server allows the Mediation Server to record quality metrics associated with its media sessions.</span></span>

  - <span data-ttu-id="05296-115">**エッジ サーバー。**</span><span class="sxs-lookup"><span data-stu-id="05296-115">**Edge Server.**</span></span> <span data-ttu-id="05296-116">外部ユーザー サポートで必要です。</span><span class="sxs-lookup"><span data-stu-id="05296-116">Required for external user support.</span></span> <span data-ttu-id="05296-117">エッジサーバーを使用すると、仲介サーバーは、NAT またはファイアウォールの内側に配置されたユーザーと対話できます。</span><span class="sxs-lookup"><span data-stu-id="05296-117">The Edge Server allows the Mediation Server to interact with users who are located behind a NAT or firewall.</span></span>

</div>

<div>

## <a name="topologies"></a><span data-ttu-id="05296-118">テクノロジ</span><span class="sxs-lookup"><span data-stu-id="05296-118">Topologies</span></span>

<span data-ttu-id="05296-119">Lync Server 2013、仲介サーバーは、既定では、Standard Edition サーバー、フロントエンドプール、または存続可能ブランチアプライアンス上のレジストラーのインスタンスに併置されます。</span><span class="sxs-lookup"><span data-stu-id="05296-119">The Lync Server 2013, Mediation Server is by default collocated with an instance of the Registrar on a Standard Edition server, a Front End pool, or Survivable Branch Appliance.</span></span> <span data-ttu-id="05296-120">フロントエンドプール内のすべての仲介サーバーは、同じように構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="05296-120">All Mediation Servers in a Front End pool must be configured identically.</span></span>

<span data-ttu-id="05296-121">パフォーマンスが問題になる場合は、専用のスタンドアロンプールに1つ以上の仲介サーバーを展開することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="05296-121">Where performance is an issue, it may be preferable to deploy one or more Mediation Servers in a dedicated stand-alone pool.</span></span> <span data-ttu-id="05296-122">または、SIP トランキングを展開している場合は、スタンドアロンの仲介サーバープールを展開することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="05296-122">Or, if you are deploying SIP trunking, we recommend that you deploy a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="05296-123">メディア バイパスと DNS 負荷分散をサポートする認定 PSTN ゲートウェイに直接 SIP 接続を展開する場合、スタンドアロンのfea-mediation-poolは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="05296-123">If you deploy Direct SIP connections to a qualified PSTN gateway that supports media bypass and DNS load balancing, a stand-alone Mediation Server pool is not necessary.</span></span> <span data-ttu-id="05296-124">スタンドアロンの仲介サーバー プールが必要でないのは、認定ゲートウェイが仲介サーバーのプールへの DNS 負荷分散に対応しており、プール内のすべての仲介サーバーからトラフィックを受信できるからです。</span><span class="sxs-lookup"><span data-stu-id="05296-124">A stand-alone Mediation Server pool is not necessary because qualified gateways are capable of DNS load balancing to a pool of Mediation Servers and they can receive traffic from any Mediation Server in a pool.</span></span>

<span data-ttu-id="05296-125">また、IP-PBX を展開している場合またはインターネット テレフォニー サーバー プロバイダーのセッション ボーダー コントローラー (SBC) に接続する場合に、以下のどちらかの条件に一致するときは、フロントエンド プールに仲介サーバーを併置することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="05296-125">We also recommend that you collocate the Mediation Server on a Front End pool when you have deployed IP-PBXs or connect to an Internet Telephony Server Provider’s Session Border Controller (SBC), as long as any of the following conditions are met:</span></span>

  - <span data-ttu-id="05296-126">IP-PBX または SBC は、プール内の任意の仲介サーバーからのトラフィックを受信するように構成されており、プール内のすべての仲介サーバーにトラフィックを均等にルーティングできる。</span><span class="sxs-lookup"><span data-stu-id="05296-126">The IP-PBX or SBC is configured to receive traffic from any Mediation Server in the pool and can route traffic uniformly to all Mediation Servers in the pool.</span></span>

  - <span data-ttu-id="05296-127">Ip-pbx はメディアバイパスをサポートしていませんが、仲介サーバーをホストしているフロントエンドプールは、メディアバイパスが適用されない通話の音声トランスコーディングを処理できます。</span><span class="sxs-lookup"><span data-stu-id="05296-127">The IP-PBX does not support media bypass, but the Front End pool that is hosting the Mediation Server can handle voice transcoding for calls to which media bypass does not apply.</span></span>

<span data-ttu-id="05296-128">Microsoft Lync Server 2013、計画ツールを使用して、仲介サーバーを併置するフロントエンドプールが負荷を処理できるかどうかを評価できます。</span><span class="sxs-lookup"><span data-stu-id="05296-128">You can use the Microsoft Lync Server 2013, Planning Tool to evaluate whether the Front End pool where you want to collocate the Mediation Server can handle the load.</span></span> <span data-ttu-id="05296-129">これらの要件に適合しない環境では、スタンドアロン仲介サーバー プールを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="05296-129">If your environment cannot meet these requirements, then you must deploy a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="05296-130">展開するトポロジの詳細については、「 [Lync server 2013 の仲介サーバーの展開ガイドライン](lync-server-2013-deployment-guidelines-for-mediation-server.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="05296-130">For details about which topology to deploy, see [Deployment guidelines for Mediation Server in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md).</span></span>

<span data-ttu-id="05296-131">次の図は、WAN リンクで接続された 2 つのサイトからなる簡単なトポロジを示しています。</span><span class="sxs-lookup"><span data-stu-id="05296-131">The following figure shows a simple topology consisting of two sites connected by a WAN link.</span></span> <span data-ttu-id="05296-132">サイト1のフロントエンドプールのレジストラーと仲介サーバーが併置されます。</span><span class="sxs-lookup"><span data-stu-id="05296-132">Mediation Server is collocated with the Registrar on a Front End pool at Site 1.</span></span> <span data-ttu-id="05296-133">サイト1の仲介サーバーは、サイト1の PSTN ゲートウェイとサイト2のゲートウェイの両方を制御します。</span><span class="sxs-lookup"><span data-stu-id="05296-133">The Mediation Servers at Site 1 controls both the PSTN gateway at Site 1 and the gateway at Site 2.</span></span> <span data-ttu-id="05296-134">このトポロジでは、サイトおよび地域情報を使用できるようにメディア バイパスがグローバルに有効になっていて、各 PSTN ゲートウェイ (GW1 と GW2) へのトランクはバイパスが有効になっています。</span><span class="sxs-lookup"><span data-stu-id="05296-134">In this topology, media bypass is enabled globally to use site and region information, and the trunks to each PSTN gateway (GW1 and GW2) have bypass enabled.</span></span>

<span data-ttu-id="05296-135">**仲介サーバーがサイト 1 にあり、PSTN ゲートウェイがサイト 2 にある、WAN リンクで接続されたサイトの例**</span><span class="sxs-lookup"><span data-stu-id="05296-135">**Example of sites connected by a WAN link with a Mediation Server at Site 1 and a PSTN gateway at Site 2**</span></span>

<span data-ttu-id="05296-136">![仲介サーバーの WAN ゲートウェイを使用した音声トポロジ](images/Gg398537.67872e61-1444-447b-918c-abe89abc3004(OCS.15).jpg "仲介サーバーの WAN ゲートウェイを使用した音声トポロジ")</span><span class="sxs-lookup"><span data-stu-id="05296-136">![Voice Topology with Mediation Server WAN Gateway](images/Gg398537.67872e61-1444-447b-918c-abe89abc3004(OCS.15).jpg "Voice Topology with Mediation Server WAN Gateway")</span></span>

<span data-ttu-id="05296-137">次の図は、サイト1のフロントエンドプールのレジストラーに仲介サーバーが併置され、サイト1の IP-PBX への直接 SIP 接続がある単純なトポロジを示しています。</span><span class="sxs-lookup"><span data-stu-id="05296-137">The next figure shows a simple topology where the Mediation Server is collocated with the Registrar on Front End pool at Site 1 and has a Direct SIP connection to the IP-PBX at Site 1.</span></span> <span data-ttu-id="05296-138">この図では、仲介サーバーはサイト2の PSTN ゲートウェイも制御します。</span><span class="sxs-lookup"><span data-stu-id="05296-138">In this figure, the Mediation Server also controls a PSTN gateway at Site 2.</span></span> <span data-ttu-id="05296-139">サイト1と2の両方に Lync ユーザーが存在するとします。</span><span class="sxs-lookup"><span data-stu-id="05296-139">Assume that Lync users exist at both Sites 1 and 2.</span></span> <span data-ttu-id="05296-140">また、ip-pbx によって制御されるメディアエンドポイントに送信される前に、Lync エンドポイントから送信されるすべてのメディアでスキャンする必要がある、関連付けられたメディアプロセッサが ip-pbx にあると仮定します。</span><span class="sxs-lookup"><span data-stu-id="05296-140">Also assume that the IP-PBX has an associated media processor that must be traversed by all media originating from Lync endpoints before being sent to media endpoints controlled by the IP-PBX.</span></span> <span data-ttu-id="05296-141">このトポロジでは、サイトおよび地域情報を使用できるようにメディア バイパスがグローバルに有効になっていて、PBX と PSTN ゲートウェイへのトランクはバイパスが有効になっています。</span><span class="sxs-lookup"><span data-stu-id="05296-141">In this topology, media bypass is enabled globally to use site and region information, and the trunks to the PBX and PSTN gateway have media bypass enabled.</span></span>

<span data-ttu-id="05296-142">**仲介サーバーがサイト 1 にあり、PBX がサイト 2 にある、WAN リンクで接続されたサイトの例**</span><span class="sxs-lookup"><span data-stu-id="05296-142">**Example of sites connected by a WAN link with a Mediation Server at Site 1 and a PBX at Site 2**</span></span>

<span data-ttu-id="05296-143">![音声トポロジ仲介サーバーの WAN PBX](images/Gg398537.df6c8a5b-8431-4187-907d-ff5ca26eeeec(OCS.15).jpg "音声トポロジ仲介サーバーの WAN PBX")</span><span class="sxs-lookup"><span data-stu-id="05296-143">![Voice Topology Mediation Server WAN PBX](images/Gg398537.df6c8a5b-8431-4187-907d-ff5ca26eeeec(OCS.15).jpg "Voice Topology Mediation Server WAN PBX")</span></span>

<span data-ttu-id="05296-144">PBX トポロジの計画の詳細については、「lync server [2013 の仲介サーバーの展開ガイドライン](lync-server-2013-deployment-guidelines-for-mediation-server.md)」と「 [Direct SIP Deployment Options in lync server 2013](lync-server-2013-direct-sip-deployment-options.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="05296-144">For details about planning for PBX topologies, see [Deployment guidelines for Mediation Server in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md) and [Direct SIP deployment options in Lync Server 2013](lync-server-2013-direct-sip-deployment-options.md).</span></span>

<span data-ttu-id="05296-145">このトピックの最後の図は、仲介サーバーがインターネットテレフォニーサービスプロバイダーの SBC に接続されているトポロジを示しています。</span><span class="sxs-lookup"><span data-stu-id="05296-145">The last figure in this topic shows a topology where the Mediation Server is connected to the SBC of an Internet Telephony Service Provider.</span></span> <span data-ttu-id="05296-146">SIP トランクトポロジの詳細については、「 [Lync Server 2013 の sip トランキング](lync-server-2013-sip-trunking.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="05296-146">For details about SIP trunk topologies, see [SIP trunking in Lync Server 2013](lync-server-2013-sip-trunking.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

