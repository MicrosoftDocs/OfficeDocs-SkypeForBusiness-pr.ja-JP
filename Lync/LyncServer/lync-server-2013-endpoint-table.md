---
title: 'Lync Server 2013: Endpoint テーブル'
TOCTitle: Endpoint テーブル
ms:assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398327(v=OCS.15)
ms:contentKeyID: 48272068
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の Endpoint テーブル

 

_**トピックの最終更新日:** 2015-03-09_

Endpoint テーブルは、データベースに記録されているセッションに参加したエンドポイントに関する情報を格納するサポート テーブルです。テーブル内の各レコードは、1 つのエンドポイントを表します。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>列</strong></th>
<th><strong>データ型</strong></th>
<th><strong>キー/インデックス</strong></th>
<th><strong>詳細</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>EndpointKey</strong></p></td>
<td><p>int</p></td>
<td><p>主/プライマリ</p></td>
<td><p>このエンドポイントを識別する一意の番号。</p></td>
</tr>
<tr class="even">
<td><p><strong>Name</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>一意</p></td>
<td><p>エンドポイント名。</p></td>
</tr>
<tr class="odd">
<td><p><strong>OS</strong></p></td>
<td><p>nvarchar (128)</p></td>
<td><p> </p></td>
<td><p>エンドポイントのオペレーティング システム (OS)。</p></td>
</tr>
<tr class="even">
<td><p><strong>CPUName</strong></p></td>
<td><p>nvarchar (128)</p></td>
<td><p></p></td>
<td><p>エンドポイントの CPU 名。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CPUNumberOfCores</strong></p></td>
<td><p>smallint</p></td>
<td><p></p></td>
<td><p>エンドポイントの CPU コアの数。</p></td>
</tr>
<tr class="even">
<td><p><strong>CPUProcessorSpeed</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>エンドポイントの CPU プロセッサ速度。</p></td>
</tr>
<tr class="odd">
<td><p><strong>VirtualizationFlag</strong></p></td>
<td><p>tinyint</p></td>
<td><p></p></td>
<td><p>システムが次の仮想環境で実行されているかどうかを示すビット フラグ。</p>
<ul>
<li><p>0x0000 - なし</p></li>
<li><p>0x0001 - HyperV</p></li>
<li><p>0x0002 - VMWare</p></li>
<li><p>0x0004 - Virtual PC</p></li>
<li><p>0x0008 - Xen PC</p></li>
</ul></td>
</tr>
</tbody>
</table>

