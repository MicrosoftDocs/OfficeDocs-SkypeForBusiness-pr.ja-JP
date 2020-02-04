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

# <a name="using-stop-for-the-centralized-logging-service-in-lync-server-2013"></a><span data-ttu-id="3877f-102">Lync Server 2013 の中央集中ログサービスに対して Stop を使用する</span><span class="sxs-lookup"><span data-stu-id="3877f-102">Using Stop for the Centralized Logging Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3877f-103">_**最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="3877f-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="3877f-p101">Stop-CsClsLogging コマンドレットを使用すると、現在実行中のログ セッションを停止できます。一般に、ログ セッションを停止しなければならない状況は多くありません。たとえば、ログを検索して構成を変更する場合も、最初にログを停止する必要はありません。例として、AlwaysOn と UserReplicator を実行する 2 つのシナリオで、Authentication に関連する情報を収集する必要がある場合を考えます。この場合、Authentication シナリオの実行を開始する前に、AlwaysOn または UserReplicator のどちらか一方のシナリオを (グローバル、サイト、プール、またはコンピューター スコープで) 停止する必要があります。詳細については、「[Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Stop-CsClsLogging)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3877f-p101">You can stop a currently running logging session with the Stop-CsClsLogging cmdlet. Generally, there aren’t many situations in which you would need to stop a logging session. For example, you can search logs and change configurations without first needing to stop logging. If you have two scenarios running, for example AlwaysOn and UserReplicator, and you need to collect information related to Authentication, you will need to stop one of the other scenarios (at a global, site, pool or computer scope) before you can start running to Authentication scenario. For details, see [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Stop-CsClsLogging).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3877f-109">特定の展開、プール、またはコンピューターで実行できるシナリオを決定する際には、<STRONG>コンピューターごと</STRONG>に2つのシナリオを実行するように制限されていることを覚えておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="3877f-109">When determining what scenarios you can run on a given deployment, pool or computer, you need to remember that you are limited to running two scenarios <STRONG>per computer</STRONG>.</span></span> <span data-ttu-id="3877f-110">プールにアクティビティを記録する場合は、プールを単一のエンティティとして扱う必要があります。</span><span class="sxs-lookup"><span data-stu-id="3877f-110">If you are logging activity on a pool, you should treat a pool as a single entity.</span></span> <span data-ttu-id="3877f-111">ほとんどの場合、プール内の各コンピューターで異なるシナリオを実行することは意味がありません。</span><span class="sxs-lookup"><span data-stu-id="3877f-111">In most cases, it would not make sense to run different scenarios on each computer in a pool.</span></span> <span data-ttu-id="3877f-112">データを収集している問題を確認し、全体的な展開で特定のコンピューターで最も意味のあるシナリオについて考えてみてください。</span><span class="sxs-lookup"><span data-stu-id="3877f-112">It does make sense to look at the problem that you are collecting data about and think about what scenario makes the most sense on a given computer in the overall deployment.</span></span> <span data-ttu-id="3877f-113">たとえば、UserReplicator シナリオを検討している場合は、Edge サーバーまたはエッジプールで UserReplicator を実行するだけでは、あまり意味がありません。</span><span class="sxs-lookup"><span data-stu-id="3877f-113">For example, if you consider the UserReplicator scenario, there would be very little value in running UserReplicator on an Edge Server or Edge pool.</span></span><BR><span data-ttu-id="3877f-p103">問題とその影響が及ぶ範囲を把握したら、次は、どのコンピューターと、どのプールで、どのようなシナリオを実行するかについて慎重に検討する必要があります。AlwaysOn シナリオは各種プロバイダーについての情報を収集するため、多岐にわたるアプリケーションに対しては有効ですが、シナリオが限定的であれば、それが効果を発揮するコンピューターやプールも一部に限定されます。また、最初に特定のシナリオの価値を理解することなく、ログ セッションをランダムに開始する場合も注意が必要です。誤ったシナリオを使用していたり、タスクに適切なシナリオであるが、そのシナリオを適用するスコープ (グローバル、サイト、プール、またはコンピューター) が誤っていたりすると、ほとんど役に立たない不適切な (シナリオをまったく実行していないかのような) データが得られる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3877f-p103">After you understand the problem and the scope of the impact, you should make careful choices about what scenarios to run on which computers and pools. While the AlwaysOn scenario makes sense for a wide scope application because it collects information on a wide variety of providers, specific scenarios only have application value on specific computers or pools. Also, you should take caution when randomly starting up a logging session without first understanding the value of a given scenario. If you use the wrong scenario, or if you use a scenario that is appropriate for the task and you apply the scenario at the wrong scope (be it global, site, pool, or computer), you can get questionable data that is not very useful—as if you didn't run the scenario at all.</span></span>



</div>

<span data-ttu-id="3877f-118">Lync Server 管理シェルを使用して集中ログサービス機能を制御するには、CsAdministrator または CsServerAdministrator の役割ベースのアクセス制御 (RBAC) セキュリティグループのメンバーであるか、またはこれら2つのグループのどちらかです。</span><span class="sxs-lookup"><span data-stu-id="3877f-118">To control the Centralized Logging Service functions by using the Lync Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="3877f-119">このコマンドレットが割り当てられているすべての RBAC ロールの一覧を返すには (自分自身で作成したカスタム RBAC ロールを含む)、Lync Server 管理シェルまたは Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="3877f-119">To return a list of all the RBAC roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Lync Server Management Shell or the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

