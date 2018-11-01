---
title: FileTransfers ビュー
TOCTitle: FileTransfers ビュー
ms:assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ721914(v=OCS.15)
ms:contentKeyID: 49887185
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# FileTransfers ビュー

 

_**トピックの最終更新日:** 2015-03-09_

FileTranfer ビューには、ピアツーピア ファイル送信セッションに関する情報が格納されます。このビューは、Microsoft Lync Server 2013 で導入されました。

> [!NOTE]
> FileTransfers ビューには、以下の列に加えて、<a href="lync-server-2013-sessiondetails-view.md">SessionDetails ビュー</a>のすべての列が含まれます。



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
<td><p><strong>FileName</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>送信されたファイルの名前です。</p></td>
</tr>
<tr class="even">
<td><p><strong>Cookie</strong></p></td>
<td><p>nvarchar(128)</p></td>
<td><p>すべてのフォローアップ メッセージをこれに関連付けられたものとして識別するために使用します。</p></td>
</tr>
<tr class="odd">
<td><p><strong>FileIdentity</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p>同じファイル名が使用されているファイル送信を区別するための一意の識別子です。</p></td>
</tr>
<tr class="even">
<td><p><strong>Accept</strong></p></td>
<td><p>bit</p></td>
<td><p>TRUE または NULL。TRUE の場合は、Reject と Cancel が NULL になります。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Reject</strong></p></td>
<td><p>bit</p></td>
<td><p>TRUE または NULL。TRUE の場合は、Accept と Cancel が NULL になります。</p></td>
</tr>
<tr class="even">
<td><p><strong>Cancel</strong></p></td>
<td><p>bit</p></td>
<td><p>TRUE または NULL。TRUE の場合は、Accept と Reject が NULL になります。</p></td>
</tr>
</tbody>
</table>

