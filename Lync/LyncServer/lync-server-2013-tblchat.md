---
title: 'Lync Server 2013: tblChat'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblChat
ms:assetid: b7fcf1b4-7a3f-4585-a6d9-95e7f030c7dc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615031(v=OCS.15)
ms:contentKeyID: 48185203
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f3879924b37fa535973116af599f4713c58a207
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764223"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblchat-in-lync-server-2013"></a>Lync Server 2013 の tblChat

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-12_

tblChat には、すべてのチャットメッセージが含まれています。

### <a name="columns"></a>行

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>列</th>
<th>型</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>channelId</p></td>
<td><p>int (null ではない)</p></td>
<td><p>ノード ID。</p></td>
</tr>
<tr class="even">
<td><p>chatId</p></td>
<td><p>bigint (null ではない)</p></td>
<td><p>TblLastChatId テーブルによって生成されたチャットルームの順序を定義する一意の連続番号 (1 ノードあたりの ID)。</p></td>
</tr>
<tr class="odd">
<td><p>chatDate</p></td>
<td><p>bigint (null ではない)</p></td>
<td><p>チャットメッセージのタイムスタンプ。</p></td>
</tr>
<tr class="even">
<td><p>userId</p></td>
<td><p>int (null ではない)</p></td>
<td><p>ポスターのプリンシパル ID。</p></td>
</tr>
<tr class="odd">
<td><p>isAlert</p></td>
<td><p>ビット、null ではない</p></td>
<td><p>メッセージが通知メッセージの場合は True です。 見つからない場合は False。</p></td>
</tr>
<tr class="even">
<td><p>コンテンツ</p></td>
<td><p>nvarchar (max)、null ではない</p></td>
<td><p>チャットコンテンツ (テキスト形式)。 通常、コンテンツはテキスト形式であり、次の例外があります。</p>
<ul>
<li><p>ファイルは、ma-filelink: リンクとして表されます。</p></li>
<li><p>リンクは HTML 要素として表示されます (ただし、コンテンツの種類は HTML と見なすことはできません)。</p></li>
<li><p>ストーリーは、"[ストーリー]..." という形式でエンコードされます。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>rtf</p></td>
<td><p>varchar (max)</p></td>
<td><p>チャットコンテンツ (RTF バージョン)。 クライアントが指定しない場合は Null になります。</p></td>
</tr>
</tbody>
</table>


### <a name="key"></a>キー

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
<td><p>&lt;channelID、chatD&gt;</p></td>
<td><p>主キー。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

