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
ms.openlocfilehash: b9d5122b375b4906320f254179ce101652ad6db2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048000"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipal-in-lync-server-2013"></a>Lync Server 2013 の tblPrincipal

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-12_

tblPrincipal テーブルには、ユーザー、フォルダー、グループなど、すべてのプリンシパルが格納されます。

### <a name="columns"></a>Columns

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>列</th>
<th>種類</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Tblprincipal.prinid</p></td>
<td><p>NULL でない int</p></td>
<td><p>プリンシパル ID。</p></td>
</tr>
<tr class="even">
<td><p>Principal.pringuid</p></td>
<td><p>NULL でない GUID</p></td>
<td><p>プリンシパル GUID。 これは、代替主キーとして広く使用されています。これは、Active Directory ドメインサービスの領域にわたる意味があるためです。 (キャッシュされたプリンシパルの GUID は、対応する Active Directory オブジェクトの GUID と同じです。)</p></td>
</tr>
<tr class="odd">
<td><p>prinUri</p></td>
<td><p>NULL でない nvarchar (256)</p></td>
<td><p>プリンシパル URI。SIP スキームはユーザーで使用され、ma-grp はユーザーを除くほぼすべてで使用されます。</p></td>
</tr>
<tr class="even">
<td><p>prinName</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>共通名。ユーザーの種類でのみ使用されます。</p></td>
</tr>
<tr class="odd">
<td><p>prinDisplayName</p></td>
<td><p>Nvarchar (256)</p></td>
<td><p>表示名。ユーザーの種類でのみ使用されます。</p></td>
</tr>
<tr class="even">
<td><p>prinCompanyName</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>会社名。ユーザーの種類でのみ使用されます。</p></td>
</tr>
<tr class="odd">
<td><p>prinEmail</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>電子メール。ユーザーの種類でのみ使用されます。</p></td>
</tr>
<tr class="even">
<td><p>prinADPath</p></td>
<td><p>nvarchar (384)</p></td>
<td><p>プリンシパルがキャッシュされたバージョンである Active Directory オブジェクトのドメイン名。Active Directory オブジェクトでない種類 (システム ユーザーなど) では NULL になります。</p></td>
</tr>
<tr class="odd">
<td><p>prinADUserPrincipalName</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>ユーザーのユーザー プリンシパル名 (UPN)。通常のユーザーの種類でのみ使用されます。</p></td>
</tr>
<tr class="even">
<td><p>prinDisabled</p></td>
<td><p>NULL でない smallint</p></td>
<td><ul>
<li><p>0: プリンシパルはアクティブです。</p></li>
<li><p>1: ユーザーの SIP 機能が無効であるため、プリンシパルは無効です。</p></li>
<li><p>2: 関連付けられている AD オブジェクトが削除されたため、プリンシパルは削除されます。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>prinTypeID</p></td>
<td><p>NULL でない smallint</p></td>
<td><p>プリンシパルの種類 (tblPrincipalType テーブルに基づいています)。</p></td>
</tr>
<tr class="even">
<td><p>prinPoolID</p></td>
<td><p>Int</p></td>
<td><p>プリンシパルの Lync プールの割り当て。</p></td>
</tr>
<tr class="odd">
<td><p>prinPolicyID</p></td>
<td><p>Int</p></td>
<td><p>タグの種類のポリシーが存在する場合、ユーザーの常設チャットサーバーポリシーの値。</p></td>
</tr>
<tr class="even">
<td><p>prinAddedBy</p></td>
<td><p>int</p></td>
<td><p>作成者のプリンシパル ID。</p></td>
</tr>
<tr class="odd">
<td><p>prinAddedOn</p></td>
<td><p>NULL でない bigint</p></td>
<td><p>作成時刻のタイム スタンプ。</p></td>
</tr>
<tr class="even">
<td><p>プリント</p></td>
<td><p>int</p></td>
<td><p>このテーブルを最後に更新したプリンシパルの ID。</p></td>
</tr>
<tr class="odd">
<td><p>prinUpdatedOn</p></td>
<td><p>NULL でない bigint</p></td>
<td><p>最後の更新のタイム スタンプ。</p></td>
</tr>
<tr class="even">
<td><p>prinVerifiedOn</p></td>
<td><p>NULL でない datetime</p></td>
<td><p>プリンシパルに対する Active Directory の同期による最終更新の日付と時刻。</p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a>Keys

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
<td><p>Tblprincipal.prinid</p></td>
<td><p>主キー。</p></td>
</tr>
<tr class="even">
<td><p>prinTypeID</p></td>
<td><p>tblPrincipalType.ptypeID テーブルを参照する外部キー。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

