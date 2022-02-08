---
title: セッション ビュー
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 49e33f5b-45d0-4146-a5a4-76954d895a98
description: セッション ビューには、データベースにレコードがあるセッションに関する情報が保存されます。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: afcff6c5032c14dbcab525a0032804493bcb0216
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62393579"
---
# <a name="session-view"></a>セッション ビュー
 
セッション ビューには、データベースにレコードがあるセッションに関する情報が保存されます。 このビューは、Microsoft Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**詳細**|
|:-----|:-----|:-----|
|ConferenceDateTime  <br/> |日付型  <br/> |MediaLine テーブルから参照されます。  <br/> |
|ConferenceURI  <br/> |nvarchar(450)  <br/> |これが会議の場合は会議 URI、ピアツーピア セッションの場合は DialogID です。  <br/> |
|関連付け  <br/> |varchar(max)  <br/> |セッションの関連付け ID。  <br/> |
|DialogCategory  <br/> |ビット  <br/> |ダイアログ カテゴリ。0 は仲介Skype for Business Serverに使用されます。1 は仲介サーバーから PSTN ゲートウェイのレッグです。  <br/> |
|MediationServerBypassFlag  <br/> |ビット  <br/> |通話がバイパスされたかどうかを示します。  <br/> |
|MediaBypassWarningFlag  <br/> |int  <br/> |このフィールドは、(存在する場合) バイパス ID が一致したのに通話がバイパスされなかった理由を示します。 このSkype for Business Server、定義される値は 1 つのみです。  <br/> 0x0001 - 既定のネットワーク アダプターの不明なバイパス ID  <br/> |
|StartTime  <br/> |日付型  <br/> |通話の開始時刻。  <br/> |
|EndTime  <br/> |日付型  <br/> |通話の終了時刻。  <br/> |
|CallerPool  <br/> |nvarchar(256)  <br/> |発信者プールの FQDN。  <br/> |
|CalleePool  <br/> |nvarchar(256)  <br/> |呼び出し先プールの FQDN。  <br/> |
|CallerPAI  <br/> |nvarchar(450)  <br/> |発信者の p-asserted ID URI。  <br/> |
|CalleePAI  <br/> |nvarchar(450)  <br/> |呼び出し先の p アサート ID URI。  <br/> |
|CallerEndpoint  <br/> |nvarchar(256)  <br/> |呼び出し元のエンドポイント名。  <br/> |
|CalleeEndpoint  <br/> |nvarchar(256)  <br/> |呼び出し元のエンドポイント名。  <br/> |
|CallerUserAgent  <br/> |nvarchar(256)  <br/> |発信者のユーザー エージェント文字列。  <br/> |
|CallerUserAgentType  <br/> |smallint  <br/> |発信者のユーザー エージェントの種類。 詳細については [、UserAgent テーブル](useragent.md) を参照してください。 <br/> |
|CallerUserAgentCategory  <br/> |nvarchar (64)  <br/> |発信者のユーザー エージェントのカテゴリ。 詳細については [、UserAgentDef テーブル (QoE) を](useragentdef-qoe.md) 参照してください。 <br/> |
|CalleeUserAgent  <br/> |nvarchar(256)  <br/> |呼び出し先のユーザー エージェント文字列。  <br/> |
|CalleeUserAgentType  <br/> |smallint  <br/> |呼び出し先のユーザー エージェント タイプ。 詳細については [、UserAgent テーブル](useragent.md) を参照してください。 <br/> |
|CalleeUserAgentCategory  <br/> |nvarchar (64)  <br/> |呼び出し先のユーザー エージェントのカテゴリ。 詳細については [、UserAgentDef テーブル (QoE) を](useragentdef-qoe.md) 参照してください。 <br/> |
|CallerURI  <br/> |nvarchar(450)  <br/> |呼び出し元の URI。  <br/> |
|CalleeURI  <br/> |nvarchar(450)  <br/> |呼び出し先の URI。  <br/> |
|CallPrioirty  <br/> |int  <br/> |通話の優先順位。  <br/> |
   

