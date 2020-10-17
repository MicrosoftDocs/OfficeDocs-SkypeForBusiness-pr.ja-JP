---
title: 共存シナリオでの Lync Server 2010 管理パックの使用
description: 共存シナリオで Lync Server 2010 管理パックを使用する。
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
ms.openlocfilehash: f5f6e76f49b74badd0f40d115101abb38aa35172
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556073"
---
# <a name="using-the-lync-server-2010-management-packs-in-a-coexistence-scenario"></a><span data-ttu-id="07189-103">共存シナリオでの Lync Server 2010 管理パックの使用</span><span class="sxs-lookup"><span data-stu-id="07189-103">Using the Lync Server 2010 management packs in a coexistence scenario</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="07189-104">_**トピックの最終更新日:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="07189-104">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="07189-105">多くのお客様は、ユーザーが Microsoft Lync Server 2010 から Lync Server 2013 に段階的に移行されることで、企業の内部でロールアウトプログラムを採用しています。</span><span class="sxs-lookup"><span data-stu-id="07189-105">Many customers adopt a rollout program inside of their enterprises in which users are progressively migrated from Microsoft Lync Server 2010 to Lync Server 2013.</span></span> <span data-ttu-id="07189-106">これらの企業の管理者は、両方のバージョンの Lync Server を監視することに注意して、すべてのエンドユーザーが確実に最高のコミュニケーションを実現できるようにしています。</span><span class="sxs-lookup"><span data-stu-id="07189-106">The administrators at these companies will care about monitoring both versions of Lync Server to help ensure that all of their end users are getting the best possible communication experience.</span></span> <span data-ttu-id="07189-107">このシナリオでは、Lync server 2013 管理パックは、Lync Server 2010 管理パックとのサイドバイサイドの移行パスをサポートします。</span><span class="sxs-lookup"><span data-stu-id="07189-107">For this scenario, the Lync Server 2013 Management Pack supports a side-by-side migration path with the Lync Server 2010 Management Pack.</span></span>

<span data-ttu-id="07189-108">Lync Server 2010 では、中央管理ストアに格納されているトポロジドキュメントを通じて Lync Server コンピューターが検出されました。</span><span class="sxs-lookup"><span data-stu-id="07189-108">In the Lync Server 2010, Lync Server computers were discovered through the topology document stored with the Central Management store.</span></span> <span data-ttu-id="07189-109">この構成では、1台のコンピューターが他のすべての Lync Server コンピューターの存在を報告します。</span><span class="sxs-lookup"><span data-stu-id="07189-109">In this configuration, a single computer would report the existence of all the other Lync Server computers.</span></span>

<span data-ttu-id="07189-110">Lync server 2013 用の管理パックは、Lync Server 2010 で使用されていた中央検出メカニズムではなく、マシンレベルの検出を使用するようになりました。</span><span class="sxs-lookup"><span data-stu-id="07189-110">The management packs for Lync Server 2013 now use machine-level discovery instead of the central discovery mechanism that was used in Lync Server 2010.</span></span> <span data-ttu-id="07189-111">これは、各 System Center エージェントが基本的に自身を検出し、その存在を System Center Operations Manager に報告することを意味します。</span><span class="sxs-lookup"><span data-stu-id="07189-111">This means that each System Center agent essentially discovers itself and reports its existence to System Center Operations Manager.</span></span> <span data-ttu-id="07189-112">コンピューターレベルの検出を使用すると、システムセンターインフラストラクチャの管理が簡単になり、Lync server 管理パックのさまざまなバージョン (たとえば、lync server 2010 用の管理パックと Lync Server 2013 用の管理パック) をより簡単に共存させることができます。</span><span class="sxs-lookup"><span data-stu-id="07189-112">Using machine-level discovery simplifies administration of your System Center infrastructure and also enables different versions of the Lync Server management packs (for example, management packs for Lync Server 2010 and management packs for Lync Server 2013) to coexist more easily.</span></span>

