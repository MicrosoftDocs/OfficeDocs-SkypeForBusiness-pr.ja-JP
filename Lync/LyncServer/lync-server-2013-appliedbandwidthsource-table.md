---
title: 'Lync Server 2013: AppliedBandwidthSource テーブル'
TOCTitle: AppliedBandwidthSource テーブル
ms:assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg425725(v=OCS.15)
ms:contentKeyID: 48271506
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の AppliedBandwidthSource テーブル

 

_**トピックの最終更新日:** 2015-03-09_

AppliedBandwidthSource テーブルはサポート テーブルです。各レコードは 1 つのソースを表します。


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
<td><p><strong>AppliedBandwidthSourceKey</strong></p></td>
<td><p>int</p></td>
<td><p>主/プライマリ</p></td>
<td><p>ソースを示す一意の番号です。</p></td>
</tr>
<tr class="even">
<td><p><strong>AppliedBandwidthSource</strong></p></td>
<td><p>varchar(256)</p></td>
<td><p>一意</p></td>
<td><p>適用されている帯域幅キャップのソースです。帯域幅制限の適用元を示します (たとえば、&quot;Policy Server&quot;、&quot;TURN Server&quot;、&quot;Modality&quot; など)。</p></td>
</tr>
</tbody>
</table>

