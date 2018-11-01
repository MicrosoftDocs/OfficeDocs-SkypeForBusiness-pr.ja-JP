---
title: 'Lync Server 2013: tblPreference'
TOCTitle: tblPreference
ms:assetid: f94eb128-f782-42ff-a568-ed3529573bc8
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg615052(v=OCS.15)
ms:contentKeyID: 48274113
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の tblPreference

 

_**トピックの最終更新日:** 2015-03-09_

tblPreference には、ユーザーのクライアントの設定が格納されています。これは一般に、 Lync 2013 より前のクライアントによって使用されます。

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
<td><p>prefLabel</p></td>
<td><p>NULL でない nvarchar (255)</p></td>
<td><p>&lt;user sip uri&gt;|username.&lt;preference set&gt; などの形式のラベル。</p></td>
</tr>
<tr class="even">
<td><p>prefSeqID</p></td>
<td><p>NULL でない int</p></td>
<td><p>バージョン付けのための連続した番号 (ラベルごと)。</p></td>
</tr>
<tr class="odd">
<td><p>prefContent</p></td>
<td><p>nvarchar (max)</p></td>
<td><p>エンコードされたコンテンツ。</p></td>
</tr>
<tr class="even">
<td><p>lastModifiedBy</p></td>
<td><p>NULL でない int</p></td>
<td><p>この設定を更新したプリンシパルの ID。</p></td>
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
<td><p>&lt;prefLabel, prefSeqID&gt;</p></td>
<td><p>主キー。</p></td>
</tr>
</tbody>
</table>

