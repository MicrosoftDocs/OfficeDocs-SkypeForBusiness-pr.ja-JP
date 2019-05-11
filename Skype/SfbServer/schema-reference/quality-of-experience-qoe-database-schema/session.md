---
title: Session テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7f05529c-794d-41ed-bca4-2e85b87b2dec
description: 各レコードは、オーディオまたはオーディオとビデオでは、1 つのセッションを表します。 セッションに関する全体的な情報が含まれています。 セッションは、2 つのエンドポイント間でオーディオまたはビデオのセッション開始プロトコル (SIP) ダイアログとして定義されます。
ms.openlocfilehash: 8aff8bb8be8366fe2e81e4d649d62562e899aab9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33897156"
---
# <a name="session-table"></a>Session テーブル
 
各レコードは、オーディオまたはオーディオとビデオでは、1 つのセッションを表します。 セッションに関する全体的な情報が含まれています。 セッションは、2 つのエンドポイント間でオーディオまたはビデオのセッション開始プロトコル (SIP) ダイアログとして定義されます。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |[ダイアログ テーブル](dialog.md)から参照されています。  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |[ダイアログ テーブル](dialog.md)から参照されています。  <br/> |
|**ConferenceKey** <br/> |int  <br/> |外部  <br/> |会議のキーです。 [会議の表](conference.md)から参照されています。  <br/> |
|**CorrelationKey** <br/> |int  <br/> |外部  <br/> |相関関係キーです。 [SessionCorrelation テーブル](sessioncorrelation.md)から参照されています。  <br/> |
|**DialogCategory** <br/> |bit  <br/> | <br/> |ダイアログのカテゴリです。0 は Skype ビジネス サーバーの仲介サーバーのレグです。1 では、仲介サーバー PSTN ゲートウェイ レグを飛行します。  <br/> |
|**MediationServerBypassFlag** <br/> |bit  <br/> ||場合に呼び出しをバイパスしないかを示すフラグを設定します。  <br/> |
|**MediaBypassWarningFlag** <br/> |int  <br/> ||このフィールドでは、存在する場合、呼び出しをバイパス Id が一致した場合でもバイパスしない理由を示します。 ビジネス サーバーの Skype は、1 つの値が定義されています。  <br/> 0x0001 - 既定のネットワーク アダプターの ID を不明なバイパスします。  <br/> |
|**StartTime** <br/> |datetime  <br/> | <br/> |開始時刻を呼び出します。  <br/> |
|**EndTime** <br/> |datetime  <br/> | <br/> |終了時刻を呼び出します。  <br/> |
|**CallerPool** <br/> |int  <br/> |外部  <br/> |呼び出し元のプールです。 [プール テーブル](pool.md)から参照されています。  <br/> |
|**CalleePool** <br/> |int  <br/> |外部  <br/> |電話の受信側のプールです。 [プール テーブル](pool.md)から参照されています。  <br/> |
|**CalleePAI** <br/> |int  <br/> |外部  <br/> |SIP p アサート (PAI) の id、受信側のエンドポイントでの SIP URI です。 [ユーザー テーブル](user-0.md)から参照されています。  <br/> |
|**CallerURI** <br/> |int  <br/> |外部  <br/> |呼び出し元の URI。 [ユーザー テーブル](user-0.md)から参照されています。  <br/> |
|**CallerEndpoint** <br/> |int  <br/> |外部  <br/> |呼び出し元のエンドポイントです。 [エンドポイントのテーブル](endpoint.md)から参照されています。  <br/> |
|**CallerUserAgent** <br/> |bit  <br/> |外部  <br/> |呼び出し元のユーザー エージェント。 [UserAgent テーブル](useragent.md)から参照されています。  <br/> |
|**CallPriority** <br/> |smallint  <br/> ||この呼び出しの優先順位です。  <br/> |
|**ClassifiedPoorCall** <br/> |bit  <br/> ||このコラムでは、推奨されていませんし、ビジネスのサーバーに、Skype で使用されていません。 代わりに、メディアごとの行ベースでこの情報が報告されます。 詳細については、 [MediaLine テーブル](medialine-0.md)を参照してください。 <br/> |
|**CallerPAI** <br/> |int  <br/> |外部  <br/> |P-アサート - ユーザーの Id の呼び出しを配置します。 P アサートされた Id (PAI) は、呼び出しを配置しているユーザーの実際の識別情報を伝えるために使用されます。  <br/> |
|**CalleeEndpoint** <br/> |int  <br/> |外部  <br/> |呼び出しを受信するエンドポイントです。  <br/> |
|**CalleeUserAgent** <br/> |int  <br/> |外部  <br/> |ユーザー エージェント ユーザーによって使用されますが、呼び出しを受信しました。 ユーザー エージェントは、クライアントのエンドポイント デバイスを表します。  <br/> |
|**CalleeUri** <br/> |int  <br/> |外部  <br/> |呼び出しを受信したユーザーの SIP URI です。  <br/> |
   

