---
title: Skype for Business Server 2015 での CLS ログ キャプチャの開始または停止
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0512b9ce-7f5b-48eb-a79e-f3498bacf2de
description: '概要: Skype for Business Server 2015 で集中ログ サービスのログ キャプチャ セッションを開始または停止する方法について学習します。'
ms.openlocfilehash: cd6864b0d4d16e952f93fe321b49522028d76e5b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49835137"
---
# <a name="start-or-stop-cls-log-capture-in-skype-for-business-server-2015"></a><span data-ttu-id="9f839-103">Skype for Business Server 2015 での CLS ログ キャプチャの開始または停止</span><span class="sxs-lookup"><span data-stu-id="9f839-103">Start or stop CLS log capture in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="9f839-104">**概要:** Skype for Business Server 2015 で集中ログ サービスログ キャプチャ セッションを開始または停止する方法について学習します。</span><span class="sxs-lookup"><span data-stu-id="9f839-104">**Summary:** Learn how to start or stop a Centralized Logging Service log capture session in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="9f839-105">集中ログ サービスを使用してトレース ログを取得するには、1 つ以上のコンピューターとプールでログ記録を開始するコマンドを発行します。</span><span class="sxs-lookup"><span data-stu-id="9f839-105">To capture trace logs using the Centralized Logging Service, you issue a command to begin logging on one or more computers and pools.</span></span> <span data-ttu-id="9f839-106">また、実行するコンピューターまたはプール、実行するシナリオ (AlwaysOn、別の定義済みシナリオ、作成したシナリオなど)、トレースする Skype for Business Server コンポーネント (S4、SipStack など) を定義するパラメーターも発行します。</span><span class="sxs-lookup"><span data-stu-id="9f839-106">You also issue parameters that define which computers or pools, what scenarios to run (for example, AlwaysOn, another predefined scenario, or a scenario you have created), what Skype for Business Server components (for example, S4, SipStack) to trace.</span></span>
  
<span data-ttu-id="9f839-107">適切な情報を取得するには、適切なシナリオを使用して問題に関連する情報を収集する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f839-107">To capture the right information, you need to make sure you use the right scenario to collect information that is relevant to the problem.</span></span> <span data-ttu-id="9f839-108">集中ログ サービスのシナリオでは、サーバー コンポーネント、ログ レベル、フラグのコレクションに基づいてログを有効にする概念が考えら、サーバー単位でこれらの要素を定義するよりも効率的で便利です。</span><span class="sxs-lookup"><span data-stu-id="9f839-108">In the Centralized Logging Service, a scenario is the concept of turning logging on based on a collection of server components, logging levels, and flags, which is much more efficient and useful than having to define these elements on a per-server basis.</span></span> <span data-ttu-id="9f839-109">実行するシナリオを定義して指定すると、シナリオはインフラストラクチャの範囲内のすべてのサーバーとプールで一貫して実行されます。</span><span class="sxs-lookup"><span data-stu-id="9f839-109">You define and specify a scenario to run and the scenario is run consistently across all servers and pools in the scope of the infrastructure.</span></span>
  
<span data-ttu-id="9f839-p103">既定のシナリオは、**AlwaysOn** です。AlwaysOn シナリオのねらいは、その名前が示すとおり、シナリオを絶えず実行することです。AlwaysOn シナリオでは、最も一般的なサーバー コンポーネントの多くについて Info レベルの情報 (Info ログ レベルには、Info のメッセージ以外に、Fatal、Error、および Warning の各メッセージも含まれます) が収集されます。AlwaysOn での情報の収集は、問題が発生する前後と問題の発生中に行われます。この点は、OCSLogger のような以前のログ記録ツールの標準的な動作とは大きく異なります。既に問題が発生した後に OCSLogger を実行すると、得られるデータが予防的なものではなく対症療法的なものになるので、トラブルシューティングの作業が困難になります。AlwaysOn では、問題のコンポーネントを特定するために探し求めている情報が得られず、(幅広い AlwaysOn のプロバイダーに与えられる可能性が低い) そのコンポーネントの修正手順が示されない場合も、ほかに行う必要があること (新しいシナリオの作成、その他の情報の収集、より焦点を絞った詳細情報を収集するための別の検索の実行など) を判断するのに適切なレベルの情報が示されます。</span><span class="sxs-lookup"><span data-stu-id="9f839-p103">The default scenario is called **AlwaysOn**. The intended purpose for AlwaysOn is to run the scenario constantly, as the name of the scenario implies. The AlwaysOn scenario collects Info level information (note that Info logging level includes Fatal, Error, and Warning in addition to Info messages) for many of the most common server components. AlwaysOn collects information before, during, and after a problem occurs. This differs dramatically from the typical behavior of previous logging tools such as OCSLogger. You ran OCSLogger after the problem had already occurred, making your troubleshooting efforts more difficult because the data that you have is reactive, not proactive. If AlwaysOn does not contain the information that you are looking for in order to point to the problem component and indicate a course of action to fix it (which is not likely given the breadth and depth of providers in AlwaysOn), it will indicate a reasonable level of information to determine what else you need to do, such as creating a new scenario, gather other information, run a different search to collect more focused details, and so on.</span></span>
  
