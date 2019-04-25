---
title: Get-CcCredential
ms.reviewer: ''
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
ms.openlocfilehash: 651190f31ad44e0bb2375bbf4a70951c2011e1a7
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32233996"
---
# <a name="get-cccredential"></a>Get-CcCredential
 
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

|**パラメーター**|**必須**|**型**|**説明**|
|:-----|:-----|:-----|:-----|
| AccountType <br/> |必須  <br/> | System.String <br/> | AccountType の値は次のいずれかになります。 <br/>  VmAdmin: 仮想マシンのクラウドのコネクタのローカル管理者。 <br/>  DomainAdmin: Cloud Connector 仮想マシン ドメインのドメイン管理者。 <br/>  SafeModeAdmin: Cloud Connector 仮想マシンのドメイン コントローラーの SafeModeAdmin。 <br/>  ExternalCert: エッジー サーバー上にインストールされた外部証明書のアカウント。 <br/>  TenantAdmin: O365 テナントの管理者。 <br/> |
   
## <a name="input-types"></a>入力の種類
<a name="InputTypes"> </a>

なし。Get-CcCredential コマンドレットはパイプライン入力を受け入れません。
  
## <a name="return-types"></a>戻り値の種類
<a name="ReturnTypes"> </a>

Get-CcCredential コマンドレットは、System.Management.Automation.PSCredential オブジェクトのインスタンスを返します。
  
## <a name="see-also"></a>関連項目
<a name="ReturnTypes"> </a>

[Set-CcCredential](set-cccredential.md)
  

