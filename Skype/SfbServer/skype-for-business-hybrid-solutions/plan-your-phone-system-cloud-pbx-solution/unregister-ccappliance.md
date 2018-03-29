---
title: 登録解除 CcAppliance
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d516e65-fb9b-4a0b-8296-969fc9eda334
description: Unregister-CcAppliance コマンドレットは、オンラインのテナント構成内の PSTN サイトから、現在の Skype for Business Cloud Connector エディションのアプライアンスを登録解除します。
ms.openlocfilehash: 21bd0a7dffc6a395f829af68a61dfd7523d2c09a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="unregister-ccappliance"></a>登録解除 CcAppliance
 
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

次の例では、オンラインのテナント構成に接続せずにローカルに登録を解除するための構成を確認します。
  
```
Unregister-CcAppliance -Local
```

### <a name="example-3"></a>例 3

次の使用例は、PSTN のサイト"Site1"名"Appliance1"を持つ現在のアプライアンスを登録解除します。
  
```
Unregister-CcAppliance -SiteName Site1 -ApplianceName Appliance1
```

## <a name="detailed-description"></a>解説
<a name="DetailedDescription"> </a>

Register-CcAppliance コマンドレットと同様に、CloudConnector.ini ファイルでエッジ サーバーの外部 FQDN と組み合わされた SiteName は PSTN サイトの ID として考慮されます。同じく、CloudConnector.ini ファイルで仲介サーバーの FQDN と組み合わされた ApplianceName は、アプライアンス ID として考慮されます。
  
アプライアンスは、登録されているが、再起動、クラウドのコネクタの管理サービスとログの NetworkService アカウントとして。
  
## <a name="parameters"></a>パラメーター
<a name="DetailedDescription"> </a>

|**パラメーター**|**必須**|**タイプ**|**説明**|
|:-----|:-----|:-----|:-----|
| サイト名 <br/> |省略可能  <br/> |System.String  <br/> |アプライアンスが登録されている PSTN サイトの名前。既定値は CloudConnector.ini ファイル内の SiteName 値です。  <br/> |
|アプライアンス名  <br/> |省略可能  <br/> |System.String  <br/> |現在のアプライアンスの名前。既定の値はホスト サーバーのコンピューター名です。  <br/> |
|Local  <br/> |省略可能  <br/> |System.Management.Automation.SwitchParameter  <br/> |オンライン テナント構成に接続することなく、ローカルで登録するための構成を確認します。  <br/> |
   
## <a name="input-types"></a>入力の種類
<a name="InputTypes"> </a>

なし。Unregister-CcAppliance コマンドレットはパイプライン入力を受け入れません。
  
## <a name="return-types"></a>戻り値の種類
<a name="ReturnTypes"> </a>

なし
  
## <a name="see-also"></a>関連項目
<a name="ReturnTypes"> </a>

[登録 CcAppliance](register-ccappliance.md)
  
[インストール CcAppliance](install-ccappliance.md)
  
[アンインストール CcAppliance](uninstall-ccappliance.md)
  
[発行 CcAppliance](publish-ccappliance.md)
  

