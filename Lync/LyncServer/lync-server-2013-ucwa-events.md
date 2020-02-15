---
title: 'Lync Server 2013: UCWA イベント'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UCWA events
ms:assetid: 26cb409d-f4e4-43c7-873f-b694702d491d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945621(v=OCS.15)
ms:contentKeyID: 51541461
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d42dbd967f90b6e2a905b92558c88fe52ef62d7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029168"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ucwa-events-in-lync-server-2013"></a>Lync Server 2013 の UCWA イベント

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-15_

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Lync Server 2013 は、統合コミュニケーション Web API (UCWA) を使用して、Microsoft Exchange への連絡先検索のアクセスからモバイルクライアントのプレゼンスの更新まで、さまざまな目的で使用します。

UCWA は、イベントの種類の情報、警告、およびエラーとして、操作動作の記録を書き込みます。 次の表では、UCWA コンポーネントによって記述できるイベントについて説明します。


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
<td><p>だけ</p></td>
<td><p>UCWA の初期化</p></td>
<td><p>該当なし</p>
<p>該当なし</p></td>
</tr>
<tr class="even">
<td><p>20002</p></td>
<td><p>Error</p></td>
<td><p>UCWA で初期化中に予期しない例外が発生しました</p></td>
<td><p>初期化中に予期しないエラーが発生しました</p>
<p>関連付けられたイベントログエントリの例外の詳細を調べて、考えられる原因を特定します。</p></td>
</tr>
<tr class="odd">
<td><p>20003</p></td>
<td><p>Error</p></td>
<td><p>UCWA で処理不能な例外が発生しました</p></td>
<td><p>処理不能な例外が発生しました</p>
<p>サーバーを再起動します。 問題が引き続き発生する場合は、製品サポートにお問い合わせください。</p></td>
</tr>
<tr class="even">
<td><p>20004</p></td>
<td><p>Error</p></td>
<td><p>HD photo の Exchange にアクセスできません</p></td>
<td><p>Exchange への接続は利用できません</p>
<p>Exchange への接続が利用可能であることを確認する</p></td>
</tr>
<tr class="odd">
<td><p>20005</p></td>
<td><p>だけ</p></td>
<td><p>HD photo の Exchange へのアクセス障害から復旧した</p></td>
<td><p>該当なし</p></td>
</tr>
<tr class="even">
<td><p>20006</p></td>
<td><p>Error</p></td>
<td><p>連絡先検索の Exchange にアクセスできない</p></td>
<td><p>Exchange への接続は利用できません</p>
<p>Exchange への接続が利用可能であることを確認する</p></td>
</tr>
<tr class="odd">
<td><p>20007</p></td>
<td><p>だけ</p></td>
<td><p>Exchange の連絡先を検索できない問題から回復した</p></td>
<td><p>該当なし</p></td>
</tr>
<tr class="even">
<td><p>20008</p></td>
<td><p>警告</p></td>
<td><p>アプリケーションごとに許可されるプレゼンスサブスクリプションを超えるサブスクライブを試行する</p></td>
<td><p>アプリケーションごとに許可されるプレゼンスサブスクリプションを超えるサブスクライブを試行する</p>
<p>クライアントに不要なサブスクリプションがあるかどうかを確認する</p></td>
</tr>
<tr class="odd">
<td><p>20009</p></td>
<td><p>警告</p></td>
<td><p>バッチごとに許可されるプレゼンスサブスクリプションの数を超えるサブスクライブを試行する</p></td>
<td><p>バッチごとに許可されるプレゼンスサブスクリプションの数を超えるサブスクライブを試行する</p>
<p>クライアントに不要なサブスクリプションがあるかどうかを確認する</p></td>
</tr>
<tr class="even">
<td><p>20010</p></td>
<td><p>Error</p></td>
<td><p>インバンドデータを取得できません</p></td>
<td><p>インバンドデータを取得できません</p>
<p>問題が引き続き発生する場合は、製品サポートにお問い合わせください。</p></td>
</tr>
<tr class="odd">
<td><p>20011</p></td>
<td><p>Error</p></td>
<td><p>プレゼンスをサブスクライブできません</p></td>
<td><p>プレゼンスをサブスクライブできません</p>
<p>問題が引き続き発生する場合は、製品サポートにお問い合わせください。</p></td>
</tr>
<tr class="even">
<td><p>20012</p></td>
<td><p>Error</p></td>
<td><p>エンドポイントの登録に失敗しました</p></td>
<td><p>エンドポイントの登録に失敗しました</p>
<p>問題が引き続き発生する場合は、製品サポートにお問い合わせください。</p></td>
</tr>
<tr class="odd">
<td><p>20013</p></td>
<td><p>Error</p></td>
<td><p>IM MCU は使用できません</p></td>
<td><p>IM MCU は使用できません</p>
<p>IM MCU が実行されているかどうかを確認する</p></td>
</tr>
<tr class="even">
<td><p>20014</p></td>
<td><p>だけ</p></td>
<td><p>IM MCU に接続できないエラーから復旧した</p></td>
<td><p>該当なし</p></td>
</tr>
<tr class="odd">
<td><p>20015</p></td>
<td><p>Error</p></td>
<td><p>AV MCU は利用できません</p></td>
<td><p>AV MCU は利用できません</p>
<p>AV MCU が実行されているかどうかを確認する</p></td>
</tr>
<tr class="even">
<td><p>20016</p></td>
<td><p>だけ</p></td>
<td><p>AV MCU に接続できないエラーから復旧した</p></td>
<td><p>該当なし</p></td>
</tr>
<tr class="odd">
<td><p>20017</p></td>
<td><p>Error</p></td>
<td><p>MCU が利用できない場合</p></td>
<td><p>MCU が利用できない場合</p>
<p>MCU が実行されているかどうかを確認する</p></td>
</tr>
<tr class="even">
<td><p>20018</p></td>
<td><p>だけ</p></td>
<td><p>MCU としての接続エラーから回復した</p></td>
<td><p>該当なし</p></td>
</tr>
<tr class="odd">
<td><p>20019</p></td>
<td><p>Error</p></td>
<td><p>データ MCU を使用できません</p></td>
<td><p>データ MCU を使用できません</p>
<p>データ MCU が実行されているかどうかを確認する</p></td>
</tr>
<tr class="even">
<td><p>20020</p></td>
<td><p>だけ</p></td>
<td><p>データ MCU に接続できないエラーから復旧した</p></td>
<td><p>該当なし</p></td>
</tr>
<tr class="odd">
<td><p>20021</p></td>
<td><p>Error</p></td>
<td><p>IM MCU に参加できません</p></td>
<td><p>IM MCU に参加できません</p>
<p>IM MCU が実行されているかどうかを確認する</p></td>
</tr>
<tr class="even">
<td><p>20022</p></td>
<td><p>Error</p></td>
<td><p>AV MCU に参加できません</p></td>
<td><p>AV MCU に参加できません</p>
<p>AV MCU が実行されているかどうかを確認する</p></td>
</tr>
<tr class="odd">
<td><p>20023</p></td>
<td><p>Error</p></td>
<td><p>MCU として参加できません</p></td>
<td><p>MCU として参加できません</p>
<p>MCU が実行されているかどうかを確認する</p></td>
</tr>
<tr class="even">
<td><p>20024</p></td>
<td><p>Error</p></td>
<td><p>データ MCU に参加できません</p></td>
<td><p>データ MCU に参加できません</p>
<p>データ MCU が実行されているかどうかを確認する</p></td>
</tr>
<tr class="odd">
<td><p>20025</p></td>
<td><p>Error</p></td>
<td><p>Active directory の写真にアクセスできません</p></td>
<td><p>Active directory への接続が利用できません</p>
<p>Active directory への接続が利用可能であることを確認する</p></td>
</tr>
<tr class="even">
<td><p>20026</p></td>
<td><p>だけ</p></td>
<td><p>Active directory の写真にアクセスできないエラーから復旧した</p></td>
<td><p>該当なし</p></td>
</tr>
<tr class="odd">
<td><p>20027</p></td>
<td><p>警告</p></td>
<td><p>逆シリアル化できません</p></td>
<td><p>逆シリアル化できません</p>
<p>問題が引き続き発生する場合は、製品サポートにお問い合わせください。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

