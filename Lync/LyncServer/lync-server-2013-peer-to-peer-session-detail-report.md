---
title: 'Lync Server 2013: ピアツーピア セッション詳細レポート'
TOCTitle: ピアツーピア セッション詳細レポート
ms:assetid: 6be1d676-68f7-4a53-a72a-de73296c5571
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg558659(v=OCS.15)
ms:contentKeyID: 48272418
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 ピアツーピア セッション詳細レポート

 

_**トピックの最終更新日:** 2015-03-09_

ピアツーピア セッション詳細レポートは、ピアツーピア セッションに関する詳細情報を提供します。たとえば、インスタント メッセージング セッションを選択すると、セッション中に 2 人のユーザーのそれぞれが送信したメッセージ数がレポートに表示されます。

## ピアツーピア セッション詳細レポートへのアクセス

ピアツーピア セッション詳細レポートには、次のいずれかのレポートからアクセスできます (これらのレポートはすべて、監視レポートのホーム ページからアクセスできます)。

  - IP 電話インベントリ レポート

  - ユーザー アクティビティ レポート

  - 通話受付管理レポート

  - エラー リスト レポート

ピアツーピア セッション詳細レポートから、診断レポート (詳細) の指標をクリックして [Lync Server 2013 の診断レポート](lync-server-2013-diagnostic-report.md)にアクセスできます。次のいずれかの指標をクリックしてトップ エラー レポートにアクセスすることもできます。

  - 応答

  - 診断 ID

## ピアツーピア セッション詳細レポートの有効活用

ピアツーピア セッション詳細レポートには数多くの指標が含まれています。システム管理者にとって馴染みのないものも多いかもしれませんが、通常は、指標のラベルにマウス ポインターを置くと簡単な説明を示したヒントが表示されます。

レポートに表示される実際の指標は、選択したピアツーピア セッションの種類によって決まります。音声ビデオ セッションのレポートに表示される指標は、インスタント メッセージング セッションの指標とは異なります。

また、応答コードおよび診断 ID の指標にマウス ポインターを置くと、その値の説明が表示されます。

## フィルター

なし。ピアツーピア セッション詳細レポートはフィルターできません。

## セッション情報の指標

次の表に、ピアツーピア セッション詳細レポートでセッションごとに提供される情報を示します。

### セッション情報の指標

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>名前</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>[ <strong>プールの FQDN</strong> ]</p></td>
<td><p>セッションに関与したレジストラー プールまたはエッジ サーバーの完全修飾ドメイン名 (FQDN) です。</p></td>
</tr>
<tr class="even">
<td><p>[ <strong>招待時間</strong> ]</p></td>
<td><p>セッションへの招待が最初に送信された日時です。</p></td>
</tr>
<tr class="odd">
<td><p>[ <strong>応答時間</strong> ]</p></td>
<td><p>招待の承諾を受信した日時。</p></td>
</tr>
<tr class="even">
<td><p>[ <strong>移動元ユーザー</strong> ]</p></td>
<td><p>セッションを開始したユーザーの SIP アドレス。</p></td>
</tr>
<tr class="odd">
<td><p><strong>送信元ユーザー エージェント</strong></p></td>
<td><p>セッションを開始したユーザーのエンドポイントで使用されているソフトウェア。</p></td>
</tr>
<tr class="even">
<td><p>[ <strong>内部の送信元ユーザー</strong> ]</p></td>
<td><p>セッションを開始したユーザーが内部ネットワークにログオンしていたかどうかを示します。</p></td>
</tr>
<tr class="odd">
<td><p>[ <strong>電話と統合された送信元ユーザー</strong> ]</p></td>
<td><p>セッションを開始したユーザーの使用するエンドポイントがそのユーザーのデスクトップ電話と統合されているかどうかを示します。</p></td>
</tr>
<tr class="even">
<td><p>[ <strong>セッションの優先順位</strong> ]</p></td>
<td><p>セッションに割り当てられた優先順位。有効な優先順位として、不明、非緊急、標準、至急、および緊急があります。</p></td>
</tr>
<tr class="odd">
<td><p><strong>応答コード</strong></p></td>
<td><p>セッションが失敗したときに送信された SIP 応答コード。</p></td>
</tr>
<tr class="even">
<td><p>[ <strong>フロントエンド</strong> ]</p></td>
<td><p>電話会議で使用されたフロントエンド サーバーの名前です。</p></td>
</tr>
<tr class="odd">
<td><p>[ <strong>キャプチャ時刻</strong> ]</p></td>
<td><p>セッションの情報が記録された日時です。</p></td>
</tr>
<tr class="even">
<td><p>[ <strong>終了時刻</strong> ]</p></td>
<td><p>セッションが終了した日時です。</p></td>
</tr>
<tr class="odd">
<td><p>[ <strong>対象ユーザー</strong> ]</p></td>
<td><p>セッションに招待されたユーザーの SIP アドレス。</p></td>
</tr>
<tr class="even">
<td><p>[ <strong>送信先ユーザー エージェント</strong> ]</p></td>
<td><p>セッションに招待されたユーザーのエンドポイントで使用されているソフトウェアです。</p></td>
</tr>
<tr class="odd">
<td><p>[ <strong>内部の送信先ユーザー</strong> ]</p></td>
<td><p>セッションに招待されたユーザーが内部ネットワークにログオンしていたかどうかを示します。</p></td>
</tr>
<tr class="even">
<td><p>[ <strong>電話と統合された送信先ユーザー</strong> ]</p></td>
<td><p>セッションに招待されたユーザーの使用するエンドポイントがそのユーザーのデスクトップ電話と統合されているかどうかを示します。</p></td>
</tr>
<tr class="odd">
<td><p>[ <strong>再試行セッション</strong> ]</p></td>
<td><p>以前エラーが発生したセッションを再試行するためのセッションかどうかを示します。</p></td>
</tr>
<tr class="even">
<td><p><strong>診断 ID</strong></p></td>
<td><p>エラーのトラブルシューティングに役立つ情報を得られることが多い、SIP メッセージに添付された一意の識別子です (ms-diagnostics ヘッダーの形式)。マウス ポインターを ID 番号の上に置くと、その ID に関する追加情報が表示されます。</p></td>
</tr>
</tbody>
</table>


