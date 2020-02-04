---
title: 'Lync Server 2013: トランク間ルーティング'
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
ms.openlocfilehash: eaa41fe229e9246506fd92eb9f48767994997e4e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725677"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="intertrunk-routing-in-lync-server-2013"></a>Lync Server 2013 のトランク間ルーティング

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-20_

Lync Server 2013 は、IP PBX を公衆交換電話網 (PSTN) ゲートウェイに接続して、PBX 携帯電話からの通話を PSTN にルーティングし、着信 PSTN 通話を構内交換機 (PBX) 電話にルーティングすることができます。 同様に、Lync Server 2013 は2つ以上の IP PBX システムを相互接続して、さまざまな IP PBX システムからの PBX 電話間で通話を発信および受信できるようにすることができます。

このクロストランクルーティング機能を構成するには、Lync Server Management Shell コマンドレット**set-cstrunkconfiguration**を使用して、新しいパラメーター PstnUsages を設定します。 このパラメーターは、使用する PSTN 利用状況レコードのセットを指定します。 トランクはこの PSTN 使用法を使ってルートを特定し、着信通話をすべてルーティングします。

    Set-CsTrunkConfiguration -Identity <TrunkId> -PstnUsages @{add="<UsageString>"}

次の図は、PSTN ゲートウェイと ip-pbx の間の相互に通信できる Lync Server 2013 を示しています。

**ゲートウェイと IP PBX 間の intertrunk ルーティング**

![Lync Server、PSTN ゲートウェイ/IP-PBX の接続図](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "Lync Server、PSTN ゲートウェイ/IP-PBX の接続図")

次の図は、2つの IP PBX システムでの Lync Server 2013 相互の相互に対応しています。

**2つの IP Pbx 間での intertrunk ルーティング**

![Lync Server、IP-PAX システムの相互接続図](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Lync Server、IP-PAX システムの相互接続図")

</div>

<span> </span>

</div>

</div>

</div>

