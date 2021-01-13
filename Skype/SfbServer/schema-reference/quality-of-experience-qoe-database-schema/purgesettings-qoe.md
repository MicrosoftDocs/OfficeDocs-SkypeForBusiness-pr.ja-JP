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
localization_priority: Normal
ms.assetid: 31b85d1c-3f32-4f67-94bf-9389cdd282c5
description: PurgeSettings テーブルには、古い QoE レコードを QoE データベースから自動的に削除するか、また削除する場合はどのタイミングで削除するかを指定する情報が含まれます。 削除に関連する情報は、次のコマンドを実行して Skype for Business Server 管理シェルから取得することもできます。
ms.openlocfilehash: eef723298b04aecf633368d767623488a53ac6ce
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815807"
---
# <a name="purgesettings-table-qoe"></a>PurgeSettings テーブル (QoE)
 
PurgeSettings テーブルには、古い QoE レコードを QoE データベースから自動的に削除するか、また削除する場合はどのタイミングで削除するかを指定する情報が含まれます。 削除に関連する情報は、次のコマンドを実行して Skype for Business Server 管理シェル内から取得することもできます。
  
```PowerShell
Get-CsQoEConfiguration
```

この表は、Microsoft Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**ID** <br/> |int  <br/> |Primary  <br/> |QoE の削除設定のコレクションに対する一意識別子。  <br/> |
|**EnablePurge** <br/> |bit  <br/> ||True (1) に設定すると、Microsoft Lync Server 2013 は QoE データベースから古いレコードを定期的に削除します。 削除は、毎日、PurgeHour 設定で指定された時間に行われます。 False (0) に設定すると、レコードがデータベースから自動的に削除されることはありません。 既定値は True です。  <br/> |
|**KeepQoEDataForDays** <br/> |int  <br/> ||データベースから削除する QoE レコードの保有期間を (日単位で) 指定します。削除が有効の場合、この値より古い QoE レコードはデータベースから削除されます。既定値は 60 日です。  <br/> |
|**PurgeHour** <br/> |int  <br/> ||データベースでの削除が行われる日のローカル時間を指定します。時刻は 24 時間制を使用して指定します。0 は夜中 12 時 (12:00 AM) を、23 は 11:00 PM を表します。指定できるのは時間のみです。(午前 10 時 00 分を意味する) 10 の値は指定できますが、(午前 10 時 30 分を意味する) 10.5 の値は指定できません。既定値は 1 です (AM 01:00:00)。  <br/> |
   

