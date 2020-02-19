---
title: 'Lync Server 2013: 集中ログサービスの Stop の使用'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Stop for the Centralized Logging Service
ms:assetid: 09ac093e-8f30-4874-84b4-12548ac8c898
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687964(v=OCS.15)
ms:contentKeyID: 49733549
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f9f1c662081b5a92d53f0658859d9fdee1a038d2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138638"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-stop-for-the-centralized-logging-service-in-lync-server-2013"></a>Lync Server 2013 での集中ログサービスの Stop の使用

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-11-01_

現在実行中のログセッションは、Stop-CsClsLogging コマンドレットを使用して停止できます。 一般的に、ログセッションを停止する必要がある状況は多くありません。 たとえば、ログを検索して構成を変更するには、最初にログ記録を停止する必要はありません。 2つのシナリオ (たとえば、AlwaysOn と UserReplicator) を実行していて、認証に関連する情報を収集する必要がある場合は、その他のシナリオ (グローバル、サイト、プール、またはコンピューターのスコープ) の1つを停止してから、の実行を開始する必要があります。認証シナリオ。 詳細については、「[Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Stop-CsClsLogging)」を参照してください。

<div>


> [!NOTE]  
> 特定の展開、プール、またはコンピューターで実行できるシナリオを決定する際には、<STRONG>コンピューターごと</STRONG>に2つのシナリオを実行することに制限されていることを覚えておく必要があります。 プールのアクティビティをログに記録する場合は、1つのエンティティとしてプールを扱う必要があります。 ほとんどの場合、プール内の各コンピューターで異なるシナリオを実行することは意味がありません。 データを収集している問題を調べ、全体的な展開において特定のコンピューターで最も適したシナリオを考えてみてください。 たとえば、UserReplicator シナリオを検討した場合、エッジサーバーまたはエッジプールで UserReplicator を実行することには、非常に小さな値があります。<BR>問題とその影響が及ぶ範囲を把握したら、次は、どのコンピューターと、どのプールで、どのようなシナリオを実行するかについて慎重に検討する必要があります。AlwaysOn シナリオは各種プロバイダーについての情報を収集するため、多岐にわたるアプリケーションに対しては有効ですが、シナリオが限定的であれば、それが効果を発揮するコンピューターやプールも一部に限定されます。また、最初に特定のシナリオの価値を理解することなく、ログ セッションをランダムに開始する場合も注意が必要です。誤ったシナリオを使用していたり、タスクに適切なシナリオであるが、そのシナリオを適用するスコープ (グローバル、サイト、プール、またはコンピューター) が誤っていたりすると、ほとんど役に立たない不適切な (シナリオをまったく実行してないかのような) データが得られる可能性があります。



</div>

Lync Server 管理シェルを使用して集中ログサービスの機能を制御するには、CsAdministrator または CsServerAdministrator の役割ベースのアクセス制御 (RBAC) セキュリティグループのメンバーであるか、またはカスタムの RBAC の役割を持っている必要があります。これら2つのグループのどちらか。 このコマンドレットが割り当てられているすべての RBAC の役割 (自分で作成したカスタムの RBAC の役割を含む) の一覧を返すには、Lync Server 管理シェルまたは Windows PowerShell プロンプトから次のコマンドを実行します。

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

次に例を示します。

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<div>

## <a name="to-stop-a-currently-running-centralized-logging-service-session"></a>現在実行中の集中ログサービスセッションを停止するには

1.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

2.  集中ログサービスを照会して、現在実行されているシナリオを確認します。そのためには、次のように入力します。
    
        Show-CsClsLogging
    
    ![Show-CsCl を呼び出した後の Windows PowerShell コンソール](images/JJ687964.eb190c32-529c-4277-a731-52c47d22d8fa(OCS.15).jpg "Show-CsCl を呼び出した後の Windows PowerShell コンソール")
    
    Show-CsClsLogging の結果、現在実行中のシナリオの概要と、そのシナリオの実行スコープが表示されます。 詳細については、「[Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Show-CsClsLogging)」を参照してください。

3.  特定のシナリオによる現在実行中のログ セッションを停止するには、次のように入力します。
    
        Stop-CsClsLogging -Scenario <scenario name> -Computers <comma separated list of fully qualified computer names> -Pools <comma separated list of fully qualified pool names>
    
    次に例を示します。
    
        Stop-CsClsLogging -Scenario UserReplicator -Pools pool01.contoso.net
    
    このコマンドは、pool01.contoso.net での UserReplicatior シナリオによるログ記録を停止します。
    
    <div>
    

    > [!NOTE]  
    > UserReplicator シナリオを使用するこのログ セッション中に作成されたログは削除されません。 このログは、Search-CsClsLogging コマンドを使用して検索を実行する場合も使用できます。 詳細については、「<A href="https://docs.microsoft.com/powershell/module/skype/Search-CsClsLogging">Search-CsClsLogging</A>」を参照してください。

    
    </div>

Start-CsClsLogging と対になる Stop-CsClsLogging コマンドレットは、シナリオによって定義されるログ セッションを終了し、ログ セッションによって作成されるログを保持します。2 つのシナリオは特定のコンピューターでいつでも実行できます。一方のシナリオを停止し、他方のシナリオを使用して情報を収集するという手段は、ほとんどのワークロードのトラブルシューティングで実行できる共通のタスクです。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でログをキャプチャするための集中ログサービスの Start の使用](lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md)  


[Lync Server 2013 の集中ログサービスの概要](lync-server-2013-overview-of-the-centralized-logging-service.md)  


[Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Show-CsClsLogging)  
[Start-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Start-CsClsLogging)  
[Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Stop-CsClsLogging)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

