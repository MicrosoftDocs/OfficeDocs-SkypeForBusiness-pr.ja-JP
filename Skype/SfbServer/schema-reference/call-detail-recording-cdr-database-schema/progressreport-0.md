---
title: 進捗状況レポートビュー
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b49f3fc7-0e2f-498f-8505-aaaf54e435f9
description: 進捗レポートビューには、完了したセッションに関する情報が格納されます。 進行状況レポートは、Lync Server 2013 で判別目的で役立つ可能性がある通話とセッションに対してのみ記録されます。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: c07b9db8ebd9f898ab9d8feb5b07c4723209522c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814985"
---
# <a name="progressreport-view"></a>進捗状況レポートビュー
 
進捗レポートビューには、完了したセッションに関する情報が格納されます。 進行状況レポートは、Lync Server 2013 で判別目的で役立つ可能性がある通話とセッションに対してのみ記録されます。 このビューは、Microsoft Lync Server 2013 で導入されました。
  
> [!NOTE]
> ErrorTime、ErrorReportSeq、進捗レポート Seq フィールドは、必ずしもエラーも参照しません。通話またはメッセージの状態を示すメッセージが表示されるわけではありません。 
  
|**列**|**データ型**|**詳細**|
|:-----|:-----|:-----|
|**ErrorTime** <br/> |datetime  <br/> |エラーが発生した時刻。 エラーを一意に識別するには、ErrorReportSeq と組み合わせて使います。  <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |エラーを識別する ID 番号。 エラーを一意に識別するための ErrorTime と共に使用されます。  <br/> |
|**進捗状況レポート Seq** <br/> |int  <br/> |進行状況レポートを識別する ID。 同じエラーレポートの進行状況レポートを区別するために使用されます。  <br/> |
|**MsDiagId** <br/> |int  <br/> |エラーレポートの診断 ID。  <br/> |
|**ソース** <br/> |nvarchar(256)  <br/> |エラーが発生したサーバーの名前 (サーバーコンポーネントからレポートが送信された場合)。  <br/> |
|**Application** <br/> |nvarchar(256)  <br/> |エラーの発生元のアプリケーションの名前 (サーバーコンポーネントからレポートが送信された場合)。  <br/> |
|**TelemetryId** <br/> |長さ  <br/> |電話会議に参加しているさまざまなコンポーネントについての、固有の識別子による結合時間情報の関連付け。  <br/> |
|**SessionSetupTime 時間** <br/> |int  <br/> |特定のコンポーネントが会議に参加するために必要な時間 (ミリ秒単位) です。  <br/> |
|**MsDiagHeader** <br/> |varchar (max)  <br/> |追加のエラー情報。  <br/> |
   

