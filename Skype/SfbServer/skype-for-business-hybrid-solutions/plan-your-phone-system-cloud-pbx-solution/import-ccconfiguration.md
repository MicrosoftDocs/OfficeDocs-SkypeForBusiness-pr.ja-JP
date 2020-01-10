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
ms.openlocfilehash: c72a72351ecb6936832bc5d6a2493c5fa8dfe324
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003337"
---
# <a name="import-ccconfiguration"></a>Import-CcConfiguration
 
ローカルファイルからクラウドコネクタホストサーバーに Skype for Business Cloud Connector エディションの構成をインポートします。
  
```powershell
Import-CcConfiguration [-Force] [<CommonParameters>]
```

## <a name="examples"></a>例
<a name="Examples"> </a>

### <a name="example-1"></a>例 1

次の例では、クラウドコネクタインスタンスのアプライアンスディレクトリから%SystemDrive%\ProgramData\CloudConnector ディレクトリに CloudConnector. .ini をコピーします。
  
```powershell
Import-CcConfiguration
```

## <a name="detailed-description"></a>解説
<a name="Examples"> </a>

このコマンドレットは、クラウドコネクタアプライアンスのアプライアンスディレクトリから%SystemDrive%\ProgramData\CloudConnector ディレクトリに CloudConnector. .ini をコピーします。 アプライアンス ディレクトリは Set-CcApplianceDirectory コマンドレットを使用して指定されます。 このコマンドレットによって、%SystemDrive%\ProgramData\CloudConnector. 内の既存のファイルが上書きされます。 このコマンドは、Cloud Connector エディションバージョン2.0.1 以降に適用されます。
  
## <a name="parameters"></a>パラメーター
<a name="Examples"> </a>

|**パラメーター**|**必須**|**種類**|**説明**|
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
  

