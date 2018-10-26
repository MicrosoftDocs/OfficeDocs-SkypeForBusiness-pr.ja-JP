---
title: 'Lync Server 2013: tblSkippedAffiliations'
TOCTitle: tblSkippedAffiliations
ms:assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg558611(v=OCS.15)
ms:contentKeyID: 48271218
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の tblSkippedAffiliations

 

_**トピックの最終更新日:** 2015-03-09_

tblSkippedAffiliations には、(通常は Active Directory ドメイン サービス アクセス エラーのため) 読み取ることができなかった所属が格納されます。

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
<td><p>affDescription</p></td>
<td><p>NULL でない nvarchar (256)</p></td>
<td><p>所属を示す文字列。</p>
<p>形式: guid: <em>{0}</em> uri: <em>{1}</em> &gt; id: <em>{2}</em></p></td>
</tr>
<tr class="odd">
<td><p>updatedBy</p></td>
<td><p>NULL でない int</p></td>
<td><p>この行を更新したプリンシパルの ID。これらのエントリのソースは Active Directory の同期だけなので、常に 1 (システム ユーザー) です。</p></td>
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
<td><p>&lt;prinID、affDescription&gt;</p></td>
<td><p>主キー。</p></td>
</tr>
<tr class="even">
<td><p>prinID</p></td>
<td><p>tblPrincipal.prinID テーブルを参照する外部キー。</p></td>
</tr>
</tbody>
</table>

