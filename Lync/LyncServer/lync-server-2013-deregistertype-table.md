---
title: 'Lync Server 2013: DeRegisterType テーブル'
description: 'Lync Server 2013: DeRegisterType テーブル。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DeRegisterType table
ms:assetid: 09148118-6209-4fd7-a494-99118689a245
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398142(v=OCS.15)
ms:contentKeyID: 48183346
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: afad63c2abeba3e91565e07dac75d0ac6c96ca3a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555353"
---
# <a name="deregistertype-table-in-lync-server-2013"></a>Lync Server 2013 の DeRegisterType テーブル

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-28_

DeRegisterType テーブルは、使用できるユーザー登録解除の種類 ("クライアント開始済み"、"登録期限切れ"、"クライアント停止済み" など) の一覧を格納する静的テーブルです。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Column</th>
<th>データ型</th>
<th>キー/インデックス</th>
<th>詳細</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>DeRegisterTypeId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Primary</p></td>
<td></td>
</tr>
<tr class="even">
<td><p><strong>DeRegisterReason</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td></td>
<td><p>有効な値は次のとおりです。</p>
<ul>
<li><p>0 -- 不明</p></li>
<li><p>1 -- クライアントが登録解除を開始済み</p></li>
<li><p>2 -- 登録期限切れ</p></li>
<li><p>3 – クライアントのクラッシュ</p></li>
<li><p>4 -- ユーザー属性変更</p></li>
<li><p>5 - 優先レジストラー変更</p></li>
<li><p>6 -- サバイバル モードのレガシ クライアント</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

