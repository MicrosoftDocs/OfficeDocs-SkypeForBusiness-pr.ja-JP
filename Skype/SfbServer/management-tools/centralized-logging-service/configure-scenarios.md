---
title: Skype for Business Server 2015 での集中ログ サービスのシナリオの構成
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 6c3bf826-e7fd-4002-95dc-01020641ef01
description: '概要: は、作成、変更、およびビジネス サーバー 2015 の Skype で集中ログ サービスのシナリオを削除する方法を説明します。'
ms.openlocfilehash: 453c9c593e53dca186b09e1ba835bc8f94bb7112
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32217678"
---
# <a name="configure-scenarios-for-the-centralized-logging-service-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 での集中ログ サービスのシナリオの構成
 
**の概要:** 作成、変更、およびビジネス サーバー 2015 の Skype で集中ログ サービスのシナリオを削除する方法について説明します。
  
シナリオが (つまり、グローバル、サイト、プール、またはコンピューター) のスコープを定義し、一元的なログ サービスで使用するには、どのようなプロバイダーです。 シナリオを使用して、プロバイダー (S4、SIPStack、IM、プレゼンスなど) のトレースを有効または無効にします。 シナリオを構成することで、特定の問題の条件に対応する特定の論理コレクションのすべてのプロバイダーをグループ化できます。 シナリオのトラブルシューティングとログのニーズを満たすために変更する必要がある場合は、ビジネスのサーバー 2015 のデバッグ ツールの Skype に関数の namedEdit CsClsScenario を含む ClsScenarioEdit.psm1 をという名前の Windows PowerShell モジュールが提供されます。 このモジュールの目的は、指定したシナリオのプロパティを編集することです。 このトピックでは、このモジュールの使用方法の例を示します。 ビジネス サーバー 2015[のデバッグ ツール](https://go.microsoft.com/fwlink/p/?LinkId=285257)のいずれかに入る前に、Skype をダウンロードします。
  
> [!IMPORTANT]
> どのスコープ (サイト、グローバル、プール、またはコンピューター) でも、一度に最大で 2 つのシナリオを実行できます。 シナリオで実行されているを確認するのには、Windows PowerShell と[Get CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps)を使用します。 Windows PowerShell と[セット CsClsScenario](https://docs.microsoft.com/powershell/module/skype/set-csclsscenario?view=skype-ps)を使用すると、どのシナリオを実行している動的に変更できます。 ログ セッション中に実行するシナリオを変更して、収集するデータや収集元のプロバイダーを変更または微調整することができます。 
  
ビジネス サーバー管理シェルには、Skype を使用して、ログ サービスの集中管理機能を実行するには、CsAdministrator または CsServerAdministrator の役割に基づくアクセス制御 (RBAC) セキュリティ グループ、またはカスタムの RBAC の役割のいずれかのメンバーをする必要がありますがこれら 2 つのグループのいずれかが含まれています。 すべての RBAC のリストを返すため、このコマンドレットに割り当てられているなど、自分で作成したカスタムの RBAC の役割の役割がビジネス サーバー管理シェルまたは Windows PowerShell プロンプトの Skype から次のコマンドを実行します。
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

次に例を示します。
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

このトピックの以降の部分では、トラブルシューティングを最適化するためのシナリオの定義、シナリオの変更、実行中のシナリオの取得、シナリオの削除、シナリオ内容の指定の方法を中心に説明します。 ビジネス サーバー管理シェルの Skype を使用するには Windows PowerShell コマンドを実行します。 Windows PowerShell を使用する場合は、ログ ・ セッションで使用するための新しいシナリオを定義できます。
  
、[ビジネス 2015年の Skype のログ サービスの一元管理](centralized-logging-service.md)の導入シナリオの要素は。
  
- **プロバイダー**OCSLogger を理解する場合は、プロバイダーはトレース エンジンからのログを収集する必要があります OCSLogger を確認する選択したコンポーネントです。 プロバイダーは、同じコンポーネントし、多くの場合 OCSLogger で、コンポーネントと同じ名前があります。 プロバイダー サーバーの役割の特定のコンポーネントは、OCSLogger に慣れていない場合は、集中ログ サービスを収集できますからログに記録します。 プロバイダーの構成に関する詳細については、[集中ログ サービスの Skype ビジネス サーバー 2015 の構成プロバイダー](configure-providers.md)を参照してください。
    
- **識別情報**パラメーターの識別情報は、シナリオの名前とスコープを設定します。 などでした「グローバル」のスコープを設定して"LyssServiceScenario"を使用してシナリオを識別します。 Id を定義する 2 つを組み合わせると、(たとえば、「LyssServiceScenario/グローバル」)。
    
    必要に応じて、使用することができます-名前と親のパラメーターです。 Name パラメーターは、シナリオを一意に識別するために定義します。 Name を使用する場合は、Parent も使用して、グローバルまたはサイトにシナリオを追加する必要があります。 
    
    > [!IMPORTANT]
    > 名前と親のパラメーターを使用する場合は使用できません、 **・ アイデンティティ**パラメーター。
  
### <a name="to-create-a-new-scenario-with-the-new-csclsscenario-cmdlet"></a>New-CsClsScenario コマンドレットを使用して新しいシナリオを作成するには

1. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。
    
2. ログ セッションのための新しいシナリオを作成するには、[New-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/new-csclsprovider?view=skype-ps) を使用し、シナリオの名前 (シナリオを一意に識別する方法) を定義します。ログ形式の種類を、WPP (Windows ソフトウェア トレース プリプロセッサ。これが既定値です)、EventLog (Windows イベント ログ形式)、または IISLog (IIS ログ ファイル形式に基づく ASCII 形式ファイル) から選択します。次に、レベル (このトピックのログ レベルの説明で定義されています) とフラグ (このトピックのフラグの説明で定義されています) を定義します。
    
    このシナリオ例では、プロバイダー変数の例として LyssProvider を使用します。
    
    定義されたオプションを使用してシナリオを作成するには、次のように入力します。
    
   ```
   New-CsClsScenario -Identity <scope>/<unique scenario name> -Provider <provider variable>
   ```

    次に例を示します。
    
   ```
   New-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider $LyssProvider
   ```

    他の形式名と親の使用します。
    
   ```
   New-CsClsScenario -Name "LyssServiceScenario" -Parent "site:Redmond" -Provider $LyssProvider
   ```

### <a name="to-create-a-new-scenario-with-multiple-providers-with-the-new-csclsscenario-cmdlet"></a>複数のプロバイダーを指定した新しいシナリオを New-CsClsScenario コマンドレットを使用して作成するには

1. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。
    
2. スコープごとのシナリオ数は 2 つまでに制限されています。 しかし、設定するプロバイダーの数に制限はありません。 この例では、3 つのプロバイダーを作成済みで、定義するシナリオに 3 つのプロバイダーをすべて割り当てる必要があるとします。 プロバイダー変数の名前は LyssProvider、ABServerProvider、および SIPStackProvider です。 定義し、シナリオに複数のプロバイダーを割り当てるするには、ビジネスのサーバー管理シェルまたは Windows PowerShell コマンド プロンプトで、Skype で次を入力します。
    
   ```
   New-CsClsScenario -Identity "site:Redmond/CollectDataScenario" -Provider @{Add=$LyssProvider, $ABServerProvider,  $SIPStackProvider}
   ```

    > [!NOTE]
    > Windows PowerShell を使用して値のハッシュ テーブルを作成するための規則で認識されている`@{<variable>=<value1>, <value2>, <value>…}`assplatting と呼びます。 Windows PowerShell のスプラッティング技法に関する詳細についてを参照してください[https://go.microsoft.com/fwlink/p/?LinkId=267760](https://go.microsoft.com/fwlink/p/?LinkId=267760)。 
  
### <a name="to-modify-an-existing-scenario-with-the-set-csclsscenario-cmdlet"></a>Set-CsClsScenario コマンドレットを使用して既存のシナリオを変更するには

1. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。
    
2. スコープごとのシナリオ数は 2 つまでに制限されています。 実行するシナリオは、ログ キャプチャ セッションの実行中を含め、いつでも変更できます。 実行するシナリオを再定義すると、現在のログ セッションは削除されたシナリオの使用を停止し、新しいシナリオの使用を開始します。 ただし、削除されたシナリオでキャプチャされたログ情報はキャプチャされたログに残ります。 新しいシナリオを定義する (つまり、"S4Provider"という名前の定義済みのプロバイダーの追加を想定して)、次の操作を行います。
    
   ```
   Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Add=<new provider to add>}
   ```

    次に例を示します。
    
   ```
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Add=$S4Provider}
   ```

    プロバイダーを置き換える場合は、現在のセットと置き換える単一のプロバイダーか、プロバイダーのコンマ区切りリストを定義します。多数のプロバイダーのうち 1 つだけを置き換える場合は、現在のプロバイダーに新しいプロバイダーを追加して、新しいプロバイダーと既存のプロバイダーの両方を含む新しいプロバイダーのセットを作成します。すべてのプロバイダーを新しいセットで置き換える場合は、次のように入力します。
    
   ```
   Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Replace=<providers to replace existing provider set>}
   ```

    たとえば、現在の $LyssProvider、$ABServerProvider、および $SIPStackProvider のセットを $LyssServiceProvider に置き換えるには、次のように入力します。
    
   ```
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider}
   ```

    現在の $LyssProvider、$ABServerProvider、および $SIPStackProvider のセットのうち、$LyssProvider プロバイダーだけを $LyssServiceProvider に置き換えるには、次のように入力します。
    
   ```
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider, $ABServerProvider, $SIPStackProvider}
   ```

### <a name="to-remove-an-existing-scenario-with-the-remove-csclsscenario-cmdlet"></a>Remove-CsClsScenario コマンドレットを使用して既存のシナリオを削除するには

1. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。
    
2. 定義済みのシナリオを削除する場合は、次のように入力します。
    
   ```
   Remove-CsClsScenario -Identity <name of scope and scenario>
   ```

    たとえば、定義済みのシナリオ site:Redmond/LyssServiceScenario を削除するには、次のようにします。
    
   ```
   Remove-CsClsScenario -Identity "site:Redmond/LyssServiceScenario"
   ```

**Remove-CsClsScenario** コマンドレットでは指定したシナリオが削除されますが、キャプチャ済みのトレースはログに残り、検索に利用できます。
### <a name="to-load-and-unload-the-edit-csclsscenario-cmdlet-using-the-clsscenarioeditpsm1-module"></a>ClsScenarioEdit.psm1 モジュールを使用して Edit-CsClsScenario コマンドレットをロードおよびアンロードするには

1. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。
    
    > [!IMPORTANT]
    > ClsScenarioEdit.psm1 モジュールは個別の Web ダウンロードとして提供されます。 モジュールは、ビジネス サーバー 2015 のデバッグ ツールの Skype の一部です。 既定では、デバッグ ツールは C:\Program Files\Skype for Business Server 2015\Debugging Tools ディレクトリにインストールされます。 
  
2. Windows PowerShell で、次のように入力します。
    
   ```
   Import-Module "CDBurn\OCO\amd64\Support"
   ```

    > [!TIP]
    > モジュールの読み込みが成功では、Windows PowerShell コマンド プロンプトに戻ります。 モジュールが読み込まれ、編集 CsClsScenario が利用できることを確認するには、次のように入力します。 `Get-Help Edit-CsClsScenario`。 すると、EditCsClsScenario の構文の基本的な概要が表示されます。 
  
3. モジュールをアンロードするには、次のように入力します。
    
   ```
   Remove-Module ClsController
   ```

    > [!TIP]
    > 成功のアンロード モジュールを返しますする Windows PowerShell コマンド プロンプトにします。 モジュールが読み込まれていることを確認するには、次のように入力します。 `Get-Help Edit-CsClsScenario`。 Windows PowerShell コマンドレットのヘルプを検索し、失敗を試みます。 
  
### <a name="to-remove-an-existing-provider-from-a-scenario-with-the-edit-clscontroller-module"></a>Edit-ClsController モジュールを使用してシナリオから既存のプロバイダーを削除するには

1. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。
    
2. Windows PowerShell で、次のように入力します。
    
   ```
   Import-Module "CDBurn\OCO\amd64\Support"
   ```

    > [!TIP]
    > モジュールの読み込みが成功では、Windows PowerShell コマンド プロンプトに戻ります。 モジュールが読み込まれ、編集 CsClsScenario が利用できることを確認するには、次のように入力します。 `Get-Help Edit-CsClsScenario`。 すると、EditCsClsScenario の構文の基本的な概要が表示されます。 
  
3. AlwaysOn シナリオからプロバイダーを削除するには、次のように入力します。
    
   ```
   Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to remove> -Remove
   ```

   次に例を示します。
    
   ```
   Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Remove
   ```

   パラメーター ScenarioName および ProviderName は、位置指定 (コマンド ライン内の指定された位置に定義する必要がある) パラメーターです。コマンドレット名を位置 1 として、シナリオ名が位置 2、プロバイダーが位置 3 にある場合は、パラメーター名を明示的に定義する必要はありません。この情報を使用すると、上記のコマンドは次のように入力できます。
    
   ```
   Edit-CsClsScenario AlwaysOn ChatServer -Remove
   ```

   パラメーターの値の位置で配置することにのみ適用されます - シナリオとプロバイダーです。 他のすべてのパラメーターは明示的に定義する必要があります。
    
### <a name="to-add-a-provider-to-a-scenario-with-the-edit-clscontroller-module"></a>Edit-ClsController モジュールを使用してシナリオにプロバイダーを追加するには

1. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。
    
2. AlwaysOn シナリオにプロバイダーを追加するには、次のように入力します。
    
   ```
   Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to add> -Level <string of type level> -Flags <string of type flags>
   ```

    次に例を示します。
    
   ```
   Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Level Info -Flags TF_COMPONENT
   ```

    -Loglevel には、Fatal、Error、Warning、Info、Verbose、Debug、または All を指定できます。 フラグには、TF_COMPONENT、TF_DIAG など、プロバイダーがサポートするためのフラグのいずれかを指定できます。 フラグことができますのすべての値
    
   上記の例を、コマンドレットの位置指定機能を使用して入力することもできます。たとえば、プロバイダー ChatServer を AlwaysOn シナリオに追加するには、次のように入力します。
    
   ```
   Edit-CsClsScenario AlwaysOn ChatServer -Level Info -Flags ALL
   ```
