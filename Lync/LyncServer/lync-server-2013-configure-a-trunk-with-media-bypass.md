---
title: 'Lync Server 2013: メディアバイパスを使用してトランクを構成する'
description: 'Lync Server 2013: メディアバイパスを使用してトランクを構成します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a trunk with media bypass
ms:assetid: 99d729ea-5a4c-4ff2-a4a3-93a24368da6d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398792(v=OCS.15)
ms:contentKeyID: 48184959
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 51bd58a685e1f4c222a863c21022b3c9dc7c70d6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566753"
---
# <a name="configure-a-trunk-with-media-bypass-in-lync-server-2013"></a><span data-ttu-id="54c87-103">Lync Server 2013 でメディアバイパスを使用してトランクを構成する</span><span class="sxs-lookup"><span data-stu-id="54c87-103">Configure a trunk with media bypass in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="54c87-104">_**トピックの最終更新日:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="54c87-104">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="54c87-105">メディアバイパスを有効にしてトランクを構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="54c87-105">Follow these steps to configure a trunk with media bypass enabled.</span></span> <span data-ttu-id="54c87-106">メディアバイパスを無効にしてトランクを構成するには、「 [Lync Server 2013 でメディアバイパスを使用せずにトランクを構成](lync-server-2013-configure-a-trunk-without-media-bypass.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54c87-106">To configure a trunk with media bypass disabled, see [Configure a trunk without media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md).</span></span> <span data-ttu-id="54c87-107">メディアバイパスは、展開する仲介サーバーの数を最小限に抑える場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="54c87-107">Media bypass is useful when you want to minimize the number of Mediation Servers deployed.</span></span> <span data-ttu-id="54c87-108">通常、仲介サーバープールは中央サイトに展開され、ブランチサイトのゲートウェイを制御します。</span><span class="sxs-lookup"><span data-stu-id="54c87-108">Typically, a Mediation Server pool will be deployed at a central site, and it will control gateways at branch sites.</span></span> <span data-ttu-id="54c87-109">メディアバイパスを有効にすると、ブランチサイトのクライアントからの公衆交換電話網 (PSTN) 通話のメディアを、それらのサイトのゲートウェイを介して直接流すことができます。</span><span class="sxs-lookup"><span data-stu-id="54c87-109">Enabling media bypass allows media for public switched telephone network (PSTN) calls from clients at branch sites to flow directly through the gateways at those sites.</span></span> <span data-ttu-id="54c87-110">Lync Server 2013 の発信通話ルートとエンタープライズ音声ポリシーを適切に構成して、ブランチサイトのクライアントからの PSTN 通話を適切なゲートウェイにルーティングできるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="54c87-110">Lync Server 2013 outbound call routes and Enterprise Voice policies must be properly configured so that PSTN calls from clients at a branch site are routed to the appropriate gateway.</span></span>

