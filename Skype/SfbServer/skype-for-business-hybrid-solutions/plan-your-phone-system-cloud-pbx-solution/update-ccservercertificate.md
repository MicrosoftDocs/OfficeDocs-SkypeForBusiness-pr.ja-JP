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
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: cd2889c4-0eb1-4752-9274-93a5a68a8080
description: このUpdate-CcServerCertificateコマンドレットは、有効期限が近い、または既に有効期限が切れているSkype for Business クラウド コネクタ エディションの証明書を更新します。
ms.openlocfilehash: 1e8afb05d691a1e3e696b619c816cfc45dd26f1e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58623379"
---
# <a name="update-ccservercertificate"></a>Update-CcServerCertificate
 
このUpdate-CcServerCertificateコマンドレットは、有効期限が近い、または既に有効期限が切れているSkype for Business クラウド コネクタ エディションの証明書を更新します。 
  
```powershell
Update-CcServerCertificate [[-Roles] <array> {Cms | MS | Edge}]
```

## <a name="examples"></a>例
<a name="Examples"> </a>

### <a name="example-1"></a>例 1

次の使用例は、証明書の有効期限が近い、または既に有効期限が切れている場合に、中央管理ストア、仲介サーバー、およびエッジ サーバーの証明書を更新します。
  
```powershell
Update-CcServerCertificate
```

### <a name="example-2"></a>例 2

次の例では、仲介サーバーとエッジ サーバーの証明書が有効期限が近い場合、または既に有効期限が切れている場合に更新します。
  
```powershell
Update-CcServerCertificate-Roles @("MS", "Edge")
```

## <a name="detailed-description"></a>解説
<a name="DetailedDescription"> </a>

中央管理ストア、仲介サーバー、エッジ サーバーに発行されたクラウド コネクタ内部証明書は、証明機関サービスから発行された後、2 年間有効です。 証明書の有効期限が近い場合、または既に有効期限が切れている場合は、Update-CcServerCertificateコマンドレットを実行して証明書を更新します。 
  
このコマンドは、Cloud Connector 2.0 Renew-CcServerCertificate以降のリリースのコマンドレットを置き換えるコマンドです。
  
## <a name="parameters"></a>パラメーター
<a name="DetailedDescription"> </a>

|**パラメーター**|**Required**|**Type**|**説明**|
|:-----|:-----|:-----|:-----|
|役割  <br/> |オプション  <br/> |System.Array  <br/> | クラウド コネクタ サーバーの役割の配列。 <br/> |
   
## <a name="input-types"></a>入力の種類
<a name="InputTypes"> </a>

なし。 このUpdate-CcServerCertificateは、パイプライン処理された入力を受け付け取らない。
  
## <a name="return-types"></a>戻り値の種類
<a name="ReturnTypes"> </a>

なし
  
## <a name="see-also"></a>関連項目
<a name="ReturnTypes"> </a>

[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Renew-CcServerCertificate](renew-ccservercertificate.md)
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

