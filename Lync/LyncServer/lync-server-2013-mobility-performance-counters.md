---
title: 'Lync Server 2013: モビリティパフォーマンスカウンター'
description: 'Lync Server 2013: モビリティパフォーマンスカウンター。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mobility performance counters
ms:assetid: d18ed85a-673d-4695-aa3f-ac83a38ab90a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690046(v=OCS.15)
ms:contentKeyID: 48185441
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 922288f6c026f088d651dc61afdcb6ba04fed30a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550533"
---
# <a name="mobility-performance-counters-in-lync-server-2013"></a>Lync Server 2013 のモビリティパフォーマンスカウンター

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-22_

次の表に、統合コミュニケーション Web API (UCWA) および Lync Server 2013 Mcx Mobility Service を実行しているサーバーの監視に使用できるパフォーマンスカウンターの名前と説明を示します。

UCWA テーブル内のカウンターのカテゴリ名は、 **LS: WEB – UCWA**です。

Mcx Mobility Service テーブル内のカウンターのカテゴリ名は、 **LS: WEB-Mobile Communication service**です。

<div>

## <a name="performance-counters-for-ucwa"></a>UCWA のパフォーマンスカウンター


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>カウンター</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>アクティブなアプリケーション数</p></td>
<td><p>現在のアプリケーション数</p></td>
</tr>
<tr class="even">
<td><p>アクティブなアプリケーション共有のモダリティ数</p></td>
<td><p>アプリケーション共有モダリティの現在の数</p></td>
</tr>
<tr class="odd">
<td><p>アクティブな音声モダリティ数</p></td>
<td><p>現在の音声モダリティ数</p></td>
</tr>
<tr class="even">
<td><p>アクティブデータコラボレーションのモダリティ数</p></td>
<td><p>現在のデータコラボレーションモダリティ数</p></td>
</tr>
<tr class="odd">
<td><p>Active Directory の写真取得待機時間 (ミリ秒)</p></td>
<td><p>このカウンターは、active directory から写真を取得する平均時間 (ミリ秒) を示します。</p></td>
</tr>
<tr class="even">
<td><p>アクティブなメッセージングモダリティ数</p></td>
<td><p>現在のメッセージングモダリティ数</p></td>
</tr>
<tr class="odd">
<td><p>アクティブなパノラマビデオモダリティ数</p></td>
<td><p>現在のパノラマビデオモダリティ数</p></td>
</tr>
<tr class="even">
<td><p>アクティブな保留中の取得数</p></td>
<td><p>現在アクティブな保留中の数を取得します。サーバーへの長時間保持接続</p></td>
</tr>
<tr class="odd">
<td><p>アクティブなセッション数</p></td>
<td><p>アプリケーションごとに UCWA に登録されている現在のエンドポイント数と合計</p></td>
</tr>
<tr class="even">
<td><p>アクティブなユーザーインスタンス数</p></td>
<td><p>ユーザーインスタンスの現在の数</p></td>
</tr>
<tr class="odd">
<td><p>アプリケーションを使用しないアクティブなユーザーインスタンス</p></td>
<td><p>アプリケーションが適用されていない現在のユーザーインスタンス数</p></td>
</tr>
<tr class="even">
<td><p>アクティブなビデオモダリティ数</p></td>
<td><p>現在のビデオモダリティ数</p></td>
</tr>
<tr class="odd">
<td><p>受信したアプリケーション作成要求の数/秒</p></td>
<td><p>受信したアプリケーション作成要求の1秒あたりの数</p></td>
</tr>
<tr class="even">
<td><p>MCU の参加に失敗した場合</p></td>
<td><p>AS MCU 参加エラーの数</p></td>
</tr>
<tr class="odd">
<td><p>AV MCU 参加エラー</p></td>
<td><p>AV MCU の参加に失敗した回数</p></td>
</tr>
<tr class="even">
<td><p>アプリケーションの平均起動時間 (ミリ秒)</p></td>
<td><p>アプリケーションの平均起動時間 (ミリ秒)</p></td>
</tr>
<tr class="odd">
<td><p>セッションの平均有効期間 (ミリ秒)</p></td>
<td><p>セッションの平均有効期間 (ミリ秒単位)</p></td>
</tr>
<tr class="even">
<td><p>データ MCU の参加エラー</p></td>
<td><p>データ MCU の参加に失敗した回数</p></td>
</tr>
<tr class="odd">
<td><p>Exchange の連絡先検索の待機時間 (ミリ秒)</p></td>
<td><p>このカウンターは、Exchange の連絡先を検索する平均時間 (ミリ秒) を示します。</p></td>
</tr>
<tr class="even">
<td><p>Exchange HD Photo Get 待機時間 (ミリ秒)</p></td>
<td><p>このカウンターは、Exchange から写真を取得する平均時間 (ミリ秒) を示します。</p></td>
</tr>
<tr class="odd">
<td><p>HTTP 4xx 応答/秒</p></td>
<td><p>HTTP 4xx コードでの応答の1秒あたりの数</p></td>
</tr>
<tr class="even">
<td><p>HTTP 5xx 応答/秒</p></td>
<td><p>HTTP 5xx コードでの応答の1秒あたりの数</p></td>
</tr>
<tr class="odd">
<td><p>IM MCU の参加エラー</p></td>
<td><p>IM MCU の参加に失敗した回数</p></td>
</tr>
<tr class="even">
<td><p>Active Directory の写真の Get エラー数</p></td>
<td><p>Active Directory からの写真の取得に失敗した回数の合計</p></td>
</tr>
<tr class="odd">
<td><p>連絡先検索エラー数</p></td>
<td><p>Exchange での連絡先の検索に失敗した回数の合計</p></td>
</tr>
<tr class="even">
<td><p>逆シリアル化エラーの数</p></td>
<td><p>逆シリアル化エラーの合計数</p></td>
</tr>
<tr class="odd">
<td><p>HD Photo Get エラーの数</p></td>
<td><p>Exchange からの HD 写真の取得に失敗した回数の合計</p></td>
</tr>
<tr class="even">
<td><p>アプリケーションごとのサブスクリプションの最大数</p></td>
<td><p>アプリケーションごとに許容される最大数を超えるサブスクリプション要求の数</p></td>
</tr>
<tr class="odd">
<td><p>バッチごとの最大サブスクリプション数</p></td>
<td><p>バッチごとに許容される最大数を超えるサブスクリプション要求の数</p></td>
</tr>
<tr class="even">
<td><p>プレゼンスサブスクリプションエラー</p></td>
<td><p>プレゼンスをサブスクライブしているエラーの数</p></td>
</tr>
<tr class="odd">
<td><p>エンドポイントエラーの登録</p></td>
<td><p>エンドポイントの登録に失敗した回数</p></td>
</tr>
<tr class="even">
<td><p>Received/Second 要求数</p></td>
<td><p>受信した要求の1秒あたりの数</p></td>
</tr>
<tr class="odd">
<td><p>成功した要求数/秒</p></td>
<td><p>成功した要求の1秒あたりの数 (HTTP 2xx/3xx 応答コード)</p></td>
</tr>
<tr class="even">
<td><p>正常に作成したアプリケーション要求/秒</p></td>
<td><p>成功したアプリケーション作成要求の1秒あたりの数</p></td>
</tr>
<tr class="odd">
<td><p>タイムアウト保留中の取得数</p></td>
<td><p>タイムアウトした保留中の取得の数</p></td>
</tr>
<tr class="even">
<td><p>受信したアプリケーション作成要求の合計数</p></td>
<td><p>サービスの開始以降に受信されたアプリケーション作成要求の合計数</p></td>
</tr>
<tr class="odd">
<td><p>HTTP 4xx 応答の合計数</p></td>
<td><p>HTTP 4xx 応答の合計数</p></td>
</tr>
<tr class="even">
<td><p>HTTP 5xx 応答の合計数</p></td>
<td><p>HTTP 5xx 応答の合計数</p></td>
</tr>
<tr class="odd">
<td><p>コマンドチャネルで受信した要求の合計数</p></td>
<td><p>コマンドチャネルで受信した要求の合計数</p></td>
</tr>
<tr class="even">
<td><p>成功した要求の合計数</p></td>
<td><p>成功した要求の合計数</p></td>
</tr>
<tr class="odd">
<td><p>開始されたセッションの合計数</p></td>
<td><p>サービスの開始以降に開始されたセッションの合計数</p></td>
</tr>
<tr class="even">
<td><p>アイドルタイムアウトが原因で終了したセッションの合計</p></td>
<td><p>ユーザーのアイドルタイムアウトが原因で終了したセッションの合計数</p></td>
</tr>
<tr class="odd">
<td><p>調整されるアプリケーションの合計数</p></td>
<td><p>調整されたアプリケーションの数</p></td>
</tr>
</tbody>
</table>


