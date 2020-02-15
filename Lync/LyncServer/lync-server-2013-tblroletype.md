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
ms.openlocfilehash: ab96d6cd090ebaaa9e33ddf1672ab704ee371f8b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046150"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblroletype-in-lync-server-2013"></a>Lync Server 2013 の tblRoleType

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-06-25_

tblRoleType は静的な検索テーブルであり、役割の種類とそれに関連付けられたアクセス許可のセットが格納されています。

### <a name="columns"></a>Columns

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>列</th>
<th>種類</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Tblroletype.rtypeid</p></td>
<td><p>NULL でない int</p></td>
<td><p>役割の種類の ID。</p></td>
</tr>
<tr class="even">
<td><p>rtypeDesc</p></td>
<td><p>NULL でない nvarchar (256)</p></td>
<td><p>役割の種類の説明。使用できる役割は次の 4 つです。</p>
<ul>
<li><p>メンバー: チャット ルームのメンバー</p></li>
<li><p>マネージャー: チャット ルームのマネージャー</p></li>
<li><p>承認されたメンバー: 大会議室のチャット ルームの発表者</p></li>
<li><p>作成者: チャット ルームの作成者</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>rtypeAllowedPermSet</p></td>
<td><p>NULL でない bigint</p></td>
<td><p>役割のアクセス許可セット。使用されるビットは次のとおりです。</p>
<ul>
<li><p>2: 役割がノードを管理できる場合は True。</p></li>
<li><p>4: 役割が子ノードを作成できる場合は True。</p></li>
<li><p>7: 役割がチャット ルーム (またはカテゴリの子チャット ルーム) に参加できる場合は True。</p></li>
<li><p>8: 役割がチャット ルーム (またはカテゴリの子チャット ルーム) でチャットできる場合は True。</p></li>
<li><p>10: 役割がチャット ルームに参加していなくてもチャットの履歴を読むことができる場合は True。</p></li>
<li><p>11: 役割がチャット ルームを見ることができる場合は True (これはスコープや可視性などの要素によってさらに微調整されます)。</p></li>
<li><p>12: 役割が大会議室のチャット ルームでチャットできる場合は True。</p></li>
<li><p>13: 役割がノードを表示するときに可視性ルールをバイパスできる場合は True。</p></li>
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
<td><p>Tblroletype.rtypeid</p></td>
<td><p>主キー。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

