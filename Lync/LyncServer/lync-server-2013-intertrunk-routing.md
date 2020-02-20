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
ms.openlocfilehash: ce206c0f20dc00c6abc1304db8c1f933cbefdbca
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145265"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="intertrunk-routing-in-lync-server-2013"></a>Lync Server 2013 でのトランク間ルーティング

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-20_

Lync Server 2013 は、PBX と公衆交換電話網 (PSTN) ゲートウェイを相互に接続して、PBX 電話からの通話を PSTN にルーティングし、PSTN 通話の着信を構内交換機 (PBX) 電話にルーティングすることができます。 同様に、Lync Server 2013 は2つ以上の ip-pbx システムを相互に接続して、異なる ip-pbx システムからの PBX 電話間で通話を発信および受信できるようにすることができます。

このトランク間ルーティング機能を構成するには、Lync Server 管理シェルコマンドレット**get-cstrunkconfiguration**を使用して、新しいパラメーターである PstnUsages を設定します。 このパラメーターでは、使用する一連の PSTN 使用法レコードを指定します。 トランクはこの PSTN 使用法を使用して、ルートを決定し、それに従って着信したすべての通話をルーティングします。

    Set-CsTrunkConfiguration -Identity <TrunkId> -PstnUsages @{add="<UsageString>"}

次の図は、PSTN ゲートウェイと ip-pbx の間の相互関係を提供する Lync Server 2013 を示しています。

**ゲートウェイと IP PBX の間のトランク間ルーティング**

![PSTN ゲートウェイまたは ip-pbx に接続する Lync Server](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "PSTN ゲートウェイまたは ip-pbx に接続する Lync Server")

次の図は、Lync Server 2013 相互に2つの ip-pbx システムを相互に相互に相互に相互に相互に相互に相互に

**2 つの IP PBX 間のトランク間ルーティング**

![Lync Server 相互による IP-PAX システムの図](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Lync Server 相互による IP-PAX システムの図")

</div>

<span> </span>

</div>

</div>

</div>