</div>

<div id="sectionSection1" class="section">

### <a name="performance-counters-for-mcx-mobility-service"></a>Mcx Mobility Service のパフォーマンスカウンター

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>カウンター</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>セッションの平均有効期間 (ミリ秒)</p></td>
<td><p>セッションの平均有効期間 (ミリ秒単位)</p></td>
</tr>
<tr class="even">
<td><p>現在のプッシュ通知サブスクリプション</p></td>
<td><p>プッシュ通知サブスクリプションの現在の数。 この数値は、現在アクティブなセッション数と組み合わせて、Windows Mobile または iPhone デバイス用に登録されている現在アクティブなセッションのサブセットを表します。</p></td>
</tr>
<tr class="odd">
<td><p>現在アクティブなネットワークのタイムアウトポーリング数</p></td>
<td><p>タイムアウトしたネットワークポーリングの数</p></td>
</tr>
<tr class="even">
<td><p>現在アクティブなポーリング数</p></td>
<td><p>現在アクティブなポーリングの数 (長時間保持されているサーバーへの接続)</p></td>
</tr>
<tr class="odd">
<td><p>現在アクティブなセッション数</p></td>
<td><p>Mobility Service に登録されている現在のエンドポイント数</p></td>
</tr>
<tr class="even">
<td><p>アクティブなプレゼンスサブスクリプションのある現在アクティブなセッション数</p></td>
<td><p>アクティブなプレゼンスサブスクリプションのある現在アクティブなセッションの数</p></td>
</tr>
<tr class="odd">
<td><p>プッシュ通知要求が失敗した/秒</p></td>
<td><p>失敗したプッシュ通知の1秒あたりの数</p></td>
</tr>
<tr class="even">
<td><p>1秒あたりに成功したプッシュ通知要求</p></td>
<td><p>成功したプッシュ通知の1秒あたりの数</p></td>
</tr>
<tr class="odd">
<td><p>プッシュ通知要求の調整/秒</p></td>
<td><p>調整されたプッシュ通知の1秒あたりの数</p></td>
</tr>
<tr class="even">
<td><p>プッシュ通知要求/秒</p></td>
<td><p>送信されたプッシュ通知の1秒あたりの数</p></td>
</tr>
<tr class="odd">
<td><p>失敗した要求数/秒</p></td>
<td><p>失敗した要求の1秒あたりの数</p></td>
</tr>
<tr class="even">
<td><p>Received/Second 要求数</p></td>
<td><p>受信した要求の1秒あたりの数</p></td>
</tr>
<tr class="odd">
<td><p>拒否された要求数/秒</p></td>
<td><p>拒否された要求の1秒あたりの数</p></td>
</tr>
<tr class="even">
<td><p>成功した要求数/秒</p></td>
<td><p>成功した要求の1秒あたりの数</p></td>
</tr>
<tr class="odd">
<td><p>正常開始セッション要求数/秒</p></td>
<td><p>成功した場所の取得要求の1秒あたりの数。 セッションを開始する要求は、サーバー上で最も CPU を消費します。 サポートされているピーク負荷は 12/秒です。 持続性は、サーバー上の他の負荷に依存します。 通常、セッションを開始することは、長期間にわたるサインアウトされたユーザーに対してサインインすることを意味します。</p></td>
</tr>
<tr class="even">
<td><p>着信音声通話の拒否合計数</p></td>
<td><p>拒否された着信音声通話の合計数</p></td>
</tr>
<tr class="odd">
<td><p>失敗した着信音声通話の合計数</p></td>
<td><p>失敗した着信音声通話の合計数</p></td>
</tr>
<tr class="even">
<td><p>失敗した発信音声通話の合計数</p></td>
<td><p>失敗した発信音声通話の合計数</p></td>
</tr>
<tr class="odd">
<td><p>ユーザーが終了したセッションの合計数</p></td>
<td><p>ユーザーが終了したセッションの合計数</p></td>
</tr>
<tr class="even">
<td><p>プッシュ通知要求の合計数</p></td>
<td><p>プッシュ通知要求の合計数</p></td>
</tr>
<tr class="odd">
<td><p>失敗したプッシュ通知要求の合計数</p></td>
<td><p>失敗したプッシュ通知要求の合計数</p></td>
</tr>
<tr class="even">
<td><p>成功したプッシュ通知要求の合計数</p></td>
<td><p>成功したプッシュ通知要求の合計数</p></td>
</tr>
<tr class="odd">
<td><p>調整されるプッシュ通知要求の合計数</p></td>
<td><p>調整されたプッシュ通知要求の合計数</p></td>
</tr>
<tr class="even">
<td><p>失敗した要求の合計数</p></td>
<td><p>失敗した要求の合計数</p></td>
</tr>
<tr class="odd">
<td><p>コマンドチャネルで受信した要求の合計数</p></td>
<td><p>コマンドチャネルで受信した要求の合計数</p></td>
</tr>
<tr class="even">
<td><p>拒否された要求の合計数</p></td>
<td><p>拒否された要求の合計数</p></td>
</tr>
<tr class="odd">
<td><p>成功した要求の合計数</p></td>
<td><p>Mobility Service に対して成功した要求の合計数</p></td>
</tr>
<tr class="even">
<td><p>セッションが開始した合計数</p></td>
<td><p>Mobility Service の開始以降に開始されたセッションの合計数</p></td>
</tr>
<tr class="odd">
<td><p>ユーザーのアイドルタイムアウトが原因で終了したセッションの合計数</p></td>
<td><p>ユーザーのアイドルタイムアウトが原因で終了したセッションの合計数</p></td>
</tr>
<tr class="even">
<td><p>成功した着信音声通話の合計数</p></td>
<td><p>成功した着信音声通話の合計数</p></td>
</tr>
<tr class="odd">
<td><p>成功した発信音声通話の合計数</p></td>
<td><p>成功した発信音声通話の合計数</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

