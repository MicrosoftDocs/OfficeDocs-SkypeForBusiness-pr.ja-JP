---
title: グローバル集中ログ サービス構成、サイト、コンピューターの管理
TOCTitle: グローバル集中ログ サービス構成、サイト、コンピューターの管理
ms:assetid: 93b9a354-9aea-4b3a-a4fe-68a89f436196
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ688138(v=OCS.15)
ms:contentKeyID: 49887058
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# グローバル集中ログ サービス構成、サイト、コンピューターの管理

 

_**トピックの最終更新日:** 2014-02-04_

集中ログ サービス は、単一のコンピューター、コンピューターのプールを含むスコープ、サイト スコープ (展開内のコンピューターとプールのコレクションを含む Redmond サイトなどの定義済みのサイト)、またはグローバル スコープ (展開内のすべてのコンピューターとプール)で実行できます。

Lync Server 管理シェルを使用して 集中ログ サービス のスコープを構成するには、CsAdministrator または CsServerAdministrator の役割ベースのアクセス制御 (RBAC) セキュリティ グループのメンバーであるか、これらの 2 つのグループのいずれかを含むカスタムの RBAC の役割を持っている必要があります。このコマンドレットが割り当てられているすべての RBAC の役割の一覧 (自身が作成したカスタムの RBAC の役割を含む) を戻すには、Lync Server 管理シェルまたは Windows PowerShell プロンプトから次のコマンドを実行します。

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Lync Server 2013 cmdlet>"}

次に例を示します。

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

> [!NOTE]
> Windows PowerShell には、CLSController.exe では使用できないオプションと追加の構成オプションがあります。CLSController には迅速かつ正確にコマンドを実行するための方法が用意されていますが、CLSController で使用可能なコマンドは制限されています。Windows PowerShell では、CLSController のコマンド プロセッサで使用可能なコマンドだけでなく、さまざまなコマンドと豊富なオプションが提供されます。たとえば、CLSController.exe は –computers と –pools のスコープ オプションを提供します。Windows PowerShell を使用すると、ほとんどのコマンドでコンピューターやプールを示すことができます。新しいシナリオ (CLSController には、ユーザーが変更できない特定数のシナリオがあります) を定義する場合は、サイト スコープまたはグローバル スコープを定義できます。Windows PowerShell のこの強力な機能を使用すると、サイト スコープまたはグローバル スコープのシナリオを定義できますが、コンピューターまたはプールに対する実際のログ記録は制限されます。<br />
> Windows PowerShell または CLSController で実行できるコマンド ラインのコマンドには根本的な違いがあります。Windows PowerShell には、シナリオを構成および定義し、トラブルシューティングのシナリオでそれらを有意義に再利用する方法が用意されています。一方、CLSController には、コマンドを高速かつ効率的に実行して結果を得るための方法が用意されています。CLSController のコマンド セットは、コマンド ラインから使用できる特定数のコマンドに制限されています。Windows PowerShell のコマンドレットとは異なり、CLSController で新しいシナリオを定義したり、サイト レベルやグローバル レベルでスコープを管理したりすることはできません。また、特定数のコマンド セットのその他の多くの制限により、コマンドを動的に構成することもできません。CLSController は高速実行のための手段を提供し、Windows PowerShell は 集中ログ サービス の機能を拡張して、CLSController ではできない処理を行うための手段を提供します。


