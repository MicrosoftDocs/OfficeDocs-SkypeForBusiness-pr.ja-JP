---
title: 'Lync Server 2013: 別のアプリケーションから Lync を起動する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Starting Lync from another application
ms:assetid: 573b30b1-6590-4b24-8e96-a41be57cb0ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398376(v=OCS.15)
ms:contentKeyID: 48184184
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dafb8295d3070cd9f38e8691e654146978156d45
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764403"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="starting-lync-from-another-application"></a>別のアプリケーションから Lync を起動する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-20_

コマンドラインパラメーターを使用して、Lync 2013 のクイック起動を行うことができます。 たとえば、ユーザーが別のアプリケーションで電話番号をクリックした場合、アプリケーションは Lync 2013 のインスタンスを起動し、その番号への通話を開始することができます。

Lync 2013 では、連絡先名のセミコロンで区切られたリストを、マルチパーティ会議でも認識できます。

Lync 2013 が起動時に自動的にサインインするように構成されている場合は、コマンドラインパラメーターを使用して Lync 2013 を起動すると、Lync メインウィンドウが開きます。 Lync が起動時に自動的にサインインするように構成されていない場合は、サインインウィンドウが開きます。

次の表は、使用できるパラメーターを示しています。

### <a name="lync-2013-command-line-parameters"></a>Lync 2013 のコマンドラインパラメーター

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>補助</th>
<th>データの書式設定</th>
<th>アクション</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>tel</p></td>
<td><p>tel URI</p></td>
<td><p>音声通話の会話ウィンドウが開きますが、指定された番号をダイヤルしません。</p></td>
</tr>
<tr class="even">
<td><p>callto</p></td>
<td><p>tel:、sip:、または?</p></td>
<td><p>音声通話の会話ウィンドウが開きますが、指定された番号をダイヤルしません。</p></td>
</tr>
<tr class="odd">
<td><p>フェデレーション</p></td>
<td><p>SIP URI</p></td>
<td><p>参加者リストの指定した SIP uri (URL) を使用して、会話ウィンドウを開きます。</p></td>
</tr>
<tr class="even">
<td><p>Sip</p></td>
<td><p>SIP URI</p></td>
<td><p>Lync 2013 がトランスポート層セキュリティ (TLS) プロトコルを使用するように構成されている場合、sip: とまったく同じ機能が使われます。 TLS が使用されていない場合は、より高いレベルのセキュリティが必要であることをユーザーに知らせるダイアログボックスが表示されます。</p></td>
</tr>
<tr class="odd">
<td><p>会議</p></td>
<td><p>参加する会議の SIP URI</p></td>
<td><p>URI が self の場合は、フォーカスがインスタンス化され、一覧のみのビューが表示されます。 そうしないと、[名簿] ビューが表示されますが、招待状は送信されません。</p></td>
</tr>
<tr class="even">
<td><p>im</p></td>
<td><p>SIP URI</p></td>
<td><p>SIP URI でインスタントメッセージング (IM) 専用の会話ウィンドウを表示します。 区切り記号を付けずに、山かっこ&lt;&gt;() 内で指定された複数の SIP uri を受け入れます。</p>
<pre><code>im:&lt;sip:user1@host&gt;&lt;sip:user2@host&gt;</code></pre></td>
</tr>
</tbody>
</table>


次の表では、これらのコマンドラインパラメーターの例を示します。

### <a name="command-line-parameter-examples"></a>コマンドラインパラメーターの例

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Instance</th>
<th>より</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Tel: + 14255550101</p></td>
<td><p>+ 14255550101 で電話専用ビューを開きます。</p></td>
</tr>
<tr class="even">
<td><p>Callto: tel: + 14255550101</p></td>
<td><p>+ 14255550101 で電話専用ビューを開きます。</p></td>
</tr>
<tr class="odd">
<td><p>Callto:sip:kazuto@litwareinc.com</p></td>
<td><p>Kazuto@litwareinc.com で電話専用ビューを開きます。</p></td>
</tr>
<tr class="even">
<td><p>sip:kazuto@litwareinc.com</p></td>
<td><p>Kazuto@litwareinc.com を使用して、会話ウィンドウを開きます。</p></td>
</tr>
<tr class="odd">
<td><p>conf: sip:https://meet.contoso.com/kazuto/7322994</p></td>
<td><p>会話ウィンドウが開き、会議の音声参加オプションが表示されます。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

