---
title: 'Lync Server 2013: tblRoleType'
TOCTitle: tblRoleType
ms:assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg558623(v=OCS.15)
ms:contentKeyID: 48271464
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の tblRoleType

 

_**トピックの最終更新日:** 2015-03-09_

tblRoleType は静的な検索テーブルであり、役割の種類とそれに関連付けられたアクセス許可のセットが格納されています。

### 列

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


### キー

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

