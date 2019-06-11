---
title: 'Lync Server 2013: tblComplianceData'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblComplianceData
ms:assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558606(v=OCS.15)
ms:contentKeyID: 48183308
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 044a57645a8c49ea74ec4e003f9e12720d0b2268
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848593"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblcompliancedata-in-lync-server-2013"></a>Lync Server 2013 の tblComplianceData

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-12_

tblComplianceData には、コンプライアンスアダプターでまだ処理されていないコンプライアンスイベントが含まれています。

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
<td><p>cmplEventID</p></td>
<td><p>bigint (null ではない)</p></td>
<td><p>イベント ID。</p></td>
</tr>
<tr class="even">
<td><p>entryDate</p></td>
<td><p>smalldatetime、null ではない</p></td>
<td><p>挿入の時刻 (その場合は、cmplType = 9 の場合は、その場合はプレースホルダーのみのエントリであるため)。</p></td>
</tr>
<tr class="odd">
<td><p>cmplType 種類</p></td>
<td><p>int (null ではない)</p></td>
<td><p>コンプライアンスイベントの種類:</p>
<ul>
<li><p>1: チャット</p></li>
<li><p>2: backchat</p></li>
<li><p>3: ファイルのダウンロード</p></li>
<li><p>4: ファイルのアップロード</p></li>
<li><p>9: 暫定ファイル送信</p></li>
<li><p>10: チャットの削除 (置換あり)</p></li>
<li><p>11: チャットの削除</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>cmplTime</p></td>
<td><p>bigint (null ではない)</p></td>
<td><p>イベントのタイムスタンプ。</p></td>
</tr>
<tr class="odd">
<td><p>cmplChannelUri</p></td>
<td><p>nvarchar (255)、null ではない</p></td>
<td><p>チャネルの Uniform Resource Identifier (URI)。</p></td>
</tr>
<tr class="even">
<td><p>cmplChatID</p></td>
<td><p>bigint</p></td>
<td><p>チャット ID (chatId テーブルに対応する tblChat)。</p></td>
</tr>
<tr class="odd">
<td><p>cmplUserID</p></td>
<td><p>int (null ではない)</p></td>
<td><p>ポスターのプリンシパル ID (tblPrincipal ID テーブルに対応)</p></td>
</tr>
<tr class="even">
<td><p>cmplUserUri</p></td>
<td><p>nvarchar (255)、null ではない</p></td>
<td><p>ユーザー URI。</p></td>
</tr>
<tr class="odd">
<td><p>cmplMessage</p></td>
<td><p>nvarchar (max)</p></td>
<td><p>メッセージ (エンコードは、cmplType 型によって異なります)。</p></td>
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
<td><p>cmplEventID</p></td>
<td><p>主キー。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

