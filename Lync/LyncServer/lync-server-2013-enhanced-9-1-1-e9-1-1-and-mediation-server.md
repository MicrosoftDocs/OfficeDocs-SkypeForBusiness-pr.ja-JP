---
title: 'Lync Server 2013: Enhanced 9-1-1 (E9-1-1) および仲介サーバー'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enhanced 9-1-1 (E9-1-1) and Mediation Server
ms:assetid: d231221f-5596-4a87-a463-269f5bcce65f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398903(v=OCS.15)
ms:contentKeyID: 48185448
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bd74c7ee030516b12039427a618596972240b901
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042134"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enhanced-9-1-1-e9-1-1-and-mediation-server-in-lync-server-2013"></a><span data-ttu-id="f34c3-102">Lync Server 2013 の拡張 9-1-1 (E9-1-1) および仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="f34c3-102">Enhanced 9-1-1 (E9-1-1) and Mediation Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f34c3-103">_**トピックの最終更新日:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="f34c3-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="f34c3-104">仲介サーバーは、拡張された 9-1-1 (E9-1-1) サービスプロバイダーと正しく対話できるように拡張された機能を備えています。</span><span class="sxs-lookup"><span data-stu-id="f34c3-104">The Mediation Server has extended capabilities so that it can correctly interact with Enhanced 9-1-1 (E9-1-1) service providers.</span></span> <span data-ttu-id="f34c3-105">仲介サーバーに特別な構成は必要ありません。E9-1-1 の相互作用に必要な SIP 拡張機能は、既定では、ゲートウェイピア (PSTN ゲートウェイ、ip-pbx、またはインターネットテレフォニーサービスプロバイダーの SBC (E9-1-1 サービスを含む) との相互作用について、仲介サーバーの SIP プロトコルに含まれています。会社</span><span class="sxs-lookup"><span data-stu-id="f34c3-105">No special configuration is needed on the Mediation Server; the SIP extensions required for E9-1-1 interaction are, by default, included in the Mediation Server’s SIP protocol for its interactions with a gateway peer (PSTN gateway, IP-PBX, or the SBC of an Internet Telephony Service Provider, including E9-1-1 Service Providers)</span></span>

<span data-ttu-id="f34c3-106">E9-1-1 サービスプロバイダーへの SIP トランクを既存の仲介サーバープールで終了することができるかどうか、またはスタンドアロンの仲介サーバーが必要かどうかは、E9-1-1 SBC が仲介サーバーのプールと対話できるかどうかによって決まります。</span><span class="sxs-lookup"><span data-stu-id="f34c3-106">Whether the SIP trunk to an E9-1-1 Service Provider can be terminated on an existing Mediation Server pool or will require stand-alone Mediation Servers will depend on whether the E9-1-1 SBC can interact with a pool of Mediation Servers.</span></span> <span data-ttu-id="f34c3-107">詳細については、「 [M:N トランク In Lync Server 2013](lync-server-2013-m-n-trunk.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f34c3-107">For details, see [M:N trunk in Lync Server 2013](lync-server-2013-m-n-trunk.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

