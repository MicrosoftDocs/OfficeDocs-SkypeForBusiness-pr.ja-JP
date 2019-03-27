---
title: ビジネス サーバー 2015 の Skype での ConferenceJoinTimeThresholds テーブル
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
description: ConferenceJoinTimeThresholds テーブルには、会議への参加時の概要レポートで使用される分類の境界が含まれています。 会議の参加時の要約レポートが正常には会議に参加するユーザーに必要な時間をまとめたもの平均とし、次のカテゴリのいずれかで、これらの時間の値が報告されます。
ms.openlocfilehash: d6fbae0d077719782b3e93c0fe008ee35ce3370e
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30895818"
---
# <a name="conferencejointimethresholds-table-in-skype-for-business-server-2015"></a>ビジネス サーバー 2015 の Skype での ConferenceJoinTimeThresholds テーブル
 
ConferenceJoinTimeThresholds テーブルには、会議への参加時の概要レポートで使用される分類の境界が含まれています。 会議の参加時の要約レポートが正常には会議に参加するユーザーに必要な時間をまとめたもの平均とし、次のカテゴリのいずれかで、これらの時間の値が報告されます。
  
- 2 秒未満です。
    
- 2 秒間、5 秒間です。
    
- 5 秒から 10 秒です。
    
- 10 秒より長くします。
    
ConferenceJoinTimeThresholds テーブルには、2 秒、5 秒から 10 秒の分類の値が含まれています。
  
このテーブルは、Microsoft Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**ThresholdId** <br/> |int  <br/> |Primary  <br/> |分類の一意の識別子です。  <br/> |
|**ThresholdValue** <br/> |int  <br/> || 分類の上限です。 有効な値は次のとおりです。 <br/>  2 <br/>  5 <br/>  10 <br/> |
   

