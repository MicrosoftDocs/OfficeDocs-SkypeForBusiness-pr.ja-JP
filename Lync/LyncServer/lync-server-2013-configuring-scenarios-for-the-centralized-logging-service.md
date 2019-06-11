---
title: 'Lync Server 2013: 一元ログサービスのシナリオを構成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring scenarios for the Centralized Logging Service
ms:assetid: 6c3bf826-e7fd-4002-95dc-01020641ef01
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688085(v=OCS.15)
ms:contentKeyID: 49733682
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: abc0be2ac6459c34546de41ee7e2c709e0d0c0f8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840183"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-scenarios-for-the-centralized-logging-service-in-lync-server-2013"></a><span data-ttu-id="fdb76-102">Lync Server 2013 の一元ログサービスのシナリオを構成する</span><span class="sxs-lookup"><span data-stu-id="fdb76-102">Configuring scenarios for the Centralized Logging Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fdb76-103">_**最終更新日:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="fdb76-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="fdb76-104">シナリオでは、スコープ (つまり、グローバル、サイト、プール、またはコンピューター) と、一元管理サービスで使用するプロバイダーを定義します。</span><span class="sxs-lookup"><span data-stu-id="fdb76-104">Scenarios define the scope (that is, global, site, pool, or computer) and what providers to use in the Centralized Logging Service.</span></span> <span data-ttu-id="fdb76-105">シナリオを使用して、プロバイダー (S4、SIPStack、IM、プレゼンスなど) のトレースを有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="fdb76-105">By using scenarios, you enable or disable tracing on providers (for example, S4, SIPStack, IM, and Presence).</span></span> <span data-ttu-id="fdb76-106">シナリオを構成することで、特定の問題の条件に対応する特定の論理コレクションのすべてのプロバイダーをグループ化できます。</span><span class="sxs-lookup"><span data-stu-id="fdb76-106">By configuring a scenario, you can group all of the providers for a given logical collection that address a specific problem condition.</span></span> <span data-ttu-id="fdb76-107">トラブルシューティングとログのニーズを満たすためにシナリオを変更する必要があることがわかった場合は、Lync Server 2013 デバッグツールによって、dlmigrationmodule.psm1 という名前の関数を含む Windows PowerShell モジュールが提供され*ます。* \*\*.</span><span class="sxs-lookup"><span data-stu-id="fdb76-107">If you find that a scenario needs to be modified to meet your troubleshooting and logging needs, the Lync Server 2013 Debug Tools provides you a Windows PowerShell module named *ClsController.psm1* that contains a function named *Edit-CsClsScenario*.</span></span> <span data-ttu-id="fdb76-108">このモジュールの目的は、指定したシナリオのプロパティを編集することです。</span><span class="sxs-lookup"><span data-stu-id="fdb76-108">The purpose of the module is to edit the properties of the named scenario.</span></span> <span data-ttu-id="fdb76-109">このトピックでは、このモジュールの使用方法の例を示します。</span><span class="sxs-lookup"><span data-stu-id="fdb76-109">Examples of how this module works are provided in this topic.</span></span> <span data-ttu-id="fdb76-110">Lync Server 2013 デバッグツールは、次のリンクからダウンロードされます。[http://go.microsoft.com/fwlink/?LinkId=285257](http://go.microsoft.com/fwlink/?linkid=285257)</span><span class="sxs-lookup"><span data-stu-id="fdb76-110">The Lync Server 2013 Debug Tools are downloaded from the following link: [http://go.microsoft.com/fwlink/?LinkId=285257](http://go.microsoft.com/fwlink/?linkid=285257)</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="fdb76-111">どのスコープ (サイト、グローバル、プール、またはコンピューター) でも、一度に最大で 2 つのシナリオを実行できます。</span><span class="sxs-lookup"><span data-stu-id="fdb76-111">For any given scope—site, global, pool or computer—you can run a maximum of two scenarios at any given time.</span></span> <span data-ttu-id="fdb76-112">現在実行されているシナリオを特定するには、Windows PowerShell と<A href="https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario">Get CsClsScenario シナリオ</A>を使用します。</span><span class="sxs-lookup"><span data-stu-id="fdb76-112">To determine which scenarios are currently running, use Windows PowerShell and <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario">Get-CsClsScenario</A>.</span></span> <span data-ttu-id="fdb76-113">Windows PowerShell と<A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClsScenario">Set-CsClsScenario</A>を使用すると、実行されているシナリオを動的に変更することができます。</span><span class="sxs-lookup"><span data-stu-id="fdb76-113">By using Windows PowerShell and <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClsScenario">Set-CsClsScenario</A>, you can dynamically change which scenarios are running.</span></span> <span data-ttu-id="fdb76-114">ログ セッション中に実行するシナリオを変更して、収集するデータや収集元のプロバイダーを変更または微調整することができます。</span><span class="sxs-lookup"><span data-stu-id="fdb76-114">You can modify which scenarios are running during a logging session to adjust or refine the data you are collecting and from which providers.</span></span>



</div>

<span data-ttu-id="fdb76-115">Lync Server 管理シェルを使用して一元的なログサービスの機能を実行するには、CsAdministrator または CsServerAdministrator の役割ベースのアクセス制御 (RBAC) セキュリティグループのメンバーであるか、または次の2つのグループがあります。</span><span class="sxs-lookup"><span data-stu-id="fdb76-115">To run the Centralized Logging Service functions by using the Lync Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="fdb76-116">このコマンドレットが割り当てられているすべての RBAC ロールの一覧を返すには、自分自身で作成したカスタム RBAC ロールも含めて、Lync Server 管理シェルまたは Windows PowerShell プロンプトから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="fdb76-116">To return a list of all the RBAC roles this cmdlet has been assigned to, including any custom RBAC roles you have created yourself, run the following command from the Lync Server Management Shell or the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

<span data-ttu-id="fdb76-117">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="fdb76-117">For example:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<span data-ttu-id="fdb76-118">このトピックの以降の部分では、トラブルシューティングを最適化するためのシナリオの定義、シナリオの変更、実行中のシナリオの取得、シナリオの削除、シナリオ内容の指定の方法を中心に説明します。</span><span class="sxs-lookup"><span data-stu-id="fdb76-118">The remainder of this topic focuses on how to define a scenario, modify a scenario, retrieve what scenarios are running, remove a scenario, and specify what a scenario contains to optimize your troubleshooting.</span></span> <span data-ttu-id="fdb76-119">一元化されたログサービスのコマンドを発行するには、2つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="fdb76-119">There are two ways to issue Centralized Logging Service commands.</span></span> <span data-ttu-id="fdb76-120">既定で\\は、ディレクトリ C: Program Files\\の共通ファイル\\Microsoft Lync Server 2013\\clscontroller である clscontroller を使うことができます。</span><span class="sxs-lookup"><span data-stu-id="fdb76-120">You can use the CLSController.exe that is located, by default, in the directory C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\CLSAgent.</span></span> <span data-ttu-id="fdb76-121">または、Lync Server 管理シェルを使用して、Windows PowerShell コマンドを発行することもできます。</span><span class="sxs-lookup"><span data-stu-id="fdb76-121">Or, you can use the Lync Server Management Shell to issue Windows PowerShell commands.</span></span> <span data-ttu-id="fdb76-122">重要な違いは、コマンドラインで CLSController を使う場合、利用可能なシナリオが限られていることです。</span><span class="sxs-lookup"><span data-stu-id="fdb76-122">The important distinction is that when you use CLSController.exe at the command line there is a finite selection of scenarios available.</span></span> <span data-ttu-id="fdb76-123">Windows PowerShell を使用する場合は、ログセッションで使用する新しいシナリオを定義できます。</span><span class="sxs-lookup"><span data-stu-id="fdb76-123">When you use Windows PowerShell, you can define new scenarios for use in your logging sessions.</span></span>

<span data-ttu-id="fdb76-124">[Lync Server 2013 の中央集中ログサービスの概要](lync-server-2013-overview-of-the-centralized-logging-service.md)で紹介したように、シナリオの要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="fdb76-124">As introduced in [Overview of the Centralized Logging Service in Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md), the elements of a scenario are:</span></span>

  - <span data-ttu-id="fdb76-125">**プロバイダー**   ocslogger に精通している場合、プロバイダーは、トレースエンジンがログを収集する必要があることを ocslogger に伝えるために選ぶコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="fdb76-125">**Providers**   If you are familiar with OCSLogger, providers are the components that you choose to tell OCSLogger what the tracing engine should collect logs from.</span></span> <span data-ttu-id="fdb76-126">プロバイダーは同じコンポーネントであり、多くの場合、OCSLogger のコンポーネントと同じ名前が付いています。</span><span class="sxs-lookup"><span data-stu-id="fdb76-126">The providers are the same components, and in many cases have the same name as the components in OCSLogger.</span></span> <span data-ttu-id="fdb76-127">OCSLogger に精通していない場合は、中央のログサービスがログを収集できるサーバーの役割固有のコンポーネントはプロバイダーです。</span><span class="sxs-lookup"><span data-stu-id="fdb76-127">If you are not familiar with OCSLogger, providers are server role specific components that the Centralized Logging Service can collect logs from.</span></span> <span data-ttu-id="fdb76-128">プロバイダーの構成の詳細については、「 [Lync Server 2013 で中央集中ログサービスのプロバイダーを構成する](lync-server-2013-configuring-providers-for-centralized-logging-service.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fdb76-128">For details about the configuration of providers, see [Configuring providers for Centralized Logging Service in Lync Server 2013](lync-server-2013-configuring-providers-for-centralized-logging-service.md).</span></span>

  - <span data-ttu-id="fdb76-129">**Identity**   パラメーター– identity は、シナリオのスコープと名前を設定します。</span><span class="sxs-lookup"><span data-stu-id="fdb76-129">**Identity**   The parameter –Identity sets the scope and name of the scenario.</span></span> <span data-ttu-id="fdb76-130">たとえば、"グローバル" のスコープを設定し、"LyssServiceScenario" を使ってシナリオを特定することができます。</span><span class="sxs-lookup"><span data-stu-id="fdb76-130">For example, you could set a scope of “global” and identify the scenario with “LyssServiceScenario”.</span></span> <span data-ttu-id="fdb76-131">この2つを組み合わせると、Id (たとえば、"global/LyssServiceScenario") が定義されます。</span><span class="sxs-lookup"><span data-stu-id="fdb76-131">When you combine the two, you define the Identity (for example, “global/LyssServiceScenario”).</span></span>
    
    <span data-ttu-id="fdb76-p107">また、-Name パラメーターと -Parent パラメーターを使用することもできます。Name パラメーターは、シナリオを一意に識別するために定義します。Name を使用する場合は、Parent も使用して、グローバルまたはサイトにシナリオを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fdb76-p107">Optionally, you can use the –Name and –Parent parameters. You define the Name parameter to uniquely identify the scenario. If you use Name, you must also use Parent to add the scenario to either global or site.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="fdb76-135">Name パラメーターと Parent パラメーターを使用する場合は、<STRONG>-Identity</STRONG> パラメーターは使用できません。</span><span class="sxs-lookup"><span data-stu-id="fdb76-135">If you use the Name and Parent parameters, you cannot use the <STRONG>–Identity</STRONG> parameter.</span></span>

    
    </div>

<div>

## <a name="to-create-a-new-scenario-with-the-new-csclsscenario-cmdlet"></a><span data-ttu-id="fdb76-136">New-CsClsScenario コマンドレットを使用して新しいシナリオを作成するには</span><span class="sxs-lookup"><span data-stu-id="fdb76-136">To create a new scenario with the New-CsClsScenario cmdlet</span></span>

1.  <span data-ttu-id="fdb76-137">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="fdb76-137">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="fdb76-p108">ログ セッションのための新しいシナリオを作成するには、[New-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/New-CsClsProvider) を使用し、シナリオの名前 (シナリオを一意に識別する方法) を定義します。ログ形式の種類を、WPP (Windows ソフトウェア トレース プリプロセッサ。これが既定値です)、EventLog (Windows イベント ログ形式)、または IISLog (IIS ログ ファイル形式に基づく ASCII 形式ファイル) から選択します。次に、レベル (このトピックのログ レベルの説明で定義されています) とフラグ (このトピックのフラグの説明で定義されています) を定義します。</span><span class="sxs-lookup"><span data-stu-id="fdb76-p108">To create a new scenario for a logging session, use [New-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/New-CsClsProvider) and define the name of the scenario (that is, how it will be uniquely identified). Choose a type of logging format from WPP (that is, Windows software tracing preprocessor and is the default), EventLog (that is, Windows event log format), or IISLog (that is, ASCII format file based on the IIS log file format). Next, define Level (as the defined under Logging Levels in this topic), and Flags (as defined under Flags in this topic).</span></span>
    
    <span data-ttu-id="fdb76-141">このシナリオ例では、プロバイダー変数の例として LyssProvider を使用します。</span><span class="sxs-lookup"><span data-stu-id="fdb76-141">For this example scenario, we use LyssProvider as the example provider variable.</span></span>
    
    <span data-ttu-id="fdb76-142">定義されたオプションを使用してシナリオを作成するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="fdb76-142">To create a scenario using the options defined, type:</span></span>
    
        New-CsClsScenario -Identity <scope>/<unique scenario name> -Provider <provider variable>
    
    <span data-ttu-id="fdb76-143">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="fdb76-143">For example:</span></span>
    
        New-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider $LyssProvider
    
    <span data-ttu-id="fdb76-144">代わりに、次のように -Name と -Parent を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="fdb76-144">The alternate format using –Name and –Parent:</span></span>
    
        New-CsClsScenario -Name "LyssServiceScenario" -Parent "site:Redmond" -Provider $LyssProvider

</div>

<div>

## <a name="to-create-a-new-scenario-with-multiple-providers-with-the-new-csclsscenario-cmdlet"></a><span data-ttu-id="fdb76-145">複数のプロバイダーを指定した新しいシナリオを New-CsClsScenario コマンドレットを使用して作成するには</span><span class="sxs-lookup"><span data-stu-id="fdb76-145">To create a new scenario with multiple providers with the New-CsClsScenario cmdlet</span></span>

1.  <span data-ttu-id="fdb76-146">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="fdb76-146">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="fdb76-147">スコープごとのシナリオ数は 2 つまでに制限されています。</span><span class="sxs-lookup"><span data-stu-id="fdb76-147">You are limited to two scenarios per scope.</span></span> <span data-ttu-id="fdb76-148">しかし、設定するプロバイダーの数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="fdb76-148">However, you are not limited to a set number of providers.</span></span> <span data-ttu-id="fdb76-149">この例では、3 つのプロバイダーを作成済みで、定義するシナリオに 3 つのプロバイダーをすべて割り当てる必要があるとします。</span><span class="sxs-lookup"><span data-stu-id="fdb76-149">In this example, assume that we have created three providers, and you want to assign all three to the scenario you are defining.</span></span> <span data-ttu-id="fdb76-150">プロバイダー変数の名前は LyssProvider、ABServerProvider、および SIPStackProvider です。</span><span class="sxs-lookup"><span data-stu-id="fdb76-150">The provider variable names are LyssProvider, ABServerProvider, and SIPStackProvider.</span></span> <span data-ttu-id="fdb76-151">1つのシナリオに複数のプロバイダーを定義して割り当てるには、Lync Server 管理シェルまたは Windows PowerShell コマンドプロンプトで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="fdb76-151">To define and assign multiple providers to a scenario, type the following at a Lync Server Management Shell or Windows PowerShell command prompt:</span></span>
    
        New-CsClsScenario -Identity "site:Redmond/CollectDataScenario" -Provider @{Add=$LyssProvider, $ABServerProvider,  $SIPStackProvider}
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fdb76-152">Windows PowerShell で知っているように、値のハッシュテーブルを作成するための<CODE>@{&lt;variable&gt;=&lt;value1&gt;, &lt;value2&gt;, &lt;value&gt;...}</CODE>規則は、 <EM>splatting</EM>と呼ばれています。</span><span class="sxs-lookup"><span data-stu-id="fdb76-152">As it is known in Windows PowerShell, the convention for creating a hash table of values using <CODE>@{&lt;variable&gt;=&lt;value1&gt;, &lt;value2&gt;, &lt;value&gt;...}</CODE> is known as <EM>splatting</EM>.</span></span> <span data-ttu-id="fdb76-153">Windows PowerShell での splatting の詳細につい<A href="http://go.microsoft.com/fwlink/p/?linkid=267760">http://go.microsoft.com/fwlink/p/?LinkId=267760</A>ては、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fdb76-153">For details about splatting in Windows PowerShell, see <A href="http://go.microsoft.com/fwlink/p/?linkid=267760">http://go.microsoft.com/fwlink/p/?LinkId=267760</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="to-modify-an-existing-scenario-with-the-set-csclsscenario-cmdlet"></a><span data-ttu-id="fdb76-154">Set-CsClsScenario コマンドレットを使用して既存のシナリオを変更するには</span><span class="sxs-lookup"><span data-stu-id="fdb76-154">To modify an existing scenario with the Set-CsClsScenario cmdlet</span></span>

1.  <span data-ttu-id="fdb76-155">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="fdb76-155">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="fdb76-p111">スコープごとのシナリオ数は 2 つまでに制限されています。実行するシナリオは、ログ キャプチャ セッションの実行中を含め、いつでも変更できます。実行するシナリオを再定義すると、現在のログ セッションは削除されたシナリオの使用を停止し、新しいシナリオの使用を開始します。ただし、削除されたシナリオでキャプチャされたログ情報はキャプチャされたログに残ります。新しいシナリオを定義するには、次のようにします (ここでは、定義済みのプロバイダー "S4Provider" を追加するものとします)。</span><span class="sxs-lookup"><span data-stu-id="fdb76-p111">You are limited to two scenarios per scope. You can change which scenarios are running at any time, even when a logging capture session is in process. If you redefine the running scenarios, the current logging session will stop using the scenario that was removed and then begin using the new scenario. However, the logging information that was captured with the removed scenario remains in the captured logs. To define a new scenario, do the following (that is, assuming the addition of an already defined provider named “S4Provider”):</span></span>
    
        Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Add=<new provider to add>}
    
    <span data-ttu-id="fdb76-161">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="fdb76-161">For example:</span></span>
    
        Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Add=$S4Provider}
    
    <span data-ttu-id="fdb76-p112">プロバイダーを置き換える場合は、現在のセットと置き換える単一のプロバイダーか、プロバイダーのコンマ区切りリストを定義します。多数のプロバイダーのうち 1 つだけを置き換える場合は、現在のプロバイダーに新しいプロバイダーを追加して、新しいプロバイダーと既存のプロバイダーの両方を含む新しいプロバイダーのセットを作成します。すべてのプロバイダーを新しいセットで置き換える場合は、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="fdb76-p112">If you want to replace providers, define a single provider or a comma separated list of providers to replace the current set. If you only want to replace one of many providers, add the current providers with the new providers to create a new set of providers that contains both new providers and existing providers. To replace all providers with a new set, type the following:</span></span>
    
        Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Replace=<providers to replace existing provider set>}
    
    <span data-ttu-id="fdb76-165">たとえば、現在の $LyssProvider、$ABServerProvider、および $SIPStackProvider のセットを $LyssServiceProvider に置き換えるには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="fdb76-165">For example, to replace the current set of $LyssProvider, $ABServerProvider, and $SIPStackProvider with $LyssServiceProvider:</span></span>
    
        Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider}
    
    <span data-ttu-id="fdb76-166">現在の $LyssProvider、$ABServerProvider、および $SIPStackProvider のセットのうち、$LyssProvider プロバイダーだけを $LyssServiceProvider に置き換えるには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="fdb76-166">To replace just the $LyssProvider provider from the current set of $LyssProvider, $ABServerProvider, and $SIPStackProvider with $LyssServiceProvider, type the following:</span></span>
    
        Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider, $ABServerProvider, $SIPStackProvider}

