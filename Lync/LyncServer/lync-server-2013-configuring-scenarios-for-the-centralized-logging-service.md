---
title: 集中ログ サービスのシナリオの構成
TOCTitle: 集中ログ サービスのシナリオの構成
ms:assetid: 6c3bf826-e7fd-4002-95dc-01020641ef01
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ688085(v=OCS.15)
ms:contentKeyID: 49886989
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 集中ログ サービスのシナリオの構成

 

_**トピックの最終更新日:** 2016-12-08_

シナリオでは、スコープ (グローバル、サイト、プール、またはコンピューター) と、集中ログ サービス で使用するプロバイダーを定義します。シナリオを使用して、プロバイダー (S4、SIPStack、IM、プレゼンスなど) のトレースを有効または無効にします。シナリオを構成することで、特定の問題の条件に対応する特定の論理コレクションのすべてのプロバイダーをグループ化できます。トラブルシューティングやログのニーズに合わせてシナリオを変更する必要がある場合は、Lync Server 2013 のデバッグ ツールにある、*Edit-CsClsScenario* という関数を含む ClsController.psm1 という Windows PowerShell モジュールを使用できます。このモジュールの目的は、指定したシナリオのプロパティを編集することです。このトピックでは、このモジュールの使用方法の例を示します。Lync Server 2013 デバッグ ツールは、次のリンクからダウンロードできます。[http://go.microsoft.com/fwlink/?LinkId=285257](http://go.microsoft.com/fwlink/?linkid=285257)


> [!IMPORTANT]
> どのスコープ (サイト、グローバル、プール、またはコンピューター) でも、一度に最大で 2 つのシナリオを実行できます。現在実行しているシナリオを調べるには、Windows PowerShell と <A href="https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsClsScenario">Get-CsClsScenario</A> を使用します。Windows PowerShell と <A href="https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClsScenario">Set-CsClsScenario</A> を使用すると、実行するシナリオを動的に変更できます。ログ セッション中に実行するシナリオを変更して、収集するデータや収集元のプロバイダーを変更または微調整することができます。



Lync Server 管理シェルを使用して 集中ログ サービス 機能を実行するには、役割ベースのアクセス制御 (RBAC) の CsAdministrator または CsServerAdministrator セキュリティ グループか、これらの 2 つのグループのいずれかを含むカスタム RBAC 役割のメンバーである必要があります。自分で作成したカスタム RBAC 役割も含めて、このコマンドレットが割り当てられているすべての RBAC 役割の一覧を取得するには、Lync Server 管理シェル または Windows PowerShell のプロンプトから次のコマンドを実行します。

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

次に例を示します。

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

このトピックの残りの部分では、トラブルシューティングを最適化するためのシナリオの定義、シナリオの変更、実行中のシナリオの取得、シナリオの削除、およびシナリオ内容の指定の方法を中心に説明します。集中ログ サービス コマンドを発行する方法は 2 つあります。CLSController.exe (既定では C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\CLSAgent ディレクトリにあります) を使用する方法と、Lync Server 管理シェルを使用して Windows PowerShell コマンドを発行する方法です。重要な違いは、コマンド ラインで CLSController.exe を使用する場合には利用できるシナリオの選択肢が限られるのに対し、Windows PowerShell を使用する場合にはログ セッションで使用する新しいシナリオを定義できるという点です。

「[集中ログサービスの概要](lync-server-2013-overview-of-the-centralized-logging-service.md)」で説明しているように、シナリオには次の要素があります。

  - **プロバイダー:** OCSLogger に精通している方のために説明すると、プロバイダーとは、トレース エンジンのログの収集元を OCSLogger に指示するために選択するコンポーネントです。プロバイダーは OCSLogger のコンポーネントと同じコンポーネントであり、多くの場合、OCSLogger のコンポーネントと名前も同じです。OCSLogger をよく知らない方のために説明すると、プロバイダーとは、集中ログ サービス がログの収集元として使用できる、サーバーの役割に固有のコンポーネントです。プロバイダーの構成の詳細については、「[集中ログ サービス プロバイダーの構成](lync-server-2013-configuring-providers-for-centralized-logging-service.md)」を参照してください。

  - **Identity:** –Identity パラメーターは、スコープとシナリオの名前を設定します。たとえば、スコープを "global" に設定し、シナリオを "LyssServiceScenario" という名前で識別するとします。この 2 つを組み合わせる場合に、Identity (たとえば "global/LyssServiceScenario") を定義します。
    
    また、–Name パラメーターと –Parent パラメーターを使用することもできます。Name パラメーターは、シナリオを一意に識別するために定義します。Name を使用する場合は、Parent も使用して、グローバルまたはサイトにシナリオを追加する必要があります。
    

    > [!IMPORTANT]
    > Name パラメーターと Parent パラメーターを使用する場合は、<STRONG>–Identity</STRONG> パラメーターは使用できません。



## New-CsClsScenario コマンドレットを使用して新しいシナリオを作成するには

1.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

2.  ログ セッションのための新しいシナリオを作成するには、[New-CsClsProvider](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsClsProvider) を使用し、シナリオの名前 (シナリオを一意に識別する方法) を定義します。ログ形式の種類を、WPP (Windows ソフトウェア トレース プリプロセッサ。これが既定値です)、EventLog (Windows イベント ログ形式)、または IISLog (IIS ログ ファイル形式に基づく ASCII 形式ファイル) から選択します。次に、レベル (このトピックのログ レベルの説明で定義されています) とフラグ (このトピックのフラグの説明で定義されています) を定義します。
    
    このシナリオ例では、プロバイダー変数の例として LyssProvider を使用します。
    
    定義されたオプションを使用してシナリオを作成するには、次のように入力します。
    
        New-CsClsScenario -Identity <scope>/<unique scenario name> -Provider <provider variable>
    
    次に例を示します。
    
        New-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider $LyssProvider
    
    これに代わる、–Name と –Parent を使用する形式は次のとおりです。
    
        New-CsClsScenario -Name "LyssServiceScenario" -Parent "site:Redmond" -Provider $LyssProvider

## 複数のプロバイダーを指定した新しいシナリオを New-CsClsScenario コマンドレットを使用して作成するには

1.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

2.  スコープごとのシナリオ数は 2 つまでに制限されています。しかし、設定するプロバイダーの数に制限はありません。この例では、3 つのプロバイダーを作成済みで、定義するシナリオに 3 つのプロバイダーをすべて割り当てる必要があるとします。プロバイダー変数の名前は LyssProvider、ABServerProvider、および SIPStackProvider です。シナリオに複数のプロバイダーを定義して割り当てるには、Lync Server 管理シェルまたは Windows PowerShell のコマンド プロンプトで次のように入力します。
    
        New-CsClsScenario -Identity "site:Redmond/CollectDataScenario" -Provider @{Add=$LyssProvider, $ABServerProvider,  $SIPStackProvider}
    
    > [!NOTE]
    > Windows PowerShell で知られているように、<code>@{&lt;variable&gt;=&lt;value1&gt;, &lt;value2&gt;, &lt;value&gt;...}</code> を使用して値のハッシュ テーブルを作成する方法をスプラッティングと呼びます。Windows PowerShell でのスプラッティングの詳細については、<a href="http://go.microsoft.com/fwlink/?linkid=267760%26clcid=0x411" class="uri">http://go.microsoft.com/fwlink/?linkid=267760&amp;clcid=0x411</a> を参照してください。


## Set-CsClsScenario コマンドレットを使用して既存のシナリオを変更するには

1.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

2.  スコープごとのシナリオ数は 2 つまでに制限されています。実行するシナリオは、ログ キャプチャ セッションの実行中を含め、いつでも変更できます。実行するシナリオを再定義すると、現在のログ セッションは削除されたシナリオの使用を停止し、新しいシナリオの使用を開始します。ただし、削除されたシナリオでキャプチャされたログ情報はキャプチャされたログに残ります。新しいシナリオを定義するには、次のようにします (ここでは、定義済みのプロバイダー "S4Provider" を追加するものとします)。
    
        Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Add=<new provider to add>}
    
    次に例を示します。
    
        Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Add=$S4Provider}
    
    プロバイダーを置き換える場合は、現在のセットと置き換える単一のプロバイダーか、プロバイダーのコンマ区切りリストを定義します。多数のプロバイダーのうち 1 つだけを置き換える場合は、現在のプロバイダーに新しいプロバイダーを追加して、新しいプロバイダーと既存のプロバイダーの両方を含む新しいプロバイダーのセットを作成します。すべてのプロバイダーを新しいセットで置き換える場合は、次のように入力します。
    
        Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Replace=<providers to replace existing provider set>}
    
    たとえば、現在の $LyssProvider、$ABServerProvider、および $SIPStackProvider のセットを $LyssServiceProvider に置き換えるには、次のように入力します。
    
        Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider}
    
    現在の $LyssProvider、$ABServerProvider、および $SIPStackProvider のセットのうち、$LyssProvider プロバイダーだけを $LyssServiceProvider に置き換えるには、次のように入力します。
    
        Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider, $ABServerProvider, $SIPStackProvider}

