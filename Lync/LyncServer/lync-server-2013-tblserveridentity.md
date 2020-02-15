---
title: 'Lync Server 2013: tblServerIdentity'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblServerIdentity
ms:assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558648(v=OCS.15)
ms:contentKeyID: 48184125
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5f6ed7f0eed08dbb4ab3b0d6f41c9ec91fb719f1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029188"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblserveridentity-in-lync-server-2013"></a>Lync Server 2013 の tblServerIdentity

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-12_

tblServerIdentity には、常設チャットサーバープール内のアクティブなチャットサーバーが含まれています。

### <a name="columns"></a>Columns

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>列</th>
<th>種類</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>serverID</p></td>
<td><p>NULL でない int</p></td>
<td><p>サーバー ID。 中央管理ストアのインスタンス ID に対応します。</p></td>
</tr>
<tr class="even">
<td><p>serverAddress</p></td>
<td><p>NULL でない nvarchar (256)</p></td>
<td><p>Windows Communication Foundation アドレスを使用したサーバー アドレス。</p></td>
</tr>
<tr class="odd">
<td><p>Serverlastping Time</p></td>
<td><p>日付型</p></td>
<td><p>チャネル サーバーが、実行中であることを示すためにこの行を更新した最新時刻。</p></td>
</tr>
</tbody>
</table>


### <a name="key"></a>キー

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>列</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>serverID</p></td>
<td><p>主キー。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