<span data-ttu-id="9f839-117">集中ログ サービスには、コマンドを発行する 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="9f839-117">The Centralized Logging Service provides two ways to issue commands.</span></span> <span data-ttu-id="9f839-118">多くのトピックでは、Skype for Business Server 管理シェルをWindows PowerShellを使用する方法に重点が置かまれています。</span><span class="sxs-lookup"><span data-stu-id="9f839-118">A number of topics have been focused squarely on using Windows PowerShell through the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="9f839-119">多数の複雑な構成とコマンドを使用する機能は、集中ログ Windows PowerShell使用する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="9f839-119">The ability to use a number of complex configurations and commands favors Windows PowerShell for Centralized Logging Service use.</span></span> <span data-ttu-id="9f839-120">Skype for Business Server Windows PowerShell管理シェルを使用する機能は Skype for Business Server のすべての機能に対してほぼ一般的なので、Windows PowerShell コマンドについてのみ説明します。</span><span class="sxs-lookup"><span data-stu-id="9f839-120">Because Windows PowerShell through the Skype for Business Server Management Shell is nearly ubiquitous for all functions in Skype for Business Server, only the Windows PowerShell commands are discussed.</span></span> 
  
### <a name="to-run-start-csclslogging-with-windows-powershell-using-basic-commands"></a><span data-ttu-id="9f839-121">基本コマンドをStart-CsClsLoggingしてWindows PowerShellを実行するには</span><span class="sxs-lookup"><span data-stu-id="9f839-121">To run Start-CsClsLogging with Windows PowerShell using basic commands</span></span>

