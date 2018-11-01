---
title: 別のアプリケーションからの Lync の開始
TOCTitle: 別のアプリケーションからの Lync の開始
ms:assetid: 573b30b1-6590-4b24-8e96-a41be57cb0ef
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398376(v=OCS.15)
ms:contentKeyID: 52056610
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 別のアプリケーションからの Lync の開始

 

_**トピックの最終更新日:** 2015-03-09_

コマンドライン パラメーターを使用して、Lync 2013 をクイック起動できます。たとえば、ユーザーが別のアプリケーション上で電話番号をクリックした場合、アプリケーションは、Lync 2013 のインスタンスを開始し、その番号への通話を発信します。

また Lync 2013 では、複数参加者の会議の、セミコロンで区切られた連絡先の名前の一覧を識別できます。

Lync 2013 が起動時に自動的にサインインするように構成されている場合、コマンドライン パラメーターで Lync 2013 を開始すると、Lync メイン ウィンドウが開きます。Lync で起動時の自動的なサインインが構成されていない場合は、サインイン ウィンドウが開きます。

次の表に、使用可能なパラメーターを示します。

### Lync 2013 コマンドライン パラメーター

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>拡張</th>
<th>データ形式</th>
<th>操作</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>tel:</p></td>
<td><p>tel URI</p></td>
<td><p>音声通話用に [会話] ウィンドウを開きますが、指定の番号はダイヤルしません。</p></td>
</tr>
<tr class="even">
<td><p>callto:</p></td>
<td><p>tel:、sip:、または入力可能な tel URI</p></td>
<td><p>音声通話用に [会話] ウィンドウを開きますが、指定の番号はダイヤルしません。</p></td>
</tr>
<tr class="odd">
<td><p>sip:</p></td>
<td><p>SIP URI</p></td>
<td><p>参加者リストの指定の SIP 一意リソース識別子 (URI) で、[会話] ウィンドウを開きます。</p></td>
</tr>
<tr class="even">
<td><p>Sips:</p></td>
<td><p>SIP URI</p></td>
<td><p>Lync 2013 でトランスポート層セキュリティ (TLS) プロトコルの使用が構成されている場合は、sip: と同様に機能します。TLS が使用されていない場合は、より高いセキュリティ レベルが必要であることをユーザーに通知するダイアログ ボックスが表示されます。</p></td>
</tr>
<tr class="odd">
<td><p>conf:</p></td>
<td><p>参加する会議の SIP URI</p></td>
<td><p>自己の URI の場合は、フォーカスをインスタンス化して名簿のみを表示します。 名簿を表示しない場合は、INVITE を送信しないでください。</p>
<p></p></td>
</tr>
<tr class="even">
<td><p>im:</p></td>
<td><p>SIP URI</p></td>
<td><p>SIP URI でインスタント メッセージング (IM) のみの [会話] ウィンドウを表示します。山かっこ (&lt;&gt;) の中に指定されている、セパレーターなしの複数の SIP URI を受け入れます。</p>
<pre><code>im:&lt;sip:user1@host&gt;&lt;sip:user2@host&gt;</code></pre></td>
</tr>
</tbody>
</table>


次の表にこれらコマンドライン パラメーターの例を示します。

### コマンドライン パラメーターの例

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
<td><p>Tel:+14255550101</p></td>
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
<td><p>conf:sip:https://meet.contoso.com/kazuto/7322994</p></td>
<td><p>[会話] ウィンドウを開いて、会議オーディオ参加オプションを表示します。</p></td>
</tr>
</tbody>
</table>

