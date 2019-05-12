---
title: Skype for Business Server 2015 での CLS ログ キャプチャの開始または終了
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0512b9ce-7f5b-48eb-a79e-f3498bacf2de
description: '概要: 開始またはビジネス サーバー 2015 の Skype のログ サービスの一元的なログのキャプチャ セッションを停止する方法を説明します。'
ms.openlocfilehash: 83c65d8bad89e8b5314ea2f76b07c6c3016a7dd0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33915067"
---
# <a name="start-or-stop-cls-log-capture-in-skype-for-business-server-2015"></a><span data-ttu-id="ab58a-103">Skype for Business Server 2015 での CLS ログ キャプチャの開始または終了</span><span class="sxs-lookup"><span data-stu-id="ab58a-103">Start or stop CLS log capture in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="ab58a-104">**の概要:** 開始またはビジネス サーバー 2015 の Skype のログ サービスの一元的なログのキャプチャ セッションを停止する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-104">**Summary:** Learn how to start or stop a Centralized Logging Service log capture session in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="ab58a-105">集中ログ サービスを使用してトレース ログをキャプチャするには、コンピューターとプールの 1 つまたは複数のログを記録するコマンドを発行します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-105">To capture trace logs using the Centralized Logging Service, you issue a command to begin logging on one or more computers and pools.</span></span> <span data-ttu-id="ab58a-106">どのコンピューターまたはプールを AlwaysOn、別の事前定義されたシナリオでは、やなどを作成した場合)、実行するには、どのようなシナリオを定義するパラメーターも発行するビジネス サーバー コンポーネント (たとえば、S4、SipStack) をトレースするのには、どのような Skype。</span><span class="sxs-lookup"><span data-stu-id="ab58a-106">You also issue parameters that define which computers or pools, what scenarios to run (for example, AlwaysOn, another predefined scenario, or a scenario you have created), what Skype for Business Server components (for example, S4, SipStack) to trace.</span></span>
  
<span data-ttu-id="ab58a-107">適切な情報をキャプチャするには、問題に関連する情報を収集するために右のシナリオを使用するかどうかを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab58a-107">To capture the right information, you need to make sure you use the right scenario to collect information that is relevant to the problem.</span></span> <span data-ttu-id="ab58a-108">集中ログ サービスのシナリオは、ログの有効化サーバー コンポーネント、ログ レベル、およびフラグのコレクションに基づく効率的で、サーバーごとにこれらの要素を定義することよりも便利であるという概念です。</span><span class="sxs-lookup"><span data-stu-id="ab58a-108">In the Centralized Logging Service, a scenario is the concept of turning logging on based on a collection of server components, logging levels, and flags, which is much more efficient and useful than having to define these elements on a per-server basis.</span></span> <span data-ttu-id="ab58a-109">定義および実行するシナリオを指定してすべてのサーバーとインフラストラクチャの範囲内のプールの間で一貫性のあるシナリオを実行します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-109">You define and specify a scenario to run and the scenario is run consistently across all servers and pools in the scope of the infrastructure.</span></span>
  
<span data-ttu-id="ab58a-p103">既定のシナリオは、**AlwaysOn** です。AlwaysOn のねらいは、その名前が示すとおり、シナリオを絶えず実行することです。AlwaysOn シナリオでは、最も一般的なサーバー コンポーネントの多くについて Info レベルの情報 (Info ログ レベルには、Info のメッセージ以外に、Fatal、Error、および Warning の各メッセージも含まれます) が収集されます。AlwaysOn での情報の収集は、問題が発生する前後と問題の発生中に行われます。この点は、OCSLogger のような以前のログ記録ツールの標準的な動作とは大きく異なります。既に問題が発生した後に OCSLogger を実行すると、得られるデータが予防的なものではなく対症療法的なものになるので、トラブルシューティングの作業が困難になります。AlwaysOn では、問題のコンポーネントを特定するために探し求めている情報が得られず、(幅広い AlwaysOn のプロバイダーに与えられる可能性が低い) そのコンポーネントの修正手順が示されない場合も、ほかに行う必要があること (新しいシナリオの作成、その他の情報の収集、より焦点を絞った詳細情報を収集するための別の検索の実行など) を判断するのに適切なレベルの情報が示されます。</span><span class="sxs-lookup"><span data-stu-id="ab58a-p103">The default scenario is called **AlwaysOn**. The intended purpose for AlwaysOn is to run the scenario constantly, as the name of the scenario implies. The AlwaysOn scenario collects Info level information (note that Info logging level includes Fatal, Error, and Warning in addition to Info messages) for many of the most common server components. AlwaysOn collects information before, during, and after a problem occurs. This differs dramatically from the typical behavior of previous logging tools such as OCSLogger. You ran OCSLogger after the problem had already occurred, making your troubleshooting efforts more difficult because the data that you have is reactive, not proactive. If AlwaysOn does not contain the information that you are looking for in order to point to the problem component and indicate a course of action to fix it (which is not likely given the breadth and depth of providers in AlwaysOn), it will indicate a reasonable level of information to determine what else you need to do, such as creating a new scenario, gather other information, run a different search to collect more focused details, and so on.</span></span>
  
