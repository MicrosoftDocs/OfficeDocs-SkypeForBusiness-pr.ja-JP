---
title: Skype for Business Server 2015 のモビリティ パフォーマンス カウンター
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d18ed85a-673d-4695-aa3f-ac83a38ab90a
description: 'Summary: Learn about the performance counters that you can use to monitor servers running the Unified Communications Web API (UCWA) and the Skype for Business Server 2015 Mcx Mobility Service.'
ms.openlocfilehash: 7f82f263969deb5fc71e448f0e514dd0056c31eb
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="mobility-performance-counters-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 のモビリティ パフォーマンス カウンター
 
**Summary:** Learn about the performance counters that you can use to monitor servers running the Unified Communications Web API (UCWA) and the Skype for Business Server 2015 Mcx Mobility Service.
  
The following tables list the names and descriptions of performance counters that you can use to monitor servers running the Unified Communications Web API (UCWA) and the Skype for Business Server 2015 Mcx Mobility Service. 
  
The category name for the counters in the UCWA table is **LS:WEB - UCWA**.
  
Mcx Mobility Service の表のカウンターのカテゴリ名は、**LS:WEB - Mobile Communication Service** です。
  
## <a name="performance-counters-for-ucwa"></a>UCWA のパフォーマンス カウンター

|**Counter**|**説明**|
|:-----|:-----|
|Active Application Count  <br/> |現在のアプリケーション数  <br/> |
|Active Application Sharing Modality Count  <br/> |現在のアプリケーション共有モダリティ数  <br/> |
|Active Audio Modality Count  <br/> |現在の音声モダリティ数  <br/> |
|Active Data Collaboration Modality Count  <br/> |現在のデータの共同作業モダリティ数  <br/> |
|Active Directory Photo Get Latency (ms)  <br/> |このカウンターは、Active Directory から写真を取得する平均時間 (ミリ秒) を示します  <br/> |
|Active Messaging Modality Count  <br/> |現在のメッセージング モダリティ数  <br/> |
|Active Panoramic Video Modality Count  <br/> |現在のパノラマ ビデオ モダリティ数  <br/> |
|Active Pending Get Count  <br/> |現在アクティブな保留中の取得数。サーバーへの接続は長時間維持されます  <br/> |
|Active Session Count  <br/> |アプリケーションごとに UCWA に登録されている現在のエンドポイント数と合計数  <br/> |
|Active User Instance Count  <br/> |現在のユーザー インスタンス数  <br/> |
|Active User Instances without Application  <br/> |現在のユーザー インスタンス数 (アプリケーションを含まない)  <br/> |
|Active Video Modality Count  <br/> |現在のビデオ モダリティ数  <br/> |
|Application Creation Requests Received/Second  <br/> |受信したアプリケーション作成要求の 1 秒あたりの数  <br/> |
|AS MCU Join Failures  <br/> |AS MCU 参加に失敗した数  <br/> |
|AV MCU Join Failures  <br/> |AV MCU 参加に失敗した数  <br/> |
|Average Application Startup Time (ms)  <br/> |アプリケーションの平均起動時間 (ミリ秒)  <br/> |
|Average Lifetime for Session (ms)  <br/> |セッションの平均存続期間 (ミリ秒)  <br/> |
|Data MCU Join Failures  <br/> |Data MCU 参加に失敗した数  <br/> |
|Exchange Contact Search Latency (ms)  <br/> |このカウンターは、Exchange 内の連絡先を検索する平均時間 (ミリ秒) を示します  <br/> |
|Exchange HD Photo Get Latency (ms)  <br/> |このカウンターは、Exchange から写真を取得する平均時間 (ミリ秒) を示します  <br/> |
|HTTP 4xx Responses/Second  <br/> |HTTP 4xx コードでの応答の 1 秒あたりの数  <br/> |
|HTTP 5xx Responses/Second  <br/> |HTTP 5xx コードでの応答の 1 秒あたりの数  <br/> |
|IM MCU Join Failures  <br/> |IM MCU 参加に失敗した数  <br/> |
|Number of Active Directory Photo Get Failures  <br/> |Active Directory からの写真の取得に失敗した合計数  <br/> |
|Number of Contact Search failures  <br/> |Exchange の連絡先の検索に失敗した合計数  <br/> |
|Number of Deserialization Failures  <br/> |シリアル化解除が失敗した合計数  <br/> |
|Number of HD Photo Get Failures  <br/> |Exchange からの HD 写真の取得に失敗した合計数  <br/> |
|Over The Maximum Subscriptions Per Application  <br/> |アプリケーションごとに許可された最大値を超えるサブスクリプション要求の数  <br/> |
|Over The Maximum Subscriptions Per Batch  <br/> |バッチごとに許可された最大値を超えるサブスクリプション要求の数  <br/> |
|Presence Subscription Failures  <br/> |プレゼンスの登録に失敗した数  <br/> |
|Registering Endpoint Failures  <br/> |エンドポイントの登録に失敗した数  <br/> |
|Requests Received/Second  <br/> |受信した要求の 1 秒あたりの数  <br/> |
|Requests Succeeded/Second  <br/> |成功した要求 (HTTP 2xx/3xx 応答コード) の 1 秒あたりの数  <br/> |
|Succeeded Create Application Requests/Second  <br/> |成功したアプリケーション作成要求の 1 秒あたりの数  <br/> |
|Timed Out Pending Get Count  <br/> |タイムアウトした保留中の取得の数  <br/> |
|Total Application Creation Requests Received  <br/> |サービスの開始以降に受信したアプリケーション作成要求の合計数  <br/> |
|Total HTTP 4xx Responses  <br/> |HTTP 4xx 応答の合計数  <br/> |
|Total HTTP 5xx Responses  <br/> |HTTP 5xx 応答の合計数  <br/> |
|Total Requests Received on the Command Channel  <br/> |コマンド チャネルで受信した要求の合計数  <br/> |
|Total Requests Succeeded  <br/> |成功した要求の合計数  <br/> |
|Total Sessions Initiated  <br/> |サービスが開始されてから起動されたセッションの合計数  <br/> |
|Total Sessions Terminated Because of Idle Timeout  <br/> |ユーザーのアイドル タイムアウトが原因で終了したセッションの合計数  <br/> |
|Total Throttled Applications  <br/> |制限されたアプリケーションの数  <br/> |
   
