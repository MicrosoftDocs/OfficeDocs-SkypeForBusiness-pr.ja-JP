---
title: コンピューター、サイト、およびグローバルな集中ログサービスの構成を管理する
description: コンピューター、サイト、およびグローバルな集中ログサービスの構成を管理します。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing computer, site and global Centralized Logging Service configuration
ms:assetid: 93b9a354-9aea-4b3a-a4fe-68a89f436196
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688138(v=OCS.15)
ms:contentKeyID: 49733738
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 37dee125d69e17664fddd0c32feb3048ffcf91b5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570383"
---
# <a name="managing-computer-site-and-global-centralized-logging-service-configuration-in-lync-server-2013"></a><span data-ttu-id="bd26e-103">Lync Server 2013 でのコンピューター、サイト、およびグローバルな集中ログサービスの構成の管理</span><span class="sxs-lookup"><span data-stu-id="bd26e-103">Managing computer, site and global Centralized Logging Service configuration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bd26e-104">_**トピックの最終更新日:** 2014-02-04_</span><span class="sxs-lookup"><span data-stu-id="bd26e-104">_**Topic Last Modified:** 2014-02-04_</span></span>

<span data-ttu-id="bd26e-105">集中ログサービスは、単一のコンピューター、コンピューターのプール、サイトスコープ (展開内のコンピューターとプールのコレクションが含まれているサイト Redmond などの定義済みサイト)、またはグローバルスコープ (展開内のすべてのコンピューターとプール) に対して実行することができます。</span><span class="sxs-lookup"><span data-stu-id="bd26e-105">The Centralized Logging Service can be run at a scope that includes a single computer, a pool of computers, at a site scope (that is, a defined site such as the site Redmond that contains a collection of computer and pools in your deployment), or at a global scope (that is, all computers and pools in your deployment).</span></span>

<span data-ttu-id="bd26e-106">Lync Server 管理シェルを使用して集中ログサービススコープを構成するには、CsAdministrator または CsServerAdministrator の役割ベースのアクセス制御 (RBAC) セキュリティグループのメンバーであるか、またはこれら2つのグループのどちらかを含むカスタムの RBAC の役割を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd26e-106">To configure the Centralized Logging Service scope by using the Lync Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="bd26e-107">このコマンドレットが割り当てられているすべての RBAC の役割 (自分で作成したカスタムの RBAC の役割を含む) の一覧を返すには、Lync Server 管理シェルまたは Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="bd26e-107">To return a list of all the RBAC roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Lync Server Management Shell or the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Lync Server 2013 cmdlet>"}

<span data-ttu-id="bd26e-108">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="bd26e-108">For example:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<div>


