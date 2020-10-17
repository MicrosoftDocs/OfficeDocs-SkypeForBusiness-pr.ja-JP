---
title: 'Lync Server 2013: トランク間ルーティング'
description: 'Lync Server 2013: トランク間ルーティング。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Intertrunk routing
ms:assetid: d3a33b4a-8bf4-4a8c-a371-8ef79e740780
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205272(v=OCS.15)
ms:contentKeyID: 48185442
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 30c838ee94a2df0807195c172d7e2a3a393523af
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553143"
---
# <a name="intertrunk-routing-in-lync-server-2013"></a><span data-ttu-id="b6efa-103">Lync Server 2013 でのトランク間ルーティング</span><span class="sxs-lookup"><span data-stu-id="b6efa-103">Intertrunk routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b6efa-104">_**トピックの最終更新日:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="b6efa-104">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="b6efa-105">Lync Server 2013 は、PBX と公衆交換電話網 (PSTN) ゲートウェイを相互に接続して、PBX 電話からの通話を PSTN にルーティングし、PSTN 通話の着信を構内交換機 (PBX) 電話にルーティングすることができます。</span><span class="sxs-lookup"><span data-stu-id="b6efa-105">Lync Server 2013 can interconnect an IP-PBX to a public switched telephone network (PSTN) gateway so that calls from a PBX phone can be routed to the PSTN, and incoming PSTN calls can be routed to a private branch exchange (PBX) phone.</span></span> <span data-ttu-id="b6efa-106">同様に、Lync Server 2013 は2つ以上の ip-pbx システムを相互に接続して、異なる ip-pbx システムからの PBX 電話間で通話を発信および受信できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="b6efa-106">Similarly, Lync Server 2013 can interconnect two or more IP-PBX systems so that calls can be placed and received between PBX phones from the different IP-PBX systems.</span></span>

<span data-ttu-id="b6efa-107">このトランク間ルーティング機能を構成するには、Lync Server 管理シェルコマンドレット **get-cstrunkconfiguration**を使用して、新しいパラメーターである PstnUsages を設定します。</span><span class="sxs-lookup"><span data-stu-id="b6efa-107">This intertrunk routing feature can be configured by using the Lync Server Management Shell cmdlet, **Set-CsTrunkConfiguration**, with the new parameter, PstnUsages.</span></span> <span data-ttu-id="b6efa-108">このパラメーターでは、使用する一連の PSTN 使用法レコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="b6efa-108">This parameter specifies the set of PSTN usage records to use.</span></span> <span data-ttu-id="b6efa-109">トランクはこの PSTN 使用法を使用して、ルートを決定し、それに従って着信したすべての通話をルーティングします。</span><span class="sxs-lookup"><span data-stu-id="b6efa-109">A trunk uses this PSTN usage to determine a route and to route all incoming calls accordingly.</span></span>

    Set-CsTrunkConfiguration -Identity <TrunkId> -PstnUsages @{add="<UsageString>"}

<span data-ttu-id="b6efa-110">次の図は、PSTN ゲートウェイと ip-pbx の間の相互関係を提供する Lync Server 2013 を示しています。</span><span class="sxs-lookup"><span data-stu-id="b6efa-110">The following diagram illustrates Lync Server 2013 providing interconnectivity between a PSTN gateway and an IP-PBX.</span></span>

<span data-ttu-id="b6efa-111">**ゲートウェイと IP PBX の間のトランク間ルーティング**</span><span class="sxs-lookup"><span data-stu-id="b6efa-111">**Intertrunk routing between gateway and IP PBX**</span></span>

<span data-ttu-id="b6efa-112">![PSTN ゲートウェイまたは ip-pbx に接続する Lync Server](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "PSTN ゲートウェイまたは ip-pbx に接続する Lync Server")</span><span class="sxs-lookup"><span data-stu-id="b6efa-112">![Lync Server connecting PSTN gateway/IP-PBX diagram](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "Lync Server connecting PSTN gateway/IP-PBX diagram")</span></span>

<span data-ttu-id="b6efa-113">次の図は、Lync Server 2013 相互に2つの ip-pbx システムを相互に相互に相互に相互に相互に相互に相互に</span><span class="sxs-lookup"><span data-stu-id="b6efa-113">The following diagram illustrates Lync Server 2013 interconnecting two IP-PBX systems.</span></span>

<span data-ttu-id="b6efa-114">**2 つの IP PBX 間のトランク間ルーティング**</span><span class="sxs-lookup"><span data-stu-id="b6efa-114">**Intertrunk routing between two IP PBXs**</span></span>

<span data-ttu-id="b6efa-115">![Lync Server 相互による IP-PAX システムの図](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Lync Server 相互による IP-PAX システムの図")</span><span class="sxs-lookup"><span data-stu-id="b6efa-115">![Lync Server interconnecting IP-PAX systems diagram](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Lync Server interconnecting IP-PAX systems diagram")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

