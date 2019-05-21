---
title: ErrorReport ビュー
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ca873f7e-b18b-4eaf-8db0-5f9d5a9b60a1
description: ErrorReport ビューには、報告されたエラーに関する情報が格納されます。 各レコードはエラー発生の1つです。 このエラーは、フロントエンドサーバーで実行されている CDR エージェントまたはクライアントから送信された cd-r エージェントによってキャプチャされます。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: a95d3d1e99fc41727c10ecef7beaafddc213dd17
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296274"
---
# <a name="errorreport-view"></a>ErrorReport ビュー
 
ErrorReport ビューには、報告されたエラーに関する情報が格納されます。 各レコードはエラー発生の1つです。 このエラーは、フロントエンドサーバーで実行されている CDR エージェントまたはクライアントから送信された cd-r エージェントによってキャプチャされます。 このビューは、Microsoft Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**詳細**|
|:-----|:-----|:-----|
|**ErrorTime** <br/> |datetime  <br/> |エラーが発生した時刻。 エラーを一意に識別するには、ErrorReportSeq と組み合わせて使います。  <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |エラーを識別する ID 番号。 エラーを一意に識別するための ErrorTime と共に使用されます。  <br/> |
|**MsDiagId** <br/> |int  <br/> |エラーレポートの診断 ID。  <br/> |
|**FromUri** <br/> |nvarchar (450)  <br/> |エラーを発生させたユーザーの URI。  <br/> |
|**FromUriType** <br/> |nvarchar(256)  <br/> |エラーを発生させたユーザーの URI の種類。 詳細については、 [UriTypes の表](uritypes.md)を参照してください。 <br/> |
|**FromTenant** <br/> |nvarchar(256)  <br/> |エラーを発生させたユーザーのテナント。 詳細については、「テナント」の[表](tenants.md)を参照してください。 <br/> |
|**ToUri** <br/> |nvarchar (450)  <br/> |エラーレポートのターゲットであるユーザーの URI。  <br/> |
|**ToUriType** <br/> |nvarchar(256)  <br/> |エラーレポートの対象となるユーザーの URI の種類。 詳細については、UriTypes の表を参照してください。  <br/> |
|**すべての Ant** <br/> |nvarchar(256)  <br/> |エラーレポートの対象ユーザーのテナント。 詳細については、「テナント」の[表](tenants.md)を参照してください。 <br/> |
|**ConferenceUri** <br/> |nvarchar (450)  <br/> |エラーレポートのターゲットとなった会議の URI。  <br/> |
|**ConferenceUriType** <br/> |nvarchar(256)  <br/> |エラーレポートのターゲットとなった会議の URI の種類。 詳細については、 [UriTypes の表](uritypes.md)を参照してください。 <br/> |
|**セッション Id** <br/> |datetime  <br/> |エラーレポートを生成したセッション要求の時刻。 セッションを一意に識別するために SessionIdSeq と組み合わせて使用されます。 詳細については、「 [Skype For Business Server 2015 のダイアログ一覧](dialogs.md)」を参照してください。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |エラーレポートを生成したセッション要求を識別する ID 番号。 セッションを一意に識別するために SessionIdTime と組み合わせて使用されます。 詳細については、「 [Skype For Business Server 2015 のダイアログ一覧](dialogs.md)」を参照してください。 <br/> |
|**この Id** <br/> |varstring (775)  <br/> |エラーを発生させたセッションの SIP ダイアログ ID。 形式は次のとおりです。  <br/> ダイアログ; 開始タグからタグへ  <br/> このデータは、次の構文を使用してテキスト形式に変換できます。  <br/> キャスト (cast (ExternalId as varbinary (max)) (varchar (max)))  <br/> |
|**ClientVersion** <br/> |nvarchar(256)  <br/> |エラーの発生元のユーザーによって使用されたクライアントのバージョン。  <br/> |
|**ClientType** <br/> |int  <br/> |エラーの発生元のユーザーによって使用されたクライアント。 詳細については、 [Useragentdef テーブル](useragentdef.md)を参照してください。 <br/> |
|**ClientCategory** <br/> |nvarchar (64)  <br/> |エラーの発生元のユーザーによって使用されたクライアントのカテゴリの名前です。  <br/> |
|**ソース** <br/> |nvarchar(256)  <br/> |エラーが発生したサーバーの名前 (サーバーコンポーネントからレポートが送信された場合)。  <br/> |
|**Application** <br/> |nvarchar(256)  <br/> |エラーの発生元のアプリケーションの名前 (サーバーコンポーネントからレポートが送信された場合)。  <br/> |
|**返信** <br/> |int  <br/> |エラーレポートが含まれる SIP メッセージのセッションへの SIP 応答コード。  <br/> |
|**RequestType** <br/> |varchar (max)  <br/> |失敗した要求の種類。  <br/> |
|**ContentType** <br/> |varchar (max)  <br/> |失敗した要求のコンテンツタイプ。  <br/> |
|**CallType** <br/> |nvarchar(256)  <br/> |セッションの種類。 詳細については、「 [Skype For Business Server 2015 の CallType テーブル](calltype.md)」を参照してください。 <br/> |
|**TelemetryId** <br/> |長さ  <br/> |電話会議に参加しているさまざまなコンポーネントについての、固有の識別子による結合時間情報の関連付け。  <br/> |
|**SetupTime 時間** <br/> |int  <br/> |特定のコンポーネントが会議に参加するために必要な時間 (ミリ秒単位) です。  <br/> |
|**IsCapturedByServer** <br/> |bit  <br/> |エラーレポートが、フロントエンドサーバーで実行されている CDR エージェントまたはクライアントによってキャプチャされたかどうかを示します。  <br/> |
|**フラッグ** <br/> |smallint  <br/> |今後の使用のために予約されています。  <br/> |
|**MsDiagHeader** <br/> |varchar (max)  <br/> |エラーに関する追加情報。  <br/> |
|**FrontEnd** <br/> |nvarchar  <br/> |レポートを提出したフロントエンドサーバーの完全修飾ドメイン名。  <br/> |
|**Pool** <br/> |nvarchar  <br/> |レポートを提出したフロントエンドサーバーを含むプールの完全修飾ドメイン名。  <br/> |
   

