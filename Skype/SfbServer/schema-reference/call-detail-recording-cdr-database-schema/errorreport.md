---
title: ビジネス サーバー 2015 の Skype で ErrorReport テーブル
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/15/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ae0287b4-e8ca-4f8c-84ef-502897dcaa2a
description: ErrorReport テーブルでは、発生したエラーに関する情報を格納します。 各レコードは、1 つのエラーの発生です。 エラーは、フロント エンド サーバーで実行されている CDR エージェントがいずれかの方法を取得またはクライアントから送信されます。
ms.openlocfilehash: 80ae8cb9fb4bea586ac31456fc396856e5263a34
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="errorreport-table-in-skype-for-business-server-2015"></a>ビジネス サーバー 2015 の Skype で ErrorReport テーブル
 
ErrorReport テーブルでは、発生したエラーに関する情報を格納します。 各レコードは、1 つのエラーの発生です。 エラーは、フロント エンド サーバーで実行されている CDR エージェントがいずれかの方法を取得またはクライアントから送信されます。
  
|**列**|**データ型**|**キーまたはインデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**ErrorTime** <br/> |datetime  <br/> |Primary  <br/> |日付と時刻のエラーが発生しました。  <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |Primary  <br/> |エラー レポートを識別する ID 番号。 エラー報告を一意に識別するのには**ErrorTime**と組み合わせてを使用します。 <br/> |
|**ErrorId** <br/> |int  <br/> |外部  <br/> |エラーの種類の一意の ID です。 詳細については、 [Skype のビジネス サーバー 2015 で ErrorDef テーブル](errordef.md)を参照してください。 <br/> |
|**FromUserId** <br/> |int  <br/> |外部  <br/> |エラーが発生した要求を発信したユーザーです。 詳細については[「ユーザー」テーブル](users.md)を参照してください。 <br/> |
|**ToUserId** <br/> |int  <br/> |外部  <br/> |エラーが発生した要求の送信先のユーザーです。 詳細については[「ユーザー」テーブル](users.md)を参照してください。 <br/> |
|**ConferenceUriId** <br/> |int  <br/> |外部  <br/> |会議 URI は、エラーに関連します。 詳細については、 [Skype のビジネス サーバー 2015 で ConferenceUris テーブル](conferenceuris.md)を参照してください。 通常、ConferenceUriId が null でない場合、FromUserId または ToUserId のいずれかは null になります。 <br/> |
|**SessionIdTime** <br/> |datetime  <br/> |外部  <br/> |セッションを一意に識別するのには**SessionIdSeq**と組み合わせてを使用します。 [Skype のビジネス サーバー 2015 のテーブル」ダイアログ ボックス](dialogs.md)の詳細についてを参照してください。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |外部  <br/> |セッションを識別する ID 番号。 セッションを一意に識別するのには**SessionIdTime**と組み合わせてを使用します。 [Skype のビジネス サーバー 2015 のテーブル」ダイアログ ボックス](dialogs.md)の詳細についてを参照してください。 <br/> |
|**SourceId** <br/> |int  <br/> |外部  <br/> |(レポート サーバー コンポーネントから送信される) 場合は、エラー報告を送信するサーバー。 詳細については[サーバーのテーブル](servers.md)を参照してください。 <br/> このフィールドは、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**付きアプリケーション Id** <br/> |int  <br/> |外部  <br/> |(レポート サーバー コンポーネントから送信される) 場合は、エラー報告を送信するサーバー。 [ビジネス サーバー 2015 の Skype のアプリケーション テーブル](application.md)の詳細についてを参照してください。 <br/> このフィールドは、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**MsDiagHeader** <br/> |画像  <br/> | <br/> |エラーの詳細については。  <br/> このデータは、この構文を使用してテキスト形式に変換できます。  <br/>  `cast(cast(Detail as varbinary(max)) as varchar(max))` <br/> |
|**ClientVersionId** <br/> |int  <br/> |外部  <br/> |エラー報告を送信するエンドポイントのクライアントのバージョンです。 詳細については、 [Skype のビジネス サーバー 2015 で ClientVersions テーブル](clientversions.md)を参照してください。 <br/> |
|**IsCapturedByServer** <br/> |bit  <br/> ||エラー報告は、フロント エンド サーバーで実行されている CDR エージェントによってキャプチャされるか、クライアントによって送信されました。  <br/> |
|**フラグ** <br/> |smallint  <br/> ||将来使用するために予約されています。  <br/> |
|**TelemetryId** <br/> |一意識別子  <br/> ||会議に関連するさまざまなコンポーネントの結合時の情報を関連付ける一意の識別子。  <br/> このフィールドは、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**SessionSetupTime** <br/> |int  <br/> ||時間 (ミリ秒単位) の会議に参加するのには特定のコンポーネントが必要です。  <br/> このフィールドは、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**ServerId** <br/> |int  <br/> |外部  <br/> |エラー レポートを生成したサーバーの完全修飾ドメイン名を表します。  <br/> |
|**PoolId** <br/> |int  <br/> |外部  <br/> |エラー レポートが生成されたプールの完全修飾ドメイン名を表します。  <br/> |
|**LastModifiedTime** <br/> |日付時刻  <br/> ||監視サービスによって内部で使用します。  <br/> このフィールドは、ビジネス サーバー 2015 の Skype で導入されました。  <br/> |
   

