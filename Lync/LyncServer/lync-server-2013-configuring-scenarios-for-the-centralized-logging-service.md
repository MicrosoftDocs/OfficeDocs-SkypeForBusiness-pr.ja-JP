---
title: 'Lync Server 2013: 集中ログサービスのシナリオの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring scenarios for the Centralized Logging Service
ms:assetid: 6c3bf826-e7fd-4002-95dc-01020641ef01
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688085(v=OCS.15)
ms:contentKeyID: 49733682
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa94715cd3360e032f2d791c0e02cc791c437185
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146930"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-scenarios-for-the-centralized-logging-service-in-lync-server-2013"></a>Lync Server 2013 での集中ログサービスのシナリオの構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-02-05_

シナリオでは、集中ログサービスで使用するスコープ (グローバル、サイト、プール、またはコンピューター) とプロバイダーを定義します。 シナリオを使用して、プロバイダー (S4、SIPStack、IM、プレゼンスなど) のトレースを有効または無効にします。 シナリオを構成することで、特定の問題の条件に対応する特定の論理コレクションのすべてのプロバイダーをグループ化できます。 トラブルシューティングとログのニーズに合わせてシナリオを変更する必要があることが判明した場合は、Lync Server 2013 デバッグツールによって、 *clscontroller.psm1*という名前の Windows PowerShell モジュールが提供されます。このモジュールには、「 *Edit-csclsscenario*」という名前の関数が含まれています。 このモジュールの目的は、指定したシナリオのプロパティを編集することです。 このトピックでは、このモジュールの使用方法の例を示します。 Lync Server 2013 デバッグツールは、次のリンクからダウンロードされます。[https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?linkid=285257)

<div>


> [!IMPORTANT]  
> どのスコープ (サイト、グローバル、プール、またはコンピューター) でも、一度に最大で 2 つのシナリオを実行できます。 現在実行されているシナリオを確認するには、Windows PowerShell を使用して、 <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario">-CsClsScenario を取得</A>します。 Windows PowerShell と<A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClsScenario">設定-CsClsScenario</A>を使用すると、実行するシナリオを動的に変更できます。 ログ セッション中に実行するシナリオを変更して、収集するデータや収集元のプロバイダーを変更または微調整することができます。



</div>

Lync Server 管理シェルを使用して集中ログサービスの機能を実行するには、CsAdministrator または CsServerAdministrator の役割ベースのアクセス制御 (RBAC) セキュリティグループのメンバーであるか、またはいずれかを含むカスタムの RBAC の役割を持っている必要があります。これらの2つのグループの場合。 このコマンドレットが割り当てられているすべての RBAC の役割の一覧を返すには、自分で作成したカスタムの RBAC の役割を含めて、Lync Server 管理シェルまたは Windows PowerShell プロンプトから次のコマンドを実行します。

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

次に例を示します。

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

このトピックの残りの部分では、シナリオを定義する方法、シナリオを変更する方法、実行しているシナリオを取得する方法、シナリオを削除する方法、およびシナリオの内容を指定してトラブルシューティングを最適化する方法について取り上げます。 集中ログサービスのコマンドを発行するには、2つの方法があります。 既定で\\は、フォルダー C: Program Files\\Common Files\\Microsoft Lync Server 2013\\clscontroller にある clscontroller を使用できます。 または、Lync Server 管理シェルを使用して、Windows PowerShell コマンドを発行することもできます。 重要な違いは、コマンドラインで CLSController を使用する場合は、使用可能なシナリオが限られていることです。 Windows PowerShell を使用すると、ログセッションで使用するための新しいシナリオを定義できます。

