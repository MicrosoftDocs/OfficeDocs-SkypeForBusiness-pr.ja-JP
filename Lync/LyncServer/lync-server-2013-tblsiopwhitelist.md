---
title: 'Lync Server 2013: tblSiopWhiteList'
TOCTitle: tblSiopWhiteList
ms:assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg558607(v=OCS.15)
ms:contentKeyID: 48271147
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の tblSiopWhiteList

 

_**トピックの最終更新日:** 2015-03-09_

tblSiopWhiteList は、ノードと関連付けることができる登録済みアドインの一覧です。

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
<td><p>siopID</p></td>
<td><p>NULL でない GUID</p></td>
<td><p>アドインの GUID。</p></td>
</tr>
<tr class="even">
<td><p>siopName</p></td>
<td><p>NULL でない nvarchar (50)</p></td>
<td><p>アドインの表示名。</p></td>
</tr>
<tr class="odd">
<td><p>siopUrl</p></td>
<td><p>NULL でない nvarchar (255)</p></td>
<td><p>アドインの URL。</p></td>
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
<td><p>siopID</p></td>
<td><p>主キー。</p></td>
</tr>
</tbody>
</table>

