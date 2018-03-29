---
title: PurgeSettings テーブル
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9ff2c8fc-4ae8-4f22-96a8-1f4d5eecbf2d
description: PurgeSettings テーブルには、(そのとき) を指定する情報が含まれている旧式の呼び出しの詳細レコードが CDR データベースから自動的に削除されます。 パージに関連する情報もから取得できます、Skype 内でビジネス サーバー 2015 の次のコマンドを実行して、注意してください。
ms.openlocfilehash: a28ac592fb1d5d2001e7f297f37fdc1938f25643
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="purgesettings-table"></a>PurgeSettings テーブル
 
PurgeSettings テーブルには、(そのとき) を指定する情報が含まれている旧式の呼び出しの詳細レコードが CDR データベースから自動的に削除されます。 パージに関連する情報もから取得できます、Skype 内でビジネス サーバー 2015 の次のコマンドを実行して、注意してください。
  
```
Get-CsCdrConfiguration
```

管理者は、読み取り専用で PurgeSettings テーブルを扱う必要があります: への呼び出しの詳細のパージ設定のみ変更してください[新規 CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps)または[セット CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps)コマンドレットを使用します。
  
このテーブルは、Microsoft Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**キーまたはインデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**Id** <br/> |int  <br/> |Primary  <br/> |CDR のコレクションの一意の識別子は、設定を削除します。  <br/> |
|**EnablePurge** <br/> |bit  <br/> ||CDR データベースからレコードを古い設定すると (1) Skype ビジネス サーバー 2015 の true を設定するのには定期的に削除します。 パージ実行されます PurgeHour 設定で指定されたサントメ毎日。 場合は False (0) のレコード セットはデータベースから自動的にパージされません。 既定値は True です。  <br/> |
|**KeepCallDetailForDays** <br/> |int  <br/> ||データベースから削除されます (日) での CDR レコードの保存期間を指定: CDR レコードがこの値よりも古いをデータベースから削除する場合は、パージを有効にすると、します。 既定値は、60 日間です。  <br/> |
|**KeepErrorReportForDays** <br/> |int  <br/> ||データベースから削除されます (日) でエラー レポート レコードの保存期間を指定します。 エラー レポートのレコードがこの値よりも古いをデータベースから削除する場合は、パージを有効にすると、します。 既定値は、60 日間です。  <br/> |
|**PurgeHour** <br/> |int  <br/> ||データベースの削除を実行する日のローカル時間を指定します。 時刻は、午前 0 時 (12時 00分 AM) と 23 の 11時 00分 PM を表すを表す 0 から 24 時間制を使用して指定します。 1 日の時間を指定することのみできます注: 10 の (10時 00分 AM を示す) の値も可能ですが、10:30 (10時 30分 AM を示す) 10.5 の値は許可されていません。 既定値は、2 (2時 00分 AM) です。  <br/> |
   