–Computers パラメーターを使用して [Search-CsClsLogging](https://docs.microsoft.com/en-us/powershell/module/skype/Search-CsClsLogging)、[Show-CsClsLogging](https://docs.microsoft.com/en-us/powershell/module/skype/Show-CsClsLogging)、[Start-CsClsLogging](https://docs.microsoft.com/en-us/powershell/module/skype/Start-CsClsLogging)、[Stop-CsClsLogging](https://docs.microsoft.com/en-us/powershell/module/skype/Stop-CsClsLogging)、[Sync-CsClsLogging](https://docs.microsoft.com/en-us/powershell/module/skype/Sync-CsClsLogging)、[Update-CsClsLogging](https://docs.microsoft.com/en-us/powershell/module/skype/Update-CsClsLogging) の各コマンドを実行する場合に、単一のコンピューターのスコープを定義できます。–Computers パラメーターには、対象のコンピューターの完全修飾ドメイン名 (FQDN) のコンマ区切り一覧を指定できます。


> [!TIP]
> –Pools およびログ記録コマンドを実行するプールのコンマ区切り一覧を定義することもできます。



サイト スコープとグローバル スコープは、集中ログ サービス の **New-**、**Set-**、および **Remove-** の各コマンドレットで定義されます。以下の例は、サイト スコープとグローバル スコープを設定する方法を示しています。


> [!IMPORTANT]
> ここに示すコマンドには、他のセクションで説明するパラメーターと概念が含まれている場合があります。このコマンド例は、<STRONG>–Identity</STRONG> パラメーターを使用してスコープを定義する方法を示すことを目的としています。完全を期すために使用されているコマンドや、スコープを指定するためのコマンドも含まれています。<STRONG>Set-CsClsConfiguration</STRONG> コマンドレットの詳細については、「操作」のドキュメントの「<A href="https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClsConfiguration">Set-CsClsConfiguration</A>」を参照してください。



## 集中ログ サービス の現在の構成を取得するには

1.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

2.  コマンド ライン プロンプトで次のように入力します。
    
        Get-CsClsConfiguration

**New-CsClsConfiguration** コマンドレットと **Set-CsClsConfiguration** コマンドレットを使用して、新しい構成を作成するか、既存の構成を更新します。

**Get-CsClsConfiguration** を実行すると、次のスクリーンショットに示すような情報が表示されます。現在、この展開には既定のグローバル構成がありますが、サイト構成は定義されていません。

![Get-CsClsConfiguration からのサンプル出力](images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "Get-CsClsConfiguration からのサンプル出力")

## コンピューターのローカル ストアから 集中ログ サービス の現在の構成を取得するには

1.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

2.  コマンド ライン プロンプトで次のように入力します。
    
        Get-CsClsConfiguration -LocalStore

**Get-CsClsConfiguration** でパラメーターを指定しない最初の例を使用すると、このコマンドはデータの中央管理ストアを参照します。–LocalStore パラメーターを指定すると、このコマンドは中央管理ストアではなくコンピューターの LocalStore を参照します。

## 現在定義されているシナリオの一覧を取得するには

1.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

2.  コマンド ライン プロンプトで次のように入力します。
    
        Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
    
    たとえば、グローバル スコープで定義されているシナリオを取得するには、次のように入力します。
    
        Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios

**Get-CsClsConfiguration** コマンドレットを使用すると、特定のスコープの構成に含まれるシナリオが常に表示されます。ほとんどの場合、シナリオがすべて表示されるのではなく、一部が切り捨てられます。ここで使用するコマンドは、すべてのシナリオおよび使用されているプロバイダー、設定、およびフラグに関する一部の情報を一覧表示します。

## Windows PowerShell を使用して 集中ログ サービス のグローバル スコープを更新するには

1.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

2.  コマンド ライン プロンプトで次のように入力します。
    
        Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
    
    次に例を示します。
    
        Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40

このコマンドは、トレース ファイルのロールオーバーのサイズを 40 MB に設定するよう、展開内の各コンピューターおよびプールの CLSAgent に指示します。すべてのサイトのコンピューターとプールがこのコマンドの対象となり、コンピューターとプールの構成済みのトレース ログのロールオーバーの値が 40 MB に設定されます。

## Windows PowerShell を使用して 集中ログ サービス のサイト スコープを更新するには

1.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

2.  コマンド ライン プロンプトで次のように入力します。
    
        Set-CsClsConfiguration -Identity <scope/site name> -EtlFileRolloverSizeMB <size for logging file in megabytes> -EtlFileFolder <default location %TEMP%\Tracing>
    
    次に例を示します。
    
        Set-CsClsConfiguration -Identity "site/Redmond" -EtlFileRolloverSizeMB 40 -EtlFileFolder "C:\LogFiles\Tracing" 
    
    > [!NOTE]
    > この例に示すように、ログ ファイルの既定の場所は %TEMP%\Tracing です。ただし、これは実際にはファイルを書き込む CLSAgent であり、CSLAgent はネットワーク サービスとして実行されるため、%TEMP% 変数は %WINDIR%\ServiceProfiles\NetworkService\AppData\Local に展開されます。


このコマンドは、トレース ファイルのロールオーバーのサイズを 40 MB に設定するよう、Redmond サイト内の各コンピューターおよびプールの CLSAgent に指示します。他のサイトのコンピューターとプールはこのコマンドの対象ではなく、現在構成されているトレース ログのロールオーバーの値 (既定値の 20 MB またはログ記録セッションの開始時に定義された値) が引き続き使用されます。

## 集中ログ サービス の新しい構成を作成するには

1.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

2.  コマンド ライン プロンプトで次のように入力します。
    
        New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
    
    > [!NOTE]
    > New-CsClsConfiguration を使用すると、オプションの多数の構成設定にアクセスできます。構成オプションの詳細については、「<a href="https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsClsConfiguration">Get-CsClsConfiguration</a>」および「<a href="lync-server-2013-understanding-centralized-logging-service-configuration-settings.md">集中ログ サービスの構成設定について</a>」を参照してください。
    
    たとえば、キャッシュ ファイル用のネットワーク フォルダー、ログ ファイルのロールオーバー時間、およびログ ファイルのロールオーバー サイズを定義する新しい構成を作成するには、次のように入力します。
    
        New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40

新しい構成の作成および 集中ログ サービス の新しいプロパティの定義方法を計画する際には注意が必要です。変更は慎重に行い、問題のシナリオのログを適切に記録する機能に及ぼす影響について理解しておいてください。ログの管理機能を強化する、つまり発生した問題を解決するためのサイズおよびロールオーバー時間を定義できるように構成を変更する必要があります。

## 集中ログ サービス の既存の構成を削除するには

1.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

2.  コマンド ライン プロンプトで次のように入力します。
    
        Remove-CsClsConfiguration -Identity <scope and name>
    
    たとえば、ログ ファイルのロールオーバー時間とログ ファイルのロールオーバー サイズを増やし、ログ ファイルのキャッシュの場所をネットワーク共有に設定するために作成した 集中ログ サービス の構成を削除するには、次のように入力します。
    
        Remove-CsClsConfiguration -Identity "site:Redmond"
    
    > [!NOTE]
    > これは、「集中ログ サービス の新しい構成を作成するには」の手順で作成された新しい構成です。


サイト レベルの構成の削除を選択すると、そのサイトではグローバル設定が使用されます。

## 関連項目

#### 概念

[集中ログサービスの概要](lync-server-2013-overview-of-the-centralized-logging-service.md)  

#### その他のリソース

[PowerShell を使用する集中ログ サービス構成設定の管理](lync-server-2013-managing-the-centralized-logging-service-configuration-settings.md)  
[Set-CsClsConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClsConfiguration)  
[Get-CsClsConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsClsConfiguration)  
[New-CsClsConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsClsConfiguration)  
[Remove-CsClsConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsClsConfiguration)

