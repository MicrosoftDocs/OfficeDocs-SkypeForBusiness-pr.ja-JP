---
title: PurgeSettings table (QoE)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 31b85d1c-3f32-4f67-94bf-9389cdd282c5
description: PurgeSettings テーブルには、古い品質のエクスペリエンスレコードが QoE データベースから自動的に削除されるかどうかを指定する情報が含まれています。 次のコマンドを実行して、Skype for Business Server 管理シェルからパージに関連する情報を取得することもできます。
ms.openlocfilehash: ec957a445c59020e8909beeb8cb3dcd12f662d68
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294776"
---
# <a name="purgesettings-table-qoe"></a>PurgeSettings table (QoE)
 
PurgeSettings テーブルには、古い品質のエクスペリエンスレコードが QoE データベースから自動的に削除されるかどうかを指定する情報が含まれています。 次のコマンドを実行して、Skype for Business Server 管理シェルからパージに関連する情報を取得することもできます。
  
```
Get-CsQoEConfiguration
```

この表は、Microsoft Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**ID** <br/> |int  <br/> |Primary  <br/> |QoE の消去設定のコレクションの一意の識別子です。  <br/> |
|**EnablePurge** <br/> |bit  <br/> ||True (1) に設定すると、Microsoft Lync Server 2013 は、古いレコードを QoE データベースから定期的に削除します。 パージは、PurgeHour 設定によって指定されたサントメで毎日行われます。 False (0) に設定すると、レコードはデータベースから自動的に削除されません。 既定値は True です。  <br/> |
|**KeepQoEDataForDays** <br/> |int  <br/> ||データベースから削除される QoE レコード (日数) を指定します。 [削除] が有効になっていると、この値よりも古い QoE レコードはデータベースから削除されます。 既定値は60日です。  <br/> |
|**PurgeHour** <br/> |int  <br/> ||データベースの消去が行われるローカル時刻を指定します。 時刻は24時間制を使用して指定します。0は午前0時 (12:00 AM)、23は 11:00 PM を表します。 時刻を指定できるのは1日の時間のみです。10の値 (10:00 AM) は許可されていますが、10.5 の 10:30 (10:30 AM を示す) は使用できません。 既定値は 1 (1:00 AM) です。 データベースの消去が行われるローカル時刻を指定します。 時刻は24時間制を使用して指定します。0は午前0時 (12:00 AM)、23は 11:00 PM を表します。 時刻を指定できるのは1日の時間のみです。10の値 (10:00 AM) は許可されていますが、10.5 の 10:30 (10:30 AM を示す) は使用できません。 既定値は 1 (1:00 AM) です。  <br/> |
   

