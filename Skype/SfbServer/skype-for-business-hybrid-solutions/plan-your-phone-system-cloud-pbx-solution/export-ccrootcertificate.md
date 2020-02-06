---
title: Export-CcRootCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/20/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1499e33c-6a7c-46b9-b9a1-f78d7853b45d
description: 'Export-CcRootCertificate コマンドレットはルート CA 証明書を Skype for Business Cloud Connector エディションのホスト サーバー上のローカル ファイルにエクスポートします。 '
ms.openlocfilehash: 2b252eba4688deb790d85b0c3663b09a9e85e7b9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41800917"
---
# <a name="export-ccrootcertificate"></a>Export-CcRootCertificate
 
Export-CcRootCertificate コマンドレットはルート CA 証明書を Skype for Business Cloud Connector エディションのホスト サーバー上のローカル ファイルにエクスポートします。  
  
```powershell
Export-CcRootCertificate [[-Path] <string>]
```

## <a name="examples"></a>例
<a name="Examples"> </a>

### <a name="example-1"></a>例 1

次の例では、Path パラメータをファイル パスではなくディレクトリ パスで設定します。 これによって、ファイル c:\test\CCERootCertificates.p7b が生成されます。
  
```powershell
Export-CcRootCertificate -Path "C:\test" 
```

## <a name="detailed-description"></a>解説
<a name="DetailedDescription"> </a>

Export-CcRootCertificate コマンドレットを使用すると、ルートおよび中間証明書をファイル パスに保存することができます。 これは、障害復旧シナリオの場合に役立ちます。  
  
## <a name="parameters"></a>パラメーター
<a name="DetailedDescription"> </a>

|**パラメーター**|**必須**|**種類**|**説明**|
|:-----|:-----|:-----|:-----|
|Path  <br/> |必須  <br/> |System.String  <br/> |証明書が保存されるファイル パス。   <br/> |
   
## <a name="input-types"></a>入力の種類
<a name="InputTypes"> </a>

なし。 Export-CcRootCertificate コマンドレットはパイプライン入力を受け入れません。  
  
## <a name="return-types"></a>戻り値の種類
<a name="ReturnTypes"> </a>

なし
  
## <a name="see-also"></a>関連項目
<a name="ReturnTypes"> </a>

なし
  

