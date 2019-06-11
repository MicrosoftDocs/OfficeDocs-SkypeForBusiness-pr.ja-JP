---
title: 一元的なログサービスのために Start を使用してログをキャプチャする
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using Start for the Centralized Logging Service to capture logs
ms:assetid: 0512b9ce-7f5b-48eb-a79e-f3498bacf2de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687958(v=OCS.15)
ms:contentKeyID: 49733543
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5033b4a8dfd8121e2f0b5926623a55358188935e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848273"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-start-for-the-centralized-logging-service-to-capture-logs-in-lync-server-2013"></a><span data-ttu-id="17578-102">Lync Server 2013 でログをキャプチャするために、一元ログサービスの開始を使用する</span><span class="sxs-lookup"><span data-stu-id="17578-102">Using Start for the Centralized Logging Service to capture logs in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="17578-103">_**最終更新日:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="17578-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="17578-104">一元ログサービスを使ってトレースログをキャプチャするには、1つ以上のコンピューターとプールでログの記録を開始するコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="17578-104">To capture trace logs using the Centralized Logging Service, you issue a command to begin logging on one or more computers and pools.</span></span> <span data-ttu-id="17578-105">また、どのコンピューターまたはプール、実行するシナリオ (AlwaysOn、別の定義済みシナリオ、作成したシナリオ)、どの Lync Server コンポーネント (S4、SipStack など) を追跡するかを定義するパラメーターを発行することもできます。</span><span class="sxs-lookup"><span data-stu-id="17578-105">You also issue parameters that define which computers or pools, what scenarios to run (for example, AlwaysOn, another predefined scenario, or a scenario you have created), what Lync Server components (for example, S4, SipStack) to trace.</span></span>

<span data-ttu-id="17578-106">適切な情報を取得するには、適切なシナリオを使用して、問題に関連する情報を収集していることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="17578-106">To capture the right information, you need to make sure you use the right scenario to collect information that is relevant to the problem.</span></span> <span data-ttu-id="17578-107">一元化されたログサービスでは、サーバーコンポーネント、ログレベル、フラグなどのコレクションに基づいてログ記録を有効にするという概念があります。これは、サーバーごとにこれらの要素を定義するよりも効率的で便利です。</span><span class="sxs-lookup"><span data-stu-id="17578-107">In the Centralized Logging Service, a scenario is the concept of turning logging on based on a collection of server components, logging levels, and flags, which is much more efficient and useful than having to define these elements on a per-server basis.</span></span> <span data-ttu-id="17578-108">実行するシナリオを定義して指定すると、インフラストラクチャの範囲内のすべてのサーバーとプールでシナリオが一貫して実行されます。</span><span class="sxs-lookup"><span data-stu-id="17578-108">You define and specify a scenario to run and the scenario is run consistently across all servers and pools in the scope of the infrastructure.</span></span>

<span data-ttu-id="17578-p103">既定のシナリオは、**AlwaysOn** です。AlwaysOn のねらいは、その名前が示すとおり、シナリオを絶えず実行することです。AlwaysOn シナリオでは、最も一般的なサーバー コンポーネントの多くについて Info レベルの情報 (Info ログ レベルには、Info のメッセージ以外に、Fatal、Error、および Warning の各メッセージも含まれます) が収集されます。AlwaysOn での情報の収集は、問題が発生する前後と問題の発生中に行われます。この点は、OCSLogger のような以前のログ記録ツールの標準的な動作とは大きく異なります。既に問題が発生した後に OCSLogger を実行すると、得られるデータが予防的なものではなく対症療法的なものになるので、トラブルシューティングの作業が困難になります。AlwaysOn では、問題のコンポーネントを特定するために探し求めている情報が得られず、(幅広い AlwaysOn のプロバイダーに与えられる可能性が低い) そのコンポーネントの修正手順が示されない場合も、ほかに行う必要があること (新しいシナリオの作成、その他の情報の収集、より焦点を絞った詳細情報を収集するための別の検索の実行など) を判断するのに適切なレベルの情報が示されます。</span><span class="sxs-lookup"><span data-stu-id="17578-p103">The default scenario is called **AlwaysOn**. The intended purpose for AlwaysOn is to run the scenario constantly, as the name of the scenario implies. The AlwaysOn scenario collects Info level information (note that Info logging level includes Fatal, Error, and Warning in addition to Info messages) for many of the most common server components. AlwaysOn collects information before, during, and after a problem occurs. This differs dramatically from the typical behavior of previous logging tools such as OCSLogger. You ran OCSLogger after the problem had already occurred, making your troubleshooting efforts more difficult because the data that you have is reactive, not proactive. If AlwaysOn does not contain the information that you are looking for in order to point to the problem component and indicate a course of action to fix it (which is not likely given the breadth and depth of providers in AlwaysOn), it will indicate a reasonable level of information to determine what else you need to do, such as creating a new scenario, gather other information, run a different search to collect more focused details, and so on.</span></span>

