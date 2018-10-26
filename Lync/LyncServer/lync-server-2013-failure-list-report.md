---
title: 'Lync Server 2013: エラー リスト レポート'
TOCTitle: エラー リスト レポート
ms:assetid: b6f3a605-e0c6-461e-b17a-41d8039ace9d
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg615446(v=OCS.15)
ms:contentKeyID: 48273337
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 のエラー リスト レポート

 

_**トピックの最終更新日:** 2015-03-09_

エラー リスト レポートは、エラーが発生したピアツーピア セッションまたは電話会議セッションに参加した個々の参加者に関する情報を提供します。この情報には、問題が発生したユーザーの URI、エラーに関連付けられている SIP 応答コードおよび診断 ID が含まれています。

## エラー リスト レポートへのアクセス

エラー リスト レポートには、 [Lync Server 2013 のエラー分布レポート](lync-server-2013-failure-distribution-report.md)の次のいずれかの指標をクリックすることによってアクセスします。

  - トップの診断理由 (セッション)

  - トップ モダリティ (セッション)

  - トップ プール (セッション)

  - トップ ソース (セッション)

  - トップ コンポーネント (セッション)

  - トップの発信元ユーザー (セッション)

  - トップの発信先ユーザー (セッション)

  - トップの発信元ユーザー エージェント (セッション)

エラー リスト レポートでピアツーピア セッションのセッション詳細の指標をクリックすると、 [Lync Server 2013 ピアツーピア セッション詳細レポート](lync-server-2013-peer-to-peer-session-detail-report.md)にアクセスできます。また、電話会議の電話会議の指標をクリックすると、会議詳細レポートにもアクセスできます。

## エラー リスト レポートの活用

エラー リスト レポートでは、マウス ポインターを値の上に置くだけで、それぞれの応答コードまたは診断 ID の説明を表示することができます。たとえば、診断 ID 7025 の上にマウス ポインターを置くと、次のような説明がツールチップに表示されます。

ユーザーのメディアの作成中に内部サーバー エラーが発生しました。

エラー リスト レポートはエラーが発生した 1 つ以上のセッションに参加したすべてのユーザーの一覧を直接取得する直接的な方法を提供せず、エラーが発生したセッションに最も頻繁に参加したユーザーを特定する方法も提供しないことに注意してください (一例を挙げると、エラー リスト レポートにはフィルター処理機能がありません)。ただし、データをエクスポートしてからコンマ区切り値ファイルに変換すると、Windows PowerShell を使用してこのような質問に対する回答を見つけることができます。たとえば、C:\\Data\\Failure\_List.csv という名前の .CSV ファイルにデータを保存するとします。次のコマンドは、このファイルに保存されたデータに基づいて、エラーが発生した 1 つ以上のセッションに参加したすべてのユーザーの一覧を表示します。

    $failures = Import-Csv -Path " C:\Data\Failure_List.csv"
    $failure |Sort-Object "From user" | Select-Object "From user" -Unique

このコマンドにより、次にような一覧が返されます。

    From user
    ----
    Pilar.Ackerman@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    David.Ahs@litwareinc.com
    Ken.Myer@litwareinc.com

次の 2 つのコマンドは、各ユーザーが参加した、エラーが発生したセッションの総数についてレポートします。

    $failures = Import-Csv -Path "C:\Data\Failure_List.csv"
    $failures | Group-Object "From user" | Select-Object Count, Name | Sort-Object -Property Count -Descending

これにより、次のようなデータが返されます。

    Count    Name
     -----    ----
        20    Pilar.Ackerman@litwareinc.com
        20    David.Ahs@litwareinc.com
        16    Gilead.Amosnino@litwareinc.com
        16    Ken.Myero@litwareinc.com
        14    Henrik.Jensen@litwareinc.com

## フィルター

なし。エラー リスト レポートはフィルターできません。

## 指標

次の表に、失敗した呼び出しごとにエラー リスト レポートで提供される情報を示します。

### エラー リスト レポートの指標

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
<td><p><strong>レポートされた時刻</strong></p></td>
<td><p>×</p></td>
<td><p>レポートが記録された日時です。</p></td>
</tr>
<tr class="even">
<td><p><strong>要求</strong></p></td>
<td><p>×</p></td>
<td><p>失敗した SIP 要求の種類です (INVITE、BYE など)。</p></td>
</tr>
<tr class="odd">
<td><p><strong>応答コード</strong></p></td>
<td><p>×</p></td>
<td><p>会議にエラーが発生したときに送信された SIP 応答コードです。</p></td>
</tr>
<tr class="even">
<td><p><strong>診断 ID</strong></p></td>
<td><p>×</p></td>
<td><p>SIP メッセージに (ms-diagnostics ヘッダーの形で) 添付された一意の識別子。多くの場合、この情報はトラブルシューティングに役立ちます。</p></td>
</tr>
<tr class="odd">
<td><p>[ <strong>Join cost time (ms)</strong> ] (参加に要した時間 (ミリ秒))</p></td>
<td><p>×</p></td>
<td><p>ユーザーが会議に参加するのに要した時間 (ミリ秒)。</p></td>
</tr>
<tr class="even">
<td><p>[ <strong>移動元ユーザー</strong> ]</p></td>
<td><p>×</p></td>
<td><p>呼び出しを開始したユーザーの SIP アドレス。</p></td>
</tr>
<tr class="odd">
<td><p><strong>送信元ユーザー エージェント</strong></p></td>
<td><p>×</p></td>
<td><p>呼び出しを開始したユーザーのエンドポイントで使用されているソフトウェアです。</p></td>
</tr>
<tr class="even">
<td><p>[ <strong>対象ユーザー</strong> ]</p></td>
<td><p>×</p></td>
<td><p>呼び出しを受けたユーザーの SIP アドレスです。</p></td>
</tr>
</tbody>
</table>

