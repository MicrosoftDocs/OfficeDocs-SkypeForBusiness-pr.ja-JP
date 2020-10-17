---
title: 'Lync Server 2013: UserSite テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UserSite table
ms:assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398256(v=OCS.15)
ms:contentKeyID: 48183552
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 656bf8f692617392db02e186fcccebba25a01b0d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530004"
---
# <a name="usersite-table-in-lync-server-2013"></a>Lync Server 2013 の UserSite テーブル

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2010-11-09_

UserSite テーブルはサポート テーブルです。各レコードは、ネットワーク構成の設定で定義されている 1 つのユーザー サイトを表します。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>列</strong></th>
<th><strong>データ型</strong></th>
<th><strong>キー/インデックス</strong></th>
<th><strong>詳細</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>UserSiteKey</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>ユーザー サイトを示す一意の番号です。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserSiteName</strong></p></td>
<td><p>nvarchar(128</p></td>
<td><p>一意</p></td>
<td><p>ユーザー サイトの名前です。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RegionKey</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p><a href="lync-server-2013-region-table.md">Lync Server 2013 の Region テーブル</a>から参照されます。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

