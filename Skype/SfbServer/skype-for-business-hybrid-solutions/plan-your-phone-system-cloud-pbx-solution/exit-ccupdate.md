---
title: Exit-CcUpdate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 463dce1e-fb60-487d-bcf1-69e7b03ecd14
description: Exit-CcUpdate コマンドレットは、Skype for Business Cloud Connector エディションのホスト サーバーでの更新のメンテナンス モードを終了します。
ms.openlocfilehash: b3558a81e1d4bc6c833cca157c2b31f2f252b595
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287427"
---
# <a name="exit-ccupdate"></a>Exit-CcUpdate
 
Exit-CcUpdate コマンドレットは、Skype for Business Cloud Connector エディションのホスト サーバーでの更新のメンテナンス モードを終了します。 
  
このコマンドレットは Skype for Business Cloud Connector エディション 1.4.1、1.4.2 に適用されます。 
  
```
Exit-CcUpdate
```

## <a name="parameters"></a>パラメーター

なし
  
## <a name="examples"></a>例
<a name="Examples"> </a>

### <a name="example-1"></a>例 1

次のコマンドは、アプライアンスを実稼働モードに戻って実行する状態にします。 
  
```
Exit-CcUpdate
```

## <a name="detailed-description"></a>解説
<a name="DetailedDescription"> </a>

Enter-CcUpdate コマンドレットを指定してメンテナンス モードにしたアプライアンスがある場合、Exit-CcUpdate コマンドレットは、これらのアプライアンスを実稼働モードに戻します。 
  
アプライアンスをメンテナンス モードにすることの詳細については、Enter-CcUpdate を参照してください。
  
## <a name="input-types"></a>入力の種類
<a name="InputTypes"> </a>

なし。Exit-CcUpdate　コマンドレットはパイプライン入力を受け入れません。
  
## <a name="return-types"></a>戻り値の種類
<a name="ReturnTypes"> </a>

なし 
  
## <a name="see-also"></a>関連項目
<a name="ReturnTypes"> </a>

[Enter-CcUpdate](enter-ccupdate.md)
  

