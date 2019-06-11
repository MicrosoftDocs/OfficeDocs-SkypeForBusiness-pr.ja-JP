---
title: 'Lync Server 2013: メディアバイパスを使用してトランクを構成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure a trunk with media bypass
ms:assetid: 99d729ea-5a4c-4ff2-a4a3-93a24368da6d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398792(v=OCS.15)
ms:contentKeyID: 48184959
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 41f5f254dfd3ad63d3f6390f16837c777bd02a91
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840491"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-trunk-with-media-bypass-in-lync-server-2013"></a><span data-ttu-id="d10fb-102">Configure a trunk with media bypass in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d10fb-102">Configure a trunk with media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d10fb-103">_**最終更新日:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="d10fb-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="d10fb-104">メディア バイパスを有効にしてトランクを構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="d10fb-104">Follow these steps to configure a trunk with media bypass enabled.</span></span> <span data-ttu-id="d10fb-105">メディアのバイパスを無効にしてトランクを構成する方法については、「 [Lync Server 2013 でメディアをバイパスせずにトランクを構成](lync-server-2013-configure-a-trunk-without-media-bypass.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d10fb-105">To configure a trunk with media bypass disabled, see [Configure a trunk without media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md).</span></span> <span data-ttu-id="d10fb-106">メディアのバイパスは、展開されている仲介サーバーの数を最小化する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="d10fb-106">Media bypass is useful when you want to minimize the number of Mediation Servers deployed.</span></span> <span data-ttu-id="d10fb-107">通常、仲介サーバープールはセントラルサイトに展開され、ブランチサイトでのゲートウェイを制御します。</span><span class="sxs-lookup"><span data-stu-id="d10fb-107">Typically, a Mediation Server pool will be deployed at a central site, and it will control gateways at branch sites.</span></span> <span data-ttu-id="d10fb-108">メディア バイパスを有効にすると、ブランチ サイトのクライアントからの公衆交換電話網 (PSTN) 通話のメディアが、そのブランチ サイトのゲートウェイを直接通過することができます。</span><span class="sxs-lookup"><span data-stu-id="d10fb-108">Enabling media bypass allows media for public switched telephone network (PSTN) calls from clients at branch sites to flow directly through the gateways at those sites.</span></span> <span data-ttu-id="d10fb-109">支社サイトのクライアントからの PSTN 通話が適切なゲートウェイにルーティングされるように、Lync Server 2013 の発信通話ルーティングとエンタープライズボイスポリシーを適切に構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d10fb-109">Lync Server 2013 outbound call routes and Enterprise Voice policies must be properly configured so that PSTN calls from clients at a branch site are routed to the appropriate gateway.</span></span>

<span data-ttu-id="d10fb-110">メディアのバイパスを有効にすることを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d10fb-110">We strongly recommend that you enable media bypass.</span></span> <span data-ttu-id="d10fb-111">ただし、SIP トランクでメディアバイパスを有効にする前に、認定された SIP トランクのプロバイダーがメディアのバイパスをサポートしており、そのシナリオを正常に有効にするための要件を満たすことができることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d10fb-111">However, before you enable media bypass on a SIP trunk, confirm that your qualified SIP trunk provider supports media bypass and is able to accommodate the requirements for successfully enabling the scenario.</span></span> <span data-ttu-id="d10fb-112">具体的には、プロバイダーは、組織の内部ネットワーク内のサーバーの IP アドレスを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d10fb-112">Specifically, the provider must have the IP addresses of servers in your organization’s internal network.</span></span> <span data-ttu-id="d10fb-113">プロバイダーがこのシナリオをサポートできない場合、メディアのバイパスは成功しません。</span><span class="sxs-lookup"><span data-stu-id="d10fb-113">If the provider cannot support this scenario, media bypass will not succeed.</span></span> <span data-ttu-id="d10fb-114">詳細については、計画ドキュメントの「 [Lync Server 2013 でのメディアのバイパスの計画](lync-server-2013-planning-for-media-bypass.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d10fb-114">For details, see [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) in the Planning documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d10fb-115">メディアバイパスは、公衆交換電話網 (PSTN) ゲートウェイ、IP PBX、およびセッションボーダーコントローラー (SBC) との相互運用には対応していません。</span><span class="sxs-lookup"><span data-stu-id="d10fb-115">Media bypass will not interoperate with every public switched telephone network (PSTN) gateway, IP-PBX, and Session Border Controller (SBC).</span></span> <span data-ttu-id="d10fb-116">マイクロソフトでは、認定パートナーの PSTN ゲートウェイと SBC でテストを行い、Cisco IP-PBX でも一定のテストを行いました。</span><span class="sxs-lookup"><span data-stu-id="d10fb-116">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="d10fb-117">メディアのバイパスは、統合された通信のオープン相互運用性プログラム– Lync Server at <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>の製品とバージョンでのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="d10fb-117">Media bypass is supported only with products and versions that are listed on Unified Communications Open Interoperability Program – Lync Server at <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>.</span></span>



