---
title: Skype for Business Server のモビリティ パフォーマンス カウンター
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d18ed85a-673d-4695-aa3f-ac83a38ab90a
description: '概要: Unified Communications Web API (UCWA) および Skype for Business Server Mcx Mobility Service を実行しているサーバーを監視するために使用できるパフォーマンス カウンターについて説明します。'
ms.openlocfilehash: d711ada11cee9cb12a5cde25cab583f8b174ac50
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814407"
---
# <a name="mobility-performance-counters-in-skype-for-business-server"></a>Skype for Business Server のモビリティ パフォーマンス カウンター
 
**概要:** Unified Communications Web API (UCWA) および Skype for Business Server Mcx Mobility Service を実行しているサーバーを監視するために使用できるパフォーマンス カウンターについて説明します。
  
次の表に、Unified Communications Web API (UCWA) および Skype for Business Server Mcx Mobility Service を実行しているサーバーを監視するために使用できるパフォーマンス カウンターの名前と説明を示します。 
  
UCWA テーブル内のカウンターのカテゴリ名は **LS:WEB - UCWA です**。
  
Mcx Mobility Service テーブルのカウンターのカテゴリ名は **、LS:WEB - Mobile Communication Service です**。

> [!NOTE]
> 従来のモバイル クライアントの MCX (モビリティ サービス) サポートは、Skype for Business Server 2019 では利用できなくなりました。 現在のすべての Skype for Business モバイル クライアントはUnified Communications Web API (UCWA) を使用して、インスタント メッセージング (IM)、プレゼンス、および連絡先をサポートしています。 MCX を使用している従来のクライアントを持っているユーザーは、現在のクライアントにアップグレードする必要があります。
  
## <a name="performance-counters-for-ucwa"></a>UCWA のパフォーマンス カウンター

