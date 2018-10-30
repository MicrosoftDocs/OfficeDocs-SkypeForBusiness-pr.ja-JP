---
title: 集中ログ サービスの Stop の使用
TOCTitle: 集中ログ サービスの Stop の使用
ms:assetid: 09ac093e-8f30-4874-84b4-12548ac8c898
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ687964(v=OCS.15)
ms:contentKeyID: 49886835
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 集中ログ サービスの Stop の使用

 

_**トピックの最終更新日:** 2012-11-01_

Stop-CsClsLogging コマンドレットを使用すると、現在実行中のログ セッションを停止できます。一般に、ログ セッションを停止しなければならない状況は多くありません。たとえば、ログを検索して構成を変更する場合も、最初にログを停止する必要はありません。例として、AlwaysOn と UserReplicator を実行する 2 つのシナリオで、Authentication に関連する情報を収集する必要がある場合を考えます。この場合、Authentication シナリオの実行を開始する前に、AlwaysOn または UserReplicator のどちらか一方のシナリオを (グローバル、サイト、プール、またはコンピューター スコープで) 停止する必要があります。詳細については、「[Stop-CsClsLogging](https://docs.microsoft.com/en-us/powershell/module/skype/Stop-CsClsLogging)」を参照してください。

> [!NOTE]
> 特定の展開、プール、またはコンピューターで実行できるシナリオについて重要なことがあります。それは、1 つのコンピューターで実行できるシナリオは 2 つに制限されているということです。プールでのアクティビティのログを記録する場合は、プールを 1 つのエンティティと見なす必要があります。ほとんどの場合、プール内のコンピューターごとに異なるシナリオを実行するのは現実的ではありません。データを収集する問題に対象を絞り、全体的な展開から特定のコンピューターに対して最も意味のあるシナリオを考えることこそ重要です。たとえば、UserReplicator シナリオの場合、エッジ サーバーまたはエッジ プールで UserReplicator を実行してもほとんど意味はありません。<br />
> 問題とその影響が及ぶ範囲を把握したら、次は、どのコンピューターと、どのプールで、どのようなシナリオを実行するかについて慎重に検討する必要があります。AlwaysOn シナリオは各種プロバイダーについての情報を収集するため、多岐にわたるアプリケーションに対しては有効ですが、シナリオが限定的であれば、それが効果を発揮するコンピューターやプールも一部に限定されます。また、最初に特定のシナリオの価値を理解することなく、ログ セッションをランダムに開始する場合も注意が必要です。誤ったシナリオを使用していたり、タスクに適切なシナリオであるが、そのシナリオを適用するスコープ (グローバル、サイト、プール、またはコンピューター) が誤っていたりすると、ほとんど役に立たない不適切な (シナリオをまったく実行してないかのような) データが得られる可能性があります。


Lync Server 管理シェルを使用して 集中ログ サービス 機能を制御するには、役割ベースのアクセス制御 (RBAC) セキュリティ グループの CsAdministrator または CsServerAdministrator のどちらかのメンバーであるか、どちらかのグループを含むカスタム RBAC 役割である必要があります。このコマンドレットが割り当てられている RBAC のすべての役割 (独自に作成したカスタム RBAC の役割を含む) のリストを返すには、Lync Server 管理シェルまたは Windows PowerShell プロンプトから次のコマンドを実行します。

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

次に例を示します。

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

## 現在実行中の 集中ログ サービス セッションを停止するには

1.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

2.  集中ログ サービス をクエリして、現在実行中のシナリオを検出します。そのためには、次のように入力します。
    
        Show-CsClsLogging
    
    ![Show-CsCl 呼び出し後の Windows PowerShell コンソール](images/JJ687964.eb190c32-529c-4277-a731-52c47d22d8fa(OCS.15).jpg "Show-CsCl 呼び出し後の Windows PowerShell コンソール")
    
    Show-CsClsLogging の結果、現在実行中のシナリオの概要と、そのシナリオの実行スコープが表示されます。詳細については、「[Show-CsClsLogging](https://docs.microsoft.com/en-us/powershell/module/skype/Show-CsClsLogging)」を参照してください。

3.  特定のシナリオによる現在実行中のログ セッションを停止するには、次のように入力します。
    
        Stop-CsClsLogging -Scenario <scenario name> -Computers <comma separated list of fully qualified computer names> -Pools <comma separated list of fully qualified pool names>
    
    次に例を示します。
    
        Stop-CsClsLogging -Scenario UserReplicator -Pools pool01.contoso.net
    
    このコマンドは、pool01.contoso.net での UserReplicatior シナリオによるログ記録を停止します。
    
    > [!NOTE]
    > UserReplicator シナリオを使用するこのログ セッション中に作成されたログは削除されません。このログは、Search-CsClsLogging コマンドを使用して検索を実行する場合も使用できます。詳細については、「<a href="https://docs.microsoft.com/en-us/powershell/module/skype/Search-CsClsLogging">Search-CsClsLogging</a>」を参照してください。


Start-CsClsLogging と対になる Stop-CsClsLogging コマンドレットは、シナリオによって定義されるログ セッションを終了し、ログ セッションによって作成されるログを保持します。2 つのシナリオは特定のコンピューターでいつでも実行できます。一方のシナリオを停止し、他方のシナリオを使用して情報を収集するという手段は、ほとんどのワークロードのトラブルシューティングで実行できる共通のタスクです。

## 関連項目

#### タスク

[集中ログ サービスの Start を使用したログのキャプチャー](lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md)  

#### 概念

[集中ログサービスの概要](lync-server-2013-overview-of-the-centralized-logging-service.md)  

#### その他のリソース

[Show-CsClsLogging](https://docs.microsoft.com/en-us/powershell/module/skype/Show-CsClsLogging)  
[Start-CsClsLogging](https://docs.microsoft.com/en-us/powershell/module/skype/Start-CsClsLogging)  
[Stop-CsClsLogging](https://docs.microsoft.com/en-us/powershell/module/skype/Stop-CsClsLogging)

