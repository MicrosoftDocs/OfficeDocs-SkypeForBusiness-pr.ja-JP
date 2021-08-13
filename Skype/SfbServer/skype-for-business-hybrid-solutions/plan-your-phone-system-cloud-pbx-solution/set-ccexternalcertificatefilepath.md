---
title: Set-CcExternalCertificateFilePath
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
ms.assetid: 443d071e-633e-4337-b20b-f30cdfbd4aaf
description: このSet-CcExternalCertificateFilePathコマンドレットは、仲介サーバーまたはエッジ サーバーの証明書が格納されるパスを指定します。
ms.openlocfilehash: 7b9b494b27f3ed05dd1ef1cdb91bd583abf2d2b391f1a49c0b2615fd3485187c
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54344566"
---
# <a name="set-ccexternalcertificatefilepath"></a>Set-CcExternalCertificateFilePath
 
このSet-CcExternalCertificateFilePathコマンドレットは、仲介サーバーまたはエッジ サーバーの証明書が格納されるパスを指定します。
  
この証明書は、展開中または新しいアプライアンスの追加時にSkype for Business クラウド コネクタ エディション。 また、展開後に仲介サーバーの新しい証明書をインポートすることもできます。
  
このコマンドレットは、Skype for Business クラウド コネクタ エディション 1.4.1、1.4.2 に適用されます。
  
```powershell
Set-CcExternalCertificateFilePath [-Target] <string> {EdgeServer | MediationServer} [-Path] <string> [-Import]  [<CommonParameters>]
```

## <a name="examples"></a>例
<a name="Examples"> </a>

### <a name="example-1"></a>例 1

次の使用例は、エッジ サーバーの証明書のパスを設定します。
  
```powershell
Set-CcExternalCertificateFilePath -Target EdgeServer -Path C:\CloudConnector\Certificates\AdatumPublicEdge.pfx
```

### <a name="example-2"></a>例 2

次の例では、仲介サーバーの証明書のパスを設定します。
  
```powershell
Set-CcExternalCertificateFilePath -Target MediationServer -Path C:\CloudConnector\Certificates\AdatumPublicMediation.pfx
```

### <a name="example-3"></a>例 3

次の例では、仲介サーバーの証明書を更新します。
  
```powershell
Set-CcExternalCertificateFilePath -Target MediationServer -Path C:\CloudConnector\Certificates\AdatumPublicMediation.pfx -Import
```

## <a name="detailed-description"></a>解説
<a name="DetailedDescription"> </a>

展開中、またはトポロジの変更中に、エッジ サーバー証明書のパスと、必要に応じて仲介サーバー証明書のパスを指定する必要があります。 
  
ゲートウェイと仲介サーバーの間で TLS を使用する場合は、仲介サーバーの証明書が必要です。 クラウド コネクタ アプライアンスを展開し、TLS を展開する場合は、仲介サーバーに展開される証明書へのパスのみを指定できます。 ただし、既に展開されているアプライアンスで仲介証明書を更新する場合は、パスと -Import パラメーターを指定する必要があります。 パスを表示するには、次のコマンドレットGet-CCExternalCertificateFilePathします。
  
## <a name="parameters"></a>パラメーター
<a name="DetailedDescription"> </a>

|**パラメーター**|**Required**|**型**|**説明**|
|:-----|:-----|:-----|:-----|
| Target <br/> | 必須 <br/> |System.String  <br/> |要求されたファイル パスの種類。 型には、次のものが含まれます。  <br/> EdgeServer (既定)  <br/> MediationServer  <br/> |
|インポート  <br/> |省略可  <br/> |System.Management.Automation.SwitchParameter  <br/> |証明書を仲介サーバーにインポートする必要があります。 アプライアンスを初めて展開する場合、このパラメーターは必要ではありません。 既に展開されているバージョンの既存の証明書を変更する場合は、このパラメーターが必要です。  <br/> |
   
## <a name="input-types"></a>入力の種類
<a name="InputTypes"> </a>

このSet-CcExternalCertificateFilePathは、パイプライン処理された入力を受け付け取らない。
  
## <a name="return-types"></a>戻り値の種類
<a name="ReturnTypes"> </a>

なし
  
## <a name="see-also"></a>関連項目
<a name="ReturnTypes"> </a>

[Get-CcExternalCertificateFilePath](get-ccexternalcertificatefilepath.md)
  

