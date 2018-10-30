---
title: ConferenceUris ビュー
TOCTitle: ConferenceUris ビュー
ms:assetid: 9a3cdcea-426e-4b6b-9876-ba746a8de706
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ688148(v=OCS.15)
ms:contentKeyID: 49887069
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ConferenceUris ビュー

 

_**トピックの最終更新日:** 2015-03-09_

ConfernceUris ビューは、会議セッションに参加した URI に関する情報を格納します。このビューは、Microsoft Lync Server 2013 で導入されました。


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
<td><p>ConferenceUriId</p></td>
<td><p>int</p></td>
<td><p>会議 URI を識別する一意の番号。</p></td>
</tr>
<tr class="even">
<td><p>ConferenceUri</p></td>
<td><p>nvarchar(450)</p></td>
<td><p>会議の URI。</p></td>
</tr>
<tr class="odd">
<td><p>ConferenceUriType</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>会議 URI の種類。詳細については、「<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 の UriTypes テーブル</a>」を参照してください。</p></td>
</tr>
</tbody>
</table>

