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
ms.localizationpriority: medium
ms.assetid: 461361a0-9aa9-469d-ace0-dc70b95cd4a3
description: ローカル ファイルからSkype for Business クラウド コネクタ エディション構成を Cloud Connector ホスト サーバーにインポートします。
ms.openlocfilehash: efcc73fd5883c61753688923d44c01e10fc74ea8
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58623405"
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

|**パラメーター**|**Required**|**Type**|**説明**|
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
  

