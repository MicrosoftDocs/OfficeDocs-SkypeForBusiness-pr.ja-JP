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
ms.openlocfilehash: af9fd674a83eed898eddc47f8cc95114a29d54b0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214547"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="inter-trunk-routing-in-lync-server-2013"></a>Lync Server 2013 でのトランク間ルーティング

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-08_

Lync Server 2013 には、トランク間ルーティングのサポートによる基本的なセッション管理が用意されています。 この新しい機能により、Lync Server は、下流のテレフォニーシステムへの通話コントロール機能を提供することができます。 トランク間ルーティングは IP-PBX と公衆交換電話網 (PSTN) ゲートウェイを相互に接続でき、それによって、構内交換機 (PBX) 電話機からの通話を PSTN にルーティングしたり、着信した PSTN の通話を PBX 電話機にルーティングしたりできます。 同様に、Lync Server は2つ以上の ip-pbx システムを相互接続して、さまざまな ip-pbx システムからの PBX 電話間で通話を送受信できるようにすることができます。

次の図は、PSTN ゲートウェイと ip-pbx の間の相互関係を提供する Lync Server 2013 を示しています。

![PSTN ゲートウェイまたは ip-pbx に接続する Lync Server](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "PSTN ゲートウェイまたは ip-pbx に接続する Lync Server")

次の図は、2つの ip-pbx システムを接続する Lync Server 2013 を示しています。

![Lync Server 相互による IP-PAX システムの図](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Lync Server 相互による IP-PAX システムの図")

</div>

<span> </span>

</div>

</div>

</div>

