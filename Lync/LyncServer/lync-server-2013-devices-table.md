---
title: 'Lync Server 2013: Devices テーブル'
TOCTitle: Devices テーブル
ms:assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398351(v=OCS.15)
ms:contentKeyID: 48272094
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の Devices テーブル

 

_**トピックの最終更新日:** 2015-03-09_

Devices テーブルは、サポート テーブルです。各レコードには、1 つのデバイス (卓上電話) に関する情報が格納されます。


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
<td><p><strong>DeviceId</strong></p></td>
<td><p>int</p></td>
<td><p>主/プライマリ</p></td>
<td><p>このハードウェア バージョンを識別する一意の番号。</p></td>
</tr>
<tr class="even">
<td><p><strong>ManufacturerId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>このデバイスの製造元。詳細については、「<a href="lync-server-2013-manufacturers-table.md">Lync Server 2013 の Manufacturers テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>HardwareVersionId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>このデバイスのハードウェア バージョン。詳細については、「<a href="lync-server-2013-hardwareversions-table.md">Lync Server 2013 の HardwareVersions テーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>MacAddress</strong></p></td>
<td><p>bigint</p></td>
<td><p></p></td>
<td><p>MAC アドレス</p></td>
</tr>
</tbody>
</table>

