---
title: 共存シナリオでの Lync Server 2010 管理パックの使用
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Lync Server 2010 management packs in a coexistence scenario
ms:assetid: 8b792503-bd88-47fe-9d97-b071e8d429a5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205078(v=OCS.15)
ms:contentKeyID: 48184772
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 264cd8f1495840eb6dd86879f279110cd4de4784
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743887"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-lync-server-2010-management-packs-in-a-coexistence-scenario"></a><span data-ttu-id="7566f-102">共存シナリオでの Lync Server 2010 管理パックの使用</span><span class="sxs-lookup"><span data-stu-id="7566f-102">Using the Lync Server 2010 management packs in a coexistence scenario</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7566f-103">_**最終更新日:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="7566f-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="7566f-104">多くのお客様は、ユーザーが Microsoft Lync Server 2010 から Lync Server 2013 に段階的に移行されている組織内でロールアウトプログラムを採用しています。</span><span class="sxs-lookup"><span data-stu-id="7566f-104">Many customers adopt a rollout program inside of their enterprises in which users are progressively migrated from Microsoft Lync Server 2010 to Lync Server 2013.</span></span> <span data-ttu-id="7566f-105">これらの会社の管理者は、両方のバージョンの Lync Server を監視して、すべてのエンドユーザーが最高のコミュニケーションエクスペリエンスを実現できるようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7566f-105">The administrators at these companies will care about monitoring both versions of Lync Server to help ensure that all of their end users are getting the best possible communication experience.</span></span> <span data-ttu-id="7566f-106">このシナリオでは、Lync Server 2013 管理パックは、Lync Server 2010 管理パックを使用してサイドバイサイドの移行パスをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="7566f-106">For this scenario, the Lync Server 2013 Management Pack supports a side-by-side migration path with the Lync Server 2010 Management Pack.</span></span>

<span data-ttu-id="7566f-107">Lync server 2010 では、Lync Server コンピューターは、中央管理ストアに保存されているトポロジドキュメントを通じて検出されました。</span><span class="sxs-lookup"><span data-stu-id="7566f-107">In the Lync Server 2010, Lync Server computers were discovered through the topology document stored with the Central Management store.</span></span> <span data-ttu-id="7566f-108">この構成では、1台のコンピューターで他のすべての Lync Server コンピューターの存在が報告されます。</span><span class="sxs-lookup"><span data-stu-id="7566f-108">In this configuration, a single computer would report the existence of all the other Lync Server computers.</span></span>

<span data-ttu-id="7566f-109">Lync server 2013 用の管理パックで、Lync Server 2010 で使用されていたセントラル探索メカニズムではなく、マシンレベルの検出が使用されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="7566f-109">The management packs for Lync Server 2013 now use machine-level discovery instead of the central discovery mechanism that was used in Lync Server 2010.</span></span> <span data-ttu-id="7566f-110">つまり、各 System Center agent は基本的に自分自身を検出し、System Center Operations Manager にその存在を報告します。</span><span class="sxs-lookup"><span data-stu-id="7566f-110">This means that each System Center agent essentially discovers itself and reports its existence to System Center Operations Manager.</span></span> <span data-ttu-id="7566f-111">マシンレベルの検出を使用すると、System Center インフラストラクチャの管理が簡単になり、さまざまなバージョンの Lync Server 管理パック (たとえば、lync Server 2010 用の管理パックと Lync Server 2013 用の管理パック) も有効になります。より簡単になります。</span><span class="sxs-lookup"><span data-stu-id="7566f-111">Using machine-level discovery simplifies administration of your System Center infrastructure and also enables different versions of the Lync Server management packs (for example, management packs for Lync Server 2010 and management packs for Lync Server 2013) to coexist more easily.</span></span>

<span data-ttu-id="7566f-112">この移行をサポートするには、最初に既存の Lync Server 2010 監視をアップグレードして、範囲内のギャップを回避する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7566f-112">To support this migration, you will first need to upgrade your existing Lync Server 2010 monitoring to avoid gaps in coverage.</span></span> <span data-ttu-id="7566f-113">これを行うには、既存の Lync Server 2010 コンピューターを選択して、中央管理ストアを Lync Server 2013 にアップグレードする前に、Lync Server 2010 のセントラル探索スクリプトを処理するようにします。</span><span class="sxs-lookup"><span data-stu-id="7566f-113">To do this, elect an existing Lync Server 2010 computer to service the Central Discovery script for the Lync Server 2010 before upgrading your Central Management store to Lync Server 2013.</span></span> <span data-ttu-id="7566f-114">これは、4つのステップからなるプロセスです。</span><span class="sxs-lookup"><span data-stu-id="7566f-114">This is a four-step process:</span></span>

