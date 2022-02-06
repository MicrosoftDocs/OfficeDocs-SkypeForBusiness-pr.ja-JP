---
title: ErrorReport ビュー
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: ca873f7e-b18b-4eaf-8db0-5f9d5a9b60a1
description: ErrorReport ビューには、報告されたエラーに関する情報が格納されます。 各レコードは 1 つのエラー発生です。 このエラーは、フロントエンド サーバーで実行されている CDR エージェントによってキャプチャされます。またはクライアントから送信されます。 このビューは、Microsoft Lync Server 2013 で導入されました。
---

# <a name="errorreport-view"></a>ErrorReport ビュー
 
ErrorReport ビューには、報告されたエラーに関する情報が格納されます。 各レコードは 1 つのエラー発生です。 このエラーは、フロントエンド サーバーで実行されている CDR エージェントによってキャプチャされます。またはクライアントから送信されます。 このビューは、Microsoft Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**詳細**|
|:-----|:-----|:-----|
|**ErrorTime** <br/> |日付型  <br/> |エラーが発生した時刻。エラー を一意に識別するために ErrorReportSeq と併用されます。  <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |エラーを識別する ID 番号。エラーを一意に識別するために ErrorTime と併用されます。  <br/> |
|**MsDiagId** <br/> |int  <br/> |エラー レポートの診断 ID。  <br/> |
|**FromUri** <br/> |nvarchar(450)  <br/> |エラーを発生したユーザーの URI。  <br/> |
|**FromUriType** <br/> |nvarchar(256)  <br/> |エラーを発生したユーザーの URI の種類。 詳細については [、UriTypes テーブル](uritypes.md) を参照してください。 <br/> |
|**FromTenant** <br/> |nvarchar(256)  <br/> |エラーを発生したユーザーのテナント。 詳細については [、「Tenants」テーブル](tenants.md) を参照してください。 <br/> |
|**ToUri** <br/> |nvarchar(450)  <br/> |エラー レポートのターゲットだったユーザーの URI。  <br/> |
|**ToUriType** <br/> |nvarchar(256)  <br/> |エラー レポートの対象となるユーザーの URI の種類。 詳細については、「UriTypes Table」を参照してください。  <br/> |
|**ToTenant** <br/> |nvarchar(256)  <br/> |エラー レポートの対象となるユーザーのテナント。 詳細については [、「Tenants」テーブル](tenants.md) を参照してください。 <br/> |
|**ConferenceUri** <br/> |nvarchar(450)  <br/> |エラー レポートの対象だった会議の URI。  <br/> |
|**ConferenceUriType** <br/> |nvarchar(256)  <br/> |エラー レポートのターゲットだった会議の URI の種類。 詳細については [、UriTypes テーブル](uritypes.md) を参照してください。 <br/> |
|**SessionIdTime** <br/> |日付型  <br/> |エラー レポートを発生したセッション要求の時刻。 セッションを一意に識別するために SessionIdSeq と組み合わせて使用されます。 詳細については[、2015 Skype for Business Serverの](dialogs.md) Dialogs テーブルを参照してください。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |エラー レポートを発生したセッション要求を識別する ID 番号。 セッションを一意に識別するために SessionIdTime と組み合わせて使用されます。 詳細については[、2015 Skype for Business Serverの](dialogs.md) Dialogs テーブルを参照してください。 <br/> |
|**DialogId** <br/> |varstring(775)  <br/> |エラーが発生したセッションの SIP ダイアログ ID。 形式は次のとおりです。  <br/> dialog;from-tag;to-tag  <br/> このデータは、次の構文を使用してテキスト形式に変換できます。  <br/> cast(cast(ExternalId as varbinary(max)) as varchar(max))  <br/> |
|**ClientVersion** <br/> |nvarchar(256)  <br/> |エラーを発生したユーザーが使用するクライアントのバージョン。  <br/> |
|**ClientType** <br/> |int  <br/> |エラーを発生したユーザーが使用するクライアント。 詳細については [、UserAgentDef の表](useragentdef.md) を参照してください。 <br/> |
|**ClientCategory** <br/> |nvarchar(64)  <br/> |エラーを発生したユーザーが使用するクライアントのカテゴリの名前。  <br/> |
|**Source** <br/> |nvarchar(256)  <br/> |エラーを発生させたサーバーの名前 (サーバー コンポーネントからレポートが送信された場合)。  <br/> |
|**Application** <br/> |nvarchar(256)  <br/> |エラーを発生させたアプリケーションの名前 (サーバー コンポーネントからレポートが送信された場合)。  <br/> |
|**ResponseCode** <br/> |int  <br/> |エラー レポートを含む SIP メッセージのセッションに対する SIP 応答コード。  <br/> |
|**RequestType** <br/> |varchar(max)  <br/> |失敗した要求の種類。  <br/> |
|**ContentType** <br/> |varchar(max)  <br/> |失敗した要求のコンテンツ タイプ。  <br/> |
|**CallType** <br/> |nvarchar(256)  <br/> |セッションの種類。 詳細については[、2015 Skype for Business Serverの CallType](calltype.md) テーブルを参照してください。 <br/> |
|**TelemetryId** <br/> |uniqueidentifier  <br/> |会議に関するさまざまなコンポーネントの参加時間情報に関係する一意の識別子。  <br/> |
|**SetupTime** <br/> |int  <br/> |特定のコンポーネントが会議に参加するのに必要な時間 (ミリ秒)。  <br/> |
|**IsCapturedByServer** <br/> |ビット  <br/> |エラー レポートがフロントエンド サーバーで実行されている CDR エージェントによってキャプチャされたのか、クライアントによって送信されたのかを示します。  <br/> |
|**Flag** <br/> |smallint  <br/> |将来使用するために予約されています。  <br/> |
|**MsDiagHeader** <br/> |varchar(max)  <br/> |エラーに関する追加情報。  <br/> |
|**FrontEnd** <br/> |nvarchar  <br/> |レポートを送信したフロントエンド サーバーの完全修飾ドメイン名。  <br/> |
|**Pool** <br/> |nvarchar  <br/> |レポートを送信したフロントエンド サーバーを含むプールの完全修飾ドメイン名。  <br/> |
   

