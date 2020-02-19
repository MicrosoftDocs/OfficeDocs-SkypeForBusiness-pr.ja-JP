---
title: 'Lync Server 2013: コールパークの処理能力計画'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning for Call Park
ms:assetid: 75520310-760a-4b1b-bcc1-4d724d13f87a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg416493(v=OCS.15)
ms:contentKeyID: 48184529
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e3bdb6899ae92d8f4d5561bd81266922284d950
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137216"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-call-park-in-lync-server-2013"></a>Lync Server 2013 でのコールパークの処理能力計画

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-13_

<div id="sectionSection0" class="section">

次の表では、容量計画の要件の基礎として使用できるコールパークユーザーモデルについて説明します。

<div>


> [!IMPORTANT]  
> 障害復旧の処理能力を計画する場合は、ペアになっているプールの各プールで、両方のプールのコールパークサービスのワークロードを処理できる必要があることに注意してください。



</div>

### <a name="call-park-user-model"></a>コール パークのユーザー モデル

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>測定基準</th>
<th>フロントエンドプールごと (8 台のフロントエンドサーバー)</th>
<th>Standard Edition サーバーごと</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>保留率</p></td>
<td><p>8 分間に 1 回</p></td>
<td><p>1 分間に 1 回</p></td>
</tr>
<tr class="even">
<td><p>取得通話保留率</p></td>
<td><p>8 分間に 1 回</p></td>
<td><p>1 分間に 1 回</p></td>
</tr>
<tr class="odd">
<td><p>平均保留時間</p></td>
<td><p>60 秒</p></td>
<td><p>60 秒</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

