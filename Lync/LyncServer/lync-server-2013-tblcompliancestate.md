---
title: 'Lync Server 2013: tblComplianceState'
TOCTitle: tblComplianceState
ms:assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg615045(v=OCS.15)
ms:contentKeyID: 48274036
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の tblComplianceState

 

_**トピックの最終更新日:** 2015-03-09_

tblComplianceState には、プール全体のコンプライアンス状態の情報が格納されます。

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
<td><p>lastProcessedEntryID</p></td>
<td><p>NULL でない bigint</p></td>
<td><p>直近に処理されたコンプライアンス イベントのID。</p></td>
</tr>
<tr class="even">
<td><p>activeServerID</p></td>
<td><p>NULL でない int</p></td>
<td><p>データベースの排他ロックを保持しているコンプライアンス サーバーの ID。存在しない場合は -1。</p></td>
</tr>
<tr class="odd">
<td><p>lockExpirationTime</p></td>
<td><p>NULL でない datetime2</p></td>
<td><p>ロックの有効期限 (activeServerID が -1 でない場合)。</p></td>
</tr>
</tbody>
</table>

