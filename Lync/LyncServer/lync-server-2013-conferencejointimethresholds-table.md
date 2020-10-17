---
title: 'Lync Server 2013: ConferenceJoinTimeThresholds テーブル'
description: 'Lync Server 2013: ConferenceJoinTimeThresholds テーブル。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceJoinTimeThresholds table
ms:assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204809(v=OCS.15)
ms:contentKeyID: 48183855
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5e38c8b99f444e16309882b6a8885d166fdceb9b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561673"
---
# <a name="conferencejointimethresholds-table-in-lync-server-2013"></a>Lync Server 2013 の ConferenceJoinTimeThresholds テーブル

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-28_

ConferenceJoinTimeThresholds テーブルには、電話会議参加時間要約レポートによって使用される分類境界が含まれます。電話会議参加時間要約レポートは、ユーザーが問題なく電話会議に参加する目的で必要な時間を集計します。これらの時間値は、平均と、以下のカテゴリの 1 つの両方で報告されます。

  - 2 秒未満。

  - 2 ～ 5 秒の間。

  - 5 ～ 10 秒の間。

  - 10 秒以上。

ConferenceJoinTimeThresholds テーブルには、2 秒、5 秒、および 10 秒の分類値が含まれます。

この表は、Microsoft Lync Server 2013 で導入されました。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Column</th>
<th>データ型</th>
<th>キー/インデックス</th>
<th>詳細</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ThresholdId</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>分類の一意識別子。</p></td>
</tr>
<tr class="even">
<td><p><strong>ThresholdValue</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>分類の上限。有効な値は次のとおりです。</p>
<ol>
<li><p>pbm-2</p></li>
<li><p>5 </p></li>
<li><p>10  </p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

