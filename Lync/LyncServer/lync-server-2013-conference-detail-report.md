---
title: 会議詳細レポート
TOCTitle: 会議詳細レポート
ms:assetid: 1d61cd81-dcfe-40b4-9a41-a73b038bc216
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ204728(v=OCS.15)
ms:contentKeyID: 48271446
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 会議詳細レポート

 

_**トピックの最終更新日:** 2015-03-09_

会議詳細レポートには、電話会議に参加したすべてのユーザーに関する詳細な情報が示されます。たとえば、ユーザーが会議に参加した日時、ユーザーが電話会議から退場した日時、ユーザーが電話会議に接続するときに使用したエンドポイントのユーザー エージェントなどの情報を確認できます。各電話会議におけるユーザーの役割 (発表者、参加者など) に関する情報も確認できます。おそらく最も重要なことは、会議への参加と終了が正常に行われたユーザーと正常に行われなかったユーザーを簡単に確認できることです。

## 会議詳細レポートへのアクセス

会議詳細レポートには、次のレポートからアクセスできます。

  - [Lync Server 2013 の通話受付管理レポート](lync-server-2013-call-admission-control-report.md) (会議の詳細指標をクリック)

  - [Lync Server 2013 のエラー リスト レポート](lync-server-2013-failure-list-report.md) (電話会議指標をクリック)

  - [Lync Server 2013 のユーザー アクティビティ レポート](lync-server-2013-user-activity-report.md) (電話会議 URI 指標をクリック)

会議詳細レポートからは、診断レポート (詳細) 指標をクリックして[Lync Server 2013 の診断レポート](lync-server-2013-diagnostic-report.md)にアクセスできます。

## フィルター

なし。会議詳細レポートにはフィルターを適用できません。

## 指標

次の表は、会議詳細レポートの \[電話会議情報\] セクションに提供される情報を示しています。

### 電話会議情報の指標

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>名前</th>
<th>この項目での並べ替え</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>[<strong>電話会議 URI</strong>]</p></td>
<td><p></p></td>
<td><p>電話会議に割り当てられる URI。次に例を示します。</p>
<p>sip:kmyer@litwareinc.com;gruu;opaque=app:conf:focus:id:drg2y8v4</p></td>
</tr>
<tr class="even">
<td><p>[<strong>プールの FQDN</strong>]</p></td>
<td><p></p></td>
<td><p>セッションに関係するレジストラー プールまたはエッジ サーバーの完全修飾名。</p></td>
</tr>
<tr class="odd">
<td><p>[<strong>開始時刻</strong>]</p></td>
<td><p></p></td>
<td><p>会議が開始した日時。</p></td>
</tr>
<tr class="even">
<td><p>[<strong>開催者</strong>]</p></td>
<td><p></p></td>
<td><p>会議を開催したユーザーの SIP アドレス。</p></td>
</tr>
<tr class="odd">
<td><p>[<strong>終了時刻</strong>]</p></td>
<td><p></p></td>
<td><p>会議が終了した日時。</p></td>
</tr>
</tbody>
</table>


次の表は、会議詳細レポートの \[電話会議の参加\] セクションに提供される情報を示しています。

### 電話会議参加の指標

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>名前</th>
<th>この項目での並べ替え</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>[<strong>ユーザー</strong>]</p></td>
<td><p></p></td>
<td><p>会議に参加したユーザーの SIP アドレス。</p></td>
</tr>
<tr class="even">
<td><p>[<strong>役割</strong>]</p></td>
<td><p></p></td>
<td><p>電話会議の参加者が担った役割 (発表者など)。</p></td>
</tr>
<tr class="odd">
<td><p>[<strong>接続</strong>]</p></td>
<td><p></p></td>
<td><p>参加者のネットワーク接続 (一般には内部送信元または外部送信元)。</p></td>
</tr>
<tr class="even">
<td><p>[参加時間]</p></td>
<td><p></p></td>
<td><p>参加者が電話会議に参加した日時。</p></td>
</tr>
<tr class="odd">
<td><p>[<strong>退場時間</strong>]</p></td>
<td><p></p></td>
<td><p>参加者が電話会議から退出した日時。</p></td>
</tr>
<tr class="even">
<td><p>[<strong>ユーザー エージェント</strong>]</p></td>
<td><p></p></td>
<td><p>参観者のエンドポイントで使用されるソフトウェアの識別子。</p></td>
</tr>
<tr class="odd">
<td><p>[<strong>診断レポート</strong>]</p></td>
<td><p></p></td>
<td><p>診断およびトラブルシューティングの情報を提供します。失敗したセッションの SIP 応答コード、診断ヘッダー、電話会議参加時間、診断 ID などがあります。</p></td>
</tr>
</tbody>
</table>


次の表は、会議詳細レポートの \[電話会議のモダリティ\] セクションに提供される情報を示しています。

### 電話会議のモダリティの指標

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>名前</th>
<th>この項目での並べ替え</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>[<strong>ユーザー</strong>]</p></td>
<td><p></p></td>
<td><p>会議に参加したユーザーの SIP アドレス。</p></td>
</tr>
<tr class="even">
<td><p>[<strong>参加時間</strong>]</p></td>
<td><p></p></td>
<td><p>参加者が電話会議に参加した日時。</p></td>
</tr>
<tr class="odd">
<td><p>[<strong>退場時間</strong>]</p></td>
<td><p></p></td>
<td><p>参加者が電話会議を退場した日時。</p></td>
</tr>
<tr class="even">
<td><p>[<strong>電話会議サーバー URI</strong>]</p></td>
<td><p></p></td>
<td><p>電話会議で使用された電話会議サーバーの URI。</p></td>
</tr>
<tr class="odd">
<td><p><strong>診断レポート</strong></p></td>
<td><p></p></td>
<td><p>診断およびトラブルシューティングの情報を提供します。失敗したセッションの SIP 応答コード、診断ヘッダー、電話会議参加時間、診断 ID などがあります。</p></td>
</tr>
</tbody>
</table>

