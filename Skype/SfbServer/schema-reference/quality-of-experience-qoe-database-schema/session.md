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
description: 各レコードは、オーディオまたはオーディオとビデオを含む 1 つのセッションを表します。 セッションに関する全体的な情報が含まれている。 セッションは、2 つのエンドポイント間の音声またはビデオのセッション開始プロトコル (SIP) ダイアログとして定義されます。
ms.openlocfilehash: cdf639e7360248e02378c66eb68a60d49acb9749
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802677"
---
# <a name="session-table"></a>セッション テーブル
 
各レコードは、オーディオまたはオーディオとビデオを含む 1 つのセッションを表します。 セッションに関する全体的な情報が含まれる。 セッションは、2 つのエンドポイント間の音声またはビデオのセッション開始プロトコル (SIP) ダイアログとして定義されます。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |日付型  <br/> |Primary  <br/> |ダイアログ テーブル [から参照されます](dialog.md)。  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |ダイアログ テーブル [から参照されます](dialog.md)。  <br/> |
|**ConferenceKey** <br/> |int  <br/> |外部  <br/> |電話会議キー。 会議テーブル [から参照されます](conference.md)。  <br/> |
|**CorrelationKey** <br/> |int  <br/> |外部  <br/> |関連付けキー。 [SessionCorrelation テーブルから参照されます](sessioncorrelation.md)。  <br/> |
|**DialogCategory** <br/> |bit  <br/> | <br/> |ダイアログ カテゴリ0 は Skype for Business Server から仲介サーバーレグです。1 は仲介サーバーから PSTN ゲートウェイレグです。  <br/> |
|**MediationServerBypassFlag** <br/> |bit  <br/> ||通話がバイパスされたかどうかを示すフラグ。  <br/> |
|**MediaBypassWarningFlag** <br/> |int  <br/> ||このフィールドは、(存在する場合) バイパス ID が一致したのに通話がバイパスされなかった理由を示します。 Skype for Business Server の場合、定義される値は 1 つのみです。  <br/> 0x0001 - 既定のネットワーク アダプターの不明なバイパス ID。  <br/> |
|**StartTime** <br/> |日付型  <br/> | <br/> |通話の開始時刻。  <br/> |
|**EndTime** <br/> |日付型  <br/> | <br/> |通話の終了時刻。  <br/> |
|**CallerPool** <br/> |int  <br/> |外部  <br/> |発信者のプール。 Pool テーブル [から参照されます](pool.md)。  <br/> |
|**CalleePool** <br/> |int  <br/> |外部  <br/> |通話レシーバーのプール。 Pool テーブル [から参照されます](pool.md)。  <br/> |
|**CalleePAI** <br/> |int  <br/> |外部  <br/> |受信側エンドポイントの SIP p アサート ID (PAI) 内の SIP URI。 ユーザー テーブル [から参照されます](user-0.md)。  <br/> |
|**CallerURI** <br/> |int  <br/> |外部  <br/> |発信者の URI。 ユーザー テーブル [から参照されます](user-0.md)。  <br/> |
|**CallerEndpoint** <br/> |int  <br/> |外部  <br/> |発信者のエンドポイント。 Endpoint テーブル [から参照されます](endpoint.md)。  <br/> |
|**CallerUserAgent** <br/> |bit  <br/> |外部  <br/> |発信者のユーザー エージェント。 [UserAgent テーブルから参照されます](useragent.md)。  <br/> |
|**CallPriority** <br/> |smallint  <br/> ||この呼び出しの優先度。  <br/> |
|**ClassifiedPoorCall** <br/> |bit  <br/> ||この列は廃止され、Skype for Business Server では使用されません。 代わりに、この情報はメディアラインベースごとに報告されます。 詳細については [、MediaLine の表](medialine-0.md) を参照してください。 <br/> |
|**CallerPAI** <br/> |int  <br/> |外部  <br/> |呼び出しを行ったユーザーの P-Asserted-Identity。 P-Asserted-Identity (PAI) は、通話を行ったユーザーの正しい ID を伝えるために使用されます。  <br/> |
|**CalleeEndpoint** <br/> |int  <br/> |外部  <br/> |通話を受信したエンドポイント。  <br/> |
|**CalleeUserAgent** <br/> |int  <br/> |外部  <br/> |通話を受信したユーザーが使用するユーザー エージェント。 ユーザー エージェントは、クライアント エンドポイント デバイスを表します。  <br/> |
|**CalleeUri** <br/> |int  <br/> |外部  <br/> |通話を受信したユーザーの SIP URI。  <br/> |
   

