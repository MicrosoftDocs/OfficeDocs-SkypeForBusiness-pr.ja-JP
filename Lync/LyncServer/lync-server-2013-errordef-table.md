---
title: 'Lync Server 2013: ErrorDef テーブル'
TOCTitle: ErrorDef テーブル
ms:assetid: 6acf3b86-da61-4923-9812-300db6f66dec
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398503(v=OCS.15)
ms:contentKeyID: 48272409
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 ErrorDef テーブル

 

_**トピックの最終更新日:** 2015-03-09_

ErrorDef テーブルには、発生する可能性があるエラーの各種類に関する情報が格納されます。それぞれのレコードが 1 種類のエラーに対応しています。


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
<td><p><strong>ErrorId</strong></p></td>
<td><p>int</p></td>
<td><p>主/プライマリ</p></td>
<td><p>このエラーの種類を識別する一意の ID 番号。</p></td>
</tr>
<tr class="even">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>このエラーに関連付けられている標準的な SIP 応答コード。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MsDiagId</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>マイクロソフトの診断 ID。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallTypeId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>通話の種類。詳細については、「<a href="lync-server-2013-calltype-table.md">Lync Server 2013 の CallType テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RequestType</strong></p></td>
<td><p>varbinary(33)</p></td>
<td><p> </p></td>
<td><p>エラーが発生した要求の種類。</p>
<p>このデータは、次の構文を使用してテキスト形式に変換できます。</p>
<p><code>cast(cast(RequestType as varbinary(max)) as varchar(max))</code></p></td>
</tr>
<tr class="even">
<td><p><strong>ContentType</strong></p></td>
<td><p>varbinary(257)</p></td>
<td><p> </p></td>
<td><p>エラーが発生した要求のコンテンツの種類。</p>
<p>このデータは、次の構文を使用してテキスト形式に変換できます。</p>
<p><code>cast(cast(ContentType as varbinary(max)) as varchar(max))</code></p></td>
</tr>
</tbody>
</table>

