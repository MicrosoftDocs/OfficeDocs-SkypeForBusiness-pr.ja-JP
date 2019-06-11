---
title: 'Lync Server 2013: 着信通話'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Incoming calls
ms:assetid: 65b9c1b4-6af7-4527-8c33-22c4442bd209
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994038(v=OCS.15)
ms:contentKeyID: 51803948
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c007fbaec317a8e9d9d374ea62dafcab6c7a63f4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833015"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="incoming-calls-in-lync-server-2013"></a>Lync Server 2013 着信通話

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-03-09_

場所に基づくルーティングが有効になっているユーザーに対する着信のルーティングは、ユーザーのエンドポイントの場所によって異なります。 着信通話のルーティングは、次のように影響されます。 ユーザーが位置情報に基づくルーティングが有効になっているネットワークサイト内のエンドポイントに対して着信した場合、そのエンドポイントが PSTN ゲートウェイと同じネットワークサイト内にある場合は、通話がルーティングされます。 ユーザーが位置情報に基づくルーティングが有効になっているネットワークサイトにあるエンドポイントへの着信通話を使用していて、そのエンドポイントが PSTN ゲートウェイとは異なるネットワークサイトにある場合、通話はルーティングされません。 着信通話の発信元の PSTN ゲートウェイと同じネットワーク サイトにエンドポイントがない場合、着信通話はユーザーのボイスメールに直接ルーティングされ、不在着信通知が呼び出し先に送信されます。

位置情報に基づくルーティングが有効になっているユーザーの着信の転送設定は引き続き適用されますが、転送された通話には、ユーザーの位置情報に基づくルーティングの制限が適用されます。

次の表は、位置情報に基づくルーティングが、呼び出し元のエンドポイントの場所に応じて着信呼び出しのルーティングにどのように影響するかを示しています。 PSTN ゲートウェイのネットワークサイトが位置情報に基づくルーティングに対応しており、位置情報に基づくルーティングでは、同じネットワークサイト内のエンドポイントへの PSTN 通話のルーティングのみを許可します。

### <a name="callee-receiving-an-inbound-call-from-the-pstn"></a>呼び出し先が PSTN から着信通話を受信する

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>呼び出し先のエンドポイントが PSTN ゲートウェイと同じネットワーク サイトにある</th>
<th>呼び出し先のエンドポイントが PSTN ゲートウェイと同じネットワーク サイトにない</th>
<th>呼び出し先のエンドポイントが不明なネットワーク サイトにある、または場所に基づくルーティングが有効になっていない</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>着信 PSTN 通話のルーティング</p></td>
<td><p>着信通話は呼び出し先のエンドポイントにルーティングされる</p></td>
<td><p>着信通話は呼び出し先のエンドポイントにルーティングされない</p></td>
<td><p>着信通話は呼び出し先のエンドポイントにルーティングされない</p></td>
</tr>
</tbody>
</table>

  

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 の場所に基づくルーティングのシナリオ](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

