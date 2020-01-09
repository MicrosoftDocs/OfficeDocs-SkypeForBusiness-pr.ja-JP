---
title: PurgeSettings テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9ff2c8fc-4ae8-4f22-96a8-1f4d5eecbf2d
description: PurgeSettings テーブルには、古い通話の詳細レコードが CDR データベースから自動的に削除されるかどうかを指定する情報が含まれています。 次のコマンドを実行して、Skype for Business Server 2015 内からパージに関連する情報を取得することもできます。
ms.openlocfilehash: fbbd7908446fdb042c8fdfa2f0c8bec2d83b24d9
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992917"
---
# <a name="purgesettings-table"></a>PurgeSettings テーブル
 
PurgeSettings テーブルには、古い通話の詳細レコードが CDR データベースから自動的に削除されるかどうかを指定する情報が含まれています。 次のコマンドを実行して、Skype for Business Server 2015 内からパージに関連する情報を取得することもできます。
  
```PowerShell
Get-CsCdrConfiguration
```

管理者は、PurgeSettings テーブルを読み取り専用として扱う必要があります。呼び出しの詳細の消去設定への変更は、 [CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps)または[CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps)コマンドレットを使用して行う必要があります。
  
この表は、Microsoft Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**ID** <br/> |int  <br/> |Primary  <br/> |CDR 消去設定のコレクションの一意の識別子です。  <br/> |
|**EnablePurge** <br/> |bit  <br/> ||True に設定すると、Skype for Business Server 2015 は、古いレコードを CDR データベースから定期的に削除します。 パージは、PurgeHour 設定によって指定されたサントメで毎日行われます。 False (0) に設定すると、レコードはデータベースから自動的に削除されません。 既定値は True です。  <br/> |
|**KeepCallDetailForDays** <br/> |int  <br/> ||データベースから削除される CDR レコード (日数) を指定します。 [削除] が有効になっていると、この値よりも古い CDR レコードがデータベースから削除されます。 既定値は60日です。  <br/> |
|**KeepErrorReportForDays** <br/> |int  <br/> ||データベースから削除されるエラーレポートレコード (日数) を指定します。 [削除] を有効にすると、この値よりも古いエラーレポートレコードがデータベースから削除されます。 既定値は60日です。  <br/> |
|**PurgeHour** <br/> |int  <br/> ||データベースの消去が行われるローカル時刻を指定します。 時刻は24時間制を使用して指定します。0は午前0時 (12:00 AM)、23は 11:00 PM を表します。 時刻を指定できるのは1日の時間のみです。10の値 (10:00 AM) は許可されていますが、10.5 の 10:30 (10:30 AM を示す) は使用できません。 既定値は 2 (2:00 AM) です。  <br/> |
   

