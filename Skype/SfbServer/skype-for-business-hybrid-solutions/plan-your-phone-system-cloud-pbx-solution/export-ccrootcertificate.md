---
title: エクスポート CcRootCertificate
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/20/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1499e33c-6a7c-46b9-b9a1-f78d7853b45d
description: Export-CcRootCertificate コマンドレットはルート CA 証明書を Skype for Business Cloud Connector エディションのホスト サーバー上のローカル ファイルにエクスポートします。
ms.openlocfilehash: 9af3701fd89cf881b4f966c2b00500ad4e55bc9b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="export-ccrootcertificate"></a>エクスポート CcRootCertificate
 
Export-CcRootCertificate コマンドレットはルート CA 証明書を Skype for Business Cloud Connector エディションのホスト サーバー上のローカル ファイルにエクスポートします。 
  
```
Export-CcRootCertificate [[-Path] <string>]
```

## <a name="examples"></a>例
<a name="Examples"> </a>

### <a name="example-1"></a>例 1

次の例では、Path パラメータをファイル パスではなくディレクトリ パスで設定します。 これによって、ファイル c:\test\CCERootCertificates.p7b が生成されます。
  
```
Export-CcRootCertificate -Path "C:\test" 
```

## <a name="detailed-description"></a>解説
<a name="DetailedDescription"> </a>

Export-CcRootCertificate コマンドレットを使用すると、ルートおよび中間証明書をファイル パスに保存することができます。 これは、障害復旧シナリオの場合に役立ちます。 
  
## <a name="parameters"></a>パラメーター
<a name="DetailedDescription"> </a>

|**パラメーター**|**必須**|**タイプ**|**説明**|
|:-----|:-----|:-----|:-----|
| Path  <br/> |必須  <br/> |System.String  <br/> |証明書が保存されるファイル パス。  <br/> |
   
## <a name="input-types"></a>入力の種類
<a name="InputTypes"> </a>

なし。 Export-CcRootCertificate コマンドレットはパイプライン入力を受け入れません。 
  
## <a name="return-types"></a>戻り値の種類
<a name="ReturnTypes"> </a>

なし
  
## <a name="see-also"></a>関連項目
<a name="ReturnTypes"> </a>

なし
  