<span data-ttu-id="17578-116">中央集中ログサービスでは、2つの方法でコマンドを発行できます。</span><span class="sxs-lookup"><span data-stu-id="17578-116">The Centralized Logging Service provides two ways to issue commands.</span></span> <span data-ttu-id="17578-117">Lync Server 管理シェルを介して Windows PowerShell を使用することに正方形て、いくつかのトピックを重点的に説明しました。</span><span class="sxs-lookup"><span data-stu-id="17578-117">A number of topics have been focused squarely on using Windows PowerShell through the Lync Server Management Shell.</span></span> <span data-ttu-id="17578-118">多数の複雑な構成とコマンドを使う機能は、Windows PowerShell を使用して一元的なログサービスを使うことができます。</span><span class="sxs-lookup"><span data-stu-id="17578-118">The ability to use a number of complex configurations and commands favors Windows PowerShell for Centralized Logging Service use.</span></span> <span data-ttu-id="17578-119">Lync Server 管理シェル経由での Windows PowerShell は、Lync Server のすべての機能に対して広く普及しているため、Windows PowerShell コマンドのみについて説明します。</span><span class="sxs-lookup"><span data-stu-id="17578-119">Because Windows PowerShell through the Lync Server Management Shell is nearly ubiquitous for all functions in Lync Server, only the Windows PowerShell commands are discussed.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="17578-120">コマンドラインから利用できる限定的なコマンドセットを使用する場合は、「」と入力<CODE>ClsController.exe</CODE>して、clscontroller に関するヘルプを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="17578-120">If you decide to use the limited command set available from the command line, you can get help with CLSController.exe by typing <CODE>ClsController.exe</CODE>.</span></span> <span data-ttu-id="17578-121">既定では、 <STRONG>Clscontroller</STRONG>がディレクトリ C:\Program の Lync Server 2013 \ clscontroller にインストールされています。</span><span class="sxs-lookup"><span data-stu-id="17578-121">By default, <STRONG>ClsController.exe</STRONG> is installed in the directory C:\Program Files\Microsoft Lync Server 2013\ClsAgent.</span></span>



</div>

<div>

## <a name="to-run-start-csclslogging-with-windows-powershell-using-basic-commands"></a><span data-ttu-id="17578-122">基本的なコマンドを使用して Windows PowerShell で CsClsLogging を実行するには</span><span class="sxs-lookup"><span data-stu-id="17578-122">To run Start-CsClsLogging with Windows PowerShell using basic commands</span></span>