<span data-ttu-id="07189-113">この移行をサポートするには、まず、既存の Lync Server 2010 監視をアップグレードして、範囲の不足を回避する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07189-113">To support this migration, you will first need to upgrade your existing Lync Server 2010 monitoring to avoid gaps in coverage.</span></span> <span data-ttu-id="07189-114">これを行うには、中央管理ストアを Lync Server 2013 にアップグレードする前に、lync Server 2010 の中央探索スクリプトを処理する既存の Lync Server 2010 コンピューターを選択します。</span><span class="sxs-lookup"><span data-stu-id="07189-114">To do this, elect an existing Lync Server 2010 computer to service the Central Discovery script for the Lync Server 2010 before upgrading your Central Management store to Lync Server 2013.</span></span> <span data-ttu-id="07189-115">このためには、次の 4 つの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="07189-115">This is a four-step process:</span></span>

1.  <span data-ttu-id="07189-116">Lync Server 2010 管理パックを累積的な更新プログラム7にアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="07189-116">Upgrade the Lync Server 2010 Management Packs to Cumulative Update 7.</span></span>

2.  <span data-ttu-id="07189-117">Lync Server 2010 コンピューターに中央探索スクリプトを実行するように指示します。</span><span class="sxs-lookup"><span data-stu-id="07189-117">Instruct a Lync Server 2010 computer to run the Central Discovery script.</span></span>

3.  <span data-ttu-id="07189-118">Microsoft Lync Server 2010 管理パックの中央探索候補を上書きします。</span><span class="sxs-lookup"><span data-stu-id="07189-118">Override the Central Discovery Candidate in the Microsoft Lync Server 2010 Management Pack.</span></span>

4.  <span data-ttu-id="07189-119">新しい Central Discovery Candidate が検出されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="07189-119">Verify that the new Central Discovery Candidate has been discovered.</span></span>

<div>

## <a name="instructing-a-lync-server-2010-computer-to-run-the-central-discovery-script"></a><span data-ttu-id="07189-120">Lync Server 2010 コンピューターに Central Discovery スクリプトを実行するよう指示する</span><span class="sxs-lookup"><span data-stu-id="07189-120">Instructing a Lync Server 2010 Computer to Run the Central Discovery script</span></span>

<span data-ttu-id="07189-121">中央管理ストアコンピューター (たとえば、Lync Server フロントエンド) サーバーが集中検出を処理するように指名するには、中央管理ストアサーバーに次のレジストリキーを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07189-121">To nominate a non-Central Management store computer (for example, a Lync Server Front End) server to handle central discovery, you will need to create the following registry key on the non-Central Management store server:</span></span>

<span data-ttu-id="07189-122">HKLM \\ ソフトウェア \\ Microsoft \\ リアルタイムコミュニケーション \\ 正常性 \\ centraldiscoverycandidate」</span><span class="sxs-lookup"><span data-stu-id="07189-122">HKLM\\Software\\Microsoft\\Real-Time Communications\\Health\\CentralDiscoveryCandidate</span></span>

<span data-ttu-id="07189-123">このレジストリ キーを作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="07189-123">You can create this registry key by completing the following procedure:</span></span>

