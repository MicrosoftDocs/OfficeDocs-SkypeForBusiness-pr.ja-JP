---
title: 'Lync Server 2013: PSTN 接続の計画'
description: 'Lync Server 2013: PSTN 接続の計画。'
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
ms.openlocfilehash: 45c0df6aa6dc9d9cc8522223056f1834849e6ddb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549323"
---
# <a name="planning-for-pstn-connectivity-in-lync-server-2013"></a><span data-ttu-id="f71da-103">Lync Server 2013 での PSTN 接続の計画</span><span class="sxs-lookup"><span data-stu-id="f71da-103">Planning for PSTN connectivity in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f71da-104">_**トピックの最終更新日:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="f71da-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="f71da-105">エンタープライズ レベルの VoIP ソリューションでは、サービスの品質 (QoS) を低下させずに公衆交換電話網 (PSTN) との通話の発信および着信を処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f71da-105">An enterprise-grade VoIP solution must provide for calls to and from the public switched telephone network (PSTN) without any decline in Quality of Service (QoS).</span></span> <span data-ttu-id="f71da-106">呼び出しを発信または受信するユーザーは、基礎となるテクノロジに気付かないようにする必要があります。これは、ユーザーの観点から、エンタープライズ Voip インフラストラクチャと PSTN との間の通話は、別の通話と同じように見えます。</span><span class="sxs-lookup"><span data-stu-id="f71da-106">Users who place and receive calls should not be aware of the underlying technology: from the user's perspective, a call between the Enterprise Voice infrastructure and the PSTN should seem like just another phone call.</span></span>

<span data-ttu-id="f71da-107">Lync Server 2013 は、次のオプションを使用して、信頼性の高いスケーラブルな PSTN 接続を提供します。</span><span class="sxs-lookup"><span data-stu-id="f71da-107">Lync Server 2013 provides reliable, scalable PSTN connectivity by using the following options:</span></span>

  - <span data-ttu-id="f71da-108">インターネット テレフォニー サービス プロバイダー (ITSP) への **SIP トランク**</span><span class="sxs-lookup"><span data-stu-id="f71da-108">**SIP trunks** to an Internet telephony service provider (ITSP)</span></span>

  - <span data-ttu-id="f71da-109">PSTN ゲートウェイへの**直接 SIP 接続**</span><span class="sxs-lookup"><span data-stu-id="f71da-109">**Direct SIP connections** to a PSTN gateway</span></span>

  - <span data-ttu-id="f71da-110">PBX への**直接 SIP 接続**</span><span class="sxs-lookup"><span data-stu-id="f71da-110">**Direct SIP connections** to a PBX</span></span>

<span data-ttu-id="f71da-111">企業は、そのサイズ、地理的範囲、および既存の音声インフラストラクチャに応じて、さまざまな場所でこれらのオプションのうちの 1 つ、2 つ、または 3 つすべてを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f71da-111">Depending on its size, geographic coverage, and existing voice infrastructure, an enterprise may use one, two, or even all three of these options at various locations.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f71da-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="f71da-112">In This Section</span></span>

  - [<span data-ttu-id="f71da-113">Lync Server 2013 での SIP トランキング</span><span class="sxs-lookup"><span data-stu-id="f71da-113">SIP trunking in Lync Server 2013</span></span>](lync-server-2013-sip-trunking.md)

  - [<span data-ttu-id="f71da-114">Lync Server 2013 の直接 SIP 接続</span><span class="sxs-lookup"><span data-stu-id="f71da-114">Direct SIP connections in Lync Server 2013</span></span>](lync-server-2013-direct-sip-connections.md)

  - [<span data-ttu-id="f71da-115">Lync Server 2013 の M:N トランク</span><span class="sxs-lookup"><span data-stu-id="f71da-115">M:N trunk in Lync Server 2013</span></span>](lync-server-2013-m-n-trunk.md)

  - [<span data-ttu-id="f71da-116">Lync Server 2013 の変換ルール</span><span class="sxs-lookup"><span data-stu-id="f71da-116">Translation rules in Lync Server 2013</span></span>](lync-server-2013-translation-rules.md)

  - [<span data-ttu-id="f71da-117">Lync Server 2013 での発信音声ルーティングの計画</span><span class="sxs-lookup"><span data-stu-id="f71da-117">Planning outbound voice routing in Lync Server 2013</span></span>](lync-server-2013-planning-outbound-voice-routing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

