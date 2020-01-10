---
title: Restore-CcCredentials
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aeca610b-db0a-45cf-95b9-ae9a6bbccb45
description: '[Cc-Credentials の復元] コマンドレットは、現在の Skype for Business Cloud Connector エディションの展開のすべての資格情報を復元します。'
ms.openlocfilehash: adac3f0b9ca6cf392b537a9c5d0f2095021c7120
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003247"
---
# <a name="restore-cccredentials"></a>Restore-CcCredentials
 
[Cc-Credentials の復元] コマンドレットは、現在の Skype for Business Cloud Connector エディションの展開のすべての資格情報を復元します。 
  
このコマンドレットは、Skype for Business Cloud Connector エディション2.1 に適用されます。
  
```powershell
Restore-CcCredentials 
```

## <a name="detailed-description"></a>解説

Restore/CcCredentials コマンドレットはすべての資格情報を消去し、現在の Skype for Business Cloud Connector の展開で使用されるすべての資格情報を再入力するように求めます。
  
## <a name="parameters"></a>パラメーター

なし
  
## <a name="input-types"></a>入力の種類

なし。 Restore-CcCredentials コマンドレットはパイプライン入力を受け取りません。
  
## <a name="return-types"></a>戻り値の種類

なし。
  
## <a name="example"></a>例

次の例では、現在のクラウドコネクタ展開のすべての資格情報を復元します。
  
```powershell
    PS C:\>Restore-CcCredentials
```

## <a name="see-also"></a>関連項目

[Get-CcCredential](get-cccredential.md)
  
[Set-CcCredential](set-cccredential.md)
  

