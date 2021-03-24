---
title: Skype for Business Server 2015 で集中ログ サービスのシナリオを構成する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: '概要: Skype for Business Server 2015 の集中ログ サービスのシナリオを作成、変更、および削除する方法について説明します。'
ms.openlocfilehash: 6ec6764ce3717f38fead9e88c570895f1676310f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098843"
---
# <a name="configure-scenarios-for-the-centralized-logging-service-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 で集中ログ サービスのシナリオを構成する
 
**概要:** Skype for Business Server 2015 の集中ログ サービスのシナリオを作成、変更、および削除する方法について説明します。
  
シナリオでは、スコープ (グローバル、サイト、プール、またはコンピューター) と、集中ログ サービスで使用するプロバイダーを定義します。 シナリオを使用して、プロバイダー (S4、SIPStack、IM、プレゼンスなど) のトレースを有効または無効にします。 シナリオを構成することで、特定の問題の条件に対応する特定の論理コレクションのすべてのプロバイダーをグループ化できます。 トラブルシューティングとログ記録のニーズを満たすためにシナリオを変更する必要がある場合、Skype for Business Server 2015 デバッグ ツールは、Edit-CsClsScenario という名前の関数を含む ClsScenarioEdit.psm1 という名前の Windows PowerShell モジュールを提供します。 このモジュールの目的は、指定したシナリオのプロパティを編集することです。 このトピックでは、このモジュールの使用方法の例を示します。 さらに進む前に、Skype for Business Server 2015 [デバッグ ツール](https://go.microsoft.com/fwlink/p/?LinkId=285257) をダウンロードしてください。
  
> [!IMPORTANT]
> どのスコープ (サイト、グローバル、プール、またはコンピューター) でも、一度に最大で 2 つのシナリオを実行できます。 現在実行されているシナリオを確認するには、Windows PowerShell [Get-CsClsScenario を使用します](/powershell/module/skype/get-csclsscenario?view=skype-ps)。 [Set-CsClsScenario](/powershell/module/skype/set-csclsscenario?view=skype-ps)Windows PowerShellを使用すると、実行中のシナリオを動的に変更できます。 ログ セッション中に実行するシナリオを変更して、収集するデータや収集元のプロバイダーを変更または微調整することができます。 
  
Skype for Business Server 管理シェルを使用して集中ログ サービス機能を実行するには、CsAdministrator または CsServerAdministrator の役割ベースのアクセス制御 (RBAC) セキュリティ グループ、またはこれら 2 つのグループのいずれかを含むカスタム RBAC 役割のメンバーである必要があります。 このコマンドレットが割り当てられているすべての RBAC 役割 (自分で作成したカスタム RBAC の役割を含む) の一覧を返す場合は、Skype for Business Server 管理シェルまたは Windows PowerShell プロンプトから次のコマンドを実行します。
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

次に例を示します。
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

このトピックの残りの部分では、シナリオの定義、シナリオの変更、実行中のシナリオの取得、シナリオの削除、およびトラブルシューティングを最適化するために含まれるシナリオを指定する方法について説明します。 Skype for Business Server 管理シェルを使用して、次のコマンドWindows PowerShellできます。 ログ セッションを使用Windows PowerShell、ログ セッションで使用する新しいシナリオを定義できます。
  
[「Skype for Business 2015](centralized-logging-service.md)の集中ログ サービス」で導入された通り、シナリオの要素は次のとおりです。
  
- **プロバイダー** OCSLogger に精通している場合、プロバイダーは、トレース エンジンがログを収集する必要がある情報を OCSLogger に伝えるコンポーネントです。 プロバイダーは同じコンポーネントであり、多くの場合、OCSLogger のコンポーネントと同じ名前を持っています。 OCSLogger に精通していない場合、プロバイダーは、集中ログ サービスがログを収集できるサーバー 役割固有のコンポーネントです。 プロバイダーの構成の詳細については、「Configure providers for Centralized Logging Service in [Skype for Business Server 2015」を参照](configure-providers.md)してください。
    
- **ID** パラメーター -Identity は、シナリオのスコープと名前を設定します。 たとえば、"global" の範囲を設定し、"LyssServiceScenario" を使用してシナリオを特定できます。 この 2 つを組み合わせると、Identity ("global/LyssServiceScenario" など) を定義します。
    
    必要に応じて、-Name パラメーターと -Parent パラメーターを使用できます。 Name パラメーターは、シナリオを一意に識別するために定義します。 Name を使用する場合は、Parent も使用して、グローバルまたはサイトにシナリオを追加する必要があります。 
    
    > [!IMPORTANT]
    > Name パラメーターと Parent パラメーターを使用する場合は **、-Identity パラメーターを使用** できません。
  
### <a name="to-create-a-new-scenario-with-the-new-csclsscenario-cmdlet"></a>New-CsClsScenario コマンドレットを使用して新しいシナリオを作成するには

1. Skype for Business Server 管理シェルを開始する: **[スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[Skype for Business Server 管理シェル]**をクリックします**。
    
2. ログ セッションの新しいシナリオを作成するには [、New-CsClsProvider](/powershell/module/skype/new-csclsprovider?view=skype-ps) を使用し、シナリオの名前 (つまり、一意に識別する方法) を定義します。 WPP からログ形式の種類を選択します (つまり、Windows ソフトウェア トレース プリプロセッサであり、既定値)、EventLog (Windows イベント ログ形式)、または IISLog (IIS ログ ファイル形式に基づく ASCII 形式のファイル) を選択します。 次に、Level (このトピックの [ログ レベル] で定義されているレベル) とフラグ (このトピックの [フラグ] で定義されているフラグ) を定義します。
    
    このシナリオ例では、プロバイダー変数の例として LyssProvider を使用します。
    
    定義されたオプションを使用してシナリオを作成するには、次のように入力します。
    
   ```PowerShell
   New-CsClsScenario -Identity <scope>/<unique scenario name> -Provider <provider variable>
   ```

    次に例を示します。
    
   ```PowerShell
   New-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider $LyssProvider
   ```

    -Name と -Parent を使用した代替形式:
    
   ```PowerShell
   New-CsClsScenario -Name "LyssServiceScenario" -Parent "site:Redmond" -Provider $LyssProvider
   ```

### <a name="to-create-a-new-scenario-with-multiple-providers-with-the-new-csclsscenario-cmdlet"></a>複数のプロバイダーを指定した新しいシナリオを New-CsClsScenario コマンドレットを使用して作成するには

1. Skype for Business Server 管理シェルを開始する: **[スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[Skype for Business Server 管理シェル]**をクリックします**。
    
2. スコープごとのシナリオ数は 2 つまでに制限されています。 しかし、設定するプロバイダーの数に制限はありません。 この例では、3 つのプロバイダーを作成済みで、定義するシナリオに 3 つのプロバイダーをすべて割り当てる必要があるとします。 プロバイダー変数の名前は LyssProvider、ABServerProvider、および SIPStackProvider です。 複数のプロバイダーを定義してシナリオに割り当てるには、Skype for Business Server 管理シェルまたはコマンド プロンプトで次Windows PowerShell入力します。
    
   ```PowerShell
   New-CsClsScenario -Identity "site:Redmond/CollectDataScenario" -Provider @{Add=$LyssProvider, $ABServerProvider,  $SIPStackProvider}
   ```

    > [!NOTE]
    > この例で知られているWindows PowerShellハッシュ テーブルを使用して作成する規則は  `@{<variable>=<value1>, <value2>, <value>…}` assplatting と呼ばれる。 Splatting の詳細については、「Windows PowerShell」を参照してください [https://go.microsoft.com/fwlink/p/?LinkId=267760](/previous-versions/technet-magazine/gg675931(v=msdn.10)) 。 
  
### <a name="to-modify-an-existing-scenario-with-the-set-csclsscenario-cmdlet"></a>Set-CsClsScenario コマンドレットを使用して既存のシナリオを変更するには

1. Skype for Business Server 管理シェルを開始する: **[スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[Skype for Business Server 管理シェル]**をクリックします**。
    
2. スコープごとのシナリオ数は 2 つまでに制限されています。 実行するシナリオは、ログ キャプチャ セッションの実行中を含め、いつでも変更できます。 実行するシナリオを再定義すると、現在のログ セッションは削除されたシナリオの使用を停止し、新しいシナリオの使用を開始します。 ただし、削除されたシナリオでキャプチャされたログ情報はキャプチャされたログに残ります。 新しいシナリオを定義するには、次の操作を行います (つまり、"S4Provider" という名前の定義済みのプロバイダーが追加されたと仮定します)。
    
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

1. Skype for Business Server 管理シェルを開始する: **[スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[Skype for Business Server 管理シェル]**をクリックします**。
    
2. 定義済みのシナリオを削除する場合は、次のように入力します。
    
   ```PowerShell
   Remove-CsClsScenario -Identity <name of scope and scenario>
   ```

    たとえば、定義済みのシナリオ site:Redmond/LyssServiceScenario を削除するには、次のようにします。
    
   ```PowerShell
   Remove-CsClsScenario -Identity "site:Redmond/LyssServiceScenario"
   ```

**Remove-CsClsScenario** コマンドレットでは指定したシナリオが削除されますが、キャプチャ済みのトレースはログに残り、検索に利用できます。
### <a name="to-load-and-unload-the-edit-csclsscenario-cmdlet-using-the-clsscenarioeditpsm1-module"></a>ClsScenarioEdit.psm1 モジュールを使用Edit-CsClsScenarioコマンドレットを読み込み、アンロードするには

1. Skype for Business Server 管理シェルを開始する: **[スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[Skype for Business Server 管理シェル]**をクリックします**。
    
    > [!IMPORTANT]
    > ClsScenarioEdit.psm1 モジュールは、個別の Web ダウンロードとして提供されます。 このモジュールは、Skype for Business Server 2015 デバッグ ツールの一部です。 既定では、デバッグ ツールはディレクトリ C:\Program Files\Skype for Business Server 2015\デバッグ ツールにインストールされます。 
  
2. 次のコマンドWindows PowerShell入力します。
    
   ```PowerShell
   Import-Module "CDBurn\OCO\amd64\Support"
   ```

    > [!TIP]
    > モジュールの読み込みが成功すると、コマンド プロンプトWindows PowerShell返されます。 モジュールが読み込まれ、使用可能なモジュールEdit-CsClsScenarioを入力します  `Get-Help Edit-CsClsScenario` 。 すると、EditCsClsScenario の構文の基本的な概要が表示されます。 
  
3. モジュールをアンロードするには、次のように入力します。
    
   ```PowerShell
   Remove-Module ClsController
   ```

    > [!TIP]
    > モジュールのアンロードが成功すると、コマンド プロンプトWindows PowerShell返されます。 モジュールがアンロードされたのを確認するには、と入力します  `Get-Help Edit-CsClsScenario` 。 Windows PowerShellコマンドレットのヘルプを見つけて失敗します。 
  
### <a name="to-remove-an-existing-provider-from-a-scenario-with-the-edit-clscontroller-module"></a>Edit-ClsController モジュールを使用してシナリオから既存のプロバイダーを削除するには

1. Skype for Business Server 管理シェルを開始する: **[スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[Skype for Business Server 管理シェル]**をクリックします**。
    
2. 次のコマンドWindows PowerShell入力します。
    
   ```PowerShell
   Import-Module "CDBurn\OCO\amd64\Support"
   ```

    > [!TIP]
    > モジュールの読み込みが成功すると、コマンド プロンプトWindows PowerShell返されます。 モジュールが読み込まれ、使用可能なモジュールEdit-CsClsScenarioを入力します  `Get-Help Edit-CsClsScenario` 。 すると、EditCsClsScenario の構文の基本的な概要が表示されます。 
  
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

   パラメーター値の位置指定は、-Scenario および -Provider にのみ適用されます。 他のすべてのパラメーターは明示的に定義する必要があります。
    
### <a name="to-add-a-provider-to-a-scenario-with-the-edit-clscontroller-module"></a>Edit-ClsController モジュールを使用してシナリオにプロバイダーを追加するには

1. Skype for Business Server 管理シェルを開始する: **[スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[Skype for Business Server 管理シェル]**をクリックします**。
    
2. AlwaysOn シナリオにプロバイダーを追加するには、次のように入力します。
    
   ```PowerShell
   Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to add> -Level <string of type level> -Flags <string of type flags>
   ```

    次に例を示します。
    
   ```PowerShell
   Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Level Info -Flags TF_COMPONENT
   ```

    -Loglevel には、Fatal、Error、Warning、Info、Verbose、Debug、または All を指定できます。 -Flags は、プロバイダーがサポートするフラグ (アプリケーション、アプリケーション、TF_COMPONENTなどTF_DIAG。 -Flags には値 ALL を指定できます。
    
   上記の例を、コマンドレットの位置指定機能を使用して入力することもできます。たとえば、プロバイダー ChatServer を AlwaysOn シナリオに追加するには、次のように入力します。
    
   ```PowerShell
   Edit-CsClsScenario AlwaysOn ChatServer -Level Info -Flags ALL
   ```