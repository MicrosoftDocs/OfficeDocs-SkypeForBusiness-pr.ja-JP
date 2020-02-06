---
title: Skype for Business Server 2015 の ConferenceJoinTimeThresholds テーブル
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
ms.assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
description: ConferenceJoinTimeThresholds テーブルには、電話会議の参加時間のサマリーレポートで使用される分類境界が含まれています。 [会議参加時間のサマリー] レポートは、ユーザーが会議に参加するのに必要な時間の概要を示します。これらの時間値は、平均として、または次のいずれかのカテゴリに報告されます。
ms.openlocfilehash: 1874a94448be5957079b1c53944bc127df761e5e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815395"
---
# <a name="conferencejointimethresholds-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 の ConferenceJoinTimeThresholds テーブル
 
ConferenceJoinTimeThresholds テーブルには、電話会議の参加時間のサマリーレポートで使用される分類境界が含まれています。 [会議参加時間のサマリー] レポートは、ユーザーが会議に参加するのに必要な時間の概要を示します。これらの時間値は、平均として、または次のいずれかのカテゴリに報告されます。
  
- 2秒未満。
    
- 2秒と5秒の間。
    
- 5 ~ 10 秒の間。
    
- 10秒以上
    
ConferenceJoinTimeThresholds テーブルには、2秒、5秒、10秒の分類値が含まれています。
  
この表は、Microsoft Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**ThresholdId** <br/> |int  <br/> |Primary  <br/> |分類の一意の識別子。  <br/> |
|**ThresholdValue** <br/> |int  <br/> || 分類の上限。 有効な値は次のとおりです。 <br/>  両面 <br/>  5 <br/>  常用 <br/> |
   

