---
title: セッション テーブル
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7f05529c-794d-41ed-bca4-2e85b87b2dec
description: 各レコードは、オーディオまたはオーディオとビデオを含む 1 つのセッションを表します。 セッションに関する全体的な情報が含まれる。 セッションは、2 つのエンドポイント間の音声またはビデオセッション開始プロトコル (SIP) ダイアログとして定義されます。
ms.openlocfilehash: 749f151def046abdb5169b39ccbd81ea5f07f5d4ee3d1c971ac112a2d4b90cce
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54340033"
---
# <a name="session-table"></a>セッション テーブル
 
各レコードは、オーディオまたはオーディオとビデオを含む 1 つのセッションを表します。 セッションに関する全体的な情報が含まれる。 セッションは、2 つのエンドポイント間の音声またはビデオセッション開始プロトコル (SIP) ダイアログとして定義されます。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |日付型  <br/> |Primary  <br/> |Dialog テーブル [から参照されます](dialog.md)。  <br/> |
|**SessionSeq** <br/> |整数  <br/> |Primary  <br/> |Dialog テーブル [から参照されます](dialog.md)。  <br/> |
|**ConferenceKey** <br/> |整数  <br/> |外部  <br/> |会議キー。 会議テーブル [から参照されます](conference.md)。  <br/> |
|**CorrelationKey** <br/> |整数  <br/> |外部  <br/> |関連付けキー。 [SessionCorrelation テーブルから参照されます](sessioncorrelation.md)。  <br/> |
|**DialogCategory** <br/> |ビット  <br/> | <br/> |ダイアログ カテゴリ。0 は仲介Skype for Business Serverに対して実行されます。1 は仲介サーバーから PSTN ゲートウェイのレッグです。  <br/> |
|**MediationServerBypassFlag** <br/> |ビット  <br/> ||通話がバイパスされたかどうかを示すフラグ。  <br/> |
|**MediaBypassWarningFlag** <br/> |整数  <br/> ||このフィールドは、(存在する場合) バイパス ID が一致したのに通話がバイパスされなかった理由を示します。 このSkype for Business Server、1 つの値だけが定義されます。  <br/> 0x0001 - 既定のネットワーク アダプターの不明なバイパス ID。  <br/> |
|**StartTime** <br/> |日付型  <br/> | <br/> |通話の開始時刻。  <br/> |
|**EndTime** <br/> |日付型  <br/> | <br/> |通話の終了時刻。  <br/> |
|**CallerPool** <br/> |整数  <br/> |外部  <br/> |呼び出し元のプール。 Pool テーブル [から参照されます](pool.md)。  <br/> |
|**CalleePool** <br/> |整数  <br/> |外部  <br/> |通話レシーバーのプール。 Pool テーブル [から参照されます](pool.md)。  <br/> |
|**CalleePAI** <br/> |整数  <br/> |外部  <br/> |受信エンドポイントの SIP p アサート ID (PAI) の SIP URI。 User テーブル [から参照されます](user-0.md)。  <br/> |
|**CallerURI** <br/> |整数  <br/> |外部  <br/> |呼び出し元の URI。 User テーブル [から参照されます](user-0.md)。  <br/> |
|**CallerEndpoint** <br/> |整数  <br/> |外部  <br/> |呼び出し元のエンドポイント。 Endpoint テーブル [から参照されます](endpoint.md)。  <br/> |
|**CallerUserAgent** <br/> |ビット  <br/> |外部  <br/> |発信者のユーザー エージェント。 [UserAgent テーブルから参照されます](useragent.md)。  <br/> |
|**CallPriority** <br/> |smallint  <br/> ||この呼び出しの優先度。  <br/> |
|**ClassifiedPoorCall** <br/> |ビット  <br/> ||この列は非推奨であり、この列では使用Skype for Business Server。 代わりに、この情報はメディアごとの回線ベースで報告されます。 詳細については [、MediaLine テーブル](medialine-0.md) を参照してください。 <br/> |
|**CallerPAI** <br/> |整数  <br/> |外部  <br/> |呼び出しを行ったユーザーの P-Asserted-Identity。 P-Asserted-Identity (PAI) は、呼び出しを行ったユーザーの真の ID を伝えるために使用されます。  <br/> |
|**CalleeEndpoint** <br/> |整数  <br/> |外部  <br/> |呼び出しを受信したエンドポイント。  <br/> |
|**CalleeUserAgent** <br/> |整数  <br/> |外部  <br/> |呼び出しを受信したユーザーが使用するユーザー エージェント。 ユーザー エージェントは、クライアント エンドポイント デバイスを表します。  <br/> |
|**CalleeUri** <br/> |整数  <br/> |外部  <br/> |呼び出しを受信したユーザーの SIP URI。  <br/> |
   

