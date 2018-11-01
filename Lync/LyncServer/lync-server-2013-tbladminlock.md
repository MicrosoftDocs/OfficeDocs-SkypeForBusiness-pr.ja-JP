---
title: 'Lync Server 2013: tblAdminLock'
TOCTitle: tblAdminLock
ms:assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg558665(v=OCS.15)
ms:contentKeyID: 48272579
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の tblAdminLock

 

_**トピックの最終更新日:** 2015-03-09_

tblAdminLock には、一部の管理者コマンドの実行に必要な管理者ロックが格納されます。

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
<td><p>lockExpiresTime</p></td>
<td><p>NULL でない datetime</p></td>
<td><p>ロックの有効期限の日時。所有者はこの値による期限を定期的に延長できます。</p></td>
</tr>
<tr class="even">
<td><p>lockServerID</p></td>
<td><p>NULL でない int</p></td>
<td><p>ロックを所有するサーバーの ID。</p></td>
</tr>
<tr class="odd">
<td><p>lockActorID</p></td>
<td><p>NULL でない int</p></td>
<td><p>ロックを所有するプリンシパルの ID。</p></td>
</tr>
</tbody>
</table>