</div>

<div>

## <a name="to-remove-an-existing-scenario-with-the-remove-csclsscenario-cmdlet"></a><span data-ttu-id="fdb76-167">Remove-CsClsScenario コマンドレットを使用して既存のシナリオを削除するには</span><span class="sxs-lookup"><span data-stu-id="fdb76-167">To remove an existing scenario with the Remove-CsClsScenario cmdlet</span></span>

1.  <span data-ttu-id="fdb76-168">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="fdb76-168">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="fdb76-169">定義済みのシナリオを削除する場合は、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="fdb76-169">If you want to remove a scenario that has been previously defined, type the following:</span></span>
    
        Remove-CsClsScenario -Identity <name of scope and scenario>
    
    <span data-ttu-id="fdb76-170">たとえば、定義済みのシナリオ site:Redmond/LyssServiceScenario を削除するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="fdb76-170">For example, to remove the defined scenario site:Redmond/LyssServiceScenario:</span></span>
    
        Remove-CsClsScenario -Identity "site:Redmond/LyssServiceScenario"

<span data-ttu-id="fdb76-171">**Remove-CsClsScenario** コマンドレットでは指定したシナリオが削除されますが、キャプチャ済みのトレースはログに残り、検索に利用できます。</span><span class="sxs-lookup"><span data-stu-id="fdb76-171">The **Remove-CsClsScenario** cmdlet removes the specified scenario, but the traces that have been captured are still available in the logs for you to search on.</span></span>

