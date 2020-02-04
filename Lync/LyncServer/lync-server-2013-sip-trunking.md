---
title: 'Lync Server 2013: SIP トランク'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SIP trunking
ms:assetid: 7c586401-d0e5-4017-b3e1-fe5e7f8fc6db
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398619(v=OCS.15)
ms:contentKeyID: 48184615
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d76907c1868e9fccb1a31e705c73807a8cbe501b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764483"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sip-trunking-in-lync-server-2013"></a><span data-ttu-id="60c00-102">Lync Server 2013 での SIP トランク</span><span class="sxs-lookup"><span data-stu-id="60c00-102">SIP trunking in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="60c00-103">_**最終更新日:** 2012-08-13_</span><span class="sxs-lookup"><span data-stu-id="60c00-103">_**Topic Last Modified:** 2012-08-13_</span></span>

<span data-ttu-id="60c00-p101">セッション開始プロトコル (SIP) は、基本的な電話サービスおよび追加のリアルタイム通信サービス (インスタント メッセージング、会議、プレゼンス検出、マルチメディアなど) のボイス オーバー IP (VoIP) 通信セッションを開始および管理するために使用します。ここでは、ローカル ネットワークの境界を越えて広がる種類の SIP 接続である、*SIP トランク*を実装するための計画情報について説明します。</span><span class="sxs-lookup"><span data-stu-id="60c00-p101">Session Initiation Protocol (SIP) is used to initiate and manage Voice over IP (VoIP) communications sessions for basic telephone service and for additional real-time communication services, such as instant messaging, conferencing, presence detection, and multimedia. This section provides planning information for implementing *SIP trunks*, a type of SIP connection that extends beyond the boundary of your local network.</span></span>

<div>

## <a name="what-is-sip-trunking"></a><span data-ttu-id="60c00-106">SIP トランクとは</span><span class="sxs-lookup"><span data-stu-id="60c00-106">What is SIP Trunking?</span></span>

<span data-ttu-id="60c00-p102">SIP トランクは、組織とファイアウォールの外側のインターネット テレフォニー サービス プロバイダー (ITSP) との間に SIP 通信リンクを確立する SIP 接続です。通常、SIP トランクは、組織の中央サイトを ITSP に接続するために使用します。ブランチ サイトを ITSP に接続するために SIP トランキングを使用する場合もあります。</span><span class="sxs-lookup"><span data-stu-id="60c00-p102">A SIP trunk is an IP connection that establishes a SIP communications link between your organization and an Internet telephony service provider (ITSP) beyond your firewall. Typically, a SIP trunk is used to connect your organization’s central site to an ITSP. In some cases, you may also opt to use SIP trunking to connect your branch site to an ITSP.</span></span>

<div>

## <a name="sip-trunks-vs-direct-sip-connections"></a><span data-ttu-id="60c00-110">SIP トランクと直接 SIP 接続の比較</span><span class="sxs-lookup"><span data-stu-id="60c00-110">SIP Trunks vs. Direct SIP Connections</span></span>

<span data-ttu-id="60c00-111">*トランク*という用語は、回路交換技術を基盤としています。</span><span class="sxs-lookup"><span data-stu-id="60c00-111">The term *trunk* is derived from circuit-switched technology.</span></span> <span data-ttu-id="60c00-112">電話交換機器を接続する専用の物理回線を指します。</span><span class="sxs-lookup"><span data-stu-id="60c00-112">It refers to a dedicated physical line that connects telephone switching equipment.</span></span> <span data-ttu-id="60c00-113">このように、trunks、SIP trunks は、2つの独立した SIP ネットワーク間の接続、Lync Server 2013 enterprise、ITSP になります。</span><span class="sxs-lookup"><span data-stu-id="60c00-113">Like their predecessor, time division multiplexing (TDM) trunks, SIP trunks are connections between two separate SIP networks—the Lync Server 2013 enterprise and the ITSP.</span></span> <span data-ttu-id="60c00-114">サーキットスイッチ trunks とは異なり、SIP trunks は、サポートされている SIP トランク接続タイプのいずれかで確立できる仮想接続です。</span><span class="sxs-lookup"><span data-stu-id="60c00-114">Unlike circuit-switched trunks, SIP trunks are virtual connections that can be established over any of the supported SIP trunking connection types.</span></span> <span data-ttu-id="60c00-115">サポートされている接続の種類の詳細については、「 [Lync Server 2013 で SIP トランクを実装する方法](lync-server-2013-how-do-i-implement-sip-trunking.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="60c00-115">For details about the supported connection types, see [How do I implement SIP trunking in Lync Server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md).</span></span>

<span data-ttu-id="60c00-116">これに対し、直接 SIP 接続は、ローカル ネットワークの境界を越えない SIP 接続です (つまり、内部ネットワーク内の公衆交換電話網 (PSTN) ゲートウェイまたは構内交換機 (PBX) に接続します)。</span><span class="sxs-lookup"><span data-stu-id="60c00-116">Direct SIP connections, on the other hand, are SIP connections that do not cross the local network boundary (that is, they connect to a public switched telephone network (PSTN) gateway or private branch exchange (PBX) within your internal network).</span></span> <span data-ttu-id="60c00-117">Lync Server 2013 での直接 SIP 接続の使用方法の詳細については、「 [Lync server 2013 の直接 sip 接続](lync-server-2013-direct-sip-connections.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="60c00-117">For details about how you can use direct SIP connections with Lync Server 2013, see [Direct SIP connections in Lync Server 2013](lync-server-2013-direct-sip-connections.md).</span></span>

</div>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="60c00-118">このセクション中</span><span class="sxs-lookup"><span data-stu-id="60c00-118">In This Section</span></span>

  - [<span data-ttu-id="60c00-119">Lync Server 2013 の SIP トランキングの概要</span><span class="sxs-lookup"><span data-stu-id="60c00-119">Overview of SIP trunking in Lync Server 2013</span></span>](lync-server-2013-overview-of-sip-trunking.md)

  - [<span data-ttu-id="60c00-120">Lync Server 2013 での SIP トランキングの実装方法</span><span class="sxs-lookup"><span data-stu-id="60c00-120">How do I implement SIP trunking in Lync Server 2013?</span></span>](lync-server-2013-how-do-i-implement-sip-trunking.md)

  - [<span data-ttu-id="60c00-121">Lync Server 2013 の SIP トランキングのコンポーネントおよびトポロジ</span><span class="sxs-lookup"><span data-stu-id="60c00-121">Components and topologies for SIP trunking in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-sip-trunking.md)

  - [<span data-ttu-id="60c00-122">Branch site SIP trunking in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="60c00-122">Branch site SIP trunking in Lync Server 2013</span></span>](lync-server-2013-branch-site-sip-trunking.md)

  - [<span data-ttu-id="60c00-123">Lync Server 2013 に関する SIP トランクの展開チェックリスト</span><span class="sxs-lookup"><span data-stu-id="60c00-123">SIP trunk deployment checklist for Lync Server 2013</span></span>](lync-server-2013-sip-trunk-deployment-checklist.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

