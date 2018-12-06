---
title: ClientVersions ビュー
TOCTitle: ClientVersions ビュー
ms:assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ721891(v=OCS.15)
ms:contentKeyID: 49887145
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ClientVersions ビュー

 

_**トピックの最終更新日:** 2015-03-09_

ClientVersions ビューは、データベースに記録されるセッションに参加した、さまざまなクライアントの種類およびバージョンの情報を格納します。ビュー内の各レコードは、1 つのクライアント バージョンを表します。このビューは、Microsoft Lync Server 2013 で導入されました。

> [!NOTE]
> 一部の列には複数のレコードが存在する場合があります。



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
<td><p><strong>VersionId</strong></p></td>
<td><p>int</p></td>
<td><p>このクライアントの種類とバージョンを識別する一意の番号。</p></td>
</tr>
<tr class="even">
<td><p><strong>Version</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>ユーザー エージェントを表す。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClientType</strong></p></td>
<td><p>int</p></td>
<td><p>クライアントの種類。</p></td>
</tr>
<tr class="even">
<td><p><strong>ClientCategory</strong></p></td>
<td><p>nvarchar(64)</p></td>
<td><p>クライアントが属するカテゴリ。たとえば、Conferencing_Attendant_1.0 というクライアントは CAA という ClientCategory に属します。</p></td>
</tr>
</tbody>
</table>

