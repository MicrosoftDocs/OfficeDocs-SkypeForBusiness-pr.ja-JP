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
description: このUninstall-CcApplianceコマンドレットは、実行中のSkype for Business クラウド コネクタ エディションアプライアンスをホスト サーバーからアンインストールします。
ms.openlocfilehash: f82459e71ee3c7eea88030a2f265f0076a633a280ee3182920e599402f69a96c
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54344556"
---
# <a name="uninstall-ccappliance"></a>Uninstall-CcAppliance
 
このUninstall-CcApplianceコマンドレットは、実行中のSkype for Business クラウド コネクタ エディションアプライアンスをホスト サーバーからアンインストールします。 
  
```powershell
Uninstall-CcAppliance [-Version <string>] [-Force] [-Confirm <bool>] [<CommonParameters>]
```

## <a name="examples"></a>例
<a name="Examples"> </a>

### <a name="example-1"></a>例 1

次の使用例は、ホスト サーバーからクラウド コネクタ アプライアンスをドレインおよびアンインストールします。
  
```powershell
Uninstall-CcAppliance
```

### <a name="example-2"></a>例 2

次の例では、ドレイン プロセスが失敗した場合でも、ホスト サーバーで実行中のクラウド コネクタ アプライアンスをドレインし、強制的にアンインストールします。
  
```powershell
Uninstall-CcAppliance -Force
```

### <a name="example-3"></a>例 3

次の例では、ユーザーの確認なしで Cloud Connector バックアップ バージョンをアンインストールします。
  
```powershell
Uninstall-CcAppliance -Version 1.3.8 -Confirm:$false
```

## <a name="detailed-description"></a>解説
<a name="DetailedDescription"> </a>

現在実行中のバージョンのクラウド コネクタをアンインストールする場合は、最初に仲介サーバーとエッジ サーバーでドレイン サービスを実行し、仮想マシンをアンインストールする前に同時呼び出しを終了します。 バックアップ バージョンをアンインストールする場合、ドレインは実行されません。
  
## <a name="parameters"></a>パラメーター
<a name="DetailedDescription"> </a>

|**パラメーター**|**Required**|**型**|**説明**|
|:-----|:-----|:-----|:-----|
| Version <br/> | 省略可 <br/> |System.String  <br/> | ホスト サーバーからアンインストールされるクラウド コネクタのバージョン。 指定しない場合は、現在実行中のバージョンをアンインストールします。 <br/> |
|Force  <br/> |省略可  <br/> |System.Management.Automation.SwitchParameter  <br/> |現在実行中のバージョンをアンインストールする場合は、仮想マシンをアンインストールする前に仲介サーバーとエッジ サーバー上のサーバーをドレインしてください。 "Force" スイッチを指定すると、ドレイン サービスが失敗した場合でも、仮想マシンはアンインストールされます。 このパラメーターは、現在実行中のバージョンをアンインストールする場合にのみ使用されます。  <br/> |
|確認  <br/> |省略可  <br/> |System.Management.Automation.SwitchParameter  <br/> |仮想マシンをアンインストールするユーザーの確認を求める。 既定値は TRUE です。  <br/> |
   
## <a name="input-types"></a>入力の種類
<a name="InputTypes"> </a>

なし。 このUninstall-CcApplianceは、パイプライン処理された入力を受け付け取らない。
  
## <a name="return-types"></a>戻り値の種類
<a name="ReturnTypes"> </a>

なし
  
## <a name="see-also"></a>関連項目
<a name="ReturnTypes"> </a>

[Install-CcAppliance](install-ccappliance.md)
  
[Publish-CcAppliance](publish-ccappliance.md)
  
[Register-CcAppliance](register-ccappliance.md)
  
[Unregister-CcAppliance](unregister-ccappliance.md)
  

