---
title: 'Lync Server 2013: 発信通話'
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
ms.openlocfilehash: 1a353cecbf1cdc1ff411c2cfe7c57edcd909c5c8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755641"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="outgoing-calls-in-lync-server-2013"></a>Lync Server 2013 の発信通話

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-03-09_

場所に基づくルーティングが有効になっているユーザーの発信通話のルーティングは、ユーザーのエンドポイントのネットワークの場所によって影響を受けます。 次の表では、呼び出し元のエンドポイントの場所に応じて、発信通話のルーティングが位置情報に基づくルーティングにどのように影響するかを示しています。

### <a name="caller-placing-an-outbound-call-to-the-pstn"></a>発信者から PSTN への発信通話

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>ユーザーのエンドポイントが、場所に基づくルーティングが有効なネットワーク サイトにある</th>
<th>ユーザーのエンドポイントが不明なネットワーク サイトまたは場所に基づくルーティングが有効でないネットワーク サイトにある</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>発信の承認</p></td>
<td><p>通話はユーザーの音声ポリシーに基づいて承認される</p></td>
<td><p>通話はユーザーの音声ポリシーに基づいて承認される</p></td>
</tr>
<tr class="even">
<td><p>発信通話のルーティング</p></td>
<td><p>通話はネットワーク サイトの音声ルーティング ポリシーに従ってルーティングされる</p></td>
<td><p>通話はユーザーの音声ポリシーに従い、場所に基づくルーティングが有効になっていないトランク (使用可能な場合) のみを経由してルーティングされる</p></td>
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

