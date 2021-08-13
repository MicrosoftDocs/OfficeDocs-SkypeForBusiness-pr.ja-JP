---
title: Reset-CcCACertificate
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
ms.assetid: 5ada7e55-df9b-4b4e-b752-2468f4e28b8a
description: このReset-CcCACertificateコマンドレットは、証明機関サービス ADサーバーを再インストールして、新しいルート CA 証明書を作成します。
ms.openlocfilehash: 8e0cb93e6f10f28df28213579674a6cda6e7e2cd1cf201319f77dc26be69de80
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54340723"
---
# <a name="reset-cccacertificate"></a>Reset-CcCACertificate
 
このReset-CcCACertificateコマンドレットは、証明機関サービス ADサーバーを再インストールして、新しいルート CA 証明書を作成します。
  
```powershell
Reset-CcCACertificate
```

## <a name="parameters"></a>パラメーター

なし
  
## <a name="examples"></a>例
<a name="Examples"> </a>

### <a name="example-1"></a>例 1

次の使用例は、証明機関サービス ADサーバーを再インストールして、新しいルート CA 証明書を作成します。
  
```powershell
Reset-CcCACertificate
```

## <a name="detailed-description"></a>解説
<a name="DetailedDescription"> </a>

ルート CA 証明書が侵害された場合、またはセキュリティ保護されなくなった場合は、ルート CA 証明書と、ルート CA によって発行されたすべての証明書を更新する必要があります。 Reset-CcCACertificateコマンドレットは、すべての証明書を取り消し、証明機関をアンインストールして再インストールし、古い証明機関サービスに関連付けのすべての証明書をクリーンアップします。 
  
詳細については、「Cloud Connector の展開のトラブルシューティング」の「CMS、仲介サーバー、エッジ サーバーに発行された証明機関証明書または内部証明書が有効期限が近い、または侵害されている」を参照してください。
  
## <a name="input-types"></a>入力の種類
<a name="InputTypes"> </a>

なし。 このReset-CcCACertificateは、パイプライン処理された入力を受け付け取らない。
  
## <a name="return-types"></a>戻り値の種類
<a name="ReturnTypes"> </a>

なし。
  
## <a name="see-also"></a>関連項目
<a name="ReturnTypes"> </a>

[Renew-CcCACertificate](renew-cccacertificate.md) バージョン 1.4.2 のみ
  
[Renew-CcServerCertificate](renew-ccservercertificate.md) バージョン 1.4.2 のみ
  
[Update-CcCACertificate](update-cccacertificate.md) バージョン 2.0 以降
  
[Renew-CcServerCertificate](renew-ccservercertificate.md) バージョン 2.0 以降
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

