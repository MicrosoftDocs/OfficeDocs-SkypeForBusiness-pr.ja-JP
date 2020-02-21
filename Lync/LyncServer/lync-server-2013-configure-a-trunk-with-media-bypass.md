---
title: 'Lync Server 2013: メディアバイパスを使用してトランクを構成する'
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
ms.openlocfilehash: 256962ace879c9d418d877b94f15227959177407
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42206943"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-a-trunk-with-media-bypass-in-lync-server-2013"></a><span data-ttu-id="29fbb-102">Lync Server 2013 でメディアバイパスを使用してトランクを構成する</span><span class="sxs-lookup"><span data-stu-id="29fbb-102">Configure a trunk with media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="29fbb-103">_**トピックの最終更新日:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="29fbb-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="29fbb-104">メディアバイパスを有効にしてトランクを構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="29fbb-104">Follow these steps to configure a trunk with media bypass enabled.</span></span> <span data-ttu-id="29fbb-105">メディアバイパスを無効にしてトランクを構成するには、「 [Lync Server 2013 でメディアバイパスを使用せずにトランクを構成](lync-server-2013-configure-a-trunk-without-media-bypass.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29fbb-105">To configure a trunk with media bypass disabled, see [Configure a trunk without media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md).</span></span> <span data-ttu-id="29fbb-106">メディアバイパスは、展開する仲介サーバーの数を最小限に抑える場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="29fbb-106">Media bypass is useful when you want to minimize the number of Mediation Servers deployed.</span></span> <span data-ttu-id="29fbb-107">通常、仲介サーバープールは中央サイトに展開され、ブランチサイトのゲートウェイを制御します。</span><span class="sxs-lookup"><span data-stu-id="29fbb-107">Typically, a Mediation Server pool will be deployed at a central site, and it will control gateways at branch sites.</span></span> <span data-ttu-id="29fbb-108">メディアバイパスを有効にすると、ブランチサイトのクライアントからの公衆交換電話網 (PSTN) 通話のメディアを、それらのサイトのゲートウェイを介して直接流すことができます。</span><span class="sxs-lookup"><span data-stu-id="29fbb-108">Enabling media bypass allows media for public switched telephone network (PSTN) calls from clients at branch sites to flow directly through the gateways at those sites.</span></span> <span data-ttu-id="29fbb-109">Lync Server 2013 の発信通話ルートとエンタープライズ音声ポリシーを適切に構成して、ブランチサイトのクライアントからの PSTN 通話を適切なゲートウェイにルーティングできるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="29fbb-109">Lync Server 2013 outbound call routes and Enterprise Voice policies must be properly configured so that PSTN calls from clients at a branch site are routed to the appropriate gateway.</span></span>

