---
title: 'Lync Server 2013: Subnet テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Subnet table
ms:assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398582(v=OCS.15)
ms:contentKeyID: 48184544
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20318d0ed2f487efccda81936b113044f75e2618
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848659"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="subnet-table-in-lync-server-2013"></a>Lync Server 2013 の Subnet テーブル

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-02_

サブネットの表はサポートテーブルです。 各レコードは、[ネットワーク構成] の設定で定義された1つのサブネットを表します。


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
<td><p><strong>SubnetIP</strong></p></td>
<td><p>int</p></td>
<td><p>プライマリ、外部</p></td>
<td><p>サブネットの IP の整数表現。</p></td>
</tr>
<tr class="even">
<td><p><strong>ネット</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>サブネット マスク。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserSiteKey</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p><a href="lync-server-2013-usersite-table.md">Lync Server 2013 の Usersite テーブル</a>から参照されます。</p></td>
</tr>
<tr class="even">
<td><p><strong>サブネットの説明</strong></p></td>
<td><p>nvarchar (512)</p></td>
<td></td>
<td><p>サブネットの説明。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

