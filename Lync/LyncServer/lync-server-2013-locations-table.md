---
title: 'Lync Server 2013: Locations テーブル'
TOCTitle: Locations テーブル
ms:assetid: 78dc1b14-5394-4f8e-89d3-4ba593272a04
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398596(v=OCS.15)
ms:contentKeyID: 48272571
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の Locations テーブル

 

_**トピックの最終更新日:** 2015-03-09_

それぞれのレコードは、E9-1-1 通話など、緊急通話における 1 つの場所の参照を表します。


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
<td><p>datetime</p></td>
<td><p>主/プライマリ、外部</p></td>
<td><p>セッション要求の時間。<strong>SessionIdSeq</strong> と合わせて使用して、セッションを一意に識別します。詳細については、「<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 の Dialogs テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>主/プライマリ、外部</p></td>
<td><p>セッションを識別するための ID 番号。セッションを一意に識別するために <strong>SessionIdTime</strong> と併用されます。詳細については、「<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 の Dialogs テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Location</strong></p></td>
<td><p>nvarchar (max)</p></td>
<td><p></p></td>
<td><p>緊急通話の場所。</p></td>
</tr>
</tbody>
</table>

