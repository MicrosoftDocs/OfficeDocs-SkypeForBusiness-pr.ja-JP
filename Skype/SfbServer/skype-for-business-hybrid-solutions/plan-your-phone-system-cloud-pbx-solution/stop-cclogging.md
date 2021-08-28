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
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: fee9eda7-ad15-40d2-b9fe-21c5462d3309
description: このStop-CcLoggingコマンドレットは、受信および送信の呼び出しログの生成を停止Skype for Business クラウド コネクタ エディションします。
ms.openlocfilehash: cfa07602f8465ce3c931010f835f52acc44e2ee2
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58580342"
---
# <a name="stop-cclogging"></a>Stop-CcLogging
 
このStop-CcLoggingコマンドレットは、受信および送信の呼び出しログの生成を停止Skype for Business クラウド コネクタ エディションします。
  
```powershell
Stop-CcLogging [-RemoveCache]
```

## <a name="examples"></a>例
<a name="Examples"> </a>

### <a name="example-1"></a>例 1

次の使用例は、着信および発信通話ログの生成を停止します。 
  
```powershell
Stop-CcLogging
```

### <a name="example-2"></a>例 2

次の例では、着信および発信呼び出しログの生成を停止し、キャッシュ ファイルをクリーンアップします。
  
```powershell
Stop-CcLogging -RemoveCache
```

## <a name="detailed-description"></a>解説
<a name="DetailedDescription"> </a>

このStop-CcLoggingは、アプライアンスでの着信および発信呼び出しのログ記録を停止します。 既定では、ログは 4 時間後に自動的に停止します。
  
## <a name="parameters"></a>パラメーター
<a name="DetailedDescription"> </a>

|**パラメーター**|**Required**|**Type**|**説明**|
|:-----|:-----|:-----|:-----|
| RemoveCache <br/> | 省略可 <br/> | System.Management.Automation.SwitchParameter <br/> |ログ キャッシュ ファイルを削除します。  <br/> |
   
## <a name="input-types"></a>入力の種類
<a name="InputTypes"> </a>

なし。 このStop-CcLoggingは、パイプライン処理された入力を受け付け取らない。
  
## <a name="return-types"></a>戻り値の種類
<a name="ReturnTypes"> </a>

なし
  
## <a name="see-also"></a>関連項目
<a name="ReturnTypes"> </a>

[Search-CcLog](search-cclog.md)
  
[Start-CcLogging](start-cclogging.md)
  

