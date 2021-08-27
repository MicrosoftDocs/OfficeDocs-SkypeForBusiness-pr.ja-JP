---
title: Set-CcApplianceDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/21/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 6da93ddb-ca99-4b5d-9b33-3d70659730b2
description: このSet-CcApplianceDirectoryは、ホスト サーバー上の作業ディレクトリをSkype for Business クラウド コネクタ エディションします。 すべての展開ファイルは、このディレクトリに格納されます。
ms.openlocfilehash: 0f64fbb52cd12020104e98051564379d1fbc4985
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58617673"
---
# <a name="set-ccappliancedirectory"></a>Set-CcApplianceDirectory
 
このSet-CcApplianceDirectoryは、ホスト サーバー上の作業ディレクトリをSkype for Business クラウド コネクタ エディションします。 すべての展開ファイルは、このディレクトリに格納されます。
  
```powershell
Set-CcApplianceDirectory[[-Path] <string>]
```

## <a name="examples"></a>例
<a name="Examples"> </a>

### <a name="example-1"></a>例 1

次の使用例は、ホスト サーバー上の作業ディレクトリを c:\cloudconnector\applianceroot に設定します。
  
```powershell
Set-CcApplianceDirectory -Path "c:\cloudconnector\applianceroot"
```

## <a name="parameters"></a>パラメーター
<a name="Examples"> </a>

|**パラメーター**|**Required**|**Type**|**説明**|
|:-----|:-----|:-----|:-----|
| パス <br/> | 必須 <br/> |System.String  <br/> | すべての展開ファイルが格納されるパスを指定します。 <br/> |
   
## <a name="input-types"></a>入力の種類
<a name="InputTypes"> </a>

なし。 このSet-CcApplianceDirectoryは、パイプライン処理された入力を受け付け取らない。
  
## <a name="return-types"></a>戻り値の種類
<a name="ReturnTypes"> </a>

なし
  
## <a name="see-also"></a>関連項目
<a name="ReturnTypes"> </a>

なし
  

