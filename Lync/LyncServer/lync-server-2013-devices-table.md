---
title: 'Lync Server 2013: Devices テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Devices table
ms:assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398351(v=OCS.15)
ms:contentKeyID: 48184169
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f78e0b4ba3bb5271a2de43e423dfa4b3baf17cf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833414"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="devices-table-in-lync-server-2013"></a>Lync Server 2013 の Devices テーブル

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-05-25_

Devices テーブルは、サポートテーブルです。 各レコードには、1つのデバイス (卓上電話) に関する情報が格納されます。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>列</th>
<th>データ型</th>
<th>キー/インデックス</th>
<th>詳細</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>DeviceId</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>このハードウェアバージョンを識別する一意の番号。</p></td>
</tr>
<tr class="even">
<td><p><strong>Manufacturerid]</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>このデバイスの製造元。 詳細については、「 <a href="lync-server-2013-manufacturers-table.md">Lync Server 2013 の製造元の表</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ハードウェアの Versionid</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>このデバイスのハードウェアバージョン。 詳細については、「 <a href="lync-server-2013-hardwareversions-table.md">Lync Server 2013 のハードウェアバージョンの表</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>MacAddress</strong></p></td>
<td><p>bigint</p></td>
<td></td>
<td><p>MAC アドレス</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