1.  <span data-ttu-id="17578-123">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="17578-123">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="17578-124">次のように入力して、集中化されたログサービスでログシナリオを開始します。</span><span class="sxs-lookup"><span data-stu-id="17578-124">Start a logging scenario with the Centralized Logging Service by typing the following:</span></span>
    
        Start-CsClsLogging -Scenario <name of scenario>
    
    <span data-ttu-id="17578-125">たとえば、**AlwaysOn** シナリオを開始するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="17578-125">For example, to start the **AlwaysOn** scenario, type:</span></span>
    
        Start-CsClsLogging -Scenario AlwaysOn
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="17578-126">AlwaysOn シナリオには、既定の実行期間がありません。</span><span class="sxs-lookup"><span data-stu-id="17578-126">The AlwaysOn scenario has no default duration.</span></span> <span data-ttu-id="17578-127">このシナリオの実行は、<STRONG>Stop-CsClsLogging</STRONG> コマンドレットによって明示的に停止するまで続きます。</span><span class="sxs-lookup"><span data-stu-id="17578-127">This scenario will run until you explicitly stop it with the <STRONG>Stop-CsClsLogging</STRONG> cmdlet.</span></span> <span data-ttu-id="17578-128">詳細については、「<A href="https://technet.microsoft.com/en-us/library/JJ619180(v=OCS.15)">Stop-CsClsLogging</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="17578-128">For details, see <A href="https://technet.microsoft.com/en-us/library/JJ619180(v=OCS.15)">Stop-CsClsLogging</A>.</span></span> <span data-ttu-id="17578-129">その他すべてのシナリオでは、既定の実行期間が 4 時間になっています。</span><span class="sxs-lookup"><span data-stu-id="17578-129">For all other scenarios, the default duration is 4 hours.</span></span>

    
    </div>

3.  <span data-ttu-id="17578-130">Enter キーを押して、コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="17578-130">Press Enter to run the command.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="17578-131">このコマンドを実行して展開内のコンピューターから状態を取得するには、いくらかの時間 (30 ～ 60 秒) がかかることがあります。</span><span class="sxs-lookup"><span data-stu-id="17578-131">It may take a short amount of time (30 to 60 seconds) for the commands to run and to receive the status back from the computers in your deployment.</span></span>

    
    </div>
    
    <span data-ttu-id="17578-132">![開始-CsClsLogging を実行しています。](images/JJ687958.c5be7413-8cef-4de7-9712-944d20cc2fa4(OCS.15).jpg "開始-CsClsLogging を実行しています。")</span><span class="sxs-lookup"><span data-stu-id="17578-132">![Running Start-CsClsLogging.](images/JJ687958.c5be7413-8cef-4de7-9712-944d20cc2fa4(OCS.15).jpg "Running Start-CsClsLogging.")</span></span>

4.  <span data-ttu-id="17578-133">別のシナリオを開始するには、次のように **Start-CsClsLogging** コマンドレットを使用して実行する追加シナリオの名前を指定します (以下は **Authentication** シナリオの場合)。</span><span class="sxs-lookup"><span data-stu-id="17578-133">To start another scenario, use the **Start-CsClsLogging** cmdlet with the name of the additional scenario to run as follows (for example, the scenario **Authentication**):</span></span>
    
        Start-CsClsLogging -Scenario Authentication
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="17578-134">それぞれのコンピューターで一度に実行できるシナリオは、合計 2 つまでです。</span><span class="sxs-lookup"><span data-stu-id="17578-134">You can have a total of two scenarios running on any given computer at any time.</span></span> <span data-ttu-id="17578-135">コマンドのスコープがグローバルの場合は、展開内のすべてのコンピューターで (1 つまたは 2 つの) シナリオが実行されます。</span><span class="sxs-lookup"><span data-stu-id="17578-135">If the command is global in scope, all of the computers in your deployment will run the scenario or scenarios.</span></span> <span data-ttu-id="17578-136">3 番目のシナリオを開始するには、その新しいシナリオを実行するコンピューター、プール、サイト、またはグローバルのスコープでログ記録を停止する必要があります。</span><span class="sxs-lookup"><span data-stu-id="17578-136">To start a third scenario, you must stop logging on the computer, pool, site, or global scope that you want to run the new scenario on.</span></span> <span data-ttu-id="17578-137">グローバル スコープでシナリオが開始されている場合は、1 つ以上のコンピューターおよびプールでそうしたシナリオのどちらかまたは両方のログ記録を停止できます。</span><span class="sxs-lookup"><span data-stu-id="17578-137">If you have started a global scope, you can stop logging for one or both of the scenarios on one or more computers and pools.</span></span> <span data-ttu-id="17578-138">実行されているシナリオを管理する方法の詳細については、「 <A href="lync-server-2013-using-stop-for-the-centralized-logging-service.md">Lync Server 2013 の集中ログサービスで Stop を使用する</A>」および「 <A href="https://technet.microsoft.com/en-us/library/JJ619180(v=OCS.15)">csclslogging</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="17578-138">For details about managing which scenarios are running, see <A href="lync-server-2013-using-stop-for-the-centralized-logging-service.md">Using Stop for the Centralized Logging Service in Lync Server 2013</A> and <A href="https://technet.microsoft.com/en-us/library/JJ619180(v=OCS.15)">Stop-CsClsLogging</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="to-run-start-csclslogging-with-windows-powershell-using-advanced-commands"></a><span data-ttu-id="17578-139">詳細なコマンドを使用して、Windows PowerShell での Start CsClsLogging を実行するには</span><span class="sxs-lookup"><span data-stu-id="17578-139">To run Start-CsClsLogging with Windows PowerShell using advanced commands</span></span>

