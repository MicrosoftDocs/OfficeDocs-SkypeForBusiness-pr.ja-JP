---
title: Skype for Business Server 2015 での集中ログ サービスのシナリオの構成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 6c3bf826-e7fd-4002-95dc-01020641ef01
description: '概要: Skype for Business Server 2015 の中央集中ログサービスのシナリオを作成、変更、削除する方法について説明します。'
ms.openlocfilehash: b7cfcbc85df7d66374d2bf33d572b9e91b30edde
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816596"
---
# <a name="configure-scenarios-for-the-centralized-logging-service-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 での集中ログ サービスのシナリオの構成
 
**概要:** Skype for Business Server 2015 の中央集中ログサービスのシナリオを作成、変更、削除する方法について説明します。
  
シナリオでは、スコープ (つまり、グローバル、サイト、プール、またはコンピューター) と、一元管理サービスで使用するプロバイダーを定義します。 シナリオを使用して、プロバイダー (S4、SIPStack、IM、プレゼンスなど) のトレースを有効または無効にします。 シナリオを構成することで、特定の問題の条件に対応する特定の論理コレクションのすべてのプロバイダーをグループ化できます。 トラブルシューティングとログのニーズに合わせてシナリオを変更する必要があることがわかった場合は、Skype for Business Server 2015 デバッグツールでは、ClsScenarioEdit という名前の Windows PowerShell モジュールが提供されます。これには、dlmigrationmodule.psm1 という名前の namedEdit が含まれています。 このモジュールの目的は、指定したシナリオのプロパティを編集することです。 このトピックでは、このモジュールの使用方法の例を示します。 さらに先に進む前に、Skype for Business Server 2015[デバッグツール](https://go.microsoft.com/fwlink/p/?LinkId=285257)をダウンロードしてください。
  
> [!IMPORTANT]
> どのスコープ (サイト、グローバル、プール、またはコンピューター) でも、一度に最大で 2 つのシナリオを実行できます。 現在実行されているシナリオを特定するには、Windows PowerShell と[Get CsClsScenario シナリオ](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps)を使用します。 Windows PowerShell と[Set-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/set-csclsscenario?view=skype-ps)を使用すると、実行されているシナリオを動的に変更することができます。 ログ セッション中に実行するシナリオを変更して、収集するデータや収集元のプロバイダーを変更または微調整することができます。 
  
Skype for Business Server 管理シェルを使用して一元的なログサービス機能を実行するには、CsAdministrator または CsServerAdministrator の役割ベースのアクセス制御 (RBAC) セキュリティグループのメンバーであるか、または、次の2つのグループのいずれかが含まれます。 自分で作成したすべての RBAC ロールの一覧を返すには、Skype for Business Server 管理シェルまたは Windows PowerShell のプロンプトから次のコマンドを実行します。次のコマンドを実行します。
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

次に例を示します。
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

このトピックの以降の部分では、トラブルシューティングを最適化するためのシナリオの定義、シナリオの変更、実行中のシナリオの取得、シナリオの削除、シナリオ内容の指定の方法を中心に説明します。 Skype for Business Server 管理シェルを使用して、Windows PowerShell コマンドを発行することができます。 Windows PowerShell を使用する場合は、ログセッションで使用する新しいシナリオを定義できます。
  
[Skype For business 2015 の中央集中ログサービス](centralized-logging-service.md)で導入されたように、シナリオの要素は次のとおりです。
  
- **Providers**OCSLogger に精通している場合、プロバイダーは、トレースエンジンがログを収集する必要があることを OCSLogger に伝えるために選ぶコンポーネントです。 プロバイダーは同じコンポーネントであり、多くの場合、OCSLogger のコンポーネントと同じ名前が付いています。 OCSLogger に精通していない場合は、中央のログサービスがログを収集できるサーバーの役割固有のコンポーネントはプロバイダーです。 プロバイダーの構成の詳細については、「 [Skype For Business Server 2015 で中央集中ログサービスのプロバイダーを構成する](configure-providers.md)」を参照してください。
    
- **Id**パラメーター-Identity は、シナリオのスコープと名前を設定します。 たとえば、"グローバル" のスコープを設定し、"LyssServiceScenario" を使ってシナリオを特定することができます。 この2つを組み合わせると、Id (たとえば、"global/LyssServiceScenario") が定義されます。
    
    必要に応じて、-Name と-Parent パラメーターを使うことができます。 Name パラメーターは、シナリオを一意に識別するために定義します。 Name を使用する場合は、Parent も使用して、グローバルまたはサイトにシナリオを追加する必要があります。 
    
    > [!IMPORTANT]
    > Name パラメーターと Parent パラメーターを使用する場合は、 **-Identity**パラメーターを使うことはできません。
  
### <a name="to-create-a-new-scenario-with-the-new-csclsscenario-cmdlet"></a>New-CsClsScenario コマンドレットを使用して新しいシナリオを作成するには

1. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。
    
2. ログ セッションのための新しいシナリオを作成するには、[New-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/new-csclsprovider?view=skype-ps) を使用し、シナリオの名前 (シナリオを一意に識別する方法) を定義します。ログ形式の種類を、WPP (Windows ソフトウェア トレース プリプロセッサ。これが既定値です)、EventLog (Windows イベント ログ形式)、または IISLog (IIS ログ ファイル形式に基づく ASCII 形式ファイル) から選択します。次に、レベル (このトピックのログ レベルの説明で定義されています) とフラグ (このトピックのフラグの説明で定義されています) を定義します。
    
    このシナリオ例では、プロバイダー変数の例として LyssProvider を使用します。
    
    定義されたオプションを使用してシナリオを作成するには、次のように入力します。
    
   ```PowerShell
   New-CsClsScenario -Identity <scope>/<unique scenario name> -Provider <provider variable>
   ```

    次に例を示します。
    
   ```PowerShell
   New-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider $LyssProvider
   ```

    -Name と-Parent を使った代替形式:
    
   ```PowerShell
   New-CsClsScenario -Name "LyssServiceScenario" -Parent "site:Redmond" -Provider $LyssProvider
   ```

### <a name="to-create-a-new-scenario-with-multiple-providers-with-the-new-csclsscenario-cmdlet"></a>複数のプロバイダーを指定した新しいシナリオを New-CsClsScenario コマンドレットを使用して作成するには

1. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。
    
2. スコープごとのシナリオ数は 2 つまでに制限されています。 しかし、設定するプロバイダーの数に制限はありません。 この例では、3 つのプロバイダーを作成済みで、定義するシナリオに 3 つのプロバイダーをすべて割り当てる必要があるとします。 プロバイダー変数の名前は LyssProvider、ABServerProvider、および SIPStackProvider です。 1つのシナリオに複数のプロバイダーを定義して割り当てるには、Skype for Business Server 管理シェルまたは Windows PowerShell コマンドプロンプトで次のように入力します。
    
   ```PowerShell
   New-CsClsScenario -Identity "site:Redmond/CollectDataScenario" -Provider @{Add=$LyssProvider, $ABServerProvider,  $SIPStackProvider}
   ```

    > [!NOTE]
    > Windows PowerShell でわかっているように、using `@{<variable>=<value1>, <value2>, <value>…}`という値のハッシュテーブルを作成するための規則は既知の assplatting です。 Windows PowerShell での splatting の詳細につい[https://go.microsoft.com/fwlink/p/?LinkId=267760](https://go.microsoft.com/fwlink/p/?LinkId=267760)ては、を参照してください。 
  
### <a name="to-modify-an-existing-scenario-with-the-set-csclsscenario-cmdlet"></a>Set-CsClsScenario コマンドレットを使用して既存のシナリオを変更するには

1. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。
    
2. スコープごとのシナリオ数は 2 つまでに制限されています。 実行するシナリオは、ログ キャプチャ セッションの実行中を含め、いつでも変更できます。 実行するシナリオを再定義すると、現在のログ セッションは削除されたシナリオの使用を停止し、新しいシナリオの使用を開始します。 ただし、削除されたシナリオでキャプチャされたログ情報はキャプチャされたログに残ります。 新しいシナリオを定義するには、次の操作を行います (つまり、"S4Provider" という名前の定義済みプロバイダーが追加されていることを前提としています)。
    
   ```PowerShell
   Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Add=<new provider to add>}
   ```

    次に例を示します。
    
   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Add=$S4Provider}
   ```

    プロバイダーを置き換える場合は、現在のセットと置き換える単一のプロバイダーか、プロバイダーのコンマ区切りリストを定義します。多数のプロバイダーのうち 1 つだけを置き換える場合は、現在のプロバイダーに新しいプロバイダーを追加して、新しいプロバイダーと既存のプロバイダーの両方を含む新しいプロバイダーのセットを作成します。すべてのプロバイダーを新しいセットで置き換える場合は、次のように入力します。
    
   ```PowerShell
   Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Replace=<providers to replace existing provider set>}
   ```

    たとえば、現在の $LyssProvider、$ABServerProvider、および $SIPStackProvider のセットを $LyssServiceProvider に置き換えるには、次のように入力します。
    
   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider}
   ```

    現在の $LyssProvider、$ABServerProvider、および $SIPStackProvider のセットのうち、$LyssProvider プロバイダーだけを $LyssServiceProvider に置き換えるには、次のように入力します。
    
   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider, $ABServerProvider, $SIPStackProvider}
   ```

### <a name="to-remove-an-existing-scenario-with-the-remove-csclsscenario-cmdlet"></a>Remove-CsClsScenario コマンドレットを使用して既存のシナリオを削除するには

1. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。
    
2. 定義済みのシナリオを削除する場合は、次のように入力します。
    
   ```PowerShell
   Remove-CsClsScenario -Identity <name of scope and scenario>
   ```

    たとえば、定義済みのシナリオ site:Redmond/LyssServiceScenario を削除するには、次のようにします。
    
   ```PowerShell
   Remove-CsClsScenario -Identity "site:Redmond/LyssServiceScenario"
   ```

**Remove-CsClsScenario** コマンドレットでは指定したシナリオが削除されますが、キャプチャ済みのトレースはログに残り、検索に利用できます。
### <a name="to-load-and-unload-the-edit-csclsscenario-cmdlet-using-the-clsscenarioeditpsm1-module"></a>ClsScenarioEdit.psm1 モジュールを使用して Edit-CsClsScenario コマンドレットをロードおよびアンロードするには

1. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。
    
    > [!IMPORTANT]
    > ClsScenarioEdit.psm1 モジュールは個別の Web ダウンロードとして提供されます。 このモジュールは、Skype for Business Server 2015 デバッグツールの一部です。 既定では、デバッグ ツールは C:\Program Files\Skype for Business Server 2015\Debugging Tools ディレクトリにインストールされます。 
  
2. Windows PowerShell で次のように入力します。
    
   ```PowerShell
   Import-Module "CDBurn\OCO\amd64\Support"
   ```

    > [!TIP]
    > モジュールの読み込みが成功すると、Windows PowerShell コマンドプロンプトに戻ります。 モジュールが読み込まれていること、および編集-CsClsScenario が利用可能`Get-Help Edit-CsClsScenario`であることを確認するには、「」と入力します。 すると、EditCsClsScenario の構文の基本的な概要が表示されます。 
  
3. モジュールをアンロードするには、次のように入力します。
    
   ```PowerShell
   Remove-Module ClsController
   ```

    > [!TIP]
    > モジュールを正常にアンロードすると、Windows PowerShell コマンドプロンプトに戻ります。 モジュールがアンロードされたことを確認`Get-Help Edit-CsClsScenario`するには、「」と入力します。 Windows PowerShell は、コマンドレットのヘルプを検索して失敗します。 
  
### <a name="to-remove-an-existing-provider-from-a-scenario-with-the-edit-clscontroller-module"></a>Edit-ClsController モジュールを使用してシナリオから既存のプロバイダーを削除するには

1. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。
    
2. Windows PowerShell で次のように入力します。
    
   ```PowerShell
   Import-Module "CDBurn\OCO\amd64\Support"
   ```

    > [!TIP]
    > モジュールの読み込みが成功すると、Windows PowerShell コマンドプロンプトに戻ります。 モジュールが読み込まれていること、および編集-CsClsScenario が利用可能`Get-Help Edit-CsClsScenario`であることを確認するには、「」と入力します。 すると、EditCsClsScenario の構文の基本的な概要が表示されます。 
  
3. AlwaysOn シナリオからプロバイダーを削除するには、次のように入力します。
    
   ```PowerShell
   Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to remove> -Remove
   ```

   次に例を示します。
    
   ```PowerShell
   Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Remove
   ```

   パラメーター ScenarioName および ProviderName は、位置指定 (コマンド ライン内の指定された位置に定義する必要がある) パラメーターです。コマンドレット名を位置 1 として、シナリオ名が位置 2、プロバイダーが位置 3 にある場合は、パラメーター名を明示的に定義する必要はありません。この情報を使用すると、上記のコマンドは次のように入力できます。
    
   ```PowerShell
   Edit-CsClsScenario AlwaysOn ChatServer -Remove
   ```

   パラメーター値の位置の配置は、シナリオとプロバイダーにのみ適用されます。 他のすべてのパラメーターは明示的に定義する必要があります。
    
### <a name="to-add-a-provider-to-a-scenario-with-the-edit-clscontroller-module"></a>Edit-ClsController モジュールを使用してシナリオにプロバイダーを追加するには

1. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。
    
2. AlwaysOn シナリオにプロバイダーを追加するには、次のように入力します。
    
   ```PowerShell
   Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to add> -Level <string of type level> -Flags <string of type flags>
   ```

    次に例を示します。
    
   ```PowerShell
   Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Level Info -Flags TF_COMPONENT
   ```

    -Loglevel には、Fatal、Error、Warning、Info、Verbose、Debug、または All を指定できます。 -フラグは、プロバイダーがサポートしている任意のフラグ (TF_COMPONENT、TF_DIAG など) にすることができます。 -フラグはすべての値にすることもできます。
    
   上記の例を、コマンドレットの位置指定機能を使用して入力することもできます。たとえば、プロバイダー ChatServer を AlwaysOn シナリオに追加するには、次のように入力します。
    
   ```PowerShell
   Edit-CsClsScenario AlwaysOn ChatServer -Level Info -Flags ALL
   ```