> [!NOTE]
> <span data-ttu-id="bd26e-109">Windows PowerShell には、CLSController.exe を使用して利用できないオプションと追加の構成オプションが用意されています。</span><span class="sxs-lookup"><span data-stu-id="bd26e-109">Windows PowerShell provides you more options and additional configuration options that are not available by using CLSController.exe.</span></span> <span data-ttu-id="bd26e-110">CLSController は、コマンドをすばやく、簡単に実行するための方法を提供しますが、CLSController で使用できるコマンドのセットに制限されています。</span><span class="sxs-lookup"><span data-stu-id="bd26e-110">CLSController offers a quick, concise method to run commands, but is limited to the set of commands available for the CLSController.</span></span> <span data-ttu-id="bd26e-111">Windows PowerShell は、CLSController のコマンドプロセッサで使用可能なコマンドだけに制限されていません。また、幅広いコマンドと豊富なオプションが用意されています。</span><span class="sxs-lookup"><span data-stu-id="bd26e-111">Windows PowerShell is not limited to just the command available to the command processor of the CLSController, and provides a wider set of commands and a richer set of options.</span></span> <span data-ttu-id="bd26e-112">たとえば、CLSController.exe によって、– computers および–プールのスコープオプションが提供されます。</span><span class="sxs-lookup"><span data-stu-id="bd26e-112">For example, CLSController.exe does provide you with a scope options for –computers and –pools.</span></span> <span data-ttu-id="bd26e-113">Windows PowerShell を使用すると、ほとんどのコマンドでコンピューターやプールを指定できます。また、新しいシナリオを定義するときに (CLSController にはユーザーが変更できないシナリオの数が限られています)、サイトまたはグローバルスコープを定義できます。</span><span class="sxs-lookup"><span data-stu-id="bd26e-113">With Windows PowerShell, you can indicate computers or pools in most commands, and when you define new scenarios (CLSController has a finite number of scenarios that are not user modifiable) you can define a site or global scope.</span></span> <span data-ttu-id="bd26e-114">Windows PowerShell のこの強力な機能により、シナリオをサイトまたはグローバルスコープで定義できますが、実際のログ出力はコンピューターまたはプールに制限されます。</span><span class="sxs-lookup"><span data-stu-id="bd26e-114">This powerful feature of Windows PowerShell enables you to define a scenario a site or global scope, but limit the actual logging to a computer or pool.</span></span><BR><span data-ttu-id="bd26e-115">Windows PowerShell または CLSController で実行できるコマンドラインコマンドには、基本的な違いがあります。</span><span class="sxs-lookup"><span data-stu-id="bd26e-115">There are fundamental differences between the command-line commands that you can run in Windows PowerShell or CLSController.</span></span> <span data-ttu-id="bd26e-116">Windows PowerShell には、シナリオを構成して定義するための豊富な方法が用意されています。また、これらのシナリオをトラブルシューティングのシナリオに合わせてわかりやすく再利用できます。</span><span class="sxs-lookup"><span data-stu-id="bd26e-116">Windows PowerShell provides a rich method to configure and define scenarios, and to reuse those scenarios in a meaningful way for your troubleshooting scenarios.</span></span> <span data-ttu-id="bd26e-117">CLSController では、コマンドを発行して結果を取得する高速で効率的な方法が提供されていますが、CLSController のコマンドセットは、コマンドラインから使用可能な有限コマンドによって制限されます。</span><span class="sxs-lookup"><span data-stu-id="bd26e-117">While CLSController does provide a fast and efficient way to issue commands and get results, the command set for CLSController is limited by the finite commands that you have available from the command line.</span></span> <span data-ttu-id="bd26e-118">Windows PowerShell コマンドレットとは異なり、CLSController では新しいシナリオを定義したり、サイトまたはグローバルレベルでスコープを管理したり、動的に構成することができない制限されたコマンドセットに関するその他の多くの制限を設けたりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="bd26e-118">Unlike the Windows PowerShell cmdlets, CLSController cannot define new scenarios, manage scope at a site or global level, and many other limitations of a finite command set that cannot be dynamically configured.</span></span> <span data-ttu-id="bd26e-119">CLSController は高速実行の手段を提供しますが、Windows PowerShell では、集中化されたログサービス機能を、CLSController で可能な範囲を超えて拡張する手段が提供されています。</span><span class="sxs-lookup"><span data-stu-id="bd26e-119">While CLSController provides a means for fast execution, Windows PowerShell provides a means to extend the Centralized Logging Service functionality beyond what is possible with CLSController.</span></span>



</div>