</div>

<div>

## <a name="to-load-and-unload-the-edit-csclsscenario-cmdlet-using-the-clscontrollerpsm1-module"></a><span data-ttu-id="fdb76-172">Dlmigrationmodule.psm1 モジュールを使用して、を編集して、編集してください。</span><span class="sxs-lookup"><span data-stu-id="fdb76-172">To load and unload the Edit-CsClsScenario cmdlet using the ClsController.psm1 module</span></span>

1.  <span data-ttu-id="fdb76-173">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="fdb76-173">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="fdb76-174">Dlmigrationmodule.psm1 モジュールは、個別の Web ダウンロードとして提供されます。</span><span class="sxs-lookup"><span data-stu-id="fdb76-174">The ClsController.psm1 module is provided as a separate Web download.</span></span> <span data-ttu-id="fdb76-175">このモジュールは、Lync Server 2013 デバッグツールの一部です。</span><span class="sxs-lookup"><span data-stu-id="fdb76-175">The module is part of the Lync Server 2013 Debugging tools.</span></span> <span data-ttu-id="fdb76-176">既定では、デバッグツールはディレクトリ C:\Program Files\Lync Server 2013 \ デバッグツールにインストールされています。</span><span class="sxs-lookup"><span data-stu-id="fdb76-176">By default, the debugging tools are installed in the directory C:\Program Files\Lync Server 2013\Debugging Tools.</span></span>

    
    </div>

