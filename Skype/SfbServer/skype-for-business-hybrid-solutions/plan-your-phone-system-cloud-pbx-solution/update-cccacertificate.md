---
title: 更新 CcCACertificate
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/11/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5b474789-75de-443c-89bd-de89be55a1dd
description: Update-CcCACertificate コマンドレットは、Skype for Business Cloud Connector エディションの有効期限が近づいている、またはすでに有効期限が切れているルート CA 証明書を更新します。
ms.openlocfilehash: f23298f1be30ab96b3e77ff0625ff6e3b419e111
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="update-cccacertificate"></a>更新 CcCACertificate
 
Update-CcCACertificate コマンドレットは、Skype for Business Cloud Connector エディションの有効期限が近づいている、またはすでに有効期限が切れているルート CA 証明書を更新します。 
  
```
Update-CcCACertificate
```

## <a name="parameters"></a>パラメーター

なし
  
## <a name="examples"></a>例
<a name="Examples"> </a>

### <a name="example-1"></a>例 1

次の例では、ルート CA 証明書を更新します。 
  
```
Update-CcCACertificate 
```

## <a name="detailed-description"></a>解説
<a name="DetailedDescription"> </a>

Cloud Connector のルート CA 証明書は証明機関サービスをインストールした日から 5 年間有効です。
  
ルート証明書の有効期限が近づいている場合またはすでに有効期限が切れている場合は、Update-CcCACertificate コマンドレットを実行して証明書を更新します。 ルート証明書を更新すると、AD サーバー、中央管理ストア、エッジ サーバーに対して新しい証明書が自動的に発行されます。
  
同一の PSTN サイトに複数のアプライアンスが存在する場合は、その PSTN サイトのすべてのアプライアンスで Update-CcCACertificate コマンドレットを実行します。
  
最後に、Export-CcRootCertificate コマンドレットを実行して、最初のアプライアンスのローカル ファイルにルート証明書をエクスポートし、エクスポートした証明書を PSTN ゲートウェイにコピーしてインストールします。
  
Cloud Connector 2.0 以降のリリースでは、このコマンドによって Renew-CcCACertificate コマンドレットが置き換えられます。
  
## <a name="input-types"></a>入力の種類
<a name="InputTypes"> </a>

なし。 Update-CcCACertificate コマンドレットはパイプライン入力を受け入れません。
  
## <a name="return-types"></a>戻り値の種類
<a name="ReturnTypes"> </a>

なし。 
  
## <a name="see-also"></a>関連項目
<a name="ReturnTypes"> </a>

[リセット CcCACertificate](reset-cccacertificate.md)
  
[更新 CcServerCertificate](renew-ccservercertificate.md)
  
[エクスポート CcRootCertificate](export-ccrootcertificate.md)
  

