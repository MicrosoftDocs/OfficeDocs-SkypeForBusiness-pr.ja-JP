---
title: モビリティ パフォーマンス カウンター
TOCTitle: モビリティ パフォーマンス カウンター
ms:assetid: d18ed85a-673d-4695-aa3f-ac83a38ab90a
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Hh690046(v=OCS.15)
ms:contentKeyID: 48273649
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# モビリティ パフォーマンス カウンター

 

_**トピックの最終更新日:** 2015-03-09_

以下の表は、Unified Communications Web API (UCWA) および Lync Server 2013 Mcx Mobility Service を実行しているサーバーの監視に使用できるパフォーマンス カウンターの名前と説明です。

UCWA の表のカウンターのカテゴリ名は、**LS:WEB - UCWA** です。

Mcx Mobility Service の表のカウンターのカテゴリ名は、**LS:WEB - Mobile Communication Service** です。

## UCWA のパフォーマンス カウンター


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
<td><p>Active Application Count</p></td>
<td><p>現在のアプリケーション数</p></td>
</tr>
<tr class="even">
<td><p>Active Application Sharing Modality Count</p></td>
<td><p>現在のアプリケーション共有モダリティ数</p></td>
</tr>
<tr class="odd">
<td><p>Active Audio Modality Count</p></td>
<td><p>現在の音声モダリティ数</p></td>
</tr>
<tr class="even">
<td><p>Active Data Collaboration Modality Count</p></td>
<td><p>現在のデータの共同作業モダリティ数</p></td>
</tr>
<tr class="odd">
<td><p>Active Directory Photo Get Latency (ms)</p></td>
<td><p>このカウンターは、Active Directory から写真を取得する平均時間 (ミリ秒) を示します</p></td>
</tr>
<tr class="even">
<td><p>Active Messaging Modality Count</p></td>
<td><p>現在のメッセージング モダリティ数</p></td>
</tr>
<tr class="odd">
<td><p>Active Panoramic Video Modality Count</p></td>
<td><p>現在のパノラマ ビデオ モダリティ数</p></td>
</tr>
<tr class="even">
<td><p>Active Pending Get Count</p></td>
<td><p>現在アクティブな保留中の取得数、サーバーへの接続は長時間維持されます</p></td>
</tr>
<tr class="odd">
<td><p>Active Session Count</p></td>
<td><p>アプリケーションごとに UCWA に登録されている現在のエンドポイント数と合計数</p></td>
</tr>
<tr class="even">
<td><p>Active User Instance Count</p></td>
<td><p>現在のユーザー インスタンス数</p></td>
</tr>
<tr class="odd">
<td><p>Active User Instances without Application</p></td>
<td><p>現在のユーザー インスタンス数 (アプリケーションを含まない)</p></td>
</tr>
<tr class="even">
<td><p>Active Video Modality Count</p></td>
<td><p>現在のビデオ モダリティ数</p></td>
</tr>
<tr class="odd">
<td><p>Application Creation Requests Received/Second</p></td>
<td><p>受信したアプリケーション作成要求の 1 秒あたりの数</p></td>
</tr>
<tr class="even">
<td><p>AS MCU Join Failures</p></td>
<td><p>AS MCU 参加に失敗した数</p></td>
</tr>
<tr class="odd">
<td><p>AV MCU Join Failures</p></td>
<td><p>AV MCU 参加に失敗した数</p></td>
</tr>
<tr class="even">
<td><p>Average Application Startup Time (ms)</p></td>
<td><p>アプリケーションの平均起動時間 (ミリ秒)</p></td>
</tr>
<tr class="odd">
<td><p>Average Lifetime for Session (ms)</p></td>
<td><p>セッションの平均存続期間 (ミリ秒)</p></td>
</tr>
<tr class="even">
<td><p>Data MCU Join Failures</p></td>
<td><p>Data MCU 参加に失敗した数</p></td>
</tr>
<tr class="odd">
<td><p>Exchange Contact Search Latency (ms)</p></td>
<td><p>このカウンターは、Exchange 内の連絡先を検索する平均時間 (ミリ秒) を示します</p></td>
</tr>
<tr class="even">
<td><p>Exchange HD Photo Get Latency (ms)</p></td>
<td><p>このカウンターは、Exchange から写真を取得する平均時間 (ミリ秒) を示します</p></td>
</tr>
<tr class="odd">
<td><p>HTTP 4xx Responses/Second</p></td>
<td><p>HTTP 4xx コードでの応答の 1 秒あたりの数</p></td>
</tr>
<tr class="even">
<td><p>HTTP 5xx Responses/Second</p></td>
<td><p>HTTP 5xx コードでの応答の 1 秒あたりの数</p></td>
</tr>
<tr class="odd">
<td><p>IM MCU Join Failures</p></td>
<td><p>IM MCU 参加に失敗した数</p></td>
</tr>
<tr class="even">
<td><p>Number of Active Directory Photo Get Failures</p></td>
<td><p>Active Directory からの写真の取得に失敗した合計数</p></td>
</tr>
<tr class="odd">
<td><p>Number of Contact Search failures</p></td>
<td><p>Exchange の連絡先の検索に失敗した合計数</p></td>
</tr>
<tr class="even">
<td><p>Number of Deserialization Failures</p></td>
<td><p>シリアル化解除が失敗した合計数</p></td>
</tr>
<tr class="odd">
<td><p>Number of HD Photo Get Failures</p></td>
<td><p>Exchange からの HD 写真の取得に失敗した合計数</p></td>
</tr>
<tr class="even">
<td><p>Over The Maximum Subscriptions Per Application</p></td>
<td><p>アプリケーションごとに許可された最大値を超えるサブスクリプション要求の数</p></td>
</tr>
<tr class="odd">
<td><p>Over The Maximum Subscriptions Per Batch</p></td>
<td><p>バッチごとに許可された最大値を超えるサブスクリプション要求の数</p></td>
</tr>
<tr class="even">
<td><p>Presence Subscription Failures</p></td>
<td><p>プレゼンスの登録に失敗した数</p></td>
</tr>
<tr class="odd">
<td><p>Registering Endpoint Failures</p></td>
<td><p>エンドポイントの登録に失敗した数</p></td>
</tr>
<tr class="even">
<td><p>Requests Received/Second</p></td>
<td><p>受信した要求の 1 秒あたりの数</p></td>
</tr>
<tr class="odd">
<td><p>Requests Succeeded/Second</p></td>
<td><p>成功した要求 (HTTP 2xx/3xx 応答コード) の 1 秒あたりの数</p></td>
</tr>
<tr class="even">
<td><p>Succeeded Create Application Requests/Second</p></td>
<td><p>成功したアプリケーション作成要求の 1 秒あたりの数</p></td>
</tr>
<tr class="odd">
<td><p>Timed Out Pending Get Count</p></td>
<td><p>タイムアウトした保留中の取得の数</p></td>
</tr>
<tr class="even">
<td><p>Total Application Creation Requests Received</p></td>
<td><p>サービスの開始以降に受信したアプリケーション作成要求の合計数</p></td>
</tr>
<tr class="odd">
<td><p>Total HTTP 4xx Responses</p></td>
<td><p>HTTP 4xx 応答の合計数</p></td>
</tr>
<tr class="even">
<td><p>Total HTTP 5xx Responses</p></td>
<td><p>HTTP 5xx 応答の合計数</p></td>
</tr>
<tr class="odd">
<td><p>Total Requests Received on the Command Channel</p></td>
<td><p>コマンド チャネルで受信した要求の合計数</p></td>
</tr>
<tr class="even">
<td><p>Total Requests Succeeded</p></td>
<td><p>成功した要求の合計数</p></td>
</tr>
<tr class="odd">
<td><p>Total Sessions Initiated</p></td>
<td><p>サービスが開始されてから起動されたセッションの合計数</p></td>
</tr>
<tr class="even">
<td><p>Total Sessions Terminated Because of Idle Timeout</p></td>
<td><p>ユーザーのアイドル タイムアウトが原因で終了したセッションの合計数</p></td>
</tr>
<tr class="odd">
<td><p>Total Throttled Applications</p></td>
<td><p>制限されたアプリケーションの数</p></td>
</tr>
</tbody>
</table>