</div>

<span data-ttu-id="d10fb-p104">以下で説明するトランク構成では、そのトランク構成が割り当てられるトランクに適用される一連のパラメーターがグループ化されています。トランク構成のスコープは、グローバル (サイトまたはプールの構成を持たないすべてのトランクに適用されます)、サイト、またはプールにすることができます。プール レベルのトランク構成は、トランク構成のスコープを 1 つのトランクにするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="d10fb-p104">A trunk configuration as described below groups a set of parameters that are applied to trunks assigned this trunk configuration. A particular trunk configuration can be scoped globally (to all trunks that do not have more specific site or pool configuration), or to a site, or to a pool. The pool-level trunk configuration is used to scope a specific trunk configuration to a single trunk.</span></span>

<span id="BKMK_ConfigTrunkMediaBypassSteps"></span>

<div>

## <a name="to-configure-a-trunk-with-media-bypass"></a><span data-ttu-id="d10fb-121">メディア バイパスを有効にしてトランクを構成するには</span><span class="sxs-lookup"><span data-stu-id="d10fb-121">To configure a trunk with media bypass</span></span>

1.  <span data-ttu-id="d10fb-122">RTCUniversalServerAdmins グループのメンバーとして、あるいは CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="d10fb-122">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="d10fb-123">詳細については、「 [Lync Server 2013 でセットアップのアクセス許可を委任](lync-server-2013-delegate-setup-permissions.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d10fb-123">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="d10fb-124">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="d10fb-124">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d10fb-125">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d10fb-125">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d10fb-126">左側のナビゲーション バーで [**音声ルーティング**] をクリックし、[**トランク構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d10fb-126">In the left navigation bar, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

4.  <span data-ttu-id="d10fb-127">[**トランク構成**] ページで、次のいずれかの方法を使用してトランクを構成します。</span><span class="sxs-lookup"><span data-stu-id="d10fb-127">On the **Trunk Configuration** page, use one of the following methods to configure a trunk:</span></span>
    
      - <span data-ttu-id="d10fb-128">既存のトランク (たとえば、[**グローバル**] トランク) をダブルクリックして [**トランク構成の編集**] ダイアログ ボックスを表示します。</span><span class="sxs-lookup"><span data-stu-id="d10fb-128">Double-click an existing trunk (for example, the **Global** trunk) to display the **Edit Trunk Configuration** dialog box.</span></span>
    
      - <span data-ttu-id="d10fb-129">[**新規**] をクリックし、新しいトランク構成のスコープを選択します。</span><span class="sxs-lookup"><span data-stu-id="d10fb-129">Click **New**, and then select a scope for the new trunk configuration:</span></span>
        
          - <span data-ttu-id="d10fb-130">**サイトトランク:**[**サイトを選択**してください] からこのトランク構成のサイトを選び、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d10fb-130">**Site trunk:** Choose the site for this trunk configuration from **Select a Site**, and then click **OK**.</span></span> <span data-ttu-id="d10fb-131">サイトに対してトランク構成が既に作成されている場合、[**サイトの選択**] にはサイトは表示されませんので注意してください。</span><span class="sxs-lookup"><span data-stu-id="d10fb-131">Note that if a trunk configuration has already been created for a site, the site does not appear in **Select a Site**.</span></span> <span data-ttu-id="d10fb-132">このトランク構成は、サイト内のすべてのトランクに適用されます。</span><span class="sxs-lookup"><span data-stu-id="d10fb-132">This trunk configuration will be applied to all trunks in the site.</span></span>
        
          - <span data-ttu-id="d10fb-133">**プールトランク:** このトランク構成が適用されるトランクの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="d10fb-133">**Pool trunk:** Choose the name of the trunk that this trunk configuration applies to.</span></span> <span data-ttu-id="d10fb-134">このトランクは、トポロジービルダーで定義されているルートトランクまたは追加の trunks にすることができます。</span><span class="sxs-lookup"><span data-stu-id="d10fb-134">This trunk can be the root trunk or any additional trunks defined in Topology Builder.</span></span> <span data-ttu-id="d10fb-135">[  **サービスの選択**  ] で、[  **OK**  ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d10fb-135">From **Select a Service**, click **OK**.</span></span> <span data-ttu-id="d10fb-136">トランク構成が既に作成されているトランクは [  **サービスの選択**  ] に表示されません。</span><span class="sxs-lookup"><span data-stu-id="d10fb-136">Note that if a trunk configuration has already been created for a specific trunk, the trunk does not appear in **Select a Service**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d10fb-137">トランク構成のスコープは、選択後に変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="d10fb-137">After you select the scope of the trunk configuration, it cannot be changed.</span></span><BR><span data-ttu-id="d10fb-138">[<STRONG>名前</STRONG>] フィールドには、トランク構成の関連付けられたサイトまたはサービスの名前が事前に入力されており、変更できません。</span><span class="sxs-lookup"><span data-stu-id="d10fb-138">The <STRONG>Name</STRONG> field is prepopulated with the name of the trunk configuration’s associated site or service and cannot be changed.</span></span>

    
    </div>

5.  <span data-ttu-id="d10fb-p109">[**サポートされる最大早期ダイアログ数**] に値を指定します。これは公衆交換電話網 (PSTN) ゲートウェイ、IP-PBX、または ITSP セッション ボーダー コントローラー (SBC) が、仲介サーバーに送信した INVITE に対して受信できる分岐応答の最大数です。既定値は 20 です。</span><span class="sxs-lookup"><span data-stu-id="d10fb-p109">Specify a value in **Maximum early dialogs supported**. This is the maximum number of forked responses a public switched telephone network (PSTN) gateway, IP-PBX, or ITSP Session Border Controller (SBC) can receive to an INVITE that it sent to the Mediation Server. The default value is 20.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d10fb-142">この値を変更する前に、サービス プロバイダーまたは機器の製造メーカーに、システムの機能の詳細について問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="d10fb-142">Before you change this value, consult your service provider or equipment manufacturer for details about the capabilities of your system.</span></span>

    
    </div>

6.  <span data-ttu-id="d10fb-143">次のいずれかの [**暗号化サポート レベル**] オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="d10fb-143">Select one of the following **Encryption support level** options:</span></span>
    
      - <span data-ttu-id="d10fb-144">**必須:** セキュリティで保護されたリアルタイムトランスポートプロトコル (SRTP) 暗号化は、仲介サーバーとゲートウェイまたはプライベートブランチ exchange (PBX) 間のトラフィックを保護するために使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d10fb-144">**Required:** Secure real-time transport protocol (SRTP) encryption must be used to help protect traffic between the Mediation Server and the gateway or private branch exchange (PBX).</span></span>
    
      - <span data-ttu-id="d10fb-145">**オプション:** SRTP 暗号化は、サービスプロバイダーまたは機器の製造元がサポートしている場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="d10fb-145">**Optional:** SRTP encryption will be used if the service provider or equipment manufacturer supports it.</span></span>
    
      - <span data-ttu-id="d10fb-146">**サポートされていない:** SRTP 暗号化は、サービスプロバイダーまたは機器の製造元によってサポートされていないため、使用されません。</span><span class="sxs-lookup"><span data-stu-id="d10fb-146">**Not Supported:** SRTP encryption is not supported by the service provider or equipment manufacturer and therefore will not be used.</span></span>

7.  <span data-ttu-id="d10fb-147">トランク ピアによる処理で、メディアが仲介サーバーをバイパスするようにする場合は、[**メディア バイパスを有効にする**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="d10fb-147">Select the **Enable media bypass** check box if you want media to bypass the Mediation Server for processing by the trunk peer.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d10fb-148">メディア バイパスが正常に機能するには、PSTN ゲートウェイ、IP-PBX、または ITSP セッション ボーダー コントローラーが一定の機能をサポートしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d10fb-148">For media bypass to work successfully, the PSTN gateway, IP-PBX, or ITSP Session Border Controller must support certain capabilities.</span></span> <span data-ttu-id="d10fb-149">詳細については、計画ドキュメントの「 <A href="lync-server-2013-planning-for-media-bypass.md">Lync Server 2013 でのメディアのバイパスの計画</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d10fb-149">For details, see <A href="lync-server-2013-planning-for-media-bypass.md">Planning for media bypass in Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>

8.  <span data-ttu-id="d10fb-p111">既知のメディア終端ポイント (たとえば、メディア終端が信号終端と同じ IP を持つ PSTN ゲートウェイ) がある場合は、[**集中メディア処理**] チェック ボックスをオンにします。トランクに既知のメディア終端ポイントがない場合は、このチェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="d10fb-p111">Select the **Centralized media processing** check box if there is a well-known media termination point (for example, a PSTN gateway where the media termination has the same IP as the signaling termination). Clear this check box if the trunk does not have a well-known media termination point.</span></span>

9.  <span data-ttu-id="d10fb-152">トランクピアが仲介サーバーからの SIP 参照要求の受信をサポートしている場合は、[**ゲートウェイへの参照を有効に**する] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="d10fb-152">If the trunk peer supports receiving SIP REFER requests from the Mediation Server, select the **Enable sending refer to the gateway** check box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d10fb-153">[<STRONG>メディア バイパスを有効にする</STRONG>] オプションが選択されている場合にこのオプションを無効にするには、追加の設定が必要です。</span><span class="sxs-lookup"><span data-stu-id="d10fb-153">If you disable this option while the <STRONG>Enable media bypass</STRONG> option is selected, additional settings are required.</span></span> <span data-ttu-id="d10fb-154">トランク ピアが仲介サーバーからの SIP REFER 要求の受信をサポートしておらず、メディア バイパスが有効な場合は、メディア バイパスの適正な状態をサポートするため、<STRONG>Set-CsTrunkConfiguration</STRONG> コマンドレットを実行して、アクティブな通話と保留通話の RTCP を無効にする必要もあります。</span><span class="sxs-lookup"><span data-stu-id="d10fb-154">If the trunk peer does not support receiving SIP REFER requests from the Mediation Server and media bypass is enabled, you must also run the <STRONG>Set-CsTrunkConfiguration</STRONG> cmdlet to disable RTCP for active and held calls in order to support proper conditions for media bypass.</span></span> <span data-ttu-id="d10fb-155">詳細については、「 <A href="lync-server-2013-lync-server-management-shell.md">Lync Server 2013 管理シェル</A>のドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d10fb-155">For details, see the <A href="lync-server-2013-lync-server-management-shell.md">Lync Server 2013 Management Shell</A> documentation.</span></span><BR><span data-ttu-id="d10fb-156">ゲートウェイが SIP REFER 要求をサポートしていない場合に転送通話をメディア バイパスするには、[<STRONG>サードパーティ通話コントロールを使用する参照を有効にする</STRONG>] を選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="d10fb-156">Alternatively, you can select <STRONG>Enable refer using third-party-call control</STRONG> if you want transferred calls to be media bypassed, and the gateway does not support SIP REFER requests.</span></span>

    
    </div>

10. <span data-ttu-id="d10fb-157">(オプション) トランク間ルーティングを有効にするには、このトランク構成に PSTN 使用法レコードを関連付けて構成します。</span><span class="sxs-lookup"><span data-stu-id="d10fb-157">(Optional) To enable inter-trunk routing, associate and configure PSTN usage records to this trunk configuration.</span></span> <span data-ttu-id="d10fb-158">このトランク構成に関連付けられている PSTN 使用状況は、Lync エンドポイントから送信されていないトランク経由のすべての着信に適用されます。</span><span class="sxs-lookup"><span data-stu-id="d10fb-158">The PSTN usages associated to this trunk configuration will be applied for all incoming calls through the trunk that is not originating from a Lync endpoint.</span></span> <span data-ttu-id="d10fb-159">トランク構成に関連付けられた PSTN 使用法レコードを管理するには、次のいずれかの方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="d10fb-159">To manage PSTN usage records associated to a trunk configuration, use one of the following methods:</span></span>
    
      - <span data-ttu-id="d10fb-160">エンタープライズ Voip 展開で利用できるすべての PSTN 利用状況レコードの一覧から1つまたは複数のレコードを選択するには、[**選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d10fb-160">To select one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="d10fb-161">このトランク構成に関連付けるレコードを選択状態にし、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d10fb-161">Highlight the records you want to associate with this trunk configuration and then click **OK**.</span></span>
    
      - <span data-ttu-id="d10fb-162">PSTN 使用法レコードをこのトランク構成から削除するには、レコードを選択して [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d10fb-162">To remove a PSTN usage record from this trunk configuration, select the record and click **Remove**.</span></span>
    
      - <span data-ttu-id="d10fb-163">新しい PSTN 使用法レコードを定義してこのトランク構成に関連付けるには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="d10fb-163">To define a new PSTN usage record and associate it with this trunk configuration, do the following:</span></span>
        
        1.  <span data-ttu-id="d10fb-164">[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d10fb-164">Click **New**.</span></span>
        
        2.  <span data-ttu-id="d10fb-165">[**名前**] フィールドに、レコードを説明する一意の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="d10fb-165">In the **Name** field, specify a descriptive name for the record that is unique.</span></span>
            
            <div>
            

            > [!NOTE]  
            > <span data-ttu-id="d10fb-p115">PSTN 使用法レコードの名前は、エンタープライズ VoIP 展開内で一意である必要があります。レコードの保存後、"<STRONG>名前</STRONG>" フィールドを編集することはできません。</span><span class="sxs-lookup"><span data-stu-id="d10fb-p115">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

            
            </div>
        
        3.  <span data-ttu-id="d10fb-168">次のいずれかの方法を使用して、この PSTN 使用法レコードのルートの関連付けと構成を行います。</span><span class="sxs-lookup"><span data-stu-id="d10fb-168">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="d10fb-169">エンタープライズ Voip 展開で利用可能なすべてのルートの一覧から1つ以上のルートを選ぶには、[**選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d10fb-169">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="d10fb-170">この PSTN 使用状況レコードと関連付けるルートを強調表示し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d10fb-170">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>
            
              - <span data-ttu-id="d10fb-171">PSTN 使用法レコードからルートを削除するには、ルートを選択して [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d10fb-171">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>
            
              - <span data-ttu-id="d10fb-172">新しいルートを定義してこの PSTN 使用法レコードに関連付けるには、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d10fb-172">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="d10fb-173">詳細については、「 [Lync Server 2013 での音声ルートの作成](lync-server-2013-create-a-voice-route.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d10fb-173">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="d10fb-174">この PSTN 使用法レコードに関連付けられているルートを編集するには、ルートを選択して [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d10fb-174">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span> <span data-ttu-id="d10fb-175">詳細については、「 [Lync Server 2013 での音声ルートの変更](lync-server-2013-modify-a-voice-route.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d10fb-175">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        4.  <span data-ttu-id="d10fb-176">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d10fb-176">Click **OK**.</span></span>
    
      - <span data-ttu-id="d10fb-177">このトランク構成に既に関連付けられている PSTN 使用法レコードを編集するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="d10fb-177">To edit a PSTN usage record that is already associated with this trunk configuration, do the following:</span></span>
        
        1.  <span data-ttu-id="d10fb-178">編集する PSTN 使用法レコードを選択し、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d10fb-178">Select the PSTN usage record you want to edit, and click **Show details**.</span></span>
        
        2.  <span data-ttu-id="d10fb-179">次のいずれかの方法を使用して、この PSTN 使用法レコードのルートの関連付けと構成を行います。</span><span class="sxs-lookup"><span data-stu-id="d10fb-179">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="d10fb-180">エンタープライズ Voip 展開で利用可能なすべてのルートの一覧から1つ以上のルートを選ぶには、[**選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d10fb-180">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="d10fb-181">この PSTN 使用状況レコードと関連付けるルートを強調表示し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d10fb-181">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>
            
              - <span data-ttu-id="d10fb-182">PSTN 使用法レコードからルートを削除するには、ルートを選択して [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d10fb-182">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>
            
              - <span data-ttu-id="d10fb-183">新しいルートを定義してこの PSTN 使用法レコードに関連付けるには、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d10fb-183">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="d10fb-184">詳細については、「 [Lync Server 2013 での音声ルートの作成](lync-server-2013-create-a-voice-route.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d10fb-184">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="d10fb-185">この PSTN 使用法レコードに関連付けられているルートを編集するには、ルートを選択して [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d10fb-185">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span> <span data-ttu-id="d10fb-186">詳細については、「 [Lync Server 2013 での音声ルートの変更](lync-server-2013-modify-a-voice-route.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d10fb-186">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        3.  <span data-ttu-id="d10fb-187">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d10fb-187">Click **OK**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d10fb-188">構成されているトランクに関連付けられている仲介サーバーピアに従って PSTN 使用状況レコードを関連付けることが重要です。</span><span class="sxs-lookup"><span data-stu-id="d10fb-188">It important to associate PSTN usage records according to the Mediation Server peer that is associated to the trunk being configured.</span></span> <span data-ttu-id="d10fb-189">仲介サーバーのピアが PSTN ゲートウェイまたはセッション境界コントローラー (SBC) である場合は、pstn の接続先または Lync 経由で接続されている他の下流システムにルーティングする PSTN 使用状況レコードに、トランク構成が関連付けられていないことを強くお勧めします。Server.</span><span class="sxs-lookup"><span data-stu-id="d10fb-189">If the Mediation Server peer is a PSTN gateway or a Session Border Controller (SBC), it is strongly recommended that the trunk configuration is not associated to a PSTN usage record that routes to a PSTN destination or any other downstream systems connected via Lync Server.</span></span>

    
    </div>

11. <span data-ttu-id="d10fb-p123">最適なパフォーマンスを得るために、PSTN 使用法レコードを並べ替えます。一覧内でのレコードの位置を変更するには、PSTN 使用法レコードを選択して、上矢印または下矢印をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d10fb-p123">Arrange the PSTN usage records for optimum performance. To change a record’s position in the list, select the PSTN usage record, and click the up or down arrows.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d10fb-192">トランク構成内の一覧における PSTN 使用法レコードの順序は重要です。</span><span class="sxs-lookup"><span data-stu-id="d10fb-192">The order in which PSTN usage records are listed in the trunk configuration is significant.</span></span> <span data-ttu-id="d10fb-193">Lync Server は、リストを上から下に移動します。</span><span class="sxs-lookup"><span data-stu-id="d10fb-193">Lync Server traverses the list from top to down.</span></span>

    
    </div>

12. <span data-ttu-id="d10fb-194">ネットワーク アドレス変換 (NAT) またはファイアウォールとラッチをサポートしている SBC の背後にあるクライアントに対してバイパス メディアを有効にするには、[**RTP ラッチを有効にする**] を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d10fb-194">**Enable RTP Latching** should be selected to enable bypass media for clients behind a network address translation (NAT) or firewall and an SBC that supports latching.</span></span>

13. <span data-ttu-id="d10fb-195">仲介サーバーのゲートウェイピアへの通話履歴情報の送信を有効にするには、[転送中の**通話履歴を有効**にする] をオンにします。</span><span class="sxs-lookup"><span data-stu-id="d10fb-195">**Enable forward call history** should be selected to enable sending of call history information to the gateway peer of the Mediation Server.</span></span>

14. <span data-ttu-id="d10fb-196">[**転送を有効に**する]-[指定した id データを有効にする] をオンにすると、仲介サーバー側とゲートウェイ側の間で転送される p-identity (pai) 呼び出しオリジネータの情報が表示されます (その逆も可能)。</span><span class="sxs-lookup"><span data-stu-id="d10fb-196">**Enable forward P-Asserted-Identity data** should be selected to enable the P-Asserted-Identity (PAI) call originator information to be forwarded between the Mediation Server side and gateway side (and vice versa), when present.</span></span>

15. <span data-ttu-id="d10fb-197">高速フェールオーバーを有効にするには、[**送信ルーティング フェールオーバー タイマーを有効にする**] を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d10fb-197">**Enable outbound routing failover timer** should be selected to enable fast failover.</span></span> <span data-ttu-id="d10fb-198">このトランクに関連付けられているゲートウェイは、発信通話を処理しているという通知を 10 秒以内に送信できます。</span><span class="sxs-lookup"><span data-stu-id="d10fb-198">The gateway associated with this trunk can give notification within 10 seconds that it is processing an outbound call.</span></span> <span data-ttu-id="d10fb-199">この通知が仲介サーバーによって受信されない場合は、別のトランクへの再ルーティングが行われます。</span><span class="sxs-lookup"><span data-stu-id="d10fb-199">Rerouting to another trunk will occur if this notification is not received by the Mediation Server.</span></span> <span data-ttu-id="d10fb-200">ネットワークの待機時間によって応答が遅れる可能性がある場合や、ゲートウェイが 10 秒以内に応答できない場合は、高速フェールオーバーを無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d10fb-200">On networks where latency may delay the response time or the gateway takes longer than 10 seconds to respond, the fast failover should be disabled.</span></span>

16. <span data-ttu-id="d10fb-201">(オプション) トランクの**発信側電話番号変換ルール**を関連付けて構成します。</span><span class="sxs-lookup"><span data-stu-id="d10fb-201">(Optional) Associate and configure **calling number translation rules** for the trunk.</span></span> <span data-ttu-id="d10fb-202">これらの変換ルールは、発信通話の発信側電話番号に適用されます。</span><span class="sxs-lookup"><span data-stu-id="d10fb-202">These translation rules apply to the calling number for outbound calls</span></span>
    
      - <span data-ttu-id="d10fb-203">エンタープライズ Voip 展開で利用できるすべての翻訳ルールの一覧から1つ以上のルールを選択するには、[**選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d10fb-203">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="d10fb-204">[**変換ルールの選択**] で、トランクに関連付けるルールをクリックして、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d10fb-204">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>
    
      - <span data-ttu-id="d10fb-205">新しい変換ルールを定義してトランクに関連付ける場合は、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d10fb-205">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="d10fb-206">新しいルールの定義の詳細については、展開ドキュメントの「 [Lync Server 2013 で翻訳ルールを定義](lync-server-2013-defining-translation-rules.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d10fb-206">For details about defining a new rule, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="d10fb-207">既にトランクに関連付けられている変換ルールを編集するには、ルールの名前をクリックして、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d10fb-207">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> <span data-ttu-id="d10fb-208">詳細については、展開ドキュメントの「 [Lync Server 2013 で翻訳ルールを定義](lync-server-2013-defining-translation-rules.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d10fb-208">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="d10fb-209">既存の変換ルールをコピーしてそれを基に新しいルールを定義するには、ルールの名前をクリックして [**コピー**] をクリックし、[**貼り付け**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d10fb-209">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="d10fb-210">詳細については、「 [Lync Server 2013 で翻訳ルールを定義](lync-server-2013-defining-translation-rules.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d10fb-210">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span></span>
    
      - <span data-ttu-id="d10fb-211">トランクから変換ルールを削除するには、ルールの名前を選択状態にして、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d10fb-211">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="d10fb-212">関連付けられたトランク ピアに対して変換ルールを構成している場合は、2 つのルールが競合する危険があるため、変換ルールをトランクに関連付けないでください。</span><span class="sxs-lookup"><span data-stu-id="d10fb-212">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>

    
    </div>

17. <span data-ttu-id="d10fb-p131">(オプション) トランクの**着信側電話番号変換ルール**を関連付けて構成します。これらの変換ルールは、発信通話の着信側電話番号に適用されます。</span><span class="sxs-lookup"><span data-stu-id="d10fb-p131">(Optional) Associate and configure **called number translation rules** for the trunk. The translation rules apply to the called number in an outbound call.</span></span>
    
      - <span data-ttu-id="d10fb-215">エンタープライズ Voip 展開で利用できるすべての翻訳ルールの一覧から1つ以上のルールを選択するには、[**選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d10fb-215">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="d10fb-216">[**変換ルールの選択**] で、トランクに関連付けるルールをクリックして、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d10fb-216">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>
    
      - <span data-ttu-id="d10fb-217">新しい変換ルールを定義してトランクに関連付ける場合は、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d10fb-217">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="d10fb-218">新しいルールの定義の詳細については、展開ドキュメントの「 [Lync Server 2013 で翻訳ルールを定義](lync-server-2013-defining-translation-rules.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d10fb-218">For details about defining a new rule, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="d10fb-219">既にトランクに関連付けられている変換ルールを編集するには、ルールの名前をクリックして、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d10fb-219">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> <span data-ttu-id="d10fb-220">詳細については、展開ドキュメントの「 [Lync Server 2013 で翻訳ルールを定義](lync-server-2013-defining-translation-rules.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d10fb-220">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="d10fb-221">既存の変換ルールをコピーしてそれを基に新しいルールを定義するには、ルールの名前をクリックして [**コピー**] をクリックし、[**貼り付け**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d10fb-221">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="d10fb-222">詳細については、「 [Lync Server 2013 で翻訳ルールを定義](lync-server-2013-defining-translation-rules.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d10fb-222">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span></span>
    
      - <span data-ttu-id="d10fb-223">トランクから変換ルールを削除するには、ルールの名前を選択状態にして、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d10fb-223">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="d10fb-224">関連付けられたトランク ピアに対して変換ルールを構成している場合は、2 つのルールが競合する危険があるため、変換ルールをトランクに関連付けないでください。</span><span class="sxs-lookup"><span data-stu-id="d10fb-224">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>

    
    </div>

18. <span data-ttu-id="d10fb-p136">トランクの変換ルールが、正しい順序で並んでいることを確認します。一覧内でのルールの位置を変更するには、ルールの名前を選んで、上矢印または下矢印をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d10fb-p136">Make sure that the trunk’s translation rules are arranged in the correct order. To change a rule’s position in the list, highlight the rule name and then click the up or down arrow.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d10fb-227">Lync Server 2013 は、翻訳ルールリストを上から下に移動し、ダイヤルされた番号に一致する最初のルールを使用します。</span><span class="sxs-lookup"><span data-stu-id="d10fb-227">Lync Server 2013 traverses the translation rule list from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="d10fb-228">トランクを構成し、その結果ダイヤルされる番号が複数の変換ルールと一致する可能性がある場合は、制限の厳しいルールを制限の緩いルールよりも上に並べ替えてください。</span><span class="sxs-lookup"><span data-stu-id="d10fb-228">If you configure a trunk so that a dialed number can match more than one translation rule, be sure that the more restrictive rules are sorted above the less restrictive rules.</span></span> <span data-ttu-id="d10fb-229">たとえば、任意の 11 桁の番号と一致する変換ルールと +1425 で始まる 11 桁の番号だけと一致する変換ルールを組み込んでいる場合、任意の 11 桁の番号と一致する変換ルールは、必ず、制限が厳しい方のルールの<EM>下に</EM>並べ替えてください。</span><span class="sxs-lookup"><span data-stu-id="d10fb-229">For example, if you have included a translation rule that matches any 11-digit number and a translation rule that matches only 11-digit numbers that start with +1425, be sure that the rule that matches any 11-digit number is sorted <EM>below</EM> the more restrictive rule.</span></span>

    
    </div>

19. <span data-ttu-id="d10fb-230">トランクの構成が終了したら、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d10fb-230">When you are finished configuring the trunk, click **OK**.</span></span>

20. <span data-ttu-id="d10fb-231">[**トランク構成**] ページで [**確定**] をクリックして、[**すべて確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d10fb-231">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d10fb-232">トランクの構成を作成または変更するときは常に、[<STRONG>すべて確定</STRONG>] コマンドを実行して、構成の変更を公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d10fb-232">Whenever you create or modify a trunk configuration, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="d10fb-233">詳細については、「操作のドキュメントで「 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 のボイスルーティング構成に保留中の変更を発行する</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d10fb-233">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

<span data-ttu-id="d10fb-234">トランクを構成したら、展開ドキュメントの「 [Lync Server 2013 のグローバルメディアバイパス](lync-server-2013-global-media-bypass-options.md)オプション」で説明されているように、[グローバルメディアバイパス] オプションを選んで、メディアバイパスの構成を続行します。</span><span class="sxs-lookup"><span data-stu-id="d10fb-234">After you have configured the trunk, continue configuring media bypass by choosing between global media bypass options, as described in [Global media bypass options in Lync Server 2013](lync-server-2013-global-media-bypass-options.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d10fb-235">関連項目</span><span class="sxs-lookup"><span data-stu-id="d10fb-235">See Also</span></span>


[<span data-ttu-id="d10fb-236">Lync Server 2013 でメディアをバイパスせずにトランクを構成する</span><span class="sxs-lookup"><span data-stu-id="d10fb-236">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)  


[<span data-ttu-id="d10fb-237">Lync Server 2013 メディア バイパスの構成</span><span class="sxs-lookup"><span data-stu-id="d10fb-237">Configure media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-media-bypass.md)  
[<span data-ttu-id="d10fb-238">Lync Server 2013 のグローバルメディアバイパスオプション</span><span class="sxs-lookup"><span data-stu-id="d10fb-238">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  


[<span data-ttu-id="d10fb-239">Lync Server 2013 での変換ルールの定義</span><span class="sxs-lookup"><span data-stu-id="d10fb-239">Defining translation rules in Lync Server 2013</span></span>](lync-server-2013-defining-translation-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

