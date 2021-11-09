---
title: ProgressReport ビュー
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b49f3fc7-0e2f-498f-8505-aaaf54e435f9
description: ProgressReport ビューは、完了したセッションに関する情報を格納します。 進行状況レポートは、Lync Server 2013 による診断時に役立ちそうな通話とセッションのみを対象として書き込まれます。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 87f1a0427f78a5d51f1f6bbd0c89e47187e06b25
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60850630"
---
# <a name="progressreport-view"></a>ProgressReport ビュー
 
ProgressReport ビューは、完了したセッションに関する情報を格納します。 進行状況レポートは、Lync Server 2013 による診断時に役立ちそうな通話とセッションのみを対象として書き込まれます。 このビューは、Microsoft Lync Server 2013 で導入されました。
  
> [!NOTE]
> ErrorTime、ErrorReportSeq、ProgressReportSeq フィールドは、必ずしもエラーではなく、呼び出しまたはメッセージの状態を示すメッセージを参照します。 
  
|**列**|**データ型**|**詳細**|
|:-----|:-----|:-----|
|**ErrorTime** <br/> |日付型  <br/> |エラーが発生した時刻。エラー を一意に識別するために ErrorReportSeq と併用されます。  <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |エラーを識別する ID 番号。エラーを一意に識別するために ErrorTime と併用されます。  <br/> |
|**ProgressReportSeq** <br/> |int  <br/> |進行状況レポートを識別するための ID。 同じエラー レポートの進行状況レポートを区別するために使用されます。  <br/> |
|**MsDiagId** <br/> |int  <br/> |エラー レポートの診断 ID。  <br/> |
|**Source** <br/> |nvarchar(256)  <br/> |エラーを発生させたサーバーの名前 (サーバー コンポーネントからレポートが送信された場合)。  <br/> |
|**アプリケーション** <br/> |nvarchar(256)  <br/> |エラーを発生させたアプリケーションの名前 (サーバー コンポーネントからレポートが送信された場合)。  <br/> |
|**TelemetryId** <br/> |uniqueidentifier  <br/> |会議に関するさまざまなコンポーネントの参加時間情報に関係する一意の識別子。  <br/> |
|**SessionSetupTime** <br/> |int  <br/> |特定のコンポーネントが会議に参加するのに必要な時間 (ミリ秒)。  <br/> |
|**MsDiagHeader** <br/> |varchar(max)  <br/> |追加のエラー情報。  <br/> |
   

