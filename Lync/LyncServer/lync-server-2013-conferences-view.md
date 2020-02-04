---
title: 'Lync Server 2013: 会議ビュー'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conferences view
ms:assetid: c0e5c4db-c135-401f-9296-e9a49f6499a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721871(v=OCS.15)
ms:contentKeyID: 49733803
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 36278c1053c2b5737e0de6caf914c050db93ea4b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741607"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferences-view-in-lync-server-2013"></a>Lync Server 2013 での会議ビュー

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-01_

会議ビューには、会議に関する情報が格納されます。 このビューは、Microsoft Lync Server 2013 で導入されました。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>列</th>
<th>データ型</th>
<th>詳細</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>セッション Id</strong></p></td>
<td><p>datetime</p></td>
<td><p>セッション要求の時刻。 セッションを一意に識別するために SessionIdSeq と組み合わせて使用されます。 詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>セッションを識別する ID 番号。 セッションを一意に識別するために SessionIdTime と組み合わせて使用されます。 詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>会議の URI。</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>会議 URI の種類。 詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConfInstance</strong></p></td>
<td><p>長さ</p></td>
<td><p>定期的な会議に使用されます。 定期的な会議の各インスタンスには、同じ ConferenceUri がありますが、ConfInstance は異なります。</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceStartTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>会議の開始時刻。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceEndTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>会議の終了時刻。</p></td>
</tr>
<tr class="even">
<td><p><strong>オーガナイザーの Uri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>会議を開催したユーザーの URI。</p></td>
</tr>
<tr class="odd">
<td><p><strong>オーガナイザーの種類</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>会議を開催したユーザーの URI の種類です。 詳細については、「 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>組織のテナント</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>会議を開催したユーザーのテナント。 詳細については、「 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 のテナントの一覧</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Pool</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>会議をホストしているプールの完全修飾ドメイン名。</p></td>
</tr>
<tr class="even">
<td><p><strong>フラッグ</strong></p></td>
<td><p>smallint</p></td>
<td><p>会議の属性が含まれているビットマスク。 値の例は次のとおりです。</p>
<p>0X01 –代理トランザクション</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

