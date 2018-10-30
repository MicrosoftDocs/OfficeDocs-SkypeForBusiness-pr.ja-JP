---
title: 'Lync Server 2013: 診断レポート'
TOCTitle: 診断レポート
ms:assetid: b389dbd9-f2e8-4184-93d0-2e504796ac16
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg615445(v=OCS.15)
ms:contentKeyID: 48273315
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の診断レポート

 

_**トピックの最終更新日:** 2016-12-08_

診断レポートは、エラーが発生したセッションに対する診断とトラブルシューティングに関する情報を提供します。この情報には、セッションにエラーが発生したときにレポートされた診断 ID と診断ヘッダーの両方が含まれます。診断 ID は、SIP メッセージに添付される一意の識別子 (ms-diagnostics ヘッダーの形式) であり、診断ヘッダーでは診断 ID に付属する説明が提供されます。また、レポートには、レポート コンポーネントによって判明した、次の例のような役立つトラブルシューティングの詳細も含まれることがあります。

  - エラーを生成した PSTN ゲートウェイによって提供された原因コード。発信通話が PSTN ネットワークで失敗すると、ISDN User Part (ISUP) の原因コードが自動的に生成されます。たとえば、PSTN ゲートウェイは原因コード 34 を送信して、通話を完了するための使用可能な回線またはチャネルが存在しないことを示す場合があります。

  - 接続エラーのピアの FQDN、ポート、および Winsock エラー。

  - DNS 解決エラーで検索されている名前。DNS 解決は、クライアントがネーム サーバーに問い合わせ、指定されたデバイス名に対応する IP アドレスを要求するときにいつでも実行されます。

## 診断レポートへのアクセス

診断レポートには、 [Lync Server 2013 ピアツーピア セッション詳細レポート](lync-server-2013-peer-to-peer-session-detail-report.md)または会議詳細レポートで \[診断レポート (詳細)\] 指標をクリックするとアクセスできます。

## フィルター

なし。診断レポートにフィルターを適用することはできません。

## 指標

次の表に、診断レポートで提供されるセッションごとの情報を示します。

### 診断レポートの指標

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
<td><p><strong>レポート時刻</strong></p></td>
<td><p>×</p></td>
<td><p>レポートが記録された日時。</p></td>
</tr>
<tr class="even">
<td><p><strong>応答コード</strong></p></td>
<td><p>×</p></td>
<td><p>セッションが失敗したときに送信された SIP 応答コード。</p></td>
</tr>
<tr class="odd">
<td><p><strong>要求の種類</strong></p></td>
<td><p>×</p></td>
<td><p>失敗した SIP 要求の種類 (INVITE、BYE、SERVICE など)。</p></td>
</tr>
<tr class="even">
<td><p><strong>ソース</strong></p></td>
<td><p>×</p></td>
<td><p>エラーのソース。</p></td>
</tr>
<tr class="odd">
<td><p><strong>送信元ユーザー URI</strong></p></td>
<td><p>×</p></td>
<td><p>セッションを開始したユーザーの SIP アドレス。</p></td>
</tr>
<tr class="even">
<td><p><strong>送信元ユーザー エージェント</strong></p></td>
<td><p>×</p></td>
<td><p>セッションを開始したユーザーのエンドポイントで使用されているソフトウェア。</p></td>
</tr>
<tr class="odd">
<td><p><strong>診断 ID</strong></p></td>
<td><p>×</p></td>
<td><p>SIP メッセージに (ms-diagnostics ヘッダーの形で) 添付された一意の識別子。多くの場合、この情報はトラブルシューティングに役立ちます。</p></td>
</tr>
<tr class="even">
<td><p><strong>コンテンツの種類</strong></p></td>
<td><p>×</p></td>
<td><p>失敗したメディア コンテンツの種類。たとえば、よく使われるコンテンツの種類は Application/sdp です。セッション記述プロトコル (SDP) は、セッションのアナウンス、セッションの招待、その他のマルチメディア セッション開始形式で使われる標準インターネット プロトコルです。</p></td>
</tr>
<tr class="odd">
<td><p><strong>アプリケーション</strong></p></td>
<td><p>×</p></td>
<td><p>エラーに関係するアプリケーション。</p></td>
</tr>
<tr class="even">
<td><p><strong>送信先ユーザー URI</strong></p></td>
<td><p>×</p></td>
<td><p>セッションに招待されたユーザーの SIP アドレス。</p></td>
</tr>
<tr class="odd">
<td><p>会議参加時間 (ミリ秒)</p></td>
<td><p>×</p></td>
<td><p>ユーザーが会議に参加するのにかかった時間 (ミリ秒)。</p></td>
</tr>
<tr class="even">
<td><p><strong>診断ヘッダー</strong></p></td>
<td><p>×</p></td>
<td><p>診断 ID の説明。</p></td>
</tr>
</tbody>
</table>


診断エラーのリストは、「 [MS 診断エラー(Ms-Diagnostics Header page)](http://msdn.microsoft.com/en-us/library/gg132446\(v=office.12\).aspx)」をご覧ください。