|カウンター|説明|
|:-----|:-----|
|Active Application Count  <br/> |現在のアプリケーション数  <br/> |
|Active Application Sharing Modality Count  <br/> |アプリケーション共有モダリティの現在の数  <br/> |
|Active Audio Modality Count  <br/> |現在のオーディオ モダリティの数  <br/> |
|Active Data Collaboration Modality Count  <br/> |データ コラボレーション モダリティの現在の数  <br/> |
|Active Directory Photo Get Latency (ms)  <br/> |このカウンターは、Active Directory から写真を取得する平均時間 (ミリ秒) を示します。  <br/> |
|Active Messaging Modality Count  <br/> |メッセージング モダリティの現在の数  <br/> |
|Active Panoramic Video Modality Count  <br/> |パノラマ ビデオ モダリティの現在の数  <br/> |
|Active Pending Get Count  <br/> |現在アクティブな保留中の取得数。サーバーへの長時間の接続  <br/> |
|アクティブ なセッション数  <br/> |アプリケーションごとの UCWA に登録されているエンドポイントの現在の数と合計  <br/> |
|アクティブ ユーザー インスタンス数  <br/> |現在のユーザー インスタンス数  <br/> |
|Application を使用しないアクティブなユーザー インスタンス  <br/> |アプリケーションのないユーザー インスタンスの現在の数  <br/> |
|Active Video Modality Count  <br/> |現在のビデオ モダリティ数  <br/> |
|Application Creation Requests Received/Second  <br/> |受信したアプリケーション作成要求の 1 秒あたりの数  <br/> |
|AS MCU Join Failures  <br/> |AS MCU 参加エラーの数  <br/> |
|AV MCU Join Failures  <br/> |AV MCU Join Failures の数  <br/> |
|平均アプリケーション起動時間 (ミリ秒)  <br/> |アプリケーションの平均起動時間 (ミリ秒)  <br/> |
|セッションの平均有効期間 (ミリ秒)  <br/> |セッションの平均有効期間 (ミリ秒単位)  <br/> |
|Data MCU Join Failures  <br/> |Data MCU Join Failures の数  <br/> |
|Exchange 連絡先検索の待機時間 (ミリ秒)  <br/> |このカウンターは、Exchange で連絡先を検索する平均時間 (ミリ秒) を示します。  <br/> |
|Exchange HD Photo Get Latency (ms)  <br/> |このカウンターは、Exchange から写真を取得する平均時間 (ミリ秒) を示します。  <br/> |
|HTTP 4xx Responses/Second  <br/> |HTTP 4xx コードを使用した 1 秒あたりの応答数  <br/> |
|HTTP 5xx Responses/Second  <br/> |HTTP 5xx コードでの 1 秒あたりの応答数  <br/> |
|IM MCU Join Failures  <br/> |IM MCU 参加エラーの数  <br/> |
|Active Directory Photo Get Failures の数  <br/> |Active Directory から写真を取得する失敗の総数  <br/> |
|連絡先検索の失敗回数  <br/> |Exchange で連絡先を検索する失敗の総数  <br/> |
|逆シリアル化エラーの数  <br/> |逆シリアル化エラーの総数  <br/> |
|HD Photo Get Failures の数  <br/> |Exchange から HD 写真を取得する失敗の総数  <br/> |
|アプリケーションあたりの最大サブスクリプション数を超える  <br/> |アプリケーションごとに許可されている最大数を超えるサブスクリプション要求の数  <br/> |
|バッチあたりの最大サブスクリプション数を超える  <br/> |バッチあたりの最大許容数を超えるサブスクリプション要求の数  <br/> |
|プレゼンス サブスクリプションの失敗  <br/> |プレゼンスをサブスクライブする失敗の数  <br/> |
|エンドポイント エラーの登録  <br/> |エンドポイントの登録に失敗した回数  <br/> |
|Requests Received/Second  <br/> |受信した要求の 1 秒あたりの数  <br/> |
|Requests Succeeded/Second  <br/> |成功した要求の 1 秒あたりの数 (HTTP 2xx/3xx 応答コード)  <br/> |
|Succeeded Create Application Requests/Second  <br/> |成功したアプリケーション作成要求の 1 秒あたりの数  <br/> |
|Timed Out Pending Get Count  <br/> |タイム アウトした保留中の取得の数  <br/> |
|Total Application Creation Requests Received  <br/> |サービスの開始後に受信したアプリケーション作成要求の総数  <br/> |
|Total HTTP 4xx Responses  <br/> |HTTP 4xx 応答の総数  <br/> |
|Total HTTP 5xx Responses  <br/> |HTTP 5xx 応答の総数  <br/> |
|コマンド チャネルで受信した要求の総数  <br/> |コマンド チャネルで受信した要求の総数  <br/> |
|Total Requests Succeeded  <br/> |成功した要求の総数  <br/> |
|開始されたセッションの総数  <br/> |サービスの開始後に開始されたセッションの総数  <br/> |
|アイドル タイムアウトにより終了したセッションの総数  <br/> |ユーザーのアイドル タイムアウトのために終了されたセッションの総数  <br/> |
|調整されたアプリケーションの総数  <br/> |調整されたアプリケーションの数  <br/> |
   
**Mcx Mobility Service のパフォーマンス カウンター**