2.  <span data-ttu-id="fdb76-177">Windows PowerShell で次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="fdb76-177">From the Windows PowerShell, type:</span></span>
    
        Import-Module "C:\Program Files\Lync Server 2013\Debugging Tools\ClsController.psm1"
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="fdb76-178">モジュールの読み込みが成功すると、Windows PowerShell コマンドプロンプトに戻ります。</span><span class="sxs-lookup"><span data-stu-id="fdb76-178">Successful loading of the module returns you to the Windows PowerShell command prompt.</span></span> <span data-ttu-id="fdb76-179">モジュールが読み込まれていること、および編集-CsClsScenario が利用可能<CODE>Get-Help Edit-CsClsScenario</CODE>であることを確認するには、「」と入力します。</span><span class="sxs-lookup"><span data-stu-id="fdb76-179">To confirm that the module is loaded and that Edit-CsClsScenario is available, type <CODE>Get-Help Edit-CsClsScenario</CODE>.</span></span> <span data-ttu-id="fdb76-180">すると、EditCsClsScenario の構文の基本的な概要が表示されます。</span><span class="sxs-lookup"><span data-stu-id="fdb76-180">You should see the basic synopsis of the syntax for EditCsClsScenario.</span></span>

    
    </div>

3.  <span data-ttu-id="fdb76-181">モジュールをアンロードするには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="fdb76-181">To unload the modules, type:</span></span>
    
        Remove-Module ClsController
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="fdb76-182">モジュールを正常にアンロードすると、Windows PowerShell コマンドプロンプトに戻ります。</span><span class="sxs-lookup"><span data-stu-id="fdb76-182">Successful unloading of the module returns you to the Windows PowerShell command prompt.</span></span> <span data-ttu-id="fdb76-183">モジュールがアンロードされたことを確認<CODE>Get-Help Edit-CsClsScenario</CODE>するには、「」と入力します。</span><span class="sxs-lookup"><span data-stu-id="fdb76-183">To confirm that the module is unloaded, type <CODE>Get-Help Edit-CsClsScenario</CODE>.</span></span> <span data-ttu-id="fdb76-184">Windows PowerShell は、コマンドレットのヘルプを検索して失敗します。</span><span class="sxs-lookup"><span data-stu-id="fdb76-184">Windows PowerShell will attempt to locate the help for the cmdlet and fail.</span></span>

    
    </div>

