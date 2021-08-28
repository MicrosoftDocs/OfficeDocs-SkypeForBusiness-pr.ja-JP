---
title: Publish-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: e7d5b63e-ba7c-4757-8670-f96b2a91e646
description: このPublish-CcApplianceは、オンライン テナント構成から高可用性情報を取得し、ホスト サーバー上の Skype for Business クラウド コネクタ エディションアプライアンスに発行します。
ms.openlocfilehash: d1cd8d3ff9a47d10089ee3ea64d0db576845a708
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58589991"
---
# <a name="publish-ccappliance"></a>Publish-CcAppliance
 
このPublish-CcApplianceは、オンライン テナント構成から高可用性情報を取得し、ホスト サーバー上の Skype for Business クラウド コネクタ エディションアプライアンスに発行します。 
  
```powershell
Publish-CcAppliance
```

## <a name="parameters"></a>パラメーター

なし
  
## <a name="examples"></a>例
<a name="Examples"> </a>

### <a name="example-1"></a>例 1

次の使用例は、オンライン テナント構成から高可用性情報を取得し、ホスト サーバー上のクラウド コネクタ アプライアンスに発行します。
  
```powershell
Publish-CcAppliance
```

## <a name="detailed-description"></a>解説
<a name="DetailedDescription"> </a>

高可用性情報には、PSTN サイトの仲介サーバーの FQDN と IP アドレスが含まれます。 新しい DNS 仲介サーバーの IP アドレスADサーバーにレコードが追加されます。 仲介サーバーの FQDN と IP アドレスの中央管理ストアに新しいトポロジ アイテムが更新されます。 
  
## <a name="input-types"></a>入力の種類
<a name="InputTypes"> </a>

なし。 このPublish-CcApplianceは、パイプライン処理された入力を受け付け取らない。
  
## <a name="return-types"></a>戻り値の種類
<a name="ReturnTypes"> </a>

なし
  
## <a name="see-also"></a>関連項目
<a name="ReturnTypes"> </a>

[Install-CcAppliance](install-ccappliance.md)
  
[Uninstall-CcAppliance](uninstall-ccappliance.md)
  
[Register-CcAppliance](register-ccappliance.md)
  
[Unregister-CcAppliance](unregister-ccappliance.md)
  

