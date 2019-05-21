---
title: Skype for Business Server 2015 の ErrorReport テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ae0287b4-e8ca-4f8c-84ef-502897dcaa2a
description: ErrorReport テーブルには、発生したエラーに関する情報が格納されます。 各レコードはエラー発生の1つです。 このエラーは、フロントエンドサーバーで実行されている CDR エージェントまたはクライアントから送信された cd-r エージェントによってキャプチャされます。
ms.openlocfilehash: 80a6106bd7c6b87a7519bca6ce5cc72f45147ad6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296267"
---
# <a name="errorreport-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 の ErrorReport テーブル
 
ErrorReport テーブルには、発生したエラーに関する情報が格納されます。 各レコードはエラー発生の1つです。 このエラーは、フロントエンドサーバーで実行されている CDR エージェントまたはクライアントから送信された cd-r エージェントによってキャプチャされます。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**ErrorTime** <br/> |datetime  <br/> |Primary  <br/> |エラーが発生した日付と時刻。  <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |Primary  <br/> |エラーレポートを識別する ID 番号。 エラーレポートを一意に識別するための**Errortime**と組み合わせて使用されます。 <br/> |
|**ErrorId** <br/> |int  <br/> |外部  <br/> |エラーの種類の一意の ID です。 詳細については、「 [Skype For Business Server 2015 の Errordef テーブル](errordef.md)」を参照してください。 <br/> |
|**FromUserId** <br/> |int  <br/> |外部  <br/> |エラーの原因となった要求を生成したユーザー。 詳細については、「ユーザー」の[表](users.md)を参照してください。 <br/> |
|**ToUserId** <br/> |int  <br/> |外部  <br/> |エラーの原因となった要求の送信先ユーザー。 詳細については、「ユーザー」の[表](users.md)を参照してください。 <br/> |
|**ConferenceUriId** <br/> |int  <br/> |外部  <br/> |エラーに関連する会議の URI。 詳細については、「 [Skype For Business Server 2015 の ConferenceUris テーブル](conferenceuris.md)」を参照してください。 通常、ConferenceUriId が null でない場合は、FromUserId または ToUserId は null になります。 <br/> |
|**セッション Id** <br/> |datetime  <br/> |外部  <br/> |セッションを一意に識別するために**Sessionidseq**と組み合わせて使用されます。 詳細については、「 [Skype For Business Server 2015 のダイアログ一覧](dialogs.md)」を参照してください。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |外部  <br/> |セッションを識別する ID 番号。 セッションを一意に識別するために**Sessionidtime**と組み合わせて使用されます。 詳細については、「 [Skype For Business Server 2015 のダイアログ一覧](dialogs.md)」を参照してください。 <br/> |
|**SourceId** <br/> |int  <br/> |外部  <br/> |エラーレポートを送信したサーバー (レポートがサーバーコンポーネントから送信されている場合)。 詳細については、「Servers」の[表](servers.md)を参照してください。 <br/> このフィールドは、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**ApplicationId** <br/> |int  <br/> |外部  <br/> |エラーレポートを送信したサーバー (レポートがサーバーコンポーネントから送信されている場合)。 詳細については、「 [Skype For Business Server 2015 のアプリケーションテーブル](application.md)」を参照してください。 <br/> このフィールドは、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**MsDiagHeader** <br/> |画像  <br/> | <br/> |エラーに関する詳細情報。  <br/> このデータは、次の構文を使用してテキスト形式に変換できます。  <br/>  `cast(cast(Detail as varbinary(max)) as varchar(max))` <br/> |
|**ClientVersionId** <br/> |int  <br/> |外部  <br/> |エラーレポートを送信するエンドポイントのクライアントバージョン。 詳細については、「 [Skype For Business Server 2015 の Clientversions](clientversions.md) 」の表を参照してください。 <br/> |
|**IsCapturedByServer** <br/> |bit  <br/> ||エラーレポートは、フロントエンドサーバーで実行されている CDR エージェントまたはクライアントによってキャプチャされます。  <br/> |
|**フラッグ** <br/> |smallint  <br/> ||今後の使用のために予約されています。  <br/> |
|**TelemetryId** <br/> |長さ  <br/> ||電話会議に参加しているさまざまなコンポーネントについての、固有の識別子による結合時間情報の関連付け。  <br/> このフィールドは、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**SessionSetupTime 時間** <br/> |int  <br/> ||特定のコンポーネントが会議に参加するために必要な時間 (ミリ秒単位) です。  <br/> このフィールドは、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**ServerId** <br/> |int  <br/> |外部  <br/> |エラーレポートを生成したサーバーの完全修飾ドメイン名を表します。  <br/> |
|**PoolId** <br/> |int  <br/> |外部  <br/> |エラーレポートが生成されたプールの完全修飾ドメイン名を表します。  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||監視サービスで内部的に使用されます。  <br/> このフィールドは、Skype for Business Server 2015 で導入されました。  <br/> |
   

