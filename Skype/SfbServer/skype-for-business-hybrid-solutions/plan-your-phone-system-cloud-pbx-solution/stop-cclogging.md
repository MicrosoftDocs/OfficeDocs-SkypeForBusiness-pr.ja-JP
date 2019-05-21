---
title: Stop-CcLogging
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fee9eda7-ad15-40d2-b9fe-21c5462d3309
description: Stop-CcLogging コマンドレットは、Skype for Business Cloud Connector エディションのアプライアンスで、着信および発信の通話ログの生成を停止します。
ms.openlocfilehash: dcc62e8ec772912a8275f5321a6c91e28dde8c25
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286937"
---
# <a name="stop-cclogging"></a>Stop-CcLogging
 
Stop-CcLogging コマンドレットは、Skype for Business Cloud Connector エディションのアプライアンスで、着信および発信の通話ログの生成を停止します。
  
```
Stop-CcLogging [-RemoveCache]
```

## <a name="examples"></a>例
<a name="Examples"> </a>

### <a name="example-1"></a>例 1

次の例では、着信および発信の通話ログの生成を停止します。 
  
```
Stop-CcLogging
```

### <a name="example-2"></a>例 2

次の例では、着信および発信の通話ログの生成を停止して、キャッシュ ファイルをクリーン　アップします。
  
```
Stop-CcLogging -RemoveCache
```

## <a name="detailed-description"></a>解説
<a name="DetailedDescription"> </a>

Stop-CcLogging コマンドレットは、アプライアンスでの着信および発信の通話のログを停止します。 既定では、ログは 4 時間後に自動的に停止します。
  
## <a name="parameters"></a>パラメーター
<a name="DetailedDescription"> </a>

|**パラメーター**|**必須**|**型**|**説明**|
|:-----|:-----|:-----|:-----|
| RemoveCache <br/> | 省略可能 <br/> | System.Management.Automation.SwitchParameter <br/> |ログのキャッシュ ファイルを削除します。  <br/> |
   
## <a name="input-types"></a>入力の種類
<a name="InputTypes"> </a>

なし。Stop-CcLogging コマンドレットはパイプライン入力を受け入れません。
  
## <a name="return-types"></a>戻り値の種類
<a name="ReturnTypes"> </a>

なし
  
## <a name="see-also"></a>関連項目
<a name="ReturnTypes"> </a>

[Search-CcLog](search-cclog.md)
  
[Start-CcLogging](start-cclogging.md)
  

