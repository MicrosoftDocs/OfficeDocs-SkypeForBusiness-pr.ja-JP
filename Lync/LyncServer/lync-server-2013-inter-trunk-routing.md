---
title: 'Lync Server 2013: トランク間ルーティング'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Inter-trunk routing
ms:assetid: f687a548-1f2e-48ed-9745-a13dc1f3698f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721940(v=OCS.15)
ms:contentKeyID: 49733877
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 37a9feb818f48317f9a3dddd78a70700e3f6ccfc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725847"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="inter-trunk-routing-in-lync-server-2013"></a><span data-ttu-id="08eea-102">Lync Server 2013 のクロストランクルーティング</span><span class="sxs-lookup"><span data-stu-id="08eea-102">Inter-trunk routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="08eea-103">_**最終更新日:** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="08eea-103">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="08eea-104">Lync Server 2013 は、intertrunk ルーティングのサポートによって基本的なセッション管理を提供します。</span><span class="sxs-lookup"><span data-stu-id="08eea-104">Lync Server 2013 provides basic session management through the support of intertrunk routing.</span></span> <span data-ttu-id="08eea-105">この新しい機能により、Lync Server は、下流のテレフォニーシステムへの通話コントロール機能を提供できるようになります。</span><span class="sxs-lookup"><span data-stu-id="08eea-105">This new capability enables Lync Server to provide call control functionalities to downstream telephony systems.</span></span> <span data-ttu-id="08eea-106">トランク間ルーティングは IP-PBX と公衆交換電話網 (PSTN) ゲートウェイを相互に接続でき、それによって、構内交換機 (PBX) 電話機からの通話を PSTN にルーティングしたり、着信した PSTN の通話を PBX 電話機にルーティングしたりできます。</span><span class="sxs-lookup"><span data-stu-id="08eea-106">Intertrunk routing can interconnect an IP-PBX to a public switched telephone network (PSTN) gateway so that calls from a private branch exchange (PBX) phone can be routed to the PSTN, and incoming PSTN calls can be routed to a PBX phone.</span></span> <span data-ttu-id="08eea-107">同様に、Lync Server は2つ以上の IP PBX システムを相互接続して、複数の IP PBX システムから PBX 電話間で通話を発信および受信することができます。</span><span class="sxs-lookup"><span data-stu-id="08eea-107">Similarly, Lync Server can interconnect two or more IP-PBX systems so that calls can be placed and received between PBX phones from the different IP-PBX systems.</span></span>

<span data-ttu-id="08eea-108">次の図は、PSTN ゲートウェイと ip-pbx の間の相互攻撃を実現する Lync Server 2013 を示しています。</span><span class="sxs-lookup"><span data-stu-id="08eea-108">The following figure illustrates Lync Server 2013 providing interconnectivity between a PSTN gateway and an IP-PBX.</span></span>

<span data-ttu-id="08eea-109">![Lync Server、PSTN ゲートウェイ/IP-PBX の接続図](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "Lync Server、PSTN ゲートウェイ/IP-PBX の接続図")</span><span class="sxs-lookup"><span data-stu-id="08eea-109">![Lync Server connecting PSTN gateway/IP-PBX diagram](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "Lync Server connecting PSTN gateway/IP-PBX diagram")</span></span>

<span data-ttu-id="08eea-110">次の図は、2つの IP PBX システムを接続する Lync Server 2013 を示しています。</span><span class="sxs-lookup"><span data-stu-id="08eea-110">The next figure illustrates Lync Server 2013 connecting two IP-PBX systems.</span></span>

<span data-ttu-id="08eea-111">![Lync Server、IP-PAX システムの相互接続図](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Lync Server、IP-PAX システムの相互接続図")</span><span class="sxs-lookup"><span data-stu-id="08eea-111">![Lync Server interconnecting IP-PAX systems diagram](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Lync Server interconnecting IP-PAX systems diagram")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

