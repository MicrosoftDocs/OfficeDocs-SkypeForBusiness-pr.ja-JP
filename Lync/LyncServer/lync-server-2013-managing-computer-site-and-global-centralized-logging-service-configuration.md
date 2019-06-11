---
title: コンピューター、サイト、グローバルな集中化されたログサービスの構成を管理する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing computer, site and global Centralized Logging Service configuration
ms:assetid: 93b9a354-9aea-4b3a-a4fe-68a89f436196
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688138(v=OCS.15)
ms:contentKeyID: 49733738
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 02c18e57b81daf93139493d046b8b2124e04e767
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34828160"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-computer-site-and-global-centralized-logging-service-configuration-in-lync-server-2013"></a><span data-ttu-id="793af-102">Lync Server 2013 でのコンピューター、サイト、グローバルな集中ログサービスの構成の管理</span><span class="sxs-lookup"><span data-stu-id="793af-102">Managing computer, site and global Centralized Logging Service configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="793af-103">_**最終更新日:** 2014-02-04_</span><span class="sxs-lookup"><span data-stu-id="793af-103">_**Topic Last Modified:** 2014-02-04_</span></span>

<span data-ttu-id="793af-104">一元ログサービスは、1台のコンピューター、コンピューターのプール、サイトのスコープ (つまり、展開のコンピューターとプールのコレクションを含むサイトの Redmond などの定義済みサイト)、またはグローバルスコープで実行することができます (これは、[展開に含まれるすべてのコンピューターとプール] を選びます。</span><span class="sxs-lookup"><span data-stu-id="793af-104">The Centralized Logging Service can be run at a scope that includes a single computer, a pool of computers, at a site scope (that is, a defined site such as the site Redmond that contains a collection of computer and pools in your deployment), or at a global scope (that is, all computers and pools in your deployment).</span></span>

<span data-ttu-id="793af-105">Lync Server 管理シェルを使用して一元的なログサービスのスコープを構成するには、CsAdministrator または CsServerAdministrator の役割ベースのアクセス制御 (RBAC) セキュリティグループのメンバーであるか、またはこれら2つのグループのどちらかです。</span><span class="sxs-lookup"><span data-stu-id="793af-105">To configure the Centralized Logging Service scope by using the Lync Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="793af-106">このコマンドレットが割り当てられているすべての RBAC ロールの一覧を返すには (自分自身で作成したカスタム RBAC ロールを含む)、Lync Server 管理シェルまたは Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="793af-106">To return a list of all the RBAC roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Lync Server Management Shell or the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Lync Server 2013 cmdlet>"}

<span data-ttu-id="793af-107">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="793af-107">For example:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<div>


> [!NOTE]
> <span data-ttu-id="793af-108">Windows PowerShell には、CLSController を使って利用できないその他のオプションとその他の構成オプションが用意されています。</span><span class="sxs-lookup"><span data-stu-id="793af-108">Windows PowerShell provides you more options and additional configuration options that are not available by using CLSController.exe.</span></span> <span data-ttu-id="793af-109">CLSController は、コマンドを実行するための簡単で簡潔な方法を提供しますが、CLSController で利用できるコマンドのセットに制限されています。</span><span class="sxs-lookup"><span data-stu-id="793af-109">CLSController offers a quick, concise method to run commands, but is limited to the set of commands available for the CLSController.</span></span> <span data-ttu-id="793af-110">Windows PowerShell は、CLSController のコマンドプロセッサで利用できるコマンドだけに限らず、幅広いコマンドと豊富なオプションを提供します。</span><span class="sxs-lookup"><span data-stu-id="793af-110">Windows PowerShell is not limited to just the command available to the command processor of the CLSController, and provides a wider set of commands and a richer set of options.</span></span> <span data-ttu-id="793af-111">たとえば、CLSController では、コンピューターとプールのスコープオプションが提供されます。</span><span class="sxs-lookup"><span data-stu-id="793af-111">For example, CLSController.exe does provide you with a scope options for –computers and –pools.</span></span> <span data-ttu-id="793af-112">Windows PowerShell では、ほとんどのコマンドでコンピューターまたはプールを示すことができます。また、新しいシナリオを定義する場合は、サイトまたはグローバルスコープを定義できます。</span><span class="sxs-lookup"><span data-stu-id="793af-112">With Windows PowerShell, you can indicate computers or pools in most commands, and when you define new scenarios (CLSController has a finite number of scenarios that are not user modifiable) you can define a site or global scope.</span></span> <span data-ttu-id="793af-113">Windows PowerShell のこの強力な機能により、サイトまたはグローバルスコープを定義できますが、実際のログはコンピューターまたはプールに制限されます。</span><span class="sxs-lookup"><span data-stu-id="793af-113">This powerful feature of Windows PowerShell enables you to define a scenario a site or global scope, but limit the actual logging to a computer or pool.</span></span><BR><span data-ttu-id="793af-114">Windows PowerShell または CLSController で実行できるコマンドラインコマンドには、基本的な違いがあります。</span><span class="sxs-lookup"><span data-stu-id="793af-114">There are fundamental differences between the command-line commands that you can run in Windows PowerShell or CLSController.</span></span> <span data-ttu-id="793af-115">Windows PowerShell には、シナリオを構成して定義するための豊富な方法が用意されています。また、トラブルシューティングシナリオには、わかりやすい方法でこれらのシナリオを再利用することもできます。</span><span class="sxs-lookup"><span data-stu-id="793af-115">Windows PowerShell provides a rich method to configure and define scenarios, and to reuse those scenarios in a meaningful way for your troubleshooting scenarios.</span></span> <span data-ttu-id="793af-116">CLSController には、コマンドを発行して結果を取得するための高速で効率的な方法が用意されていますが、CLSController 用のコマンドセットは、コマンドラインから利用できる有限コマンドによって制限されます。</span><span class="sxs-lookup"><span data-stu-id="793af-116">While CLSController does provide a fast and efficient way to issue commands and get results, the command set for CLSController is limited by the finite commands that you have available from the command line.</span></span> <span data-ttu-id="793af-117">Windows PowerShell コマンドレットとは異なり、CLSController では、新しいシナリオを定義することはできません。サイトまたはグローバルレベルでスコープを管理することも、動的に構成できない有限コマンドセットに関するその他多くの制限事項もあります。</span><span class="sxs-lookup"><span data-stu-id="793af-117">Unlike the Windows PowerShell cmdlets, CLSController cannot define new scenarios, manage scope at a site or global level, and many other limitations of a finite command set that cannot be dynamically configured.</span></span> <span data-ttu-id="793af-118">CLSController は、高速実行の手段を提供しますが、Windows PowerShell は、CLSController で可能な範囲を超えて一元的なログサービス機能を拡張するための手段を提供します。</span><span class="sxs-lookup"><span data-stu-id="793af-118">While CLSController provides a means for fast execution, Windows PowerShell provides a means to extend the Centralized Logging Service functionality beyond what is possible with CLSController.</span></span>



</div>

<span data-ttu-id="793af-p104">-Computers パラメーターを使用して [Search-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619189(v=OCS.15))、[Show-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619173(v=OCS.15))、[Start-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619190(v=OCS.15))、[Stop-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619180(v=OCS.15))、[Sync-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619169(v=OCS.15))、[Update-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619170(v=OCS.15)) の各コマンドを実行する場合に、単一のコンピューターのスコープを定義できます。-Computers パラメーターには、対象のコンピューターの完全修飾ドメイン名 (FQDN) のコンマ区切り一覧を指定できます。</span><span class="sxs-lookup"><span data-stu-id="793af-p104">A single computer scope can be defined during the execution of a [Search-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619189(v=OCS.15)), [Show-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619173(v=OCS.15)), [Start-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619190(v=OCS.15)), [Stop-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619180(v=OCS.15)), [Sync-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619169(v=OCS.15)) and [Update-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619170(v=OCS.15)) command using the –Computers parameter. The –Computers parameter accepts a comma separated list of fully qualified domain names (FQDNs) for the target computer.</span></span>

<div>


> [!TIP]
> <span data-ttu-id="793af-121">-Pools およびログ記録コマンドを実行するプールのコンマ区切り一覧を定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="793af-121">You can also define –Pools and a comma separated list of pools that you want to run the logging commands on.</span></span>



</div>

<span data-ttu-id="793af-122">サイトとグローバルスコープは、**新しい**集中化された\*\*\*\* ログサービスコマンドレット\*\*\*\* で定義されます。</span><span class="sxs-lookup"><span data-stu-id="793af-122">Site and Global scopes are defined in the **New-**, **Set-**, and **Remove-** Centralized Logging Service cmdlets.</span></span> <span data-ttu-id="793af-123">以下の例は、サイト スコープとグローバル スコープを設定する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="793af-123">The following examples demonstrate how to set a site and a global scope.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="793af-124">表示されるコマンドには、他のセクションで説明するパラメーターと概念が含まれている場合があります。</span><span class="sxs-lookup"><span data-stu-id="793af-124">The commands shown may contain parameters and concepts that are covered in other sections.</span></span> <span data-ttu-id="793af-125">この例のコマンドは、スコープを定義する<STRONG>– Identity</STRONG>パラメーターの使い方を示すことを目的としており、その他のパラメーターが完全に含まれており、スコープを指定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="793af-125">The example commands are intended to demonstrate the use of the <STRONG>–Identity</STRONG> parameter to define scope, and the other parameters are included for completeness and to specify the scope.</span></span> <span data-ttu-id="793af-126"><STRONG>Set-csclsconfiguration</STRONG>コマンドレットの詳細については、「操作のドキュメントでの<A href="https://technet.microsoft.com/en-us/library/JJ619182(v=OCS.15)">Set-csclsconfiguration</A> 」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="793af-126">For details about the <STRONG>Set-CsClsConfiguration</STRONG> cmdlets, see <A href="https://technet.microsoft.com/en-us/library/JJ619182(v=OCS.15)">Set-CsClsConfiguration</A> in the Operations documentation.</span></span>



</div>

<div>

## <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a><span data-ttu-id="793af-127">現在の集中化ログサービス構成を取得するには</span><span class="sxs-lookup"><span data-stu-id="793af-127">To retrieve the current Centralized Logging Service configuration</span></span>

1.  <span data-ttu-id="793af-128">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="793af-128">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="793af-129">コマンド ライン プロンプトで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="793af-129">Type the following at the command-line prompt:</span></span>
    
        Get-CsClsConfiguration

<span data-ttu-id="793af-130">**New-CsClsConfiguration** コマンドレットと **Set-CsClsConfiguration** コマンドレットを使用して、新しい構成を作成するか、既存の構成を更新します。</span><span class="sxs-lookup"><span data-stu-id="793af-130">Use the **New-CsClsConfiguration** and **Set-CsClsConfiguration** cmdlets to create a new configuration or to update an existing configuration.</span></span>

<span data-ttu-id="793af-131">**Get-CsClsConfiguration** を実行すると、次のスクリーンショットに示すような情報が表示されます。現在、この展開には既定のグローバル構成がありますが、サイト構成は定義されていません。</span><span class="sxs-lookup"><span data-stu-id="793af-131">When you run **Get-CsClsConfiguration**, it displays information similar to the following screen shot, where the deployment currently has the default Global configuration, but no site configurations defined:</span></span>

<span data-ttu-id="793af-132">「 ![CsClsConfiguration」のサンプル出力。]「 (images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "CsClsConfiguration」のサンプル出力。")</span><span class="sxs-lookup"><span data-stu-id="793af-132">![Sample output from Get-CsClsConfiguration.](images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "Sample output from Get-CsClsConfiguration.")</span></span>

</div>

<div>

## <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a><span data-ttu-id="793af-133">コンピューターのローカルストアから現在の集中化されたログサービス構成を取得するには</span><span class="sxs-lookup"><span data-stu-id="793af-133">To retrieve the current Centralized Logging Service configuration from the computer local store</span></span>

1.  <span data-ttu-id="793af-134">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="793af-134">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="793af-135">コマンド ライン プロンプトで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="793af-135">Type the following at the command-line prompt:</span></span>
    
        Get-CsClsConfiguration -LocalStore

<span data-ttu-id="793af-136">最初の例の " **Get-CsClsConfiguration**でパラメーターが指定されていない" という最初の例を使用すると、コマンドはデータの中央管理ストアを参照します。</span><span class="sxs-lookup"><span data-stu-id="793af-136">When you use the first example where **Get-CsClsConfiguration** does not specify any parameters, the command references the Central Management store for the data.</span></span> <span data-ttu-id="793af-137">Parameter – LocalStore を指定した場合、コマンドは中央管理ストアではなくコンピューターの LocalStore を参照します。</span><span class="sxs-lookup"><span data-stu-id="793af-137">If you specify the parameter –LocalStore, the command references the computer LocalStore instead of the Central Management store.</span></span>

</div>

<div>

## <a name="to-retrieve-a-listing-of-scenarios-currently-defined"></a><span data-ttu-id="793af-138">現在定義されているシナリオの一覧を取得するには</span><span class="sxs-lookup"><span data-stu-id="793af-138">To retrieve a listing of scenarios currently defined</span></span>

1.  <span data-ttu-id="793af-139">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="793af-139">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="793af-140">コマンド ライン プロンプトで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="793af-140">Type the following at the command-line prompt:</span></span>
    
        Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
    
    <span data-ttu-id="793af-141">たとえば、グローバル スコープで定義されているシナリオを取得するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="793af-141">For example, to retrieve the scenarios that is defined at the global scope:</span></span>
    
        Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios

<span data-ttu-id="793af-142">**Get-CsClsConfiguration** コマンドレットを使用すると、特定のスコープの構成に含まれるシナリオが常に表示されます。</span><span class="sxs-lookup"><span data-stu-id="793af-142">The cmdlet **Get-CsClsConfiguration** always displays the scenarios that are a part of a given scope’s configuration.</span></span> <span data-ttu-id="793af-143">ほとんどの場合、シナリオがすべて表示されるのではなく、一部が切り捨てられます。</span><span class="sxs-lookup"><span data-stu-id="793af-143">In most cases, all scenarios are not displayed, and are truncated.</span></span> <span data-ttu-id="793af-144">ここで使用するコマンドは、すべてのシナリオおよび使用されているプロバイダー、設定、およびフラグに関する一部の情報を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="793af-144">The command used here lists all of the scenarios and partial information about what providers, settings, and flags are used.</span></span>

</div>

<div>

## <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a><span data-ttu-id="793af-145">Windows PowerShell を使用して一元的なログサービスのグローバルスコープを更新するには</span><span class="sxs-lookup"><span data-stu-id="793af-145">To update a global scope for the Centralized Logging Service by using Windows PowerShell</span></span>

1.  <span data-ttu-id="793af-146">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="793af-146">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="793af-147">コマンド ライン プロンプトで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="793af-147">Type the following at the command-line prompt:</span></span>
    
        Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
    
    <span data-ttu-id="793af-148">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="793af-148">For example:</span></span>
    
        Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40

<span data-ttu-id="793af-p109">このコマンドは、トレース ファイルのロールオーバーのサイズを 40 MB に設定するよう、展開内の各コンピューターおよびプールの CLSAgent に指示します。すべてのサイトのコンピューターとプールがこのコマンドの対象となり、コンピューターとプールの構成済みのトレース ログのロールオーバーの値が 40 MB に設定されます。</span><span class="sxs-lookup"><span data-stu-id="793af-p109">The command tells the CLSAgent on each computer and pool in the deployment to set the size of the rollover value on the tracing file to 40 megabytes. Computers and pools in all sites are affected by the command, and will set their configured trace log rollover value to 40 megabytes.</span></span>

</div>

<div>

## <a name="to-update-a-site-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a><span data-ttu-id="793af-151">Windows PowerShell を使用して一元的なログサービスのサイト範囲を更新するには</span><span class="sxs-lookup"><span data-stu-id="793af-151">To update a site scope for the Centralized Logging Service by using Windows PowerShell</span></span>

1.  <span data-ttu-id="793af-152">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="793af-152">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="793af-153">コマンド ライン プロンプトで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="793af-153">Type the following at the command-line prompt:</span></span>
    
        Set-CsClsConfiguration -Identity <scope/site name> -EtlFileRolloverSizeMB <size for logging file in megabytes> -EtlFileFolder <default location %TEMP%\Tracing>
    
    <span data-ttu-id="793af-154">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="793af-154">For example:</span></span>
    
        Set-CsClsConfiguration -Identity "site/Redmond" -EtlFileRolloverSizeMB 40 -EtlFileFolder "C:\LogFiles\Tracing" 
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="793af-p110">この例に示すように、ログ ファイルの既定の場所は %TEMP%\Tracing です。ただし、これは実際にはファイルを書き込む CLSAgent であり、CSLAgent はネットワーク サービスとして実行されるため、%TEMP% 変数は %WINDIR%\ServiceProfiles\NetworkService\AppData\Local に展開されます。</span><span class="sxs-lookup"><span data-stu-id="793af-p110">As noted in the example, the default location of the log files is %TEMP%\Tracing. However, because it is actually CLSAgent that is writing the file and CSLAgent runs as Network Service, the %TEMP% variable expands to %WINDIR%\ServiceProfiles\NetworkService\AppData\Local.</span></span>

    
    </div>

<span data-ttu-id="793af-p111">このコマンドは、トレース ファイルのロールオーバーのサイズを 40 MB に設定するよう、Redmond サイト内の各コンピューターおよびプールの CLSAgent に指示します。他のサイトのコンピューターとプールはこのコマンドの対象ではなく、現在構成されているトレース ログのロールオーバーの値 (既定値の 20 MB またはログ記録セッションの開始時に定義された値) が引き続き使用されます。</span><span class="sxs-lookup"><span data-stu-id="793af-p111">The command tells the CLSAgent on each computer and pool in the site Redmond to set the size of the rollover value on the tracing file to 40 megabytes. Computers and pools in other sites will not be affected by the command, and will continue to use the currently configured trace log rollover value defined either by default (20 megabytes) or during the start of the logging session.</span></span>

</div>

<div>

## <a name="to-create-a-new-centralized-logging-service-configuration"></a><span data-ttu-id="793af-159">新しい一元ログサービス構成を作成するには</span><span class="sxs-lookup"><span data-stu-id="793af-159">To create a new Centralized Logging Service configuration</span></span>

1.  <span data-ttu-id="793af-160">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="793af-160">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="793af-161">コマンド ライン プロンプトで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="793af-161">Type the following at the command-line prompt:</span></span>
    
        New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="793af-162">New-CsClsConfiguration を使用すると、オプションの多数の構成設定にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="793af-162">New-CsClsConfiguration provides access to a large number of optional configuration settings.</span></span> <span data-ttu-id="793af-163">構成オプションの詳細については、「 <A href="https://technet.microsoft.com/en-us/library/JJ619179(v=OCS.15)">CsClsConfiguration</A> 」および「 <A href="lync-server-2013-understanding-centralized-logging-service-configuration-settings.md">Lync Server 2013 での一元ログサービスの構成設定につい</A>て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="793af-163">For details about the configuration options, see <A href="https://technet.microsoft.com/en-us/library/JJ619179(v=OCS.15)">Get-CsClsConfiguration</A> and <A href="lync-server-2013-understanding-centralized-logging-service-configuration-settings.md">Understanding Centralized Logging Service configuration settings in Lync Server 2013</A>.</span></span>

    
    </div>
    
    <span data-ttu-id="793af-164">たとえば、キャッシュ ファイル用のネットワーク フォルダー、ログ ファイルのロールオーバー時間、およびログ ファイルのロールオーバー サイズを定義する新しい構成を作成するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="793af-164">For example, to create a new configuration that defines a network folder for cache files, rollover time period for the log files and rollover size for the log files, you would type:</span></span>
    
        New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40

<span data-ttu-id="793af-165">新しい構成の作成を慎重に計画し、一元管理サービスの新しいプロパティを定義する方法を検討してください。</span><span class="sxs-lookup"><span data-stu-id="793af-165">You should carefully plan the creation of new configurations and how you define new properties for the Centralized Logging Service.</span></span> <span data-ttu-id="793af-166">変更は慎重に行い、問題のシナリオのログを適切に記録する機能に及ぼす影響について理解しておいてください。</span><span class="sxs-lookup"><span data-stu-id="793af-166">You should be cautious about making changes and make sure you understand the impact on your ability to properly log problem scenarios.</span></span> <span data-ttu-id="793af-167">ログの管理機能を強化する、つまり発生した問題を解決するためのサイズおよびロールオーバー時間を定義できるように構成を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="793af-167">You should make changes to the configuration that will enhance your ability to manage logs to a size and a rollover period that will allow problem solving when it arises.</span></span>

</div>

<div>

## <a name="to-remove-an-existing-centralized-logging-service-configuration"></a><span data-ttu-id="793af-168">既存の一元ログサービス構成を削除するには</span><span class="sxs-lookup"><span data-stu-id="793af-168">To remove an existing Centralized Logging Service configuration</span></span>

1.  <span data-ttu-id="793af-169">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="793af-169">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="793af-170">コマンド ライン プロンプトで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="793af-170">Type the following at the command-line prompt:</span></span>
    
        Remove-CsClsConfiguration -Identity <scope and name>
    
    <span data-ttu-id="793af-171">たとえば、ログファイルのロールオーバー時間を増やすために作成した一元ログサービスの構成を削除するには、ロールオーバーログファイルのサイズを大きくして、次のようにログファイルキャッシュの場所をネットワーク共有に設定します。</span><span class="sxs-lookup"><span data-stu-id="793af-171">For example, to remove a Centralized Logging Service configuration that you created to increase the log file rollover time, increase the rollover log file size, and set the log file cache location to a network share as follows:</span></span>
    
        Remove-CsClsConfiguration -Identity "site:Redmond"
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="793af-172">これは、「新しい一元ログサービス構成を作成する」の手順で作成した新しい構成です。</span><span class="sxs-lookup"><span data-stu-id="793af-172">This is the new configuration that was created in the procedure "To create a new Centralized Logging Service configuration."</span></span>

    
    </div>

<span data-ttu-id="793af-173">サイト レベルの構成の削除を選択すると、そのサイトではグローバル設定が使用されます。</span><span class="sxs-lookup"><span data-stu-id="793af-173">If you choose to remove a site-level configuration, the site will use the global settings.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="793af-174">関連項目</span><span class="sxs-lookup"><span data-stu-id="793af-174">See Also</span></span>


[<span data-ttu-id="793af-175">Lync Server 2013 の一元管理されたログサービスの概要</span><span class="sxs-lookup"><span data-stu-id="793af-175">Overview of the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-centralized-logging-service.md)  


[<span data-ttu-id="793af-176">Lync Server 2013 で中央集中ログサービスの構成設定を管理する</span><span class="sxs-lookup"><span data-stu-id="793af-176">Managing the Centralized Logging Service configuration settings in Lync Server 2013</span></span>](lync-server-2013-managing-the-centralized-logging-service-configuration-settings.md)  
<span data-ttu-id="793af-177">[Set-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619182(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="793af-177">[Set-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619182(v=OCS.15))</span></span>  
<span data-ttu-id="793af-178">[Get-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619179(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="793af-178">[Get-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619179(v=OCS.15))</span></span>  
<span data-ttu-id="793af-179">[New-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619177(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="793af-179">[New-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619177(v=OCS.15))</span></span>  
<span data-ttu-id="793af-180">[CsClsConfiguration の削除](https://technet.microsoft.com/en-us/library/JJ619191(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="793af-180">[Remove-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619191(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

