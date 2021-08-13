---
title: Renew-CcCACertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/18/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 44da2f8d-0bf5-4f3e-b2e7-bb181dbbe646
description: このRenew-CcCACertificateコマンドレットは、有効期限Skype for Business クラウド コネクタ エディション近い、または既に有効期限が切れているルート CA 証明書を更新します。 このコマンドは、Cloud Connector 2.0 Update-CcCACertificate以降のリリースで変更されました。
ms.openlocfilehash: 49b58e18d6393d5a3f9665fea98cba73f22d9c3259f0036dc93dce9dbf67e567
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54340783"
---
# <a name="renew-cccacertificate"></a>Renew-CcCACertificate
 
このRenew-CcCACertificateコマンドレットは、有効期限Skype for Business クラウド コネクタ エディション近い、または既に有効期限が切れているルート CA 証明書を更新します。 このコマンドは、Cloud Connector 2.0 Update-CcCACertificate以降のリリースで変更されました。
  
```powershell
Renew-CcCACertificate
```

## <a name="parameters"></a>パラメーター

なし
  
## <a name="examples"></a>例
<a name="Examples"> </a>

### <a name="example-1"></a>例 1

次の例では、ルート CA 証明書を更新します。 
  
```powershell
Renew-CcCACertificate 
```

## <a name="detailed-description"></a>解説
<a name="DetailedDescription"> </a>

Cloud Connector ルート CA 証明書は、証明機関サービスがインストールされた日から 5 年間有効です。
  
ルート証明書の有効期限が近い場合、または既に有効期限が切れている場合は、Renew-CcCACertificateコマンドレットを実行して証明書を更新します。 ルート証明書が更新された後、ADサーバー、サーバーの全体管理ストア、およびエッジ サーバーが自動的に新しい証明書を発行します。
  
同じ PSTN サイトに複数のアプライアンスがある場合は、同じ PSTN サイトのすべてのRenew-CcCACertificateコマンドレットを実行します。
  
最後の手順として、Export-CcRootCertificateを実行して、ルート証明書を最初のアプライアンスのローカル ファイルにエクスポートし、エクスポートした証明書を PSTN ゲートウェイにコピーしてインストールします。
  
## <a name="input-types"></a>入力の種類
<a name="InputTypes"> </a>

なし。 このRenew-CcCACertificateは、パイプライン処理された入力を受け付け取らない。
  
## <a name="return-types"></a>戻り値の種類
<a name="ReturnTypes"> </a>

なし
  
## <a name="see-also"></a>関連項目
<a name="ReturnTypes"> </a>

[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Renew-CcServerCertificate](renew-ccservercertificate.md)
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

