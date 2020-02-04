---
title: 'Lync Server 2013: 集中ログサービスに Stop を使用する'
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
ms.openlocfilehash: 621d7c02530fea62b1601c1db755292c8f819a6e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743967"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-stop-for-the-centralized-logging-service-in-lync-server-2013"></a>Lync Server 2013 の中央集中ログサービスに対して Stop を使用する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-11-01_

Stop-CsClsLogging コマンドレットを使用すると、現在実行中のログ セッションを停止できます。一般に、ログ セッションを停止しなければならない状況は多くありません。たとえば、ログを検索して構成を変更する場合も、最初にログを停止する必要はありません。例として、AlwaysOn と UserReplicator を実行する 2 つのシナリオで、Authentication に関連する情報を収集する必要がある場合を考えます。この場合、Authentication シナリオの実行を開始する前に、AlwaysOn または UserReplicator のどちらか一方のシナリオを (グローバル、サイト、プール、またはコンピューター スコープで) 停止する必要があります。詳細については、「[Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Stop-CsClsLogging)」を参照してください。

<div>


> [!NOTE]  
> 特定の展開、プール、またはコンピューターで実行できるシナリオを決定する際には、<STRONG>コンピューターごと</STRONG>に2つのシナリオを実行するように制限されていることを覚えておく必要があります。 プールにアクティビティを記録する場合は、プールを単一のエンティティとして扱う必要があります。 ほとんどの場合、プール内の各コンピューターで異なるシナリオを実行することは意味がありません。 データを収集している問題を確認し、全体的な展開で特定のコンピューターで最も意味のあるシナリオについて考えてみてください。 たとえば、UserReplicator シナリオを検討している場合は、Edge サーバーまたはエッジプールで UserReplicator を実行するだけでは、あまり意味がありません。<BR>問題とその影響が及ぶ範囲を把握したら、次は、どのコンピューターと、どのプールで、どのようなシナリオを実行するかについて慎重に検討する必要があります。AlwaysOn シナリオは各種プロバイダーについての情報を収集するため、多岐にわたるアプリケーションに対しては有効ですが、シナリオが限定的であれば、それが効果を発揮するコンピューターやプールも一部に限定されます。また、最初に特定のシナリオの価値を理解することなく、ログ セッションをランダムに開始する場合も注意が必要です。誤ったシナリオを使用していたり、タスクに適切なシナリオであるが、そのシナリオを適用するスコープ (グローバル、サイト、プール、またはコンピューター) が誤っていたりすると、ほとんど役に立たない不適切な (シナリオをまったく実行していないかのような) データが得られる可能性があります。



</div>

Lync Server 管理シェルを使用して集中ログサービス機能を制御するには、CsAdministrator または CsServerAdministrator の役割ベースのアクセス制御 (RBAC) セキュリティグループのメンバーであるか、またはこれら2つのグループのどちらかです。 このコマンドレットが割り当てられているすべての RBAC ロールの一覧を返すには (自分自身で作成したカスタム RBAC ロールを含む)、Lync Server 管理シェルまたは Windows PowerShell プロンプトから次のコマンドを実行します。

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

次に例を示します。

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<div>

## <a name="to-stop-a-currently-running-centralized-logging-service-session"></a>現在実行中の中央記録サービスセッションを停止するには

1.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

2.  次を入力して、現在実行されているシナリオを確認します。
    
        Show-CsClsLogging
    
    ![Show-CsCl 呼び出し後の Windows PowerShell コンソール](images/JJ687964.eb190c32-529c-4277-a731-52c47d22d8fa(OCS.15).jpg "Show-CsCl 呼び出し後の Windows PowerShell コンソール")
    
    Show-CsClsLogging の結果、現在実行中のシナリオの概要と、そのシナリオの実行スコープが表示されます。詳細については、「[Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Show-CsClsLogging)」を参照してください。

3.  特定のシナリオによる現在実行中のログ セッションを停止するには、次のように入力します。
    
        Stop-CsClsLogging -Scenario <scenario name> -Computers <comma separated list of fully qualified computer names> -Pools <comma separated list of fully qualified pool names>
    
    次に例を示します。
    
        Stop-CsClsLogging -Scenario UserReplicator -Pools pool01.contoso.net
    
    このコマンドは、pool01.contoso.net での UserReplicatior シナリオによるログ記録を停止します。
    
    <div>
    

    > [!NOTE]  
    > UserReplicator シナリオを使用するこのログ セッション中に作成されたログは削除されません。このログは、Search-CsClsLogging コマンドを使用して検索を実行する場合も使用できます。詳細については、「<A href="https://docs.microsoft.com/powershell/module/skype/Search-CsClsLogging">Search-CsClsLogging</A>」を参照してください。

    
    </div>

Start-CsClsLogging と対になる Stop-CsClsLogging コマンドレットは、シナリオによって定義されるログ セッションを終了し、ログ セッションによって作成されるログを保持します。2 つのシナリオは特定のコンピューターでいつでも実行できます。一方のシナリオを停止し、他方のシナリオを使用して情報を収集するという手段は、ほとんどのワークロードのトラブルシューティングで実行できる共通のタスクです。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でログをキャプチャするために、一元ログサービスの開始を使用する](lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md)  


[Lync Server 2013 の一元管理されたログサービスの概要](lync-server-2013-overview-of-the-centralized-logging-service.md)  


[[表示]-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Show-CsClsLogging)  
[スタート-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Start-CsClsLogging)  
[は、CsClsLogging の停止](https://docs.microsoft.com/powershell/module/skype/Stop-CsClsLogging)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

