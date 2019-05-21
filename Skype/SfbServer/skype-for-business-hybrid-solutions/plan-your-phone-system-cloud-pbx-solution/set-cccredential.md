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
localization_priority: Normal
ms.assetid: 784ff94a-4b33-4dbd-ba74-27acc3eb6954
description: Set-CcCredential コマンドレットは、現在の Skype for Business Cloud Connector エディションの展開の資格情報を設定します。
ms.openlocfilehash: 59c058f8965bbc6fc011806f383c547c1e7b6cd1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286979"
---
# <a name="set-cccredential"></a>Set-CcCredential
 
Set-CcCredential コマンドレットは、現在の Skype for Business Cloud Connector エディションの展開の資格情報を設定します。 
  
Cloud Connector バージョン2.0 以降では、このコマンドレットでは、仮想マシン管理者とドメイン管理者のアカウント情報を設定することもできます。
  
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

Set-CcCredential コマンドレットによって、テナント管理者のアカウント名とパスワードが設定されます。 2.0 より前のリリースでは、この管理者は、Office 365 の全体管理者である必要があります。 クラウドコネクタはこのアカウントを使用して、構成情報を取得し、構成パラメーターを設定し、アプライアンスの状態を Office 365 テナント構成に更新します。 リリース2.0 以降では、このコマンドレットを使用して、VmAdmin および DomainAdmin アカウントのパスワードを更新することもできます。
  
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
  

