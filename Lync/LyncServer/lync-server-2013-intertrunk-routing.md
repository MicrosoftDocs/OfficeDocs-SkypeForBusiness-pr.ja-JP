---
title: 'Lync Server 2013: トランク間ルーティング'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Intertrunk routing
ms:assetid: d3a33b4a-8bf4-4a8c-a371-8ef79e740780
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205272(v=OCS.15)
ms:contentKeyID: 48185442
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c1b66ea04ed72bab6d33114f52fa9fe96364b48
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832955"
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

![PSTN ゲートウェイ/IP-PBX 図を接続]している Lync Server(images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "PSTN ゲートウェイ/IP-PBX 図を接続")している Lync Server

次の図は、2つの IP PBX システムでの Lync Server 2013 相互の相互に対応しています。

**2つの IP Pbx 間での intertrunk ルーティング**

![Lync Server の相互に対応する IP PAX システム図](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Lync Server の相互に対応する IP PAX システム図")

</div>

<span> </span>

</div>

</div>

</div>

