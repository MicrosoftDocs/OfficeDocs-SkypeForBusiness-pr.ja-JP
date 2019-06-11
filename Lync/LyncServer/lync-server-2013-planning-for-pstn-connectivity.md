---
title: 'Lync Server 2013: PSTN 接続の計画'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for PSTN connectivity
ms:assetid: 280f684a-740a-443d-8ecf-574241382a42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425749(v=OCS.15)
ms:contentKeyID: 48183684
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d64089661b5d185362a8e47128e9a890b03edfd8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824583"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-pstn-connectivity-in-lync-server-2013"></a><span data-ttu-id="3fa9f-102">Lync Server 2013 での PSTN 接続の計画</span><span class="sxs-lookup"><span data-stu-id="3fa9f-102">Planning for PSTN connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3fa9f-103">_**最終更新日:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="3fa9f-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="3fa9f-104">エンタープライズ レベルの VoIP ソリューションでは、サービスの品質 (QoS) を低下させずに公衆交換電話網 (PSTN) との通話の発信および着信を処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3fa9f-104">An enterprise-grade VoIP solution must provide for calls to and from the public switched telephone network (PSTN) without any decline in Quality of Service (QoS).</span></span> <span data-ttu-id="3fa9f-105">通話の発信と受信を行うユーザーは、基になるテクノロジを認識していません。ユーザーの視点から見ると、エンタープライズ Voip インフラストラクチャと PSTN との間の通話は、別の電話会議と同じように見えます。</span><span class="sxs-lookup"><span data-stu-id="3fa9f-105">Users who place and receive calls should not be aware of the underlying technology: from the user's perspective, a call between the Enterprise Voice infrastructure and the PSTN should seem like just another phone call.</span></span>

<span data-ttu-id="3fa9f-106">Lync Server 2013 は、次のオプションを使用して、信頼性の高いスケーラブルな PSTN 接続を提供します。</span><span class="sxs-lookup"><span data-stu-id="3fa9f-106">Lync Server 2013 provides reliable, scalable PSTN connectivity by using the following options:</span></span>

  - <span data-ttu-id="3fa9f-107">インターネット テレフォニー サービス プロバイダー (ITSP) への **SIP トランク**</span><span class="sxs-lookup"><span data-stu-id="3fa9f-107">**SIP trunks** to an Internet telephony service provider (ITSP)</span></span>

  - <span data-ttu-id="3fa9f-108">PSTN ゲートウェイへの**直接 SIP 接続**</span><span class="sxs-lookup"><span data-stu-id="3fa9f-108">**Direct SIP connections** to a PSTN gateway</span></span>

  - <span data-ttu-id="3fa9f-109">PBX への**直接 SIP 接続**</span><span class="sxs-lookup"><span data-stu-id="3fa9f-109">**Direct SIP connections** to a PBX</span></span>

<span data-ttu-id="3fa9f-110">企業は、その規模、地理的範囲、および既存の音声インフラストラクチャに応じて、さまざまな場所でこれらのオプションのうちの 1 つ、2 つ、または 3 つすべてを使用できます。</span><span class="sxs-lookup"><span data-stu-id="3fa9f-110">Depending on its size, geographic coverage, and existing voice infrastructure, an enterprise may use one, two, or even all three of these options at various locations.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="3fa9f-111">このセクション中</span><span class="sxs-lookup"><span data-stu-id="3fa9f-111">In This Section</span></span>

  - [<span data-ttu-id="3fa9f-112">Lync Server 2013 での SIP トランク</span><span class="sxs-lookup"><span data-stu-id="3fa9f-112">SIP trunking in Lync Server 2013</span></span>](lync-server-2013-sip-trunking.md)

  - [<span data-ttu-id="3fa9f-113">Lync Server 2013 での直接 SIP 接続</span><span class="sxs-lookup"><span data-stu-id="3fa9f-113">Direct SIP connections in Lync Server 2013</span></span>](lync-server-2013-direct-sip-connections.md)

  - [<span data-ttu-id="3fa9f-114">Lync Server 2013 の M:N トランク</span><span class="sxs-lookup"><span data-stu-id="3fa9f-114">M:N trunk in Lync Server 2013</span></span>](lync-server-2013-m-n-trunk.md)

  - [<span data-ttu-id="3fa9f-115">Lync Server 2013 の翻訳ルール</span><span class="sxs-lookup"><span data-stu-id="3fa9f-115">Translation rules in Lync Server 2013</span></span>](lync-server-2013-translation-rules.md)

  - [<span data-ttu-id="3fa9f-116">Lync Server 2013 での発信音声ルーティングの計画</span><span class="sxs-lookup"><span data-stu-id="3fa9f-116">Planning outbound voice routing in Lync Server 2013</span></span>](lync-server-2013-planning-outbound-voice-routing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

