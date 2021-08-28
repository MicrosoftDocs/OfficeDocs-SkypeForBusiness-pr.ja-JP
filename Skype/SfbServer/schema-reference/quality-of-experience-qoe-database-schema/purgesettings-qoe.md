---
title: PurgeSettings テーブル (QoE)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 31b85d1c-3f32-4f67-94bf-9389cdd282c5
description: PurgeSettings テーブルには、古い QoE レコードを QoE データベースから自動的に削除するか、また削除する場合はどのタイミングで削除するかを指定する情報が含まれます。 次のコマンドを実行して、管理シェル内から削除関連Skype for Business Server取得することもできます。
ms.openlocfilehash: eb5b0570073498580ec2ad468ea50474e0246b07
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58620823"
---
# <a name="purgesettings-table-qoe"></a>PurgeSettings テーブル (QoE)
 
PurgeSettings テーブルには、古い QoE レコードを QoE データベースから自動的に削除するか、また削除する場合はどのタイミングで削除するかを指定する情報が含まれます。 次のコマンドを実行して、管理シェル内から削除関連Skype for Business Server取得することもできます。
  
```PowerShell
Get-CsQoEConfiguration
```

この表は、Microsoft Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**ID** <br/> |int  <br/> |Primary  <br/> |QoE の削除設定のコレクションに対する一意識別子。  <br/> |
|**EnablePurge** <br/> |ビット  <br/> ||True に設定すると (1) Microsoft Lync Server 2013 は、古いレコードを QoE データベースから定期的に削除します。 削除は、毎日、PurgeHour 設定で指定された時間に行われます。 False (0) に設定すると、レコードがデータベースから自動的に削除されることはありません。 既定値は True です。  <br/> |
|**KeepQoEDataForDays** <br/> |int  <br/> ||データベースから削除する QoE レコードの保有期間を (日単位で) 指定します。削除が有効の場合、この値より古い QoE レコードはデータベースから削除されます。既定値は 60 日です。  <br/> |
|**PurgeHour** <br/> |int  <br/> ||データベースでの削除が行われる日のローカル時間を指定します。時刻は 24 時間制を使用して指定します。0 は夜中 12 時 (12:00 AM) を、23 は 11:00 PM を表します。指定できるのは時間のみです。(午前 10 時 00 分を意味する) 10 の値は指定できますが、(午前 10 時 30 分を意味する) 10.5 の値は指定できません。既定値は 1 です (AM 01:00:00)。  <br/> |
   

