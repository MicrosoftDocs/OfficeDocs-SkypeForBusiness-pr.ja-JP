---
title: Get-CcApplianceLogDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8f16d8ea-8161-4b07-9c79-d57e786b3e78
description: このGet-CcApplianceLogDirectoryは、アプライアンスのログが格納されている現在Skype for Business クラウド コネクタ エディションを示します。
ms.openlocfilehash: 75f3ba3a5de5198456e053bd51ef567df1a0ae43461e9888e87294d3af406288
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54318660"
---
# <a name="get-ccappliancelogdirectory"></a>Get-CcApplianceLogDirectory
 
このGet-CcApplianceLogDirectoryは、アプライアンスのログが格納されている現在Skype for Business クラウド コネクタ エディションを示します。
  
このコマンドレットは、Skype for Business クラウド コネクタ エディション 1.4.1、1.4.2 に適用されます。
  
```powershell
Get-CcApplianceLogDirectory
```

## <a name="parameters"></a>パラメーター

なし
  
## <a name="examples"></a>例
<a name="Examples"> </a>

### <a name="example-1"></a>例 1

次の例は、クラウド コネクタの現在のアプライアンスのログが格納されている現在のフォルダーを示しています。
  
```powershell
Get-CcApplianceLogDirectory
```

## <a name="detailed-description"></a>解説
<a name="DetailedDescription"> </a>

このGet-CcApplianceLogDirectoryは、クラウド コネクタ アプライアンスのログが格納されている現在のディレクトリを示します。 既定のフォルダーは C:\Users \% userprofile%\CloudConnector\ApplianceRoot\Logs です。 
  
ディレクトリは、このコマンドレットを使用してSet-CcApplianceDirectoryできます。 
  
注: アプライアンス ディレクトリを変更せずにログ フォルダーの場所のみを変更するコマンドレットはありません。
  
## <a name="input-types"></a>入力の種類
<a name="InputTypes"> </a>

なし。 このGet-CcApplianceLogDirectoryは、パイプライン処理された入力を受け付け取らない。
  
## <a name="return-types"></a>戻り値の種類
<a name="ReturnTypes"> </a>

このコマンドは、ファイル パスを返します。
  
## <a name="see-also"></a>関連項目
<a name="ReturnTypes"> </a>

[Set-CcApplianceDirectory](set-ccappliancedirectory.md)
  

