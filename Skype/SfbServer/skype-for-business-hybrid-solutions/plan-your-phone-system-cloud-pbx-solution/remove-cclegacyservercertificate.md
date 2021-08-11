---
title: Remove-CcLegacyServerCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/22/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ff21cecb-5035-48fd-9705-11ea81ce7df6
description: Remove-CcLegacyServerCertificate コマンドレットは、Renew-CcCACertificate または Renew CcServerCertificate コマンドレットを実行した後、中央管理ストア、仲介サーバー、およびエッジ サーバー上の従来のサーバー証明書を削除します。
ms.openlocfilehash: 6c1665d0c21e5afd25ed630fc1da4f1987264d9325fec2058981fe91a1edc0bb
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54288735"
---
# <a name="remove-cclegacyservercertificate"></a>Remove-CcLegacyServerCertificate
 
Remove-CcLegacyServerCertificate コマンドレットは、Renew-CcCACertificate または Renew CcServerCertificate コマンドレットを実行した後、中央管理ストア、仲介サーバー、およびエッジ サーバー上の従来のサーバー証明書を削除します。
  
```powershell
Remove-CcLegacyServerCertificate [[-Roles] <array> {Cms | MS | Edge}] 
```

## <a name="examples"></a>例
<a name="Examples"> </a>

### <a name="example-1"></a>例 1

次の例では、証明書を更新した後、中央管理ストア、仲介サーバー、エッジ サーバーに対して発行された従来の証明書を削除します。
  
```powershell
Remove-CcLegacyServerCertificate
```

### <a name="example-2"></a>例 2

次の例では、証明書を更新した後に仲介サーバーとエッジ サーバー用に発行された証明書を削除します。 
  
```powershell
Remove-CcLegacyServerCertificate -Roles @("MS", "Edge") 
```

## <a name="parameters"></a>パラメーター
<a name="Examples"> </a>

|**パラメーター**|**Required**|**型**|**説明**|
|:-----|:-----|:-----|:-----|
| Roles <br/> |省略可能  <br/> |System.Array  <br/> | クラウド コネクタ サーバーの役割の配列。 <br/> |
   
## <a name="input-types"></a>入力の種類
<a name="InputTypes"> </a>

なし。 このRemove-CcLegacyServerCertificateは、パイプライン処理された入力を受け付け取らない。
  
## <a name="return-types"></a>戻り値の種類
<a name="ReturnTypes"> </a>

なし
  
## <a name="see-also"></a>関連項目
<a name="ReturnTypes"> </a>

[Renew-CcServerCertificate](renew-ccservercertificate.md)
  
[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Renew-CcCACertificate](renew-cccacertificate.md)
  
[Update-CcCACertificate](update-cccacertificate.md)
  

