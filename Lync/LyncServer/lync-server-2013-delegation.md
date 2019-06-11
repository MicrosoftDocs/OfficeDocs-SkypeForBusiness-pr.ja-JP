---
title: 'Lync Server 2013: 委任'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delegation
ms:assetid: 89e76e5c-3cfb-4504-8d0d-7509c8ba9815
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994045(v=OCS.15)
ms:contentKeyID: 51803956
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82be0bdc382440cc8a4307dc0ba981f31c5a9313
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833660"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delegation-in-lync-server-2013"></a>Lync Server 2013 の委任

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-03-09_

Lync の委任機能は、次のような方法で位置情報に基づくルーティングによって影響を受けます。

  - 位置情報に基づくルーティングを有効にした代理人が管理者の代わりに通話を発信する場合、代理人のボイスポリシーを使って通話を承認し、代理人のサイトボイスルーティングポリシーを使って通話をルーティングします。

  - マネージャーへの着信 PSTN 通話については、通話の転送または同時呼び出しに適用されるのと同じルールが適用されます (着信の転送と通話の転送および同時呼び出しのトピックを参照してください)。

  - 代理人がマネージャーへの着信通話に対して PSTN エンドポイントを同時呼び出しターゲットとして設定すると、代理人の PSTN エンドポイントへの通話のルーティングに、受信トランクに関連付けられたサイトの音声ルーティング ポリシーが使用されます。

  - 委任に関して、通常はマネージャーとその関連付けられた代理人を同じネットワーク サイトに配置することをお勧めします。

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 の場所に基づくルーティングのシナリオ](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

