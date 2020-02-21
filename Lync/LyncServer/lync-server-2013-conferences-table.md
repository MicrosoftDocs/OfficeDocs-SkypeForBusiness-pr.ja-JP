---
title: 'Lync Server 2013: 電話会議テーブル'
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
ms.openlocfilehash: d3dbaf1a721433cc04aa681dad56d753de8bc9a3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190250"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conferences-table-in-lync-server-2013"></a>Lync Server 2013 の会議テーブル

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-28_

この表の各レコードには、1つの会議に関する通話の詳細が含まれています。


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
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>日付型</p></td>
<td><p>Primary</p></td>
<td><p>会議出席依頼が CDR エージェントによってキャプチャされた時刻。 会議インスタンスを一意に識別する主キーとしてのみ使用されます。</p></td>
</tr>
<tr class="even">
<td><p><strong>Sessionidseq と</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>セッションを識別するための ID 番号。 <strong>Sessionidtime</strong>と組み合わせて、電話会議のインスタンスを一意に識別するために使用されます。 *</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceUriId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>会議 URI。 詳細については、「 <a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013 の ConferenceUris テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>ConfInstance</strong></p></td>
<td><p>識別子</p></td>
<td><p> </p></td>
<td><p>定期的な電話会議に役立ちます。定期的な会議の各インスタンスには同じ<strong>ConferenceUri</strong>がありますが、別の<strong>confinstance</strong>があります。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceStartTime</strong></p></td>
<td><p>日付型</p></td>
<td><p> </p></td>
<td><p>電話会議の開始時刻。</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceEndTime</strong></p></td>
<td><p>日付型</p></td>
<td><p> </p></td>
<td><p>電話会議の開始時刻。</p></td>
</tr>
<tr class="odd">
<td><p><strong>PoolId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>電話会議がキャプチャされたプールを識別する ID 番号。 詳細については、「 <a href="lync-server-2013-pools-table.md">Lync Server 2013 のプール</a>」の表を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>組織の Erid</strong></p></td>
<td><p>Int</p></td>
<td><p>外部</p></td>
<td><p>この電話会議の開催者 URI を識別する ID 番号。 詳細については、「 <a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザー</a> 」の表を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Flag</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>会議の属性を含むビットマスク。 使用可能な値は次のいずれかです。</p>
<ul>
<li><p>0X01</p></li>
<li><p>代理</p></li>
<li><p>トランザクション</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>実行</strong></p></td>
<td><p>若干</p></td>
<td></td>
<td><p>監視サービスによって使用される内部フィールド。</p>
<p>このフィールドは、Microsoft Lync Server 2013 で導入されました。</p></td>
</tr>
</tbody>
</table>


\*ほとんどのセッションでは、SessionIdSeq の値は1になります。 2つのセッションがまったく同じ時刻に開始された場合は、1つの SessionIdSeq が1になります。その他の場合は2になります。

</div>

<span> </span>

</div>

</div>

</div>

