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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: aeca610b-db0a-45cf-95b9-ae9a6bbccb45
description: Restore Cc-Credentialsコマンドレットは、現在の展開のすべての資格情報をSkype for Business クラウド コネクタ エディションします。
ms.openlocfilehash: 95b93e28bb109c26927a940324edef20479bed8c193efea6923c74058995a5bd
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54340673"
---
# <a name="restore-cccredentials"></a>Restore-CcCredentials
 
Restore Cc-Credentialsコマンドレットは、現在の展開のすべての資格情報をSkype for Business クラウド コネクタ エディションします。 
  
このコマンドレットは、2.1 Skype for Business クラウド コネクタ エディションに適用されます。
  
```powershell
Restore-CcCredentials 
```

## <a name="detailed-description"></a>解説

このRestore-CcCredentialsコマンドレットは、すべての資格情報をクリーンアップし、現在のクラウド コネクタ展開で使用Skype for Business資格情報を再入力するように求めるメッセージを表示します。
  
## <a name="parameters"></a>パラメーター

なし
  
## <a name="input-types"></a>入力の種類

なし。 このRestore-CcCredentialsは、パイプライン処理された入力を受け付け取らない。
  
## <a name="return-types"></a>戻り値の種類

なし。
  
## <a name="example"></a>例

次の使用例は、現在のクラウド コネクタ展開のすべての資格情報を復元します。
  
```powershell
    PS C:\>Restore-CcCredentials
```

## <a name="see-also"></a>関連項目

[Get-CcCredential](get-cccredential.md)
  
[Set-CcCredential](set-cccredential.md)
  

