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
ms.openlocfilehash: f68c638b16ae0e7a253c063351784ce9f7d4d7c5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509474"
---
# <a name="tblchat-in-lync-server-2013"></a>Lync Server 2013 の tblChat

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-12_

tblChat には、すべてのチャット メッセージが格納されます。

### <a name="columns"></a>段組み

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Column</th>
<th>種類</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>channelId</p></td>
<td><p>NULL でない int</p></td>
<td><p>ノード ID。</p></td>
</tr>
<tr class="even">
<td><p>chatId</p></td>
<td><p>NULL でない bigint</p></td>
<td><p>チャット ルームの順番を定義する一意の連続番号 (ノード ID ごと)。tblLastChatId テーブルによって生成されます。</p></td>
</tr>
<tr class="odd">
<td><p>chatDate</p></td>
<td><p>NULL でない bigint</p></td>
<td><p>チャット メッセージのタイムスタンプ。</p></td>
</tr>
<tr class="even">
<td><p>userId</p></td>
<td><p>NULL でない int</p></td>
<td><p>投稿者のプリンシパル ID。</p></td>
</tr>
<tr class="odd">
<td><p>isAlert</p></td>
<td><p>NULL でない bit</p></td>
<td><p>メッセージが警告メッセージの場合は True、警告メッセージでない場合は False。</p></td>
</tr>
<tr class="even">
<td><p>content</p></td>
<td><p>NULL でない nvarchar (max)</p></td>
<td><p>チャットの内容 (プレーン テキスト バージョン)。内容は、通常、プレーン テキストですが、次の例外があります。</p>
<ul>
<li><p>ファイルは ma-filelink: リンクとして表されます。</p></li>
<li><p>リンクは HTML 要素として表されます (ただし、コンテンツの種類は HTML とは見なされません)。</p></li>
<li><p>ストーリーは “[STORY]....” のような形式でエンコードされます。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>rtf</p></td>
<td><p>varchar (max)</p></td>
<td><p>チャットの内容 (RTF バージョン)。クライアントによって提供されない場合は NULL になります。</p></td>
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

