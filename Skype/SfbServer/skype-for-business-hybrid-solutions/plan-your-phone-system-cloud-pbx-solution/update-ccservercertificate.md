---
title: Update-CcServerCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/11/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cd2889c4-0eb1-4752-9274-93a5a68a8080
description: 'Update-CcServerCertificate コマンドレットは、Skype for Business Cloud Connector エディションの証明書の有効期限が近づいている場合またはすでに有効期限が切れている場合にそれを更新します。 '
ms.openlocfilehash: 34da35e607f8941da9c962386509f8a0b87ec122
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286881"
---
# <a name="update-ccservercertificate"></a>Update-CcServerCertificate
 
Update-CcServerCertificate コマンドレットは、Skype for Business Cloud Connector エディションの証明書の有効期限が近づいている場合またはすでに有効期限が切れている場合にそれを更新します。  
  
```
Update-CcServerCertificate [[-Roles] <array> {Cms | MS | Edge}]
```

## <a name="examples"></a>例
<a name="Examples"> </a>

### <a name="example-1"></a>例 1

次の例では、中央管理サーバー、仲介サーバーおよびエッジ サーバーの証明書の有効期限が近づいている場合またはすでに有効期限が切れている場合にそれらを更新します。
  
```
Update-CcServerCertificate
```

### <a name="example-2"></a>例 2

次の例では、仲介サーバーとエッジ サーバーの証明書の有効期限が近づいている場合またはすでに有効期限が切れている場合にそれらを更新します。
  
```
Update-CcServerCertificate-Roles @("MS", "Edge")
```

## <a name="detailed-description"></a>解説
<a name="DetailedDescription"> </a>

クラウドコネクタ中央管理ストア、仲介サーバー、エッジサーバーに発行された内部証明書は、証明機関サービスから発行されてから2年間有効です。 証明書の有効期限が近づいている場合またはすでに有効期限が切れている場合は、Update-CcServerCertificate コマンドレットを実行して、証明書を更新します。 
  
Cloud Connector 2.0 以降のリリースでは、このコマンドによって Renew-CcServerCertificate コマンドレットが置き換えられます。
  
## <a name="parameters"></a>パラメーター
<a name="DetailedDescription"> </a>

|**パラメーター**|**必須**|**型**|**説明**|
|:-----|:-----|:-----|:-----|
|役割  <br/> |省略可能  <br/> |System.Array  <br/> | Cloud Connector サーバーの役割のアレイ。 <br/> |
   
## <a name="input-types"></a>入力の種類
<a name="InputTypes"> </a>

なし。 Update-CcServerCertificate コマンドレットはパイプライン入力を受け入れません。
  
## <a name="return-types"></a>戻り値の種類
<a name="ReturnTypes"> </a>

なし
  
## <a name="see-also"></a>関連項目
<a name="ReturnTypes"> </a>

[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Renew-CcServerCertificate](renew-ccservercertificate.md)
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

