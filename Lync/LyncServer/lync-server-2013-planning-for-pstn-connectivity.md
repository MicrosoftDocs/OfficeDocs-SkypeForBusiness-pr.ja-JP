---
title: 'Lync Server 2013: PSTN 接続の計画'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for PSTN connectivity
ms:assetid: 280f684a-740a-443d-8ecf-574241382a42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425749(v=OCS.15)
ms:contentKeyID: 48183684
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 41de8ee220ef1bbe88601d53886046c28f72e954
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521944"
---
# <a name="planning-for-pstn-connectivity-in-lync-server-2013"></a><span data-ttu-id="a893b-102">Lync Server 2013 での PSTN 接続の計画</span><span class="sxs-lookup"><span data-stu-id="a893b-102">Planning for PSTN connectivity in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a893b-103">_**トピックの最終更新日:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="a893b-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="a893b-104">エンタープライズ レベルの VoIP ソリューションでは、サービスの品質 (QoS) を低下させずに公衆交換電話網 (PSTN) との通話の発信および着信を処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a893b-104">An enterprise-grade VoIP solution must provide for calls to and from the public switched telephone network (PSTN) without any decline in Quality of Service (QoS).</span></span> <span data-ttu-id="a893b-105">呼び出しを発信または受信するユーザーは、基礎となるテクノロジに気付かないようにする必要があります。これは、ユーザーの観点から、エンタープライズ Voip インフラストラクチャと PSTN との間の通話は、別の通話と同じように見えます。</span><span class="sxs-lookup"><span data-stu-id="a893b-105">Users who place and receive calls should not be aware of the underlying technology: from the user's perspective, a call between the Enterprise Voice infrastructure and the PSTN should seem like just another phone call.</span></span>

<span data-ttu-id="a893b-106">Lync Server 2013 は、次のオプションを使用して、信頼性の高いスケーラブルな PSTN 接続を提供します。</span><span class="sxs-lookup"><span data-stu-id="a893b-106">Lync Server 2013 provides reliable, scalable PSTN connectivity by using the following options:</span></span>

  - <span data-ttu-id="a893b-107">インターネット テレフォニー サービス プロバイダー (ITSP) への **SIP トランク**</span><span class="sxs-lookup"><span data-stu-id="a893b-107">**SIP trunks** to an Internet telephony service provider (ITSP)</span></span>

  - <span data-ttu-id="a893b-108">PSTN ゲートウェイへの**直接 SIP 接続**</span><span class="sxs-lookup"><span data-stu-id="a893b-108">**Direct SIP connections** to a PSTN gateway</span></span>

  - <span data-ttu-id="a893b-109">PBX への**直接 SIP 接続**</span><span class="sxs-lookup"><span data-stu-id="a893b-109">**Direct SIP connections** to a PBX</span></span>

<span data-ttu-id="a893b-110">企業は、そのサイズ、地理的範囲、および既存の音声インフラストラクチャに応じて、さまざまな場所でこれらのオプションのうちの 1 つ、2 つ、または 3 つすべてを使用できます。</span><span class="sxs-lookup"><span data-stu-id="a893b-110">Depending on its size, geographic coverage, and existing voice infrastructure, an enterprise may use one, two, or even all three of these options at various locations.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a893b-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="a893b-111">In This Section</span></span>

  - [<span data-ttu-id="a893b-112">Lync Server 2013 での SIP トランキング</span><span class="sxs-lookup"><span data-stu-id="a893b-112">SIP trunking in Lync Server 2013</span></span>](lync-server-2013-sip-trunking.md)

  - [<span data-ttu-id="a893b-113">Lync Server 2013 の直接 SIP 接続</span><span class="sxs-lookup"><span data-stu-id="a893b-113">Direct SIP connections in Lync Server 2013</span></span>](lync-server-2013-direct-sip-connections.md)

  - [<span data-ttu-id="a893b-114">Lync Server 2013 の M:N トランク</span><span class="sxs-lookup"><span data-stu-id="a893b-114">M:N trunk in Lync Server 2013</span></span>](lync-server-2013-m-n-trunk.md)

  - [<span data-ttu-id="a893b-115">Lync Server 2013 の変換ルール</span><span class="sxs-lookup"><span data-stu-id="a893b-115">Translation rules in Lync Server 2013</span></span>](lync-server-2013-translation-rules.md)

  - [<span data-ttu-id="a893b-116">Lync Server 2013 での発信音声ルーティングの計画</span><span class="sxs-lookup"><span data-stu-id="a893b-116">Planning outbound voice routing in Lync Server 2013</span></span>](lync-server-2013-planning-outbound-voice-routing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

