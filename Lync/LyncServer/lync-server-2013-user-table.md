---
title: 'Lync Server 2013: User テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: User table
ms:assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398505(v=OCS.15)
ms:contentKeyID: 48184437
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4baaf8b8dea0f9e5aa77986791c82051fc00e90b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848335"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-table-in-lync-server-2013"></a>Lync Server 2013 の User テーブル

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-02_

ユーザーテーブルは、データベースに記録されているセッションに参加しているさまざまなユーザーの一覧を格納するサポートテーブルです。 テーブル内の各レコードは、1人のユーザーを表します。


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
<td><p><strong>UserKey</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>このユーザーを識別する一意の番号です。</p></td>
</tr>
<tr class="even">
<td><p><strong>URI</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>一意</p></td>
<td><p>URI 文字列。</p></td>
</tr>
<tr class="odd">
<td><p><strong>URIType</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>1の URI の型が不明です。</p>
<p>2はユーザー URI です。</p>
<p>4は会議の URI です。</p>
<p>8は電話の URI です。</p></td>
</tr>
<tr class="even">
<td><p><strong>TenantKey</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>テナントテーブルから参照されたユーザーのテナント。</p></td>
</tr>
<tr class="odd">
<td><p><strong>LastPoorCallTime</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>ユーザーが低品質の音声通話を行ったときの最新のタイムスタンプ。</p></td>
</tr>
<tr class="even">
<td><p><strong>Nextupdatupdat</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>内部使用のみ。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

