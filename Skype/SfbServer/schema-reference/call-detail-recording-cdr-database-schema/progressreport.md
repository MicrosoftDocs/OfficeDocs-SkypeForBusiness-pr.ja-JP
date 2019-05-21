---
title: ProgressReport テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 38e5f060-5e9b-4185-87b2-7ef61c4bb75f
description: 進行状況レポートは、呼び出しまたはセッションが完了した後に、クライアントからデータベースにアップロードされたデータに基づいています。 進行状況レポートは、Skype for Business Server 2015 で診断目的として役立つ可能性がある通話とセッションに対してのみ作成されます。
ms.openlocfilehash: 9022c7707e0d2f0a4346ed629bf51420c312b10a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295903"
---
# <a name="progressreport-table"></a>ProgressReport テーブル
 
進行状況レポートは、呼び出しまたはセッションが完了した後に、クライアントからデータベースにアップロードされたデータに基づいています。 進行状況レポートは、Skype for Business Server 2015 で診断目的として役立つ可能性がある通話とセッションに対してのみ作成されます。
  
ErrorTime、ErrorReportSeq、進捗レポート Seq フィールドは、必ずしもエラーも参照しません。通話またはメッセージの状態を示すメッセージが表示されるわけではありません。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**ErrorTime** <br/> |datetime  <br/> |プライマリ、外部  <br/> |この進捗状況レポートが含まれる進捗状況エラーレポートの日付と時刻。 詳細については、「 [Skype For Business Server 2015 の ErrorReport テーブル](errorreport.md)」を参照してください。 <br/> |
|**ErrorId** <br/> |int  <br/> |プライマリ、外部  <br/> |ID 番号は、ErrorTime と共に使用されます。進捗レポートは、進行状況レポートを一意に識別するために使われます。 詳細については、「 [Skype For Business Server 2015 の ErrorReport テーブル](errorreport.md)」を参照してください。 <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |プライマリ、外部  <br/> |エラーレポートを識別する ID 番号。 エラーレポートを一意に識別するには、ErrorReporSeq と ErrorTime との組み合わせで使用されます。 詳細については、「 [Skype For Business Server 2015 の ErrorReport テーブル](errorreport.md)」を参照してください。 <br/> このフィールドは、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**進捗状況レポート Seq** <br/> |int  <br/> |Primary  <br/> |進捗状況レポートを識別する ID 番号。 ErrorTime と ErrorReportSeq と組み合わせて、進行状況レポートを一意に識別するために使用されます。  <br/> |
|**MsDiagId** <br/> |int  <br/> ||進行状況レポートの診断 ID。  <br/> このフィールドは、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**SourceId** <br/> |int  <br/> |外部  <br/> |エラーレポートを送信したサーバー (レポートがサーバーコンポーネントから送信された場合)。 詳細については、「Servers」の[表](servers.md)を参照してください。このフィールドは、Microsoft Lync Server 2013 で導入されました。 <br/> |
|**ApplicationId** <br/> |int  <br/> ||レポートの作成に関する Lync Server プロセス。 詳しくは、アプリケーションの表をご覧ください。  <br/> |
|**[詳細]** <br/> |画像  <br/> ||サイズを節約するためのバイナリ形式で保存された進行状況レポートの詳細。このデータは、次の構文を使用してテキスト形式に変換できます。  <br/> cast (cast (varbinary (max) としての Detail (max))  <br/> |
|**TelemetryId** <br/> |長さ  <br/> ||会議に参加しているさまざまなコンポーネントの参加時間情報を関連付ける一意の識別子です。  <br/> このフィールドは、Microsoft Lync Server 2013 で導入されました。  <br/> |
|**SessionSetupTime 時間** <br/> |int  <br/> ||特定のコンポーネントが会議に参加するまでの時間 (ミリ秒単位) です。  <br/> このフィールドは、Microsoft Lync Server 2013 で導入されました。  <br/> |
   

