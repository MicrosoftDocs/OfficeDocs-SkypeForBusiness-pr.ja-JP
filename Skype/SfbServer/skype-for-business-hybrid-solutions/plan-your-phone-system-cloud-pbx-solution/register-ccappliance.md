---
title: Register-CcAppliance
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
ms.assetid: 01eed3c5-af68-4db7-90b3-d28ebe7ffef1
description: Register-CcAppliance コマンドレットは、アプライアンス情報をオンライン テナント構成の PSTN サイトに登録します。 アプライアンスを Skype for Business Cloud Connector エディションの管理サービスで展開および管理する前に、アプライアンスの登録が必要です。
ms.openlocfilehash: a94f9d7189f4872fcee2439afd2b210933f8bb06
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824303"
---
# <a name="register-ccappliance"></a>Register-CcAppliance
 
Register-CcAppliance コマンドレットは、アプライアンス情報をオンライン テナント構成の PSTN サイトに登録します。 アプライアンスを Skype for Business Cloud Connector エディションの管理サービスで展開および管理する前に、アプライアンスの登録が必要です。
  
```powershell
Register-CcAppliance [[-SiteName] <string>] [[-ApplianceName] <string>] [-Local]
```

## <a name="examples"></a>例
<a name="Examples"> </a>

### <a name="example-1"></a>例 1

次の例では、現在のアプライアンス情報をオンライン テナント構成に登録します。
  
```powershell
Register-CcAppliance
```

### <a name="example-2"></a>例 2

次の例では、オンライン テナント構成に接続せずにローカルで登録の構成をチェックします。
  
```powershell
Register-CcAppliance -Local
```

### <a name="example-3"></a>例 3

次の例では、「Appliance1」という名前を持つ現在のアプライアンスを「Site1」という PSTN サイトに登録します。
  
```powershell
Register-CcAppliance -SiteName Site1 -ApplianceName Appliance1
```

## <a name="detailed-description"></a>解説
<a name="DetailedDescription"> </a>

テナント管理者のアカウント名とパスワードを入力します。 Cloud Connector のオンライン管理用に作成したアカウントを使用します。 
  
Release 1.4.2 以前のバージョンでは、次の手順に従って、外部証明書のパスワード、セーフモードのパスワード、ドメイン管理者のパスワード、VM 管理者のパスワードを指定します。 
  
リリース 2.0 以降の場合は、指示に従って外部証明書のパスワード、CceService パスワード、CABackupFile パスワードを入力します。
  
登録が終了したら、クラウドコネクタ管理サービスを再起動し、CceService アカウントとしてサービスにログオンします。
  
CloudConnector.ini ファイルでエッジ サーバーの外部 FQDN と組み合わされた SiteName は PSTN サイトの ID として考慮されます。SiteName またはエッジ サーバーの外部 FQDN がサイトの登録に使用されない場合、このアプライアンスに対しては、オンライン テナント構成で新しいサイトが作成されます。PSTN サイトの ID が見つかった場合、PSTN サイトはこの ID を使用します。アプライアンスはこの PSTN サイトに登録されます。 
  
次の場合、コマンドレットは失敗し、Site1 が既に登録されていることを示します。 
  
- SiteName が Site1 であり、エッジ サーバーの外部 FQDN が edgserver1.contoso.com である場合。 
    
- SiteName が Site1 であり、エッジ サーバーの外部 FQDN が edgserver.contoso.com である PSTN サイト。
    
- SiteName が NewSite で、エッジ サーバーの外部 FQDN が edgserver1.contoso.com である PSTN サイトがすでに登録されている場合。 
    
CloudConnector.ini ファイルで仲介サーバーの FQDN と組み合わされた ApplianceName は アプライアンスの ID として考慮されます。ApplianceName または仲介サーバーの FQDN がアプライアンスの登録に使用されない場合、オンライン テナント構成で新しいアプライアンスが作成されます。アプライアンスがすでに登録されている場合、コマンドレットは失敗します。
  
次の場合、コマンドレットは失敗し、アプライアンスがすでに登録されていることを示します。 
  
- ApplianceName が Appliance1 であり、仲介サーバーの FQDN が ms1.vdomain.com である場合 。
    
- 現在の PSTN サイトで、名前が Appliance1 で、仲介サーバーの FQDN が ms.vdomain.com であるアプライアンス、または名前が NewAppliance で、仲介サーバーの FQDN が ms1.vdomain.com であるアプライアンスがすでに登録されている場合。
    
## <a name="parameters"></a>パラメーター
<a name="DetailedDescription"> </a>

|**パラメーター**|**必須**|**種類**|**説明**|
|:-----|:-----|:-----|:-----|
|SiteName  <br/> |省略可能  <br/> |System.String  <br/> |アプライアンスが登録される PSTN サイトの名前。既定の値は CloudConnector.ini ファイル内の SiteName 値です。  <br/> |
|ApplianceName  <br/> |省略可能  <br/> |System.String  <br/> |現在のアプライアンスの名前。既定の値はホスト サーバーのコンピューター名です。  <br/> |
|Local  <br/> |省略可能  <br/> |System.Management.Automation.SwitchParameter  <br/> |オンライン テナント構成に接続せずにローカルで登録の構成をチェックします。  <br/> |
   
## <a name="input-types"></a>入力の種類
<a name="InputTypes"> </a>

なし。Register-CcAppliance コマンドレットはパイプライン入力を受け入れません。
  
## <a name="return-types"></a>戻り値の種類
<a name="ReturnTypes"> </a>

なし
  
## <a name="see-also"></a>関連項目
<a name="ReturnTypes"> </a>

[Unregister-CcAppliance](unregister-ccappliance.md)
  
[Publish-CcAppliance](publish-ccappliance.md)
  
[Install-CcAppliance](install-ccappliance.md)
  
[Uninstall-CcAppliance](uninstall-ccappliance.md)
  

