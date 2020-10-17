---
title: 'Lync Server 2013: 応答グループの処理能力の計画'
description: 'Lync Server 2013: 応答グループの処理能力の計画。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning for Response Group
ms:assetid: a2459a69-1f45-4f2f-bca5-d4f442708e44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412754(v=OCS.15)
ms:contentKeyID: 48184951
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 78c543f558f67deaaeb781b308aa5f68d39cd785
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544433"
---
# <a name="capacity-planning-for-response-group-in-lync-server-2013"></a>Lync Server 2013 の応答グループの処理能力の計画

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-29_

<div id="sectionSection0" class="section">

次の表では、容量計画の要件の基礎として使用できる応答グループのユーザーモデルについて説明します。

<div>


> [!NOTE]  
> 次の表に示す数値は、すべての応答グループのオーディオファイルに 16 kHz、モノ、16ビットの Wave (.wav) ファイルを使用することを前提としています。 Windows Media Audio (.wma) など、他のファイル形式を使用する場合は、数字が異なる場合があります。



</div>

<div>


> [!IMPORTANT]  
> 障害復旧の処理能力を計画する場合は、ペアになっているプールの各プールで、両方のプールのすべての応答グループのワークロードを処理できる必要があることに注意してください。



</div>

### <a name="response-group-user-model"></a>応答グループのユーザーモデル

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>測定基準</th>
<th>Enterprise Edition プールごと (8 台のフロントエンドサーバー)</th>
<th>Standard Edition サーバーごと</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1秒あたりの着信</p></td>
<td><p>16 </p></td>
<td><p>pbm-2</p></td>
</tr>
<tr class="even">
<td><p>IVR または MoH に接続された同時通話</p></td>
<td><p>480</p></td>
<td><p>60</p></td>
</tr>
<tr class="odd">
<td><p>匿名の同時セッション (IM なし)</p></td>
<td><p>224</p></td>
<td><p>個</p></td>
</tr>
<tr class="even">
<td><p>匿名の同時セッション (IM を使用)</p></td>
<td><p>64</p></td>
<td><p>8 </p></td>
</tr>
<tr class="odd">
<td><p>アクティブなエージェント (公式および非公式)</p></td>
<td><p>1200</p></td>
<td><p>1200</p></td>
</tr>
<tr class="even">
<td><p>ハントグループの数</p></td>
<td><p>400</p></td>
<td><p>400</p></td>
</tr>
<tr class="odd">
<td><p>IVR グループ数 (音声認識を使用)</p></td>
<td><p>200</p></td>
<td><p>200</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

