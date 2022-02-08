---
title: セッション テーブル
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 7f05529c-794d-41ed-bca4-2e85b87b2dec
description: 各レコードは、オーディオまたはオーディオとビデオを含む 1 つのセッションを表します。 セッションに関する全体的な情報が含まれる。 セッションは、2 つのエンドポイント間の音声またはビデオセッション開始プロトコル (SIP) ダイアログとして定義されます。
ms.openlocfilehash: 6e69ca38a0338075975919f087c066f683fcfb87
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62394616"
---
# <a name="session-table"></a>セッション テーブル
 
各レコードは、オーディオまたはオーディオとビデオを含む 1 つのセッションを表します。 セッションに関する全体的な情報が含まれる。 セッションは、2 つのエンドポイント間の音声またはビデオセッション開始プロトコル (SIP) ダイアログとして定義されます。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |日付型  <br/> |Primary  <br/> |Dialog テーブル [から参照されます](dialog.md)。  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |Dialog テーブル [から参照されます](dialog.md)。  <br/> |
|**ConferenceKey** <br/> |int  <br/> |外部  <br/> |会議キー。 会議テーブル [から参照されます](conference.md)。  <br/> |
|**CorrelationKey** <br/> |int  <br/> |外部  <br/> |関連付けキー。 [SessionCorrelation テーブルから参照されます](sessioncorrelation.md)。  <br/> |
|**DialogCategory** <br/> |ビット  <br/> | <br/> |ダイアログ カテゴリ。0 は仲介Skype for Business Serverに使用されます。1 は仲介サーバーから PSTN ゲートウェイのレッグです。  <br/> |
|**MediationServerBypassFlag** <br/> |ビット  <br/> ||通話がバイパスされたかどうかを示すフラグ。  <br/> |
|**MediaBypassWarningFlag** <br/> |int  <br/> ||このフィールドは、(存在する場合) バイパス ID が一致したのに通話がバイパスされなかった理由を示します。 このSkype for Business Server、1 つの値だけが定義されます。  <br/> 0x0001 - 既定のネットワーク アダプターの不明なバイパス ID。  <br/> |
|**StartTime** <br/> |日付型  <br/> | <br/> |通話の開始時刻。  <br/> |
|**EndTime** <br/> |日付型  <br/> | <br/> |通話の終了時刻。  <br/> |
|**CallerPool** <br/> |int  <br/> |外部  <br/> |呼び出し元のプール。 Pool テーブル [から参照されます](pool.md)。  <br/> |
|**CalleePool** <br/> |int  <br/> |外部  <br/> |通話レシーバーのプール。 Pool テーブル [から参照されます](pool.md)。  <br/> |
|**CalleePAI** <br/> |int  <br/> |外部  <br/> |受信エンドポイントの SIP p アサート ID (PAI) の SIP URI。 User テーブル [から参照されます](user-0.md)。  <br/> |
|**CallerURI** <br/> |int  <br/> |外部  <br/> |呼び出し元の URI。 User テーブル [から参照されます](user-0.md)。  <br/> |
|**CallerEndpoint** <br/> |int  <br/> |外部  <br/> |呼び出し元のエンドポイント。 Endpoint テーブル [から参照されます](endpoint.md)。  <br/> |
|**CallerUserAgent** <br/> |ビット  <br/> |外部  <br/> |発信者のユーザー エージェント。 [UserAgent テーブルから参照されます](useragent.md)。  <br/> |
|**CallPriority** <br/> |smallint  <br/> ||この呼び出しの優先度。  <br/> |
|**ClassifiedPoorCall** <br/> |ビット  <br/> ||この列は非推奨であり、この列では使用Skype for Business Server。 代わりに、この情報はメディアごとの回線ベースで報告されます。 詳細については [、MediaLine テーブル](medialine-0.md) を参照してください。 <br/> |
|**CallerPAI** <br/> |int  <br/> |外部  <br/> |呼び出しを行ったユーザーの P-Asserted-Identity。 P-Asserted-Identity (PAI) は、呼び出しを行ったユーザーの真の ID を伝えるために使用されます。  <br/> |
|**CalleeEndpoint** <br/> |int  <br/> |外部  <br/> |呼び出しを受信したエンドポイント。  <br/> |
|**CalleeUserAgent** <br/> |int  <br/> |外部  <br/> |呼び出しを受信したユーザーが使用するユーザー エージェント。 ユーザー エージェントは、クライアント エンドポイント デバイスを表します。  <br/> |
|**CalleeUri** <br/> |int  <br/> |外部  <br/> |呼び出しを受信したユーザーの SIP URI。  <br/> |
   

