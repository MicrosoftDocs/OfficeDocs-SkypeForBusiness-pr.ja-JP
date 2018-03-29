---
title: セット CcExternalCertificateFilePath
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 443d071e-633e-4337-b20b-f30cdfbd4aaf
description: Set-CcExternalCertificateFilePath コマンドレットは仲介サーバーまたはエッジ サーバーの証明書が保管されているパスを指定します。
ms.openlocfilehash: 89216fb2b56130dd76b711a483c6279ac1073392
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="set-ccexternalcertificatefilepath"></a>セット CcExternalCertificateFilePath
 
Set-CcExternalCertificateFilePath コマンドレットは仲介サーバーまたはエッジ サーバーの証明書が保管されているパスを指定します。
  
この証明書は、展開時や Skype for Business Cloud Connector エディションの新しいアプライアンスを追加するときに必要になります。コマンドにより、展開後に仲介サーバーの新しい証明書をインポートすることも可能になります。
  
このコマンドレットは Skype for Business Cloud Connector エディション 1.4.1、1.4.2 に適用されます。
  
```
Set-CcExternalCertificateFilePath [-Target] <string> {EdgeServer | MediationServer} [-Path] <string> [-Import]  [<CommonParameters>]
```

## <a name="examples"></a>例
<a name="Examples"> </a>

### <a name="example-1"></a>例 1

次の例は、エッジ サーバーの証明書のパスを設定します。
  
```
Set-CcExternalCertificateFilePath -Target EdgeServer -Path C:\CloudConnector\Certificates\AdatumPublicEdge.pfx
```

### <a name="example-2"></a>例 2

次の例は、仲介サーバーの証明書のパスを設定します。
  
```
Set-CcExternalCertificateFilePath -Target MediationServer -Path C:\CloudConnector\Certificates\AdatumPublicMediation.pfx
```

### <a name="example-3"></a>例 3

次の例は、仲介サーバーの証明書を更新します。
  
```
Set-CcExternalCertificateFilePath -Target MediationServer -Path C:\CloudConnector\Certificates\AdatumPublicMediation.pfx -Import
```

## <a name="detailed-description"></a>解説
<a name="DetailedDescription"> </a>

展開時またはトポロジを変更しているときに、エッジ サーバーの証明書のパスを指定する必要があります。必要に応じて、仲介サーバーの証明書のパスも任意で指定します。 
  
仲介サーバーの証明書は、TLS がゲートウェイと仲介サーバーの間で使用される場合に必要となります。 クラウド コネクタのアプライアンスを導入し、TLS を展開する仲介サーバー上に配置される証明書へのパスのみ指定できます。 ただし、既に展開済みのアプライアンス上の仲介証明書を更新する場合は、パスと -Import パラメーターを指定する必要があります。 パスを表示するには、Get-CCExternalCertificateFilePath コマンドレットを使用します。
  
## <a name="parameters"></a>パラメーター
<a name="DetailedDescription"> </a>

|**パラメーター**|**必須**|**タイプ**|**説明**|
|:-----|:-----|:-----|:-----|
| Target <br/> | 必須 <br/> |System.String  <br/> |必要なファイル パスの種類。種類:  <br/> EdgeServer (既定)  <br/> MediationServer  <br/> |
|Import  <br/> |省略可能  <br/> |System.Management.Automation.SwitchParameter  <br/> |証明書が仲介サーバーにインポートされる必要があることを示します。初めてアプライアンスを展開する場合は、このパラメーターは必要ありません。このパラメーターは、既に展開済みのバージョン上で、既存の証明書を変更する場合に必要です。  <br/> |
   
## <a name="input-types"></a>入力の種類
<a name="InputTypes"> </a>

Set-CcExternalCertificateFilePath コマンドレットはパイプライン入力を受け入れません。
  
## <a name="return-types"></a>戻り値の種類
<a name="ReturnTypes"> </a>

なし
  
## <a name="see-also"></a>関連項目
<a name="ReturnTypes"> </a>

[Get CcExternalCertificateFilePath](get-ccexternalcertificatefilepath.md)
  

