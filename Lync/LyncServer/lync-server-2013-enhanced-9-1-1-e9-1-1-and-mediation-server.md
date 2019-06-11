---
title: 'Lync Server 2013: Enhanced 9-1-1 (E9-1-1) と仲介サーバー'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enhanced 9-1-1 (E9-1-1) and Mediation Server
ms:assetid: d231221f-5596-4a87-a463-269f5bcce65f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398903(v=OCS.15)
ms:contentKeyID: 48185448
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8a4d8ba329d55c916b089437d4c63804c592c0a2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833212"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enhanced-9-1-1-e9-1-1-and-mediation-server-in-lync-server-2013"></a><span data-ttu-id="4850f-102">Lync Server 2013 の Enhanced 9-1-1 (E9-1-1) と仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="4850f-102">Enhanced 9-1-1 (E9-1-1) and Mediation Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4850f-103">_**最終更新日:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="4850f-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="4850f-104">仲介サーバーは、拡張された 9-1-1 (E9) サービスプロバイダーと正しく対話できるように拡張された機能を備えています。</span><span class="sxs-lookup"><span data-stu-id="4850f-104">The Mediation Server has extended capabilities so that it can correctly interact with Enhanced 9-1-1 (E9-1-1) service providers.</span></span> <span data-ttu-id="4850f-105">仲介サーバーには特別な構成は必要ありません。E9 の操作に必要な SIP 拡張機能は、既定では、仲介サーバーの SIP プロトコル (PSTN ゲートウェイ、IP PBX、またはインターネットテレフォニーサービスプロバイダーの E9 に含まれています) に含まれていますが、これには、サービスが含まれています。会社</span><span class="sxs-lookup"><span data-stu-id="4850f-105">No special configuration is needed on the Mediation Server; the SIP extensions required for E9-1-1 interaction are, by default, included in the Mediation Server’s SIP protocol for its interactions with a gateway peer (PSTN gateway, IP-PBX, or the SBC of an Internet Telephony Service Provider, including E9-1-1 Service Providers)</span></span>

<span data-ttu-id="4850f-106">E9 サービスプロバイダーへの SIP トランクを既存の仲介サーバープールで終了できるかどうかは、E9 の SBC が仲介サーバーのプールを操作できるかどうかによって、スタンドアロンの仲介サーバーが必要になるかどうかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="4850f-106">Whether the SIP trunk to an E9-1-1 Service Provider can be terminated on an existing Mediation Server pool or will require stand-alone Mediation Servers will depend on whether the E9-1-1 SBC can interact with a pool of Mediation Servers.</span></span> <span data-ttu-id="4850f-107">詳細については、「 [Lync Server 2013 の M:N トランク](lync-server-2013-m-n-trunk.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4850f-107">For details, see [M:N trunk in Lync Server 2013](lync-server-2013-m-n-trunk.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