1.  <span data-ttu-id="07189-124">[**スタート**] ボタンをクリックし、[**ファイル名を指定して実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="07189-124">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="07189-125">[**ファイル名を指定して実行**] ダイアログ ボックスで「**regedit**」と入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="07189-125">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="07189-126">レジストリエディターで、[ **HKEY \_ LOCAL \_ MACHINE**] を展開し、[ **ソフトウェア**] を展開し、[ **Microsoft**] を展開して、[ **リアルタイム通信**] を展開します。</span><span class="sxs-lookup"><span data-stu-id="07189-126">In Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SOFTWARE**, expand **Microsoft**, and then expand **Real-Time Communications**.</span></span>

4.  <span data-ttu-id="07189-p105">[**Health**] を右クリックし、[**新規**] をクリックして、[**キー**] をクリックします。**Health** キーが存在しない場合は、[**Real-Time Communications**] を右クリックし、[**新規**] をポイントして、[**キー**] をクリックします。新しいキーが作成されたら、「Health」と入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="07189-p105">Right-click **Health**, click **New**, and then click **Key**. If the **Health** key does not exist, then right-click **Real-Time Communications**, point to **New**, and then click **Key**. When the new key is created, type Health, and then press ENTER.</span></span>
    
    <span data-ttu-id="07189-130">新しいキーが作成されたら、「**CentralDiscoveryCandidate**」と入力し、Enter キーを押してキーの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="07189-130">After the new key has been created, type **CentralDiscoveryCandidate** and then press ENTER to rename the key.</span></span>

<span data-ttu-id="07189-131">コンピューターがこの変更を取得するのに数時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="07189-131">It may take the computer several hours to pick up this change.</span></span> <span data-ttu-id="07189-132">この変更を直ちに有効にするには、Health Agent サービスをいったん停止してから再起動します。</span><span class="sxs-lookup"><span data-stu-id="07189-132">To make the change take effect immediately, stop and then restart the Health Agent service.</span></span> <span data-ttu-id="07189-133">正常性エージェントサービスを再起動するには、Lync Server 2010 コンピューターで次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="07189-133">To restart the Health Agent service, complete the following procedure on the Lync Server 2010 computer:</span></span>

1.  <span data-ttu-id="07189-134">[**スタート**] ボタンをクリックし、[**すべてのプログラム**]、[**アクセサリ**] の順にクリックし、[**コマンド プロンプト**] を右クリックし、[**管理者として実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="07189-134">Click **Start**, click **All Programs**, click **Accessories**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="07189-135">コンソール ウィンドウで、次のコマンドを入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="07189-135">In the console window, type the following command and then press ENTER:</span></span>
    
        Net stop HealthService

3.  <span data-ttu-id="07189-p107">"System Center Management サービスが停止する" ことを知らせるメッセージが表示され、その後、サービスが停止したことを伝えるメッセージが表示されます。サービスが停止した後、次のコマンドを入力し、Enter キーを押すと、サービスを再起動できます。</span><span class="sxs-lookup"><span data-stu-id="07189-p107">You will see a message that states "The System Center Management service is stopping," followed by a second message that tells you that the service has been stopped. After the service has stopped, you can restart it by typing the following command and pressing ENTER:</span></span>
    
        Net start HealthService

</div>

<div>

## <a name="overriding-the-central-discovery-candidate-in-the-lync-server-2010-management-pack"></a><span data-ttu-id="07189-138">Lync Server 2010 管理パックでの Central Discovery Candidate のオーバーライド</span><span class="sxs-lookup"><span data-stu-id="07189-138">Overriding the Central Discovery Candidate in the Lync Server 2010 Management Pack</span></span>

<span data-ttu-id="07189-139">Lync server 2010 コンピューターに Lync Server 2010 コンピューターのレポートを表示するように指示した後、lync server 2010 管理パックにもこの変更について通知する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07189-139">After instructing a Lync Server 2010 computer to report on Lync Server 2010 computers, you will need to inform the Lync Server 2010 Management Pack about this change as well.</span></span> <span data-ttu-id="07189-140">これを行うには、管理パックにオーバーライドを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07189-140">To do this, you will need to create an override in the Management Pack.</span></span> <span data-ttu-id="07189-141">このためには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="07189-141">That can be done by completing the following procedure:</span></span>

1.  <span data-ttu-id="07189-142">Operations Manager コンソールで、[**作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="07189-142">In the Operations Manager console, click **Authoring**.</span></span>

2.  <span data-ttu-id="07189-143">[作成] タブで [**管理パック オブジェクト**] を展開し、[**オブジェクト検出**] をクリックし、[**スコープ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="07189-143">On the Authoring tab, expand **Management Pack Objects**, click **Object Discoveries**, and then click **Scope**.</span></span>

3.  <span data-ttu-id="07189-144">[**管理パック オブジェクトのスコープ設定**] ダイアログ ボックスで、ターゲット **LS Discovery Candidate**が指定された項目選択し、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="07189-144">In the **Scope Management Pack Objects** dialog box, select the item with the Target **LS Discovery Candidate** and then click **OK**.</span></span> <span data-ttu-id="07189-145">Lync Server 2010 管理パックをインストールした場合にのみ、LS 検出候補が表示されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="07189-145">Note that LS Discovery Candidate will appear only if you have installed the Lync Server 2010 Management Pack.</span></span>

4.  <span data-ttu-id="07189-146">Operations Manager コンソールで、[**LS Discovery Candidate**] を右クリックし、[**上書き**]、[**オブジェクト検出の上書き**] の順にポイントし、[**クラス LS Discovery Candidate のすべてのオブジェクト**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="07189-146">In the Operations Manager console, right-click **LS Discovery Candidate**, point to **Overrides**, point to **Override the Object Discovery**, and then click **For all objects of class: LS Discovery Candidate**.</span></span>

5.  <span data-ttu-id="07189-147">[**上書きのプロパティ**] ダイアログ ボックスで、パラメーター **Central Discovery WatcherNode Fqdn** の横の [**上書き**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="07189-147">In the **Override Properties** dialog box, select the **Override** check box next to the parameter **Central Discovery WatcherNode Fqdn**.</span></span> <span data-ttu-id="07189-148">[ **上書き値** ] ボックスと [ **有効な値** ] ボックスに、Lync Server 2010 コンピューターの完全修飾ドメイン名を入力します。</span><span class="sxs-lookup"><span data-stu-id="07189-148">Type the fully qualified domain name of the Lync Server 2010 computer in the **Override Value** and **Effective Value** boxes.</span></span> <span data-ttu-id="07189-149">[**強制**] チェック ボックスをオンにして、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="07189-149">Select the **Enforced** check box and click **OK**.</span></span>

<span data-ttu-id="07189-p111">オーバーライドを作成した後、ルート管理サーバーで正常性サービスを再起動する必要があります。正常性サービスを再起動するには、ルート管理サーバーで次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="07189-p111">After you have created the override, you need to restart the health service on the Root Management Server. To restart the health service, complete the following procedure on the Root Management Server:</span></span>

1.  <span data-ttu-id="07189-152">[**スタート**] ボタンをクリックし、[**すべてのプログラム**]、[**アクセサリ**] の順にクリックし、[**コマンド プロンプト**] を右クリックし、[**管理者として実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="07189-152">Click **Start**, click **All Programs**, click **Accessories**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="07189-153">コンソール ウィンドウで、次のコマンドを入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="07189-153">In the console window, type the following command, and then press ENTER:</span></span>
    
        Net stop HealthService

3.  <span data-ttu-id="07189-p112">"System Center Management サービスが停止する" ことを知らせるメッセージが表示され、その後、サービスが停止したことを伝えるメッセージが表示されます。サービスが停止したら、次のコマンドを入力し、Enter キーを押して、サービスを再起動できます。</span><span class="sxs-lookup"><span data-stu-id="07189-p112">You will see a message stating that "The System Center Management service is stopping," followed by a second message that tells you that the service has been stopped. After the service has stopped, you can then restart it by typing the following command and pressing ENTER:</span></span>
    
        Net start HealthService

</div>

<div>

## <a name="verifying-that-the-new-central-discovery-candidate-was-discovered"></a><span data-ttu-id="07189-156">新しい Central Discovery Candidate が検出されたことを確認する</span><span class="sxs-lookup"><span data-stu-id="07189-156">Verifying that the New Central Discovery Candidate Was Discovered</span></span>

<span data-ttu-id="07189-157">中央管理ストアをアップグレードする前に、最後の手順として、Lync Server 2010 管理パックによって新しい中央検出候補が検出されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="07189-157">The final step before upgrading Central Management store is to make sure that the new central discovery candidate was discovered by the Lync Server 2010 Management Pack.</span></span> <span data-ttu-id="07189-158">このためには、Operations Manager コンソールを開き、[監視] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="07189-158">To do this, open the Operations Manager console and then click Monitoring.</span></span> <span data-ttu-id="07189-159">[監視] タブで、[**Microsoft Lync Server 2010 Health**]、[**Topology Discovery**] の順に展開し、[**Discovery State View**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="07189-159">On the Monitoring tab, expand **Microsoft Lync Server 2010 Health**, expand **Topology Discovery**, and then click **Discovery State View**.</span></span> <span data-ttu-id="07189-160">表示の行の**パス**に Central Discovery Candidate の完全修飾ドメイン名が表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="07189-160">Verify that a row in the display has a **Path** that lists the fully qualified domain name of the central discovery candidate.</span></span> <span data-ttu-id="07189-161">コンピューターの状態が**健全**と報告されていることを確認する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="07189-161">You should also verify that the computer state is reported as **Healthy**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