<span data-ttu-id="54c87-111">メディアバイパスを有効にすることを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="54c87-111">We strongly recommend that you enable media bypass.</span></span> <span data-ttu-id="54c87-112">ただし、SIP トランクに対してメディアバイパスを有効にする前に、認定された SIP トランクプロバイダーがメディアバイパスをサポートしており、シナリオを正常に有効にするための要件を満たすことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="54c87-112">However, before you enable media bypass on a SIP trunk, confirm that your qualified SIP trunk provider supports media bypass and is able to accommodate the requirements for successfully enabling the scenario.</span></span> <span data-ttu-id="54c87-113">具体的には、プロバイダーは、組織の内部ネットワーク内のサーバーの IP アドレスを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="54c87-113">Specifically, the provider must have the IP addresses of servers in your organization’s internal network.</span></span> <span data-ttu-id="54c87-114">このシナリオをプロバイダーがサポートできない場合、メディア バイパスは成功しません。</span><span class="sxs-lookup"><span data-stu-id="54c87-114">If the provider cannot support this scenario, media bypass will not succeed.</span></span> <span data-ttu-id="54c87-115">詳細については、「計画」のドキュメントの「 [planning for media バイパス In Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54c87-115">For details, see [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) in the Planning documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="54c87-116">メディアバイパスは、すべての公衆交換電話網 (PSTN) ゲートウェイ、IP-PBX、およびセッションボーダーコントローラー (SBC) と相互運用することはできません。</span><span class="sxs-lookup"><span data-stu-id="54c87-116">Media bypass will not interoperate with every public switched telephone network (PSTN) gateway, IP-PBX, and Session Border Controller (SBC).</span></span> <span data-ttu-id="54c87-117">Microsoft は、認定パートナーで PSTN ゲートウェイと sbc のセットをテストしており、Cisco IP-PBX でいくつかのテストを行いました。</span><span class="sxs-lookup"><span data-stu-id="54c87-117">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="54c87-118">メディアバイパスがサポートされるのは、統合コミュニケーションのオープン相互運用性プログラム– Lync Server at に記載されている製品およびバージョンのみです <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A> 。</span><span class="sxs-lookup"><span data-stu-id="54c87-118">Media bypass is supported only with products and versions that are listed on Unified Communications Open Interoperability Program – Lync Server at <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A>.</span></span>



</div>

<span data-ttu-id="54c87-119">以下に示すトランク構成は、このトランク構成を割り当てられたトランクに適用されるパラメータセットをグループ化します。</span><span class="sxs-lookup"><span data-stu-id="54c87-119">A trunk configuration as described below groups a set of parameters that are applied to trunks assigned this trunk configuration.</span></span> <span data-ttu-id="54c87-120">特定のトランク構成は、グローバルに範囲指定できます (特定のサイトまたはプール構成を持たないすべてのトランク、サイト、またはプール)。</span><span class="sxs-lookup"><span data-stu-id="54c87-120">A particular trunk configuration can be scoped globally (to all trunks that do not have more specific site or pool configuration), or to a site, or to a pool.</span></span> <span data-ttu-id="54c87-121">プールレベルのトランク構成は、1つのトランクに特定のトランク構成のスコープを設定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="54c87-121">The pool-level trunk configuration is used to scope a specific trunk configuration to a single trunk.</span></span>

<span id="BKMK_ConfigTrunkMediaBypassSteps"></span>

<div>

## <a name="to-configure-a-trunk-with-media-bypass"></a><span data-ttu-id="54c87-122">メディアバイパスを使用してトランクを構成するには</span><span class="sxs-lookup"><span data-stu-id="54c87-122">To configure a trunk with media bypass</span></span>

1.  <span data-ttu-id="54c87-123">RTCUniversalServerAdmins グループのメンバーとして、または CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="54c87-123">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="54c87-124">詳細については、「 [Lync Server 2013 でのセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54c87-124">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="54c87-125">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="54c87-125">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="54c87-126">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54c87-126">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="54c87-127">左側のナビゲーション バーで [**音声ルーティング**] をクリックし、[**トランク構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="54c87-127">In the left navigation bar, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

4.  <span data-ttu-id="54c87-128">[**トランク構成**] ページで、次のいずれかの方法を使用してトランクを構成します。</span><span class="sxs-lookup"><span data-stu-id="54c87-128">On the **Trunk Configuration** page, use one of the following methods to configure a trunk:</span></span>
    
      - <span data-ttu-id="54c87-129">既存のトランク (たとえば、[**グローバル**] トランク) をダブルクリックして [**トランク構成の編集**] ダイアログ ボックスを表示します。</span><span class="sxs-lookup"><span data-stu-id="54c87-129">Double-click an existing trunk (for example, the **Global** trunk) to display the **Edit Trunk Configuration** dialog box.</span></span>
    
      - <span data-ttu-id="54c87-130">[**新規**] をクリックし、新しいトランクのスコープ構成を選択します。</span><span class="sxs-lookup"><span data-stu-id="54c87-130">Click **New**, and then select a scope for the new trunk configuration:</span></span>
        
          - <span data-ttu-id="54c87-131">**サイトトランク:** [ **サイトの選択**] で、このトランク構成のサイトを選択し、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="54c87-131">**Site trunk:** Choose the site for this trunk configuration from **Select a Site**, and then click **OK**.</span></span> <span data-ttu-id="54c87-132">サイトに対してトランク構成が既に作成されている場合、[**サイトの選択**] にはサイトは表示されませんので注意してください。</span><span class="sxs-lookup"><span data-stu-id="54c87-132">Note that if a trunk configuration has already been created for a site, the site does not appear in **Select a Site**.</span></span> <span data-ttu-id="54c87-133">このトランク構成は、サイト内のすべてのトランクに適用されます。</span><span class="sxs-lookup"><span data-stu-id="54c87-133">This trunk configuration will be applied to all trunks in the site.</span></span>
        
          - <span data-ttu-id="54c87-134">**プールトランク:** このトランク構成を適用するトランクの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="54c87-134">**Pool trunk:** Choose the name of the trunk that this trunk configuration applies to.</span></span> <span data-ttu-id="54c87-135">このトランクは、ルートトランクまたはトポロジビルダーで定義された追加のトランクにすることができます。</span><span class="sxs-lookup"><span data-stu-id="54c87-135">This trunk can be the root trunk or any additional trunks defined in Topology Builder.</span></span> <span data-ttu-id="54c87-136">[ **サービスの選択**] で、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="54c87-136">From **Select a Service**, click **OK**.</span></span> <span data-ttu-id="54c87-137">特定のトランクに対してトランク構成が既に作成されている場合、[**サービスの選択**] にはトランクは表示されませんので注意してください。</span><span class="sxs-lookup"><span data-stu-id="54c87-137">Note that if a trunk configuration has already been created for a specific trunk, the trunk does not appear in **Select a Service**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="54c87-138">トランク構成のスコープは、選択した後は変更できません。</span><span class="sxs-lookup"><span data-stu-id="54c87-138">After you select the scope of the trunk configuration, it cannot be changed.</span></span><BR><span data-ttu-id="54c87-139">[<STRONG>名前</STRONG>] フィールドには、トランク構成に関連付けられたサイトまたはサービスの名前が事前に入力されており、変更できません。</span><span class="sxs-lookup"><span data-stu-id="54c87-139">The <STRONG>Name</STRONG> field is prepopulated with the name of the trunk configuration’s associated site or service and cannot be changed.</span></span>

    
    </div>

5.  <span data-ttu-id="54c87-140">**事前にサポートされている最大のダイアログボックス**に値を指定します。</span><span class="sxs-lookup"><span data-stu-id="54c87-140">Specify a value in **Maximum early dialogs supported**.</span></span> <span data-ttu-id="54c87-141">これは、公衆交換電話網 (PSTN) ゲートウェイ、IP-PBX、または ITSP セッションボーダーコントローラー (SBC) が仲介サーバーに送信した INVITE に対して受信できる分岐応答の最大数です。</span><span class="sxs-lookup"><span data-stu-id="54c87-141">This is the maximum number of forked responses a public switched telephone network (PSTN) gateway, IP-PBX, or ITSP Session Border Controller (SBC) can receive to an INVITE that it sent to the Mediation Server.</span></span> <span data-ttu-id="54c87-142">既定値は 20 です。</span><span class="sxs-lookup"><span data-stu-id="54c87-142">The default value is 20.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="54c87-143">この値を変更する前に、サービス プロバイダーまたは機器の製造メーカーに、システムの機能の詳細について問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="54c87-143">Before you change this value, consult your service provider or equipment manufacturer for details about the capabilities of your system.</span></span>

    
    </div>

6.  <span data-ttu-id="54c87-144">次のいずれかの **[暗号化サポート レベル]** オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="54c87-144">Select one of the following **Encryption support level** options:</span></span>
    
      - <span data-ttu-id="54c87-145">**必須:** 仲介サーバーとゲートウェイまたは構内交換 (PBX) 間のトラフィックを保護するためには、セキュリティで保護されたリアルタイム転送プロトコル (SRTP) 暗号化を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="54c87-145">**Required:** Secure real-time transport protocol (SRTP) encryption must be used to help protect traffic between the Mediation Server and the gateway or private branch exchange (PBX).</span></span>
    
      - <span data-ttu-id="54c87-146">**省略可能:** SRTP 暗号化は、サービスプロバイダーまたは機器の製造メーカーがサポートしている場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="54c87-146">**Optional:** SRTP encryption will be used if the service provider or equipment manufacturer supports it.</span></span>
    
      - <span data-ttu-id="54c87-147">**サポート対象外:** SRTP 暗号化は、サービスプロバイダーまたは機器の製造元によってサポートされていないため、使用されません。</span><span class="sxs-lookup"><span data-stu-id="54c87-147">**Not Supported:** SRTP encryption is not supported by the service provider or equipment manufacturer and therefore will not be used.</span></span>

7.  <span data-ttu-id="54c87-148">トランク ピアによる処理で、メディアが仲介サーバーをバイパスするようにする場合は、**[メディア バイパスを有効にする]** チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="54c87-148">Select the **Enable media bypass** check box if you want media to bypass the Mediation Server for processing by the trunk peer.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="54c87-149">メディア バイパスが正常に機能するには、PSTN ゲートウェイ、IP-PBX、または ITSP セッション ボーダー コントローラーが一定の機能をサポートしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="54c87-149">For media bypass to work successfully, the PSTN gateway, IP-PBX, or ITSP Session Border Controller must support certain capabilities.</span></span> <span data-ttu-id="54c87-150">詳細については、「計画」のドキュメントの「 <A href="lync-server-2013-planning-for-media-bypass.md">planning for media バイパス In Lync Server 2013</A> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54c87-150">For details, see <A href="lync-server-2013-planning-for-media-bypass.md">Planning for media bypass in Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>

8.  <span data-ttu-id="54c87-p111">既知のメディア終端ポイント (たとえば、メディア終端が信号終端と同じ IP を持つ PSTN ゲートウェイ) がある場合は、**[集中メディア処理]** チェック ボックスをオンにします。 トランクに既知のメディア終端ポイントがない場合は、このチェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="54c87-p111">Select the **Centralized media processing** check box if there is a well-known media termination point (for example, a PSTN gateway where the media termination has the same IP as the signaling termination). Clear this check box if the trunk does not have a well-known media termination point.</span></span>

9.  <span data-ttu-id="54c87-153">トランクピアが仲介サーバーからの SIP 参照要求の受信をサポートしている場合は、[ **ゲートウェイへの参照の送信を有効に** する] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="54c87-153">If the trunk peer supports receiving SIP REFER requests from the Mediation Server, select the **Enable sending refer to the gateway** check box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="54c87-154"><STRONG>[メディア バイパスを有効にする]</STRONG> オプションが選択されている場合にこのオプションを無効にするには、追加の設定が必要です。</span><span class="sxs-lookup"><span data-stu-id="54c87-154">If you disable this option while the <STRONG>Enable media bypass</STRONG> option is selected, additional settings are required.</span></span> <span data-ttu-id="54c87-155">トランク ピアが仲介サーバーからの SIP REFER 要求の受信をサポートしておらず、メディア バイパスが有効な場合は、メディア バイパスの適正な状態をサポートするため、<STRONG>Set-CsTrunkConfiguration</STRONG> コマンドレットを実行して、アクティブな通話と保留通話の RTCP を無効にする必要もあります。</span><span class="sxs-lookup"><span data-stu-id="54c87-155">If the trunk peer does not support receiving SIP REFER requests from the Mediation Server and media bypass is enabled, you must also run the <STRONG>Set-CsTrunkConfiguration</STRONG> cmdlet to disable RTCP for active and held calls in order to support proper conditions for media bypass.</span></span> <span data-ttu-id="54c87-156">詳細については、「 <A href="lync-server-2013-lync-server-management-shell.md">Lync Server 2013 Management Shell</A> 」のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="54c87-156">For details, see the <A href="lync-server-2013-lync-server-management-shell.md">Lync Server 2013 Management Shell</A> documentation.</span></span><BR><span data-ttu-id="54c87-157">または、転送された通話をメディアバイパスで、ゲートウェイが SIP REFER 要求をサポートしていない場合は、[ <STRONG>サードパーティの通話制御を使用して参照を有効</STRONG> にする] を選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="54c87-157">Alternatively, you can select <STRONG>Enable refer using third-party-call control</STRONG> if you want transferred calls to be media bypassed, and the gateway does not support SIP REFER requests.</span></span>

    
    </div>

10. <span data-ttu-id="54c87-p113">(省略可) トランク間ルーティングを有効にするには、このトランク構成に PSTN 使用法レコードを関連付けして、構成します。このトランク構成に関連付けられた PSTN 使用法は、Lync エンドポイントに由来しない、このトランクからのすべての着信に適用されます。トランク構成に関連付けられた PSTN 使用法レコードを管理するには、以下の方法の 1 つを使用します。</span><span class="sxs-lookup"><span data-stu-id="54c87-p113">(Optional) To enable inter-trunk routing, associate and configure PSTN usage records to this trunk configuration. The PSTN usages associated to this trunk configuration will be applied for all incoming calls through the trunk that is not originating from a Lync endpoint. To manage PSTN usage records associated to a trunk configuration, use one of the following methods:</span></span>
    
      - <span data-ttu-id="54c87-161">エンタープライズ Voip 展開で利用できるすべての PSTN 使用法レコードの一覧から、1つまたは複数のレコードを選択するには、[ **選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="54c87-161">To select one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="54c87-162">このトランク構成に関連付けるレコードを選択状態にし、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="54c87-162">Highlight the records you want to associate with this trunk configuration and then click **OK**.</span></span>
    
      - <span data-ttu-id="54c87-163">PSTN 使用法レコードをこのトランク構成から削除するには、レコードを選択して [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="54c87-163">To remove a PSTN usage record from this trunk configuration, select the record and click **Remove**.</span></span>
    
      - <span data-ttu-id="54c87-164">新しい PSTN 使用法レコードを定義してこのトランク構成に関連付けるには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="54c87-164">To define a new PSTN usage record and associate it with this trunk configuration, do the following:</span></span>
        
        1.  <span data-ttu-id="54c87-165">[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="54c87-165">Click **New**.</span></span>
        
        2.  <span data-ttu-id="54c87-166">[**名前**] フィールドに、レコードを説明する一意の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="54c87-166">In the **Name** field, specify a descriptive name for the record that is unique.</span></span>
            
            <div>
            

            > [!NOTE]  
            > <span data-ttu-id="54c87-p115">PSTN 使用法レコードの名前は、エンタープライズ VoIP 展開内で一意である必要があります。レコードの保存後、[<STRONG>名前</STRONG>] フィールドを編集することはできません。</span><span class="sxs-lookup"><span data-stu-id="54c87-p115">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

            
            </div>
        
        3.  <span data-ttu-id="54c87-169">次のいずれかの方法を使用して、この PSTN 使用法レコードのルートの関連付けと構成を行います。</span><span class="sxs-lookup"><span data-stu-id="54c87-169">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="54c87-170">エンタープライズ Voip 展開で利用できるすべてのルートの一覧から1つ以上のルートを選択するには、[ **選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="54c87-170">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="54c87-171">この PSTN 使用法レコードに関連付けるルートを強調表示して、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="54c87-171">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>
            
              - <span data-ttu-id="54c87-172">PSTN 使用法レコードからルートを削除するには、ルートを選択し、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="54c87-172">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>
            
              - <span data-ttu-id="54c87-173">新しいルートを定義してこの PSTN 使用法レコードに関連付けるには、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="54c87-173">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="54c87-174">詳細については、「 [Lync Server 2013 で音声ルートを作成する](lync-server-2013-create-a-voice-route.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54c87-174">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="54c87-175">この PSTN 使用法レコードに関連付けられているルートを編集するには、ルートを選択し、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="54c87-175">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span> <span data-ttu-id="54c87-176">詳細については、「 [Modify a voice route In Lync Server 2013](lync-server-2013-modify-a-voice-route.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54c87-176">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        4.  <span data-ttu-id="54c87-177">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="54c87-177">Click **OK**.</span></span>
    
      - <span data-ttu-id="54c87-178">このトランク構成にすでに関連付けられている PSTN 使用法レコードを編集するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="54c87-178">To edit a PSTN usage record that is already associated with this trunk configuration, do the following:</span></span>
        
        1.  <span data-ttu-id="54c87-179">編集する PSTN 使用法レコードを選択して、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="54c87-179">Select the PSTN usage record you want to edit, and click **Show details**.</span></span>
        
        2.  <span data-ttu-id="54c87-180">次のいずれかの方法を使用して、この PSTN 使用法レコードのルートの関連付けと構成を行います。</span><span class="sxs-lookup"><span data-stu-id="54c87-180">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="54c87-181">エンタープライズ Voip 展開で利用できるすべてのルートの一覧から1つ以上のルートを選択するには、[ **選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="54c87-181">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="54c87-182">この PSTN 使用法レコードに関連付けるルートを強調表示して、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="54c87-182">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>
            
              - <span data-ttu-id="54c87-183">PSTN 使用法レコードからルートを削除するには、ルートを選択し、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="54c87-183">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>
            
              - <span data-ttu-id="54c87-184">新しいルートを定義してこの PSTN 使用法レコードに関連付けるには、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="54c87-184">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="54c87-185">詳細については、「 [Lync Server 2013 で音声ルートを作成する](lync-server-2013-create-a-voice-route.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54c87-185">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="54c87-186">この PSTN 使用法レコードに関連付けられているルートを編集するには、ルートを選択し、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="54c87-186">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span> <span data-ttu-id="54c87-187">詳細については、「 [Modify a voice route In Lync Server 2013](lync-server-2013-modify-a-voice-route.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54c87-187">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        3.  <span data-ttu-id="54c87-188">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="54c87-188">Click **OK**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="54c87-189">構成するトランクに関連付けられている仲介サーバーのピアに従って PSTN 使用法レコードを関連付けることが重要です。</span><span class="sxs-lookup"><span data-stu-id="54c87-189">It important to associate PSTN usage records according to the Mediation Server peer that is associated to the trunk being configured.</span></span> <span data-ttu-id="54c87-190">仲介サーバーのピアが PSTN ゲートウェイまたはセッションボーダーコントローラー (SBC) である場合は、PSTN の宛先または Lync Server を介して接続されている他のダウンストリームシステムにルーティングする PSTN 使用法レコードに関連付けられていない構成を使用することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="54c87-190">If the Mediation Server peer is a PSTN gateway or a Session Border Controller (SBC), it is strongly recommended that the trunk configuration is not associated to a PSTN usage record that routes to a PSTN destination or any other downstream systems connected via Lync Server.</span></span>

    
    </div>

11. <span data-ttu-id="54c87-p123">最適なパフォーマンスを得る目的で、PSTN 使用法レコードを並べ替えます。一覧内でのレコードの位置を変更するには、PSTN 使用法レコードを選択して、上矢印または下矢印をクリックします。</span><span class="sxs-lookup"><span data-stu-id="54c87-p123">Arrange the PSTN usage records for optimum performance. To change a record’s position in the list, select the PSTN usage record, and click the up or down arrows.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="54c87-193">トランク構成の PSTN 使用法レコードのリスト内の順序は重要です。</span><span class="sxs-lookup"><span data-stu-id="54c87-193">The order in which PSTN usage records are listed in the trunk configuration is significant.</span></span> <span data-ttu-id="54c87-194">Lync Server は、一覧を上から下に移動します。</span><span class="sxs-lookup"><span data-stu-id="54c87-194">Lync Server traverses the list from top to down.</span></span>

    
    </div>

12. <span data-ttu-id="54c87-195">ネットワークアドレス変換 (NAT) またはファイアウォールと、ラッチをサポートする SBC の背後にあるクライアントのバイパスメディアを有効にするには、[ **RTP ラッチを有効**にする] を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="54c87-195">**Enable RTP Latching** should be selected to enable bypass media for clients behind a network address translation (NAT) or firewall and an SBC that supports latching.</span></span>

13. <span data-ttu-id="54c87-196">[**フォワード呼び出し履歴を有効**にする] を選択して、仲介サーバーのゲートウェイピアへの通話履歴情報の送信を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="54c87-196">**Enable forward call history** should be selected to enable sending of call history information to the gateway peer of the Mediation Server.</span></span>

14. <span data-ttu-id="54c87-197">[転送を有効にする] **-id データを有効**にします。これを有効にするには、仲介サーバー側とゲートウェイ側 (およびその逆) の間で、p がアサート状態 (pai) の呼び出し元情報を転送できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="54c87-197">**Enable forward P-Asserted-Identity data** should be selected to enable the P-Asserted-Identity (PAI) call originator information to be forwarded between the Mediation Server side and gateway side (and vice versa), when present.</span></span>

15. <span data-ttu-id="54c87-198">[**送信ルーティング フェールオーバー タイマーを有効にする**] は、高速なフェールオーバーを有効にする場合に選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="54c87-198">**Enable outbound routing failover timer** should be selected to enable fast failover.</span></span> <span data-ttu-id="54c87-199">このトランクに関連付けられたゲートウェイは、発信を処理している 10 秒中に通知をすることができます。</span><span class="sxs-lookup"><span data-stu-id="54c87-199">The gateway associated with this trunk can give notification within 10 seconds that it is processing an outbound call.</span></span> <span data-ttu-id="54c87-200">この通知が仲介サーバーによって受信されない場合は、別のトランクへの再ルーティングが発生します。</span><span class="sxs-lookup"><span data-stu-id="54c87-200">Rerouting to another trunk will occur if this notification is not received by the Mediation Server.</span></span> <span data-ttu-id="54c87-201">待機時間により反応時間が遅くなるネットワーク、または、応答するのに 10 秒以上かかるゲートウェイでは、高速のフェールオーバーを無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="54c87-201">On networks where latency may delay the response time or the gateway takes longer than 10 seconds to respond, the fast failover should be disabled.</span></span>

16. <span data-ttu-id="54c87-202">(省略可) トランクの**発信通話番号変換ルール**を関連付けて構成します。</span><span class="sxs-lookup"><span data-stu-id="54c87-202">(Optional) Associate and configure **calling number translation rules** for the trunk.</span></span> <span data-ttu-id="54c87-203">これらの変換ルールは、発信電話番号に適用されます。</span><span class="sxs-lookup"><span data-stu-id="54c87-203">These translation rules apply to the calling number for outbound calls</span></span>
    
      - <span data-ttu-id="54c87-204">エンタープライズ Voip 展開で利用できるすべての変換ルールの一覧から1つ以上のルールを選択するには、[ **選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="54c87-204">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="54c87-205">[**変換ルールの選択**] で、トランクに関連付けるルールをクリックして、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="54c87-205">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>
    
      - <span data-ttu-id="54c87-206">新しい変換ルールを定義してトランクに関連付ける場合は、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="54c87-206">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="54c87-207">新しいルールの定義の詳細については、「展開」のドキュメントの「 [Lync Server 2013 で変換ルールを定義](lync-server-2013-defining-translation-rules.md) する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54c87-207">For details about defining a new rule, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="54c87-208">既にトランクに関連付けられている変換ルールを編集するには、ルールの名前をクリックして、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="54c87-208">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> <span data-ttu-id="54c87-209">詳細については、「展開」のドキュメントの「 [Lync Server 2013 で変換ルールを定義](lync-server-2013-defining-translation-rules.md) する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54c87-209">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="54c87-210">既存の変換ルールをコピーしてそれを基に新しいルールを定義するには、ルールの名前をクリックして [**コピー**] をクリックし、[**貼り付け**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="54c87-210">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="54c87-211">詳細については、「 [Lync Server 2013 で変換ルールを定義](lync-server-2013-defining-translation-rules.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54c87-211">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span></span>
    
      - <span data-ttu-id="54c87-212">トランクから変換ルールを削除するには、ルールの名前を選択状態にし、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="54c87-212">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="54c87-213">関連付けられたトランク ピアに対して変換ルールを構成している場合は、2 つのルールが競合する危険があることから、変換ルールをトランクに関連付けないでください。</span><span class="sxs-lookup"><span data-stu-id="54c87-213">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>

    
    </div>

17. <span data-ttu-id="54c87-p131">(省略可) トランクの**発信先通話番号変換ルール**を関連付けて構成します。これらの変換ルールは、発信電話の発信先の電話番号に適用されます。</span><span class="sxs-lookup"><span data-stu-id="54c87-p131">(Optional) Associate and configure **called number translation rules** for the trunk. The translation rules apply to the called number in an outbound call.</span></span>
    
      - <span data-ttu-id="54c87-216">エンタープライズ Voip 展開で利用できるすべての変換ルールの一覧から1つ以上のルールを選択するには、[ **選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="54c87-216">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="54c87-217">[**変換ルールの選択**] で、トランクに関連付けるルールをクリックして、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="54c87-217">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>
    
      - <span data-ttu-id="54c87-218">新しい変換ルールを定義してトランクに関連付ける場合は、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="54c87-218">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="54c87-219">新しいルールの定義の詳細については、「展開」のドキュメントの「 [Lync Server 2013 で変換ルールを定義](lync-server-2013-defining-translation-rules.md) する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54c87-219">For details about defining a new rule, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="54c87-220">既にトランクに関連付けられている変換ルールを編集するには、ルールの名前をクリックして、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="54c87-220">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> <span data-ttu-id="54c87-221">詳細については、「展開」のドキュメントの「 [Lync Server 2013 で変換ルールを定義](lync-server-2013-defining-translation-rules.md) する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54c87-221">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="54c87-222">既存の変換ルールをコピーしてそれを基に新しいルールを定義するには、ルールの名前をクリックして [**コピー**] をクリックし、[**貼り付け**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="54c87-222">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="54c87-223">詳細については、「 [Lync Server 2013 で変換ルールを定義](lync-server-2013-defining-translation-rules.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54c87-223">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span></span>
    
      - <span data-ttu-id="54c87-224">トランクから変換ルールを削除するには、ルールの名前を選択状態にし、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="54c87-224">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="54c87-225">関連付けられたトランク ピアに対して変換ルールを構成している場合は、2 つのルールが競合する危険があることから、変換ルールをトランクに関連付けないでください。</span><span class="sxs-lookup"><span data-stu-id="54c87-225">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>

    
    </div>

18. <span data-ttu-id="54c87-226">トランクの変換ルールが正しい順序で並んでいることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="54c87-226">Make sure that the trunk’s translation rules are arranged in the correct order.</span></span> <span data-ttu-id="54c87-227">一覧内でのルールの位置を変更するには、ルールの名前を選択状態にして、上矢印または下矢印をクリックします。</span><span class="sxs-lookup"><span data-stu-id="54c87-227">To change a rule’s position in the list, highlight the rule name and then click the up or down arrow.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="54c87-228">Lync Server 2013 は、変換ルールの一覧を上から順にスキャンし、ダイヤルされた番号と最初に一致するルールを使用します。</span><span class="sxs-lookup"><span data-stu-id="54c87-228">Lync Server 2013 traverses the translation rule list from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="54c87-229">トランクを構成し、その結果ダイヤルされる番号が複数の変換ルールと一致する可能性がある場合は、制限の厳しいルールを制限の緩いルールよりも上に並べ替えてください。</span><span class="sxs-lookup"><span data-stu-id="54c87-229">If you configure a trunk so that a dialed number can match more than one translation rule, be sure that the more restrictive rules are sorted above the less restrictive rules.</span></span> <span data-ttu-id="54c87-230">たとえば、任意の 11 桁の番号と一致する変換ルールと +1425 で始まる 11 桁の番号だけと一致する変換ルールを組み込んでいる場合、任意の 11 桁の番号と一致する変換ルールは、必ず、制限が厳しい方のルールの<EM></EM>下に並べ替えてください。</span><span class="sxs-lookup"><span data-stu-id="54c87-230">For example, if you have included a translation rule that matches any 11-digit number and a translation rule that matches only 11-digit numbers that start with +1425, be sure that the rule that matches any 11-digit number is sorted <EM>below</EM> the more restrictive rule.</span></span>

    
    </div>

19. <span data-ttu-id="54c87-231">トランクの構成が終了したら、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="54c87-231">When you are finished configuring the trunk, click **OK**.</span></span>

20. <span data-ttu-id="54c87-232">[**トランク構成**] ページで [**確定**] をクリックして、[**すべて確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="54c87-232">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="54c87-233">トランクの構成を作成または変更するときは常に、[<STRONG>すべて確定</STRONG>] コマンドを実行して、構成の変更を公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="54c87-233">Whenever you create or modify a trunk configuration, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="54c87-234">詳細については、「操作」のドキュメントの「 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 での音声ルーティング構成に対する保留中の変更の公開</A> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54c87-234">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

<span data-ttu-id="54c87-235">トランクを構成した後は、「展開」のドキュメントの「 [グローバルメディアバイパスオプション (Lync Server 2013](lync-server-2013-global-media-bypass-options.md) )」で説明するように、グローバルメディアバイパスオプションの中から選択して、メディアバイパスの構成を続行します。</span><span class="sxs-lookup"><span data-stu-id="54c87-235">After you have configured the trunk, continue configuring media bypass by choosing between global media bypass options, as described in [Global media bypass options in Lync Server 2013](lync-server-2013-global-media-bypass-options.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="54c87-236">関連項目</span><span class="sxs-lookup"><span data-stu-id="54c87-236">See Also</span></span>


[<span data-ttu-id="54c87-237">Lync Server 2013 でメディアバイパスを使用せずにトランクを構成する</span><span class="sxs-lookup"><span data-stu-id="54c87-237">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)  


[<span data-ttu-id="54c87-238">Lync Server 2013 でメディアバイパスを構成する</span><span class="sxs-lookup"><span data-stu-id="54c87-238">Configure media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-media-bypass.md)  
[<span data-ttu-id="54c87-239">Lync Server 2013 のグローバルメディアバイパスオプション</span><span class="sxs-lookup"><span data-stu-id="54c87-239">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  


[<span data-ttu-id="54c87-240">Lync Server 2013 での変換ルールの定義</span><span class="sxs-lookup"><span data-stu-id="54c87-240">Defining translation rules in Lync Server 2013</span></span>](lync-server-2013-defining-translation-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

