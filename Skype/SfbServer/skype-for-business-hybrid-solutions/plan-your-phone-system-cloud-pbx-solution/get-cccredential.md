---
title: Get CcCredential
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/8/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b2b5aefb-a08d-4bec-9204-76597d413849
description: Get-CcCredential コマンドレットは、現在の Skype for Business Cloud Connector エディションの展開の資格情報を返します。
ms.openlocfilehash: 4d8c9d95b9de0930e0c332f419f00947ca271821
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="get-cccredential"></a>Get CcCredential
 
Get-CcCredential コマンドレットは、現在の Skype for Business Cloud Connector エディションの展開の資格情報を返します。 
  
バージョン 2.0 以降のバージョンとは、TenantAdmin、DomainAdmin、および VMAdmin のパスワードを表示するのには-DisplayPassword パラメーターを使用することができますもします。
  
```
Get-CcCredential [[-AccountType] <string> {VmAdmin | DomainAdmin | SafeModeAdmin | ExternalCert | TenantAdmin}]
```

## <a name="examples"></a>例
<a name="Examples"> </a>

### <a name="example-1"></a>例 1

次の例は、Cloud Connector 仮想マシン ドメインのドメイン管理者の資格情報を返します。
  
```
Get-CcCredential -AccountType DomainAdmin
```

## <a name="detailed-description"></a>解説
<a name="DetailedDescription"> </a>

Get-CcCredential コマンドレットは指定したアカウントの種類についての資格情報を返します。これらの資格情報は、現在のアプライアンスの展開時に Register-CcAppliance コマンドレットおよび Install-CcAppliance コマンドレットを実行する管理者によって指定されます。 
  
Get-CcCredential コマンドレットは、System.Management.Automation.PSCredential オブジェクトのインスタンスを返します。戻りオブジェクトのパスワード プロパティは　System.Security.SecureString です。
  
ドメイン管理者のパスワードのクリア テキストを取得する場合は、必ずホスト サーバーの現在のログオン アカウントでパスワードが入力されるようにしてから、PowerShell コンソールを管理者として開いて以下のスクリプトを実行してください。
  
```
$cred = Get-CcCredential -AccountType DomainAdmin
$password =  $cred.Password
$bstr = [System.Runtime.InteropServices.Marshal]::SecureStringToBSTR($password);
$text = [System.Runtime.InteropServices.Marshal]::PtrToStringAuto($bstr);
[System.Runtime.InteropServices.Marshal]::ZeroFreeBSTR($bstr);
Write-Host $text

```

## <a name="parameters"></a>パラメーター
<a name="DetailedDescription"> </a>

|**パラメーター**|**必須**|**タイプ**|**説明**|
|:-----|:-----|:-----|:-----|
| AccountType <br/> |必須  <br/> | System.String <br/> | AccountType の値は次のいずれかになります。 <br/>  VmAdmin: 仮想マシンのクラウドのコネクタのローカル管理者。 <br/>  クラウド コネクタの仮想マシンのドメインの DomainAdmin: ドメイン管理者。 <br/>  SafeModeAdmin: Cloud Connector 仮想マシンのドメイン コントローラーの SafeModeAdmin。 <br/>  ExternalCert: エッジー サーバー上にインストールされた外部証明書のアカウント。 <br/>  TenantAdmin: O365 テナントの管理者。 <br/> |
   
## <a name="input-types"></a>入力の種類
<a name="InputTypes"> </a>

なし。Get-CcCredential コマンドレットはパイプライン入力を受け入れません。
  
## <a name="return-types"></a>戻り値の種類
<a name="ReturnTypes"> </a>

Get-CcCredential コマンドレットは、System.Management.Automation.PSCredential オブジェクトのインスタンスを返します。
  
## <a name="see-also"></a>関連項目
<a name="ReturnTypes"> </a>

[セット CcCredential](set-cccredential.md)
  

