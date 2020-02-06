---
title: Session テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7f05529c-794d-41ed-bca4-2e85b87b2dec
description: 各レコードは、オーディオまたはオーディオとビデオを含む1つのセッションを表します。 セッションに関する全体的な情報が含まれています。 セッションは、2つのエンドポイント間のオーディオまたはビデオセッションの開始プロトコル (SIP) ダイアログとして定義されます。
ms.openlocfilehash: f48857f826a4e85519d7dc7d2942d48967df8b01
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805775"
---
# <a name="session-table"></a>Session テーブル
 
各レコードは、オーディオまたはオーディオとビデオを含む1つのセッションを表します。 セッションに関する全体的な情報が含まれています。 セッションは、2つのエンドポイント間のオーディオまたはビデオセッションの開始プロトコル (SIP) ダイアログとして定義されます。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |[ダイアログテーブル](dialog.md)から参照されます。  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |[ダイアログテーブル](dialog.md)から参照されます。  <br/> |
|**ConferenceKey** <br/> |int  <br/> |外部  <br/> |会議キー。 [会議テーブル](conference.md)から参照されます。  <br/> |
|**CorrelationKey** <br/> |int  <br/> |外部  <br/> |相関関係キー。 [Sessioncorrelation テーブル](sessioncorrelation.md)から参照されます。  <br/> |
|**このカテゴリ** <br/> |bit  <br/> | <br/> |ダイアログカテゴリ0は、Skype for Business Server と仲介サーバーの間の区間です。1は、PSTN ゲートウェイ区間への仲介サーバーです。  <br/> |
|**MediationServerBypassFlag** <br/> |bit  <br/> ||通話がバイパスされたかどうかを示すフラグ。  <br/> |
|**Mediabypasswarnings フラグ** <br/> |int  <br/> ||このフィールドは、バイパス Id が一致した場合でも、着信がバイパスされなかった理由を示します (存在する場合)。 Skype for Business Server の場合は、1つの値のみが定義されます。  <br/> 0x0001-既定のネットワークアダプターの不明なバイパス ID。  <br/> |
|**StartTime** <br/> |datetime  <br/> | <br/> |通話開始時刻。  <br/> |
|**EndTime** <br/> |datetime  <br/> | <br/> |通話終了時刻。  <br/> |
|**CallerPool** <br/> |int  <br/> |外部  <br/> |発信者のプール。 [プールテーブル](pool.md)から参照されている。  <br/> |
|**CalleePool** <br/> |int  <br/> |外部  <br/> |通話受信者のプール。 [プールテーブル](pool.md)から参照されている。  <br/> |
|**CalleePAI** <br/> |int  <br/> |外部  <br/> |受信エンドポイントの SIP p-アサートされた id (PAI) の SIP URI。 [ユーザーテーブル](user-0.md)から参照されている。  <br/> |
|**CallerURI** <br/> |int  <br/> |外部  <br/> |発信者の URI。 [ユーザーテーブル](user-0.md)から参照されている。  <br/> |
|**CallerEndpoint** <br/> |int  <br/> |外部  <br/> |発信者のエンドポイント。 [エンドポイントテーブル](endpoint.md)から参照されます。  <br/> |
|**CallerUserAgent** <br/> |bit  <br/> |外部  <br/> |発信者のユーザーエージェント。 [UserAgent テーブル](useragent.md)から参照されます。  <br/> |
|**CallPriority** <br/> |smallint  <br/> ||この通話の優先度。  <br/> |
|**ClassifiedPoorCall** <br/> |bit  <br/> ||この列は推奨されなくなりました。 Skype for Business Server では使用されません。 代わりに、この情報はメディアラインベースごとに報告されます。 詳細については、 [MediaLine の表](medialine-0.md)を参照してください。 <br/> |
|**CallerPAI** <br/> |int  <br/> |外部  <br/> |P-アサート済み-通話を発信したユーザーの Id です。 P がアサートされた Id (PAI) を使って、通話を発信したユーザーの実際の id を伝えます。  <br/> |
|**CalleeEndpoint** <br/> |int  <br/> |外部  <br/> |通話を受信したエンドポイント。  <br/> |
|**CalleeUserAgent** <br/> |int  <br/> |外部  <br/> |通話を受信したユーザーが採用したユーザーエージェント。 ユーザーエージェントは、クライアントエンドポイントデバイスを表します。  <br/> |
|**CalleeUri** <br/> |int  <br/> |外部  <br/> |通話を受信したユーザーの SIP URI。  <br/> |
   

