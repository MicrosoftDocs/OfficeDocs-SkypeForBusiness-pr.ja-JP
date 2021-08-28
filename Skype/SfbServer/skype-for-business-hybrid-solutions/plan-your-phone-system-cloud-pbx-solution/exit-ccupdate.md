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
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 463dce1e-fb60-487d-bcf1-69e7b03ecd14
description: このExit-CcUpdateコマンドレットは、ホスト サーバー上の更新Skype for Business クラウド コネクタ エディション終了します。
ms.openlocfilehash: 11499950a3332de31fe045ea23c1aa8f567da072
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58625019"
---
# <a name="exit-ccupdate"></a>Exit-CcUpdate
 
このExit-CcUpdateコマンドレットは、ホスト サーバー上の更新Skype for Business クラウド コネクタ エディション終了します。 
  
このコマンドレットは、Skype for Business クラウド コネクタ エディション 1.4.1、1.4.2 に適用されます。 
  
```powershell
Exit-CcUpdate
```

## <a name="parameters"></a>パラメーター

なし
  
## <a name="examples"></a>例
<a name="Examples"> </a>

### <a name="example-1"></a>例 1

次のコマンドは、実行するアプライアンスを実稼働モードに戻します。 
  
```powershell
Exit-CcUpdate
```

## <a name="detailed-description"></a>解説
<a name="DetailedDescription"> </a>

Enter-CcUpdate コマンドレットを指定してメンテナンス モードにしたアプライアンスがある場合、Exit-CcUpdate コマンドレットはこれらを運用モードに戻します。 
  
アプライアンスをメンテナンス モードに設定する方法の詳細については、「Enter-CcUpdate」を参照してください。
  
## <a name="input-types"></a>入力の種類
<a name="InputTypes"> </a>

なし。 このExit-CcUpdateは、パイプライン処理された入力を受け付け取らない。
  
## <a name="return-types"></a>戻り値の種類
<a name="ReturnTypes"> </a>

なし 
  
## <a name="see-also"></a>関連項目
<a name="ReturnTypes"> </a>

[Enter-CcUpdate](enter-ccupdate.md)
  

