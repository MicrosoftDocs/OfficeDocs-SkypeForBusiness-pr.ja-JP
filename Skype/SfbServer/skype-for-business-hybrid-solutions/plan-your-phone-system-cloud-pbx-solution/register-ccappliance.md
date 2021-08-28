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
ms.localizationpriority: medium
ms.assetid: 01eed3c5-af68-4db7-90b3-d28ebe7ffef1
description: このRegister-CcApplianceコマンドレットは、オンライン テナント構成でアプライアンス情報を PSTN サイトに登録します。 アプライアンスを展開し、管理サービスによって管理するには、その前にSkype for Business クラウド コネクタ エディション必要があります。
ms.openlocfilehash: 159e74f91ca26cd0f8bdd214c9cd6ac45b5c1196
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58589961"
---
# <a name="register-ccappliance"></a>Register-CcAppliance
 
このRegister-CcApplianceコマンドレットは、オンライン テナント構成でアプライアンス情報を PSTN サイトに登録します。 アプライアンスを展開し、管理サービスによって管理するには、その前にSkype for Business クラウド コネクタ エディション必要があります。
  
```powershell
Register-CcAppliance [[-SiteName] <string>] [[-ApplianceName] <string>] [-Local]
```

## <a name="examples"></a>例
<a name="Examples"> </a>

### <a name="example-1"></a>例 1

次の使用例は、現在のアプライアンス情報をオンライン テナント構成に登録します。
  
```powershell
Register-CcAppliance
```

### <a name="example-2"></a>例 2

次の例では、オンライン テナント構成に接続せずに、ローカルで登録の構成を確認します。
  
```powershell
Register-CcAppliance -Local
```

### <a name="example-3"></a>例 3

次の使用例は、現在のアプライアンスを "Appliance1" という名前で PSTN サイト "Site1" に登録します。
  
```powershell
Register-CcAppliance -SiteName Site1 -ApplianceName Appliance1
```

## <a name="detailed-description"></a>解説
<a name="DetailedDescription"> </a>

テナント管理者アカウント名とパスワードを指定する必要があります。 クラウド コネクタのオンライン管理用に作成したアカウントを使用します。 
  
リリース 1.4.2 以前では、指示に従って、外部証明書パスワード、セーフ モード管理者パスワード、ドメイン管理者パスワード、VM 管理者パスワードを指定します。 
  
リリース 2.0 以降では、指示に従って外部証明書パスワード、CceService パスワード、CABackupFile パスワードを指定します。
  
登録の最後に、クラウド コネクタ管理サービスを再起動し、CceService アカウントとしてサービスにログオンします。
  
SiteName とエッジ サーバーの外部 FQDN CloudConnector.iniは、PSTN サイト ID と見なされます。 サイトの登録に SiteName もエッジ サーバーの外部 FQDN も使用されていない場合は、オンライン テナント構成でこのアプライアンス用に新しいサイトが作成されます。 PSTN サイト ID が見つかった場合、PSTN サイトはこの ID を使用し、アプライアンスはこの PSTN サイトに登録されます。 
  
次の状況では、コマンドレットは失敗し、Site1 が既に登録されています。 
  
- SiteName は Site1 で、エッジ サーバーの外部 FQDN は edgserver1.contoso.com。 
    
- SiteName が Site1 であり、エッジ サーバーの外部 FQDN を持つ PSTN サイトが edgserver.contoso.com。
    
- SiteName が NewSite で、エッジ サーバーの外部 FQDN が登録されている PSTN edgserver1.contoso.com サイトです。 
    
アプライアンスファイルの仲介サーバー FQDN と組み合CloudConnector.iniアプライアンス ID と見なされます。 アプライアンスの登録に ApplianceName も仲介サーバー FQDN も使用されていない場合は、オンライン テナント構成で新しいアプライアンスが作成されます。 アプライアンスが既に登録されている場合、コマンドレットは失敗します。
  
次の状況では、コマンドレットは失敗し、アプライアンスが既に登録されています。 
  
- ApplianceName はアプライアンス 1 で、仲介サーバー FQDN は ms1.vdomain.com。
    
- 現在の PSTN サイトで、Appliance1 と Mediation Server FQDN という名前のアプライアンスが ms.vdomain.com または NewAppliance および仲介サーバー FQDN という名前のアプライアンスが ms1.vdomain.com 登録されている場合。
    
## <a name="parameters"></a>パラメーター
<a name="DetailedDescription"> </a>

|**パラメーター**|**Required**|**Type**|**説明**|
|:-----|:-----|:-----|:-----|
|SiteName  <br/> |省略可  <br/> |System.String  <br/> |アプライアンスが登録されている PSTN サイト名。 既定値は、ファイル内の SiteName CloudConnector.iniです。  <br/> |
|ApplianceName  <br/> |省略可  <br/> |System.String  <br/> |現在のアプライアンスの名前。 既定値は、ホスト サーバーのコンピューター名です。  <br/> |
|ローカル  <br/> |省略可  <br/> |System.Management.Automation.SwitchParameter  <br/> |オンライン テナント構成に接続せずに、ローカルで登録の構成を確認します。  <br/> |
   
## <a name="input-types"></a>入力の種類
<a name="InputTypes"> </a>

なし。 このRegister-CcApplianceは、パイプライン処理された入力を受け付け取らない。
  
## <a name="return-types"></a>戻り値の種類
<a name="ReturnTypes"> </a>

なし
  
## <a name="see-also"></a>関連項目
<a name="ReturnTypes"> </a>

[Unregister-CcAppliance](unregister-ccappliance.md)
  
[Publish-CcAppliance](publish-ccappliance.md)
  
[Install-CcAppliance](install-ccappliance.md)
  
[Uninstall-CcAppliance](uninstall-ccappliance.md)
  

