---
title: 'Lync Server 2013: PSTN ゲートウェイの場所'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: PSTN gateway's location
ms:assetid: 49693a35-fad3-49ee-a71e-c7e4537b79aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994031(v=OCS.15)
ms:contentKeyID: 51803940
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b897d9ce438844cde7617bb7c3e1dae086605f09
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823547"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-gateways-location-in-lync-server-2013"></a>Lync Server 2013 の PSTN ゲートウェイの場所

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-03-09_

PSTN ゲートウェイと Pbx 経由の通話には、そのシステムの場所に応じて位置情報に基づくルーティング制限が必要になることがあります。 位置情報に基づくルーティングは、トランクごとに細分度で有効にすることができます。

場所に基づくルーティングでは、トランクで有効にすると、次のルールが設定されます。

  - 1回のトランクで位置情報に基づくルーティングが有効になっている場合、そのトランクで定義されたルールは、そのトランクでルーティングされる通話にのみ適用されます。

  - Pstn tolls が、PSTN ゲートウェイが配置されているネットワークサイトとは異なるネットワークサイトから発信される場合は、場所に基づくルーティングによって、ネットワークサイトと特定のトランクとの関連付けが行われます。 これにより、特定のトランクへの通話のルーティングを許可するネットワーク サイトが定義されます。

Trunks ベースのルーティングの場合、次の2つの方法でを有効にすることができます。

  - トランクは、通話を PSTN に退出させる PSTN ゲートウェイに対して定義されています。この種のトランクによってルーティングされた着信通話は、トランクと同じネットワーク サイト内にあるエンドポイントにのみルーティングされます。

  - トランクは、PSTN に着信を転送しない仲介サーバーピアに対して定義されます。これは、固定の場所 (PBX 電話) で従来の電話を使用しているユーザーを対象としています。 このような特定の構成の場合、この種のトランクによってルーティングされたすべての着信通話は、トランクと同じネットワーク サイトから発信されていると見なされます。 PBX ユーザーからの通話では、トランクと同じネットワークサイトに配置されている Lync ユーザーと同じ場所に基づくルーティングが適用されます。 別々のネットワークサイトに配置されている2つの PBX システムが Lync Server 経由で接続されている場合、場所に基づくルーティングによって、あるネットワークサイトの1つの PBX エンドポイントから別のネットワークサイトの別の PBX エンドポイントへのルーティングが許可されます。 このシナリオは、位置に基づくルーティングによってブロックされることはありません。 このシナリオに加えて、同じ場所の Lync ユーザーと同じように、この構成の仲介サーバーピアに接続されたエンドポイントは、PSTN への通話をルーティングしない他の仲介サーバーピアとの間での通話の発信と受信を行うことができます。e: 仲介サーバーピアが関連付けられているネットワークサイトに関係なく、別の PBX に接続されているエンドポイント。 PSTN エンドポイントを含むすべての着信通話、発信通話、通話転送、通話転送には、位置に基づくルーティングが適用されます。この仲介サーバーピアのローカルとして定義されている PSTN ゲートウェイのみを使用します。

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 の場所に基づくルーティングのガイダンス](lync-server-2013-guidance-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

