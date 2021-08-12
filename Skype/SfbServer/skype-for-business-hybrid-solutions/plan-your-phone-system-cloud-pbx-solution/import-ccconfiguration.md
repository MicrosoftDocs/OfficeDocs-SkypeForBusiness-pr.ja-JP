---
title: Import-CcConfiguration
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 10/11/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 461361a0-9aa9-469d-ace0-dc70b95cd4a3
description: ローカル ファイルからSkype for Business クラウド コネクタ エディション構成を Cloud Connector ホスト サーバーにインポートします。
ms.openlocfilehash: 4ac32f460c2c493f5d78f1a38adcdd0728763bbbcf57a67470823fb88d407d09
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54349499"
---
# <a name="import-ccconfiguration"></a>Import-CcConfiguration
 
ローカル ファイルからSkype for Business クラウド コネクタ エディション構成を Cloud Connector ホスト サーバーにインポートします。
  
```powershell
Import-CcConfiguration [-Force] [<CommonParameters>]
```

## <a name="examples"></a>例
<a name="Examples"> </a>

### <a name="example-1"></a>例 1

次の使用例はCloudConnector.iniのアプライアンス ディレクトリから %SystemDrive%\ProgramData\CloudConnector ディレクトリにコピーします。
  
```powershell
Import-CcConfiguration
```

## <a name="detailed-description"></a>解説
<a name="Examples"> </a>

このコマンドレットは、CloudConnector.iniコネクタ アプライアンスのアプライアンス ディレクトリから %SystemDrive%\ProgramData\CloudConnector ディレクトリにコピーします。 アプライアンス ディレクトリは、このコマンドレットを使用してSet-CcApplianceDirectoryされます。 このコマンドレットは、%SystemDrive%\ProgramData\CloudConnector 内の既存のファイルを上書きします。 このコマンドは、Cloud Connector Edition バージョン 2.0.1 以降に適用されます。
  
## <a name="parameters"></a>パラメーター
<a name="Examples"> </a>

|**パラメーター**|**Required**|**型**|**説明**|
|:-----|:-----|:-----|:-----|
|Force  <br/> |省略可  <br/> |System.Management.Automation.SwitchParameter  <br/> |通知なしで %SystemDrive%\ProgramData\CloudConnector の既存のファイルを上書きします。  <br/> |
   
## <a name="input-types"></a>入力の種類
<a name="Examples"> </a>

なし。 このImport-CcConfigurationは、パイプライン処理された入力を受け付け取らない。
  
## <a name="return-types"></a>戻り値の種類
<a name="Examples"> </a>

なし。
  
## <a name="see-also"></a>関連項目
<a name="Examples"> </a>

Export-CcConfiguration
  

