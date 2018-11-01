---
title: 'Lync Server 2013: MediationServers テーブル'
TOCTitle: MediationServers テーブル
ms:assetid: 9f757377-ab79-4795-aaa9-1163cb9c8a59
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg412743(v=OCS.15)
ms:contentKeyID: 48273010
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の MediationServers テーブル

 

_**トピックの最終更新日:** 2015-03-09_

MediationServers テーブルは補助的なテーブルです。この個々のレコードには、データベースに記録が残された通話に関係する特定の仲介サーバーの情報が格納されています。


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
<td><p><strong>MediationServerId</strong></p></td>
<td><p>int</p></td>
<td><p>主/プライマリ</p></td>
<td><p>この仲介サーバーを識別する一意の番号。</p></td>
</tr>
<tr class="even">
<td><p><strong>MediationServer</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p> </p></td>
<td><p>仲介サーバーの名前。</p></td>
</tr>
</tbody>
</table>

