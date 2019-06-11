---
title: 'Lync Server 2013: バックエンドの Lync Server 記憶域のパフォーマンスを監視する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Monitoring back end Lync Server 2013 storage performance
ms:assetid: 71627c70-1953-4ac2-afbe-f3ad85be0f44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720917(v=OCS.15)
ms:contentKeyID: 63969619
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b4c63956cebc7f532f92b6e0729bdfe811d0fdfb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826760"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-back-end-lync-server-2013-storage-performance"></a>バックエンドの Lync Server 2013 ストレージパフォーマンスの監視

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-05-02_

Lync Server 2013 バックエンドデータベースは、Lync Server 2013 の展開において非常に重要な部分です。 Lync Server 2013 のバックエンドが最適に動作していることを確認するために、データベースとそれぞれのトランザクションログを定期的に監視することをお勧めします。

次の表は、記憶域のパフォーマンスに関する情報を確認するために監視する必要があるパフォーマンスカウンターを示しています。 これらのカウンターのベースライン値は、システムの負荷が高すぎるときにパフォーマンスの変化を理解するために、最初に決定する必要があります (システムが通常、予想される負荷の場合)。

### <a name="performance-counters-to-be-monitored"></a>監視対象のパフォーマンスカウンター

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>パフォーマンスカウンター</th>
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
<td><p>ログのフラッシュ回数/秒 (RTC)</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>ログのフラッシュ回数/秒 (rtcdyn)</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>ログのフラッシュ回数/秒 (tempdb)</p></td>
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
<td><p>Disk 伝送/sec-rtcdyn db</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Disk 伝送/sec-rtcdyn ログ</p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

