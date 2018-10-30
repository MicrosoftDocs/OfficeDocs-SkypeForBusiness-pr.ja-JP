---
title: UCWA イベント
TOCTitle: UCWA イベント
ms:assetid: 26cb409d-f4e4-43c7-873f-b694702d491d
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ945621(v=OCS.15)
ms:contentKeyID: 52056557
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# UCWA イベント

 

_**トピックの最終更新日:** 2015-03-09_

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Lync Server 2013 は、Microsoft Exchange にアクセスして連絡先を検索することから、モバイル クライアントのプレゼンスを更新することまで、さまざまな目的で統合コミュニケーション Web API を使用します。

UCWA は、実行動作の記録を、"情報"、"警告"、および "エラー" のイベントの種類として書き込みます。次の表に、UCWA コンポーネントによって書き込まれる可能性があるイベントを示します。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>イベント ID</th>
<th>イベントの種類</th>
<th>要約</th>
<th>原因および解決策</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>20001</p></td>
<td><p>情報</p></td>
<td><p>UCWA が初期化されました</p></td>
<td><p>該当なし</p>
<p>該当なし</p></td>
</tr>
<tr class="even">
<td><p>20002</p></td>
<td><p>エラー</p></td>
<td><p>初期化中に UCWA で予期しない例外が発生しました</p></td>
<td><p>初期化中に予期しないエラーが発生しました</p>
<p>関連付けられたイベント ログ エントリで例外の詳細を調査し、可能性のある原因を特定します</p></td>
</tr>
<tr class="odd">
<td><p>20003</p></td>
<td><p>エラー</p></td>
<td><p>UCWA で処理不能な例外が発生しました</p></td>
<td><p>処理不能な例外が発生しました</p>
<p>サーバーを再起動します。問題が解決しない場合は、製品サポートに問い合わせてください。</p></td>
</tr>
<tr class="even">
<td><p>20004</p></td>
<td><p>エラー</p></td>
<td><p>Exchange の HD 写真にアクセスできません</p></td>
<td><p>Exchange への接続を利用できません</p>
<p>Exchange への接続が利用できることを確認します</p></td>
</tr>
<tr class="odd">
<td><p>20005</p></td>
<td><p>情報</p></td>
<td><p>Exchange の HD 写真にアクセスできないエラーから復旧しました</p></td>
<td><p>該当なし</p></td>
</tr>
<tr class="even">
<td><p>20006</p></td>
<td><p>エラー</p></td>
<td><p>Exchange の連絡先検索にアクセスできません</p></td>
<td><p>Exchange への接続を利用できません</p>
<p>Exchange への接続が利用できることを確認します</p></td>
</tr>
<tr class="odd">
<td><p>20007</p></td>
<td><p>情報</p></td>
<td><p>Exchange の連絡先を検索できないエラーから復旧しました</p></td>
<td><p>該当なし</p></td>
</tr>
<tr class="even">
<td><p>20008</p></td>
<td><p>警告</p></td>
<td><p>アプリケーションごとの許容数を超えるプレゼンス サブスクリプションの登録が試みられました</p></td>
<td><p>アプリケーションごとの許容数を超えるプレゼンス サブスクリプションの登録が試みられました</p>
<p>クライアントに不要なサブスクリプションがないかどうかを確認します</p></td>
</tr>
<tr class="odd">
<td><p>20009</p></td>
<td><p>警告</p></td>
<td><p>バッチごとの許容数を超えるプレゼンス サブスクリプションの登録が試みられました</p></td>
<td><p>バッチごとの許容数を超えるプレゼンス サブスクリプションの登録が試みられました</p>
<p>クライアントに不要なサブスクリプションがないかどうかを確認します</p></td>
</tr>
<tr class="even">
<td><p>20010</p></td>
<td><p>エラー</p></td>
<td><p>インバンド データを取得できません</p></td>
<td><p>インバンド データを取得できません</p>
<p>問題が解決しない場合は、製品サポートに問い合わせてください。</p></td>
</tr>
<tr class="odd">
<td><p>20011</p></td>
<td><p>エラー</p></td>
<td><p>プレゼンスを登録できません</p></td>
<td><p>プレゼンスを登録できません</p>
<p>問題が解決しない場合は、製品サポートに問い合わせてください。</p></td>
</tr>
<tr class="even">
<td><p>20012</p></td>
<td><p>エラー</p></td>
<td><p>エンドポイントの登録に失敗しました</p></td>
<td><p>エンドポイントの登録に失敗しました</p>
<p>問題が解決しない場合は、製品サポートに問い合わせてください。</p></td>
</tr>
<tr class="odd">
<td><p>20013</p></td>
<td><p>エラー</p></td>
<td><p>IM MCU を利用できません</p></td>
<td><p>IM MCU を利用できません</p>
<p>IM MCU が実行されているかどうかを確認します</p></td>
</tr>
<tr class="even">
<td><p>20014</p></td>
<td><p>情報</p></td>
<td><p>IM MCU に接続できないエラーから復旧しました</p></td>
<td><p>該当なし</p></td>
</tr>
<tr class="odd">
<td><p>20015</p></td>
<td><p>エラー</p></td>
<td><p>AV MCU を利用できません</p></td>
<td><p>AV MCU を利用できません</p>
<p>AV MCU が実行されているかどうかを確認します</p></td>
</tr>
<tr class="even">
<td><p>20016</p></td>
<td><p>情報</p></td>
<td><p>AV MCU に接続できないエラーから復旧しました</p></td>
<td><p>該当なし</p></td>
</tr>
<tr class="odd">
<td><p>20017</p></td>
<td><p>エラー</p></td>
<td><p>AS MCU を利用できません</p></td>
<td><p>AS MCU を利用できません</p>
<p>AS MCU が実行されているかどうかを確認します</p></td>
</tr>
<tr class="even">
<td><p>20018</p></td>
<td><p>情報</p></td>
<td><p>AS MCU に接続できないエラーから復旧しました</p></td>
<td><p>該当なし</p></td>
</tr>
<tr class="odd">
<td><p>20019</p></td>
<td><p>エラー</p></td>
<td><p>データ MCU を利用できません</p></td>
<td><p>データ MCU を利用できません</p>
<p>データ MCU が実行されていることを確認します</p></td>
</tr>
<tr class="even">
<td><p>20020</p></td>
<td><p>情報</p></td>
<td><p>データ MCU に接続できないエラーから復旧しました</p></td>
<td><p>該当なし</p></td>
</tr>
<tr class="odd">
<td><p>20021</p></td>
<td><p>エラー</p></td>
<td><p>IM MCU に参加できません</p></td>
<td><p>IM MCU に参加できません</p>
<p>IM MCU が実行されているかどうかを確認します</p></td>
</tr>
<tr class="even">
<td><p>20022</p></td>
<td><p>エラー</p></td>
<td><p>AV MCU に参加できません</p></td>
<td><p>AV MCU に参加できません</p>
<p>AV MCU が実行されているかどうかを確認します</p></td>
</tr>
<tr class="odd">
<td><p>20023</p></td>
<td><p>エラー</p></td>
<td><p>AS MCU に参加できません</p></td>
<td><p>AS MCU に参加できません</p>
<p>AS MCU が実行されているかどうかを確認します</p></td>
</tr>
<tr class="even">
<td><p>20024</p></td>
<td><p>エラー</p></td>
<td><p>データ MCU に参加できません</p></td>
<td><p>データ MCU に参加できません</p>
<p>データ MCU が実行されていることを確認します</p></td>
</tr>
<tr class="odd">
<td><p>20025</p></td>
<td><p>エラー</p></td>
<td><p>Active Directory の写真にアクセスできません</p></td>
<td><p>Active Directory への接続を利用できません</p>
<p>Active Directory への接続が利用できることを確認します</p></td>
</tr>
<tr class="even">
<td><p>20026</p></td>
<td><p>情報</p></td>
<td><p>Active Directory の写真にアクセスできないエラーから復旧しました</p></td>
<td><p>該当なし</p></td>
</tr>
<tr class="odd">
<td><p>20027</p></td>
<td><p>警告</p></td>
<td><p>逆シリアル化できません</p></td>
<td><p>逆シリアル化できません</p>
<p>問題が解決しない場合は、製品サポートに問い合わせてください。</p></td>
</tr>
</tbody>
</table>

