---
title: 更新 CcServerCertificate
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/18/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7844b55e-b7e9-4599-9962-f0322728405a
description: Renew-CcServerCertificate コマンドレットは、Skype for Business Cloud Connector エディションの証明書の有効期限が近づいている場合またはすでに有効期限が切れている場合にそれを更新します。 Cloud Connector  2.0 以降のリリースにおいて、このコマンドは Update-CcServerCertificate に変更されました。
ms.openlocfilehash: 3d895a24c4cc8b400aa48ce394324435cfbb3979
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="renew-ccservercertificate"></a>更新 CcServerCertificate
 
Renew-CcServerCertificate コマンドレットは、Skype for Business Cloud Connector エディションの証明書の有効期限が近づいている場合またはすでに有効期限が切れている場合にそれを更新します。 Cloud Connector  2.0 以降のリリースにおいて、このコマンドは Update-CcServerCertificate に変更されました。 
  
```
Renew-CcServerCertificate [[-Roles] <array> {Cms | MS | Edge}]
```

## <a name="examples"></a>例
<a name="Examples"> </a>

### <a name="example-1"></a>例 1

次の例では、中央管理サーバー、仲介サーバーおよびエッジ サーバーの証明書の有効期限が近づいている場合またはすでに有効期限が切れている場合にそれらを更新します。
  
```
Renew-CcServerCertificate
```

### <a name="example-2"></a>例 2

次の例では、仲介サーバーとエッジ サーバーの証明書の有効期限が近づいている場合またはすでに有効期限が切れている場合にそれらを更新します。
  
```
Renew-CcServerCertificate-Roles @("MS", "Edge")
```

## <a name="detailed-description"></a>解説
<a name="DetailedDescription"> </a>

中央管理ストア、仲介サーバー、およびエッジ サーバーに内部証明書が発行されたクラウドのコネクタは、証明機関サービスから発行され、後の 2 年間有効です。 証明書の有効期限が近づいている場合またはすでに有効期限が切れている場合は、Renew-CcServerCertificate コマンドレットを実行して、証明書を更新します。 
  
## <a name="parameters"></a>パラメーター
<a name="DetailedDescription"> </a>

|**パラメーター**|**必須**|**タイプ**|**説明**|
|:-----|:-----|:-----|:-----|
|役割  <br/> |省略可能  <br/> |System.Array  <br/> | Cloud Connector サーバーの役割のアレイ。 <br/> |
   
## <a name="input-types"></a>入力の種類
<a name="InputTypes"> </a>

なし。Renew-CcServerCertificate コマンドレットはパイプライン入力を受け入れません。
  
## <a name="return-types"></a>戻り値の種類
<a name="ReturnTypes"> </a>

なし
  
## <a name="see-also"></a>関連項目
<a name="ReturnTypes"> </a>

[リセット CcCACertificate](reset-cccacertificate.md)
  
[更新 CcServerCertificate](renew-ccservercertificate.md)
  
[エクスポート CcRootCertificate](export-ccrootcertificate.md)
  