1.  <span data-ttu-id="17578-140">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="17578-140">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="17578-p108">追加のパラメーターを使用して、このログ記録コマンドを管理できます。シナリオの実行期間を調整するには、-Duration を使用します。また、-Computers や -Pools を使用して、ログを有効にするコンピューターやプールの完全修飾ドメイン名 (FQDN) のコンマ区切りリストを定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="17578-p108">Additional parameters are available to manage the logging commands. You can use –Duration to adjust the length of time for the scenario to run. You also can define –Computers, a list of computer fully qualified domain names (FQDNs) separated by a comma, or –Pools, a comma separated list of FQDNs for pools that you want to run logging on.</span></span>
    
    <span data-ttu-id="17578-144">*UserReplicator* というシナリオによるログ セッションをプール “pool01.contoso.net” で開始するとします。</span><span class="sxs-lookup"><span data-stu-id="17578-144">You start a logging session for the *UserReplicator* scenario on the pool "pool01.contoso.net".</span></span> <span data-ttu-id="17578-145">また、このログ セッションの期間を 8 時間に指定します。</span><span class="sxs-lookup"><span data-stu-id="17578-145">You also define the duration of the logging session at 8 hours.</span></span> <span data-ttu-id="17578-146">この場合、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="17578-146">To do this, type:</span></span>
    
        Start-CsClsLogging -Scenario UserReplicator -Duration 8:00 -Pools "pool01.contoso.net"
    
    <span data-ttu-id="17578-147">このシナリオが正常に実行されると、次のような結果が返されます。</span><span class="sxs-lookup"><span data-stu-id="17578-147">The successful execution of this scenario returns a result like the following:</span></span>
    
    <span data-ttu-id="17578-148">![開始-CsClsLogging を実行しています。](images/JJ687958.399f0c2e-c08c-40ab-b6c6-381dddc12fe9(OCS.15).jpg "開始-CsClsLogging を実行しています。")</span><span class="sxs-lookup"><span data-stu-id="17578-148">![Running Start-CsClsLogging.](images/JJ687958.399f0c2e-c08c-40ab-b6c6-381dddc12fe9(OCS.15).jpg "Running Start-CsClsLogging.")</span></span>
    
    <span data-ttu-id="17578-149">この例では、AlwaysOn シナリオと UserReplicator シナリオが実行中であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="17578-149">Note that in this example, the AlwaysOn scenario is running and the UserReplicator scenario is running.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="17578-150">関連項目</span><span class="sxs-lookup"><span data-stu-id="17578-150">See Also</span></span>


[<span data-ttu-id="17578-151">Lync Server 2013 の一元管理されたログサービスの概要</span><span class="sxs-lookup"><span data-stu-id="17578-151">Overview of the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-centralized-logging-service.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

