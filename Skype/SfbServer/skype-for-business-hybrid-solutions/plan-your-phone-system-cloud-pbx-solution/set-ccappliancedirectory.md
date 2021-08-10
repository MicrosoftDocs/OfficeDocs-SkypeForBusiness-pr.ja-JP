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
localization_priority: Normal
ms.assetid: 6da93ddb-ca99-4b5d-9b33-3d70659730b2
description: このSet-CcApplianceDirectoryは、ホスト サーバー上の作業ディレクトリをSkype for Business クラウド コネクタ エディションします。 すべての展開ファイルは、このディレクトリに格納されます。
ms.openlocfilehash: 8ca6b8b8e175058e5f19c86a9dd1c6e0cf8a43ab6ef7a439eee4e09b5430f6a2
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54306598"
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

|**パラメーター**|**Required**|**型**|**説明**|
|:-----|:-----|:-----|:-----|
| Path <br/> | 必須 <br/> |System.String  <br/> | すべての展開ファイルが格納されるパスを指定します。 <br/> |
   
## <a name="input-types"></a>入力の種類
<a name="InputTypes"> </a>

なし。 このSet-CcApplianceDirectoryは、パイプライン処理された入力を受け付け取らない。
  
## <a name="return-types"></a>戻り値の種類
<a name="ReturnTypes"> </a>

なし
  
## <a name="see-also"></a>関連項目
<a name="ReturnTypes"> </a>

なし
  

