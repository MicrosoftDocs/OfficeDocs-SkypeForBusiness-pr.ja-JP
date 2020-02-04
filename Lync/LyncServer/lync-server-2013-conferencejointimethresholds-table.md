---
title: 'Lync Server 2013: ConferenceJoinTimeThresholds テーブル'
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
ms.openlocfilehash: baf29af4b9d1f2b026271b84cb54436e8f4b233f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740057"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencejointimethresholds-table-in-lync-server-2013"></a>Lync Server 2013 の ConferenceJoinTimeThresholds テーブル

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-28_

ConferenceJoinTimeThresholds テーブルには、電話会議の参加時間のサマリーレポートで使用される分類境界が含まれています。 [会議参加時間のサマリー] レポートは、ユーザーが会議に参加するのに必要な時間の概要を示します。これらの時間値は、平均として、または次のいずれかのカテゴリに報告されます。

  - 2秒未満。

  - 2秒と5秒の間。

  - 5 ~ 10 秒の間。

  - 10秒以上

ConferenceJoinTimeThresholds テーブルには、2秒、5秒、10秒の分類値が含まれています。

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
<td><p>Primary</p></td>
<td><p>分類の一意の識別子。</p></td>
</tr>
<tr class="even">
<td><p><strong>ThresholdValue</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>分類の上限。 有効な値は次のとおりです。</p>
<ol>
<li><p>両面</p></li>
<li><p>5</p></li>
<li><p>常用</p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

