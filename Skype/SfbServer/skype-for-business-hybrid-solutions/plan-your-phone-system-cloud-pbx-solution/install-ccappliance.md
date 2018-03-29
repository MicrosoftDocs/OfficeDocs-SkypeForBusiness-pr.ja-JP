---
title: インストール CcAppliance
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 385453cd-3a96-4837-8bb4-513aa97a256b
description: Install-CcAppliance コマンドレットは、AD、中央管理ストア (CMS)、仲介サーバー、エッジ サーバー仮想マシンなどの、Skype for Business Cloud Connector エディションのアプライアンスをホスト　サーバーにインストールします。
ms.openlocfilehash: a3717e510ccadaa930d50573f067888780f7dce5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="install-ccappliance"></a>インストール CcAppliance
 
Install-CcAppliance コマンドレットは、AD、中央管理ストア (CMS)、仲介サーバー、エッジ サーバー仮想マシンなどの、Skype for Business Cloud Connector エディションのアプライアンスをホスト　サーバーにインストールします。 
  
```
Install-CcAppliance [-Steps <array>] [-SkipExistingObjects] [-Upgrade] [-UpdateAllCredentials] [<CommonParameters>]
Install-CcAppliance [-Steps <array>] [-PrepareOnly]  [<CommonParameters>]
Install-CcAppliance [-ShowStepsOnly]  [<CommonParameters>]

```

## <a name="examples"></a>例
<a name="Examples"> </a>

### <a name="example-1"></a>例 1

次の例では、ホスト サーバー上で新しいコネクタのクラウド アプライアンスがインストールされます。
  
```
Install-CcAppliance
```

### <a name="example-2"></a>例 2

次の例では、最新バージョンにクラウドのコネクタをアップグレードします。
  
```
Install-CcAppliance -Upgrade
```

### <a name="example-3"></a>例 3

次の例では、もう一度、すべての資格情報を指定するように求めるホスト サーバーにキャッシュされているすべてのクラウド コネクタの資格情報を削除し、クラウドのコネクタがインストールされます。
  
```
Install-CcAppliance -UpdateAllCredentials
```

### <a name="example-4"></a>例 4

次の例は、PowerShell コンソールでの展開のすべての手順を示します。
  
```
Install-CcAppliance -ShowStepsOnly
```

ShowStepsOnly パラメーターは、トラブルシューティングのみで使用されます。
  
### <a name="example-5"></a>例 5

次の例では、ホスト サーバーでの展開の各手順で構成ファイルを生成します。 構成ファイルに保存されます、 \<ApplianceRoot\>\Instances\\< バージョン\>のホスト サーバー上のフォルダーを default\ExportedConfig。
  
```
Install-CcAppliance -PrepareOnly
```

アプライアンスのルートを判別するには、Get-CcApplianceDirectory コマンドレットを実行します。 
  
### <a name="example-6"></a>例 6

次の例では、Cloud Connector が展開の手順 1、2、3 を実行して仮想スイッチの作成、AD 仮想マシンの作成、および AD サーバーへのドメイン サービスのインストールを行います。既に実行済みの手順はスキップされます。
  
```
Install-CcAppliance -Steps @(1,2,3) -SkipExistingObjects
```

SkipExistingObjects パラメーターは、Steps パラメーターと共に使用する必要があります。
  
> [!NOTE]
> Steps パラメーターは、トラブルシューティングのみで使用されます。 アプライアンスを展開したり、サービス中のアプライアンスをアップグレードしたりするために、このパラメーターを使用しないでください。 
  
展開の手順を判別するには、次のコマンドを実行します。
  
インストール CcAppliance ShowStepsOnly
  
## <a name="detailed-description"></a>解説
<a name="DetailedDescription"> </a>

インストール CcAppliance コマンドレットは、新しいアプライアンスにクラウドのコネクタを展開する、または既存のアプライアンスを最新バージョンにアップグレードするに使用されます。
  
新しいアプライアンスがある場合は、最初に必ず「Cloud Connector 1.4.1 の展開環境の準備」を読んでから、Register-CcAppliance コマンドレットを実行してアプライアンスを登録し、Install-CcAppliance コマンドレットを実行します。 詳細については、[クラウドのコネクタで 1 つのサイトを展開](deploy-a-single-site-in-cloud-connector.md)し、[クラウドのコネクタで複数のサイトを展開](deploy-multiple-sites-in-cloud-connector.md)を参照してください。 
  
クラウド コネクタの既存の配置があり、アップグレードする場合は、[クラウドのコネクタの新しいバージョンへのアップグレード](upgrade-to-a-new-version-of-cloud-connector.md)の指示に従ってください。
  
## <a name="parameters"></a>パラメーター
<a name="DetailedDescription"> </a>

|**パラメーター**|**必須**|**タイプ**|**説明**|
|:-----|:-----|:-----|:-----|
|PrepareOnly  <br/> |省略可能  <br/> |System.Management.Automation.SwitchParameter  <br/> | 展開の各手順について、構成ファイルを生成します。このパラメーターは、トラブルシューティングのみで使用されます。 <br/> |
|ShowStepsOnly  <br/> |省略可能  <br/> |System.Management.Automation.SwitchParameter  <br/> |展開の手順の名前のみを表示します。このパラメーターは、トラブルシューティングのみで使用されます。  <br/> |
|SkipExistingObjects  <br/> |省略可能  <br/> |System.Management.Automation.SwitchParameter  <br/> |このパラメーターは、Steps パラメーターと共に使用する必要があります。このパラメーターは、トラブルシューティングのみで使用されます。  <br/> |
|Steps  <br/> |省略可能  <br/> |System.Array  <br/> |展開の手順を実行します。このパラメーターは、トラブルシューティングのみで使用されます。  <br/> |
|Upgrade  <br/> |省略可能  <br/> |System.Management.Automation.SwitchParameter  <br/> |既存の Cloud Connector を最新バージョンに更新します。  <br/> |
|UpdateAllCredentials  <br/> |省略可能  <br/> |System.Management.Automation.SwitchParameter  <br/> |キャッシュ内には、クラウドのコネクタのすべての資格情報を削除します。 ユーザーにインストールのための新しい資格情報を指定するよう求めます。  <br/> |
   
## <a name="input-types"></a>入力の種類
<a name="InputTypes"> </a>

なし。Install-CcAppliance  コマンドレットはパイプライン入力を受け入れません。
  
## <a name="return-types"></a>戻り値の種類
<a name="ReturnTypes"> </a>

なし
  
## <a name="see-also"></a>関連項目
<a name="ReturnTypes"> </a>

[発行 CcAppliance](publish-ccappliance.md)
  
[登録 CcAppliance](register-ccappliance.md)
  
[登録解除 CcAppliance](unregister-ccappliance.md)
  
[アンインストール CcAppliance](uninstall-ccappliance.md)
  

