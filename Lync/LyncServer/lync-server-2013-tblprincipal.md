---
title: 'Lync Server 2013: tblPrincipal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipal
ms:assetid: 79a24502-b4ce-41f0-8979-8caddf535338
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558667(v=OCS.15)
ms:contentKeyID: 48184571
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 25de9273fb6e153bb154bf0062edd96cb67bbac2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731537"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipal-in-lync-server-2013"></a>Lync Server 2013 の tblPrincipal

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-12_

tblPrincipal には、ユーザー、フォルダー、グループを含むすべてのプリンシパルが含まれています。

### <a name="columns"></a>行

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
<td><p>int (null ではない)</p></td>
<td><p>プリンシパル ID。</p></td>
</tr>
<tr class="even">
<td><p>prinGuid</p></td>
<td><p>GUID、null ではない</p></td>
<td><p>プリンシパル GUID。 これは、プライマリキーとして広く使用されており、その意味は Active Directory ドメインサービスの領域にあります。 (キャッシュされるプリンシパルの GUID は、対応する Active Directory オブジェクト GUID と同じです)。</p></td>
</tr>
<tr class="odd">
<td><p>prinUri</p></td>
<td><p>nvarchar (256)、null ではない</p></td>
<td><p>プリンシパル URI。 SIP スキームはユーザのために使用され、ma はその他ほとんどすべてに使用されます。</p></td>
</tr>
<tr class="even">
<td><p>prinName</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>共通名。 ユーザーの種類によってのみ使用されます。</p></td>
</tr>
<tr class="odd">
<td><p>prinDisplayName</p></td>
<td><p>Nvarchar (256)</p></td>
<td><p>表示名。 ユーザーの種類によってのみ使用されます。</p></td>
</tr>
<tr class="even">
<td><p>prinCompanyName</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>会社名。 ユーザーの種類によってのみ使用されます。</p></td>
</tr>
<tr class="odd">
<td><p>メールをプリントする</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>電子メール。 ユーザーの種類によってのみ使用されます。</p></td>
</tr>
<tr class="even">
<td><p>prinADPath</p></td>
<td><p>nvarchar (384)</p></td>
<td><p>プリンシパルがキャッシュされたバージョンである Active Directory オブジェクトのドメイン名。 Active Directory オブジェクト (システムユーザーなど) ではない型の場合は Null にすることができます。</p></td>
</tr>
<tr class="odd">
<td><p>プリント</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>ユーザーのユーザープリンシパル名 (UPN)。 通常のユーザーの種類でのみ使用されます。</p></td>
</tr>
<tr class="even">
<td><p>prinDisabled</p></td>
<td><p>smallint (null ではない)</p></td>
<td><ul>
<li><p>0: プリンシパルは有効です。</p></li>
<li><p>1: ユーザーの SIP 機能が無効になっているため、プリンシパルが無効になっています。</p></li>
<li><p>2: 関連付けられている広告オブジェクトが削除されたため、プリンシパルが削除されました。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>prinTypeID</p></td>
<td><p>smallint (null ではない)</p></td>
<td><p>プリンシパルの種類 (tblPrincipalType テーブルから)。</p></td>
</tr>
<tr class="even">
<td><p>prinPoolID</p></td>
<td><p>Int</p></td>
<td><p>プリンシパルの Lync プールの割り当て。</p></td>
</tr>
<tr class="odd">
<td><p>prinPolicyID</p></td>
<td><p>Int</p></td>
<td><p>タグの種類のポリシーが存在する場合は、ユーザーの常設チャットサーバーポリシーの値。</p></td>
</tr>
<tr class="even">
<td><p>プリント</p></td>
<td><p>int</p></td>
<td><p>作成者のプリンシパル ID。</p></td>
</tr>
<tr class="odd">
<td><p>prinAddedOn</p></td>
<td><p>bigint (null ではない)</p></td>
<td><p>作成時刻のタイムスタンプ。</p></td>
</tr>
<tr class="even">
<td><p>プリント</p></td>
<td><p>int</p></td>
<td><p>最後に更新したプリンシパルの ID です。</p></td>
</tr>
<tr class="odd">
<td><p>prinUpdatedOn</p></td>
<td><p>bigint (null ではない)</p></td>
<td><p>最終更新のタイムスタンプ。</p></td>
</tr>
<tr class="even">
<td><p>prinVerifiedOn</p></td>
<td><p>datetime。 null ではありません</p></td>
<td><p>プリンシパルの前回の Active Directory 同期更新の日付と時刻。</p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a>機能

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
<td><p>prinTypeID</p></td>
<td><p>TblPrincipalType テーブルで参照する外部キー。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

