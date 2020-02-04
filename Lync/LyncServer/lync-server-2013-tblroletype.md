---
title: 'Lync Server 2013: tblRoleType'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblRoleType
ms:assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558623(v=OCS.15)
ms:contentKeyID: 48183577
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba6b5041453b0965fafc12ada2be62ec42316f89
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731187"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblroletype-in-lync-server-2013"></a>Lync Server 2013 の tblRoleType

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-06-25_

tblRoleType は、役割の種類とそれに関連付けられたアクセス許可セットを含む静的参照テーブルです。

### <a name="columns"></a>行

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>列</th>
<th>型</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>rtypeID</p></td>
<td><p>int (null ではない)</p></td>
<td><p>役割の種類 ID。</p></td>
</tr>
<tr class="even">
<td><p>rtypeDesc</p></td>
<td><p>nvarchar (256)、null ではない</p></td>
<td><p>役割の種類の説明。 次の4つの役割を使用できます。</p>
<ul>
<li><p>メンバー: チャットルームのメンバー</p></li>
<li><p>管理職: チャットルームマネージャー</p></li>
<li><p>読み上げ: 聴衆チャットルームの発表者</p></li>
<li><p>作成者: チャットルームを作成できる</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>rtypeAllowedPermSet</p></td>
<td><p>bigint (null ではない)</p></td>
<td><p>ロールの権限セット。 使用されるビットは次のとおりです。</p>
<ul>
<li><p>2: 役割がノードを管理できる場合は True。</p></li>
<li><p>4: 役割で子ノードを作成できる場合は True です。</p></li>
<li><p>7: 役割がチャットルーム (または、カテゴリの子チャットルーム) に参加できる場合は True。</p></li>
<li><p>8: 役割がチャットルーム (または、カテゴリの子チャットルーム) でチャットできる場合は True。</p></li>
<li><p>10: 役割がチャットルームに参加していないときでもチャット履歴を読むことができる場合は True。</p></li>
<li><p>11: 役割がチャットルームを表示できる場合は True です。 (これは、スコープや可視性などの要因によってさらに改良されています)。</p></li>
<li><p>12: この役割が聴衆チャットルームでチャットできる場合は True です。</p></li>
<li><p>13: ノードを表示したときに、役割が可視性規則を無視できる場合は True です。</p></li>
</ul></td>
</tr>
</tbody>
</table>


### <a name="key"></a>キー

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>列</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>rtypeID</p></td>
<td><p>主キー。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

