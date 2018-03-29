---
title: ProgressReport ビュー
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b49f3fc7-0e2f-498f-8505-aaaf54e435f9
description: ProgressReport ビューでは、完了したセッションに関する情報を格納します。 進行状況レポートは、呼び出しと Lync Server 2013 では、診断に役立つことがありますを決定するためのセッションにのみ書き込まれます。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 7dab41202eb098e2e49e5d4960b0c7b4e4c6570d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="progressreport-view"></a>ProgressReport ビュー
 
ProgressReport ビューでは、完了したセッションに関する情報を格納します。 進行状況レポートは、呼び出しと Lync Server 2013 では、診断に役立つことがありますを決定するためのセッションにのみ書き込まれます。 このビューは、Microsoft Lync Server 2013 で導入されました。
  
> [!NOTE]
> 呼び出しまたはメッセージの状態を示すメッセージですが、エラーにも、ErrorTime、ErrorReportSeq、ProgressReportSeq フィールドが参照するいないとは限りません。 
  
|**列**|**データ型**|**詳細**|
|:-----|:-----|:-----|
|**ErrorTime** <br/> |datetime  <br/> |時間のエラーが発生しました。 エラーを一意に識別するのには ErrorReportSeq と組み合わせてを使用します。  <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |エラーを識別する ID 番号。 エラーを一意に識別するのには ErrorTime と組み合わせてを使用します。  <br/> |
|**ProgressReportSeq** <br/> |int  <br/> |進行状況レポートを識別する ID です。 同じエラー レポートの進行状況レポートを区別するために使用されます。  <br/> |
|**MsDiagId** <br/> |int  <br/> |エラー レポートの診断 ID。  <br/> |
|**ソース** <br/> |nvarchar(256)  <br/> |(レポートは、サーバー コンポーネントから送信された) 場合、エラーが発生したサーバーの名前です。  <br/> |
|**アプリケーション** <br/> |nvarchar(256)  <br/> |(レポートは、サーバー コンポーネントから送信された) 場合、エラーが発生したアプリケーションの名前です。  <br/> |
|**TelemetryId** <br/> |一意識別子  <br/> |会議に関連するさまざまなコンポーネントの結合時の情報を関連付ける一意の識別子。  <br/> |
|**SessionSetupTime** <br/> |int  <br/> |時間 (ミリ秒単位) の会議に参加するのには特定のコンポーネントが必要です。  <br/> |
|**MsDiagHeader** <br/> |は  <br/> |追加のエラー情報です。  <br/> |
   

