---
title: ビジネス サーバー 2015 の Skype での IMReportSummary テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
description: IMReportSummaryTable では、インスタント メッセージング セッションを保持している組織内で、総合的なレポートを提供します。 このテーブルは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 3611243e49821e5fae211ce55858cdee555dd383
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901046"
---
# <a name="imreportsummary-table-in-skype-for-business-server-2015"></a>ビジネス サーバー 2015 の Skype での IMReportSummary テーブル
 
IMReportSummaryTable では、インスタント メッセージング セッションを保持している組織内で、総合的なレポートを提供します。 このテーブルは、Microsoft Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**StartTime** <br/> |datetime  <br/> |Primary  <br/> |日付と時刻、インスタント メッセージング セッションを開始しました。  <br/> |
|**TimePeriod** <br/> |char(1)  <br/> |Primary  <br/> ||
|**PoolFQDN** <br/> |nvarchar(257)  <br/> |Primary  <br/> |セッションをホストしているプールの完全修飾ドメイン名です。  <br/> |
|**空の AuthType** <br/> |int  <br/> |Primary  <br/> |(たとえば、緊急または非緊急) 呼び出しの優先順位です。 優先順位については、[ビジネス サーバー 2015 の Skype での CallPriorities テーブル](callpriorities.md)に格納されます。  <br/> |
|**SessionCount** <br/> |bigint 型の値  <br/> |||
|**MsgCount** <br/> |bigint 型の値  <br/> ||セッション中に交換するインスタント メッセージの合計数です。  <br/> |
   

