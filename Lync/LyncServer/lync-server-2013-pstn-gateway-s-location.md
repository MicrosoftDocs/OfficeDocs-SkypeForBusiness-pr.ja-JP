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
ms.openlocfilehash: 29898244dc0e54da2586d0a58212148c493b96db
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512444"
---
# <a name="pstn-gateways-location-in-lync-server-2013"></a>Lync Server 2013 の PSTN ゲートウェイの場所

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-03-09_

PSTN ゲートウェイおよび Pbx 経由でルーティングされる通話には、そのようなシステムの場所に応じて Location-Based ルーティング制限が必要になることがあります。 Location-Based ルーティングは、トランクごとの粒度で有効にすることができます。

Location-Based ルーティングは、トランクに対して有効になっている場合に次のルールセットを導入します。

  - Location-Based ルーティングがトランクごとに有効になっている場合、そのトランクで定義されたルールは、そのトランク経由でルーティングされる通話にのみ適用されます。

  - Pstn ゲートウェイが存在するネットワークサイトとは異なるように、ネットワークサイトから呼び出しが行われる pstn かからないがバイパスされないようにするために、Location-Based ルーティングでは、特定のトランクへのネットワークサイトの関連付けを導入します。 これにより、特定のトランクに対して呼び出しをルーティングできるようにするネットワークサイトが定義されます。

トランクは、次の2つの方法で Location-Based ルーティングに対して有効にすることができます。

  - トランクは、pstn への通話を egresses する PSTN ゲートウェイに対して定義されています。 この種類のトランクによってルーティングされる着信呼び出しは、トランクと同じネットワークサイト内にあるエンドポイントにのみルーティングされます。

  - このトランクは、PSTN への通話を発信しない仲介サーバーピアに対して定義されており、固定の場所 (PBX 電話) で従来の電話を使用しているユーザーをサービスします。 この構成では、この種類のトランクによってルーティングされるすべての着信呼び出しは、トランクと同じネットワークサイトから発信されるものと見なされます。 PBX ユーザーからの呼び出しでは、トランクと同じネットワークサイトにある Lync ユーザーと同じ Location-Based ルーティング強制が適用されます。 別のネットワークサイトにある2つの PBX システムが Lync Server を介して接続されている場合、Location-Based ルーティングによって、あるネットワークサイト内の1つの PBX エンドポイントから別の PBX エンドポイントへのルーティングができます。 このシナリオは Location-Based ルーティングによってブロックされることはありません。 このシナリオだけでなく、同じ場所にある Lync ユーザーと同様の方法で、この構成の仲介サーバーピアに接続されているエンドポイントは、仲介サーバーピアが関連付けられているネットワークサイトに関係なく、PSTN (つまり、別の PBX に接続されているエンドポイント) に対して通話を発信または受信できません。 PSTN エンドポイントを使用するすべての着信呼び出し、発信呼び出し、通話転送、および着信転送は、このような仲介サーバーピアのローカルとして定義されている PSTN ゲートウェイのみを使用するために、場所に基づいたルーティングの対象となります。

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での Location-Based ルーティングに関するガイダンス](lync-server-2013-guidance-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

