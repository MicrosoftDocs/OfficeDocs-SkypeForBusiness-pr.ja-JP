---
title: Unregister-CcAppliance
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
ms.assetid: 3d516e65-fb9b-4a0b-8296-969fc9eda334
description: このUnregister-CcApplianceコマンドレットは、オンライン テナント構成Skype for Business クラウド コネクタ エディション PSTN サイトから現在のアプライアンスの登録を解除します。
ms.openlocfilehash: c48a7b53d757dab446a8939a3e3203d8e66fccab
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58603656"
---
# <a name="unregister-ccappliance"></a>Unregister-CcAppliance
 
このUnregister-CcApplianceコマンドレットは、オンライン テナント構成Skype for Business クラウド コネクタ エディション PSTN サイトから現在のアプライアンスの登録を解除します。
  
```powershell
Unregister-CcAppliance [[-SiteName] <string>] [[-ApplianceName] <string>] [-Local]
```

## <a name="examples"></a>例
<a name="Examples"> </a>

### <a name="example-1"></a>例 1

次の使用例は、現在のアプライアンスをオンライン テナント構成から登録解除します。
  
```powershell
Unregister-CcAppliance
```

### <a name="example-2"></a>例 2

次の例では、オンライン テナント構成に接続せずに、ローカルで登録を解除するための構成を確認します。
  
```powershell
Unregister-CcAppliance -Local
```

### <a name="example-3"></a>例 3

次の例では、"Appliance1" という名前の現在のアプライアンスを PSTN サイト "Site1" に登録解除します。
  
```powershell
Unregister-CcAppliance -SiteName Site1 -ApplianceName Appliance1
```

## <a name="detailed-description"></a>解説
<a name="DetailedDescription"> </a>

Register-CcAppliance コマンドレットと同様に、SiteName とエッジ サーバーの外部 FQDN CloudConnector.iniは PSTN サイト ID と見なされます。 同様に、アプライアンス名と仲介サーバーの FQDN CloudConnector.iniは、アプライアンス ID と見なされます。
  
アプライアンスの登録が解除された後、クラウド コネクタ管理サービスを再起動し、NetworkService アカウントとしてログオンします。
  
## <a name="parameters"></a>パラメーター
<a name="DetailedDescription"> </a>

|**パラメーター**|**Required**|**Type**|**説明**|
|:-----|:-----|:-----|:-----|
| SiteName <br/> |省略可  <br/> |System.String  <br/> |アプライアンスが登録されている PSTN サイト名。 既定値は、ファイル内の SiteName CloudConnector.iniです。  <br/> |
|ApplianceName  <br/> |省略可  <br/> |System.String  <br/> |現在のアプライアンスの名前。 既定値は、ホスト サーバーのコンピューター名です。  <br/> |
|ローカル  <br/> |省略可  <br/> |System.Management.Automation.SwitchParameter  <br/> |オンライン テナント構成に接続せずに、ローカルで登録の構成を確認します。  <br/> |
   
## <a name="input-types"></a>入力の種類
<a name="InputTypes"> </a>

なし。 このUnregister-CcApplianceは、パイプライン処理された入力を受け付け取らない。
  
## <a name="return-types"></a>戻り値の種類
<a name="ReturnTypes"> </a>

なし
  
## <a name="see-also"></a>関連項目
<a name="ReturnTypes"> </a>

[Register-CcAppliance](register-ccappliance.md)
  
[Install-CcAppliance](install-ccappliance.md)
  
[Uninstall-CcAppliance](uninstall-ccappliance.md)
  
[Publish-CcAppliance](publish-ccappliance.md)
  

