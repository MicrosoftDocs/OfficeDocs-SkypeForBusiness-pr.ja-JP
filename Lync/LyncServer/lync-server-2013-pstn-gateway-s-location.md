---
title: 'Lync Server 2013: PSTN ゲートウェイの場所'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN gateway's location
ms:assetid: 49693a35-fad3-49ee-a71e-c7e4537b79aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994031(v=OCS.15)
ms:contentKeyID: 51803940
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef9c58115349e8fedaf25d6f8bc4e1991b65a963
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152311"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="pstn-gateways-location-in-lync-server-2013"></a>Lync Server 2013 の PSTN ゲートウェイの場所

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-03-09_

PSTN ゲートウェイおよび Pbx 経由でルーティングされる通話には、そのようなシステムの場所に応じて、場所に基づくルーティング制限が必要になることがあります。 場所に基づくルーティングは、トランクごとの粒度で有効にすることができます。

場所に基づくルーティングでは、トランクに対して有効になっている場合、次のルールセットが導入されます。

  - 場所に基づくルーティングがトランクごとに有効になっている場合、そのトランクで定義されたルールは、そのトランクを経由してルーティングされる通話にのみ適用されます。

  - Pstn ゲートウェイが配置されているネットワークサイトとは異なり、ネットワークサイトから呼び出しが行われる pstn かからないがバイパスされないようにするために、場所に基づいたルーティングによって、特定のトランクへのネットワークサイトの関連付けが導入されます。 これにより、特定のトランクに対して呼び出しをルーティングできるようにするネットワークサイトが定義されます。

トランクは、次の2つの方法で場所に基づくルーティングに対して有効にすることができます。

  - トランクは、pstn への通話を egresses する PSTN ゲートウェイに対して定義されています。 この種類のトランクによってルーティングされる着信呼び出しは、トランクと同じネットワークサイト内にあるエンドポイントにのみルーティングされます。

  - このトランクは、PSTN への通話を発信しない仲介サーバーピアに対して定義されており、固定の場所 (PBX 電話) で従来の電話を使用しているユーザーをサービスします。 この構成では、この種類のトランクによってルーティングされるすべての着信呼び出しは、トランクと同じネットワークサイトから発信されるものと見なされます。 PBX ユーザーからの呼び出しでは、トランクと同じネットワークサイトにある Lync ユーザーと同じ場所に基づいたルーティングの実施が行われます。 別のネットワークサイトにある2つの PBX システムが Lync Server を介して接続されている場合は、場所に基づくルーティングによって、あるネットワークサイト内の1つの PBX エンドポイントから別の PBX エンドポイントへのルーティングが可能になります。 このシナリオは、場所に基づくルーティングによってブロックされることはありません。 このシナリオだけでなく、同じ場所にある Lync ユーザーと同様の方法で、この構成の仲介サーバーピアに接続されているエンドポイントは、PSTN への通話をルーティングしない他の仲介サーバーピアとの通話を発信または受信できます。e.i は、仲介サーバーピアが関連付けられているネットワークサイトに関係なく、別の PBX に接続されたエンドポイントです。 PSTN エンドポイントを使用するすべての着信呼び出し、発信呼び出し、通話転送、および着信転送は、このような仲介サーバーピアのローカルとして定義されている PSTN ゲートウェイのみを使用するために、場所に基づいたルーティングの対象となります。

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での場所に基づくルーティングのガイダンス](lync-server-2013-guidance-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

