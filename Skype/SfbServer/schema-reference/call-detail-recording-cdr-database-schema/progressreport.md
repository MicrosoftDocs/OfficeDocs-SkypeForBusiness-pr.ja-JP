---
title: ProgressReport テーブル
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 38e5f060-5e9b-4185-87b2-7ef61c4bb75f
description: 進行状況レポートは、呼び出し、またはセッションが完了した後に、データベースにクライアントによってアップロードされたデータに基づいています。 進行状況レポートは、呼び出しとビジネス サーバー 2015 の Skype では、診断に役立つことがありますを決定するためのセッションにのみ書き込まれます。
ms.openlocfilehash: 6d638411f39956664c977e87785a1269ee788a5f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899758"
---
# <a name="progressreport-table"></a>ProgressReport テーブル
 
進行状況レポートは、呼び出し、またはセッションが完了した後に、データベースにクライアントによってアップロードされたデータに基づいています。 進行状況レポートは、呼び出しとビジネス サーバー 2015 の Skype では、診断に役立つことがありますを決定するためのセッションにのみ書き込まれます。
  
呼び出しまたはメッセージの状態を示すメッセージですが、エラーにも、ErrorTime、ErrorReportSeq、ProgressReportSeq フィールドが参照するいないとは限りません。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**ErrorTime** <br/> |datetime  <br/> |プライマリ サーバーで、外部  <br/> |日付と時刻この進行状況レポートを含む進行中のエラー報告します。 [ビジネス サーバー 2015 の Skype で ErrorReport テーブル](errorreport.md)の詳細についてを参照してください。 <br/> |
|**ErrorId** <br/> |int  <br/> |プライマリ サーバーで、外部  <br/> |ID 番号が ErrorTime、進行状況レポートを一意に識別するのには ProgressReportSeq と組み合わせて使用します。 [ビジネス サーバー 2015 の Skype で ErrorReport テーブル](errorreport.md)の詳細についてを参照してください。 <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |プライマリ サーバーで、外部  <br/> |エラー レポートを識別する ID 番号。 ErrorReporSeq は、エラー レポートを一意に識別するに ErrorTime と組み合わせてを使用します。 [ビジネス サーバー 2015 の Skype で ErrorReport テーブル](errorreport.md)の詳細についてを参照してください。 <br/> このフィールドは、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**ProgressReportSeq** <br/> |int  <br/> |Primary  <br/> |進行状況レポートを識別する ID 番号。 ErrorTime と ErrorReportSeq と組み合わせてを使用し、進行状況レポートを一意に識別します。  <br/> |
|**MsDiagId** <br/> |int  <br/> ||進行状況レポートの診断 ID。  <br/> このフィールドは、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**SourceId** <br/> |int  <br/> |外部  <br/> |(レポートは、サーバー コンポーネントから送信された) 場合、エラー レポートを送信するサーバー。 詳細については[サーバーのテーブル](servers.md)を参照してください。このフィールドは、Microsoft Lync Server 2013 で導入されました。 <br/> |
|**付きアプリケーション Id** <br/> |int  <br/> ||に関するレポートは、Lync Server のプロセスです。 詳細についてはアプリケーションのテーブルを参照してください。  <br/> |
|**[詳細]** <br/> |画像  <br/> ||進行状況レポートの詳細、領域を節約するのにはバイナリ形式で格納します。このデータは、この構文を使用してテキスト形式に変換できます。  <br/> キャスト (cast (varchar(max)) と varbinary(max)) と詳細  <br/> |
|**TelemetryId** <br/> |一意識別子  <br/> ||相関関係づけが会議に関連するさまざまなコンポーネントについては、時間を結合する一意の識別子。  <br/> このフィールドは、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**SessionSetupTime** <br/> |int  <br/> ||時間 (ミリ秒単位) が会議に参加するのには特定のコンポーネントにします。  <br/> このフィールドは、Microsoft Lync Server 2013 で導入されました。  <br/> |
   

