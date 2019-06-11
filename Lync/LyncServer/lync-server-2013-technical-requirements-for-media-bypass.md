---
title: 'Lync Server 2013: メディア バイパスの技術要件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Technical requirements for media bypass
ms:assetid: 6162a204-0e7c-460a-8eb2-e592c6590a8a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398435(v=OCS.15)
ms:contentKeyID: 48184321
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5f59e0c025935ca8c2cd341549cdb58a44e7dbb8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848546"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-media-bypass-in-lync-server-2013"></a><span data-ttu-id="725de-102">Lync Server 2013 メディア バイパスの技術要件</span><span class="sxs-lookup"><span data-stu-id="725de-102">Technical requirements for media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="725de-103">_**最終更新日:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="725de-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="725de-104">PSTN サーバーは、PSTN への各通話について、仲介サーバーを走査せずに、送信元の Lync エンドポイントからのメディアを仲介サーバーピアに直接送信できるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="725de-104">For each call to the PSTN, the Mediation Server determines whether media from the Lync endpoint of origin can be sent directly to a Mediation Server peer without traversing the Mediation Server.</span></span> <span data-ttu-id="725de-105">ピアには、通話がルーティングされる仲介サーバー間のトランクに関連付けられた PSTN ゲートウェイ、IP-PBX、またはインターネット テレフォニー サービス プロバイダー (ITSP) のセッション ボーダー コントローラー (SBC) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="725de-105">The peer can be a PSTN gateway, IP-PBX, or Session Border Controller (SBC) at an Internet telephony service provider (ITSP) that is associated with the trunk between the Mediation Server where the call is routed.</span></span>

<span data-ttu-id="725de-106">メディア バイパスを使用できるのは、次の要件を満たす場合です。</span><span class="sxs-lookup"><span data-stu-id="725de-106">Media bypass can be employed when the following requirements are met:</span></span>

  - <span data-ttu-id="725de-107">仲介サーバーピアは、メディアバイパスに必要な機能をサポートしている必要があります。最も重要なことは、複数のフォークされた応答を処理する機能 ("初期ダイアログ" と呼ばれます) です。</span><span class="sxs-lookup"><span data-stu-id="725de-107">A Mediation Server peer must support the necessary capabilities for media bypass, the most important being the ability to handle multiple forked responses (known as “early dialogs”).</span></span> <span data-ttu-id="725de-108">ゲートウェイまたは PBX、または ITSP の製造元に問い合わせて、ゲートウェイ、PBX、または SBC が受け入れられる初期ダイアログの最大数の値を取得します。</span><span class="sxs-lookup"><span data-stu-id="725de-108">Contact the manufacturer of your gateway or PBX, or your ITSP, to obtain the value for the maximum number of early dialogs that the gateway, PBX, or SBC can accept.</span></span>

  - <span data-ttu-id="725de-109">仲介サーバーピアは、Lync エンドポイントから直接メディアトラフィックを受け取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="725de-109">The Mediation Server peer must accept media traffic directly from Lync endpoints.</span></span> <span data-ttu-id="725de-110">多くの ITSPs は、SBC が仲介サーバーからのみトラフィックを受信できるようにします。</span><span class="sxs-lookup"><span data-stu-id="725de-110">Many ITSPs allow their SBC to receive traffic only from the Mediation Server.</span></span> <span data-ttu-id="725de-111">ITSP に連絡して、SBC が Lync エンドポイントから直接メディアトラフィックを受け入れているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="725de-111">Contact your ITSP to determine whether its SBC accepts media traffic directly from Lync endpoints.</span></span>

  - <span data-ttu-id="725de-112">Lync クライアントと仲介サーバーピアは適切に接続されている必要があります。つまり、それらは、帯域幅の制約がない WAN リンクを経由して、同一のネットワーク領域またはネットワークサイトに配置されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="725de-112">Lync clients and a Mediation Server peer must be well connected, meaning that they are either located in the same network region or at network sites that connect to the region over WAN links that have no bandwidth constraints</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="725de-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="725de-113">See Also</span></span>


[<span data-ttu-id="725de-114">Lync Server 2013 のメディア バイパス モード</span><span class="sxs-lookup"><span data-stu-id="725de-114">Media bypass modes in Lync Server 2013</span></span>](lync-server-2013-media-bypass-modes.md)  
[<span data-ttu-id="725de-115">Lync Server 2013 でのメディア バイパスと通話受付管理</span><span class="sxs-lookup"><span data-stu-id="725de-115">Media bypass and call admission control in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-call-admission-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

