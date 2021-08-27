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
ms.localizationpriority: medium
ms.assetid: 784ff94a-4b33-4dbd-ba74-27acc3eb6954
description: このSet-CcCredentialは、現在の展開の資格情報をSkype for Business クラウド コネクタ エディションします。
ms.openlocfilehash: fa0d5f69e3263d273fabe17ae74ea46e0af40908
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58617669"
---
# <a name="set-cccredential"></a>Set-CcCredential
 
このSet-CcCredentialは、現在の展開の資格情報をSkype for Business クラウド コネクタ エディションします。 
  
クラウド コネクタ バージョン 2.0 以降では、このコマンドレットは仮想マシン管理者とドメイン管理者のアカウント情報を設定することもできます。
  
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

このSet-CcCredentialは、テナント管理者のアカウント名とパスワードを設定します。 2.0 より前のリリースでは、この管理者はグローバル管理者である必要があります。 Cloud Connector は、このアカウントを使用して構成情報を取得し、構成パラメーターを設定し、アプライアンスの状態を組織の構成Microsoft 365またはOffice 365更新します。 リリース 2.0 以降では、このコマンドレットを使用して VmAdmin アカウントと DomainAdmin アカウントのパスワードを更新することもできます。
  
## <a name="parameters"></a>パラメーター
<a name="DetailedDescription"> </a>

|**パラメーター**|**Required**|**Type**|**説明**|
|:-----|:-----|:-----|:-----|
| AccountType <br/> | 必須 <br/> |System.String  <br/> | パラメーターの値は、"TenantAdmin"、"VmAdmin"、または "DomainAdmin" である必要があります。 <br/> |
   
## <a name="input-types"></a>入力の種類
<a name="InputTypes"> </a>

なし。 このSet-CcCredentialは、パイプライン処理された入力を受け付け取らない。
  
## <a name="return-types"></a>戻り値の種類
<a name="ReturnTypes"> </a>

なし
  
## <a name="see-also"></a>関連項目
<a name="ReturnTypes"> </a>

[Get-CcCredential](get-cccredential.md)
  

