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
description: PurgeSettings テーブルには、古い通話詳細レコードが CDR データベースから自動的に削除される場合 (およびいつ) を指定する情報が含まれます。 次のコマンドを実行して、2015 年 2015 年Skype for Business Serverから削除関連の情報を取得することもできます。
ms.openlocfilehash: 80e8e19a8df9a6f597967a71430686fd399d9bb2e8647989a410845af5b66e0e
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54343211"
---
# <a name="purgesettings-table"></a>PurgeSettings テーブル
 
PurgeSettings テーブルには、古い通話詳細レコードが CDR データベースから自動的に削除される場合 (およびいつ) を指定する情報が含まれます。 次のコマンドを実行して、2015 年 2015 年Skype for Business Serverから削除関連の情報を取得することもできます。
  
```PowerShell
Get-CsCdrConfiguration
```

管理者は PurgeSettings テーブルを読み取り専用として扱う必要があります。呼び出しの詳細の削除設定の変更は [、New-CsCdrConfiguration](/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) コマンドレットまたは [Set-CsCdrConfiguration](/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) コマンドレットのみを使用して行う必要があります。
  
この表は、Microsoft Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**Id** <br/> |整数  <br/> |Primary  <br/> |CDR パージ設定のコレクションの一意の識別子。  <br/> |
|**EnablePurge** <br/> |ビット  <br/> ||True (1) に設定すると、2015 Skype for Business Server古いレコードが CDR データベースから定期的に削除されます。 削除は、毎日、PurgeHour 設定で指定された時間に行われます。 False (0) に設定すると、レコードがデータベースから自動的に削除されることはありません。 既定値は True です。  <br/> |
|**KeepCallDetailForDays** <br/> |整数  <br/> ||データベースから削除される CDR レコードの年齢 (日数) を指定します。削除が有効な場合、この値より古い CDR レコードはデータベースから削除されます。 既定値は 60 日です。  <br/> |
|**KeepErrorReportForDays** <br/> |整数  <br/> ||データベースから削除されるエラー レポート レコードの日数を指定します。削除が有効な場合、この値より古いエラー レポート レコードはデータベースから削除されます。 既定値は 60 日です。  <br/> |
|**PurgeHour** <br/> |整数  <br/> ||データベース削除が行なうローカル時刻を指定します。 時刻は 24 時間時計を使用して指定され、0 は午前 0 時 (午前 12:00)、23 は午後 11:00 を表します。 1 日の時間のみを指定できますが、値 10 (午前 10:00 を示す) は許可されますが、10.5 の値 10:30 (午前 10:30 を示す) は使用できない点に注意してください。 既定値は 2 (午前 2 時) です。  <br/> |