[Lync Server 2013 の集中ログサービスの概要](lync-server-2013-overview-of-the-centralized-logging-service.md)で説明されているように、シナリオの要素は次のとおりです。

  - **プロバイダー**   ocslogger を熟知している場合、プロバイダーは、トレースエンジンがログを収集する内容を ocslogger に通知するために選択するコンポーネントです。 プロバイダーは同じコンポーネントで、多くの場合、OCSLogger のコンポーネントと同じ名前になります。 OCSLogger を使い慣れていない場合、プロバイダーは、集中ログサービスがログを収集できるサーバーロール固有のコンポーネントです。 プロバイダーの構成の詳細については、「 [Lync Server 2013 の集中ログサービスのプロバイダーの構成](lync-server-2013-configuring-providers-for-centralized-logging-service.md)」を参照してください。

  - **Identity**   パラメーター-identity は、シナリオのスコープと名前を設定します。 たとえば、"グローバル" の範囲を設定し、"LyssServiceScenario" を使用してシナリオを特定することができます。 2つを組み合わせる場合は、Id (たとえば、"global/LyssServiceScenario") を定義します。
    
    また、–Name パラメーターと –Parent パラメーターを使用することもできます。Name パラメーターは、シナリオを一意に識別するために定義します。Name を使用する場合は、Parent も使用して、グローバルまたはサイトにシナリオを追加する必要があります。
    
    <div>
    

    > [!IMPORTANT]  
    > Name パラメーターと Parent パラメーターを使用する場合は、<STRONG>–Identity</STRONG> パラメーターは使用できません。

    
    </div>

<div>

## <a name="to-create-a-new-scenario-with-the-new-csclsscenario-cmdlet"></a>New-CsClsScenario コマンドレットを使用して新しいシナリオを作成するには

1.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

2.  ログセッションの新しいシナリオを作成するには、[新しい-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/New-CsClsProvider)を使用して、シナリオの名前 (一意に識別される方法) を定義します。 WPP からのログ形式の種類 (つまり、Windows software tracing プリプロセッサと既定値)、EventLog (Windows イベントログの形式)、または IISLog (つまり、IIS ログファイル形式に基づいた ASCII 形式ファイル) を選択します。 次に、レベルを定義します (このトピックのログレベルで定義されています)。フラグ (このトピックのフラグの下で定義されています)。
    
    このシナリオ例では、プロバイダー変数の例として LyssProvider を使用します。
    
    定義されたオプションを使用してシナリオを作成するには、次のように入力します。
    
        New-CsClsScenario -Identity <scope>/<unique scenario name> -Provider <provider variable>
    
    次に例を示します。
    
        New-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider $LyssProvider
    
    これに代わる、–Name と –Parent を使用する形式は次のとおりです。
    
        New-CsClsScenario -Name "LyssServiceScenario" -Parent "site:Redmond" -Provider $LyssProvider

</div>

<div>

## <a name="to-create-a-new-scenario-with-multiple-providers-with-the-new-csclsscenario-cmdlet"></a>複数のプロバイダーを指定した新しいシナリオを New-CsClsScenario コマンドレットを使用して作成するには

1.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

2.  スコープごとのシナリオ数は 2 つまでに制限されています。 しかし、設定するプロバイダーの数に制限はありません。 この例では、3 つのプロバイダーを作成済みで、定義するシナリオに 3 つのプロバイダーをすべて割り当てる必要があるとします。 プロバイダー変数の名前は LyssProvider、ABServerProvider、および SIPStackProvider です。 複数のプロバイダーを定義してシナリオに割り当てるには、Lync Server 管理シェルまたは Windows PowerShell コマンドプロンプトで次のように入力します。
    
        New-CsClsScenario -Identity "site:Redmond/CollectDataScenario" -Provider @{Add=$LyssProvider, $ABServerProvider,  $SIPStackProvider}
    
    <div>
    

    > [!NOTE]  
    > Windows PowerShell で認識されているように、を使用して<CODE>@{&lt;variable&gt;=&lt;value1&gt;, &lt;value2&gt;, &lt;value&gt;...}</CODE>ハッシュテーブルを作成する規則は、<EM>スプラッティング</EM>と呼ばれます。 Windows PowerShell のスプラッティングの詳細について<A href="https://go.microsoft.com/fwlink/p/?linkid=267760">https://go.microsoft.com/fwlink/p/?LinkId=267760</A>は、「」を参照してください。

    
    </div>

</div>

<div>

## <a name="to-modify-an-existing-scenario-with-the-set-csclsscenario-cmdlet"></a>Set-CsClsScenario コマンドレットを使用して既存のシナリオを変更するには

1.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

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

</div>

<div>

## <a name="to-remove-an-existing-scenario-with-the-remove-csclsscenario-cmdlet"></a>Remove-CsClsScenario コマンドレットを使用して既存のシナリオを削除するには

1.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