1. <span data-ttu-id="9f839-122">Skype for Business Server 管理シェルを起動します。[スタート] ボタン、[すべてのプログラム] の順にクリックし **、[Skype for Business 2015]** をクリックして **、[Skype for Business Server 管理シェル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9f839-122">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="9f839-123">次のように入力して、集中ログ サービスを使用してログシナリオを開始します。</span><span class="sxs-lookup"><span data-stu-id="9f839-123">Start a logging scenario with the Centralized Logging Service by typing the following:</span></span>
    
   ```PowerShell
   Start-CsClsLogging -Scenario <name of scenario>
   ```

    <span data-ttu-id="9f839-124">たとえば、**AlwaysOn** シナリオを開始するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="9f839-124">For example, to start the **AlwaysOn** scenario, type:</span></span>
    
   ```PowerShell
   Start-CsClsLogging -Scenario AlwaysOn
   ```

    > [!NOTE]
    > <span data-ttu-id="9f839-125">AlwaysOn シナリオには、既定の実行期間がありません。</span><span class="sxs-lookup"><span data-stu-id="9f839-125">The AlwaysOn scenario has no default duration.</span></span> <span data-ttu-id="9f839-126">このシナリオの実行は、**Stop-CsClsLogging** コマンドレットによって明示的に停止されるまで続きます。</span><span class="sxs-lookup"><span data-stu-id="9f839-126">This scenario will run until you explicitly stop it with the **Stop-CsClsLogging** cmdlet.</span></span> <span data-ttu-id="9f839-127">詳細については、「[Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9f839-127">For details, see [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps).</span></span> <span data-ttu-id="9f839-128">その他すべてのシナリオでは、既定の実行期間が 4 時間になっています。</span><span class="sxs-lookup"><span data-stu-id="9f839-128">For all other scenarios, the default duration is 4 hours.</span></span> 
  
3. <span data-ttu-id="9f839-129">Enter キーを押して、コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9f839-129">Press Enter to run the command.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="9f839-130">このコマンドを実行して展開内のコンピューターから状態を取得するには、いくらかの時間 (30 ～ 60 秒) がかかることがあります。</span><span class="sxs-lookup"><span data-stu-id="9f839-130">It may take a short amount of time (30 to 60 seconds) for the commands to run and to receive the status back from the computers in your deployment.</span></span> 
  
     ![Start-CsClsLogging の実行。](../../media/Ops_CLS_Show_and_Start_ClsLogging.jpg)
  
4. <span data-ttu-id="9f839-132">別のシナリオを開始するには、次のように **Start-CsClsLogging** コマンドレットを使用して実行する追加シナリオの名前を指定します (以下は **Authentication** シナリオの場合)。</span><span class="sxs-lookup"><span data-stu-id="9f839-132">To start another scenario, use the **Start-CsClsLogging** cmdlet with the name of the additional scenario to run as follows (for example, the scenario **Authentication**):</span></span>
    
   ```PowerShell
   Start-CsClsLogging -Scenario Authentication
   ```

    > [!IMPORTANT]
    > <span data-ttu-id="9f839-133">それぞれのコンピューターで一度に実行できるシナリオは、合計 2 つまでです。</span><span class="sxs-lookup"><span data-stu-id="9f839-133">You can have a total of two scenarios running on any given computer at any time.</span></span> <span data-ttu-id="9f839-134">コマンドのスコープがグローバルの場合は、展開内のすべてのコンピューターで (1 つまたは 2 つの) シナリオが実行されます。</span><span class="sxs-lookup"><span data-stu-id="9f839-134">If the command is global in scope, all of the computers in your deployment will run the scenario or scenarios.</span></span> <span data-ttu-id="9f839-135">3 番目のシナリオを開始するには、その新しいシナリオを実行するコンピューター、プール、サイト、またはグローバルのスコープでログ記録を停止する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f839-135">To start a third scenario, you must stop logging on the computer, pool, site, or global scope that you want to run the new scenario on.</span></span> <span data-ttu-id="9f839-136">グローバル スコープでシナリオが開始されている場合は、1 つ以上のコンピューターおよびプールでそうしたシナリオのどちらかまたは両方のログ記録を停止できます。</span><span class="sxs-lookup"><span data-stu-id="9f839-136">If you have started a global scope, you can stop logging for one or both of the scenarios on one or more computers and pools.</span></span> 
  
### <a name="to-run-start-csclslogging-with-windows-powershell-using-advanced-commands"></a><span data-ttu-id="9f839-137">高度なコマンドをStart-CsClsLoggingしてWindows PowerShellを実行するには</span><span class="sxs-lookup"><span data-stu-id="9f839-137">To run Start-CsClsLogging with Windows PowerShell using advanced commands</span></span>

1. <span data-ttu-id="9f839-138">Skype for Business Server 管理シェルを起動します。[スタート] ボタン、[すべてのプログラム] の順にクリックし **、[Skype for Business 2015]** をクリックして **、[Skype for Business Server 管理シェル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9f839-138">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="9f839-139">追加のパラメーターを使用して、このログ記録コマンドを管理できます。</span><span class="sxs-lookup"><span data-stu-id="9f839-139">Additional parameters are available to manage the logging commands.</span></span> <span data-ttu-id="9f839-140">-Duration を使用すると、シナリオを実行する時間の長さを調整できます。</span><span class="sxs-lookup"><span data-stu-id="9f839-140">You can use -Duration to adjust the length of time for the scenario to run.</span></span> <span data-ttu-id="9f839-141">また、-Computers、コンマで区切られたコンピューターの完全修飾ドメイン名 (FQDN) の一覧、またはログオンを実行するプールの FQDN のコンマ区切りリストである -Pools を定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="9f839-141">You also can define -Computers, a list of computer fully qualified domain names (FQDNs) separated by a comma, or -Pools, a comma separated list of FQDNs for pools that you want to run logging on.</span></span>
    
    <span data-ttu-id="9f839-142">UserReplicator シナリオのログ セッションは、プール "pool01.contoso.net" で開始します。</span><span class="sxs-lookup"><span data-stu-id="9f839-142">You start a logging session for the UserReplicator scenario on the pool "pool01.contoso.net".</span></span> <span data-ttu-id="9f839-143">また、このログ セッションの期間を 8 時間に指定します。</span><span class="sxs-lookup"><span data-stu-id="9f839-143">You also define the duration of the logging session at 8 hours.</span></span> <span data-ttu-id="9f839-144">この場合、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="9f839-144">To do this, type:</span></span>
    
   ```PowerShell
   Start-CsClsLogging -Scenario UserReplicator -Duration 8:00 -Pools "pool01.contoso.net"
   ```

    <span data-ttu-id="9f839-145">このシナリオが正常に実行されると、次のような結果が返されます。</span><span class="sxs-lookup"><span data-stu-id="9f839-145">The successful execution of this scenario returns a result like the following:</span></span>
    
     ![Start-CsClsLogging の実行。](../../media/Ops_CsClsLogging_UserReplicator_Exp.jpg)
  
<span data-ttu-id="9f839-147">この例では、AlwaysOn シナリオと UserReplicator シナリオが実行中であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="9f839-147">Note that in this example, the AlwaysOn scenario is running and the UserReplicator scenario is running.</span></span> 
    
## <a name="stop-the-centralized-logging-service-log-capture"></a><span data-ttu-id="9f839-148">集中ログ サービスのログ キャプチャを停止する</span><span class="sxs-lookup"><span data-stu-id="9f839-148">Stop the Centralized Logging Service log capture</span></span>
<span data-ttu-id="9f839-149"><a name="stop"> </a></span><span class="sxs-lookup"><span data-stu-id="9f839-149"><a name="stop"> </a></span></span>

<span data-ttu-id="9f839-150">このコマンドレットを使用して、現在実行中のログ セッションStop-CsClsLoggingできます。</span><span class="sxs-lookup"><span data-stu-id="9f839-150">You can stop a currently running logging session with the Stop-CsClsLogging cmdlet.</span></span> <span data-ttu-id="9f839-151">通常、ログ セッションを停止する必要がある状況はそれほど多くはない。</span><span class="sxs-lookup"><span data-stu-id="9f839-151">Generally, there aren't many situations in which you would need to stop a logging session.</span></span> <span data-ttu-id="9f839-152">たとえば、最初にログを停止することなく、ログを検索して構成を変更できます。</span><span class="sxs-lookup"><span data-stu-id="9f839-152">For example, you can search logs and change configurations without first needing to stop logging.</span></span> <span data-ttu-id="9f839-153">AlwaysOn や UserReplicator などの 2 つのシナリオが実行されている場合、認証に関連する情報を収集する必要がある場合は、認証シナリオの実行を開始する前に、他のシナリオ (グローバル スコープ、サイト スコープ、プール スコープ、またはコンピューター スコープ) のいずれかを停止する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f839-153">If you have two scenarios running, for example AlwaysOn and UserReplicator, and you need to collect information related to Authentication, you will need to stop one of the other scenarios (at a global, site, pool or computer scope) before you can start running to Authentication scenario.</span></span> <span data-ttu-id="9f839-154">詳細については、「[Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9f839-154">For details, see [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps).</span></span>
  
> [!NOTE]
> <span data-ttu-id="9f839-155">特定の展開、プール、またはコンピューターで実行できるシナリオを決定する場合は、AlwaysOn と 1 つのカスタムシナリオという 2 つのシナリオをコンピューターごとに実行できる点に注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f839-155">When determining what scenarios you can run on a given deployment, pool or computer, you need to remember that you are limited to running two scenarios **per computer**: AlwaysOn and one custom scenario.</span></span> <span data-ttu-id="9f839-156">プールのアクティビティをログに記録する場合は、プールを単一のエンティティとして扱う必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f839-156">If you are logging activity on a pool, you should treat a pool as a single entity.</span></span> <span data-ttu-id="9f839-157">ほとんどの場合、プール内の各コンピューターで異なるシナリオを実行しても意味がありません。</span><span class="sxs-lookup"><span data-stu-id="9f839-157">In most cases, it would not make sense to run different scenarios on each computer in a pool.</span></span> <span data-ttu-id="9f839-158">データを収集している問題を見て、展開全体で特定のコンピューターで最も意味のあるシナリオについて考えるのは理にかなっています。</span><span class="sxs-lookup"><span data-stu-id="9f839-158">It does make sense to look at the problem that you are collecting data about and think about what scenario makes the most sense on a given computer in the overall deployment.</span></span> <span data-ttu-id="9f839-159">たとえば、UserReplicator シナリオを考える場合、エッジ サーバーまたはエッジ プールで UserReplicator を実行する価値はほとんどない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9f839-159">For example, if you consider the UserReplicator scenario, there would be very little value in running UserReplicator on an Edge Server or Edge pool.</span></span> 
  
<span data-ttu-id="9f839-p111">問題とその影響が及ぶ範囲を把握したら、次は、どのコンピューターと、どのプールで、どのようなシナリオを実行するかについて慎重に検討する必要があります。AlwaysOn シナリオは各種プロバイダーについての情報を収集するため、多岐にわたるアプリケーションに対しては有効ですが、シナリオが限定的であれば、それが効果を発揮するコンピューターやプールも一部に限定されます。また、最初に特定のシナリオの価値を理解することなく、ログ セッションをランダムに開始する場合も注意が必要です。誤ったシナリオを使用していたり、タスクに適切なシナリオであるが、そのシナリオを適用するスコープ (グローバル、サイト、プール、またはコンピューター) が誤っていたりすると、ほとんど役に立たない不適切な (シナリオをまったく実行してないかのような) データが得られる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9f839-p111">After you understand the problem and the scope of the impact, you should make careful choices about what scenarios to run on which computers and pools. While the AlwaysOn scenario makes sense for a wide scope application because it collects information on a wide variety of providers, specific scenarios only have application value on specific computers or pools. Also, you should take caution when randomly starting up a logging session without first understanding the value of a given scenario. If you use the wrong scenario, or if you use a scenario that is appropriate for the task and you apply the scenario at the wrong scope (be it global, site, pool, or computer), you can get questionable data that is not very useful—as if you didn't run the scenario at all.</span></span>
  
<span data-ttu-id="9f839-164">Skype for Business Server 管理シェルを使用して集中ログ サービス機能を制御するには、CsAdministrator または CsServerAdministrator の役割ベースのアクセス制御 (RBAC) セキュリティ グループのメンバーか、これら 2 つのグループのいずれかを含むカスタム RBAC の役割のメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f839-164">To control the Centralized Logging Service functions by using the Skype for Business Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="9f839-165">このコマンドレットが割り当てられているすべての RBAC の役割 (自身が作成したカスタムの RBAC の役割を含む) の一覧を戻す場合は、Skype for Business Server 管理シェルまたは Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9f839-165">To return a list of all the RBAC roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Skype for Business Server Management Shell or the Windows PowerShell prompt:</span></span>
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

<span data-ttu-id="9f839-166">例:</span><span class="sxs-lookup"><span data-stu-id="9f839-166">For example:</span></span>
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

> [!NOTE]
> <span data-ttu-id="9f839-167">ログを有効にしたのですが、ログはどこに保存されますか?</span><span class="sxs-lookup"><span data-stu-id="9f839-167">So you may be wondering: Now that you've enabled logging, where are the logs kept?</span></span> <span data-ttu-id="9f839-168">CLS エージェントに送信される管理シェル クエリを使用してログに格納されている情報にアクセスし、結果をいくつかのファイル形式に出力できます。各サーバーでは、CLS エージェントがレコードを保持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f839-168">Since you'll access the information stored in the logs using management shell queries sent to the CLS Agents, and you can output the results to several possible file formats, where on each server a CLS Agent keeps its records isn't actually important to know.</span></span>  <span data-ttu-id="9f839-169">ログ ファイルは、Snooper.exeやテキスト ファイルを読み取り可能なツール **(Notepad.exe** など) など、さまざまなツールを使用して、指定した場所に保存し、読み取りおよび分析 **できます**。</span><span class="sxs-lookup"><span data-stu-id="9f839-169">The log files can be saved to a location you specify and  read and analyzed using a variety of tools, including **Snooper.exe** and any tool that can read a text file, such as **Notepad.exe**.</span></span> <span data-ttu-id="9f839-170">Snooper.exe Skype for Business Server 2015 デバッグ ツールの一部であり、Web ダウンロードとして [利用できます](https://go.microsoft.com/fwlink/p/?LinkId=285257)。</span><span class="sxs-lookup"><span data-stu-id="9f839-170">Snooper.exe is part of the Skype for Business Server 2015 Debug Tools and is available as a [Web download](https://go.microsoft.com/fwlink/p/?LinkId=285257).</span></span>

### <a name="to-stop-a-currently-running-centralized-logging-service-session"></a><span data-ttu-id="9f839-171">現在実行中の集中ログ サービス セッションを停止するには</span><span class="sxs-lookup"><span data-stu-id="9f839-171">To stop a currently running Centralized Logging Service session</span></span>

1. <span data-ttu-id="9f839-172">Skype for Business Server 管理シェルを起動します。[スタート] ボタン、[すべてのプログラム] の順にクリックし **、[Skype for Business 2015]** をクリックして **、[Skype for Business Server 管理シェル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9f839-172">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="9f839-173">集中ログ サービスに対してクエリを実行し、現在実行されているシナリオを確認するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="9f839-173">Query the Centralized Logging Service to find out what scenarios are currently running by typing the following:</span></span>
    
   ```PowerShell
   Show-CsClsLogging
   ```

   ![Windows PowerShell呼び出した後にコンソールをShow-CsCl](../../media/Ops_Show_Stop_CsClsLogging.jpg)
  
   <span data-ttu-id="9f839-175">Show-CsClsLogging の結果、現在実行中のシナリオの概要と、そのシナリオの実行スコープが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9f839-175">The result of Show-CsClsLogging is a summary of the scenarios that are running and what scope they are running in.</span></span> <span data-ttu-id="9f839-176">詳細については、「[Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9f839-176">For details, see [Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps).</span></span>
    
3. <span data-ttu-id="9f839-177">特定のシナリオによる現在実行中のログ セッションを停止するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="9f839-177">To stop a currently running logging session with a specific scenario, type:</span></span>
    
   ```PowerShell
   Stop-CsClsLogging -Scenario <scenario name> -Computers <comma separated list of fully qualified computer names> -Pools <comma separated list of fully qualified pool names>
   ```
   <span data-ttu-id="9f839-178">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="9f839-178">For example:</span></span>
    
   ```PowerShell
   Stop-CsClsLogging -Scenario UserReplicator -Pools pool01.contoso.net
   ```

   <span data-ttu-id="9f839-179">このコマンドは、pool01.contoso.net での UserReplicatior シナリオによるログ記録を停止します。</span><span class="sxs-lookup"><span data-stu-id="9f839-179">This command will stop logging with the UserReplicatior scenario on pool01.contoso.net.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9f839-180">UserReplicator シナリオを使用するこのログ セッション中に作成されたログは削除されません。</span><span class="sxs-lookup"><span data-stu-id="9f839-180">Logs created during this logging session using the UserReplicator scenario are not deleted.</span></span> <span data-ttu-id="9f839-181">このログは、Search-CsClsLogging コマンドを使用して検索を実行する場合も使用できます。</span><span class="sxs-lookup"><span data-stu-id="9f839-181">The logging is still available for you to execute searches against using the Search-CsClsLogging command.</span></span> <span data-ttu-id="9f839-182">詳細については、「[Search-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9f839-182">For details, see [Search-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps).</span></span> 
  
<span data-ttu-id="9f839-p116">Start-CsClsLogging と対になる Stop-CsClsLogging コマンドレットは、シナリオによって定義されるログ セッションを終了し、ログ セッションによって作成されるログを保持します。2 つのシナリオは特定のコンピューターでいつでも実行できます。一方のシナリオを停止し、他方のシナリオを使用して情報を収集するという手段は、ほとんどのワークロードのトラブルシューティングで実行できる共通のタスクです。</span><span class="sxs-lookup"><span data-stu-id="9f839-p116">Acting as the companion command to Start-CsClsLogging, the Stop-CsClsLogging cmdlet ends the logging session, defined by scenarios, and retains the logs created by the logging session. You can run two scenarios on a given computer at any time. The method of stopping one scenario to gather information using another scenario is a common task that you can perform during most workload troubleshooting.</span></span>
## <a name="see-also"></a><span data-ttu-id="9f839-186">関連項目</span><span class="sxs-lookup"><span data-stu-id="9f839-186">See also</span></span>
<span data-ttu-id="9f839-187"><a name="stop"> </a></span><span class="sxs-lookup"><span data-stu-id="9f839-187"><a name="stop"> </a></span></span>

[<span data-ttu-id="9f839-188">Skype for Business 2015 の集中ログ サービス</span><span class="sxs-lookup"><span data-stu-id="9f839-188">Centralized Logging Service in Skype for Business 2015</span></span>](centralized-logging-service.md)
