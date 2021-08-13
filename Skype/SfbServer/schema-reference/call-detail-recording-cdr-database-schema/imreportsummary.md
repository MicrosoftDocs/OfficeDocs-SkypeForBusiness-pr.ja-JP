---
title: IMReportSummary テーブル (2015 Skype for Business Server)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
description: IMReportSummaryTable は、組織内で確立されているインスタント メッセージング セッションについての概要レポートを提供します。 この表は、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 204aeb21037f69eb34c2e12ee642d2ed6495111f8ae68d8c8f3786eb49a957fa
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54341722"
---
# <a name="imreportsummary-table-in-skype-for-business-server-2015"></a>IMReportSummary テーブル (2015 Skype for Business Server)
 
IMReportSummaryTable は、組織内で確立されているインスタント メッセージング セッションについての概要レポートを提供します。 この表は、Microsoft Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**StartTime** <br/> |日付型  <br/> |Primary  <br/> |インスタント メッセージング セッションが開始された日時。  <br/> |
|**TimePeriod** <br/> |char(1)  <br/> |Primary  <br/> ||
|**PoolFQDN** <br/> |nvarchar(257)  <br/> |Primary  <br/> |セッションをホストするプールの完全修飾ドメイン名。  <br/> |
|**AuthType** <br/> |整数  <br/> |Primary  <br/> |通話の優先度 (緊急、非緊急など)。 優先度情報は[、2015 年の CallPriorities テーブルSkype for Business Serverされます](callpriorities.md)。  <br/> |
|**SessionCount** <br/> |bigint  <br/> |||
|**MsgCount** <br/> |bigint  <br/> ||セッション中に交換されたインスタント メッセージの合計数。  <br/> |
   

