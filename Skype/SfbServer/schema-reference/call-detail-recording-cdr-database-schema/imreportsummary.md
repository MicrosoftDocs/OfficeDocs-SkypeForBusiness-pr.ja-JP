---
title: IMReportSummary テーブル (2015 Skype for Business Server)
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
description: IMReportSummaryTable は、組織内で確立されているインスタント メッセージング セッションについての概要レポートを提供します。 この表は、Microsoft Lync Server 2013 で導入されました。
---

# <a name="imreportsummary-table-in-skype-for-business-server-2015"></a>IMReportSummary テーブル (2015 Skype for Business Server)
 
IMReportSummaryTable は、組織内で確立されているインスタント メッセージング セッションについての概要レポートを提供します。 この表は、Microsoft Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**StartTime** <br/> |日付型  <br/> |Primary  <br/> |インスタント メッセージング セッションが開始された日時。  <br/> |
|**TimePeriod** <br/> |char(1)  <br/> |Primary  <br/> ||
|**PoolFQDN** <br/> |nvarchar(257)  <br/> |Primary  <br/> |セッションをホストするプールの完全修飾ドメイン名。  <br/> |
|**AuthType** <br/> |int  <br/> |Primary  <br/> |通話の優先度 (緊急、非緊急など)。 優先度情報は、[2015 年の CallPriorities テーブルSkype for Business Serverされます](callpriorities.md)。  <br/> |
|**SessionCount** <br/> |bigint  <br/> |||
|**MsgCount** <br/> |bigint  <br/> ||セッション中に交換されたインスタント メッセージの合計数。  <br/> |
   

