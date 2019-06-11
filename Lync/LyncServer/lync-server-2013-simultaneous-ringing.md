---
title: 'Lync Server 2013: 同時呼び出し'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Simultaneous ringing
ms:assetid: df02f919-4d50-4832-9300-6c51f8b4fc56
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994079(v=OCS.15)
ms:contentKeyID: 51803990
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7303c1fc77d109bd08044c8acff56aaf538790d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848724"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="simultaneous-ringing-in-lync-server-2013"></a>Lync Server 2013 での同時呼び出し

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-03-09_

通話先の相手が同時呼び出しを有効にしている場合、位置情報に基づくルーティングは、通話をルーティングする必要があるかどうかを判断するために、発信元の場所と、通話相手のエンドポイントを分析します。

次の表は、同時呼び出しが構成されたユーザーを示します。同時呼び出しのターゲット ユーザーは、同じネットワーク サイトのユーザー、異なるネットワーク サイトのユーザー、または不明なネットワーク サイトのユーザーです。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>PSTN 着信の対象</th>
<th>呼び出し先と同じネットワーク サイトにある</th>
<th>呼び出し先とは別のネットワーク サイトにある</th>
<th>不明のネットワークサイトに配置されているか、位置情報に基づくルーティング用に有効になっていない</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync ユーザー</p></td>
<td><p>同時呼び出しが許可される</p></td>
<td><p>同時呼び出しは許可されない</p></td>
<td><p>同時呼び出しは許可されない</p></td>
</tr>
</tbody>
</table>

  
次の表は、同じネットワークサイト、別のネットワークサイト、または不明なネットワークサイトの Lync ユーザー (Lync 発信者) からの通話の例を示しています。 呼び出し先には、同時呼び出しのターゲット ユーザーとして、PSTN エンドポイント (携帯電話) が構成されています。 このシナリオでは、位置情報に基づくルーティングによって、呼び出し元の同時呼び出しターゲット (携帯電話) に呼び出しをルーティングするかどうかが決定されます。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>同時呼び出しのターゲット ユーザー</th>
<th>呼び出し先と同じネットワーク サイトにある</th>
<th>呼び出し先とは別のネットワーク サイトにある</th>
<th>不明のネットワークサイトに配置されているか、位置情報に基づくルーティング用に有効になっていない</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PSTN エンドポイント</p></td>
<td><p>呼び出し元のサイトの音声ルーティング ポリシーによって同時呼び出しが許可される</p></td>
<td><p>呼び出し元のサイトの音声ルーティング ポリシーによって同時呼び出しが許可される</p></td>
<td><p>場所に基づくルーティングが有効になっていないトランクへの呼び出し元の音声ポリシーによって同時呼び出しが許可される</p></td>
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

