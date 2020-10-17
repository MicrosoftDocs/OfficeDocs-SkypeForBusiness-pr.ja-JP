---
title: 'Lync Server 2013: UserAgent テーブル'
description: 'Lync Server 2013: UserAgent テーブル。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UserAgent table
ms:assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398939(v=OCS.15)
ms:contentKeyID: 48185582
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b701d8384313d0267dd566e0c32242f6cc077472
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558893"
---
# <a name="useragent-table-in-lync-server-2013"></a>Lync Server 2013 の UserAgent テーブル

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-05-25_

UserAgent テーブルは、データベースに記録されたセッションに参加しているさまざまなユーザーエージェントのリストを格納するサポートテーブルです。 テーブル内の各レコードは、1つのユーザーエージェントを表します。


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
<td><p><strong>UserAgentKey</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>このユーザーエージェントを識別する一意の番号。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserAgent</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>一意</p></td>
<td><p>ユーザーエージェント文字列。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UAType</strong></p></td>
<td><p>smallint</p></td>
<td><p> </p></td>
<td><p>1は仲介サーバーです。</p>
<p>2は音声ビデオ会議サーバーです。</p>
<p>4は Lync です。</p>
<p>8は IP 電話です。</p>
<p>16は Live Meeting コンソールです。</p>
<p>32は展開検証ツール (DVT) です。</p>
<p>64は、Macintosh コンピューターの Lync です。</p>
<p>128は、Office Communications Server 2007 R2 アテンダントです。</p>
<p>256は会議アナウンスサービスです。</p>
<p>512は、会議自動応答です。</p>
<p>1024は応答グループアプリケーションです。</p>
<p>2048は外部音声コントロールです。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

