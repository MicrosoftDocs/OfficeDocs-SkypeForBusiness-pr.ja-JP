---
title: Skype for Business Server 2015 の IMReportSummary テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
description: Imreportの概要表は、組織内で開催されたインスタントメッセージセッションに関する全体的なレポートを提供します。 この表は、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 647b8dc3e48e56d126a65f524de90954b7aeca8f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296127"
---
# <a name="imreportsummary-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 の IMReportSummary テーブル
 
Imreportの概要表は、組織内で開催されたインスタントメッセージセッションに関する全体的なレポートを提供します。 この表は、Microsoft Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**StartTime** <br/> |datetime  <br/> |Primary  <br/> |インスタントメッセージングセッションが開始された日付と時刻。  <br/> |
|**期間** <br/> |char (1)  <br/> |Primary  <br/> ||
|**PoolFQDN** <br/> |nvarchar (257)  <br/> |Primary  <br/> |セッションをホストしているプールの完全修飾ドメイン名。  <br/> |
|**AuthType** <br/> |int  <br/> |Primary  <br/> |通話の優先度 (緊急または不急など) 優先度の情報は、 [Skype For Business Server 2015 の callpriorities テーブル](callpriorities.md)に格納されます。  <br/> |
|**SessionCount** <br/> |bigint  <br/> |||
|**MsgCount** <br/> |bigint  <br/> ||セッション中に交換されたインスタントメッセージの合計数です。  <br/> |
   