</div>

<div>

## <a name="to-remove-an-existing-provider-from-a-scenario-with-the-edit-clscontroller-module"></a><span data-ttu-id="fdb76-185">Edit-ClsController モジュールを使用してシナリオから既存のプロバイダーを削除するには</span><span class="sxs-lookup"><span data-stu-id="fdb76-185">To remove an existing provider from a scenario with the Edit-ClsController module</span></span>

1.  <span data-ttu-id="fdb76-186">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="fdb76-186">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="fdb76-187">AlwaysOn シナリオからプロバイダーを削除するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="fdb76-187">To remove a provider from the AlwaysOn scenario, type:</span></span>
    
        Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to remove> -Remove
    
    <span data-ttu-id="fdb76-188">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="fdb76-188">For Example:</span></span>
    
        Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Remove
    
    <span data-ttu-id="fdb76-p116">パラメーター ScenarioName および ProviderName は、位置指定 (コマンド ライン内の指定された位置に定義する必要がある) パラメーターです。コマンドレット名を位置 1 として、シナリオ名が位置 2、プロバイダーが位置 3 にある場合は、パラメーター名を明示的に定義する必要はありません。この情報を使用すると、上記のコマンドは次のように入力できます。</span><span class="sxs-lookup"><span data-stu-id="fdb76-p116">The parameters ScenarioName and ProviderName are positional (that is, they must be defined in the expected position in the command line) parameters. The parameter name does not have to be explicitly defined if the scenario name is in position two and the provider is in position three, relative to the name of the cmdlet as position one. Using this information, the previous command would be typed as:</span></span>
    
        Edit-CsClsScenario AlwaysOn ChatServer -Remove
    
    <span data-ttu-id="fdb76-p117">パラメーター値の位置指定は、-Scenario と -Provider にのみ適用されます。他のすべてのパラメーターは明示的に定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fdb76-p117">The positional placing of the parameter values applies only to –Scenario and –Provider. All other parameters must be explicitly defined.</span></span>

