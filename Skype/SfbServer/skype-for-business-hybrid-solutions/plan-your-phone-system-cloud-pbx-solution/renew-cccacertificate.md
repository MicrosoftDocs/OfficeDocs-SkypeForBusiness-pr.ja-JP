---
title: Renew-CcCACertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/18/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 44da2f8d-0bf5-4f3e-b2e7-bb181dbbe646
description: Renew-CcCACertificate コマンドレットは、有効期限が近づいている、またはすでに有効期限が切れている Skype for Business Cloud Connector エディションのルート CA 証明書を更新します。 このコマンドは、クラウド コネクタ 2.0 およびそれ以降のリリースで更新プログラムを CcCACertificate に変更されました。
ms.openlocfilehash: 616abb35d577b816368854396a201b9f07b40d12
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30893863"
---
# <a name="renew-cccacertificate"></a>Renew-CcCACertificate
 
Renew-CcCACertificate コマンドレットは、有効期限が近づいている、またはすでに有効期限が切れている Skype for Business Cloud Connector エディションのルート CA 証明書を更新します。 このコマンドは、クラウド コネクタ 2.0 およびそれ以降のリリースで更新プログラムを CcCACertificate に変更されました。
  
```
Renew-CcCACertificate
```

## <a name="parameters"></a>パラメーター

なし
  
## <a name="examples"></a>例
<a name="Examples"> </a>

### <a name="example-1"></a>例 1

次の例では、ルート CA 証明書を更新します。 
  
```
Renew-CcCACertificate 
```

## <a name="detailed-description"></a>解説
<a name="DetailedDescription"> </a>

Cloud Connector のルート CA 証明書は証明機関サービスをインストールした日から 5 年間有効です。
  
ルート証明書の有効期限が近づいている場合またはすでに有効期限が切れている場合は、Renew-CcCACertificate コマンドレットを実行して証明書を更新します。ルート証明書を更新すると、AD サーバー、中央管理ストア、エッジ サーバーに対して新しい証明書が自動的に発行されます。
  
同一の PSTN サイトに複数のアプライアンスが存在する場合は、その PSTN サイトのすべてのアプライアンスで Renew-CcCACertificate コマンドレットを実行します。
  
最後に、Export-CcRootCertificate コマンドレットを実行して、最初のアプライアンスのローカル ファイルにルート証明書をエクスポートし、エクスポートした証明書を PSTN ゲートウェイにコピーしてインストールします。
  
## <a name="input-types"></a>入力の種類
<a name="InputTypes"> </a>

なし。Renew-CcCACertificate コマンドレットはパイプライン入力を受け入れません。
  
## <a name="return-types"></a>戻り値の種類
<a name="ReturnTypes"> </a>

なし
  
## <a name="see-also"></a>関連項目
<a name="ReturnTypes"> </a>

[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Renew-CcServerCertificate](renew-ccservercertificate.md)
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

