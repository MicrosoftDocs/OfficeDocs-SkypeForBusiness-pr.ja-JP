---
title: 'Lync Server 2013: トランク間ルーティング'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Inter-trunk routing
ms:assetid: f687a548-1f2e-48ed-9745-a13dc1f3698f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721940(v=OCS.15)
ms:contentKeyID: 49733877
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 204402ba6620fa75b64bb9710ce979b44b63f412
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832959"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="inter-trunk-routing-in-lync-server-2013"></a>Lync Server 2013 のクロストランクルーティング

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-08_

Lync Server 2013 は、intertrunk ルーティングのサポートによって基本的なセッション管理を提供します。 この新しい機能により、Lync Server は、下流のテレフォニーシステムへの通話コントロール機能を提供できるようになります。 トランク間ルーティングは IP-PBX と公衆交換電話網 (PSTN) ゲートウェイを相互に接続でき、それによって、構内交換機 (PBX) 電話機からの通話を PSTN にルーティングしたり、着信した PSTN の通話を PBX 電話機にルーティングしたりできます。 同様に、Lync Server は2つ以上の IP PBX システムを相互接続して、複数の IP PBX システムから PBX 電話間で通話を発信および受信することができます。

次の図は、PSTN ゲートウェイと ip-pbx の間の相互攻撃を実現する Lync Server 2013 を示しています。

![PSTN ゲートウェイ/IP-PBX 図を接続]している Lync Server(images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "PSTN ゲートウェイ/IP-PBX 図を接続")している Lync Server

次の図は、2つの IP PBX システムを接続する Lync Server 2013 を示しています。

![Lync Server の相互に対応する IP PAX システム図](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Lync Server の相互に対応する IP PAX システム図")

</div>

<span> </span>

</div>

</div>

</div>

