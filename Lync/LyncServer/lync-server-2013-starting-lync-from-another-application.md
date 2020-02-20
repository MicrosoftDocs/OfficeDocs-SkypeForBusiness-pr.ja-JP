---
title: 'Lync Server 2013: 別のアプリケーションからの Lync の起動'
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
ms.openlocfilehash: 75e7a48645301b6c822eed52ea31e6d4b46019bd
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142513"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="starting-lync-from-another-application"></a>別のアプリケーションからの Lync の起動

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-20_

コマンドラインパラメーターを使用して、Lync 2013 をクイックスタートすることができます。 たとえば、ユーザーが別のアプリケーションで電話番号をクリックすると、アプリケーションは Lync 2013 のインスタンスを開始し、その番号への呼び出しを開始することができます。

Lync 2013 は、マルチパーティ会議の連絡先名のセミコロンで区切られたリストを認識することもできます。

Lync 2013 が開始時に自動的にサインインするように構成されている場合、lync 2013 をコマンドラインパラメーター付きで開始すると、Lync のメインウィンドウが開きます。 Lync で起動時の自動的なサインインが構成されていない場合は、サインイン ウィンドウが開きます。

次の表に、使用可能なパラメーターを示します。

### <a name="lync-2013-command-line-parameters"></a>Lync 2013 コマンドラインパラメーター

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>拡張子</th>
<th>データ形式</th>
<th>Action</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>電話</p></td>
<td><p>tel URI</p></td>
<td><p>音声通話用に [会話] ウィンドウを開きますが、指定の番号はダイヤルしません。</p></td>
</tr>
<tr class="even">
<td><p>callto</p></td>
<td><p>tel:、sip:、または入力可能な tel URI</p></td>
<td><p>音声通話用に [会話] ウィンドウを開きますが、指定の番号はダイヤルしません。</p></td>
</tr>
<tr class="odd">
<td><p>sip</p></td>
<td><p>SIP URI</p></td>
<td><p>参加者リストの指定の SIP 一意リソース識別子 (URI) で、[会話] ウィンドウを開きます。</p></td>
</tr>
<tr class="even">
<td><p>Sips</p></td>
<td><p>SIP URI</p></td>
<td><p>Lync 2013 がトランスポート層セキュリティ (TLS) プロトコルを使用するように構成されている場合は、sip: とまったく同じように機能します。 TLS が使用されていない場合は、より高いセキュリティ レベルが必要であることをユーザーに通知するダイアログ ボックスが表示されます。</p></td>
</tr>
<tr class="odd">
<td><p>conf</p></td>
<td><p>参加する会議の SIP URI</p></td>
<td><p>自己の URI の場合は、フォーカスをインスタンス化して名簿のみを表示します。 名簿を表示しない場合は、INVITE を送信しないでください。</p></td>
</tr>
<tr class="even">
<td><p>メッセージング</p></td>
<td><p>SIP URI</p></td>
<td><p>SIP URI でインスタント メッセージング (IM) のみの [会話] ウィンドウを表示します。 山かっこ (&lt;&gt;) 内で指定した複数の SIP uri を区切り記号なしで受け入れます。</p>
<pre><code>im:&lt;sip:user1@host&gt;&lt;sip:user2@host&gt;</code></pre></td>
</tr>
</tbody>
</table>


次の表にこれらコマンドライン パラメーターの例を示します。

### <a name="command-line-parameter-examples"></a>コマンドライン パラメーターの例

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>インスタンス</th>
<th>結果</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Tel: + 14255550101</p></td>
<td><p>+14255550101 の電話のみの表示を開きます。</p></td>
</tr>
<tr class="even">
<td><p>Callto:tel:+ 14255550101</p></td>
<td><p>+14255550101 の電話のみの表示を開きます。</p></td>
</tr>
<tr class="odd">
<td><p>Callto:sip:kazuto@litwareinc.com</p></td>
<td><p>kazuto@litwareinc.com との電話のみの表示を開きます。</p></td>
</tr>
<tr class="even">
<td><p>sip:kazuto@litwareinc.com</p></td>
<td><p>kazuto@litwareinc.com との [会話] ウィンドウを開きます。</p></td>
</tr>
<tr class="odd">
<td><p>conf: sip:https://meet.contoso.com/kazuto/7322994</p></td>
<td><p>会話ウィンドウが開き、会議のオーディオ参加オプションが表示されます。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

