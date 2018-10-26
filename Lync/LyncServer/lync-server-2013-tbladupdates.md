---
title: 'Lync Server 2013: tblADUpdates'
TOCTitle: tblADUpdates
ms:assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg615033(v=OCS.15)
ms:contentKeyID: 48273387
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の tblADUpdates

 

_**トピックの最終更新日:** 2015-03-09_

tblADUpdates には、最新の Active Directory の同期の手順でまだ処理されていない Active Directory ドメイン サービス の変更が含まれています。

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
<td><p>prinGuid</p></td>
<td><p>NULL でない GUID</p></td>
<td><p>変更したオブジェクトのプリンシパル GUID。</p></td>
</tr>
<tr class="even">
<td><p>prinADPath</p></td>
<td><p>NULL でない nvarchar (384)</p></td>
<td><p>オブジェクトの識別名。</p></td>
</tr>
<tr class="odd">
<td><p>prinAttributesChanged</p></td>
<td><p>NULL でない bit</p></td>
<td><p>オブジェクトの属性が 1 つ以上変更された場合は True。</p></td>
</tr>
<tr class="even">
<td><p>prinMembersChanged</p></td>
<td><p>NULL でない bit</p></td>
<td><p>メンバーシップが変更された場合は True。</p></td>
</tr>
<tr class="odd">
<td><p>prinAffiliationsChanged</p></td>
<td><p>NULL でない bit</p></td>
<td><p>不使用。</p></td>
</tr>
<tr class="even">
<td><p>prinDeleted</p></td>
<td><p>NULL でない bit</p></td>
<td><p>オブジェクトが削除された場合は True。</p></td>
</tr>
<tr class="odd">
<td><p>lastUpdated</p></td>
<td><p>NULL でない datetime</p></td>
<td><p>行が挿入された時点のタイムスタンプ。</p></td>
</tr>
</tbody>
</table>

