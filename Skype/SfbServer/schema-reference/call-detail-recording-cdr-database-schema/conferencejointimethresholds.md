---
title: ConferenceJoinTimeThresholds テーブル (Skype for Business Server 2015)
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
ms.assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
description: ConferenceJoinTimeThresholds テーブルには、電話会議参加時間要約レポートによって使用される分類境界が含まれます。電話会議参加時間要約レポートは、ユーザーが問題なく電話会議に参加する目的で必要な時間を集計します。これらの時間値は、平均と、以下のカテゴリの 1 つの両方で報告されます。
ms.openlocfilehash: df247fc259d17fbb0ec263210216563b5b96b0e5
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60854181"
---
# <a name="conferencejointimethresholds-table-in-skype-for-business-server-2015"></a>ConferenceJoinTimeThresholds テーブル (Skype for Business Server 2015)
 
ConferenceJoinTimeThresholds テーブルには、電話会議参加時間要約レポートによって使用される分類境界が含まれます。電話会議参加時間要約レポートは、ユーザーが問題なく電話会議に参加する目的で必要な時間を集計します。これらの時間値は、平均と、以下のカテゴリの 1 つの両方で報告されます。
  
- 2 秒未満。
    
- 2 ～ 5 秒の間。
    
- 5 ～ 10 秒の間。
    
- 10 秒以上。
    
ConferenceJoinTimeThresholds テーブルには、2 秒、5 秒、および 10 秒の分類値が含まれます。
  
この表は、Microsoft Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**ThresholdId** <br/> |int  <br/> |Primary  <br/> |分類の一意識別子。  <br/> |
|**ThresholdValue** <br/> |int  <br/> || 分類の上限。有効な値は次のとおりです。 <br/>  2 <br/>  5 <br/>  10 <br/> |
   

