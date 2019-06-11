---
title: 'Lync Server 2013: 通話転送と着信転送'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Call transfers and call forwarding
ms:assetid: 978610ec-63c7-4cf6-ad7a-9ef91559bf12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994051(v=OCS.15)
ms:contentKeyID: 51803962
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6d5b0661cfaaef2e514f070260f44abc4ea00572
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840685"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-transfers-and-call-forwarding-in-lync-server-2013"></a>Lync Server 2013 の通話転送と着信転送

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-03-09_

PSTN エンドポイントが関与している場合は、位置情報に基づくルーティングによって、calle のエンドポイントの位置と、通話が転送または転送されるエンドポイント (転送/転送ターゲット) が分析されます。 位置に基づくルーティングは、両方のエンドポイントの場所に応じて、通話を転送するか転送するかを決定します。

次の表は、PSTN エンドポイントを使用した通話での Lync ユーザーのシナリオと、Lync ユーザーが別の Lync ユーザーに通話を転送するシナリオを示しています。 Transferee のエンドポイントのネットワークサイトの場所に応じて、位置ベースのルーティングは、通話転送または転送のルーティングに影響します。

### <a name="initiating-call-transfer-or-forward"></a>通話転送または着信転送の開始

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>通話転送または着信転送を開始するユーザー</th>
<th>ターゲット エンドポイントが、通話転送または着信転送を開始するユーザーと同じネットワーク サイトにある</th>
<th>ターゲット エンドポイントが、通話転送または着信転送を開始するユーザーとは別のネットワーク サイトにある</th>
<th>ターゲットエンドポイントが不明なネットワークサイトにあるか、または場所ベースのルーティングで有効でないネットワークサイトにある</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync ユーザー</p></td>
<td><p>通話または着信を転送できます。</p></td>
<td><p>通話または着信を転送できません。</p></td>
<td><p>通話または着信を転送できません。</p></td>
</tr>
</tbody>
</table>

  

たとえば、PSTN エンドポイントでの Lync ユーザーは、同じネットワークサイト内の別の Lync ユーザーに通話を転送します。 この場合、通話の転送が許可されます。

次の表は、別の Lync ユーザーとの通話での Lync ユーザーのシナリオと、いずれかのユーザーが通話を PSTN エンドポイントに転送するシナリオを示しています。 一方のユーザーが通話を PSTN エンドポイントに転送した場合に、通話の転送先ユーザーの場所によって、場所に基づくルーティングが通話にどのように影響するかを表しています。

### <a name="call-transfer-or-forward-to-pstn-endpoint"></a>PSTN エンドポイントへの通話転送または着信転送

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>通話/着信転送エンドポイント ターゲット</th>
<th>同じネットワークサイト内の Lync ユーザー</th>
<th>異なるネットワークサイトの Lync ユーザー</th>
<th>不明のネットワークサイトまたはネットワークサイト内の一方または両方の Lync ユーザーが位置情報に基づくルーティングを有効にしていない</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PSTN エンドポイント</p></td>
<td><p>転送先ユーザーのサイトの音声ルーティング ポリシーによって、通話または着信の転送が許可される</p></td>
<td><p>転送先ユーザーのサイトの音声ルーティング ポリシーによって、通話または着信の転送が許可される</p></td>
<td><p>通話または着信の転送は、転送先ユーザーの音声ポリシーによって、場所に基づくルーティングが有効になっていないトランクのみを経由して許可される</p></td>
</tr>
</tbody>
</table>

  
たとえば、同じネットワークサイト内の別の Lync ユーザーとの通話で Lync ユーザーが通話を PSTN エンドポイントに転送し、通話転送が許可されているとします。

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 の場所に基づくルーティングのシナリオ](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

