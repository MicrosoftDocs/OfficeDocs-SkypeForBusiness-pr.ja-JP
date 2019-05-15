---
title: PurgeSettings テーブル (QoE)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 31b85d1c-3f32-4f67-94bf-9389cdd282c5
description: PurgeSettings テーブルには、(そのとき) を指定する情報が含まれている高品質のエクスペリエンスの古いレコードは QoE データベースから自動的に削除されます。 パージに関連する情報もから取得できます、Skype 内でビジネス サーバー管理シェルの次のコマンドを実行して、注意してください。
ms.openlocfilehash: 2b78f066907d6d0763fab7faa9d378e51f3715fc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924788"
---
# <a name="purgesettings-table-qoe"></a>PurgeSettings テーブル (QoE)
 
PurgeSettings テーブルには、(そのとき) を指定する情報が含まれている高品質のエクスペリエンスの古いレコードは QoE データベースから自動的に削除されます。 パージに関連する情報もから取得できます、Skype 内でビジネス サーバー管理シェルの次のコマンドを実行して、注意してください。
  
```
Get-CsQoEConfiguration
```

このテーブルは、Microsoft Lync Server 2013 で導入されました。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**ID** <br/> |int  <br/> |Primary  <br/> |QoE のコレクションの一意の識別子は、設定を削除します。  <br/> |
|**EnablePurge** <br/> |bit  <br/> ||(1) は、Microsoft Lync Server 2013 を True に設定が QoE データベースから古いレコードを定期的に削除するができます。 パージ実行されます PurgeHour 設定で指定されたサントメ毎日。 場合は False (0) のレコード セットはデータベースから自動的にパージされません。 既定値は True です。  <br/> |
|**KeepQoEDataForDays** <br/> |int  <br/> ||(日) で、データベースからパージされる QoE レコードの保存期間を指定: QoE レコードがこの値よりも古いをデータベースから削除する場合は、パージを有効にすると、します。 既定値は、60 日間です。  <br/> |
|**PurgeHour** <br/> |int  <br/> ||データベースの削除を実行する日のローカル時間を指定します。 時刻は、午前 0 時 (12時 00分 AM) と 23 の 11時 00分 PM を表すを表す 0 から 24 時間制を使用して指定します。 1 日の時間を指定することのみできます注: 10 の (10時 00分 AM を示す) の値も可能ですが、10:30 (10時 30分 AM を示す) 10.5 の値は許可されていません。 既定値は 1 (1時 00分 AM) です。 データベースの削除を実行する日のローカル時間を指定します。 時刻は、午前 0 時 (12時 00分 AM) と 23 の 11時 00分 PM を表すを表す 0 から 24 時間制を使用して指定します。 1 日の時間を指定することのみできます注: 10 の (10時 00分 AM を示す) の値も可能ですが、10:30 (10時 30分 AM を示す) 10.5 の値は許可されていません。 既定値は 1 (1時 00分 AM) です。  <br/> |
   

