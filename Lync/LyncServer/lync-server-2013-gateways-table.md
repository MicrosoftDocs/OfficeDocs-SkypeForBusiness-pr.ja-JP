---
title: 'Lync Server 2013: ゲートウェイ テーブル'
TOCTitle: ゲートウェイ テーブル
ms:assetid: a909daad-d137-45e0-b149-1de9f8e1e029
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg412795(v=OCS.15)
ms:contentKeyID: 48273188
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 のゲートウェイ テーブル

 

_**トピックの最終更新日:** 2015-03-09_

ゲートウェイ テーブルは補助的なテーブルです。この個々のレコードには、データベースに記録が残された公衆交換電話網 (PSTN) に関係する特定のゲートウェイの情報が格納されています。


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
<td><p><strong>GatewayId</strong></p></td>
<td><p>int</p></td>
<td><p>主/プライマリ</p></td>
<td><p>このゲートウェイを識別する一意の番号。</p></td>
</tr>
<tr class="even">
<td><p><strong>Gateway</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p> </p></td>
<td><p>ゲートウェイ名。</p></td>
</tr>
</tbody>
</table>

