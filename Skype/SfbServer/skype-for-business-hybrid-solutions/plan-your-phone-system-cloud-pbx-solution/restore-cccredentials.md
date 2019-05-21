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
ms.openlocfilehash: efa1bcda9af6abccd2ced0faf1e772e779a4483f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287084"
---
# <a name="restore-cccredentials"></a>Restore-CcCredentials
 
[Cc-Credentials の復元] コマンドレットは、現在の Skype for Business Cloud Connector エディションの展開のすべての資格情報を復元します。 
  
このコマンドレットは、Skype for Business Cloud Connector エディション2.1 に適用されます。
  
```
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
  
```
    PS C:\>Restore-CcCredentials
```

## <a name="see-also"></a>関連項目

[Get-CcCredential](get-cccredential.md)
  
[Set-CcCredential](set-cccredential.md)
  