### Mcx Mobility Service のパフォーマンス カウンター

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
<td><p>Average Lifetime for a Session in Milliseconds</p></td>
<td><p>セッションの平均存続期間 (ミリ秒)</p></td>
</tr>
<tr class="even">
<td><p>Current Push Notification Subscriptions</p></td>
<td><p>プッシュ通知サブスクリプションの現在の数。この数は、Currently Active Session Count と連携して、Windows Mobile または iPhone のデバイスに登録された現在アクティブなセッションのサブセットを表します。</p></td>
</tr>
<tr class="odd">
<td><p>Currently Active Network Timeout Poll Count</p></td>
<td><p>タイムアウトしたネットワーク ポーリングの数</p></td>
</tr>
<tr class="even">
<td><p>Currently Active Poll Count</p></td>
<td><p>現在アクティブなポーリングの数 (長時間維持されるサーバーとの接続)</p></td>
</tr>
<tr class="odd">
<td><p>Currently Active Session Count</p></td>
<td><p>Mobility Service に登録されたエンドポイントの現在の数</p></td>
</tr>
<tr class="even">
<td><p>Currently Active Session Count with Active Presence Subscriptions</p></td>
<td><p>アクティブなプレゼンス サブスクリプションのある現在アクティブなセッションの数</p></td>
</tr>
<tr class="odd">
<td><p>Push Notification Requests Failed/Second</p></td>
<td><p>失敗したプッシュ通知の 1 秒あたりの数</p></td>
</tr>
<tr class="even">
<td><p>Push Notification Requests Succeeded/Second</p></td>
<td><p>成功したプッシュ通知の 1 秒あたりの数</p></td>
</tr>
<tr class="odd">
<td><p>Push Notification Requests Throttled/Second</p></td>
<td><p>調整済みのプッシュ通知の 1 秒あたりの数</p></td>
</tr>
<tr class="even">
<td><p>Push Notification Requests/Second</p></td>
<td><p>送信されたプッシュ通知の 1 秒あたりの数</p></td>
</tr>
<tr class="odd">
<td><p>Requests Failed/Second</p></td>
<td><p>失敗した要求の 1 秒あたりの数</p></td>
</tr>
<tr class="even">
<td><p>Requests Received/Second</p></td>
<td><p>受信した要求の 1 秒あたりの数</p></td>
</tr>
<tr class="odd">
<td><p>Requests Rejected/Second</p></td>
<td><p>拒否された要求の 1 秒あたりの数</p></td>
</tr>
<tr class="even">
<td><p>Requests Succeeded/Second</p></td>
<td><p>成功した要求の 1 秒あたりの数</p></td>
</tr>
<tr class="odd">
<td><p>Succeeded Initiate Session Requests/Second</p></td>
<td><p>成功した Get Location 要求の 1 秒あたりの数。セッションを開始する要求は、サーバー上の大部分の CPU を消費します。ピーク時にサポートされるロードは 12/秒です。持続可能性は、サーバー上の他のロードによって異なります。セッションの開始は、通常、長時間サインアウトしていたユーザーのサインインを意味します。</p></td>
</tr>
<tr class="even">
<td><p>Total Declined Inbound Voice Calls</p></td>
<td><p>拒否された着信音声通話の合計数</p></td>
</tr>
<tr class="odd">
<td><p>Total Failed Inbound Voice Calls</p></td>
<td><p>失敗した着信音声通話の合計数</p></td>
</tr>
<tr class="even">
<td><p>Total Failed Outbound Voice Calls</p></td>
<td><p>失敗した発信音声通話の合計数</p></td>
</tr>
<tr class="odd">
<td><p>Total number of sessions terminated by user</p></td>
<td><p>ユーザーが終了したセッションの合計数</p></td>
</tr>
<tr class="even">
<td><p>Total Push Notification Requests</p></td>
<td><p>プッシュ通知要求の合計数</p></td>
</tr>
<tr class="odd">
<td><p>Total Push Notification Requests Failed</p></td>
<td><p>失敗したプッシュ通知要求の合計数</p></td>
</tr>
<tr class="even">
<td><p>Total Push Notification Requests Succeeded</p></td>
<td><p>成功したプッシュ通知要求の合計数</p></td>
</tr>
<tr class="odd">
<td><p>Total Push Notification Requests Throttled</p></td>
<td><p>調整済みのプッシュ通知要求の合計数</p></td>
</tr>
<tr class="even">
<td><p>Total Requests Failed</p></td>
<td><p>失敗した要求の合計数</p></td>
</tr>
<tr class="odd">
<td><p>Total Requests received on the Command Channel</p></td>
<td><p>コマンド チャネルで受信した要求の合計数</p></td>
</tr>
<tr class="even">
<td><p>Total Requests Rejected</p></td>
<td><p>拒否された要求の合計数</p></td>
</tr>
<tr class="odd">
<td><p>Total Requests Succeeded</p></td>
<td><p>Mobility Service に対する成功した要求の合計数</p></td>
</tr>
<tr class="even">
<td><p>Total Session Initiated Count</p></td>
<td><p>Mobility Service が開始されてから起動されたセッションの合計数</p></td>
</tr>
<tr class="odd">
<td><p>Total Sessions Terminated Because of User Idle Timeout</p></td>
<td><p>ユーザーのアイドル タイムアウトが原因で終了したセッションの合計数</p></td>
</tr>
<tr class="even">
<td><p>Total Successful Inbound Voice Calls</p></td>
<td><p>成功した着信音声通話の合計数</p></td>
</tr>
<tr class="odd">
<td><p>Total Successful Outbound Voice Calls</p></td>
<td><p>成功した発信音声通話の合計数</p></td>
</tr>
</tbody>
</table>

