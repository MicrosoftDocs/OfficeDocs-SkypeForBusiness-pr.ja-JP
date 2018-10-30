---
title: 'Lync Server 2013: HardwareVersions テーブル'
TOCTitle: HardwareVersions テーブル
ms:assetid: ca05582b-082c-4bab-9233-36fc9434dbca
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398839(v=OCS.15)
ms:contentKeyID: 48273571
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の HardwareVersions テーブル

 

_**トピックの最終更新日:** 2015-03-09_

HardwareVersions テーブルは、サポート テーブルです。各レコードには、1 つのデバイス ハードウェア バージョンに関する情報が格納されています。


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
<td><p><strong>VersionId</strong></p></td>
<td><p>int</p></td>
<td><p>主/プライマリ</p></td>
<td><p>このハードウェア バージョンを識別する一意の番号。</p></td>
</tr>
<tr class="even">
<td><p><strong>バージョン</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p> </p></td>
<td><p>ハードウェア バージョン。</p></td>
</tr>
</tbody>
</table>

