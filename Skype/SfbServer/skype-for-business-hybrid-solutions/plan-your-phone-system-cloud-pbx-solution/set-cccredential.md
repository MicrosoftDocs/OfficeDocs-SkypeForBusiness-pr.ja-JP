---
title: Set-CcCredential
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/8/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 784ff94a-4b33-4dbd-ba74-27acc3eb6954
description: Set-CcCredential コマンドレットは、現在の Skype for Business Cloud Connector エディションの展開の資格情報を設定します。
ms.openlocfilehash: 547f0b87b006347a337a2c25222aecbd4f402669
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30876642"
---
# <a name="set-cccredential"></a>Set-CcCredential
 
Set-CcCredential コマンドレットは、現在の Skype for Business Cloud Connector エディションの展開の資格情報を設定します。 
  
クラウド コネクタ バージョン 2.0 以降では、このコマンドレットも設定できますアカウントについては、仮想マシンの管理者およびドメイン管理者。
  
```
Set-CcCredential [[-AccountType] <string> {TenantAdmin}]
```

## <a name="examples"></a>例
<a name="Examples"> </a>

### <a name="example-1"></a>例 1

次の例は、テナント管理者のアカウント名とパスワードを指定します。
  
```
Set-CcCredential -AccountType "TenantAdmin"
```

## <a name="detailed-description"></a>解説
<a name="DetailedDescription"> </a>

Set-CcCredential コマンドレットによって、テナント管理者のアカウント名とパスワードが設定されます。 2.0 より前のリリースでは、この管理者は、Office 365 の全体管理者である必要があります。 クラウドのコネクタは、構成情報を取得、構成パラメーター、およびアプライアンスの状態の更新プログラムを Office 365 のテナント構成に設定するのにはこのアカウントを使用します。 2.0 のリリースし、後で使用することもこのコマンドレット、VmAdmin および DomainAdmin のアカウントのパスワードを更新します。
  
## <a name="parameters"></a>パラメーター
<a name="DetailedDescription"> </a>

|**パラメーター**|**必須**|**型**|**説明**|
|:-----|:-----|:-----|:-----|
| AccountType <br/> | 必須 <br/> |System.String  <br/> | パラメーター値は「TenantAdmin」、「VmAdmin」、または「DomainAdmin」にする必要があります。 <br/> |
   
## <a name="input-types"></a>入力の種類
<a name="InputTypes"> </a>

なし。Set-CcCredential コマンドレットはパイプライン入力を受け入れません。
  
## <a name="return-types"></a>戻り値の種類
<a name="ReturnTypes"> </a>

なし
  
## <a name="see-also"></a>関連項目
<a name="ReturnTypes"> </a>

[Get-CcCredential](get-cccredential.md)
  

