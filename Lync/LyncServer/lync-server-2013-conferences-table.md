---
title: 'Lync Server 2013: Conferences テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conferences table
ms:assetid: c3da6271-b3c6-4898-894f-10456ec794d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412964(v=OCS.15)
ms:contentKeyID: 48185340
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c5464d3161a52a31fddb1322c82181d6e7a97fe
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756401"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferences-table-in-lync-server-2013"></a>Lync Server 2013 の Conferences テーブル

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-28_

この表の各レコードには、1人の会議に関する通話の詳細が含まれています。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>列</th>
<th>データ型</th>
<th>キー/インデックス</th>
<th>詳細</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>セッション Id</strong></p></td>
<td><p>datetime</p></td>
<td><p>Primary</p></td>
<td><p>会議出席依頼が CDR エージェントによってキャプチャされた時刻。 会議インスタンスを一意に識別するために、主キーとしてのみ使用されます。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>セッションを識別する ID 番号。 電話会議インスタンスを一意に識別するために<strong>Sessionidtime</strong>と組み合わせて使用されます。 *</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceUriId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>会議の URI。 詳細については、「 <a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013 の ConferenceUris テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>ConfInstance</strong></p></td>
<td><p>長さ</p></td>
<td><p> </p></td>
<td><p>定期的な会議に便利。定期的な会議の各インスタンスには、同じ<strong>ConferenceUri</strong>がありますが、別の<strong>confinstance</strong>があります。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceStartTime</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>会議の開始時刻。</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceEndTime</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>会議の開始時刻。</p></td>
</tr>
<tr class="odd">
<td><p><strong>PoolId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>会議がキャプチャされたプールを識別する ID 番号。 詳細については、「 <a href="lync-server-2013-pools-table.md">Lync Server 2013 のプールテーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>オーガナイザー Erid</strong></p></td>
<td><p>Int</p></td>
<td><p>外部</p></td>
<td><p>この会議の開催者の URI を識別する ID 番号。 詳細については、「 <a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザーテーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>フラッグ</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>会議の属性が含まれているビットマスク。 値の例は次のとおりです。</p>
<ul>
<li><p>0X01</p></li>
<li><p>Synthetic</p></li>
<li><p>トランザクション</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>処理</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>監視サービスで使用される内部フィールド。</p>
<p>このフィールドは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
</tbody>
</table>


\*ほとんどのセッションでは、SessionIdSeq の値は1になります。 2つのセッションがまったく同じ時刻に開始された場合、1つのセッションの SessionIdSeq は1になり、残りのセッションは2になります。

</div>

<span> </span>

</div>

</div>

</div>

