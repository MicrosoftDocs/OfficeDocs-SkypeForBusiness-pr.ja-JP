---
title: Install-CcAppliance
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
ms.assetid: 385453cd-3a96-4837-8bb4-513aa97a256b
description: Install-CcApplianceコマンドレットは、Skype for Business クラウド コネクタ エディション アプライアンス (AD、中央管理ストア、仲介サーバー、エッジ サーバーの仮想マシンを含む) をホスト サーバーにインストールします。
ms.openlocfilehash: b88b869e3c30783a69bc16ab690a258506ebcc90e849eb474a17859140485e8d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54343181"
---
# <a name="install-ccappliance"></a>Install-CcAppliance
 
Install-CcApplianceコマンドレットは、Skype for Business クラウド コネクタ エディション アプライアンス (AD、中央管理ストア、仲介サーバー、エッジ サーバーの仮想マシンを含む) をホスト サーバーにインストールします。 
  
```powershell
Install-CcAppliance [-Steps <array>] [-SkipExistingObjects] [-Upgrade] [-UpdateAllCredentials] [<CommonParameters>]
Install-CcAppliance [-Steps <array>] [-PrepareOnly]  [<CommonParameters>]
Install-CcAppliance [-ShowStepsOnly]  [<CommonParameters>]
```

## <a name="examples"></a>例
<a name="Examples"> </a>

### <a name="example-1"></a>例 1

次の使用例は、ホスト サーバーに新しいクラウド コネクタ アプライアンスをインストールします。
  
```powershell
Install-CcAppliance
```

### <a name="example-2"></a>例 2

次の例では、クラウド コネクタを最新バージョンにアップグレードします。
  
```powershell
Install-CcAppliance -Upgrade
```

### <a name="example-3"></a>例 3

次の使用例は、ホスト サーバーにキャッシュされているクラウド コネクタ資格情報を削除し、すべての資格情報を再度指定するようにユーザーに求め、クラウド コネクタをインストールします。
  
```powershell
Install-CcAppliance -UpdateAllCredentials
```

### <a name="example-4"></a>例 4

次の例では、PowerShell コンソールのすべての展開手順を表示します。
  
```powershell
Install-CcAppliance -ShowStepsOnly
```

-ShowStepsOnly パラメーターは、トラブルシューティング専用です。
  
### <a name="example-5"></a>例 5

次の使用例は、ホスト サーバー上の展開手順ごとに構成ファイルを生成します。 構成ファイルは、ホスト サーバーの \<ApplianceRoot\> \Instances \\<\> バージョン -default\ExportedConfig フォルダーに保存されます。
  
```powershell
Install-CcAppliance -PrepareOnly
```

アプライアンスのルートを確認するには、次のコマンドレットGet-CcApplianceDirectoryします。 
  
### <a name="example-6"></a>例 6

次の例では、Cloud Connector は展開手順 1、2、3 を実行して仮想スイッチを作成し、AD 仮想マシンを作成し、AD サーバーにドメイン サービスをインストールします。 手順が既に実行されている場合は、手順をスキップします。
  
```powershell
Install-CcAppliance -Steps @(1,2,3) -SkipExistingObjects
```

SkipExistingObjects パラメーターは、Steps パラメーターと組み合わせて使用する必要があります。
  
> [!NOTE]
> Steps パラメーターは、トラブルシューティングのみを目的とします。 このパラメーターを使用して、アプライアンスを展開したり、サービス中のアプライアンスをアップグレードしたりすることはできません。 
  
展開の手順を確認するには、次のコマンドを実行します。
  
Install-CcAppliance -ShowStepsOnly
  
## <a name="detailed-description"></a>解説
<a name="DetailedDescription"> </a>

このInstall-CcApplianceは、クラウド コネクタを新しいアプライアンスに展開したり、既存のアプライアンスを最新バージョンにアップグレードしたりするために使用されます。
  
新しいアプライアンスがある場合は、「まずクラウド コネクタの環境を準備する」を参照し、Register-CcAppliance コマンドレットを実行してアプライアンスを登録し、Install-CcAppliance コマンドレットを実行します。 詳細については、「単一サイト [をクラウド コネクタに展開](deploy-a-single-site-in-cloud-connector.md) する」および「Cloud Connector で複数のサイトを展開する」 [を参照してください](deploy-multiple-sites-in-cloud-connector.md)。 
  
クラウド コネクタを既存の展開でアップグレードする場合は、「新しいバージョンのクラウド コネクタにアップグレードする」の手順に [従ってください](upgrade-to-a-new-version-of-cloud-connector.md)。
  
## <a name="parameters"></a>パラメーター
<a name="DetailedDescription"> </a>

|**パラメーター**|**Required**|**型**|**説明**|
|:-----|:-----|:-----|:-----|
|PrepareOnly  <br/> |省略可  <br/> |System.Management.Automation.SwitchParameter  <br/> | 展開手順ごとに構成ファイルを生成します。 このパラメーターは、トラブルシューティング専用です。 <br/> |
|ShowStepsOnly  <br/> |省略可  <br/> |System.Management.Automation.SwitchParameter  <br/> |展開手順名のみを表示します。 このパラメーターは、トラブルシューティング専用です。  <br/> |
|SkipExistingObjects  <br/> |省略可  <br/> |System.Management.Automation.SwitchParameter  <br/> |このパラメーターは、Steps パラメーターと組み合わせて使用する必要があります。 このパラメーターは、トラブルシューティング専用です。  <br/> |
|手順  <br/> |省略可能  <br/> |System.Array  <br/> |展開手順を実行します。 このパラメーターは、トラブルシューティング専用です。  <br/> |
|アップグレード  <br/> |省略可  <br/> |System.Management.Automation.SwitchParameter  <br/> |既存のクラウド コネクタを最新バージョンにアップグレードします。  <br/> |
|UpdateAllCredentials  <br/> |省略可  <br/> |System.Management.Automation.SwitchParameter  <br/> |キャッシュ内のすべてのクラウド コネクタ資格情報を削除します。 インストールの新しい資格情報を指定するようにユーザーに求めるメッセージを表示します。  <br/> |
   
## <a name="input-types"></a>入力の種類
<a name="InputTypes"> </a>

なし。 このInstall-CcApplianceは、パイプライン処理された入力を受け付け取らない。
  
## <a name="return-types"></a>戻り値の種類
<a name="ReturnTypes"> </a>

なし
  
## <a name="see-also"></a>関連項目
<a name="ReturnTypes"> </a>

[Publish-CcAppliance](publish-ccappliance.md)
  
[Register-CcAppliance](register-ccappliance.md)
  
[Unregister-CcAppliance](unregister-ccappliance.md)
  
[Uninstall-CcAppliance](uninstall-ccappliance.md)
  

