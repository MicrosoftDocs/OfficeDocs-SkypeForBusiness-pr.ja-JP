---
title: 復元 CcCredentials
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aeca610b-db0a-45cf-95b9-ae9a6bbccb45
description: Cc-資格情報の復元コマンドレットでは、ビジネスのクラウド コネクタのエディションの展開の現在の Skype のすべての資格情報を復元します。
ms.openlocfilehash: bb74444c5f63b792abf6c12c317c1a824298426c
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569734"
---
# <a name="restore-cccredentials"></a>復元 CcCredentials
 
Cc-資格情報の復元コマンドレットでは、ビジネスのクラウド コネクタのエディションの展開の現在の Skype のすべての資格情報を復元します。 
  
このコマンドレットは、クラウド コネクタ版 2.1 のビジネスには、Skype に適用されます。
  
```
Restore-CcCredentials 
```

## <a name="detailed-description"></a>解説

復元 CcCredentials コマンドレットでは、すべての資格情報をクリーンアップし、ビジネスのクラウドのコネクタの配置の現在の Skype を使用するすべての資格情報を再入力するように求められます。
  
## <a name="parameters"></a>パラメーター

なし
  
## <a name="input-types"></a>入力の種類

なし。 復元 CcCredentials コマンドレットでは、パイプラインの入力は受け付けられません。
  
## <a name="return-types"></a>戻り値の種類

なし。
  
## <a name="example"></a>例

次の例では、現在のクラウドのコネクタの配置のすべての資格情報が復元されます。
  
```
    PS C:\>Restore-CcCredentials
```

## <a name="see-also"></a>関連項目

[Get CcCredential](get-cccredential.md)
  
[セット CcCredential](set-cccredential.md)
  

