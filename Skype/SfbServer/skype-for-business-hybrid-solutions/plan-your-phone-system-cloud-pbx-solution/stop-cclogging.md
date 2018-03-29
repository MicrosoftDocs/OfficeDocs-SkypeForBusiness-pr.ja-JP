---
title: Stop CcLogging
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fee9eda7-ad15-40d2-b9fe-21c5462d3309
description: Stop CcLogging コマンドレットでは、ビジネス クラウド コネクタ ・ エディションのアプライアンス用の Skype の着信および発信呼び出しのログの生成を停止します。
ms.openlocfilehash: abecc5acc6a454b2965fbf79caadb23f2256e4cd
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="stop-cclogging"></a>Stop CcLogging
 
Stop CcLogging コマンドレットでは、ビジネス クラウド コネクタ ・ エディションのアプライアンス用の Skype の着信および発信呼び出しのログの生成を停止します。
  
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

Stop-CcLogging コマンドレットは、アプライアンスでの着信および発信の通話のログを停止します。既定では、ログは 4 時間後に自動的に停止します。
  
## <a name="parameters"></a>パラメーター
<a name="DetailedDescription"> </a>

|**パラメーター**|**必須**|**タイプ**|**説明**|
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

[検索 CcLog](search-cclog.md)
  
[開始 CcLogging](start-cclogging.md)
  

