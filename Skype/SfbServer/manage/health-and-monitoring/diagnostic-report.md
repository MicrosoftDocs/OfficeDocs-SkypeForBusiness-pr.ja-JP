---
title: '[診断レポート] Skype for Business Server'
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b389dbd9-f2e8-4184-93d0-2e504796ac16
description: '概要: [診断レポート] の詳細については、「Skype for Business Server。'
ms.openlocfilehash: 9ab417619828f4c48695ce19d68a5d1bc0f91171
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62397781"
---
# <a name="diagnostic-report-in-skype-for-business-server"></a>[診断レポート] Skype for Business Server
 
**概要:**[診断レポート] の詳細については、「Skype for Business Server。
  
診断レポートは、失敗したセッションの診断およびトラブルシューティング情報を提供します。 この情報には、セッションが失敗した場合に報告された診断 ID と診断ヘッダーの両方が含まれます。 診断 ID は SIP メッセージに接続される一意の識別子 (ms-diagnostics ヘッダーの形式) ですが、診断ヘッダーには診断 ID の説明が付属しています。 レポートには、レポート コンポーネントで知られている貴重なトラブルシューティングの詳細が含まれている場合があります。 次に例を示します。
  
- エラーを生成した PSTN ゲートウェイによって提供された原因コード。発信通話が PSTN ネットワークで失敗すると、ISDN User Part (ISUP) の原因コードが自動的に生成されます。たとえば、PSTN ゲートウェイは原因コード 34 を送信して、通話を完了するための使用可能な回線またはチャネルが存在しないことを示す場合があります。
    
- 接続エラーのピアの FQDN、ポート、および Winsock エラー。
    
- DNS 解決エラーで検索されている名前。DNS 解決は、クライアントがネーム サーバーに問い合わせ、指定されたデバイス名に対応する IP アドレスを要求するときにいつでも実行されます。
    
## <a name="accessing-the-diagnostic-report"></a>診断レポートへのアクセス

診断レポートにアクセスするには、Skype for Business Server のピアツーピア セッション詳細レポートまたは会議詳細レポートの診断[](peer-to-peer-session-detail-report.md)レポート (詳細) メトリックをクリックします。
  
## <a name="filters"></a>フィルター

なし。診断レポートにフィルターを適用することはできません。
  
## <a name="metrics"></a>指標

次の表に、診断レポートで提供されるセッションごとの情報を示します。
  
**診断レポートの指標**

|**名前**|**このアイテムを並べ替えることはできますか?**|**説明**|
|:-----|:-----|:-----|
|**レポート時刻** <br/> |不要  <br/> |レポートが記録された日時。  <br/> |
|**応答コード** <br/> |不要  <br/> |セッションが失敗したときに送信された SIP 応答コード。  <br/> |
|**要求の種類** <br/> |不要  <br/> |失敗した SIP 要求の種類 (INVITE、BYE、SERVICE など)。  <br/> |
|**Source** <br/> |不要  <br/> |エラーのソース。  <br/> |
|**送信元ユーザー URI** <br/> |不要  <br/> |セッションを開始したユーザーの SIP アドレス。  <br/> |
|**送信元ユーザー エージェント** <br/> |不要  <br/> |セッションを開始したユーザーのエンドポイントで使用されているソフトウェア。  <br/> |
|[**診断 ID**] <br/> |いいえ  <br/> |エラーのトラブルシューティングに役立つ情報を得られることが多い、SIP メッセージに添付された一意の識別子です (ms-diagnostics ヘッダーの形式)。  <br/> |
|**コンテンツの種類** <br/> |不要  <br/> |失敗したメディア コンテンツの種類。たとえば、よく使われるコンテンツの種類は Application/sdp です。セッション記述プロトコル (SDP) は、セッションのアナウンス、セッションの招待、その他のマルチメディア セッション開始形式で使われる標準インターネット プロトコルです。  <br/> |
|**Application** <br/> |不要  <br/> |エラーに関係するアプリケーション。  <br/> |
|**送信先ユーザー URI** <br/> |不要  <br/> |セッションに招待されたユーザーの SIP アドレス。  <br/> |
|**会議参加時間 (ミリ秒)** <br/> |不要  <br/> |ユーザーが会議に参加するのにかかった時間 (ミリ秒)。  <br/> |
|**診断ヘッダー** <br/> |不要  <br/> |診断 ID の説明。  <br/> |
   
診断エラーの一覧は、[ [Ms-Diagnostics Header] ページに表示されます](/openspecs/office_protocols/ms-ocer/f6787b39-0842-43ca-94a2-6afadda5f0a3)。
