---
title: 'Lync Server 2013: 送信呼び出し'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Outgoing calls
ms:assetid: 885ffe6f-cd51-4f21-8d4f-a1ff8d818858
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994049(v=OCS.15)
ms:contentKeyID: 51803960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ca0cdc7781143b0e76ff83a980f00da58c814f02
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049569"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="outgoing-calls-in-lync-server-2013"></a>Lync Server 2013 の送信呼び出し

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-03-09_

場所に基づくルーティングが有効になっているユーザーの発信呼び出しのルーティングは、ユーザーのエンドポイントのネットワーク上の場所によって影響を受けます。 次の表は、発信者のエンドポイントの場所に応じて、場所に基づくルーティングが発信呼び出しのルーティングにどのように影響するかを示しています。

### <a name="caller-placing-an-outbound-call-to-the-pstn"></a>発信者が PSTN への発信通話を配置する

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>場所に基づくルーティングが有効なネットワークサイトに配置されたユーザーエンドポイント</th>
<th>不明なネットワークサイトにある、または場所に基づくルーティングが有効になっていないユーザーエンドポイント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>発信呼び出しの承認</p></td>
<td><p>通話はユーザーの音声ポリシーに基づいて承認されます。</p></td>
<td><p>通話はユーザーの音声ポリシーに基づいて承認されます。</p></td>
</tr>
<tr class="even">
<td><p>発信通話のルーティング</p></td>
<td><p>呼び出しは、ネットワークサイトの音声ルーティングポリシーに従ってルーティングされます。</p></td>
<td><p>通話はユーザーの音声ポリシーに従ってルーティングされ、場所に基づくルーティングが有効になっていない場合にのみトランクによってルーティングされます (使用可能な場合)。</p></td>
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

