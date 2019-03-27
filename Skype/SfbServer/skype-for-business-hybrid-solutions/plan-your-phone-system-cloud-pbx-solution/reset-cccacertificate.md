---
title: Reset-CcCACertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/22/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5ada7e55-df9b-4b4e-b752-2468f4e28b8a
description: Reset-CcCACertificate コマンドレットは、証明機関サービスの AD サーバーを再インストールして、新しいルート CA 証明書を作成します。
ms.openlocfilehash: 1ed9aaa8b7caf1edd5324d082094fa247c858853
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30898537"
---
# <a name="reset-cccacertificate"></a>Reset-CcCACertificate
 
Reset-CcCACertificate コマンドレットは、証明機関サービスの AD サーバーを再インストールして、新しいルート CA 証明書を作成します。
  
```
Reset-CcCACertificate
```

## <a name="parameters"></a>パラメーター

なし
  
## <a name="examples"></a>例
<a name="Examples"> </a>

### <a name="example-1"></a>例 1

次の例では、証明機関サービスの AD サーバーを再インストールして、新しいルート CA 証明書を作成します。
  
```
Reset-CcCACertificate
```

## <a name="detailed-description"></a>解説
<a name="DetailedDescription"> </a>

ルート CA 証明書が侵害された場合やすでに安全でない場合は、ルート CA 証明書、およびルート CA によって発行されたすべての証明書を更新する必要があります。 Reset-CcCACertificate コマンドレットは、すべての証明書を取り消し、証明機関のアンインストールと再インストールを行い、以前の証明機関サービスに関連するすべての証明書を削除します。 
  
詳細については、コネクタのクラウド展開のトラブルシューティングで [証明機関証明書や CMS、仲介サーバー、およびエッジ サーバーに対して発行された証明書を内部、有効期限の近くにあるかが侵害された証明書] を参照してください。
  
## <a name="input-types"></a>入力の種類
<a name="InputTypes"> </a>

なし。Reset-CcCACertificate コマンドレットはパイプライン入力を受け入れません。
  
## <a name="return-types"></a>戻り値の種類
<a name="ReturnTypes"> </a>

なし。
  
## <a name="see-also"></a>関連項目
<a name="ReturnTypes"> </a>

[Renew-CcCACertificate](renew-cccacertificate.md) バージョン 1.4.2 のみ
  
[Renew-CcServerCertificate](renew-ccservercertificate.md) バージョン 1.4.2 のみ
  
[Update-CcCACertificate](update-cccacertificate.md) バージョン 2.0 以降
  
[更新 CcServerCertificate](renew-ccservercertificate.md)バージョン 2.0 以降では
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

