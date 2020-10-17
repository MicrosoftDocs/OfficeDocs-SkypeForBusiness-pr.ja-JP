---
title: 'Lync Server 2013: 通話転送と着信転送'
description: 'Lync Server 2013: 通話転送と着信転送。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call transfers and call forwarding
ms:assetid: 978610ec-63c7-4cf6-ad7a-9ef91559bf12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994051(v=OCS.15)
ms:contentKeyID: 51803962
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d9359cb64b386d022eab33e4523dfaccf784075b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565253"
---
# <a name="call-transfers-and-call-forwarding-in-lync-server-2013"></a>Lync Server 2013 での通話転送と着信の転送

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-03-09_

PSTN エンドポイントが関係している場合、Location-Based ルーティングによって、calle のエンドポイントの場所と、呼び出しが転送または転送されるエンドポイント (移行先と転送先) が分析されます。 Location-Based ルーティングは、両方のエンドポイントの場所に応じて、通話を転送するか転送するかを決定します。

次の表は、PSTN エンドポイントを使用した通話での Lync ユーザーのシナリオと、Lync ユーザーが別の Lync ユーザーに通話を転送する例を示しています。 通話のエンドポイントのネットワークサイトの場所に応じて、Location-Based ルーティングは、通話の転送または転送のルーティングに影響します。

### <a name="initiating-call-transfer-or-forward"></a>着信転送または転送の開始

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>着信転送/転送を開始するユーザー</th>
<th>ターゲットエンドポイントが、着信転送または転送を開始したユーザーと同じネットワークサイトにある</th>
<th>転送先エンドポイントが別のネットワークサイトにある場合に、着信転送または着信転送を開始します。</th>
<th>ターゲットエンドポイントが不明なネットワークサイトにあるか、または Location-Based ルーティングで有効になっていないネットワークサイトにあります</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync ユーザー</p></td>
<td><p>着信/転送が許可されている</p></td>
<td><p>着信/転送は許可されていません</p></td>
<td><p>着信/転送は許可されていません</p></td>
</tr>
</tbody>
</table>

  

たとえば、PSTN エンドポイントを使用する Lync ユーザーは、同じネットワークサイトにある別の Lync ユーザーに通話を転送します。 この場合は、通話の転送が許可されます。

次の表は、別の Lync ユーザーとの通話での Lync ユーザーのシナリオと、その通話を PSTN エンドポイントに転送するユーザーの1人を示しています。 呼び出しが転送されるユーザーの場所に応じて、Location-Based ルーティングが通話に与える影響についての詳細を表に示します。

### <a name="call-transfer-or-forward-to-pstn-endpoint"></a>PSTN エンドポイントへの着信転送または転送

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>着信転送/転送エンドポイントのターゲット</th>
<th>同じネットワークサイト内の Lync ユーザー</th>
<th>異なるネットワークサイトにある Lync ユーザー</th>
<th>不明なネットワークサイトまたはネットワークサイト内の1つまたは両方の Lync ユーザーが、Location-Based ルーティングに対して有効になっていません</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PSTN エンドポイント</p></td>
<td><p>転送されたユーザーのサイトの音声ルーティングポリシーによって許可される通話転送または転送</p></td>
<td><p>転送されたユーザーのサイトの音声ルーティングポリシーによって許可される通話転送または転送</p></td>
<td><p>転送されたユーザーの音声ポリシーによって許可される通話転送または転送は、Location-Based ルーティングに対してトランクが有効になっていません。</p></td>
</tr>
</tbody>
</table>

  
たとえば、同じネットワークサイトにある別の Lync ユーザーとの通話で Lync ユーザーが通話を転送すると、通話転送が許可されます。

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での Location-Based ルーティングのシナリオ](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

