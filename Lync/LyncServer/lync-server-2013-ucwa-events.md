---
title: 'Lync Server 2013: UCWA イベント'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: UCWA events
ms:assetid: 26cb409d-f4e4-43c7-873f-b694702d491d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945621(v=OCS.15)
ms:contentKeyID: 51541461
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0671b51e5fbd4b5f072676855d9e8f5201b3e04
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848381"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ucwa-events-in-lync-server-2013"></a>Lync Server での UCWA 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-15_

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Lync Server 2013 は、Microsoft Exchange に連絡して、モバイルクライアントのプレゼンスを更新するなど、さまざまな目的で、ユニファイドコミュニケーション Web API (UCWA) を使用します。

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
<th>概要</th>
<th>原因と解決策</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>20001</p></td>
<td><p>情報</p></td>
<td><p>UCWA が初期化されました</p></td>
<td><p>N/A</p>
<p>N/A</p></td>
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
<td><p>N/A</p></td>
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
<td><p>N/A</p></td>
</tr>
<tr class="even">
<td><p>20008</p></td>
<td><p>警告</p></td>
<td><p>アプリケーションごとの許容数を超えるプレゼンス サブスクリプションの登録が試行されました</p></td>
<td><p>アプリケーションごとの許容数を超えるプレゼンス サブスクリプションの登録が試行されました</p>
<p>クライアントに不要なサブスクリプションがないかどうかを確認します</p></td>
</tr>
<tr class="odd">
<td><p>20009</p></td>
<td><p>警告</p></td>
<td><p>バッチごとの許容数を超えるプレゼンス サブスクリプションの登録が試行されました</p></td>
<td><p>バッチごとの許容数を超えるプレゼンス サブスクリプションの登録が試行されました</p>
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
<td><p>N/A</p></td>
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
<td><p>N/A</p></td>
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
<td><p>N/A</p></td>
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


</div>

<span> </span>

</div>

</div>

</div>

