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
localization_priority: Normal
ms.assetid: 3d516e65-fb9b-4a0b-8296-969fc9eda334
description: Unregister-CcAppliance コマンドレットは、オンラインのテナント構成内の PSTN サイトから、現在の Skype for Business Cloud Connector エディションのアプライアンスを登録解除します。
ms.openlocfilehash: fafe374371cd01b2ec7c67ade89dd2a905e16d18
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286874"
---
# <a name="unregister-ccappliance"></a>Unregister-CcAppliance
 
Unregister-CcAppliance コマンドレットは、オンラインのテナント構成内の PSTN サイトから、現在の Skype for Business Cloud Connector エディションのアプライアンスを登録解除します。
  
```
Unregister-CcAppliance [[-SiteName] <string>] [[-ApplianceName] <string>] [-Local]
```

## <a name="examples"></a>例
<a name="Examples"> </a>

### <a name="example-1"></a>例 1

次の例では、オンラインのテナント構成から現在のアプライアンスの登録を解除します。
  
```
Unregister-CcAppliance
```

### <a name="example-2"></a>例 2

次の例では、オンラインのテナント構成に接続せずにローカルで登録解除するために、構成を確認します。
  
```
Unregister-CcAppliance -Local
```

### <a name="example-3"></a>例 3

次の例では、「Appliance1」という名前を持つ現在のアプライアンスを「Site1」という PSTN サイトで登録解除します。
  
```
Unregister-CcAppliance -SiteName Site1 -ApplianceName Appliance1
```

## <a name="detailed-description"></a>解説
<a name="DetailedDescription"> </a>

Register-CcAppliance コマンドレットと同様に、CloudConnector.ini ファイルでエッジ サーバーの外部 FQDN と組み合わされた SiteName は PSTN サイトの ID として考慮されます。同じく、CloudConnector.ini ファイルで仲介サーバーの FQDN と組み合わされた ApplianceName は、アプライアンス ID として考慮されます。
  
アプライアンスの登録が解除されたら、クラウドコネクタ管理サービスを再起動し、NetworkService アカウントとしてログオンします。
  
## <a name="parameters"></a>パラメーター
<a name="DetailedDescription"> </a>

|**パラメーター**|**必須**|**型**|**説明**|
|:-----|:-----|:-----|:-----|
| SiteName <br/> |省略可能  <br/> |System.String  <br/> |アプライアンスが登録されている PSTN サイトの名前。既定値は CloudConnector.ini ファイル内の SiteName 値です。  <br/> |
|ApplianceName  <br/> |省略可能  <br/> |System.String  <br/> |現在のアプライアンスの名前。既定の値はホスト サーバーのコンピューター名です。  <br/> |
|Local  <br/> |省略可能  <br/> |System.Management.Automation.SwitchParameter  <br/> |オンライン テナント構成に接続することなく、ローカルで登録するための構成を確認します。  <br/> |
   
## <a name="input-types"></a>入力の種類
<a name="InputTypes"> </a>

なし。Unregister-CcAppliance コマンドレットはパイプライン入力を受け入れません。
  
## <a name="return-types"></a>戻り値の種類
<a name="ReturnTypes"> </a>

なし
  
## <a name="see-also"></a>関連項目
<a name="ReturnTypes"> </a>

[Register-CcAppliance](register-ccappliance.md)
  
[Install-CcAppliance](install-ccappliance.md)
  
[Uninstall-CcAppliance](uninstall-ccappliance.md)
  
[Publish-CcAppliance](publish-ccappliance.md)
  

