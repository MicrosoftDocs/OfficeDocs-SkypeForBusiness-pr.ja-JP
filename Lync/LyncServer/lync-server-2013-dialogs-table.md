---
title: 'Lync Server 2013: Dialogs テーブル'
TOCTitle: Dialogs テーブル
ms:assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg425954(v=OCS.15)
ms:contentKeyID: 48271974
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の Dialogs テーブル

 

_**トピックの最終更新日:** 2015-03-09_

Dialogs テーブルは、ピアツーピア セッションの DialogID に関する情報を格納するサポート テーブルです。


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
<td><p>主/プライマリ</p></td>
<td><p>セッション要求の時刻。セッションを一意に識別するために SessionIDSeq と併用されます。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>主/プライマリ</p></td>
<td><p>セッションを識別するための ID 番号。セッションを一意に識別するために SessionIDTime と併用されます。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ExternalChecksum</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>ExternalID のチェックサム。このフィールドは、データベースの検索速度を上げるために使用されます。</p></td>
</tr>
<tr class="even">
<td><p><strong>ExternalId</strong></p></td>
<td><p>varbinary(775)</p></td>
<td><p> </p></td>
<td><p>SIP ダイアログ ID。バイナリとして格納されます。バイナリの形式は次のとおりです。</p>
<p>dialog;from-tag;to-tag</p>
<p>このデータは、次の構文を使用してテキスト形式に変換できます。</p>
<p><code>cast(cast(ExternalId as varbinary(max)) as varchar(max))</code></p></td>
</tr>
</tbody>
</table>