|**カウンター**|**説明**|
|:-----|:-----|
|セッションの平均有効期間 (ミリ秒単位)  <br/> |セッションの平均有効期間 (ミリ秒単位)  <br/> |
|Current Push Notification Subscriptions  <br/> |プッシュ通知サブスクリプションの現在の数。 この番号は、Currently Active Session Count と共に、Windows Mobile または iPhone デバイスに登録されている現在アクティブなセッションのサブセットを表します。  <br/> |
|Currently Active Network Timeout Poll Count  <br/> |タイム アウトしたネットワーク ポーリングの数  <br/> |
|現在アクティブなポーリング数  <br/> |現在アクティブなポーリングの数 (サーバーへの長時間の接続)  <br/> |
|現在アクティブなセッション数  <br/> |Mobility Service に登録されているエンドポイントの現在の数  <br/> |
|Currently Active Session Count with Active Presence Subscriptions  <br/> |アクティブなプレゼンス サブスクリプションを使用している現在アクティブなセッションの数  <br/> |
|プッシュ通知要求が失敗/秒  <br/> |失敗したプッシュ通知の 1 秒あたりの数  <br/> |
|プッシュ通知要求の成功/秒  <br/> |成功したプッシュ通知の 1 秒あたりの数  <br/> |
|プッシュ通知要求の調整/秒  <br/> |調整されたプッシュ通知の 1 秒あたりの数  <br/> |
|プッシュ通知要求/秒  <br/> |送信されたプッシュ通知の 1 秒あたりの数  <br/> |
|Requests Failed/Second  <br/> |失敗した要求の 1 秒あたりの数  <br/> |
|Requests Received/Second  <br/> |受信した要求の 1 秒あたりの数  <br/> |
|Requests Rejected/Second  <br/> |拒否された要求の 1 秒あたりの数  <br/> |
|Requests Succeeded/Second  <br/> |成功した要求の 1 秒あたりの数  <br/> |
|Succeeded Initiate Session Requests/Second  <br/> |成功した場所の取得要求の 1 秒あたりの数。 セッションを開始する要求は、サーバー上で最も多くの CPU を消費します。 サポートされるピーク負荷は 12/秒です。 負荷は、サーバー上の他の負荷に依存します。 セッションの開始は、通常、長期サインアウトしたユーザーのサインインを意味します。  <br/> |
|Total Declined Inbound Voice Calls  <br/> |辞退された着信音声通話の総数  <br/> |
|Total Failed Inbound Voice Calls  <br/> |失敗した着信音声呼び出しの総数  <br/> |
|Total Failed Outbound Voice Calls  <br/> |失敗した発信音声通話の総数  <br/> |
|ユーザーによって終了されたセッションの総数  <br/> |ユーザーによって終了されたセッションの総数  <br/> |
|Total Push Notification Requests  <br/> |プッシュ通知要求の総数  <br/> |
|Total Push Notification Requests Failed  <br/> |失敗したプッシュ通知要求の総数  <br/> |
|Total Push Notification Requests Succeeded  <br/> |成功したプッシュ通知要求の総数  <br/> |
|Total Push Notification Requests Throttled  <br/> |調整されたプッシュ通知要求の総数  <br/> |
|Total Requests Failed  <br/> |失敗した要求の総数  <br/> |
|コマンド チャネルで受信した要求の総数  <br/> |コマンド チャネルで受信した要求の総数  <br/> |
|Total Requests Rejected  <br/> |拒否された要求の総数  <br/> |
|Total Requests Succeeded  <br/> |Mobility Service に対して成功した要求の総数  <br/> |
|Total Session Initiated Count  <br/> |Mobility Service の開始後に開始されたセッションの総数  <br/> |
|ユーザーのアイドル タイムアウトにより終了したセッションの総数  <br/> |ユーザーのアイドル タイムアウトのために終了されたセッションの総数  <br/> |
|Total Successful Inbound Voice Calls  <br/> |成功した着信音声呼び出しの総数  <br/> |
|Total Successful Outbound Voice Calls  <br/> |成功した発信音声通話の総数  <br/> |
   
> [!NOTE]
> 従来のモバイル クライアントの MCX (モビリティ サービス) サポートは、Skype for Business Server 2019 では利用できなくなりました。 現在のすべての Skype for Business モバイル クライアントはUnified Communications Web API (UCWA) を使用して、インスタント メッセージング (IM)、プレゼンス、および連絡先をサポートしています。 MCX を使用している従来のクライアントを持っているユーザーは、現在のクライアントにアップグレードする必要があります。
