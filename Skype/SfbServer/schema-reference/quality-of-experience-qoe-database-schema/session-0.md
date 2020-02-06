---
title: セッションビュー
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 49e33f5b-45d0-4146-a5a4-76954d895a98
description: セッションビューには、データベース内にレコードがあるセッションに関する情報が格納されます。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: cd304123022e0d4d921ecb1cd2599c636aaa9013
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805905"
---
# <a name="session-view"></a>セッションビュー
 
セッションビューには、データベース内にレコードがあるセッションに関する情報が格納されます。 このビューは、Microsoft Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**詳細**|
|:-----|:-----|:-----|
|ConferenceDateTime  <br/> |datetime  <br/> |MediaLine テーブルから参照されます。  <br/> |
|ConferenceURI  <br/> |nvarchar (450)  <br/> |会議の URI (会議の場合) または [この Id がピアツーピアセッションの場合] です。  <br/> |
|関連性  <br/> |varchar (max)  <br/> |セッションの関連付け ID。  <br/> |
|このカテゴリ  <br/> |bit  <br/> |ダイアログカテゴリ0は、Skype for Business Server と仲介サーバーの間の区間です。1は、PSTN ゲートウェイ区間への仲介サーバーです。  <br/> |
|MediationServerBypassFlag  <br/> |bit  <br/> |通話がバイパスされたかどうかを示します。  <br/> |
|Mediabypasswarnings フラグ  <br/> |int  <br/> |このフィールドは、バイパス Id が一致した場合でも、着信がバイパスされなかった理由を示します (存在する場合)。 Skype for Business Server では、1つの値のみが定義されます。  <br/> 0x0001-既定のネットワークアダプターの不明なバイパス ID  <br/> |
|StartTime  <br/> |datetime  <br/> |通話開始時刻。  <br/> |
|EndTime  <br/> |datetime  <br/> |通話終了時刻。  <br/> |
|CallerPool  <br/> |nvarchar(256)  <br/> |発信者番号プールの FQDN。  <br/> |
|CalleePool  <br/> |nvarchar(256)  <br/> |呼び出し元プールの FQDN。  <br/> |
|CallerPAI  <br/> |nvarchar (450)  <br/> |呼び出し元の p がアサートされた id URI。  <br/> |
|CalleePAI  <br/> |nvarchar (450)  <br/> |呼び出し先の p-アサートされた id URI。  <br/> |
|CallerEndpoint  <br/> |nvarchar(256)  <br/> |発信者のエンドポイント名。  <br/> |
|CalleeEndpoint  <br/> |nvarchar(256)  <br/> |発信者のエンドポイント名。  <br/> |
|CallerUserAgent  <br/> |nvarchar(256)  <br/> |呼び出し元のユーザーエージェント文字列。  <br/> |
|CallerUserAgentType  <br/> |smallint  <br/> |呼び出し元のユーザーエージェントの種類。 詳細については、 [UserAgent の表](useragent.md)を参照してください。 <br/> |
|CallerUserAgentCategory  <br/> |nvarchar (64)  <br/> |呼び出し元のユーザーエージェントのカテゴリ。 詳しくは、 [Useragentdef テーブル (QoE)](useragentdef-qoe.md)をご覧ください。 <br/> |
|CalleeUserAgent  <br/> |nvarchar(256)  <br/> |呼び出し先のユーザーエージェント文字列。  <br/> |
|CalleeUserAgentType  <br/> |smallint  <br/> |呼び出し先のユーザーエージェントの種類。 詳細については、 [UserAgent の表](useragent.md)を参照してください。 <br/> |
|CalleeUserAgentCategory  <br/> |nvarchar (64)  <br/> |呼び出し先のユーザーエージェントカテゴリ。 詳しくは、 [Useragentdef テーブル (QoE)](useragentdef-qoe.md)をご覧ください。 <br/> |
|CallerURI  <br/> |nvarchar (450)  <br/> |発信者の URI。  <br/> |
|CalleeURI  <br/> |nvarchar (450)  <br/> |呼び出し先の URI。  <br/> |
|通話  <br/> |int  <br/> |通話の優先度。  <br/> |
   

