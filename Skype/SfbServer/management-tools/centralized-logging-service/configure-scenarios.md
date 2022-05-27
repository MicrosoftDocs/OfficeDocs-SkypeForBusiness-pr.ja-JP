---
title: Skype for Business Server 2015 で集中ログ サービスのシナリオを構成する
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 6c3bf826-e7fd-4002-95dc-01020641ef01
description: '概要: Skype for Business Server 2015 の集中ログ サービスのシナリオを作成、変更、および削除する方法について説明します。'
ms.openlocfilehash: ecd96dc849030cb035f965c8cb52eb7607bd9667
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676359"
---
# <a name="configure-scenarios-for-the-centralized-logging-service-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 で集中ログ サービスのシナリオを構成する

**概要：** Skype for Business Server 2015 の集中ログ サービスのシナリオを作成、変更、削除する方法について説明します。

シナリオでは、スコープ (つまり、グローバル、サイト、プール、またはコンピューター) と、集中ログ サービスで使用するプロバイダーを定義します。 シナリオを使用して、プロバイダー (S4、SIPStack、IM、プレゼンスなど) のトレースを有効または無効にします。 シナリオを構成することで、特定の問題の条件に対応する特定の論理コレクションのすべてのプロバイダーをグループ化できます。 トラブルシューティングとログ記録のニーズを満たすためにシナリオを変更する必要がある場合、Skype for Business Server 2015 Debug Tools には、Edit-CsClsScenario という名前の関数を含む ClsScenarioEdit.psm1 という名前のWindows PowerShell モジュールが用意されています。 このモジュールの目的は、指定したシナリオのプロパティを編集することです。 このトピックでは、このモジュールの使用方法の例を示します。 さらに進む前に、Skype for Business Server 2015 [デバッグ ツールを](https://go.microsoft.com/fwlink/p/?LinkId=285257)ダウンロードしてください。

> [!IMPORTANT]
> どのスコープ (サイト、グローバル、プール、またはコンピューター) でも、一度に最大で 2 つのシナリオを実行できます。 現在実行されているシナリオを確認するには、Windows PowerShellと [Get-CsClsScenario](/powershell/module/skype/get-csclsscenario) を使用します。 Windows PowerShellと [Set-CsClsScenario](/powershell/module/skype/set-csclsscenario) を使用すると、実行されているシナリオを動的に変更できます。 ログ セッション中に実行するシナリオを変更して、収集するデータや収集元のプロバイダーを変更または微調整することができます。

Skype for Business Server管理シェルを使用して集中ログ サービス機能を実行するには、CsAdministrator または CsServerAdministrator ロールベースのアクセス制御 (RBAC) セキュリティ グループ、またはこれら 2 つのグループのいずれかを含むカスタム RBAC ロールのメンバーである必要があります。 自分で作成したすべてのカスタム RBAC ロールを含め、このコマンドレットが割り当てられているすべての RBAC ロールの一覧を返すには、Skype for Business Server管理シェルまたはWindows PowerShell プロンプトから次のコマンドを実行します。

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

次に例を示します。

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

このトピックの残りの部分では、シナリオの定義、シナリオの変更、実行されているシナリオの取得、シナリオの削除、トラブルシューティングを最適化するためのシナリオの内容の指定方法について説明します。 Skype for Business Server管理シェルを使用して、Windows PowerShell コマンドを発行できます。 Windows PowerShellを使用する場合は、ログ セッションで使用する新しいシナリオを定義できます。

[Skype for Business 2015 の一元化されたログ サービスで](centralized-logging-service.md)導入されているように、シナリオの要素は次のとおりです。

- **プロバイダー** OCSLogger に精通している場合、プロバイダーは、トレース エンジンがログを収集する対象を OCSLogger に指示するコンポーネントです。 プロバイダーは同じコンポーネントであり、多くの場合、OCSLogger のコンポーネントと同じ名前を持ちます。 OCSLogger に慣れていない場合、プロバイダーは、集中ログ サービスがログを収集できるサーバー ロール固有のコンポーネントです。 プロバイダーの構成の詳細については、[Skype for Business Server 2015 の集中ログ サービスのプロバイダーの構成](configure-providers.md)に関するページを参照してください。

- **Id** パラメーター -Identity は、シナリオのスコープと名前を設定します。 たとえば、"global" のスコープを設定し、"LyssServiceScenario" でシナリオを特定できます。 2 つを組み合わせる場合は、IDENTITY を定義します (たとえば、"global/LyssServiceScenario")。

    必要に応じて、-Name パラメーターと -Parent パラメーターを使用できます。 Name パラメーターは、シナリオを一意に識別するために定義します。 Name を使用する場合は、Parent も使用して、グローバルまたはサイトにシナリオを追加する必要があります。

    > [!IMPORTANT]
    > Name パラメーターと Parent パラメーターを使用する場合は、 **-Identity** パラメーターを使用できません。

## <a name="to-create-a-new-scenario-with-the-new-csclsscenario-cmdlet"></a>New-CsClsScenario コマンドレットを使用して新しいシナリオを作成するには

1. Skype for Business Server管理シェルを起動します。 **[スタート]** をクリックし、[**すべてのプログラム**] をクリック **し、[Skype for Business 2015**] をクリックして、[**管理シェルSkype for Business Server**] をクリックします。

2. ログ セッションのための新しいシナリオを作成するには、[New-CsClsProvider](/powershell/module/skype/new-csclsprovider) を使用し、シナリオの名前 (シナリオを一意に識別する方法) を定義します。ログ形式の種類を、WPP (Windows ソフトウェア トレース プリプロセッサ。これが既定値です)、EventLog (Windows イベント ログ形式)、または IISLog (IIS ログ ファイル形式に基づく ASCII 形式ファイル) から選択します。次に、レベル (このトピックのログ レベルの説明で定義されています) とフラグ (このトピックのフラグの説明で定義されています) を定義します。

    このシナリオ例では、プロバイダー変数の例として LyssProvider を使用します。

    定義されたオプションを使用してシナリオを作成するには、次のように入力します。

   ```PowerShell
   New-CsClsScenario -Identity <scope>/<unique scenario name> -Provider <provider variable>
   ```

    次に例を示します。

   ```PowerShell
   New-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider $LyssProvider
   ```

    名前と -Parent を使用する代替形式:

   ```PowerShell
   New-CsClsScenario -Name "LyssServiceScenario" -Parent "site:Redmond" -Provider $LyssProvider
   ```

## <a name="to-create-a-new-scenario-with-multiple-providers-with-the-new-csclsscenario-cmdlet"></a>複数のプロバイダーを指定した新しいシナリオを New-CsClsScenario コマンドレットを使用して作成するには

1. Skype for Business Server管理シェルを起動します。 **[スタート]** をクリックし、[**すべてのプログラム**] をクリック **し、[Skype for Business 2015**] をクリックして、[**管理シェルSkype for Business Server**] をクリックします。

2. スコープごとのシナリオ数は 2 つまでに制限されています。 しかし、設定するプロバイダーの数に制限はありません。 この例では、3 つのプロバイダーを作成済みで、定義するシナリオに 3 つのプロバイダーをすべて割り当てる必要があるとします。 プロバイダー変数の名前は LyssProvider、ABServerProvider、および SIPStackProvider です。 シナリオに複数のプロバイダーを定義して割り当てるには、Skype for Business Server Management Shell または Windows PowerShell コマンド プロンプトで次のように入力します。

   ```PowerShell
   New-CsClsScenario -Identity "site:Redmond/CollectDataScenario" -Provider @{Add=$LyssProvider, $ABServerProvider,  $SIPStackProvider}
   ```

    > [!NOTE]
    > Windows PowerShellで知られているように、値`@{<variable>=<value1>, <value2>, <value>...}`のハッシュ テーブルを作成するための規則は、assplatting と呼ばれます。 Windows PowerShellでのスプラティングの詳細については、次を参照してください[https://go.microsoft.com/fwlink/p/?LinkId=267760](/previous-versions/technet-magazine/gg675931(v=msdn.10))。

## <a name="to-modify-an-existing-scenario-with-the-set-csclsscenario-cmdlet"></a>Set-CsClsScenario コマンドレットを使用して既存のシナリオを変更するには

1. Skype for Business Server管理シェルを起動します。 **[スタート]** をクリックし、[**すべてのプログラム**] をクリック **し、[Skype for Business 2015**] をクリックして、[**管理シェルSkype for Business Server**] をクリックします。

2. スコープごとのシナリオ数は 2 つまでに制限されています。 実行するシナリオは、ログ キャプチャ セッションの実行中を含め、いつでも変更できます。 実行するシナリオを再定義すると、現在のログ セッションは削除されたシナリオの使用を停止し、新しいシナリオの使用を開始します。 ただし、削除されたシナリオでキャプチャされたログ情報はキャプチャされたログに残ります。 新しいシナリオを定義するには、次の手順を実行します (つまり、"S4Provider" という名前の既に定義されているプロバイダーが追加されていると仮定します)。

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

## <a name="to-remove-an-existing-scenario-with-the-remove-csclsscenario-cmdlet"></a>Remove-CsClsScenario コマンドレットを使用して既存のシナリオを削除するには

1. Skype for Business Server管理シェルを起動します。 **[スタート]** をクリックし、[**すべてのプログラム**] をクリック **し、[Skype for Business 2015**] をクリックして、[**管理シェルSkype for Business Server**] をクリックします。

2. 定義済みのシナリオを削除する場合は、次のように入力します。

   ```PowerShell
   Remove-CsClsScenario -Identity <name of scope and scenario>
   ```

    たとえば、定義済みのシナリオ site:Redmond/LyssServiceScenario を削除するには、次のようにします。

   ```PowerShell
   Remove-CsClsScenario -Identity "site:Redmond/LyssServiceScenario"
   ```

**Remove-CsClsScenario** コマンドレットでは指定したシナリオが削除されますが、キャプチャ済みのトレースはログに残り、検索に利用できます。

## <a name="to-load-and-unload-the-edit-csclsscenario-cmdlet-using-the-clsscenarioeditpsm1-module"></a>ClsScenarioEdit.psm1 モジュールを使用してEdit-CsClsScenario コマンドレットを読み込んでアンロードするには

1. Skype for Business Server管理シェルを起動します。 **[スタート]** をクリックし、[**すべてのプログラム**] をクリック **し、[Skype for Business 2015**] をクリックして、[**管理シェルSkype for Business Server**] をクリックします。

    > [!IMPORTANT]
    > ClsScenarioEdit.psm1 モジュールは、個別の Web ダウンロードとして提供されます。 このモジュールは、Skype for Business Server 2015 デバッグ ツールの一部です。 既定では、デバッグ ツールはディレクトリ C:\Program Files\Skype for Business Server 2015\Debugging Tools にインストールされます。

2. Windows PowerShellから、次のように入力します。

   ```PowerShell
   Import-Module "CDBurn\OCO\amd64\Support"
   ```

    > [!TIP]
    > モジュールの読み込みに成功すると、Windows PowerShell コマンド プロンプトに戻ります。 モジュールが読み込まれ、Edit-CsClsScenarioが使用可能であることを確認するには、「.」と入力します  `Get-Help Edit-CsClsScenario`。 すると、EditCsClsScenario の構文の基本的な概要が表示されます。

3. モジュールをアンロードするには、次のように入力します。

   ```PowerShell
   Remove-Module ClsController
   ```

    > [!TIP]
    > モジュールのアンロードに成功すると、Windows PowerShell コマンド プロンプトに戻ります。 モジュールがアンロードされていることを確認するには、「.」と入力します  `Get-Help Edit-CsClsScenario`。 Windows PowerShellコマンドレットのヘルプの検索が試行され、失敗します。

## <a name="to-remove-an-existing-provider-from-a-scenario-with-the-edit-clscontroller-module"></a>Edit-ClsController モジュールを使用してシナリオから既存のプロバイダーを削除するには

1. Skype for Business Server管理シェルを起動します。 **[スタート]** をクリックし、[**すべてのプログラム**] をクリック **し、[Skype for Business 2015**] をクリックして、[**管理シェルSkype for Business Server**] をクリックします。

2. Windows PowerShellから、次のように入力します。

   ```PowerShell
   Import-Module "CDBurn\OCO\amd64\Support"
   ```

    > [!TIP]
    > モジュールの読み込みに成功すると、Windows PowerShell コマンド プロンプトに戻ります。 モジュールが読み込まれ、Edit-CsClsScenarioが使用可能であることを確認するには、「.」と入力します  `Get-Help Edit-CsClsScenario`。 すると、EditCsClsScenario の構文の基本的な概要が表示されます。

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

   パラメーター値の位置指定は、-Scenario と -Provider にのみ適用されます。 他のすべてのパラメーターは明示的に定義する必要があります。

## <a name="to-add-a-provider-to-a-scenario-with-the-edit-clscontroller-module"></a>Edit-ClsController モジュールを使用してシナリオにプロバイダーを追加するには

1. Skype for Business Server管理シェルを起動します。 **[スタート]** をクリックし、[**すべてのプログラム**] をクリック **し、[Skype for Business 2015**] をクリックして、[**管理シェルSkype for Business Server**] をクリックします。

2. AlwaysOn シナリオにプロバイダーを追加するには、次のように入力します。

   ```PowerShell
   Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to add> -Level <string of type level> -Flags <string of type flags>
   ```

    次に例を示します。

   ```PowerShell
   Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Level Info -Flags TF_COMPONENT
   ```

    -Loglevel には、Fatal、Error、Warning、Info、Verbose、Debug、または All を指定できます。 -Flags には、プロバイダーがサポートする任意のフラグ (TF_COMPONENT、TF_DIAGなど) を指定できます。 -Flags には ALL 値を指定することもできます。

   上記の例を、コマンドレットの位置指定機能を使用して入力することもできます。たとえば、プロバイダー ChatServer を AlwaysOn シナリオに追加するには、次のように入力します。

   ```PowerShell
   Edit-CsClsScenario AlwaysOn ChatServer -Level Info -Flags ALL
   ```
