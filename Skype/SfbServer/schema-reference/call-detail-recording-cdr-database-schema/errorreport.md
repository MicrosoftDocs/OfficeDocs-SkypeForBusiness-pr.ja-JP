---
title: ErrorReport テーブル in Skype for Business Server 2015
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: ae0287b4-e8ca-4f8c-84ef-502897dcaa2a
description: ErrorReport テーブルには、発生したエラーに関する情報が格納されます。 各レコードは 1 つのエラー発生です。 このエラーは、フロントエンド サーバーで実行されている CDR エージェントによってキャプチャされます。またはクライアントから送信されます。
---

# <a name="errorreport-table-in-skype-for-business-server-2015"></a>ErrorReport テーブル in Skype for Business Server 2015
 
ErrorReport テーブルには、発生したエラーに関する情報が格納されます。 各レコードは 1 つのエラー発生です。 このエラーは、フロントエンド サーバーで実行されている CDR エージェントによってキャプチャされます。またはクライアントから送信されます。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**ErrorTime** <br/> |日付型  <br/> |Primary  <br/> |エラーが発生した日時。  <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |Primary  <br/> |エラー レポートを識別する ID 番号。 ErrorTime と組み合 **わせて使用して** 、エラー レポートを一意に識別します。 <br/> |
|**ErrorId** <br/> |int  <br/> |外部  <br/> |エラーの種類の一意の ID。 詳細については[、2015 Skype for Business Serverの ErrorDef](errordef.md) テーブルを参照してください。 <br/> |
|**FromUserId** <br/> |int  <br/> |外部  <br/> |エラーの原因となる要求を発生したユーザー。 詳細については [、「Users」テーブル](users.md) を参照してください。 <br/> |
|**ToUserId** <br/> |int  <br/> |外部  <br/> |エラーの原因となる要求の宛先ユーザー。 詳細については [、「Users」テーブル](users.md) を参照してください。 <br/> |
|**ConferenceUriId** <br/> |int  <br/> |外部  <br/> |エラーに関連する会議 URI。 詳細については[、2015 Skype for Business Serverの ConferenceUris](conferenceuris.md) テーブルを参照してください。 通常、ConferenceUriId が null ではない場合は、FromUserId または ToUserId のどちらかが null になります。 <br/> |
|**SessionIdTime** <br/> |日付型  <br/> |外部  <br/> |セッションを一意に識別するために **SessionIdSeq** と併用されます。 詳細については[、2015 Skype for Business Serverの](dialogs.md) Dialogs テーブルを参照してください。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |外部  <br/> |セッションを識別するための ID 番号。 セッションを一意に識別するために **SessionIdTime** と併用されます。 詳細については[、2015 Skype for Business Serverの](dialogs.md) Dialogs テーブルを参照してください。 <br/> |
|**SourceId** <br/> |int  <br/> |外部  <br/> |エラー レポートを送信したサーバー (レポートがサーバー コンポーネントから送信されている場合)。 詳細については [、「サーバー」の表](servers.md) を参照してください。 <br/> このフィールドは、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**ApplicationId** <br/> |int  <br/> |外部  <br/> |エラー レポートを送信したサーバー (レポートがサーバー コンポーネントから送信されている場合)。 詳細については[、2015 Skype for Business Serverの](application.md) Application テーブルを参照してください。 <br/> このフィールドは、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**MsDiagHeader** <br/> |image  <br/> | <br/> |エラーの詳細。  <br/> このデータは、次の構文を使用してテキスト形式に変換できます。  <br/>  `cast(cast(Detail as varbinary(max)) as varchar(max))` <br/> |
|**ClientVersionId** <br/> |int  <br/> |外部  <br/> |エラー レポートを送信するエンドポイントのクライアント バージョン。 詳細については[、2015 年Skype for Business Server ClientVersions](clientversions.md) テーブルを参照してください。 <br/> |
|**IsCapturedByServer** <br/> |ビット  <br/> ||フロントエンド サーバーで実行されている CDR エージェントによってキャプチャされたエラー レポートか、クライアントによって送信されたエラー レポートです。  <br/> |
|**Flag** <br/> |smallint  <br/> ||将来使用するために予約されています。  <br/> |
|**TelemetryId** <br/> |uniqueIdentifier  <br/> ||会議に関するさまざまなコンポーネントの参加時間情報に関係する一意の識別子。  <br/> このフィールドは、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**SessionSetupTime** <br/> |int  <br/> ||特定のコンポーネントが会議に参加するのに必要な時間 (ミリ秒)。  <br/> このフィールドは、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**ServerId** <br/> |int  <br/> |外部  <br/> |エラー レポートを生成したサーバーの完全修飾ドメイン名を表します。  <br/> |
|**PoolId** <br/> |int  <br/> |外部  <br/> |エラー レポートが生成されたプールの完全修飾ドメイン名を表します。  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||監視サービスの内部用テーブル。  <br/> このフィールドは、2015 年Skype for Business Serverされました。  <br/> |
   

