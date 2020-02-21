---
title: 'Lync Server 2013: 着信呼び出し'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Incoming calls
ms:assetid: 65b9c1b4-6af7-4527-8c33-22c4442bd209
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994038(v=OCS.15)
ms:contentKeyID: 51803948
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c5a6cd54732bb6c33e358eeb1a5dbb72a1a4e789
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204750"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="incoming-calls-in-lync-server-2013"></a>Lync Server 2013 の着信呼び出し

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-03-09_

場所に基づくルーティングが有効になっているユーザーへの着信通話のルーティングは、ユーザーのエンドポイントの場所によって異なります。 着信呼び出しのルーティングには、次のような影響があります。 ユーザーが場所に基づくルーティングが有効なネットワークサイトにあるエンドポイントへの着信呼び出しを行い、エンドポイントが PSTN ゲートウェイと同じネットワークサイトにある場合、通話はルーティングされます。 ユーザーが場所に基づくルーティングが有効なネットワークサイトにあるエンドポイントへの着信呼び出しを行い、エンドポイントが PSTN ゲートウェイとは別のネットワークサイトにある場合、通話はルーティングされません。 着信呼び出しが行われている PSTN ゲートウェイと同じネットワークサイト内にエンドポイントが存在しない場合、着信呼び出しは直接ユーザーのボイスメールにルーティングされ、不在着信通知が呼び出し元に送信されます。

場所に基づくルーティングが有効になっているユーザーの着信転送設定は引き続き強制されますが、転送される呼び出しは、ユーザーの場所に基づいたルーティング制限の対象となります。

次の表は、呼び出し先のエンドポイントの場所に応じて、場所に基づくルーティングが着信呼び出しのルーティングにどのように影響するかを示しています。 PSTN ゲートウェイのネットワークサイトは、場所に基づいたルーティングに対して有効になっており、場所に基づくルーティングでは、同じネットワークサイト内のエンドポイントへの PSTN 通話のルーティングのみが許可されます。

### <a name="callee-receiving-an-inbound-call-from-the-pstn"></a>PSTN からの着信通話を受信する呼び出し先

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
<th>PSTN ゲートウェイと同じネットワークサイトにある呼び出し先のエンドポイント</th>
<th>呼び出し先のエンドポイントが PSTN ゲートウェイと同じネットワークサイトにありません</th>
<th>呼び出し先のエンドポイントが不明なネットワークサイトにあるか、または場所に基づくルーティングに対して有効になっていません</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>着信 PSTN 通話のルーティング</p></td>
<td><p>着信呼び出しは、呼び出し先のエンドポイントにルーティングされます。</p></td>
<td><p>着信呼び出しが、呼び出し先のエンドポイントにルーティングされない</p></td>
<td><p>着信呼び出しが、呼び出し先のエンドポイントにルーティングされない</p></td>
</tr>
</tbody>
</table>

  

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での場所に基づくルーティングのシナリオ](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

