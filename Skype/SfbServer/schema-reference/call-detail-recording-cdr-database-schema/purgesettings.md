---
title: PurgeSettings テーブル
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9ff2c8fc-4ae8-4f22-96a8-1f4d5eecbf2d
description: PurgeSettings テーブルには、古い通話詳細記録を CDR データベースから自動的に削除する (およびいつ) か指定する情報が含まれます。 削除に関連する情報は、次のコマンドを実行して Skype for Business Server 2015 内から取得することもできます。
ms.openlocfilehash: c90c36dc91eaaac6fe38c6eea8e2a5617264e200
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823167"
---
# <a name="purgesettings-table"></a>PurgeSettings テーブル
 
PurgeSettings テーブルには、古い通話詳細記録を CDR データベースから自動的に削除する (およびいつ) か指定する情報が含まれます。 削除に関連する情報は、次のコマンドを実行して Skype for Business Server 2015 内から取得することもできます。
  
```PowerShell
Get-CsCdrConfiguration
```

管理者は PurgeSettings テーブルを読み取り専用として扱う必要があります。通話詳細消去設定の変更は [、New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) または [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) コマンドレットを使用する必要があります。
  
この表は、Microsoft Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**Id** <br/> |int  <br/> |Primary  <br/> |CDR 消去設定のコレクションの一意の識別子。  <br/> |
|**EnablePurge** <br/> |bit  <br/> ||True (1) に設定すると、Skype for Business Server 2015 は CDR データベースから古いレコードを定期的に削除します。 削除は、毎日、PurgeHour 設定で指定された時間に行われます。 False (0) に設定すると、レコードがデータベースから自動的に削除されることはありません。 既定値は True です。  <br/> |
|**KeepCallDetailForDays** <br/> |int  <br/> ||データベースから削除する CDR レコードの保存時間 (日数) を指定します。削除が有効な場合、この値より古い CDR レコードはデータベースから削除されます。 既定値は 60 日です。  <br/> |
|**KeepErrorReportForDays** <br/> |int  <br/> ||データベースから削除するエラー報告レコードの保存時間 (日数) を指定します。削除が有効な場合、この値より古いエラー報告レコードはデータベースから削除されます。 既定値は 60 日です。  <br/> |
|**PurgeHour** <br/> |int  <br/> ||データベースの削除を行う現地時刻を指定します。 時刻は 24 時間形式で指定され、0 は午前 0 時 (午前 12:00) を表し、23 は午後 11:00 を表します。 1 日の時間のみを指定できます。値 10 (10:00 AM を示す) は許可されますが、10.5 の 10:30 (10:30 AM を示す) の値は許可されません。 既定値は 2 (午前 2 時) です。  <br/> |
   