## Remove-CsClsScenario コマンドレットを使用して既存のシナリオを削除するには

1.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

2.  定義済みのシナリオを削除する場合は、次のように入力します。
    
        Remove-CsClsScenario -Identity <name of scope and scenario>
    
    たとえば、定義済みのシナリオ site:Redmond/LyssServiceScenario を削除するには、次のようにします。
    
        Remove-CsClsScenario -Identity "site:Redmond/LyssServiceScenario"

**Remove-CsClsScenario** コマンドレットでは指定したシナリオが削除されますが、キャプチャ済みのトレースはログに残り、検索に利用できます。

## ClsController.psm1 モジュールを使用して Edit-CsClsScenario コマンドレットをロードおよびアンロードするには

1.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。
    

    > [!IMPORTANT]
    > ClsController.psm1 モジュールは個別の Web ダウンロードとして提供されます。このモジュールは Lync Server 2013 デバッグ ツールの一部です。既定では、デバッグ ツールは C:\Program Files\Lync Server 2013\Debugging Tools ディレクトリにインストールされます。



2.  Windows PowerShell から次のように入力します。
    
        Import-Module "C:\Program Files\Lync Server 2013\Debugging Tools\ClsController.psm1"
    

    > [!TIP]
    > モジュールのロードが成功すると、Windows PowerShell コマンド プロンプトに戻ります。モジュールがロードされ、Edit-CsClsScenario を使用できることを確認するには、「<CODE>Get-Help Edit-CsClsScenario</CODE>」と入力します。すると、EditCsClsScenario の構文の基本的な概要が表示されます。



