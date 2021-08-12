---
title: Get-CcCredential
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/8/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b2b5aefb-a08d-4bec-9204-76597d413849
description: このGet-CcCredentialは、現在の展開の資格情報をSkype for Business クラウド コネクタ エディションします。
ms.openlocfilehash: 277062068c6e5e630fd22cd1bd4c6dbfb873db1cb90b915424aa6e3a3eb6ce50
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54322890"
---
# <a name="get-cccredential"></a>Get-CcCredential
 
このGet-CcCredentialは、現在の展開の資格情報をSkype for Business クラウド コネクタ エディションします。 
  
バージョン 2.0 以降では、-DisplayPassword パラメーターを使用して、TenantAdmin、DomainAdmin、VMAdmin のパスワードを表示することもできます。
  
```powershell
Get-CcCredential [[-AccountType] <string> {VmAdmin | DomainAdmin | SafeModeAdmin | ExternalCert | TenantAdmin}]
```

## <a name="examples"></a>例
<a name="Examples"> </a>

### <a name="example-1"></a>例 1

次の使用例は、Cloud Connector 仮想マシン ドメインのドメイン管理者の資格情報を返します。
  
```powershell
Get-CcCredential -AccountType DomainAdmin
```

## <a name="detailed-description"></a>解説
<a name="DetailedDescription"> </a>

このGet-CcCredentialは、指定したアカウントの種類に関する資格情報を返します。 これらの資格情報は、現在のアプライアンスを展開するときに、Register-CcApplianceおよびInstall-CcApplianceコマンドレットを実行する管理者によって指定されます。 
  
このGet-CcCredentialは、System.Management.Automation.PSCredential オブジェクトのインスタンスを返します。 戻り値オブジェクトの password プロパティは System.Security.SecureString です。
  
ドメイン管理者パスワードのクリア テキストを取得する場合は、ホスト サーバー上の現在のログオン アカウントでパスワードが入力され、管理者として PowerShell コンソールを開き、次のスクリプトを実行します。
  
```powershell
$cred = Get-CcCredential -AccountType DomainAdmin
$password =  $cred.Password
$bstr = [System.Runtime.InteropServices.Marshal]::SecureStringToBSTR($password);
$text = [System.Runtime.InteropServices.Marshal]::PtrToStringAuto($bstr);
[System.Runtime.InteropServices.Marshal]::ZeroFreeBSTR($bstr);
Write-Host $text
```

## <a name="parameters"></a>パラメーター
<a name="DetailedDescription"> </a>

|**パラメーター**|**Required**|**型**|**説明**|
|:-----|:-----|:-----|:-----|
| AccountType <br/> |必須  <br/> | System.String <br/> | AccountType 値には、次のいずれかを指定できます。 <br/>  VmAdmin: クラウド コネクタ仮想マシンのローカル管理者。 <br/>  DomainAdmin: Cloud Connector 仮想マシン ドメインのドメイン管理者。 <br/>  SafeModeAdmin: Cloud Connector 仮想マシン ドメイン コントローラーの SafeModeAdmin。 <br/>  ExternalCert: エッジ サーバーにインストールされている外部証明書のアカウント。 <br/>  TenantAdmin: O365 テナントの管理者。 <br/> |
   
## <a name="input-types"></a>入力の種類
<a name="InputTypes"> </a>

なし。 このGet-CcCredentialは、パイプライン処理された入力を受け付け取らない。
  
## <a name="return-types"></a>戻り値の種類
<a name="ReturnTypes"> </a>

このGet-CcCredentialは、System.Management.Automation.PSCredential オブジェクトのインスタンスを返します。
  
## <a name="see-also"></a>関連項目
<a name="ReturnTypes"> </a>

[Set-CcCredential](set-cccredential.md)
  

