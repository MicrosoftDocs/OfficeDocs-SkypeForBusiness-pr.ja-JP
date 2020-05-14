---
title: Set-CcCredential
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
ms.assetid: 784ff94a-4b33-4dbd-ba74-27acc3eb6954
description: CcCredential コマンドレットは、現在の Skype for Business Cloud Connector エディションの展開の資格情報を設定します。
ms.openlocfilehash: 3717eb0dcaa46bb6708f40ecb7f94869f24774a2
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221571"
---
# <a name="set-cccredential"></a>Set-CcCredential
 
CcCredential コマンドレットは、現在の Skype for Business Cloud Connector エディションの展開の資格情報を設定します。 
  
Cloud Connector バージョン2.0 以降では、このコマンドレットを使用して、仮想マシン管理者とドメイン管理者のアカウント情報を設定することもできます。
  
```powershell
Set-CcCredential [[-AccountType] <string> {TenantAdmin}]
```

## <a name="examples"></a>例
<a name="Examples"> </a>

### <a name="example-1"></a>例 1

次の例では、テナント管理者のアカウント名とパスワードを指定します。
  
```powershell
Set-CcCredential -AccountType "TenantAdmin"
```

## <a name="detailed-description"></a>解説
<a name="DetailedDescription"> </a>

CcCredential コマンドレットは、テナント管理者のアカウント名とパスワードを設定します。 2.0 より前のリリースでは、この管理者はグローバル管理者である必要があります。 Cloud Connector はこのアカウントを使用して、構成情報を取得し、構成パラメーターを設定し、アプライアンスの状態を Microsoft 365 または Office 365 組織の構成に更新します。 リリース2.0 以降では、このコマンドレットを使用して、VmAdmin および DomainAdmin アカウントのパスワードを更新することもできます。
  
## <a name="parameters"></a>パラメーター
<a name="DetailedDescription"> </a>

|**パラメーター**|**Required**|**Type**|**説明**|
|:-----|:-----|:-----|:-----|
| AccountType <br/> | 必須 <br/> |System.String  <br/> | パラメーターの値は、"TenantAdmin"、"VmAdmin"、または "DomainAdmin" である必要があります。 <br/> |
   
## <a name="input-types"></a>入力の種類
<a name="InputTypes"> </a>

なし。 CcCredential コマンドレットはパイプライン入力を受け入れません。
  
## <a name="return-types"></a>戻り値の種類
<a name="ReturnTypes"> </a>

なし
  
## <a name="see-also"></a>関連項目
<a name="ReturnTypes"> </a>

[Get-CcCredential](get-cccredential.md)
  