<span data-ttu-id="bd26e-120">1台のコンピュータースコープは、検索の実行中に定義できます。このスコープは、-Computers パラメーターを使用して、 [検索-CsClsLogging](https://technet.microsoft.com/library/JJ619189(v=OCS.15))、 [Show-](https://technet.microsoft.com/library/JJ619173(v=OCS.15))csclslogging、 [Start-CsClsLogging](https://technet.microsoft.com/library/JJ619190(v=OCS.15))、 [Stop-csclslogging](https://technet.microsoft.com/library/JJ619180(v=OCS.15))、 [Sync-csclslogging](https://technet.microsoft.com/library/JJ619169(v=OCS.15)) 、および [Update-](https://technet.microsoft.com/library/JJ619170(v=OCS.15)) csclslogging コマンドの実行中に定義できます。</span><span class="sxs-lookup"><span data-stu-id="bd26e-120">A single computer scope can be defined during the execution of a [Search-CsClsLogging](https://technet.microsoft.com/library/JJ619189(v=OCS.15)), [Show-CsClsLogging](https://technet.microsoft.com/library/JJ619173(v=OCS.15)), [Start-CsClsLogging](https://technet.microsoft.com/library/JJ619190(v=OCS.15)), [Stop-CsClsLogging](https://technet.microsoft.com/library/JJ619180(v=OCS.15)), [Sync-CsClsLogging](https://technet.microsoft.com/library/JJ619169(v=OCS.15)) and [Update-CsClsLogging](https://technet.microsoft.com/library/JJ619170(v=OCS.15)) command using the –Computers parameter.</span></span> <span data-ttu-id="bd26e-121">– Computers パラメーターには、ターゲットコンピューターの完全修飾ドメイン名 (Fqdn) のコンマ区切りリストを指定します。</span><span class="sxs-lookup"><span data-stu-id="bd26e-121">The –Computers parameter accepts a comma separated list of fully qualified domain names (FQDNs) for the target computer.</span></span>

<div>


> [!TIP]
> <span data-ttu-id="bd26e-122">また、ログコマンドを実行するプールとコンマで区切られた一覧を定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="bd26e-122">You can also define –Pools and a comma separated list of pools that you want to run the logging commands on.</span></span>



</div>

<span data-ttu-id="bd26e-123">サイトとグローバルスコープは、 **新しい-**、 **Set-** および **Remove-** 集中ログサービスのコマンドレットで定義されています。</span><span class="sxs-lookup"><span data-stu-id="bd26e-123">Site and Global scopes are defined in the **New-**, **Set-**, and **Remove-** Centralized Logging Service cmdlets.</span></span> <span data-ttu-id="bd26e-124">次の例は、サイトとグローバルスコープを設定する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="bd26e-124">The following examples demonstrate how to set a site and a global scope.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="bd26e-125">表示されているコマンドには、他のセクションで説明しているパラメーターと概念が含まれている場合があります。</span><span class="sxs-lookup"><span data-stu-id="bd26e-125">The commands shown may contain parameters and concepts that are covered in other sections.</span></span> <span data-ttu-id="bd26e-126">この例では、 <STRONG>-Identity</STRONG> パラメーターを使用してスコープを定義することを示し、その他のパラメーターは完全に、そのスコープを指定することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="bd26e-126">The example commands are intended to demonstrate the use of the <STRONG>–Identity</STRONG> parameter to define scope, and the other parameters are included for completeness and to specify the scope.</span></span> <span data-ttu-id="bd26e-127"><STRONG>設定-csclsconfiguration</STRONG>コマンドレットの詳細については、「操作」のドキュメントの「 <A href="https://technet.microsoft.com/library/JJ619182(v=OCS.15)">Set-csclsconfiguration</A> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd26e-127">For details about the <STRONG>Set-CsClsConfiguration</STRONG> cmdlets, see <A href="https://technet.microsoft.com/library/JJ619182(v=OCS.15)">Set-CsClsConfiguration</A> in the Operations documentation.</span></span>



</div>

<div>

## <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a><span data-ttu-id="bd26e-128">現在の集中ログサービスの構成を取得するには</span><span class="sxs-lookup"><span data-stu-id="bd26e-128">To retrieve the current Centralized Logging Service configuration</span></span>

1.  <span data-ttu-id="bd26e-129">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="bd26e-129">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="bd26e-130">コマンドラインプロンプトで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="bd26e-130">Type the following at the command-line prompt:</span></span>
    
        Get-CsClsConfiguration

<span data-ttu-id="bd26e-131">新しい構成を作成したり、既存の構成を更新したりするには、 **新しい-csclsconfiguration** および **Set-csclsconfiguration** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="bd26e-131">Use the **New-CsClsConfiguration** and **Set-CsClsConfiguration** cmdlets to create a new configuration or to update an existing configuration.</span></span>

<span data-ttu-id="bd26e-132">**取得-CsClsConfiguration**を実行すると、次のスクリーンショットに示すような情報が表示されます。現在、展開には既定のグローバル構成がありますが、サイト構成は定義されていません。</span><span class="sxs-lookup"><span data-stu-id="bd26e-132">When you run **Get-CsClsConfiguration**, it displays information similar to the following screen shot, where the deployment currently has the default Global configuration, but no site configurations defined:</span></span>

<span data-ttu-id="bd26e-133">![Get-CsClsConfiguration からの出力例。](images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "Get-CsClsConfiguration からの出力例。")</span><span class="sxs-lookup"><span data-stu-id="bd26e-133">![Sample output from Get-CsClsConfiguration.](images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "Sample output from Get-CsClsConfiguration.")</span></span>

</div>

<div>

## <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a><span data-ttu-id="bd26e-134">コンピューターのローカルストアから現在の集中ログサービスの構成を取得するには</span><span class="sxs-lookup"><span data-stu-id="bd26e-134">To retrieve the current Centralized Logging Service configuration from the computer local store</span></span>

1.  <span data-ttu-id="bd26e-135">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="bd26e-135">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="bd26e-136">コマンドラインプロンプトで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="bd26e-136">Type the following at the command-line prompt:</span></span>
    
        Get-CsClsConfiguration -LocalStore

<span data-ttu-id="bd26e-137">**Get-CsClsConfiguration**でパラメーターが指定されていない最初の例を使用すると、コマンドはデータの中央管理ストアを参照します。</span><span class="sxs-lookup"><span data-stu-id="bd26e-137">When you use the first example where **Get-CsClsConfiguration** does not specify any parameters, the command references the Central Management store for the data.</span></span> <span data-ttu-id="bd26e-138">パラメーター– LocalStore を指定すると、コマンドは中央管理ストアの代わりにコンピューターの LocalStore を参照します。</span><span class="sxs-lookup"><span data-stu-id="bd26e-138">If you specify the parameter –LocalStore, the command references the computer LocalStore instead of the Central Management store.</span></span>

</div>

<div>

## <a name="to-retrieve-a-listing-of-scenarios-currently-defined"></a><span data-ttu-id="bd26e-139">現在定義されているシナリオの一覧を取得するには</span><span class="sxs-lookup"><span data-stu-id="bd26e-139">To retrieve a listing of scenarios currently defined</span></span>

1.  <span data-ttu-id="bd26e-140">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="bd26e-140">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="bd26e-141">コマンドラインプロンプトで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="bd26e-141">Type the following at the command-line prompt:</span></span>
    
        Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
    
    <span data-ttu-id="bd26e-142">たとえば、グローバルスコープで定義されているシナリオを取得するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="bd26e-142">For example, to retrieve the scenarios that is defined at the global scope:</span></span>
    
        Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios

<span data-ttu-id="bd26e-143">コマンドレットを **取得** すると、指定したスコープの構成の一部であるシナリオが常に表示されます。</span><span class="sxs-lookup"><span data-stu-id="bd26e-143">The cmdlet **Get-CsClsConfiguration** always displays the scenarios that are a part of a given scope’s configuration.</span></span> <span data-ttu-id="bd26e-144">ほとんどの場合、すべてのシナリオは表示されず、切り捨てられます。</span><span class="sxs-lookup"><span data-stu-id="bd26e-144">In most cases, all scenarios are not displayed, and are truncated.</span></span> <span data-ttu-id="bd26e-145">ここで使用しているコマンドは、すべてのシナリオと、プロバイダー、設定、およびフラグを使用することに関する情報の一部を示しています。</span><span class="sxs-lookup"><span data-stu-id="bd26e-145">The command used here lists all of the scenarios and partial information about what providers, settings, and flags are used.</span></span>

</div>

<div>

## <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a><span data-ttu-id="bd26e-146">Windows PowerShell を使用して集中ログサービスのグローバルスコープを更新するには</span><span class="sxs-lookup"><span data-stu-id="bd26e-146">To update a global scope for the Centralized Logging Service by using Windows PowerShell</span></span>

1.  <span data-ttu-id="bd26e-147">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="bd26e-147">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="bd26e-148">コマンドラインプロンプトで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="bd26e-148">Type the following at the command-line prompt:</span></span>
    
        Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
    
    <span data-ttu-id="bd26e-149">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="bd26e-149">For example:</span></span>
    
        Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40

<span data-ttu-id="bd26e-150">このコマンドは、展開内の各コンピューターおよびプールの CLSAgent に対して、トレースファイルのロールオーバー値のサイズを 40 mb に設定するように指示します。</span><span class="sxs-lookup"><span data-stu-id="bd26e-150">The command tells the CLSAgent on each computer and pool in the deployment to set the size of the rollover value on the tracing file to 40 megabytes.</span></span> <span data-ttu-id="bd26e-151">すべてのサイトのコンピューターとプールはコマンドの影響を受け、構成済みのトレースログのロールオーバー値は40メガバイトに設定されます。</span><span class="sxs-lookup"><span data-stu-id="bd26e-151">Computers and pools in all sites are affected by the command, and will set their configured trace log rollover value to 40 megabytes.</span></span>

</div>

<div>

## <a name="to-update-a-site-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a><span data-ttu-id="bd26e-152">Windows PowerShell を使用して集中ログサービスのサイトスコープを更新するには</span><span class="sxs-lookup"><span data-stu-id="bd26e-152">To update a site scope for the Centralized Logging Service by using Windows PowerShell</span></span>

1.  <span data-ttu-id="bd26e-153">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="bd26e-153">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="bd26e-154">コマンドラインプロンプトで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="bd26e-154">Type the following at the command-line prompt:</span></span>
    
        Set-CsClsConfiguration -Identity <scope/site name> -EtlFileRolloverSizeMB <size for logging file in megabytes> -EtlFileFolder <default location %TEMP%\Tracing>
    
    <span data-ttu-id="bd26e-155">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="bd26e-155">For example:</span></span>
    
        Set-CsClsConfiguration -Identity "site/Redmond" -EtlFileRolloverSizeMB 40 -EtlFileFolder "C:\LogFiles\Tracing" 
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="bd26e-156">例に示されているように、ログファイルの既定の場所は%TEMP%\Tracing. です。</span><span class="sxs-lookup"><span data-stu-id="bd26e-156">As noted in the example, the default location of the log files is %TEMP%\Tracing.</span></span> <span data-ttu-id="bd26e-157">ただし、実際には、ファイルを書き込み中で、CSLAgent はネットワークサービスとして実行されるので、このような場合、%Windir%\serviceprofiles\networkservice\appdata\local には% TEMP% 変数が展開されます。</span><span class="sxs-lookup"><span data-stu-id="bd26e-157">However, because it is actually CLSAgent that is writing the file and CSLAgent runs as Network Service, the %TEMP% variable expands to %WINDIR%\ServiceProfiles\NetworkService\AppData\Local.</span></span>

    
    </div>

<span data-ttu-id="bd26e-158">このコマンドは、サイト Redmond の各コンピューターおよびプールの CLSAgent に対して、トレースファイルのロールオーバー値のサイズを 40 mb に設定します。</span><span class="sxs-lookup"><span data-stu-id="bd26e-158">The command tells the CLSAgent on each computer and pool in the site Redmond to set the size of the rollover value on the tracing file to 40 megabytes.</span></span> <span data-ttu-id="bd26e-159">他のサイト内のコンピューターとプールはコマンドの影響を受けず、現在構成されているトレースログのロールオーバー値 (既定値 (20 mb) またはログセッションの開始時) を引き続き使用します。</span><span class="sxs-lookup"><span data-stu-id="bd26e-159">Computers and pools in other sites will not be affected by the command, and will continue to use the currently configured trace log rollover value defined either by default (20 megabytes) or during the start of the logging session.</span></span>

</div>

<div>

## <a name="to-create-a-new-centralized-logging-service-configuration"></a><span data-ttu-id="bd26e-160">新しい集中ログサービスの構成を作成するには</span><span class="sxs-lookup"><span data-stu-id="bd26e-160">To create a new Centralized Logging Service configuration</span></span>

1.  <span data-ttu-id="bd26e-161">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="bd26e-161">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="bd26e-162">コマンドラインプロンプトで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="bd26e-162">Type the following at the command-line prompt:</span></span>
    
        New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="bd26e-163">New-CsClsConfiguration を使用すると、多数のオプションの構成設定にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="bd26e-163">New-CsClsConfiguration provides access to a large number of optional configuration settings.</span></span> <span data-ttu-id="bd26e-164">構成オプションの詳細については、「 <A href="https://technet.microsoft.com/library/JJ619179(v=OCS.15)">取得-CsClsConfiguration</A> 」および「 <A href="lync-server-2013-understanding-centralized-logging-service-configuration-settings.md">Lync Server 2013 での集中ログサービスの構成設定に</A>ついて」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd26e-164">For details about the configuration options, see <A href="https://technet.microsoft.com/library/JJ619179(v=OCS.15)">Get-CsClsConfiguration</A> and <A href="lync-server-2013-understanding-centralized-logging-service-configuration-settings.md">Understanding Centralized Logging Service configuration settings in Lync Server 2013</A>.</span></span>

    
    </div>
    
    <span data-ttu-id="bd26e-165">たとえば、キャッシュファイル用のネットワークフォルダー、ログファイルのロールオーバー期間、およびログファイルのロールオーバーサイズを定義する新しい構成を作成するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="bd26e-165">For example, to create a new configuration that defines a network folder for cache files, rollover time period for the log files and rollover size for the log files, you would type:</span></span>
    
        New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40

<span data-ttu-id="bd26e-166">新しい構成の作成を慎重に計画し、集中ログサービスの新しいプロパティを定義する方法を検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd26e-166">You should carefully plan the creation of new configurations and how you define new properties for the Centralized Logging Service.</span></span> <span data-ttu-id="bd26e-167">変更を行って、問題のシナリオを適切にログに記録する機能への影響を理解しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd26e-167">You should be cautious about making changes and make sure you understand the impact on your ability to properly log problem scenarios.</span></span> <span data-ttu-id="bd26e-168">ログの管理能力を向上させるように構成を変更する必要があります。これにより、問題が発生したときに問題を解決するためのサイズとロールオーバー期間が向上します。</span><span class="sxs-lookup"><span data-stu-id="bd26e-168">You should make changes to the configuration that will enhance your ability to manage logs to a size and a rollover period that will allow problem solving when it arises.</span></span>

</div>

<div>

## <a name="to-remove-an-existing-centralized-logging-service-configuration"></a><span data-ttu-id="bd26e-169">既存の集中ログサービスの構成を削除するには</span><span class="sxs-lookup"><span data-stu-id="bd26e-169">To remove an existing Centralized Logging Service configuration</span></span>

1.  <span data-ttu-id="bd26e-170">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="bd26e-170">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="bd26e-171">コマンドラインプロンプトで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="bd26e-171">Type the following at the command-line prompt:</span></span>
    
        Remove-CsClsConfiguration -Identity <scope and name>
    
    <span data-ttu-id="bd26e-172">たとえば、ログファイルのロールオーバー時間を長くするために作成した集中ログサービスの構成を削除するには、次のように、ロールオーバーログファイルのサイズを大きくして、ログファイルのキャッシュの場所をネットワーク共有に設定します。</span><span class="sxs-lookup"><span data-stu-id="bd26e-172">For example, to remove a Centralized Logging Service configuration that you created to increase the log file rollover time, increase the rollover log file size, and set the log file cache location to a network share as follows:</span></span>
    
        Remove-CsClsConfiguration -Identity "site:Redmond"
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="bd26e-173">これは、「新しい集中ログサービスの構成を作成するには」の手順で作成した新しい構成です。</span><span class="sxs-lookup"><span data-stu-id="bd26e-173">This is the new configuration that was created in the procedure "To create a new Centralized Logging Service configuration."</span></span>

    
    </div>

<span data-ttu-id="bd26e-174">サイトレベルの構成の削除を選択すると、サイトではグローバル設定が使用されます。</span><span class="sxs-lookup"><span data-stu-id="bd26e-174">If you choose to remove a site-level configuration, the site will use the global settings.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bd26e-175">関連項目</span><span class="sxs-lookup"><span data-stu-id="bd26e-175">See Also</span></span>


[<span data-ttu-id="bd26e-176">Lync Server 2013 の集中ログサービスの概要</span><span class="sxs-lookup"><span data-stu-id="bd26e-176">Overview of the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-centralized-logging-service.md)  


[<span data-ttu-id="bd26e-177">Lync Server 2013 での集中ログサービスの構成設定の管理</span><span class="sxs-lookup"><span data-stu-id="bd26e-177">Managing the Centralized Logging Service configuration settings in Lync Server 2013</span></span>](lync-server-2013-managing-the-centralized-logging-service-configuration-settings.md)  
<span data-ttu-id="bd26e-178">[設定-CsClsConfiguration](https://technet.microsoft.com/library/JJ619182(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="bd26e-178">[Set-CsClsConfiguration](https://technet.microsoft.com/library/JJ619182(v=OCS.15))</span></span>  
<span data-ttu-id="bd26e-179">[取得-CsClsConfiguration](https://technet.microsoft.com/library/JJ619179(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="bd26e-179">[Get-CsClsConfiguration](https://technet.microsoft.com/library/JJ619179(v=OCS.15))</span></span>  
<span data-ttu-id="bd26e-180">[新しい-CsClsConfiguration](https://technet.microsoft.com/library/JJ619177(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="bd26e-180">[New-CsClsConfiguration](https://technet.microsoft.com/library/JJ619177(v=OCS.15))</span></span>  
<span data-ttu-id="bd26e-181">[削除-CsClsConfiguration](https://technet.microsoft.com/library/JJ619191(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="bd26e-181">[Remove-CsClsConfiguration](https://technet.microsoft.com/library/JJ619191(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

