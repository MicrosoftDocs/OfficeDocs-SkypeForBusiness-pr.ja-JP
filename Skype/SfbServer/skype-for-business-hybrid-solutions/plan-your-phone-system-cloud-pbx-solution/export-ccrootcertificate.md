---
title: Export-CcRootCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/20/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1499e33c-6a7c-46b9-b9a1-f78d7853b45d
description: このExport-CcRootCertificateは、ルート CA 証明書をホスト サーバー上のローカル ファイルSkype for Business クラウド コネクタ エディションします。
ms.openlocfilehash: 04ba7af5801f124a76e515b311a0507e3cbb764a6f2769d9f1d9080ec8c7d9d9
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54326253"
---
# <a name="export-ccrootcertificate"></a>Export-CcRootCertificate
 
このExport-CcRootCertificateは、ルート CA 証明書をホスト サーバー上のローカル ファイルSkype for Business クラウド コネクタ エディションします。 
  
```powershell
Export-CcRootCertificate [[-Path] <string>]
```

## <a name="examples"></a>例
<a name="Examples"> </a>

### <a name="example-1"></a>例 1

次の使用例は、Path パラメーターをファイル パスではなくディレクトリ パスとして設定します。 ファイル c:\test\CCERootCertificates.p7b を生成します。
  
```powershell
Export-CcRootCertificate -Path "C:\test" 
```

## <a name="detailed-description"></a>解説
<a name="DetailedDescription"> </a>

このExport-CcRootCertificateを使用すると、ルート証明書と中間証明書をファイル パスに保存できます。 これは、障害復旧シナリオの場合に役立ちます。 
  
## <a name="parameters"></a>パラメーター
<a name="DetailedDescription"> </a>

|**パラメーター**|**Required**|**型**|**説明**|
|:-----|:-----|:-----|:-----|
|Path  <br/> |必須  <br/> |System.String  <br/> |証明書が保存されるファイル パス。  <br/> |
   
## <a name="input-types"></a>入力の種類
<a name="InputTypes"> </a>

なし。 このExport-CcRootCertificateは、パイプライン処理された入力を受け付け取らない。 
  
## <a name="return-types"></a>戻り値の種類
<a name="ReturnTypes"> </a>

なし
  
## <a name="see-also"></a>関連項目
<a name="ReturnTypes"> </a>

なし
  