<span data-ttu-id="ab58a-117">集中ログ サービスでは、コマンドを実行する 2 つの方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-117">The Centralized Logging Service provides two ways to issue commands.</span></span> <span data-ttu-id="ab58a-118">トピックの数がされてにフォーカスしたビジネス サーバー管理シェルには、Skype で Windows PowerShell を使用しています。</span><span class="sxs-lookup"><span data-stu-id="ab58a-118">A number of topics have been focused squarely on using Windows PowerShell through the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="ab58a-119">多数の複雑な構成とコマンドを使用することは、ログ サービスの集中管理用の Windows PowerShell を優先します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-119">The ability to use a number of complex configurations and commands favors Windows PowerShell for Centralized Logging Service use.</span></span> <span data-ttu-id="ab58a-120">ビジネス サーバー管理シェルの Skype を介して Windows PowerShell が Skype ビジネス サーバー用のすべての関数の普及のため、Windows PowerShell コマンドのみを説明します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-120">Because Windows PowerShell through the Skype for Business Server Management Shell is nearly ubiquitous for all functions in Skype for Business Server, only the Windows PowerShell commands are discussed.</span></span> 
  
### <a name="to-run-start-csclslogging-with-windows-powershell-using-basic-commands"></a><span data-ttu-id="ab58a-121">基本的なコマンドを使用して Windows PowerShell を開始 CsClsLogging を実行するには</span><span class="sxs-lookup"><span data-stu-id="ab58a-121">To run Start-CsClsLogging with Windows PowerShell using basic commands</span></span>

