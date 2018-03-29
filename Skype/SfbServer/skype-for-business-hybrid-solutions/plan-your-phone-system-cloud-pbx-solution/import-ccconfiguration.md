---
title: インポート-CcConfiguration
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 10/11/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 461361a0-9aa9-469d-ace0-dc70b95cd4a3
description: クラウド コネクタのホスト サーバーにローカル ファイルから、Skype ビジネス クラウド コネクタのエディション構成をインポートします。
ms.openlocfilehash: 46f4099258ce4090fa23ec980801e55f7300895f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="import-ccconfiguration"></a>インポート-CcConfiguration
 
クラウド コネクタのホスト サーバーにローカル ファイルから、Skype ビジネス クラウド コネクタのエディション構成をインポートします。
  
```

Import-CcConfiguration [-Force] [<CommonParameters>]
```

## <a name="examples"></a>例
<a name="Examples"> </a>

### <a name="example-1"></a>例 1

次の例では、%SystemDrive%\ProgramData\CloudConnector ディレクトリに、クラウドのコネクタ インスタンスのアプライアンスのディレクトリから、CloudConnector.ini をコピーします。
  
```
Import-CcConfiguration
```

## <a name="detailed-description"></a>解説
<a name="Examples"> </a>

このコマンドレットは、クラウドのコネクタのアプライアンスのアプライアンスのディレクトリから %SystemDrive%\ProgramData\CloudConnector ディレクトリに、CloudConnector.ini をコピーします。 アプライアンス ディレクトリは Set-CcApplianceDirectory コマンドレットを使用して指定されます。 コマンドレットは、%systemdrive%\programdata\cloudconnector で既存のファイルで上書きされます。 クラウド コネクタ版 2.0.1 にこのコマンドが適用されると、後で。
  
## <a name="parameters"></a>パラメーター
<a name="Examples"> </a>

|**パラメーター**|**必須**|**タイプ**|**説明**|
|:-----|:-----|:-----|:-----|
|Force  <br/> |省略可能  <br/> |System.Management.Automation.SwitchParameter  <br/> |%SystemDrive%\ProgramData\CloudConnector 警告を表示せずに既存のファイルを上書きします。  <br/> |
   
## <a name="input-types"></a>入力の種類
<a name="Examples"> </a>

なし。 インポート CcConfiguration コマンドレットでは、パイプラインの入力は受け付けられません。
  
## <a name="return-types"></a>戻り値の種類
<a name="Examples"> </a>

なし。
  
## <a name="see-also"></a>関連項目
<a name="Examples"> </a>

エクスポート CcConfiguration
  

