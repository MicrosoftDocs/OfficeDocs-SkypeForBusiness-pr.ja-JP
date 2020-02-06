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
localization_priority: Normal
ms.assetid: e7d5b63e-ba7c-4757-8670-f96b2a91e646
description: Publish-CcAppliance コマンドレットは高可用性の情報をオンラインのテナント構成から取得して、ホスト サーバー上の Skype for Business Cloud Connector エディションのアプライアンスに公開します。
ms.openlocfilehash: 159247614733261cac4b3381e35d8dd297cf9a23
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824313"
---
# <a name="publish-ccappliance"></a>Publish-CcAppliance
 
Publish-CcAppliance コマンドレットは高可用性の情報をオンラインのテナント構成から取得して、ホスト サーバー上の Skype for Business Cloud Connector エディションのアプライアンスに公開します。 
  
```powershell
Publish-CcAppliance
```

## <a name="parameters"></a>パラメーター

なし
  
## <a name="examples"></a>例
<a name="Examples"> </a>

### <a name="example-1"></a>例 1

次の例では、オンラインテナント構成から高可用性情報を取得し、それをホストサーバー上のクラウドコネクタアプライアンスに公開しています。
  
```powershell
Publish-CcAppliance
```

## <a name="detailed-description"></a>解説
<a name="DetailedDescription"> </a>

高可用性の情報には、PSTN サイトの仲介サーバーの FQDN と IP アドレスが含まれます。新しい DNS A レコードが、仲介サーバーの IP アドレスの AD サーバーに追加されます。新しいトポロジ項目が、仲介サーバーの FQDN と IP アドレスの中央管理ストアに更新されます。 
  
## <a name="input-types"></a>入力の種類
<a name="InputTypes"> </a>

なし。 Publish-CcAppliance コマンドレットはパイプライン入力を受け入れません。
  
## <a name="return-types"></a>戻り値の種類
<a name="ReturnTypes"> </a>

なし
  
## <a name="see-also"></a>関連項目
<a name="ReturnTypes"> </a>

[Install-CcAppliance](install-ccappliance.md)
  
[Uninstall-CcAppliance](uninstall-ccappliance.md)
  
[Register-CcAppliance](register-ccappliance.md)
  
[Unregister-CcAppliance](unregister-ccappliance.md)
  