## モダリティの指標

次の表に、ピアツーピア セッション詳細レポートでセッションのモダリティごとに提供される情報を示します。

### モダリティの指標

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
<td><p>[ <strong>モダリティ</strong> ]</p></td>
<td><p>×</p></td>
<td><p>セッションで使用されるモダリティ。インスタント メッセージング (IM)、ファイル送信など。</p></td>
</tr>
<tr class="even">
<td><p>[ <strong>送信元ユーザー メッセージ</strong> ]</p></td>
<td><p>×</p></td>
<td><p>セッションを開始したユーザーが送信したメッセージの数です。</p></td>
</tr>
<tr class="odd">
<td><p>[ <strong>送信先ユーザー メッセージ</strong> ]</p></td>
<td><p>×</p></td>
<td><p>セッションに招待されたユーザーが送信したメッセージの数です。</p></td>
</tr>
</tbody>
</table>


## 診断レポートの指標

次の表に、ピアツーピア セッション詳細レポートで診断レポートごとに提供される情報を示します。

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
<td><p>[ <strong>詳細</strong> ]</p></td>
<td><p>×</p></td>
<td><p>この項目をクリックすると、セッションの診断レポートが表示されます。</p></td>
</tr>
<tr class="even">
<td><p><strong>レポート時刻</strong></p></td>
<td><p>×</p></td>
<td><p>レポートが記録された日時です。</p></td>
</tr>
<tr class="odd">
<td><p><strong>要求</strong></p></td>
<td><p>×</p></td>
<td><p>SIP 要求の種類。INVITE、BYE など。</p></td>
</tr>
<tr class="even">
<td><p><strong>診断 ID</strong></p></td>
<td><p>×</p></td>
<td><p>SIP メッセージに (ms-diagnostics ヘッダーの形で) 添付された一意の識別子。多くの場合、この情報はトラブルシューティングに役立ちます。</p></td>
</tr>
<tr class="odd">
<td><p><strong>コンテンツの種類</strong></p></td>
<td><p>×</p></td>
<td><p>会議で使用されたメディア コンテンツの種類。たとえば、一般的なコンテンツの種類は &quot;アプリケーション/sdp&quot; です。セッション記述プロトコル (SDP) は、セッションのアナウンス、セッションへの招待、およびその他の形のマルチメディア セッションの開始で使用される標準的なインターネット プロトコルです。</p></td>
</tr>
<tr class="even">
<td><p>[ <strong>レポート作成者</strong> ]</p></td>
<td><p>×</p></td>
<td><p>問題を報告したコンピューター (クライアントまたはサーバー) です。</p></td>
</tr>
</tbody>
</table>

