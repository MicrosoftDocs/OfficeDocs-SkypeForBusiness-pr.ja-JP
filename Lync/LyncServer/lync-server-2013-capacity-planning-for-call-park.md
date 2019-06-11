---
title: 'Lync Server 2013: コール パークの処理能力計画'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Capacity planning for Call Park
ms:assetid: 75520310-760a-4b1b-bcc1-4d724d13f87a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg416493(v=OCS.15)
ms:contentKeyID: 48184529
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5fe55e09c67e62676202def9e3def3454d7cbd33
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840677"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-call-park-in-lync-server-2013"></a>Lync Server 2013 のコール パークの処理能力計画

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-13_

<div id="sectionSection0" class="section">

次の表では、キャパシティ計画の要件の基礎として使用できるコールパークユーザーモデルについて説明します。

<div>


> [!IMPORTANT]  
> 障害復旧のキャパシティ計画として、ペアリングされたプールの各プールは、両方のプールのコールパークサービスのワークロードを処理できる必要があることに注意してください。



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
<th>指標</th>
<th>フロントエンドプールあたり (8 個のフロントエンドサーバーを含む)</th>
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