2.  定義済みのシナリオを削除する場合は、次のように入力します。
    
        Remove-CsClsScenario -Identity <name of scope and scenario>
    
    たとえば、定義済みのシナリオ site:Redmond/LyssServiceScenario を削除するには、次のようにします。
    
        Remove-CsClsScenario -Identity "site:Redmond/LyssServiceScenario"

**Remove-CsClsScenario** コマンドレットでは指定したシナリオが削除されますが、キャプチャ済みのトレースはログに残り、検索に利用できます。

</div>

<div>

## <a name="to-load-and-unload-the-edit-csclsscenario-cmdlet-using-the-clscontrollerpsm1-module"></a>ClsController.psm1 モジュールを使用して Edit-CsClsScenario コマンドレットをロードおよびアンロードするには

1.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。
    
    <div>
    

    > [!IMPORTANT]  
    > ClsController.psm1 モジュールは個別の Web ダウンロードとして提供されます。 このモジュールは、Lync Server 2013 デバッグツールに含まれています。 既定では、デバッグ ツールは C:\Program Files\Lync Server 2013\Debugging Tools ディレクトリにインストールされます。

    
    </div>

2.  Windows PowerShell で、次のように入力します。
    
        Import-Module "C:\Program Files\Lync Server 2013\Debugging Tools\ClsController.psm1"
    
    <div>
    

    > [!TIP]  
    > モジュールの読み込みが成功すると、Windows PowerShell コマンドプロンプトに戻ります。 モジュールが読み込まれ、編集-CsClsScenario が使用可能であることを<CODE>Get-Help Edit-CsClsScenario</CODE>確認するには、「」と入力します。 すると、EditCsClsScenario の構文の基本的な概要が表示されます。

    
    </div>

3.  モジュールをアンロードするには、次のように入力します。
    
        Remove-Module ClsController
    
    <div>
    

    > [!TIP]  
    > モジュールが正常にアンロードされると、Windows PowerShell コマンドプロンプトに戻ります。 モジュールがアンロードされたことを確認<CODE>Get-Help Edit-CsClsScenario</CODE>するには、「」と入力します。 Windows PowerShell は、コマンドレットのヘルプを検索して失敗します。

    
    </div>

</div>

<div>

## <a name="to-remove-an-existing-provider-from-a-scenario-with-the-edit-clscontroller-module"></a>Edit-ClsController モジュールを使用してシナリオから既存のプロバイダーを削除するには

1.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

2.  AlwaysOn シナリオからプロバイダーを削除するには、次のように入力します。
    
        Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to remove> -Remove
    
    次に例を示します。
    
        Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Remove
    
    パラメーター ScenarioName および ProviderName は、位置指定 (コマンド ライン内の指定された位置に定義する必要がある) パラメーターです。コマンドレット名を位置 1 として、シナリオ名が位置 2、プロバイダーが位置 3 にある場合は、パラメーター名を明示的に定義する必要はありません。この情報を使用すると、上記のコマンドは次のように入力できます。
    
        Edit-CsClsScenario AlwaysOn ChatServer -Remove
    
    パラメーター値の位置指定は、–Scenario と –Provider にのみ適用されます。他のすべてのパラメーターは明示的に定義する必要があります。

</div>

<div>

## <a name="to-add-a-provider-to-a-scenario-with-the-edit-clscontroller-module"></a>Edit-ClsController モジュールを使用してシナリオにプロバイダーを追加するには

1.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

2.  AlwaysOn シナリオにプロバイダーを追加するには、次のように入力します。
    
        Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to add> -Level <string of type level> -Flags <string of type flags>
    
    次に例を示します。
    
        Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Level Info -Flags TF_COMPONENT
    
    \-Loglevel には、Fatal、Error、Warning、Info、Verbose、Debug、または All の種類を指定できます。 – Flags には、プロバイダーがサポートする任意のフラグ (TF\_COMPONENT、tf\_DIAG など) を指定できます。 また、値 ALL も指定できます。
    
    上記の例を、コマンドレットの位置指定機能を使用して入力することもできます。たとえば、プロバイダー ChatServer を AlwaysOn シナリオに追加するには、次のように入力します。
    
        Edit-CsClsScenario AlwaysOn ChatServer -Level Info -Flags ALL

</div>

</div>

<span> </span>

</div>

</div>

</div>