<span data-ttu-id="29fbb-110">メディアバイパスを有効にすることを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="29fbb-110">We strongly recommend that you enable media bypass.</span></span> <span data-ttu-id="29fbb-111">ただし、SIP トランクに対してメディアバイパスを有効にする前に、認定された SIP トランクプロバイダーがメディアバイパスをサポートしており、シナリオを正常に有効にするための要件を満たすことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="29fbb-111">However, before you enable media bypass on a SIP trunk, confirm that your qualified SIP trunk provider supports media bypass and is able to accommodate the requirements for successfully enabling the scenario.</span></span> <span data-ttu-id="29fbb-112">具体的には、プロバイダーは、組織の内部ネットワーク内のサーバーの IP アドレスを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="29fbb-112">Specifically, the provider must have the IP addresses of servers in your organization’s internal network.</span></span> <span data-ttu-id="29fbb-113">このシナリオをプロバイダーがサポートできない場合、メディア バイパスは成功しません。</span><span class="sxs-lookup"><span data-stu-id="29fbb-113">If the provider cannot support this scenario, media bypass will not succeed.</span></span> <span data-ttu-id="29fbb-114">詳細については、「計画」のドキュメントの「 [planning for media バイパス In Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29fbb-114">For details, see [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) in the Planning documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="29fbb-115">メディアバイパスは、すべての公衆交換電話網 (PSTN) ゲートウェイ、IP-PBX、およびセッションボーダーコントローラー (SBC) と相互運用することはできません。</span><span class="sxs-lookup"><span data-stu-id="29fbb-115">Media bypass will not interoperate with every public switched telephone network (PSTN) gateway, IP-PBX, and Session Border Controller (SBC).</span></span> <span data-ttu-id="29fbb-116">Microsoft は、認定パートナーで PSTN ゲートウェイと sbc のセットをテストしており、Cisco IP-PBX でいくつかのテストを行いました。</span><span class="sxs-lookup"><span data-stu-id="29fbb-116">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="29fbb-117">メディアバイパスがサポートされるのは、統合コミュニケーションのオープン相互運用性プログラム– Lync Server at <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A>に記載されている製品およびバージョンのみです。</span><span class="sxs-lookup"><span data-stu-id="29fbb-117">Media bypass is supported only with products and versions that are listed on Unified Communications Open Interoperability Program – Lync Server at <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A>.</span></span>



</div>

<span data-ttu-id="29fbb-118">以下に示すトランク構成は、このトランク構成を割り当てられたトランクに適用されるパラメータセットをグループ化します。</span><span class="sxs-lookup"><span data-stu-id="29fbb-118">A trunk configuration as described below groups a set of parameters that are applied to trunks assigned this trunk configuration.</span></span> <span data-ttu-id="29fbb-119">特定のトランク構成は、グローバルに範囲指定できます (特定のサイトまたはプール構成を持たないすべてのトランク、サイト、またはプール)。</span><span class="sxs-lookup"><span data-stu-id="29fbb-119">A particular trunk configuration can be scoped globally (to all trunks that do not have more specific site or pool configuration), or to a site, or to a pool.</span></span> <span data-ttu-id="29fbb-120">プールレベルのトランク構成は、1つのトランクに特定のトランク構成のスコープを設定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="29fbb-120">The pool-level trunk configuration is used to scope a specific trunk configuration to a single trunk.</span></span>

<span id="BKMK_ConfigTrunkMediaBypassSteps"></span>

<div>

## <a name="to-configure-a-trunk-with-media-bypass"></a><span data-ttu-id="29fbb-121">メディアバイパスを使用してトランクを構成するには</span><span class="sxs-lookup"><span data-stu-id="29fbb-121">To configure a trunk with media bypass</span></span>

1.  <span data-ttu-id="29fbb-122">RTCUniversalServerAdmins グループのメンバーとして、または CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="29fbb-122">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="29fbb-123">詳細については、「 [Lync Server 2013 でのセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29fbb-123">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="29fbb-124">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="29fbb-124">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="29fbb-125">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29fbb-125">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="29fbb-126">左側のナビゲーション バーで [**音声ルーティング**] をクリックし、[**トランク構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="29fbb-126">In the left navigation bar, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

4.  <span data-ttu-id="29fbb-127">[**トランク構成**] ページで、次のいずれかの方法を使用してトランクを構成します。</span><span class="sxs-lookup"><span data-stu-id="29fbb-127">On the **Trunk Configuration** page, use one of the following methods to configure a trunk:</span></span>
    
      - <span data-ttu-id="29fbb-128">既存のトランク (たとえば、[**グローバル**] トランク) をダブルクリックして [**トランク構成の編集**] ダイアログ ボックスを表示します。</span><span class="sxs-lookup"><span data-stu-id="29fbb-128">Double-click an existing trunk (for example, the **Global** trunk) to display the **Edit Trunk Configuration** dialog box.</span></span>
    
      - <span data-ttu-id="29fbb-129">[**新規**] をクリックし、新しいトランクのスコープ構成を選択します。</span><span class="sxs-lookup"><span data-stu-id="29fbb-129">Click **New**, and then select a scope for the new trunk configuration:</span></span>
        
          - <span data-ttu-id="29fbb-130">**サイトトランク:**[**サイトの選択**] で、このトランク構成のサイトを選択し、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="29fbb-130">**Site trunk:** Choose the site for this trunk configuration from **Select a Site**, and then click **OK**.</span></span> <span data-ttu-id="29fbb-131">サイトに対してトランク構成が既に作成されている場合、[**サイトの選択**] にはサイトは表示されませんので注意してください。</span><span class="sxs-lookup"><span data-stu-id="29fbb-131">Note that if a trunk configuration has already been created for a site, the site does not appear in **Select a Site**.</span></span> <span data-ttu-id="29fbb-132">このトランク構成は、サイト内のすべてのトランクに適用されます。</span><span class="sxs-lookup"><span data-stu-id="29fbb-132">This trunk configuration will be applied to all trunks in the site.</span></span>
        
          - <span data-ttu-id="29fbb-133">**プールトランク:** このトランク構成を適用するトランクの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="29fbb-133">**Pool trunk:** Choose the name of the trunk that this trunk configuration applies to.</span></span> <span data-ttu-id="29fbb-134">このトランクは、ルートトランクまたはトポロジビルダーで定義された追加のトランクにすることができます。</span><span class="sxs-lookup"><span data-stu-id="29fbb-134">This trunk can be the root trunk or any additional trunks defined in Topology Builder.</span></span> <span data-ttu-id="29fbb-135">[**サービスの選択**] で、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="29fbb-135">From **Select a Service**, click **OK**.</span></span> <span data-ttu-id="29fbb-136">特定のトランクに対してトランク構成が既に作成されている場合、[**サービスの選択**] にはトランクは表示されませんので注意してください。</span><span class="sxs-lookup"><span data-stu-id="29fbb-136">Note that if a trunk configuration has already been created for a specific trunk, the trunk does not appear in **Select a Service**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="29fbb-137">トランク構成のスコープは、選択した後は変更できません。</span><span class="sxs-lookup"><span data-stu-id="29fbb-137">After you select the scope of the trunk configuration, it cannot be changed.</span></span><BR><span data-ttu-id="29fbb-138">[<STRONG>名前</STRONG>] フィールドには、トランク構成に関連付けられたサイトまたはサービスの名前が事前に入力されており、変更できません。</span><span class="sxs-lookup"><span data-stu-id="29fbb-138">The <STRONG>Name</STRONG> field is prepopulated with the name of the trunk configuration’s associated site or service and cannot be changed.</span></span>

    
    </div>

5.  <span data-ttu-id="29fbb-139">**事前にサポートされている最大のダイアログボックス**に値を指定します。</span><span class="sxs-lookup"><span data-stu-id="29fbb-139">Specify a value in **Maximum early dialogs supported**.</span></span> <span data-ttu-id="29fbb-140">これは、公衆交換電話網 (PSTN) ゲートウェイ、IP-PBX、または ITSP セッションボーダーコントローラー (SBC) が仲介サーバーに送信した INVITE に対して受信できる分岐応答の最大数です。</span><span class="sxs-lookup"><span data-stu-id="29fbb-140">This is the maximum number of forked responses a public switched telephone network (PSTN) gateway, IP-PBX, or ITSP Session Border Controller (SBC) can receive to an INVITE that it sent to the Mediation Server.</span></span> <span data-ttu-id="29fbb-141">既定値は 20 です。</span><span class="sxs-lookup"><span data-stu-id="29fbb-141">The default value is 20.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="29fbb-142">この値を変更する前に、サービス プロバイダーまたは機器の製造メーカーに、システムの機能の詳細について問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="29fbb-142">Before you change this value, consult your service provider or equipment manufacturer for details about the capabilities of your system.</span></span>

    
    </div>

6.  <span data-ttu-id="29fbb-143">次のいずれかの **[暗号化サポート レベル]** オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="29fbb-143">Select one of the following **Encryption support level** options:</span></span>
    
      - <span data-ttu-id="29fbb-144">**必須:** 仲介サーバーとゲートウェイまたは構内交換 (PBX) 間のトラフィックを保護するためには、セキュリティで保護されたリアルタイム転送プロトコル (SRTP) 暗号化を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="29fbb-144">**Required:** Secure real-time transport protocol (SRTP) encryption must be used to help protect traffic between the Mediation Server and the gateway or private branch exchange (PBX).</span></span>
    
      - <span data-ttu-id="29fbb-145">**省略可能:** SRTP 暗号化は、サービスプロバイダーまたは機器の製造メーカーがサポートしている場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="29fbb-145">**Optional:** SRTP encryption will be used if the service provider or equipment manufacturer supports it.</span></span>
    
      - <span data-ttu-id="29fbb-146">**サポート対象外:** SRTP 暗号化は、サービスプロバイダーまたは機器の製造元によってサポートされていないため、使用されません。</span><span class="sxs-lookup"><span data-stu-id="29fbb-146">**Not Supported:** SRTP encryption is not supported by the service provider or equipment manufacturer and therefore will not be used.</span></span>

7.  <span data-ttu-id="29fbb-147">トランク ピアによる処理で、メディアが仲介サーバーをバイパスするようにする場合は、**[メディア バイパスを有効にする]** チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="29fbb-147">Select the **Enable media bypass** check box if you want media to bypass the Mediation Server for processing by the trunk peer.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="29fbb-148">メディア バイパスが正常に機能するには、PSTN ゲートウェイ、IP-PBX、または ITSP セッション ボーダー コントローラーが一定の機能をサポートしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="29fbb-148">For media bypass to work successfully, the PSTN gateway, IP-PBX, or ITSP Session Border Controller must support certain capabilities.</span></span> <span data-ttu-id="29fbb-149">詳細については、「計画」のドキュメントの「 <A href="lync-server-2013-planning-for-media-bypass.md">planning for media バイパス In Lync Server 2013</A> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29fbb-149">For details, see <A href="lync-server-2013-planning-for-media-bypass.md">Planning for media bypass in Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>

8.  <span data-ttu-id="29fbb-p111">既知のメディア終端ポイント (たとえば、メディア終端が信号終端と同じ IP を持つ PSTN ゲートウェイ) がある場合は、**[集中メディア処理]** チェック ボックスをオンにします。 トランクに既知のメディア終端ポイントがない場合は、このチェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="29fbb-p111">Select the **Centralized media processing** check box if there is a well-known media termination point (for example, a PSTN gateway where the media termination has the same IP as the signaling termination). Clear this check box if the trunk does not have a well-known media termination point.</span></span>

9.  <span data-ttu-id="29fbb-152">トランクピアが仲介サーバーからの SIP 参照要求の受信をサポートしている場合は、[**ゲートウェイへの参照の送信を有効に**する] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="29fbb-152">If the trunk peer supports receiving SIP REFER requests from the Mediation Server, select the **Enable sending refer to the gateway** check box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="29fbb-153"><STRONG>[メディア バイパスを有効にする]</STRONG> オプションが選択されている場合にこのオプションを無効にするには、追加の設定が必要です。</span><span class="sxs-lookup"><span data-stu-id="29fbb-153">If you disable this option while the <STRONG>Enable media bypass</STRONG> option is selected, additional settings are required.</span></span> <span data-ttu-id="29fbb-154">トランク ピアが仲介サーバーからの SIP REFER 要求の受信をサポートしておらず、メディア バイパスが有効な場合は、メディア バイパスの適正な状態をサポートするため、<STRONG>Set-CsTrunkConfiguration</STRONG> コマンドレットを実行して、アクティブな通話と保留通話の RTCP を無効にする必要もあります。</span><span class="sxs-lookup"><span data-stu-id="29fbb-154">If the trunk peer does not support receiving SIP REFER requests from the Mediation Server and media bypass is enabled, you must also run the <STRONG>Set-CsTrunkConfiguration</STRONG> cmdlet to disable RTCP for active and held calls in order to support proper conditions for media bypass.</span></span> <span data-ttu-id="29fbb-155">詳細については、「 <A href="lync-server-2013-lync-server-management-shell.md">Lync Server 2013 Management Shell</A> 」のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="29fbb-155">For details, see the <A href="lync-server-2013-lync-server-management-shell.md">Lync Server 2013 Management Shell</A> documentation.</span></span><BR><span data-ttu-id="29fbb-156">または、転送された通話をメディアバイパスで、ゲートウェイが SIP REFER 要求をサポートしていない場合は、[<STRONG>サードパーティの通話制御を使用して参照を有効</STRONG>にする] を選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="29fbb-156">Alternatively, you can select <STRONG>Enable refer using third-party-call control</STRONG> if you want transferred calls to be media bypassed, and the gateway does not support SIP REFER requests.</span></span>

    
    </div>

10. <span data-ttu-id="29fbb-p113">(省略可) トランク間ルーティングを有効にするには、このトランク構成に PSTN 使用法レコードを関連付けして、構成します。このトランク構成に関連付けられた PSTN 使用法は、Lync エンドポイントに由来しない、このトランクからのすべての着信に適用されます。トランク構成に関連付けられた PSTN 使用法レコードを管理するには、以下の方法の 1 つを使用します。</span><span class="sxs-lookup"><span data-stu-id="29fbb-p113">(Optional) To enable inter-trunk routing, associate and configure PSTN usage records to this trunk configuration. The PSTN usages associated to this trunk configuration will be applied for all incoming calls through the trunk that is not originating from a Lync endpoint. To manage PSTN usage records associated to a trunk configuration, use one of the following methods:</span></span>
    
      - <span data-ttu-id="29fbb-160">エンタープライズ Voip 展開で利用できるすべての PSTN 使用法レコードの一覧から、1つまたは複数のレコードを選択するには、[**選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="29fbb-160">To select one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="29fbb-161">このトランク構成に関連付けるレコードを選択状態にし、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="29fbb-161">Highlight the records you want to associate with this trunk configuration and then click **OK**.</span></span>
    
      - <span data-ttu-id="29fbb-162">PSTN 使用法レコードをこのトランク構成から削除するには、レコードを選択して [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="29fbb-162">To remove a PSTN usage record from this trunk configuration, select the record and click **Remove**.</span></span>
    
      - <span data-ttu-id="29fbb-163">新しい PSTN 使用法レコードを定義してこのトランク構成に関連付けるには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="29fbb-163">To define a new PSTN usage record and associate it with this trunk configuration, do the following:</span></span>
        
        1.  <span data-ttu-id="29fbb-164">[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="29fbb-164">Click **New**.</span></span>
        
        2.  <span data-ttu-id="29fbb-165">[**名前**] フィールドに、レコードを説明する一意の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="29fbb-165">In the **Name** field, specify a descriptive name for the record that is unique.</span></span>
            
            <div>
            

            > [!NOTE]  
            > <span data-ttu-id="29fbb-p115">PSTN 使用法レコードの名前は、エンタープライズ VoIP 展開内で一意である必要があります。レコードの保存後、[<STRONG>名前</STRONG>] フィールドを編集することはできません。</span><span class="sxs-lookup"><span data-stu-id="29fbb-p115">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

            
            </div>
        
        3.  <span data-ttu-id="29fbb-168">次のいずれかの方法を使用して、この PSTN 使用法レコードのルートの関連付けと構成を行います。</span><span class="sxs-lookup"><span data-stu-id="29fbb-168">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="29fbb-169">エンタープライズ Voip 展開で利用できるすべてのルートの一覧から1つ以上のルートを選択するには、[**選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="29fbb-169">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="29fbb-170">この PSTN 使用法レコードに関連付けるルートを強調表示して、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="29fbb-170">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>
            
              - <span data-ttu-id="29fbb-171">PSTN 使用法レコードからルートを削除するには、ルートを選択し、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="29fbb-171">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>
            
              - <span data-ttu-id="29fbb-172">新しいルートを定義してこの PSTN 使用法レコードに関連付けるには、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="29fbb-172">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="29fbb-173">詳細については、「 [Lync Server 2013 で音声ルートを作成する](lync-server-2013-create-a-voice-route.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29fbb-173">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="29fbb-174">この PSTN 使用法レコードに関連付けられているルートを編集するには、ルートを選択し、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="29fbb-174">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span> <span data-ttu-id="29fbb-175">詳細については、「 [Modify a voice route In Lync Server 2013](lync-server-2013-modify-a-voice-route.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29fbb-175">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        4.  <span data-ttu-id="29fbb-176">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="29fbb-176">Click **OK**.</span></span>
    
      - <span data-ttu-id="29fbb-177">このトランク構成にすでに関連付けられている PSTN 使用法レコードを編集するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="29fbb-177">To edit a PSTN usage record that is already associated with this trunk configuration, do the following:</span></span>
        
        1.  <span data-ttu-id="29fbb-178">編集する PSTN 使用法レコードを選択して、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="29fbb-178">Select the PSTN usage record you want to edit, and click **Show details**.</span></span>
        
        2.  <span data-ttu-id="29fbb-179">次のいずれかの方法を使用して、この PSTN 使用法レコードのルートの関連付けと構成を行います。</span><span class="sxs-lookup"><span data-stu-id="29fbb-179">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="29fbb-180">エンタープライズ Voip 展開で利用できるすべてのルートの一覧から1つ以上のルートを選択するには、[**選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="29fbb-180">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="29fbb-181">この PSTN 使用法レコードに関連付けるルートを強調表示して、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="29fbb-181">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>
            
              - <span data-ttu-id="29fbb-182">PSTN 使用法レコードからルートを削除するには、ルートを選択し、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="29fbb-182">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>
            
              - <span data-ttu-id="29fbb-183">新しいルートを定義してこの PSTN 使用法レコードに関連付けるには、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="29fbb-183">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="29fbb-184">詳細については、「 [Lync Server 2013 で音声ルートを作成する](lync-server-2013-create-a-voice-route.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29fbb-184">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="29fbb-185">この PSTN 使用法レコードに関連付けられているルートを編集するには、ルートを選択し、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="29fbb-185">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span> <span data-ttu-id="29fbb-186">詳細については、「 [Modify a voice route In Lync Server 2013](lync-server-2013-modify-a-voice-route.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29fbb-186">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        3.  <span data-ttu-id="29fbb-187">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="29fbb-187">Click **OK**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="29fbb-188">構成するトランクに関連付けられている仲介サーバーのピアに従って PSTN 使用法レコードを関連付けることが重要です。</span><span class="sxs-lookup"><span data-stu-id="29fbb-188">It important to associate PSTN usage records according to the Mediation Server peer that is associated to the trunk being configured.</span></span> <span data-ttu-id="29fbb-189">仲介サーバーのピアが PSTN ゲートウェイまたはセッションボーダーコントローラー (SBC) である場合は、PSTN の構成に関連付けられている pstn 使用法レコードに関連付けられていないため、PSTN の宛先または Lync 経由で接続された他のダウンストリームシステムServer.</span><span class="sxs-lookup"><span data-stu-id="29fbb-189">If the Mediation Server peer is a PSTN gateway or a Session Border Controller (SBC), it is strongly recommended that the trunk configuration is not associated to a PSTN usage record that routes to a PSTN destination or any other downstream systems connected via Lync Server.</span></span>

    
    </div>

11. <span data-ttu-id="29fbb-p123">最適なパフォーマンスを得る目的で、PSTN 使用法レコードを並べ替えます。一覧内でのレコードの位置を変更するには、PSTN 使用法レコードを選択して、上矢印または下矢印をクリックします。</span><span class="sxs-lookup"><span data-stu-id="29fbb-p123">Arrange the PSTN usage records for optimum performance. To change a record’s position in the list, select the PSTN usage record, and click the up or down arrows.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="29fbb-192">トランク構成の PSTN 使用法レコードのリスト内の順序は重要です。</span><span class="sxs-lookup"><span data-stu-id="29fbb-192">The order in which PSTN usage records are listed in the trunk configuration is significant.</span></span> <span data-ttu-id="29fbb-193">Lync Server は、一覧を上から下に移動します。</span><span class="sxs-lookup"><span data-stu-id="29fbb-193">Lync Server traverses the list from top to down.</span></span>

    
    </div>

12. <span data-ttu-id="29fbb-194">ネットワークアドレス変換 (NAT) またはファイアウォールと、ラッチをサポートする SBC の背後にあるクライアントのバイパスメディアを有効にするには、[ **RTP ラッチを有効**にする] を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="29fbb-194">**Enable RTP Latching** should be selected to enable bypass media for clients behind a network address translation (NAT) or firewall and an SBC that supports latching.</span></span>

13. <span data-ttu-id="29fbb-195">[**フォワード呼び出し履歴を有効**にする] を選択して、仲介サーバーのゲートウェイピアへの通話履歴情報の送信を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="29fbb-195">**Enable forward call history** should be selected to enable sending of call history information to the gateway peer of the Mediation Server.</span></span>

14. <span data-ttu-id="29fbb-196">[転送を有効にする] **-id データを有効**にします。これを有効にするには、仲介サーバー側とゲートウェイ側 (およびその逆) の間で、p がアサート状態 (pai) の呼び出し元情報を転送できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="29fbb-196">**Enable forward P-Asserted-Identity data** should be selected to enable the P-Asserted-Identity (PAI) call originator information to be forwarded between the Mediation Server side and gateway side (and vice versa), when present.</span></span>

15. <span data-ttu-id="29fbb-197">[**送信ルーティング フェールオーバー タイマーを有効にする**] は、高速なフェールオーバーを有効にする場合に選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="29fbb-197">**Enable outbound routing failover timer** should be selected to enable fast failover.</span></span> <span data-ttu-id="29fbb-198">このトランクに関連付けられたゲートウェイは、発信を処理している 10 秒中に通知をすることができます。</span><span class="sxs-lookup"><span data-stu-id="29fbb-198">The gateway associated with this trunk can give notification within 10 seconds that it is processing an outbound call.</span></span> <span data-ttu-id="29fbb-199">この通知が仲介サーバーによって受信されない場合は、別のトランクへの再ルーティングが発生します。</span><span class="sxs-lookup"><span data-stu-id="29fbb-199">Rerouting to another trunk will occur if this notification is not received by the Mediation Server.</span></span> <span data-ttu-id="29fbb-200">待機時間により反応時間が遅くなるネットワーク、または、応答するのに 10 秒以上かかるゲートウェイでは、高速のフェールオーバーを無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="29fbb-200">On networks where latency may delay the response time or the gateway takes longer than 10 seconds to respond, the fast failover should be disabled.</span></span>

16. <span data-ttu-id="29fbb-201">(省略可) トランクの**発信通話番号変換ルール**を関連付けて構成します。</span><span class="sxs-lookup"><span data-stu-id="29fbb-201">(Optional) Associate and configure **calling number translation rules** for the trunk.</span></span> <span data-ttu-id="29fbb-202">これらの変換ルールは、発信電話番号に適用されます。</span><span class="sxs-lookup"><span data-stu-id="29fbb-202">These translation rules apply to the calling number for outbound calls</span></span>
    
      - <span data-ttu-id="29fbb-203">エンタープライズ Voip 展開で利用できるすべての変換ルールの一覧から1つ以上のルールを選択するには、[**選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="29fbb-203">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="29fbb-204">[**変換ルールの選択**] で、トランクに関連付けるルールをクリックして、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="29fbb-204">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>
    
      - <span data-ttu-id="29fbb-205">新しい変換ルールを定義してトランクに関連付ける場合は、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="29fbb-205">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="29fbb-206">新しいルールの定義の詳細については、「展開」のドキュメントの「 [Lync Server 2013 で変換ルールを定義](lync-server-2013-defining-translation-rules.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29fbb-206">For details about defining a new rule, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="29fbb-207">既にトランクに関連付けられている変換ルールを編集するには、ルールの名前をクリックして、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="29fbb-207">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> <span data-ttu-id="29fbb-208">詳細については、「展開」のドキュメントの「 [Lync Server 2013 で変換ルールを定義](lync-server-2013-defining-translation-rules.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29fbb-208">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="29fbb-209">既存の変換ルールをコピーしてそれを基に新しいルールを定義するには、ルールの名前をクリックして [**コピー**] をクリックし、[**貼り付け**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="29fbb-209">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="29fbb-210">詳細については、「 [Lync Server 2013 で変換ルールを定義](lync-server-2013-defining-translation-rules.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29fbb-210">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span></span>
    
      - <span data-ttu-id="29fbb-211">トランクから変換ルールを削除するには、ルールの名前を選択状態にし、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="29fbb-211">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="29fbb-212">関連付けられたトランク ピアに対して変換ルールを構成している場合は、2 つのルールが競合する危険があることから、変換ルールをトランクに関連付けないでください。</span><span class="sxs-lookup"><span data-stu-id="29fbb-212">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>

    
    </div>

17. <span data-ttu-id="29fbb-p131">(省略可) トランクの**発信先通話番号変換ルール**を関連付けて構成します。これらの変換ルールは、発信電話の発信先の電話番号に適用されます。</span><span class="sxs-lookup"><span data-stu-id="29fbb-p131">(Optional) Associate and configure **called number translation rules** for the trunk. The translation rules apply to the called number in an outbound call.</span></span>
    
      - <span data-ttu-id="29fbb-215">エンタープライズ Voip 展開で利用できるすべての変換ルールの一覧から1つ以上のルールを選択するには、[**選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="29fbb-215">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="29fbb-216">[**変換ルールの選択**] で、トランクに関連付けるルールをクリックして、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="29fbb-216">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>
    
      - <span data-ttu-id="29fbb-217">新しい変換ルールを定義してトランクに関連付ける場合は、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="29fbb-217">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="29fbb-218">新しいルールの定義の詳細については、「展開」のドキュメントの「 [Lync Server 2013 で変換ルールを定義](lync-server-2013-defining-translation-rules.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29fbb-218">For details about defining a new rule, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="29fbb-219">既にトランクに関連付けられている変換ルールを編集するには、ルールの名前をクリックして、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="29fbb-219">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> <span data-ttu-id="29fbb-220">詳細については、「展開」のドキュメントの「 [Lync Server 2013 で変換ルールを定義](lync-server-2013-defining-translation-rules.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29fbb-220">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="29fbb-221">既存の変換ルールをコピーしてそれを基に新しいルールを定義するには、ルールの名前をクリックして [**コピー**] をクリックし、[**貼り付け**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="29fbb-221">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="29fbb-222">詳細については、「 [Lync Server 2013 で変換ルールを定義](lync-server-2013-defining-translation-rules.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29fbb-222">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span></span>
    
      - <span data-ttu-id="29fbb-223">トランクから変換ルールを削除するには、ルールの名前を選択状態にし、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="29fbb-223">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="29fbb-224">関連付けられたトランク ピアに対して変換ルールを構成している場合は、2 つのルールが競合する危険があることから、変換ルールをトランクに関連付けないでください。</span><span class="sxs-lookup"><span data-stu-id="29fbb-224">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>

    
    </div>

18. <span data-ttu-id="29fbb-225">トランクの変換ルールが正しい順序で並んでいることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="29fbb-225">Make sure that the trunk’s translation rules are arranged in the correct order.</span></span> <span data-ttu-id="29fbb-226">一覧内でのルールの位置を変更するには、ルールの名前を選択状態にして、上矢印または下矢印をクリックします。</span><span class="sxs-lookup"><span data-stu-id="29fbb-226">To change a rule’s position in the list, highlight the rule name and then click the up or down arrow.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="29fbb-227">Lync Server 2013 は、変換ルールの一覧を上から順にスキャンし、ダイヤルされた番号と最初に一致するルールを使用します。</span><span class="sxs-lookup"><span data-stu-id="29fbb-227">Lync Server 2013 traverses the translation rule list from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="29fbb-228">トランクを構成し、その結果ダイヤルされる番号が複数の変換ルールと一致する可能性がある場合は、制限の厳しいルールを制限の緩いルールよりも上に並べ替えてください。</span><span class="sxs-lookup"><span data-stu-id="29fbb-228">If you configure a trunk so that a dialed number can match more than one translation rule, be sure that the more restrictive rules are sorted above the less restrictive rules.</span></span> <span data-ttu-id="29fbb-229">たとえば、任意の 11 桁の番号と一致する変換ルールと +1425 で始まる 11 桁の番号だけと一致する変換ルールを組み込んでいる場合、任意の 11 桁の番号と一致する変換ルールは、必ず、制限が厳しい方のルールの<EM></EM>下に並べ替えてください。</span><span class="sxs-lookup"><span data-stu-id="29fbb-229">For example, if you have included a translation rule that matches any 11-digit number and a translation rule that matches only 11-digit numbers that start with +1425, be sure that the rule that matches any 11-digit number is sorted <EM>below</EM> the more restrictive rule.</span></span>

    
    </div>

19. <span data-ttu-id="29fbb-230">トランクの構成が終了したら、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="29fbb-230">When you are finished configuring the trunk, click **OK**.</span></span>

20. <span data-ttu-id="29fbb-231">[**トランク構成**] ページで [**確定**] をクリックして、[**すべて確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="29fbb-231">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="29fbb-232">トランクの構成を作成または変更するときは常に、[<STRONG>すべて確定</STRONG>] コマンドを実行して、構成の変更を公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="29fbb-232">Whenever you create or modify a trunk configuration, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="29fbb-233">詳細については、「操作」のドキュメントの「 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 での音声ルーティング構成に対する保留中の変更の公開</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29fbb-233">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

<span data-ttu-id="29fbb-234">トランクを構成した後は、「展開」のドキュメントの「[グローバルメディアバイパスオプション (Lync Server 2013](lync-server-2013-global-media-bypass-options.md) )」で説明するように、グローバルメディアバイパスオプションの中から選択して、メディアバイパスの構成を続行します。</span><span class="sxs-lookup"><span data-stu-id="29fbb-234">After you have configured the trunk, continue configuring media bypass by choosing between global media bypass options, as described in [Global media bypass options in Lync Server 2013](lync-server-2013-global-media-bypass-options.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="29fbb-235">関連項目</span><span class="sxs-lookup"><span data-stu-id="29fbb-235">See Also</span></span>


[<span data-ttu-id="29fbb-236">Lync Server 2013 でメディアバイパスを使用せずにトランクを構成する</span><span class="sxs-lookup"><span data-stu-id="29fbb-236">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)  


[<span data-ttu-id="29fbb-237">Lync Server 2013 でメディアバイパスを構成する</span><span class="sxs-lookup"><span data-stu-id="29fbb-237">Configure media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-media-bypass.md)  
[<span data-ttu-id="29fbb-238">Lync Server 2013 のグローバルメディアバイパスオプション</span><span class="sxs-lookup"><span data-stu-id="29fbb-238">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  


[<span data-ttu-id="29fbb-239">Lync Server 2013 での変換ルールの定義</span><span class="sxs-lookup"><span data-stu-id="29fbb-239">Defining translation rules in Lync Server 2013</span></span>](lync-server-2013-defining-translation-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

