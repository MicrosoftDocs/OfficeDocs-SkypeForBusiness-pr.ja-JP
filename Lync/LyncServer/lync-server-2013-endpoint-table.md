---
title: 'Lync Server 2013: Endpoint テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Endpoint table
ms:assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398327(v=OCS.15)
ms:contentKeyID: 48184098
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a71e59b6cf9b4143a5b984cc7b169279aa2cb57
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533324"
---
# <a name="endpoint-table-in-lync-server-2013"></a>Lync Server 2013 のエンドポイントテーブル

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-02_

エンドポイントテーブルは、データベースに記録されたセッションに参加しているエンドポイントに関する情報を格納するサポートテーブルです。 テーブル内の各レコードは、1つのエンドポイントを表します。


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
<td><p><strong>EndpointKey</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>このエンドポイントを識別する一意の番号です。</p></td>
</tr>
<tr class="even">
<td><p><strong>名前</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>一意</p></td>
<td><p>エンドポイント名。</p></td>
</tr>
<tr class="odd">
<td><p><strong>OS</strong></p></td>
<td><p>nvarchar(128</p></td>
<td><p> </p></td>
<td><p>エンドポイントのオペレーティングシステム (OS)。</p></td>
</tr>
<tr class="even">
<td><p><strong>CPUName</strong></p></td>
<td><p>nvarchar(128</p></td>
<td></td>
<td><p>エンドポイントの CPU 名。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CPUNumberOfCores</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>エンドポイントの CPU コアの数。</p></td>
</tr>
<tr class="even">
<td><p><strong>Cpu プロセッサ速度</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>エンドポイントの CPU プロセッサ速度。</p></td>
</tr>
<tr class="odd">
<td><p><strong>VirtualizationFlag</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>システムが仮想化環境で実行されているかどうかを示すビットフラグ。</p>
<ul>
<li><p>0x0000 –なし</p></li>
<li><p>0x0001 – HyperV</p></li>
<li><p>0x0002 –ヴイエムウェア</p></li>
<li><p>0x0004 –仮想 PC</p></li>
<li><p>0x0008 – Xen PC</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

