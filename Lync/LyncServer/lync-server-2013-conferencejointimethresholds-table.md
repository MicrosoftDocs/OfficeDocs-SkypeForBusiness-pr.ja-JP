---
title: ConferenceJoinTimeThresholds テーブル
TOCTitle: ConferenceJoinTimeThresholds テーブル
ms:assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ204809(v=OCS.15)
ms:contentKeyID: 48271792
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ConferenceJoinTimeThresholds テーブル

 

_**トピックの最終更新日:** 2015-03-09_

ConferenceJoinTimeThresholds テーブルには、電話会議参加時間要約レポートによって使用される分類境界が含まれます。電話会議参加時間要約レポートは、ユーザーが問題なく電話会議に参加する目的で必要な時間を集計します。これらの時間値は、平均と、以下のカテゴリの 1 つの両方で報告されます。

  - 2 秒未満。

  - 2 ～ 5 秒の間。

  - 5 ～ 10 秒の間。

  - 10 秒以上。

ConferenceJoinTimeThresholds テーブルには、2 秒、5 秒、および 10 秒の分類値が含まれます。

このテーブルは、Microsoft Lync Server 2013 で導入されました。


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
<td><p><strong>ThresholdId</strong></p></td>
<td><p>int</p></td>
<td><p>主/プライマリ</p></td>
<td><p>分類の一意識別子。</p></td>
</tr>
<tr class="even">
<td><p><strong>ThresholdValue</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>分類の上限。有効な値は次のとおりです。</p>
<ol>
<li><p>2</p></li>
<li><p>5</p></li>
<li><p>10</p></li>
</ol></td>
</tr>
</tbody>
</table>

