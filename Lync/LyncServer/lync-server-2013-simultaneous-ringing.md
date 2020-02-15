---
title: 'Lync Server 2013: 同時呼び出し'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Simultaneous ringing
ms:assetid: df02f919-4d50-4832-9300-6c51f8b4fc56
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994079(v=OCS.15)
ms:contentKeyID: 51803990
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e3104da5e7d351bda26698087e97106cafbdff4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037507"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="simultaneous-ringing-in-lync-server-2013"></a>Lync Server 2013 での同時呼び出し

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-03-09_

呼び出し先に同時呼び出しが有効になっている場合、場所に基づくルーティングによって、呼び出し元の場所と、呼び出された相手のエンドポイントが分析され、呼び出しがルーティングされるかどうかが判断されます。

次の表は、ユーザーが同時呼び出しを使用して構成されており、同時呼び出し先が、同じネットワークサイト、別のネットワークサイト、または不明なネットワークサイト内のユーザーであることを示しています。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>の PSTN 通話の着信</th>
<th>呼び出し先と同じネットワークサイトに配置されている</th>
<th>呼び出し先が異なるネットワークサイトにある</th>
<th>不明なネットワークサイトに配置されているか、場所に基づくルーティングが有効になっていません</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync ユーザー</p></td>
<td><p>同時呼び出し許可</p></td>
<td><p>同時呼び出しを許可しない</p></td>
<td><p>同時呼び出しを許可しない</p></td>
</tr>
</tbody>
</table>

  
次の表は、同一のネットワークサイト、別のネットワークサイト、または不明なネットワークサイトにある Lync ユーザー (Lync 発信者) からの呼び出しを示しています。 呼び出し先には、同時呼び出しのターゲットとして構成されている PSTN エンドポイント (携帯電話) があります。 このシナリオでは、場所に基づくルーティングによって、呼び出し先 (携帯電話) の同時呼び出し先 (つまり、) に通話をルーティングする必要があるかどうかが判断されます。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>同時呼び出しのターゲット</th>
<th>呼び出し先と同じネットワークサイトに配置されている</th>
<th>呼び出し先が異なるネットワークサイトにある</th>
<th>不明なネットワークサイトに配置されているか、場所に基づくルーティングが有効になっていません</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PSTN エンドポイント</p></td>
<td><p>発信者のサイトの音声ルーティングポリシーを使用して同時呼び出しが許可される</p></td>
<td><p>発信者のサイトの音声ルーティングポリシーを使用して同時呼び出しが許可される</p></td>
<td><p>発信者の音声ポリシーによって、場所に基づくルーティングが有効になっていないトランクに対して同時呼び出しが許可されている</p></td>
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

