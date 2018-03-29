---
title: アンインストール CcAppliance
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/23/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e1b3cdd7-08e9-41a6-843a-3b4baf886cd0
description: Uninstall-CcAppliance コマンドレットは実行中の Skype for Business Cloud Connector エディションのアプライアンスをホスト サーバーからアンインストールします。
ms.openlocfilehash: 325e21d28ef87f9d27e87721452bc3d67d197169
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="uninstall-ccappliance"></a>アンインストール CcAppliance
 
Uninstall-CcAppliance コマンドレットは実行中の Skype for Business Cloud Connector エディションのアプライアンスをホスト サーバーからアンインストールします。 
  
```
Uninstall-CcAppliance [-Version <string>] [-Force] [-Confirm <bool>] [<CommonParameters>]
```

## <a name="examples"></a>例
<a name="Examples"> </a>

### <a name="example-1"></a>例 1

次の例では、回収されてしまったし、クラウド コネクタ アプライアンスをホスト サーバーからアンインストールします。
  
```
Uninstall-CcAppliance
```

### <a name="example-2"></a>例 2

次の例では、回収されてしまったし、ドレン処理が失敗した場合でも、ホスト サーバーで実行されているクラウド コネクタ アプライアンスを強制的にアンインストールします。
  
```
Uninstall-CcAppliance -Force
```

### <a name="example-3"></a>例 3

次の使用例は、ユーザーの確認なしのクラウドのコネクタのバックアップ バージョンをアンインストールします。
  
```
Uninstall-CcAppliance -Version 1.3.8 -Confirm:$false
```

## <a name="detailed-description"></a>解説
<a name="DetailedDescription"> </a>

クラウド コネクタの現在実行中のバージョンをアンインストールする場合はドレン サービス最初同時呼び出しの仮想マシンをアンインストールする前に完了させるには、仲介サーバーとエッジ サーバーで実行されます。 バックアップ バージョンをアンインストールしている場合は、ドレイン処理は実行されません。
  
## <a name="parameters"></a>パラメーター
<a name="DetailedDescription"> </a>

|**パラメーター**|**必須**|**タイプ**|**説明**|
|:-----|:-----|:-----|:-----|
| Version <br/> | 省略可能 <br/> |System.String  <br/> | ホスト サーバーからアンインストールされるクラウド コネクタのバージョンです。 指定されていない場合、現在実行中のバージョンをアンインストールします。 <br/> |
|Force  <br/> |省略可能  <br/> |System.Management.Automation.SwitchParameter  <br/> |現在の実行中バージョンをアンインストールする場合、仮想マシンをアンインストールする前に仲介サーバーとエッジ サーバーで、サーバーのドレイン処理を試みます。「Force」スイッチを指定すると、ドレイン サービスが失敗した場合でも、仮想マシンはアンインストールされます。このパラメーターは現在の実行中バージョンをアンインストールするためのみに使用されます。  <br/> |
|Confirm  <br/> |省略可能  <br/> |System.Management.Automation.SwitchParameter  <br/> |仮想マシンをアンインストールするのにはユーザーの確認を依頼してください。 既定値は TRUE です。  <br/> |
   
## <a name="input-types"></a>入力の種類
<a name="InputTypes"> </a>

なし。Uninstall-CcAppliance コマンドレットはパイプライン入力を受け入れません。
  
## <a name="return-types"></a>戻り値の種類
<a name="ReturnTypes"> </a>

なし
  
## <a name="see-also"></a>関連項目
<a name="ReturnTypes"> </a>

[インストール CcAppliance](install-ccappliance.md)
  
[発行 CcAppliance](publish-ccappliance.md)
  
[登録 CcAppliance](register-ccappliance.md)
  
[登録解除 CcAppliance](unregister-ccappliance.md)
  

