---
title: ErrorReport ビュー
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ca873f7e-b18b-4eaf-8db0-5f9d5a9b60a1
description: ErrorReport ビューでは、報告されたエラーに関する情報を格納します。 各レコードは、1 つのエラーの発生です。 エラーは、フロント エンド サーバーで実行されている CDR エージェントがいずれかの方法を取得またはクライアントから送信されます。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 8d72ad73b5894e73b7d95b1b11bc10dffcabc5f7
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874180"
---
# <a name="errorreport-view"></a>ErrorReport ビュー
 
ErrorReport ビューでは、報告されたエラーに関する情報を格納します。 各レコードは、1 つのエラーの発生です。 エラーは、フロント エンド サーバーで実行されている CDR エージェントがいずれかの方法を取得またはクライアントから送信されます。 このビューは、Microsoft Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**詳細**|
|:-----|:-----|:-----|
|**ErrorTime** <br/> |datetime  <br/> |時間のエラーが発生しました。 エラーを一意に識別するのには ErrorReportSeq と組み合わせてを使用します。  <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |エラーを識別する ID 番号。 エラーを一意に識別するのには ErrorTime と組み合わせてを使用します。  <br/> |
|**MsDiagId** <br/> |int  <br/> |エラー レポートの診断 ID。  <br/> |
|**FromUri** <br/> |nvarchar(450)  <br/> |エラーが発生したユーザーの URI。  <br/> |
|**FromUriType** <br/> |nvarchar(256)  <br/> |エラーが発生したユーザーの URI の種類です。 詳細については、 [UriTypes テーブル](uritypes.md)を参照してください。 <br/> |
|**FromTenant** <br/> |nvarchar(256)  <br/> |エラーを開始したユーザーのテナントです。 詳細については[テナントのテーブル](tenants.md)を参照してください。 <br/> |
|**ToUri** <br/> |nvarchar(450)  <br/> |エラー報告のターゲット ユーザーの URI。  <br/> |
|**ToUriType** <br/> |nvarchar(256)  <br/> |ターゲット ユーザーの URI の種類のエラー報告します。 詳細については UriTypes 表を参照してください。  <br/> |
|**ToTenant** <br/> |nvarchar(256)  <br/> |テナントを対象としたユーザーのエラー報告の。 詳細については[テナントのテーブル](tenants.md)を参照してください。 <br/> |
|**ConferenceUri** <br/> |nvarchar(450)  <br/> |エラー報告の対象にされた会議の URI。  <br/> |
|**ConferenceUriType** <br/> |nvarchar(256)  <br/> |エラー報告の対象にされた会議の URI タイプです。 詳細については、 [UriTypes テーブル](uritypes.md)を参照してください。 <br/> |
|**SessionIdTime** <br/> |datetime  <br/> |エラー レポートを生成したセッションの要求の時間です。 セッションを一意に識別するのには SessionIdSeq と組み合わせてを使用します。 [Skype のビジネス サーバー 2015 のテーブル」ダイアログ ボックス](dialogs.md)の詳細についてを参照してください。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |エラー レポートを生成したセッション要求を識別する ID 番号。 セッションを一意に識別するのには SessionIdTime と組み合わせてを使用します。 [Skype のビジネス サーバー 2015 のテーブル」ダイアログ ボックス](dialogs.md)の詳細についてを参照してください。 <br/> |
|**DialogId** <br/> |varstring(775)  <br/> |SIP ダイアログのセッションの ID、エラーが発生しました。 形式は次のとおりです。  <br/> ダイアログ; タグからタグに  <br/> このデータは、この構文を使用してテキスト形式に変換できます。  <br/> キャスト (cast (varchar(max)) と varbinary(max)) と ExternalId  <br/> |
|**ClientVersion** <br/> |nvarchar(256)  <br/> |エラーが発生したユーザーが使用するクライアントのバージョンです。  <br/> |
|**顧客タイプ** <br/> |int  <br/> |エラーを開始したユーザーによって使用されるクライアントです。 詳細については、 [UserAgentDef テーブル](useragentdef.md)を参照してください。 <br/> |
|**ClientCategory** <br/> |nvarchar(64)  <br/> |エラーが発生したユーザーが使用するクライアントのカテゴリの名前です。  <br/> |
|**ソース** <br/> |nvarchar(256)  <br/> |(レポートは、サーバー コンポーネントから送信された) 場合、エラーが発生したサーバーの名前です。  <br/> |
|**Application** <br/> |nvarchar(256)  <br/> |(レポートは、サーバー コンポーネントから送信された) 場合、エラーが発生したアプリケーションの名前です。  <br/> |
|**ResponseCode** <br/> |int  <br/> |エラー レポートが含まれている SIP メッセージのセッションに応答コードを SIP します。  <br/> |
|**修飾子の一覧** <br/> |は  <br/> |失敗した要求の種類です。  <br/> |
|**コンテンツ タイプ** <br/> |は  <br/> |失敗した要求のコンテンツ タイプ。  <br/> |
|**CallType** <br/> |nvarchar(256)  <br/> |セッションの種類。 [ビジネス サーバー 2015 の Skype の CallType テーブル](calltype.md)の詳細についてを参照してください。 <br/> |
|**TelemetryId** <br/> |一意識別子  <br/> |会議に関連するさまざまなコンポーネントの結合時の情報を関連付ける一意の識別子。  <br/> |
|**SetupTime** <br/> |int  <br/> |時間 (ミリ秒単位) の会議に参加するのには特定のコンポーネントが必要です。  <br/> |
|**IsCapturedByServer** <br/> |bit  <br/> |エラー レポートが、フロント エンド サーバーで実行されている CDR エージェントによってキャプチャされるか、クライアントによって送信されたかどうかを示します。  <br/> |
|**フラグ** <br/> |smallint  <br/> |将来使用するために予約されています。  <br/> |
|**MsDiagHeader** <br/> |は  <br/> |エラーに関する追加情報です。  <br/> |
|**FrontEnd** <br/> |nvarchar  <br/> |レポートを提出するフロント エンド サーバーの完全修飾ドメイン名です。  <br/> |
|**Pool** <br/> |nvarchar  <br/> |レポートを提出するフロント エンド サーバーを含むプールのドメイン名を完全修飾します。  <br/> |
   

