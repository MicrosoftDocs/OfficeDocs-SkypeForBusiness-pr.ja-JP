---
title: Get-CcExternalCertificateFilePath
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 62fdc9cc-e82e-463f-b8b3-05d5c6482ea2
description: このGet-CcExternalCertificateFilePathは、展開の外部証明書ファイル パスをSkype for Business クラウド コネクタ エディションします。 ユーザーは、この証明書を準備します。
ms.openlocfilehash: 9b06958d68d73bc68fc0fda4e681af2e7b9b4f9e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58622039"
---
# <a name="get-ccexternalcertificatefilepath"></a>Get-CcExternalCertificateFilePath
 
このGet-CcExternalCertificateFilePathは、展開の外部証明書ファイル パスをSkype for Business クラウド コネクタ エディションします。 ユーザーは、この証明書を準備します。
  
このコマンドレットは、Skype for Business クラウド コネクタ エディション 1.4.1、1.4.2 に適用されます。
  
```powershell
Get-CcExternalCertificateFilePath [[-Target] <string> {EdgeServer | MediationServer}]
```

## <a name="examples"></a>例
<a name="Examples"> </a>

### <a name="example-1"></a>例 1

次の例は、エッジ サーバーの証明書のパスを示しています。
  
```powershell
Get-CcExternalCertificateFilePath -Target EdgeServer
```

### <a name="example-2"></a>例 2

次の例は、仲介サーバーの証明書セットを示しています。
  
```powershell
Get-CcExternalCertificateFilePath -Target MediationServer
```

## <a name="detailed-description"></a>解説
<a name="DetailedDescription"> </a>

展開中、またはトポロジを変更する場合は、エッジ サーバー証明書のパスと、必要に応じて仲介サーバーのパスを指定する必要があります。 ゲートウェイと仲介サーバーの間で TLS を使用する場合は、仲介サーバーの証明書が必要です。 パスを変更するには、次のコマンドレットSet-CcExternalCertificateFilePathします。
  
## <a name="parameters"></a>パラメーター
<a name="DetailedDescription"> </a>

|**パラメーター**|**Required**|**Type**|**説明**|
|:-----|:-----|:-----|:-----|
|対象  <br/> |省略可  <br/> | System.Management.Automation.SwitchParameter <br/> |要求されたファイル パスの種類。 型には、次のものが含まれます。  <br/> EdgeServer (既定)  <br/> MediationServer  <br/> |
   
## <a name="input-types"></a>入力の種類
<a name="InputTypes"> </a>

このGet-CcExternalCertificateFilePathは、パイプライン処理された入力を受け付け取らない。
  
## <a name="return-types"></a>戻り値の種類
<a name="ReturnTypes"> </a>

コマンドはファイル パスを返します。
  
## <a name="see-also"></a>関連項目
<a name="ReturnTypes"> </a>

[Set-CcExternalCertificateFilePath](set-ccexternalcertificatefilepath.md)
  

