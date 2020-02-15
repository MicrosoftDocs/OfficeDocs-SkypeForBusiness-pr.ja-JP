---
title: Skype for Business Server の診断レポート
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b389dbd9-f2e8-4184-93d0-2e504796ac16
description: '概要: Skype for Business Server の診断レポートについて説明します。'
ms.openlocfilehash: f1a8d9a0c027019708f2be75fec14634197c4e2b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041994"
---
# <a name="diagnostic-report-in-skype-for-business-server"></a>Skype for Business Server の診断レポート
 
**概要:** Skype for Business Server の診断レポートについて説明します。
  
診断レポートは、エラーが発生したセッションの診断とトラブルシューティングの情報を提供します。 この情報には、診断 ID と、セッションが失敗したときに報告された診断ヘッダーの両方が含まれます。 診断 ID は、SIP メッセージに関連付けられた一意の識別子 (ms diagnostics ヘッダーの形式) ですが、診断ヘッダーは診断 ID に関する説明を提供します。 レポートには、レポートコンポーネントによって知られる重要なトラブルシューティングの詳細が含まれていることもあります。 例:
  
- エラーを生成した PSTN ゲートウェイによって提供された原因コード。発信通話が PSTN ネットワークで失敗すると、ISDN User Part (ISUP) の原因コードが自動的に生成されます。たとえば、PSTN ゲートウェイは原因コード 34 を送信して、通話を完了するための使用可能な回線またはチャネルが存在しないことを示す場合があります。
    
- 接続エラーのピアの FQDN、ポート、および Winsock エラー。
    
- DNS 解決エラーで検索されている名前。DNS 解決は、クライアントがネーム サーバーに問い合わせ、指定されたデバイス名に対応する IP アドレスを要求するときにいつでも実行されます。
    
## <a name="accessing-the-diagnostic-report"></a>診断レポートへのアクセス

診断レポートには、Skype for Business Server または会議詳細レポートの[ピアツーピアセッション詳細レポート](peer-to-peer-session-detail-report.md)で [診断レポート (詳細)] 指標をクリックするとアクセスできます。
  
## <a name="filters"></a>フィルター

なし。診断レポートにフィルターを適用することはできません。
  
## <a name="metrics"></a>指標

次の表に、診断レポートで提供されるセッションごとの情報を示します。
  
**診断レポートの指標**

|**名前**|**この項目での並べ替え**|**説明**|
|:-----|:-----|:-----|
|**レポート時刻** <br/> |いいえ  <br/> |レポートが記録された日時。  <br/> |
|**応答コード** <br/> |いいえ  <br/> |セッションが失敗したときに送信された SIP 応答コード。  <br/> |
|**要求の種類** <br/> |いいえ  <br/> |失敗した SIP 要求の種類 (INVITE、BYE、SERVICE など)。  <br/> |
|**Source** <br/> |いいえ  <br/> |エラーのソース。  <br/> |
|**送信元ユーザー URI** <br/> |いいえ  <br/> |セッションを開始したユーザーの SIP アドレス。  <br/> |
|**送信元ユーザー エージェント** <br/> |いいえ  <br/> |セッションを開始したユーザーのエンドポイントで使用されているソフトウェア。  <br/> |
|**診断 ID** <br/> |いいえ  <br/> |エラーのトラブルシューティングに役立つ情報を得られることが多い、SIP メッセージに添付された一意の識別子です (ms-diagnostics ヘッダーの形式)。  <br/> |
|**コンテンツの種類** <br/> |いいえ  <br/> |失敗したメディア コンテンツの種類。たとえば、よく使われるコンテンツの種類は Application/sdp です。セッション記述プロトコル (SDP) は、セッションのアナウンス、セッションの招待、その他のマルチメディア セッション開始形式で使われる標準インターネット プロトコルです。  <br/> |
|**Application** <br/> |いいえ  <br/> |エラーに関係するアプリケーション。  <br/> |
|**送信先ユーザー URI** <br/> |いいえ  <br/> |セッションに招待されたユーザーの SIP アドレス。  <br/> |
|**会議参加時間 (ミリ秒)** <br/> |いいえ  <br/> |ユーザーが会議に参加するのにかかった時間 (ミリ秒)。  <br/> |
|**診断ヘッダー** <br/> |いいえ  <br/> |診断 ID の説明。  <br/> |
   
診断エラーの一覧については、「 [Ms Diagnostics Header」ページ](https://msdn.microsoft.com/library/gg132446%28v=office.12%29.aspx)を参照してください。
  

