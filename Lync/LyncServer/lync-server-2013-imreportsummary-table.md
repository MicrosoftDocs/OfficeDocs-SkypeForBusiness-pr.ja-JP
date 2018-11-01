---
title: IMReportSummary テーブル
TOCTitle: IMReportSummary テーブル
ms:assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ204753(v=OCS.15)
ms:contentKeyID: 48271617
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# IMReportSummary テーブル

 

_**トピックの最終更新日:** 2015-03-09_

IMReportSummaryTable は、組織内で確立されているインスタント メッセージング セッションについての概要レポートを提供します。このテーブルは、Microsoft Lync Server 2013 で導入されました。


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
<td><p><strong>StartTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>主/プライマリ</p></td>
<td><p>インスタント メッセージング セッションが開始された日時。</p></td>
</tr>
<tr class="even">
<td><p><strong>TimePeriod</strong></p></td>
<td><p>char(1)</p></td>
<td><p>主/プライマリ</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>PoolFQDN</strong></p></td>
<td><p>nvarchar (257)</p></td>
<td><p>主/プライマリ</p></td>
<td><p>セッションをホストするプールの完全修飾ドメイン名。</p></td>
</tr>
<tr class="even">
<td><p><strong>AuthType</strong></p></td>
<td><p>int</p></td>
<td><p>主/プライマリ</p></td>
<td><p>通話の優先度 (緊急、非緊急など)。優先度の情報は、<a href="lync-server-2013-callpriorities-table.md">Lync Server 2013 の CallPriorities テーブル</a>に格納されます。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SessionCount</strong></p></td>
<td><p>bigint</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>MsgCount</strong></p></td>
<td><p>bigint</p></td>
<td><p></p></td>
<td><p>セッション中に交換されたインスタント メッセージの合計数。</p></td>
</tr>
</tbody>
</table>

