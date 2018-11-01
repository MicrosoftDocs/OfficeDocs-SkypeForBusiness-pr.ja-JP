---
title: 'Lync Server 2013: tblLastInviteId'
TOCTitle: tblLastInviteId
ms:assetid: 222b3508-5963-4ddc-b4f3-e8412767e61b
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg558625(v=OCS.15)
ms:contentKeyID: 48271491
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の tblLastInviteId

 

_**トピックの最終更新日:** 2015-03-09_

tblLastInviteId には、各ユーザーに対して生成された (そして tblPrincipalInvites テーブルで使用された) 最後の招待 ID が格納されます。

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
<td><p>prinID</p></td>
<td><p>NULL でない int</p></td>
<td><p>プリンシパル ID。</p></td>
</tr>
<tr class="even">
<td><p>lastInviteID</p></td>
<td><p>NULL でない int</p></td>
<td><p>最後に使用された招待 ID。</p></td>
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
<td><p>prinID</p></td>
<td><p>主キー。</p></td>
</tr>
<tr class="even">
<td><p>prinID</p></td>
<td><p>tblPrincipal.prinID テーブルを参照する外部キー。</p></td>
</tr>
</tbody>
</table>


## 関連項目

#### 概念

[Lync Server 2013 の tblPrincipalInvites](lync-server-2013-tblprincipalinvites.md)

