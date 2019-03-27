---
title: Get-CcExternalCertificateFilePath
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 62fdc9cc-e82e-463f-b8b3-05d5c6482ea2
description: Get-CcExternalCertificateFilePath コマンドレットは、Skype for Business Cloud Connector エディションの展開用に外部証明書ファイルのパスを返します。 この証明書はユーザーが準備します。
ms.openlocfilehash: 997b5d7a39decf11a19c307f4e7a7b439069441f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30882587"
---
# <a name="get-ccexternalcertificatefilepath"></a>Get-CcExternalCertificateFilePath
 
Get-CcExternalCertificateFilePath コマンドレットは、Skype for Business Cloud Connector エディションの展開用に外部証明書ファイルのパスを返します。この証明書はユーザーが準備します。
  
このコマンドレットは、Skype for Business Cloud Connector エディション 1.4.1、1.4.2 に適用されます。
  
```
Get-CcExternalCertificateFilePath [[-Target] <string> {EdgeServer | MediationServer}]
```

## <a name="examples"></a>例
<a name="Examples"> </a>

### <a name="example-1"></a>例 1

次の例では、エッジ サーバーの証明書のパスを示します。
  
```
Get-CcExternalCertificateFilePath -Target EdgeServer
```

### <a name="example-2"></a>例 2

次の例では、仲介サーバーの証明書セットを示します。
  
```
Get-CcExternalCertificateFilePath -Target MediationServer
```

## <a name="detailed-description"></a>解説
<a name="DetailedDescription"> </a>

展開中またはトポロジの変更時には、エッジ サーバーの証明書および仲介サーバーの証明書 (省略可能) のパスを指定する必要があります。仲介サーバーの証明書は、ゲートウェイと仲介サーバーの間に TLS を使用する場合に必要です。パスを変更するには、Set-CcExternalCertificateFilePath コマンドレットを使用します。
  
## <a name="parameters"></a>パラメーター
<a name="DetailedDescription"> </a>

|**パラメーター**|**必須**|**型**|**説明**|
|:-----|:-----|:-----|:-----|
|Target  <br/> |省略可能  <br/> | System.Management.Automation.SwitchParameter <br/> |必要なファイル パスの種類。種類:  <br/> EdgeServer (既定)  <br/> MediationServer  <br/> |
   
## <a name="input-types"></a>入力の種類
<a name="InputTypes"> </a>

Get-CcExternalCertificateFilePath コマンドレットはパイプライン入力を受け入れません。
  
## <a name="return-types"></a>戻り値の種類
<a name="ReturnTypes"> </a>

このコマンドはファイル パスを返します。
  
## <a name="see-also"></a>関連項目
<a name="ReturnTypes"> </a>

[Set-CcExternalCertificateFilePath](set-ccexternalcertificatefilepath.md)
  