3.  モジュールをアンロードするには、次のように入力します。
    
        Remove-Module ClsController
    

    > [!TIP]
    > モジュールのアンロードが成功すると、Windows PowerShell コマンド プロンプトに戻ります。モジュールがアンロードされたことを確認するには、「<CODE>Get-Help Edit-CsClsScenario</CODE>」と入力します。すると、Windows PowerShell はこのコマンドレットのヘルプの検出を試みて失敗します。



## Edit-ClsController モジュールを使用してシナリオから既存のプロバイダーを削除するには

1.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

2.  AlwaysOn シナリオからプロバイダーを削除するには、次のように入力します。
    
        Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to remove> -Remove
    
    次に例を示します。
    
        Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Remove
    
    パラメーター ScenarioName および ProviderName は、位置指定 (コマンド ライン内の指定された位置に定義する必要がある) パラメーターです。コマンドレット名を位置 1 として、シナリオ名が位置 2、プロバイダーが位置 3 にある場合は、パラメーター名を明示的に定義する必要はありません。この情報を使用すると、上記のコマンドは次のように入力できます。
    
        Edit-CsClsScenario AlwaysOn ChatServer -Remove
    
    パラメーター値の位置指定は、–Scenario と –Provider にのみ適用されます。他のすべてのパラメーターは明示的に定義する必要があります。

## Edit-ClsController モジュールを使用してシナリオにプロバイダーを追加するには

1.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

2.  AlwaysOn シナリオにプロバイダーを追加するには、次のように入力します。
    
        Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to add> -Level <string of type level> -Flags <string of type flags>
    
    次に例を示します。
    
        Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Level Info -Flags TF_COMPONENT
    
    \-Loglevel には、Fatal、Error、Warning、Info、Verbose、Debug、または All を指定できます。–Flags には、TF\_COMPONENT、TF\_DIAG など、プロバイダーでサポートされるフラグのいずれかを指定できます。また、値 ALL も指定できます。
    
    上記の例を、コマンドレットの位置指定機能を使用して入力することもできます。たとえば、プロバイダー ChatServer を AlwaysOn シナリオに追加するには、次のように入力します。
    
        Edit-CsClsScenario AlwaysOn ChatServer -Level Info -Flags ALL

