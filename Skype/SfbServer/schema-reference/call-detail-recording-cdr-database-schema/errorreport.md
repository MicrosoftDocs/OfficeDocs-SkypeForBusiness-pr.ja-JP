---
title: Skype for Business Server 2015 の ErrorReport テーブル
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ae0287b4-e8ca-4f8c-84ef-502897dcaa2a
description: ErrorReport テーブルには、発生したエラーに関する情報が格納されます。 各レコードは 1 つのエラー発生です。 エラーは、フロントエンド サーバーで実行されている CDR エージェントまたはクライアントから送信された CDR エージェントによってキャプチャされます。
ms.openlocfilehash: b2f81df1134294185124d78b90c2e4f639575ded
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821677"
---
# <a name="errorreport-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 の ErrorReport テーブル
 
ErrorReport テーブルには、発生したエラーに関する情報が格納されます。 各レコードは 1 つのエラー発生です。 エラーは、フロントエンド サーバーで実行されている CDR エージェントまたはクライアントから送信された CDR エージェントによって取得されます。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**ErrorTime** <br/> |日付型  <br/> |Primary  <br/> |エラーが発生した日時。  <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |Primary  <br/> |エラー レポートを識別する ID 番号。 ErrorTime と組み **合わせて使用して** 、エラー レポートを一意に識別します。 <br/> |
|**ErrorId** <br/> |int  <br/> |外部  <br/> |エラーの種類の一意の ID。 詳細については [、Skype for Business Server 2015](errordef.md) の ErrorDef テーブルを参照してください。 <br/> |
|**FromUserId** <br/> |int  <br/> |外部  <br/> |エラーの原因となる要求を発信したユーザー。 詳細については [、Users の表](users.md) を参照してください。 <br/> |
|**ToUserId** <br/> |int  <br/> |外部  <br/> |エラーを発生した要求の送信先ユーザー。 詳細については [、Users の表](users.md) を参照してください。 <br/> |
|**ConferenceUriId** <br/> |int  <br/> |外部  <br/> |エラーに関連する電話会議 URI。 詳細については [、Skype for Business Server 2015 の ConferenceUris テーブル](conferenceuris.md) を参照してください。 通常、ConferenceUriId が null ではない場合、FromUserId または ToUserId は null になります。 <br/> |
|**SessionIdTime** <br/> |日付型  <br/> |外部  <br/> |セッションを一意に識別するために **SessionIdSeq** と併用されます。 詳細については [、Skype for Business Server 2015](dialogs.md) のダイアログ の表を参照してください。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |外部  <br/> |セッションを識別するための ID 番号。 セッションを一意に識別するために **SessionIdTime** と併用されます。 詳細については [、Skype for Business Server 2015](dialogs.md) のダイアログ の表を参照してください。 <br/> |
|**SourceId** <br/> |int  <br/> |外部  <br/> |エラー レポートを送信したサーバー (レポートがサーバー コンポーネントから送信されている場合)。 詳細については [、Servers の表](servers.md) を参照してください。 <br/> このフィールドは、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**ApplicationId** <br/> |int  <br/> |外部  <br/> |エラー レポートを送信したサーバー (レポートがサーバー コンポーネントから送信されている場合)。 詳細については [、Skype for Business Server 2015](application.md) の Application テーブルを参照してください。 <br/> このフィールドは、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**MsDiagHeader** <br/> |image  <br/> | <br/> |エラーに関する詳細。  <br/> このデータは、次の構文を使用してテキスト形式に変換できます。  <br/>  `cast(cast(Detail as varbinary(max)) as varchar(max))` <br/> |
|**ClientVersionId** <br/> |int  <br/> |外部  <br/> |エラー レポートを送信するエンドポイントのクライアント バージョン。 詳細については [、Skype for Business Server 2015 の ClientVersions テーブル](clientversions.md) を参照してください。 <br/> |
|**IsCapturedByServer** <br/> |bit  <br/> ||フロントエンド サーバーで実行されている CDR エージェントによってキャプチャされたエラー レポートか、クライアントによって送信されたエラー レポートです。  <br/> |
|**Flag** <br/> |smallint  <br/> ||将来使用するために予約されています。  <br/> |
|**TelemetryId** <br/> |uniqueIdentifier  <br/> ||会議に関するさまざまなコンポーネントの参加時間情報に関係する一意の識別子。  <br/> このフィールドは、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**SessionSetupTime** <br/> |int  <br/> ||特定のコンポーネントが会議に参加するのに必要な時間 (ミリ秒)。  <br/> このフィールドは、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**ServerId** <br/> |int  <br/> |外部  <br/> |エラー レポートを生成したサーバーの完全修飾ドメイン名を表します。  <br/> |
|**PoolId** <br/> |int  <br/> |外部  <br/> |エラー レポートが生成されたプールの完全修飾ドメイン名を表します。  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||監視サービスの内部用テーブル。  <br/> このフィールドは、Skype for Business Server 2015 で導入されました。  <br/> |
   

