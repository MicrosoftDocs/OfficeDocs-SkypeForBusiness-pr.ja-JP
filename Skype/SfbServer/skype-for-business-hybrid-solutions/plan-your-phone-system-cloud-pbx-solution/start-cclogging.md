---
title: Start-CcLogging
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
localization_priority: Normal
ms.assetid: 01b62253-2aaf-43ed-9d63-804e31edc522
description: このStart-CcLoggingコマンドレットは、アプライアンスの着信および発信呼び出しSkype for Business クラウド コネクタ エディションします。
ms.openlocfilehash: c1e78f19a0df22749480b21410d3bcfcdba54f429ef1c8afb48467edd0ee7dbc
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54329322"
---
# <a name="start-cclogging"></a>Start-CcLogging
 
このStart-CcLoggingコマンドレットは、アプライアンスの着信および発信呼び出しSkype for Business クラウド コネクタ エディションします。 
  
```powershell
Start-CcLogging
```

## <a name="parameters"></a>パラメーター

なし
  
## <a name="examples"></a>例
<a name="Examples"> </a>

### <a name="example-1"></a>例 1

次の例では、着信通話ログと発信通話ログを生成します。
  
```powershell
Start-CcLogging
```

## <a name="detailed-description"></a>解説
<a name="DetailedDescription"> </a>

このStart-CcLoggingは、管理者がクラウド コネクタ アプライアンスで着信および発信呼び出しのログ記録を開始する方法を提供します。 既定では、ログは 4 時間後に自動的に停止します。
  
## <a name="input-types"></a>入力の種類
<a name="InputTypes"> </a>

なし。 このStart-CcLoggingは、パイプライン処理された入力を受け付け取らない。
  
## <a name="return-types"></a>戻り値の種類
<a name="ReturnTypes"> </a>

なし
  
## <a name="see-also"></a>関連項目
<a name="ReturnTypes"> </a>

[Search-CcLog](search-cclog.md)
  
[Stop-CcLogging](stop-cclogging.md)
  

