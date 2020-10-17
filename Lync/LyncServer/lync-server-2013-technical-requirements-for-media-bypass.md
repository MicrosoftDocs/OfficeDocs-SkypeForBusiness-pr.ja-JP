---
title: 'Lync Server 2013: メディアバイパスの技術要件'
description: 'Lync Server 2013: メディアバイパスの技術要件。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for media bypass
ms:assetid: 6162a204-0e7c-460a-8eb2-e592c6590a8a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398435(v=OCS.15)
ms:contentKeyID: 48184321
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dee594139031966342fcec2bc1296a603055b4cc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559443"
---
# <a name="technical-requirements-for-media-bypass-in-lync-server-2013"></a><span data-ttu-id="81ef1-103">Lync Server 2013 でのメディアバイパスの技術要件</span><span class="sxs-lookup"><span data-stu-id="81ef1-103">Technical requirements for media bypass in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="81ef1-104">_**トピックの最終更新日:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="81ef1-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="81ef1-105">PSTN への各呼び出しに対して、仲介サーバーは、仲介サーバーを通過せずに、送信元の Lync エンドポイントからのメディアを仲介サーバーのピアに直接送信できるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="81ef1-105">For each call to the PSTN, the Mediation Server determines whether media from the Lync endpoint of origin can be sent directly to a Mediation Server peer without traversing the Mediation Server.</span></span> <span data-ttu-id="81ef1-106">ピアには、通話がルーティングされる仲介サーバー間のトランクに関連付けられた PSTN ゲートウェイ、IP-PBX、またはインターネット テレフォニー サービス プロバイダー (ITSP) のセッション ボーダー コントローラー (SBC) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="81ef1-106">The peer can be a PSTN gateway, IP-PBX, or Session Border Controller (SBC) at an Internet telephony service provider (ITSP) that is associated with the trunk between the Mediation Server where the call is routed.</span></span>

<span data-ttu-id="81ef1-107">メディア バイパスを使用できるのは、次の要件を満たす場合です。</span><span class="sxs-lookup"><span data-stu-id="81ef1-107">Media bypass can be employed when the following requirements are met:</span></span>

  - <span data-ttu-id="81ef1-108">仲介サーバーのピアは、メディアバイパスに必要な機能をサポートしている必要があります。最も重要な点は、複数の分岐された応答を処理する機能 ("初期ダイアログ" と呼ばれる) です。</span><span class="sxs-lookup"><span data-stu-id="81ef1-108">A Mediation Server peer must support the necessary capabilities for media bypass, the most important being the ability to handle multiple forked responses (known as “early dialogs”).</span></span> <span data-ttu-id="81ef1-109">Gateway、pbx、または ITSP の製造元に問い合わせて、gateway、PBX、または SBC が受け付けることができる初期ダイアログの最大数の値を取得します。</span><span class="sxs-lookup"><span data-stu-id="81ef1-109">Contact the manufacturer of your gateway or PBX, or your ITSP, to obtain the value for the maximum number of early dialogs that the gateway, PBX, or SBC can accept.</span></span>

  - <span data-ttu-id="81ef1-110">仲介サーバーのピアは、Lync エンドポイントから直接メディアトラフィックを受け入れる必要があります。</span><span class="sxs-lookup"><span data-stu-id="81ef1-110">The Mediation Server peer must accept media traffic directly from Lync endpoints.</span></span> <span data-ttu-id="81ef1-111">多くの ITSPs は、トラフィックを仲介サーバーからのみ受信することを SBC に許可します。</span><span class="sxs-lookup"><span data-stu-id="81ef1-111">Many ITSPs allow their SBC to receive traffic only from the Mediation Server.</span></span> <span data-ttu-id="81ef1-112">ITSP に問い合わせて、SBC が Lync エンドポイントから直接メディアトラフィックを受け付けるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="81ef1-112">Contact your ITSP to determine whether its SBC accepts media traffic directly from Lync endpoints.</span></span>

  - <span data-ttu-id="81ef1-113">Lync クライアントと仲介サーバーピアは適切に接続されている必要があります。つまり、帯域幅の制約がない WAN リンクを介して地域に接続されたネットワークサイトまたはネットワークサイトにある。</span><span class="sxs-lookup"><span data-stu-id="81ef1-113">Lync clients and a Mediation Server peer must be well connected, meaning that they are either located in the same network region or at network sites that connect to the region over WAN links that have no bandwidth constraints</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="81ef1-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="81ef1-114">See Also</span></span>


[<span data-ttu-id="81ef1-115">Lync Server 2013 のメディアバイパスモード</span><span class="sxs-lookup"><span data-stu-id="81ef1-115">Media bypass modes in Lync Server 2013</span></span>](lync-server-2013-media-bypass-modes.md)  
[<span data-ttu-id="81ef1-116">Lync Server 2013 でのメディアバイパスと通話受付管理</span><span class="sxs-lookup"><span data-stu-id="81ef1-116">Media bypass and call admission control in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-call-admission-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

