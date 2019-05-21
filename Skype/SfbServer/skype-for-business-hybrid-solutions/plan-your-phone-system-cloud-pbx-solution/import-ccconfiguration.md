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
localization_priority: Normal
ms.assetid: 461361a0-9aa9-469d-ace0-dc70b95cd4a3
description: ローカルファイルからクラウドコネクタホストサーバーに Skype for Business Cloud Connector エディションの構成をインポートします。
ms.openlocfilehash: 3e165250b5158513aa683770d5eb1768c0e1e29c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287280"
---
# <a name="import-ccconfiguration"></a>Import-CcConfiguration
 
ローカルファイルからクラウドコネクタホストサーバーに Skype for Business Cloud Connector エディションの構成をインポートします。
  
```
Import-CcConfiguration [-Force] [<CommonParameters>]
```

## <a name="examples"></a>例
<a name="Examples"> </a>

### <a name="example-1"></a>例 1

次の例では、クラウドコネクタインスタンスのアプライアンスディレクトリから%SystemDrive%\ProgramData\CloudConnector ディレクトリに CloudConnector. .ini をコピーします。
  
```
Import-CcConfiguration
```

## <a name="detailed-description"></a>解説
<a name="Examples"> </a>

このコマンドレットは、クラウドコネクタアプライアンスのアプライアンスディレクトリから%SystemDrive%\ProgramData\CloudConnector ディレクトリに CloudConnector. .ini をコピーします。 アプライアンス ディレクトリは Set-CcApplianceDirectory コマンドレットを使用して指定されます。 このコマンドレットによって、%SystemDrive%\ProgramData\CloudConnector. 内の既存のファイルが上書きされます。 このコマンドは、Cloud Connector エディションバージョン2.0.1 以降に適用されます。
  
## <a name="parameters"></a>パラメーター
<a name="Examples"> </a>

|**パラメーター**|**必須**|**型**|**説明**|
|:-----|:-----|:-----|:-----|
|Force  <br/> |省略可能  <br/> |System.Management.Automation.SwitchParameter  <br/> |%SystemDrive%\ProgramData\CloudConnector 内の既存のファイルを通知なしで上書きします。  <br/> |
   
## <a name="input-types"></a>入力の種類
<a name="Examples"> </a>

なし。 インポート-CcConfiguration コマンドレットはパイプライン入力を受け取りません。
  
## <a name="return-types"></a>戻り値の種類
<a name="Examples"> </a>

なし。
  
## <a name="see-also"></a>関連項目
<a name="Examples"> </a>

Export-CcConfiguration
  

