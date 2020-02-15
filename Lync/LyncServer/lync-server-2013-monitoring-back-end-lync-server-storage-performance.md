---
title: 'Lync Server 2013: バックエンド Lync Server ストレージのパフォーマンスの監視'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring back end Lync Server 2013 storage performance
ms:assetid: 71627c70-1953-4ac2-afbe-f3ad85be0f44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720917(v=OCS.15)
ms:contentKeyID: 63969619
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 760e66403fd1da2b5a45cf0db065dc201e1fd02a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051159"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-back-end-lync-server-2013-storage-performance"></a>バックエンド Lync Server 2013 ストレージのパフォーマンスの監視

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-05-02_

Lync Server 2013 のバックエンドデータベースは、Lync Server 2013 の展開において非常に重要な部分です。 Lync Server 2013 のバックエンドが最適に実行されていることを確認するために、データベースとそれぞれのトランザクションログを絶えず監視することをお勧めします。

次の表に、ストレージのパフォーマンスに関する情報を取得するために監視する必要があるパフォーマンスカウンターを示します。 これらのカウンターのベースライン値は、最初に決定する必要があります (システムの負荷が分散されているときに、システムが通常、予想される負荷)。

### <a name="performance-counters-to-be-monitored"></a>監視するパフォーマンスカウンター

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>パフォーマンス カウンター</th>
<th>ベースラインのしきい値</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>トランザクション/秒 (RTC)</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>トランザクション/秒 (rtcdyn)</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>トランザクション/秒 (tempdb)</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>ログのフラッシュ/秒 (RTC)</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>ログのフラッシュ/秒 (rtcdyn)</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>ログのフラッシュ/秒 (tempdb)</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>ディスク転送/秒 (読み取り + 書き込み)-RTC db</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>ディスク転送/秒-RTC ログ</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>ディスク転送/秒-rtcdyn db</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>ディスク転送/sec-rtcdyn ログ</p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

