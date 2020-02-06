---
title: Uninstall-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/23/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e1b3cdd7-08e9-41a6-843a-3b4baf886cd0
description: Uninstall-CcAppliance コマンドレットは実行中の Skype for Business Cloud Connector エディションのアプライアンスをホスト サーバーからアンインストールします。
ms.openlocfilehash: c92ad5c31e2e254e4f10511835b6cc9f60c7c43c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824141"
---
# <a name="uninstall-ccappliance"></a>Uninstall-CcAppliance
 
Uninstall-CcAppliance コマンドレットは実行中の Skype for Business Cloud Connector エディションのアプライアンスをホスト サーバーからアンインストールします。 
  
```powershell
Uninstall-CcAppliance [-Version <string>] [-Force] [-Confirm <bool>] [<CommonParameters>]
```

## <a name="examples"></a>例
<a name="Examples"> </a>

### <a name="example-1"></a>例 1

次の例では、ホストサーバーからクラウドコネクタアプライアンスを処理し、アンインストールします。
  
```powershell
Uninstall-CcAppliance
```

### <a name="example-2"></a>例 2

次の例では、ドレインプロセスが失敗した場合でも、ホストサーバー上で実行されているクラウドコネクタのアプライアンスをドレインして、強制的にアンインストールします。
  
```powershell
Uninstall-CcAppliance -Force
```

### <a name="example-3"></a>例 3

次の例では、ユーザーの確認なしにクラウドコネクタのバックアップバージョンをアンインストールします。
  
```powershell
Uninstall-CcAppliance -Version 1.3.8 -Confirm:$false
```

## <a name="detailed-description"></a>解説
<a name="DetailedDescription"> </a>

現在実行されているクラウドコネクタのバージョンをアンインストールする場合、ドレインサービスは、仮想マシンをアンインストールする前に同時呼び出しが終了するように、仲介サーバーとエッジサーバー上で最初に実行されます。 バックアップ バージョンをアンインストールしている場合は、ドレイン処理は実行されません。
  
## <a name="parameters"></a>パラメーター
<a name="DetailedDescription"> </a>

|**パラメーター**|**必須**|**種類**|**説明**|
|:-----|:-----|:-----|:-----|
| Version <br/> | 省略可能 <br/> |System.String  <br/> | ホストサーバーからアンインストールされるクラウドコネクタのバージョン。 指定されていない場合、現在実行中のバージョンをアンインストールします。 <br/> |
|Force  <br/> |省略可能  <br/> |System.Management.Automation.SwitchParameter  <br/> |現在の実行中バージョンをアンインストールする場合、仮想マシンをアンインストールする前に仲介サーバーとエッジ サーバーで、サーバーのドレイン処理を試みます。「Force」スイッチを指定すると、ドレイン サービスが失敗した場合でも、仮想マシンはアンインストールされます。このパラメーターは現在の実行中バージョンをアンインストールするためのみに使用されます。  <br/> |
|Confirm  <br/> |省略可能  <br/> |System.Management.Automation.SwitchParameter  <br/> |仮想マシンをアンインストールするかどうかをユーザーに確認します。 既定値は TRUE です。  <br/> |
   
## <a name="input-types"></a>入力の種類
<a name="InputTypes"> </a>

なし。Uninstall-CcAppliance コマンドレットはパイプライン入力を受け入れません。
  
## <a name="return-types"></a>戻り値の種類
<a name="ReturnTypes"> </a>

なし
  
## <a name="see-also"></a>関連項目
<a name="ReturnTypes"> </a>

[Install-CcAppliance](install-ccappliance.md)
  
[Publish-CcAppliance](publish-ccappliance.md)
  
[Register-CcAppliance](register-ccappliance.md)
  
[Unregister-CcAppliance](unregister-ccappliance.md)
  

