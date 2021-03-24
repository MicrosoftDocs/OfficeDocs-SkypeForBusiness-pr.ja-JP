---
title: Skype for Business Server の診断レポート
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
ms.assetid: b389dbd9-f2e8-4184-93d0-2e504796ac16
description: '概要: Skype for Business Server の診断レポートについて説明します。'
ms.openlocfilehash: b7739214cf176336e47a5d2e11b36b52ea87eca7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095241"
---
# <a name="diagnostic-report-in-skype-for-business-server"></a>Skype for Business Server の診断レポート
 
**概要:** Skype for Business Server の診断レポートについて説明します。
  
診断レポートは、失敗したセッションの診断およびトラブルシューティング情報を提供します。 この情報には、セッションが失敗した場合に報告された診断 ID と診断ヘッダーの両方が含まれます。 診断 ID は SIP メッセージに接続される一意の識別子 (ms-diagnostics ヘッダーの形式) ですが、診断ヘッダーには診断 ID の説明が付属しています。 レポートには、レポート コンポーネントで知られている貴重なトラブルシューティングの詳細が含まれている場合があります。 例:
  
- エラーを生成した PSTN ゲートウェイによって提供された原因コード。発信通話が PSTN ネットワークで失敗すると、ISDN User Part (ISUP) の原因コードが自動的に生成されます。たとえば、PSTN ゲートウェイは原因コード 34 を送信して、通話を完了するための使用可能な回線またはチャネルが存在しないことを示す場合があります。
    
- 接続エラーのピアの FQDN、ポート、および Winsock エラー。
    
- DNS 解決エラーで検索されている名前。DNS 解決は、クライアントがネーム サーバーに問い合わせ、指定されたデバイス名に対応する IP アドレスを要求するときにいつでも実行されます。
    
## <a name="accessing-the-diagnostic-report"></a>診断レポートへのアクセス

診断レポートにアクセスするには [、Skype for Business Server](peer-to-peer-session-detail-report.md) のピアツーピア セッション詳細レポートまたは会議詳細レポートの診断レポート (詳細) メトリックをクリックします。
  
## <a name="filters"></a>フィルター

なし。診断レポートにフィルターを適用することはできません。
  
## <a name="metrics"></a>指標

次の表に、診断レポートで提供されるセッションごとの情報を示します。
  
**診断レポートの指標**

|**名前**|**このアイテムを並べ替えることはできますか?**|**説明**|
|:-----|:-----|:-----|
|**レポート時刻** <br/> |いいえ  <br/> |レポートが記録された日時。  <br/> |
|**応答コード** <br/> |いいえ  <br/> |セッションが失敗したときに送信された SIP 応答コード。  <br/> |
|**要求の種類** <br/> |いいえ  <br/> |失敗した SIP 要求の種類 (INVITE、BYE、SERVICE など)。  <br/> |
|**Source** <br/> |いいえ  <br/> |エラーのソース。  <br/> |
|**送信元ユーザー URI** <br/> |いいえ  <br/> |セッションを開始したユーザーの SIP アドレス。  <br/> |
|**送信元ユーザー エージェント** <br/> |いいえ  <br/> |セッションを開始したユーザーのエンドポイントで使用されているソフトウェア。  <br/> |
|[**診断 ID**] <br/> |いいえ  <br/> |エラーのトラブルシューティングに役立つ情報を得られることが多い、SIP メッセージに添付された一意の識別子です (ms-diagnostics ヘッダーの形式)。  <br/> |
|**コンテンツの種類** <br/> |いいえ  <br/> |失敗したメディア コンテンツの種類。たとえば、よく使われるコンテンツの種類は Application/sdp です。セッション記述プロトコル (SDP) は、セッションのアナウンス、セッションの招待、その他のマルチメディア セッション開始形式で使われる標準インターネット プロトコルです。  <br/> |
|**アプリケーション** <br/> |いいえ  <br/> |エラーに関係するアプリケーション。  <br/> |
|**送信先ユーザー URI** <br/> |いいえ  <br/> |セッションに招待されたユーザーの SIP アドレス。  <br/> |
|**会議参加時間 (ミリ秒)** <br/> |いいえ  <br/> |ユーザーが会議に参加するのにかかった時間 (ミリ秒)。  <br/> |
|**診断ヘッダー** <br/> |いいえ  <br/> |診断 ID の説明。  <br/> |
   
診断エラーの一覧は [、[Ms-Diagnostics Header] ページに表示されます](/openspecs/office_protocols/ms-ocer/f6787b39-0842-43ca-94a2-6afadda5f0a3)。