1.  <span data-ttu-id="7566f-115">Lync Server 2010 管理パックを累積更新プログラム7にアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="7566f-115">Upgrade the Lync Server 2010 Management Packs to Cumulative Update 7.</span></span>

2.  <span data-ttu-id="7566f-116">Lync Server 2010 コンピューターに、セントラル探索スクリプトを実行するように指示します。</span><span class="sxs-lookup"><span data-stu-id="7566f-116">Instruct a Lync Server 2010 computer to run the Central Discovery script.</span></span>

3.  <span data-ttu-id="7566f-117">Microsoft Lync Server 2010 管理パックのセントラル探索候補を上書きします。</span><span class="sxs-lookup"><span data-stu-id="7566f-117">Override the Central Discovery Candidate in the Microsoft Lync Server 2010 Management Pack.</span></span>

4.  <span data-ttu-id="7566f-118">新しいセントラル検出候補が検出されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="7566f-118">Verify that the new Central Discovery Candidate has been discovered.</span></span>

<div>

## <a name="instructing-a-lync-server-2010-computer-to-run-the-central-discovery-script"></a><span data-ttu-id="7566f-119">セントラル探索スクリプトを実行するように Lync Server 2010 コンピューターに指示する</span><span class="sxs-lookup"><span data-stu-id="7566f-119">Instructing a Lync Server 2010 Computer to Run the Central Discovery script</span></span>

<span data-ttu-id="7566f-120">中央の検出を処理するために、中央管理ストア以外のコンピューター (たとえば、Lync Server フロントエンド) サーバーを指名するには、次のレジストリキーをサーバーの非セントラル管理ストアサーバーに作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7566f-120">To nominate a non-Central Management store computer (for example, a Lync Server Front End) server to handle central discovery, you will need to create the following registry key on the non-Central Management store server:</span></span>

<span data-ttu-id="7566f-121">HKLM\\ソフトウェア\\Microsoft\\リアルタイム通信\\正常性\\CentralDiscoveryCandidate</span><span class="sxs-lookup"><span data-stu-id="7566f-121">HKLM\\Software\\Microsoft\\Real-Time Communications\\Health\\CentralDiscoveryCandidate</span></span>

<span data-ttu-id="7566f-122">このレジストリキーを作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="7566f-122">You can create this registry key by completing the following procedure:</span></span>

