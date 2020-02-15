---
title: 'Lync Server 2013: tblComplianceData'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblComplianceData
ms:assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558606(v=OCS.15)
ms:contentKeyID: 48183308
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03f5a65b11c610849c5b9d031f24d236dcbcf332
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048508"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblcompliancedata-in-lync-server-2013"></a>Lync Server 2013 の tblComplianceData

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-12_

tblComplianceData には、コンプライアンス アダプターによってまだ処理されていないコンプライアンス イベントが格納されます。

### <a name="columns"></a>Columns

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>列</th>
<th>種類</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Tblcompliancedata.cmpleventid</p></td>
<td><p>NULL でない bigint</p></td>
<td><p>イベント ID。</p></td>
</tr>
<tr class="even">
<td><p>entryDate</p></td>
<td><p>NULL でない smalldatetime</p></td>
<td><p>挿入の日時 (cmplType=9 の場合は、エントリが単なるプレースホルダーなので、遠い将来になる可能性があります)。</p></td>
</tr>
<tr class="odd">
<td><p>cmplType</p></td>
<td><p>NULL でない int</p></td>
<td><p>コンプライアンス イベントの種類。</p>
<ul>
<li><p>1: チャット</p></li>
<li><p>2: バックチャット</p></li>
<li><p>3: ファイル ダウンロード</p></li>
<li><p>4: ファイル アップロード</p></li>
<li><p>9: 暫定ファイル転送</p></li>
<li><p>10: (置き換えによる) チャットの削除</p></li>
<li><p>11: チャットの削除</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>cmplTime</p></td>
<td><p>NULL でない bigint</p></td>
<td><p>イベントのタイムスタンプ。</p></td>
</tr>
<tr class="odd">
<td><p>cmplChannelUri</p></td>
<td><p>NULL でない nvarchar (255)</p></td>
<td><p>チャネルの URI (Uniform Resource Identifier)。</p></td>
</tr>
<tr class="even">
<td><p>cmplChatID</p></td>
<td><p>bigint</p></td>
<td><p>チャット ID (tblChat.chatId テーブルに対応)。</p></td>
</tr>
<tr class="odd">
<td><p>cmplUserID</p></td>
<td><p>NULL でない int</p></td>
<td><p>ポスターのプリンシパル ID (tblPrincipal.prinID テーブルに対応)。</p></td>
</tr>
<tr class="even">
<td><p>cmplUserUri</p></td>
<td><p>NULL でない nvarchar (255)</p></td>
<td><p>ユーザーの URI。</p></td>
</tr>
<tr class="odd">
<td><p>cmplMessage</p></td>
<td><p>nvarchar (max)</p></td>
<td><p>メッセージ (エンコードは cmplType に依存)。</p></td>
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
<td><p>Tblcompliancedata.cmpleventid</p></td>
<td><p>主キー。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

