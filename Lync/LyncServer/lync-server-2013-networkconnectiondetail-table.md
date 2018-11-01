---
title: Lync Server 2013 での NetworkConnectionDetail テーブル
TOCTitle: Lync Server 2013 での NetworkConnectionDetail テーブル
ms:assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205185(v=OCS.15)
ms:contentKeyID: 48273339
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での NetworkConnectionDetail テーブル

 

_**トピックの最終更新日:** 2015-03-09_

NetworkConnectionDetail テーブルは、Quality of Experience データベースの他の場所で使用されるネットワーク接続の識別子にネットワーク接続の種類を対応させます。このテーブルは、Microsoft Lync Server 2013 で導入されました。


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
<td><p><strong>NetworkConnectionDetailKey</strong></p></td>
<td><p>tinyint</p></td>
<td><p>主/プライマリ</p></td>
<td><p>ネットワーク接続の種類の一意の識別子。</p></td>
</tr>
<tr class="even">
<td><p><strong>NetworkConnectionDetail</strong></p></td>
<td><p>varchar(256)</p></td>
<td><p>一意</p></td>
<td><p>NetworkConnectionDetailKey に対応するネットワーク接続の種類。有効な値は次のとおりです。</p>
<ol>
<li><p>0: 有線</p></li>
<li><p>1: WiFi</p></li>
<li><p>2: イーサネット</p></li>
</ol></td>
</tr>
</tbody>
</table>

