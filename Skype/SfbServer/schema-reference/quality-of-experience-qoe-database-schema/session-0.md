---
title: セッションの表示
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 49e33f5b-45d0-4146-a5a4-76954d895a98
description: セッション ビューは、データベースにレコードが存在しているセッションに関する情報を格納します。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: c72773b4ff87786ab5b4e73b67e89032dc393fa1
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30880222"
---
# <a name="session-view"></a>セッションの表示
 
セッション ビューは、データベースにレコードが存在しているセッションに関する情報を格納します。 このビューは、Microsoft Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**詳細**|
|:-----|:-----|:-----|
|ConferenceDateTime  <br/> |datetime  <br/> |MediaLine テーブルから参照されています。  <br/> |
|ConferenceURI  <br/> |nvarchar(450)  <br/> |会議 URI は、会議では、DialogID この場合は、ピア ツー ピア セッションです。  <br/> |
|相関関係  <br/> |は  <br/> |セッションの相関関係 ID です。  <br/> |
|DialogCategory  <br/> |bit  <br/> |ダイアログのカテゴリです。0 は Skype ビジネス サーバーの仲介サーバーのレグです。1 では、仲介サーバー PSTN ゲートウェイ レグを飛行します。  <br/> |
|MediationServerBypassFlag  <br/> |bit  <br/> |呼び出しをバイパスするかどうかを示します。  <br/> |
|MediaBypassWarningFlag  <br/> |int  <br/> |このフィールドでは、存在する場合、呼び出しをバイパス Id が一致した場合でもバイパスしない理由を示します。 ビジネス サーバーの Skype は、1 つの値が定義されます。  <br/> 0x0001 - 既定のネットワーク アダプターの ID を不明なバイパス  <br/> |
|StartTime  <br/> |datetime  <br/> |開始時刻を呼び出します。  <br/> |
|EndTime  <br/> |datetime  <br/> |終了時刻を呼び出します。  <br/> |
|CallerPool  <br/> |nvarchar(256)  <br/> |呼び出し元プールの FQDN です。  <br/> |
|CalleePool  <br/> |nvarchar(256)  <br/> |呼び出し先プールの FQDN です。  <br/> |
|CallerPAI  <br/> |nvarchar(450)  <br/> |呼び出し元の p がアサートされた id URI です。  <br/> |
|CalleePAI  <br/> |nvarchar(450)  <br/> |呼び出し先の p でアサートされたアイデンティティ URI です。  <br/> |
|CallerEndpoint  <br/> |nvarchar(256)  <br/> |呼び出し元のエンドポイントの名前です。  <br/> |
|CalleeEndpoint  <br/> |nvarchar(256)  <br/> |呼び出し元のエンドポイントの名前です。  <br/> |
|CallerUserAgent  <br/> |nvarchar(256)  <br/> |呼び出し元のユーザー エージェント文字列です。  <br/> |
|CallerUserAgentType  <br/> |smallint  <br/> |呼び出し元のユーザー エージェントの種類です。 [UserAgent テーブル](useragent.md)の詳細についてはを参照してください。 <br/> |
|CallerUserAgentCategory  <br/> |nvarchar (64)  <br/> |呼び出し元のユーザー エージェントのカテゴリです。 詳細については、 [UserAgentDef テーブル (QoE)](useragentdef-qoe.md)を参照してください。 <br/> |
|CalleeUserAgent  <br/> |nvarchar(256)  <br/> |呼び出し先のユーザー エージェント文字列です。  <br/> |
|CalleeUserAgentType  <br/> |smallint  <br/> |呼び出し先のユーザー エージェントの種類です。 [UserAgent テーブル](useragent.md)の詳細についてはを参照してください。 <br/> |
|CalleeUserAgentCategory  <br/> |nvarchar (64)  <br/> |呼び出し先のユーザー エージェントのカテゴリです。 詳細については、 [UserAgentDef テーブル (QoE)](useragentdef-qoe.md)を参照してください。 <br/> |
|CallerURI  <br/> |nvarchar(450)  <br/> |呼び出し元の URI。  <br/> |
|CalleeURI  <br/> |nvarchar(450)  <br/> |呼び出し先の URI。  <br/> |
|CallPrioirty  <br/> |int  <br/> |呼び出しの優先順位です。  <br/> |
   