</div>

<div>

## <a name="to-add-a-provider-to-a-scenario-with-the-edit-clscontroller-module"></a><span data-ttu-id="fdb76-194">Edit-ClsController モジュールを使用してシナリオにプロバイダーを追加するには</span><span class="sxs-lookup"><span data-stu-id="fdb76-194">To add a provider to a scenario with the Edit-ClsController module</span></span>

1.  <span data-ttu-id="fdb76-195">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="fdb76-195">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="fdb76-196">AlwaysOn シナリオにプロバイダーを追加するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="fdb76-196">To add a provider to the AlwaysOn scenario, type:</span></span>
    
        Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to add> -Level <string of type level> -Flags <string of type flags>
    
    <span data-ttu-id="fdb76-197">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="fdb76-197">For Example:</span></span>
    
        Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Level Info -Flags TF_COMPONENT
    
    <span data-ttu-id="fdb76-198">\-Loglevel は、Fatal、エラー、警告、Info、Verbose、Debug、または All の型にすることができます。</span><span class="sxs-lookup"><span data-stu-id="fdb76-198">\-Loglevel can be of the type Fatal, Error, Warning, Info, Verbose, Debug, or All.</span></span> <span data-ttu-id="fdb76-199">– Flags には、TF\_COMPONENT、tf\_DIAG など、プロバイダーがサポートするすべてのフラグを指定できます。</span><span class="sxs-lookup"><span data-stu-id="fdb76-199">–Flags can be any of the flags that the provider supports, such as TF\_COMPONENT, TF\_DIAG.</span></span> <span data-ttu-id="fdb76-200">また、値 ALL も指定できます。</span><span class="sxs-lookup"><span data-stu-id="fdb76-200">–Flags can also be of value ALL</span></span>
    
    <span data-ttu-id="fdb76-p119">上記の例を、コマンドレットの位置指定機能を使用して入力することもできます。たとえば、プロバイダー ChatServer を AlwaysOn シナリオに追加するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="fdb76-p119">The previous example can also be typed using the positional feature of the cmdlet. For example, to add the provider ChatServer to the AlwaysOn scenario, type:</span></span>
    
        Edit-CsClsScenario AlwaysOn ChatServer -Level Info -Flags ALL

</div>

</div>

<span> </span>

</div>

</div>

</div>

