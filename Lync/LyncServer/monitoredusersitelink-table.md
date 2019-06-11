---
title: MonitoredUserSiteLink テーブル
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: MonitoredUserSiteLink table
ms:assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398233(v=OCS.15)
ms:contentKeyID: 48183508
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f5de189abc64271a915cfe88ae450dc349709e0d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848044"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoredusersitelink-table"></a>MonitoredUserSiteLink テーブル

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-02_

MonitoredUserSiteLink リンクテーブルは、サポートテーブルです。 各レコードは、2つのユーザーサイト間のリンク1つを表します。


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
<td><p><strong>UserSite1Key</strong></p></td>
<td><p>int</p></td>
<td><p>プライマリ、外部</p></td>
<td><p><a href="lync-server-2013-usersite-table.md">Lync Server 2013 の Usersite テーブル</a>から参照されます。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserSite2Key</strong></p></td>
<td><p>int</p></td>
<td><p>プライマリ、外部</p></td>
<td><p><a href="lync-server-2013-usersite-table.md">Lync Server 2013 で Usersite テーブル</a>から参照します。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

