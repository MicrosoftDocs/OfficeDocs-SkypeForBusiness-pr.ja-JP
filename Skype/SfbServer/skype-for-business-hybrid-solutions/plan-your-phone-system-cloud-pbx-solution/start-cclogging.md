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
description: Start-CcLogging コマンドレットは、Skype for Business Cloud Connector エディションのアプライアンスで、着信および発信の通話ログを生成します。
ms.openlocfilehash: bf84b55484e7f1d4f557730408676e337063a040
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824171"
---
# <a name="start-cclogging"></a>Start-CcLogging
 
Start-CcLogging コマンドレットは、Skype for Business Cloud Connector エディションのアプライアンスで、着信および発信の通話ログを生成します。 
  
```powershell
Start-CcLogging
```

## <a name="parameters"></a>パラメーター

なし
  
## <a name="examples"></a>例
<a name="Examples"> </a>

### <a name="example-1"></a>例 1

次の例では、着信および発信の通話ログを生成します。
  
```powershell
Start-CcLogging
```

## <a name="detailed-description"></a>解説
<a name="DetailedDescription"> </a>

スタート-CcLogging コマンドレットを使用すると、管理者は、クラウドコネクタアプライアンスでの着信通話と発信通話の記録を開始することができます。 既定では、ログは 4 時間後に自動的に停止します。
  
## <a name="input-types"></a>入力の種類
<a name="InputTypes"> </a>

なし。Start-CcLogging コマンドレットはパイプライン入力を受け入れません。
  
## <a name="return-types"></a>戻り値の種類
<a name="ReturnTypes"> </a>

なし
  
## <a name="see-also"></a>関連項目
<a name="ReturnTypes"> </a>

[Search-CcLog](search-cclog.md)
  
[Stop-CcLogging](stop-cclogging.md)
  