<span data-ttu-id="3877f-120">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="3877f-120">For example:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<div>

## <a name="to-stop-a-currently-running-centralized-logging-service-session"></a><span data-ttu-id="3877f-121">現在実行中の中央記録サービスセッションを停止するには</span><span class="sxs-lookup"><span data-stu-id="3877f-121">To stop a currently running Centralized Logging Service session</span></span>

1.  <span data-ttu-id="3877f-122">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="3877f-122">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="3877f-123">次を入力して、現在実行されているシナリオを確認します。</span><span class="sxs-lookup"><span data-stu-id="3877f-123">Query the Centralized Logging Service to find out what scenarios are currently running by typing the following:</span></span>
    
        Show-CsClsLogging
    
    <span data-ttu-id="3877f-124">![Show-CsCl 呼び出し後の Windows PowerShell コンソール](images/JJ687964.eb190c32-529c-4277-a731-52c47d22d8fa(OCS.15).jpg "Show-CsCl 呼び出し後の Windows PowerShell コンソール")</span><span class="sxs-lookup"><span data-stu-id="3877f-124">![Windows PowerShell console after calling Show-CsCl](images/JJ687964.eb190c32-529c-4277-a731-52c47d22d8fa(OCS.15).jpg "Windows PowerShell console after calling Show-CsCl")</span></span>
    
    <span data-ttu-id="3877f-p105">Show-CsClsLogging の結果、現在実行中のシナリオの概要と、そのシナリオの実行スコープが表示されます。詳細については、「[Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Show-CsClsLogging)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3877f-p105">The result of Show-CsClsLogging is a summary of the scenarios that are running and what scope they are running in. For details, see [Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Show-CsClsLogging).</span></span>

3.  <span data-ttu-id="3877f-127">特定のシナリオによる現在実行中のログ セッションを停止するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="3877f-127">To stop a currently running logging session with a specific scenario, type:</span></span>
    
        Stop-CsClsLogging -Scenario <scenario name> -Computers <comma separated list of fully qualified computer names> -Pools <comma separated list of fully qualified pool names>
    
    <span data-ttu-id="3877f-128">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="3877f-128">For example:</span></span>
    
        Stop-CsClsLogging -Scenario UserReplicator -Pools pool01.contoso.net
    
    <span data-ttu-id="3877f-129">このコマンドは、pool01.contoso.net での UserReplicatior シナリオによるログ記録を停止します。</span><span class="sxs-lookup"><span data-stu-id="3877f-129">This command will stop logging with the UserReplicatior scenario on pool01.contoso.net.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3877f-p106">UserReplicator シナリオを使用するこのログ セッション中に作成されたログは削除されません。このログは、Search-CsClsLogging コマンドを使用して検索を実行する場合も使用できます。詳細については、「<A href="https://docs.microsoft.com/powershell/module/skype/Search-CsClsLogging">Search-CsClsLogging</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3877f-p106">Logs created during this logging session using the UserReplicator scenario are not deleted. The logging is still available for you to execute searches against using the Search-CsClsLogging command. For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Search-CsClsLogging">Search-CsClsLogging</A>.</span></span>

    
    </div>

<span data-ttu-id="3877f-p107">Start-CsClsLogging と対になる Stop-CsClsLogging コマンドレットは、シナリオによって定義されるログ セッションを終了し、ログ セッションによって作成されるログを保持します。2 つのシナリオは特定のコンピューターでいつでも実行できます。一方のシナリオを停止し、他方のシナリオを使用して情報を収集するという手段は、ほとんどのワークロードのトラブルシューティングで実行できる共通のタスクです。</span><span class="sxs-lookup"><span data-stu-id="3877f-p107">Acting as the companion command to Start-CsClsLogging, the Stop-CsClsLogging cmdlet ends the logging session, defined by scenarios, and retains the logs created by the logging session. You can run two scenarios on a given computer at any time. The method of stopping one scenario to gather information using another scenario is a common task that you can perform during most workload troubleshooting.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3877f-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="3877f-136">See Also</span></span>


[<span data-ttu-id="3877f-137">Lync Server 2013 でログをキャプチャするために、一元ログサービスの開始を使用する</span><span class="sxs-lookup"><span data-stu-id="3877f-137">Using Start for the Centralized Logging Service to capture logs in Lync Server 2013</span></span>](lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md)  


[<span data-ttu-id="3877f-138">Lync Server 2013 の一元管理されたログサービスの概要</span><span class="sxs-lookup"><span data-stu-id="3877f-138">Overview of the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-centralized-logging-service.md)  


<span data-ttu-id="3877f-139">[[表示]-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Show-CsClsLogging)</span><span class="sxs-lookup"><span data-stu-id="3877f-139">[Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Show-CsClsLogging)</span></span>  
[<span data-ttu-id="3877f-140">スタート-CsClsLogging</span><span class="sxs-lookup"><span data-stu-id="3877f-140">Start-CsClsLogging</span></span>](https://docs.microsoft.com/powershell/module/skype/Start-CsClsLogging)  
[<span data-ttu-id="3877f-141">は、CsClsLogging の停止</span><span class="sxs-lookup"><span data-stu-id="3877f-141">Stop-CsClsLogging</span></span>](https://docs.microsoft.com/powershell/module/skype/Stop-CsClsLogging)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

