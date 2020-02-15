---
title: 'Lync Server 2013: tblADCookie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblADCookie
ms:assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558610(v=OCS.15)
ms:contentKeyID: 48183366
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f733397483693ad4c18418f3e82b9f99cfa640f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42031191"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tbladcookie-in-lync-server-2013"></a>Lync Server 2013 の tblADCookie

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-06-25_

tblADCookie には、現在のライトウェイト ディレクトリ アクセス プロトコル (LDAP) 同期 Cookie が格納されます。

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
<td><p>Principal.pringuid</p></td>
<td><p>NULL でない GUID</p></td>
<td><p>監視対象のドメインのプリンシパル GUID。</p></td>
</tr>
<tr class="even">
<td><p>prinDCHost</p></td>
<td><p>nvarchar (255)</p></td>
<td><p>Active Directory ドメインサービスの同期に使用される現在のドメインコントローラーの完全修飾ドメイン名 (FQDN)。情報の値があります。</p></td>
</tr>
<tr class="odd">
<td><p>adcContent</p></td>
<td><p>image (バイナリ)</p></td>
<td><p>Active Directory の同期 Cookie。</p></td>
</tr>
<tr class="even">
<td><p>lastUpdated</p></td>
<td><p>日付型</p></td>
<td><p>行更新時刻でのタイムスタンプ。</p></td>
</tr>
<tr class="odd">
<td><p>lockedUntil</p></td>
<td><p>日付型</p></td>
<td><p>行が変更のためにロックされるまでの時間。これは、一度に 1 つのチャット サービスのみが Active Directory 同期を行うことを保証するソフトウェア インタロック メカニズムの一部です。</p></td>
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
<th>列 (複数可)</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Principal.pringuid</p></td>
<td><p>主キー。</p></td>
</tr>
<tr class="even">
<td><p>Principal.pringuid</p></td>
<td><p>Principal.prinGuid テーブル内の参照による外部キー。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