**Performance Counters for Mcx Mobility Service**

|**Counter**|**説明**|
|:-----|:-----|
|Average Lifetime for a Session in Milliseconds  <br/> |セッションの平均存続期間 (ミリ秒)  <br/> |
|Current Push Notification Subscriptions  <br/> |プッシュ通知サブスクリプションの現在の数。この数は、Currently Active Session Count と連携して、Windows Mobile または iPhone のデバイスに登録された現在アクティブなセッションのサブセットを表します。  <br/> |
|Currently Active Network Timeout Poll Count  <br/> |タイムアウトしたネットワーク ポーリングの数  <br/> |
|Currently Active Poll Count  <br/> |現在アクティブなポーリングの数 (長時間維持されるサーバーとの接続)  <br/> |
|Currently Active Session Count  <br/> |Mobility Service に登録されたエンドポイントの現在の数  <br/> |
|Currently Active Session Count with Active Presence Subscriptions  <br/> |アクティブなプレゼンス サブスクリプションのある現在アクティブなセッションの数  <br/> |
|Push Notification Requests Failed/Second  <br/> |失敗したプッシュ通知の 1 秒あたりの数  <br/> |
|Push Notification Requests Succeeded/Second  <br/> |成功したプッシュ通知の 1 秒あたりの数  <br/> |
|Push Notification Requests Throttled/Second  <br/> |調整済みのプッシュ通知の 1 秒あたりの数  <br/> |
|Push Notification Requests/Second  <br/> |送信されたプッシュ通知の 1 秒あたりの数  <br/> |
|Requests Failed/Second  <br/> |失敗した要求の 1 秒あたりの数  <br/> |
|Requests Received/Second  <br/> |受信した要求の 1 秒あたりの数  <br/> |
|Requests Rejected/Second  <br/> |拒否された要求の 1 秒あたりの数  <br/> |
|Requests Succeeded/Second  <br/> |成功した要求の 1 秒あたりの数  <br/> |
|Succeeded Initiate Session Requests/Second  <br/> |成功した Get Location 要求の 1 秒あたりの数。セッションを開始する要求は、サーバー上の大部分の CPU を消費します。ピーク時にサポートされるロードは 12/秒です。持続可能性は、サーバー上の他のロードによって異なります。セッションの開始は、通常、長時間サインアウトしていたユーザーのサインインを意味します。  <br/> |
|Total Declined Inbound Voice Calls  <br/> |拒否された着信音声通話の合計数  <br/> |
|Total Failed Inbound Voice Calls  <br/> |失敗した着信音声通話の合計数  <br/> |
|Total Failed Outbound Voice Calls  <br/> |失敗した発信音声通話の合計数  <br/> |
|Total number of sessions terminated by user  <br/> |ユーザーが終了したセッションの合計数  <br/> |
|Total Push Notification Requests  <br/> |プッシュ通知要求の合計数  <br/> |
|Total Push Notification Requests Failed  <br/> |失敗したプッシュ通知要求の合計数  <br/> |
|Total Push Notification Requests Succeeded  <br/> |成功したプッシュ通知要求の合計数  <br/> |
|Total Push Notification Requests Throttled  <br/> |調整済みのプッシュ通知要求の合計数  <br/> |
|Total Requests Failed  <br/> |失敗した要求の合計数  <br/> |
|Total Requests received on the Command Channel  <br/> |コマンド チャネルで受信した要求の合計数  <br/> |
|Total Requests Rejected  <br/> |拒否された要求の合計数  <br/> |
|Total Requests Succeeded  <br/> |Mobility Service に対する成功した要求の合計数  <br/> |
|Total Session Initiated Count  <br/> |Mobility Service が開始されてから起動されたセッションの合計数  <br/> |
|Total Sessions Terminated Because of User Idle Timeout  <br/> |ユーザーのアイドル タイムアウトが原因で終了したセッションの合計数  <br/> |
|Total Successful Inbound Voice Calls  <br/> |成功した着信音声通話の合計数  <br/> |
|Total Successful Outbound Voice Calls  <br/> |成功した発信音声通話の合計数  <br/> |
   