1.  <span data-ttu-id="7566f-123">[**スタート**] をクリックし、[**実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7566f-123">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="7566f-124">[**実行**] ダイアログボックスで、「 **regedit** 」と入力し、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="7566f-124">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="7566f-125">レジストリエディターで、[ **HKEY\_ローカル\_コンピューター**]、[**ソフトウェア**]、[ **Microsoft**] の順に展開し、[**リアルタイム通信**] を展開します。</span><span class="sxs-lookup"><span data-stu-id="7566f-125">In Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SOFTWARE**, expand **Microsoft**, and then expand **Real-Time Communications**.</span></span>

4.  <span data-ttu-id="7566f-126">[**正常性**] を右クリックし、[**新規作成**] をクリックして、[**キー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7566f-126">Right-click **Health**, click **New**, and then click **Key**.</span></span> <span data-ttu-id="7566f-127">**正常性**キーが存在しない場合は、**リアルタイム通信**を右クリックし、[**新規作成**] をポイントして、[**キー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7566f-127">If the **Health** key does not exist, then right-click **Real-Time Communications**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="7566f-128">新しいキーが作成されたら、「Health」と入力して、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="7566f-128">When the new key is created, type Health, and then press ENTER.</span></span>
    
    <span data-ttu-id="7566f-129">新しいキーを作成したら、「 **CentralDiscoveryCandidate** 」と入力し、enter キーを押してキーの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="7566f-129">After the new key has been created, type **CentralDiscoveryCandidate** and then press ENTER to rename the key.</span></span>

<span data-ttu-id="7566f-130">この変更を選択するには、コンピューターに数時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="7566f-130">It may take the computer several hours to pick up this change.</span></span> <span data-ttu-id="7566f-131">変更をすぐに有効にするには、正常性エージェントサービスを停止してから再起動します。</span><span class="sxs-lookup"><span data-stu-id="7566f-131">To make the change take effect immediately, stop and then restart the Health Agent service.</span></span> <span data-ttu-id="7566f-132">正常性エージェントサービスを再起動するには、Lync Server 2010 コンピューターで次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="7566f-132">To restart the Health Agent service, complete the following procedure on the Lync Server 2010 computer:</span></span>

1.  <span data-ttu-id="7566f-133">[**スタート**] をクリックし、[**すべてのプログラム**]、[**アクセサリ**]、[**コマンドプロンプト**] を右クリックして、[**管理者として実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7566f-133">Click **Start**, click **All Programs**, click **Accessories**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="7566f-134">コンソールウィンドウで、次のコマンドを入力し、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="7566f-134">In the console window, type the following command and then press ENTER:</span></span>
    
        Net stop HealthService

3.  <span data-ttu-id="7566f-135">"System Center 管理サービスは停止しています" というメッセージが表示され、その後にサービスが停止されたことを示す2番目のメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7566f-135">You will see a message that states "The System Center Management service is stopping," followed by a second message that tells you that the service has been stopped.</span></span> <span data-ttu-id="7566f-136">サービスが停止した後、次のコマンドを入力して ENTER キーを押すと、サービスを再起動できます。</span><span class="sxs-lookup"><span data-stu-id="7566f-136">After the service has stopped, you can restart it by typing the following command and pressing ENTER:</span></span>
    
        Net start HealthService

</div>

<div>

## <a name="overriding-the-central-discovery-candidate-in-the-lync-server-2010-management-pack"></a><span data-ttu-id="7566f-137">Lync Server 2010 管理パックでの中央の検出候補の上書き</span><span class="sxs-lookup"><span data-stu-id="7566f-137">Overriding the Central Discovery Candidate in the Lync Server 2010 Management Pack</span></span>

<span data-ttu-id="7566f-138">Lync server 2010 コンピューターに Lync Server 2010 コンピューターについて報告するように指示した後、lync Server 2010 管理パックにもこの変更について通知する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7566f-138">After instructing a Lync Server 2010 computer to report on Lync Server 2010 computers, you will need to inform the Lync Server 2010 Management Pack about this change as well.</span></span> <span data-ttu-id="7566f-139">これを行うには、管理パックで上書きを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7566f-139">To do this, you will need to create an override in the Management Pack.</span></span> <span data-ttu-id="7566f-140">この操作を行うには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="7566f-140">That can be done by completing the following procedure:</span></span>

1.  <span data-ttu-id="7566f-141">Operations Manager コンソールで、[**作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7566f-141">In the Operations Manager console, click **Authoring**.</span></span>

2.  <span data-ttu-id="7566f-142">[作成] タブで [**管理パックオブジェクト**] を展開し、[**オブジェクト**検出] をクリックして、[**スコープ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7566f-142">On the Authoring tab, expand **Management Pack Objects**, click **Object Discoveries**, and then click **Scope**.</span></span>

3.  <span data-ttu-id="7566f-143">[ **Scope Management Pack Objects** ] ダイアログボックスで、対象の**LS 検出候補**を含むアイテムを選び、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7566f-143">In the **Scope Management Pack Objects** dialog box, select the item with the Target **LS Discovery Candidate** and then click **OK**.</span></span> <span data-ttu-id="7566f-144">LS 検出候補は、Lync Server 2010 管理パックをインストールしている場合にのみ表示されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="7566f-144">Note that LS Discovery Candidate will appear only if you have installed the Lync Server 2010 Management Pack.</span></span>

4.  <span data-ttu-id="7566f-145">Operations Manager コンソールで、[ **LS 検出候補** **] を右**クリックし、[上書き] をポイントして、[**オブジェクト検出の上書き**] をポイントし、[ **class: LS 検出候補のすべてのオブジェクト**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7566f-145">In the Operations Manager console, right-click **LS Discovery Candidate**, point to **Overrides**, point to **Override the Object Discovery**, and then click **For all objects of class: LS Discovery Candidate**.</span></span>

5.  <span data-ttu-id="7566f-146">[**プロパティの上書き**] ダイアログボックスで、[ **Central Discovery WatcherNode Fqdn**] の横にある [**上書き**] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="7566f-146">In the **Override Properties** dialog box, select the **Override** check box next to the parameter **Central Discovery WatcherNode Fqdn**.</span></span> <span data-ttu-id="7566f-147">[**上書き値**] ボックスと [**有効な値**] ボックスに、Lync Server 2010 コンピューターの完全修飾ドメイン名を入力します。</span><span class="sxs-lookup"><span data-stu-id="7566f-147">Type the fully qualified domain name of the Lync Server 2010 computer in the **Override Value** and **Effective Value** boxes.</span></span> <span data-ttu-id="7566f-148">[**強制**] チェックボックスをオンにし、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7566f-148">Select the **Enforced** check box and click **OK**.</span></span>

<span data-ttu-id="7566f-149">上書きを作成したら、ルート管理サーバーで正常性サービスを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7566f-149">After you have created the override, you need to restart the health service on the Root Management Server.</span></span> <span data-ttu-id="7566f-150">正常性サービスを再起動するには、ルート管理サーバーで次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="7566f-150">To restart the health service, complete the following procedure on the Root Management Server:</span></span>

1.  <span data-ttu-id="7566f-151">[**スタート**] をクリックし、[**すべてのプログラム**]、[**アクセサリ**]、[**コマンドプロンプト**] を右クリックして、[**管理者として実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7566f-151">Click **Start**, click **All Programs**, click **Accessories**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="7566f-152">コンソールウィンドウで、次のコマンドを入力し、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="7566f-152">In the console window, type the following command, and then press ENTER:</span></span>
    
        Net stop HealthService

3.  <span data-ttu-id="7566f-153">"System Center 管理サービスは停止しています" というメッセージが表示され、その後にサービスが停止されたことを示す2番目のメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7566f-153">You will see a message stating that "The System Center Management service is stopping," followed by a second message that tells you that the service has been stopped.</span></span> <span data-ttu-id="7566f-154">サービスが停止した後、次のコマンドを入力して ENTER キーを押すと、サービスを再起動できます。</span><span class="sxs-lookup"><span data-stu-id="7566f-154">After the service has stopped, you can then restart it by typing the following command and pressing ENTER:</span></span>
    
        Net start HealthService

</div>

<div>

## <a name="verifying-that-the-new-central-discovery-candidate-was-discovered"></a><span data-ttu-id="7566f-155">新しいセントラル探索候補が検出されたことを確認する</span><span class="sxs-lookup"><span data-stu-id="7566f-155">Verifying that the New Central Discovery Candidate Was Discovered</span></span>

<span data-ttu-id="7566f-156">全体管理ストアをアップグレードする前の最後の手順では、新しいセントラル探索候補が Lync Server 2010 管理パックによって検出されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="7566f-156">The final step before upgrading Central Management store is to make sure that the new central discovery candidate was discovered by the Lync Server 2010 Management Pack.</span></span> <span data-ttu-id="7566f-157">これを行うには、Operations Manager コンソールを開き、[監視] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7566f-157">To do this, open the Operations Manager console and then click Monitoring.</span></span> <span data-ttu-id="7566f-158">[監視] タブで、[ **Microsoft Lync Server 2010 正常性**] を展開し、[**トポロジの検出**] を展開して、[**検出状態の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7566f-158">On the Monitoring tab, expand **Microsoft Lync Server 2010 Health**, expand **Topology Discovery**, and then click **Discovery State View**.</span></span> <span data-ttu-id="7566f-159">表示される行に、セントラル検出候補の完全修飾ドメイン名を一覧表示する**パス**が含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7566f-159">Verify that a row in the display has a **Path** that lists the fully qualified domain name of the central discovery candidate.</span></span> <span data-ttu-id="7566f-160">また、コンピューターの状態が**正常**であると報告されていることも確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7566f-160">You should also verify that the computer state is reported as **Healthy**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

