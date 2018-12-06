---
title: 'Lync Server 2013: tblConfig'
TOCTitle: tblConfig
ms:assetid: 7445e7db-c574-46fa-b964-8640d77047a8
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg558663(v=OCS.15)
ms:contentKeyID: 48272467
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の tblConfig

 

_**トピックの最終更新日:** 2015-03-09_

tblConfig には、 常設チャット サーバーでサポートされないいくつかの構成が 1 行に格納されています。

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
<td><p>configLabel</p></td>
<td><p>NULL でない nvarchar (255)</p></td>
<td><p>&quot;プール&quot; を含みます。</p></td>
</tr>
<tr class="even">
<td><p>configContent</p></td>
<td><p>nvarchar (max)</p></td>
<td><p>構成の内容です。</p></td>
</tr>
<tr class="odd">
<td><p>configPoolID</p></td>
<td><p>NULL でない GUID</p></td>
<td><p>データベース インスタンスの一意の識別子。</p></td>
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
<td><p>configLabel</p></td>
<td><p>主キー。</p></td>
</tr>
</tbody>
</table>

