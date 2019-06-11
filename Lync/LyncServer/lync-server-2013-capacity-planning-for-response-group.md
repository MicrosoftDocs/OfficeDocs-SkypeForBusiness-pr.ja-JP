---
title: 'Lync Server 2013: 応答グループの処理能力の計画'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Capacity planning for Response Group
ms:assetid: a2459a69-1f45-4f2f-bca5-d4f442708e44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412754(v=OCS.15)
ms:contentKeyID: 48184951
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 72f3e49806dc573a4e17bc917834deba97a74ca2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840671"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-response-group-in-lync-server-2013"></a>Lync Server 2013 の応答グループの処理能力の計画

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-29_

<div id="sectionSection0" class="section">

次の表では、キャパシティ計画の要件の基礎として使用できる応答グループのユーザーモデルについて説明します。

<div>


> [!NOTE]  
> 次の表の数字は、すべての応答グループのオーディオ ファイルに、16 kHz、モノ、16 ビットの WAVE (.wav) ファイルを使用することを前提としています。Windows Media Audio (.wma) ファイルなどの他のファイル形式を使用した場合は、数字が変わる可能性があります。



</div>

<div>


> [!IMPORTANT]  
> 障害復旧のキャパシティ計画時には、ペアになっているプールの各プールで、両方のプールに含まれるすべての応答グループのワークロードを処理する必要があることを念頭においてください。



</div>

### <a name="response-group-user-model"></a>応答グループのユーザー モデル

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>指標</th>
<th>Enterprise Edition プール (8 台のフロントエンドサーバーを含む)</th>
<th>Standard Edition サーバーごと</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1 秒あたりの着信</p></td>
<td><p>16</p></td>
<td><p>2</p></td>
</tr>
<tr class="even">
<td><p>IVR または MoH に接続した同時通話</p></td>
<td><p>480</p></td>
<td><p>60</p></td>
</tr>
<tr class="odd">
<td><p>匿名の同時セッション (IM なし)</p></td>
<td><p>224</p></td>
<td><p>日</p></td>
</tr>
<tr class="even">
<td><p>匿名の同時セッション (IM あり)</p></td>
<td><p>64</p></td>
<td><p>個</p></td>
</tr>
<tr class="odd">
<td><p>アクティブ エージェント (公式および非公式)</p></td>
<td><p>1200</p></td>
<td><p>1200</p></td>
</tr>
<tr class="even">
<td><p>ハント グループ数</p></td>
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

