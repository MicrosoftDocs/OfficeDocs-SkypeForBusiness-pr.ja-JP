---
title: ProgressReport テーブル
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 38e5f060-5e9b-4185-87b2-7ef61c4bb75f
description: 進行状況レポートは、通話またはセッションの完了後にクライアントによってデータベースにアップロードされたデータに基づきます。 進行状況レポートは、2015 年から 2015 年Skype for Business Serverの呼び出しとセッションに対してのみ書き込まれます。
ms.openlocfilehash: 6429700f902caec80db02f3db6c78420b5c108ce6a39383da8914955df16f80d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54286226"
---
# <a name="progressreport-table"></a>ProgressReport テーブル
 
進行状況レポートは、通話またはセッションの完了後にクライアントによってデータベースにアップロードされたデータに基づきます。 進行状況レポートは、2015 年から 2015 年Skype for Business Serverの呼び出しとセッションに対してのみ書き込まれます。
  
ErrorTime、ErrorReportSeq、ProgressReportSeq フィールドは、必ずしもエラーではなく、呼び出しまたはメッセージの状態を示すメッセージを参照します。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**ErrorTime** <br/> |日付型  <br/> |主/プライマリ、外部  <br/> |この進行状況レポートを含む進行状況エラー レポートの日時。 詳細については[、2015 年Skype for Business Server ErrorReport](errorreport.md)テーブルを参照してください。 <br/> |
|**ErrorId** <br/> |整数  <br/> |主/プライマリ、外部  <br/> |進行状況レポートを一意に識別するために ErrorTime、ProgressReportSeq と組み合わせて使用される ID 番号。 詳細については[、2015 年Skype for Business Server ErrorReport](errorreport.md)テーブルを参照してください。 <br/> |
|**ErrorReportSeq** <br/> |整数  <br/> |主/プライマリ、外部  <br/> |エラー レポートを識別する ID 番号。 ErrorReporSeq は、一意的にエラー レポートを識別する目的で ErrorTime と共に使用されます。 詳細については[、2015 Skype for Business Serverの ErrorReport](errorreport.md)テーブルを参照してください。 <br/> このフィールドは、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**ProgressReportSeq** <br/> |整数  <br/> |Primary  <br/> |進行状況レポートを識別するための ID 番号。進行状況レポートを一意に識別するために ErrorTime と ErrorReportSeq と併用されます。  <br/> |
|**MsDiagId** <br/> |整数  <br/> ||進行状況レポートの診断 ID。  <br/> このフィールドは、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**SourceId** <br/> |整数  <br/> |外部  <br/> |エラー レポートを送信したサーバー (レポートがサーバー コンポーネントから送信された場合)。 詳細については [、「サーバー」の表](servers.md) を参照してください。このフィールドは、Microsoft Lync Server 2013 で導入されました。 <br/> |
|**ApplicationId** <br/> |整数  <br/> ||レポートの対象となる Lync Server プロセス。詳細については、「アプリケーション テーブル」を参照してください。  <br/> |
|**詳細** <br/> |image  <br/> ||進行状況レポートの詳細。記憶域を節約するできるようにバイナリ形式で格納されます。このデータは、次のコードを使用してテキスト形式に変換できます。  <br/> cast(cast(Detail as varbinary(max)) as varchar(max))  <br/> |
|**TelemetryId** <br/> |uniqueIdentifier  <br/> ||電話会議に関係するさまざまなコンポーネントの参加時間情報を関連付ける一意識別子。  <br/> このフィールドは、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**SessionSetupTime** <br/> |整数  <br/> ||特定のコンポーネントが電話会議に参加する時間 (単位はミリ秒)。  <br/> このフィールドは、Microsoft Lync Server 2013 で導入されました。  <br/> |
   

