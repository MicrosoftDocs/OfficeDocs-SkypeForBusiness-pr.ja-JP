---
title: 'Lync Server 2013: TraceRoute テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: TraceRoute table
ms:assetid: b9493cef-6ece-4f13-bf68-dbf132aab4f4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205205(v=OCS.15)
ms:contentKeyID: 48185242
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1dd0f9bc3bd900d71a316bf2ff1ab7612a51194
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848392"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="traceroute-table-in-lync-server-2013"></a>Lync Server 2013 の TraceRoute テーブル

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-02-21_

TraceRoute テーブルには、通話のルーティング情報が含まれています。 この表は、Microsoft Lync Server 2013 で導入されました。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>列</strong></th>
<th><strong>データ型</strong></th>
<th><strong>キー/インデックス</strong></th>
<th><strong>詳細</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ConferenceDateTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>プライマリ、外部</p></td>
<td><p>通話が開始された日付と時刻。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>プライマリ、外部</p></td>
<td><p>同じ日付と同時に開始された可能性がある複数の通話を区別するために使用される一意の識別子。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>tinyint</p></td>
<td><p>プライマリ、外部</p></td>
<td><p>通話で使用されるビデオラインの種類を表します。 有効な値は次のとおりです。</p>
<ul>
<li><p>0–音声</p></li>
<li><p>1-ビデオ</p></li>
<li><p>2-パノラマビデオ</p></li>
<li><p>3-アプリケーション/デスクトップ共有</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>FromCaller</strong></p></td>
<td><p>bit</p></td>
<td><p>Primary</p></td>
<td><p>通話を発信したエンドポイント。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ホップ</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>ネットワークホップ/</p></td>
</tr>
<tr class="even">
<td><p><strong>IPAddressKey</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>IP アドレスの一意の識別子。 IP アドレス情報は、 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 の IPAddress テーブル</a>に格納されます。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RTT</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>往復時間。 往復時間は、ボイスパケットがその宛先に到達し、受信した通知を返信するのにかかる時間を測定します。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