1. <span data-ttu-id="ab58a-122">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="ab58a-122">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="ab58a-123">集中ログ サービスで、次を入力してログのシナリオを開始します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-123">Start a logging scenario with the Centralized Logging Service by typing the following:</span></span>
    
   ```
   Start-CsClsLogging -Scenario <name of scenario>
   ```

    <span data-ttu-id="ab58a-124">たとえば、**AlwaysOn** シナリオを開始するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-124">For example, to start the **AlwaysOn** scenario, type:</span></span>
    
   ```
   Start-CsClsLogging -Scenario AlwaysOn
   ```

    > [!NOTE]
    > <span data-ttu-id="ab58a-125">AlwaysOn シナリオには、既定の実行期間がありません。</span><span class="sxs-lookup"><span data-stu-id="ab58a-125">The AlwaysOn scenario has no default duration.</span></span> <span data-ttu-id="ab58a-126">このシナリオの実行は、**Stop-CsClsLogging** コマンドレットによって明示的に停止するまで続きます。</span><span class="sxs-lookup"><span data-stu-id="ab58a-126">This scenario will run until you explicitly stop it with the **Stop-CsClsLogging** cmdlet.</span></span> <span data-ttu-id="ab58a-127">詳細については、「[Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab58a-127">For details, see [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps).</span></span> <span data-ttu-id="ab58a-128">その他すべてのシナリオでは、既定の実行期間が 4 時間になっています。</span><span class="sxs-lookup"><span data-stu-id="ab58a-128">For all other scenarios, the default duration is 4 hours.</span></span> 
  
3. <span data-ttu-id="ab58a-129">Enter キーを押して、コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-129">Press Enter to run the command.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="ab58a-130">このコマンドを実行して展開内のコンピューターから状態を取得するには、いくらかの時間 (30 ～ 60 秒) がかかることがあります。</span><span class="sxs-lookup"><span data-stu-id="ab58a-130">It may take a short amount of time (30 to 60 seconds) for the commands to run and to receive the status back from the computers in your deployment.</span></span> 
  
     ![Start-CsClsLogging の実行](../../media/Ops_CLS_Show_and_Start_ClsLogging.jpg)
  
4. <span data-ttu-id="ab58a-132">別のシナリオを開始するには、次のように **Start-CsClsLogging** コマンドレットを使用して実行する追加シナリオの名前を指定します (以下は **Authentication** シナリオの場合)。</span><span class="sxs-lookup"><span data-stu-id="ab58a-132">To start another scenario, use the **Start-CsClsLogging** cmdlet with the name of the additional scenario to run as follows (for example, the scenario **Authentication**):</span></span>
    
   ```
   Start-CsClsLogging -Scenario Authentication
   ```

    > [!IMPORTANT]
    > <span data-ttu-id="ab58a-p106">それぞれのコンピューターで一度に実行できるシナリオは、合計 2 つまでです。コマンドのスコープがグローバルの場合は、展開内のすべてのコンピューターで (1 つまたは 2 つの) シナリオが実行されます。3 番目のシナリオを開始するには、その新しいシナリオを実行するコンピューター、プール、サイト、またはグローバルのスコープでログ記録を停止する必要があります。グローバル スコープでシナリオが開始されている場合は、1 つ以上のコンピューターおよびプールでそうしたシナリオのどちらかまたは両方のログ記録を停止できます。</span><span class="sxs-lookup"><span data-stu-id="ab58a-p106">You can have a total of two scenarios running on any given computer at any time. If the command is global in scope, all of the computers in your deployment will run the scenario or scenarios. To start a third scenario, you must stop logging on the computer, pool, site, or global scope that you want to run the new scenario on. If you have started a global scope, you can stop logging for one or both of the scenarios on one or more computers and pools.</span></span> 
  
### <a name="to-run-start-csclslogging-with-windows-powershell-using-advanced-commands"></a><span data-ttu-id="ab58a-137">高度なコマンドを使用して Windows PowerShell を開始 CsClsLogging を実行するには</span><span class="sxs-lookup"><span data-stu-id="ab58a-137">To run Start-CsClsLogging with Windows PowerShell using advanced commands</span></span>

1. <span data-ttu-id="ab58a-138">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="ab58a-138">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="ab58a-139">追加のパラメーターを使用して、このログ記録コマンドを管理できます。</span><span class="sxs-lookup"><span data-stu-id="ab58a-139">Additional parameters are available to manage the logging commands.</span></span> <span data-ttu-id="ab58a-140">-を使用することができますを実行するシナリオでは、時間の長さを調整する期間です。</span><span class="sxs-lookup"><span data-stu-id="ab58a-140">You can use -Duration to adjust the length of time for the scenario to run.</span></span> <span data-ttu-id="ab58a-141">定義することも、コンピューター、コンピューターの完全修飾ドメイン名 (Fqdn)、コンマで区切られたリストまたは、プールでは、コンマ区切りのログオンを実行するプールの Fqdn の一覧です。</span><span class="sxs-lookup"><span data-stu-id="ab58a-141">You also can define -Computers, a list of computer fully qualified domain names (FQDNs) separated by a comma, or -Pools, a comma separated list of FQDNs for pools that you want to run logging on.</span></span>
    
    <span data-ttu-id="ab58a-142">UserReplicator というシナリオによるログ セッションをプール “pool01.contoso.net” で開始するとします。</span><span class="sxs-lookup"><span data-stu-id="ab58a-142">You start a logging session for the UserReplicator scenario on the pool "pool01.contoso.net".</span></span> <span data-ttu-id="ab58a-143">また、このログ セッションの期間を 8 時間に指定します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-143">You also define the duration of the logging session at 8 hours.</span></span> <span data-ttu-id="ab58a-144">この場合、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-144">To do this, type:</span></span>
    
   ```
   Start-CsClsLogging -Scenario UserReplicator -Duration 8:00 -Pools "pool01.contoso.net"
   ```

    <span data-ttu-id="ab58a-145">このシナリオが正常に実行されると、次のような結果が返されます。</span><span class="sxs-lookup"><span data-stu-id="ab58a-145">The successful execution of this scenario returns a result like the following:</span></span>
    
     ![Start-CsClsLogging の実行](../../media/Ops_CsClsLogging_UserReplicator_Exp.jpg)
  
<span data-ttu-id="ab58a-147">この例では、AlwaysOn シナリオと UserReplicator シナリオが実行中であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="ab58a-147">Note that in this example, the AlwaysOn scenario is running and the UserReplicator scenario is running.</span></span> 
    
## <a name="stop-the-centralized-logging-service-log-capture"></a><span data-ttu-id="ab58a-148">集中ログ サービスのログ キャプチャを終了する</span><span class="sxs-lookup"><span data-stu-id="ab58a-148">Stop the Centralized Logging Service log capture</span></span>
<span data-ttu-id="ab58a-149"><a name="stop"> </a></span><span class="sxs-lookup"><span data-stu-id="ab58a-149"></span></span>

<span data-ttu-id="ab58a-150">現在実行中のセッションを停止 CsClsLogging コマンドレットを使用してログオンを停止することができます。</span><span class="sxs-lookup"><span data-stu-id="ab58a-150">You can stop a currently running logging session with the Stop-CsClsLogging cmdlet.</span></span> <span data-ttu-id="ab58a-151">一般に、さまざまな状況のログ セッションを停止する必要がありません。</span><span class="sxs-lookup"><span data-stu-id="ab58a-151">Generally, there aren't many situations in which you would need to stop a logging session.</span></span> <span data-ttu-id="ab58a-152">たとえば、ログを検索し、最初にログ記録を停止する必要のない構成を変更できます。</span><span class="sxs-lookup"><span data-stu-id="ab58a-152">For example, you can search logs and change configurations without first needing to stop logging.</span></span> <span data-ttu-id="ab58a-153">実行する開始する前に (、グローバル、サイト、プール、またはコンピューターのスコープで) その他のシナリオのいずれかの場合は 2 つのシナリオを実行している、AlwaysOn と UserReplicator などがある場合、認証に関連する情報を収集する必要がありを停止する必要があります。認証のシナリオです。</span><span class="sxs-lookup"><span data-stu-id="ab58a-153">If you have two scenarios running, for example AlwaysOn and UserReplicator, and you need to collect information related to Authentication, you will need to stop one of the other scenarios (at a global, site, pool or computer scope) before you can start running to Authentication scenario.</span></span> <span data-ttu-id="ab58a-154">詳細については、「[Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab58a-154">For details, see [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps).</span></span>
  
> [!NOTE]
> <span data-ttu-id="ab58a-155">特定の展開、プール、またはコンピューターで実行することがどのようなシナリオを決定するときは、**コンピューターごと**に実行されている 2 つのシナリオに限定されることに注意してくださいする必要があります: AlwaysOn と 1 つのカスタム シナリオです。</span><span class="sxs-lookup"><span data-stu-id="ab58a-155">When determining what scenarios you can run on a given deployment, pool or computer, you need to remember that you are limited to running two scenarios **per computer**: AlwaysOn and one custom scenario.</span></span> <span data-ttu-id="ab58a-156">プール上でのアクティビティ ログに記録する場合は、単一のエンティティとして、プールを扱う必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab58a-156">If you are logging activity on a pool, you should treat a pool as a single entity.</span></span> <span data-ttu-id="ab58a-157">ほとんどの場合、そのことをプール内の各コンピューター上のさまざまなシナリオを実行します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-157">In most cases, it would not make sense to run different scenarios on each computer in a pool.</span></span> <span data-ttu-id="ab58a-158">させることに関するデータを収集しているし、どのようなシナリオでは、展開全体で特定のコンピューターで最も有用なを考えている問題を確認します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-158">It does make sense to look at the problem that you are collecting data about and think about what scenario makes the most sense on a given computer in the overall deployment.</span></span> <span data-ttu-id="ab58a-159">などの UserReplicator のシナリオを検討する場合は非常に小さな値にありますエッジ サーバーまたはエッジ プールの UserReplicator を実行しています。</span><span class="sxs-lookup"><span data-stu-id="ab58a-159">For example, if you consider the UserReplicator scenario, there would be very little value in running UserReplicator on an Edge Server or Edge pool.</span></span> 
  
<span data-ttu-id="ab58a-p111">問題とその影響が及ぶ範囲を把握したら、次は、どのコンピューターと、どのプールで、どのようなシナリオを実行するかについて慎重に検討する必要があります。AlwaysOn シナリオは各種プロバイダーについての情報を収集するため、多岐にわたるアプリケーションに対しては有効ですが、シナリオが限定的であれば、それが効果を発揮するコンピューターやプールも一部に限定されます。また、最初に特定のシナリオの価値を理解することなく、ログ セッションをランダムに開始する場合も注意が必要です。誤ったシナリオを使用していたり、タスクに適切なシナリオであるが、そのシナリオを適用するスコープ (グローバル、サイト、プール、またはコンピューター) が誤っていたりすると、ほとんど役に立たない不適切な (シナリオをまったく実行していないかのような) データが得られる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ab58a-p111">After you understand the problem and the scope of the impact, you should make careful choices about what scenarios to run on which computers and pools. While the AlwaysOn scenario makes sense for a wide scope application because it collects information on a wide variety of providers, specific scenarios only have application value on specific computers or pools. Also, you should take caution when randomly starting up a logging session without first understanding the value of a given scenario. If you use the wrong scenario, or if you use a scenario that is appropriate for the task and you apply the scenario at the wrong scope (be it global, site, pool, or computer), you can get questionable data that is not very useful—as if you didn't run the scenario at all.</span></span>
  
<span data-ttu-id="ab58a-164">ビジネス サーバー管理シェルには、Skype を使用して、ログ サービスの集中管理機能を制御するには、CsAdministrator または CsServerAdministrator の役割に基づくアクセス制御 (RBAC) セキュリティ グループ、またはカスタムの RBAC の役割のいずれかのメンバーをする必要があります。これら 2 つのグループのいずれかが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ab58a-164">To control the Centralized Logging Service functions by using the Skype for Business Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="ab58a-165">(自分で作成したカスタムの RBAC の役割を含む) には、このコマンドレットが割り当てられているすべての RBAC の役割の一覧を返すするには、ビジネスのサーバー管理シェルまたは Windows PowerShell プロンプトに、Skype から次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-165">To return a list of all the RBAC roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Skype for Business Server Management Shell or the Windows PowerShell prompt:</span></span>
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

<span data-ttu-id="ab58a-166">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-166">For example:</span></span>
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

> [!NOTE]
> <span data-ttu-id="ab58a-167">いらっしゃるように: ログ記録を有効にした場合は、これでは、ログが保存されているでしょうか。</span><span class="sxs-lookup"><span data-stu-id="ab58a-167">So you may be wondering: Now that you've enabled logging, where are the logs kept?</span></span> <span data-ttu-id="ab58a-168">CLS のエージェントに送信される管理シェルのクエリを使用してログに格納されている情報にアクセスすることし、いくつかの可能なファイル形式に結果を出力することができます、ため、各サーバー上で CLS エージェントは、そのレコードを知っている実際に重要ではないです。</span><span class="sxs-lookup"><span data-stu-id="ab58a-168">Since you'll access the information stored in the logs using management shell queries sent to the CLS Agents, and you can output the results to several possible file formats, where on each server a CLS Agent keeps its records isn't actually important to know.</span></span>  <span data-ttu-id="ab58a-169">ログ ファイルを読み取るし、さまざまな**Snooper.exe** 、 **Notepad.exe**などのテキスト ファイルを読み取ることができる任意のツールなどのツールを使用して分析する指定の場所に保存できます。</span><span class="sxs-lookup"><span data-stu-id="ab58a-169">The log files can be saved to a location you specify and  read and analyzed using a variety of tools, including **Snooper.exe** and any tool that can read a text file, such as **Notepad.exe**.</span></span> <span data-ttu-id="ab58a-170">Snooper.exe は、ビジネス サーバー 2015 のデバッグ ツールの Skype の一部であり[Web ダウンロード](https://go.microsoft.com/fwlink/p/?LinkId=285257)として利用可能です。</span><span class="sxs-lookup"><span data-stu-id="ab58a-170">Snooper.exe is part of the Skype for Business Server 2015 Debug Tools and is available as a [Web download](https://go.microsoft.com/fwlink/p/?LinkId=285257).</span></span>

### <a name="to-stop-a-currently-running-centralized-logging-service-session"></a><span data-ttu-id="ab58a-171">現在実行中のログ サービスの一元的なセッションを停止するには</span><span class="sxs-lookup"><span data-stu-id="ab58a-171">To stop a currently running Centralized Logging Service session</span></span>

1. <span data-ttu-id="ab58a-172">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="ab58a-172">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="ab58a-173">集中ログ サービスがどのようなシナリオは、現在実行されている、次を入力して、検索するクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-173">Query the Centralized Logging Service to find out what scenarios are currently running by typing the following:</span></span>
    
   ```
   Show-CsClsLogging
   ```

   ![Show-CsCl 呼び出し後の Windows PowerShell コンソール](../../media/Ops_Show_Stop_CsClsLogging.jpg)
  
   <span data-ttu-id="ab58a-p114">Show-CsClsLogging の結果、現在実行中のシナリオの概要と、そのシナリオの実行スコープが表示されます。詳細については、「[Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab58a-p114">The result of Show-CsClsLogging is a summary of the scenarios that are running and what scope they are running in. For details, see [Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps).</span></span>
    
3. <span data-ttu-id="ab58a-177">特定のシナリオによる現在実行中のログ セッションを停止するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-177">To stop a currently running logging session with a specific scenario, type:</span></span>
    
   ```
   Stop-CsClsLogging -Scenario <scenario name> -Computers <comma separated list of fully qualified computer names> -Pools <comma separated list of fully qualified pool names>
   ```
   <span data-ttu-id="ab58a-178">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-178">For example:</span></span>
    
   ```
   Stop-CsClsLogging -Scenario UserReplicator -Pools pool01.contoso.net
   ```

   <span data-ttu-id="ab58a-179">このコマンドは、pool01.contoso.net での UserReplicatior シナリオによるログ記録を停止します。</span><span class="sxs-lookup"><span data-stu-id="ab58a-179">This command will stop logging with the UserReplicatior scenario on pool01.contoso.net.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ab58a-p115">UserReplicator シナリオを使用するこのログ セッション中に作成されたログは削除されません。このログは、Search-CsClsLogging コマンドを使用して検索を実行する場合も使用できます。詳細については、「[Search-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab58a-p115">Logs created during this logging session using the UserReplicator scenario are not deleted. The logging is still available for you to execute searches against using the Search-CsClsLogging command. For details, see [Search-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps).</span></span> 
  
<span data-ttu-id="ab58a-p116">Start-CsClsLogging と対になる Stop-CsClsLogging コマンドレットは、シナリオによって定義されるログ セッションを終了し、ログ セッションによって作成されるログを保持します。2 つのシナリオは特定のコンピューターでいつでも実行できます。一方のシナリオを停止し、他方のシナリオを使用して情報を収集するという手段は、ほとんどのワークロードのトラブルシューティングで実行できる共通のタスクです。</span><span class="sxs-lookup"><span data-stu-id="ab58a-p116">Acting as the companion command to Start-CsClsLogging, the Stop-CsClsLogging cmdlet ends the logging session, defined by scenarios, and retains the logs created by the logging session. You can run two scenarios on a given computer at any time. The method of stopping one scenario to gather information using another scenario is a common task that you can perform during most workload troubleshooting.</span></span>
## <a name="see-also"></a><span data-ttu-id="ab58a-186">関連項目</span><span class="sxs-lookup"><span data-stu-id="ab58a-186">See also</span></span>
<span data-ttu-id="ab58a-187"><a name="stop"> </a></span><span class="sxs-lookup"><span data-stu-id="ab58a-187"></span></span>

[<span data-ttu-id="ab58a-188">Centralized Logging Service in Skype for Business 2015</span><span class="sxs-lookup"><span data-stu-id="ab58a-188">Centralized Logging Service in Skype for Business 2015</span></span>](centralized-logging-service.md)
