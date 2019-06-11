---
title: 'Lync Server 2013: メディアをバイパスせずにトランクを構成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure a trunk without media bypass
ms:assetid: 3422e93e-7bd2-4470-968c-dc38345b18ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425831(v=OCS.15)
ms:contentKeyID: 48183825
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2e6508fe88a585c22b9936e787be2ee99b8f9b7c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840479"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-trunk-without-media-bypass-in-lync-server-2013"></a><span data-ttu-id="369be-102">Lync Server 2013 でメディアをバイパスせずにトランクを構成する</span><span class="sxs-lookup"><span data-stu-id="369be-102">Configure a trunk without media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="369be-103">_**最終更新日:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="369be-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="369be-104">メディア バイパスを無効にしてトランクを構成する場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="369be-104">If you want to configure a trunk with media bypass disabled, follow these steps.</span></span> <span data-ttu-id="369be-105">メディアバイパスを有効にしてトランクを構成する場合は、「 [Lync Server 2013 でメディアバイパスを使用してトランクを構成](lync-server-2013-configure-a-trunk-with-media-bypass.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="369be-105">If you want to configure a trunk with media bypass enabled, see [Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md).</span></span>

<span data-ttu-id="369be-p102">以下で説明するトランク構成とは、トランクに適用される一連のパラメーターをグループ化したものです。これらのパラメーターは、このトランク構成に割り当てられたものです。特定のトランク構成は、グローバルに (つまり特定のサイトまたはプール構成を持っていないすべてのトランクを対象とする)、またはサイトあるいはプールに対してスコープ指定できます。プールレベル トランク構成は、単一のトランクに固有のトランク構成のスコープを指定する目的で使用されます。</span><span class="sxs-lookup"><span data-stu-id="369be-p102">A trunk configuration, as described below, groups a set of parameters that are applied to trunks assigned this trunk configuration. A particular trunk configuration can be scoped globally (to all trunks that do not have more specific site or pool configuration), or to a site, or to a pool. The pool-level trunk configuration is used to scope a specific trunk configuration to a single trunk.</span></span>

<span id="BKMK_ConfigTrunkGenericSteps"></span>

<div>

## <a name="to-configure-a-trunk-without-media-bypass"></a><span data-ttu-id="369be-109">メディア バイパスを無効にしてトランクを構成するには</span><span class="sxs-lookup"><span data-stu-id="369be-109">To configure a trunk without media bypass</span></span>

1.  <span data-ttu-id="369be-110">RTCUniversalServerAdmins グループのメンバーとして、あるいは CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="369be-110">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="369be-111">詳細については、「 [Lync Server 2013 でセットアップのアクセス許可を委任](lync-server-2013-delegate-setup-permissions.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="369be-111">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="369be-112">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="369be-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="369be-113">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="369be-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="369be-114">左側のナビゲーション バーで [**音声ルーティング**] をクリックし、[**トランク構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="369be-114">In the left navigation bar, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

4.  <span data-ttu-id="369be-115">[**トランク構成**] ページで、次のいずれかの方法を使用してトランクを構成します。</span><span class="sxs-lookup"><span data-stu-id="369be-115">On the **Trunk Configuration** page, use one of the following methods to configure a trunk:</span></span>
    
      - <span data-ttu-id="369be-116">既存のトランク (たとえば、[**グローバル**] トランク) をダブルクリックして [**トランク構成の編集**] ダイアログ ボックスを表示します。</span><span class="sxs-lookup"><span data-stu-id="369be-116">Double-click an existing trunk (for example, the **Global** trunk) to display the **Edit Trunk Configuration** dialog box.</span></span>
    
      - <span data-ttu-id="369be-117">[**新規**] をクリックし、新しいトランク構成のスコープを選択します。</span><span class="sxs-lookup"><span data-stu-id="369be-117">Click **New**, and then select a scope for the new trunk configuration:</span></span>
        
          - <span data-ttu-id="369be-118">**サイトトランク:** このトランク構成のサイトを [**サイトの選択**] で選び、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="369be-118">**Site trunk:** Choose the site for this trunk configuration in **Select a Site** , and then click **OK**.</span></span> <span data-ttu-id="369be-119">サイトに対してトランク構成が既に作成されている場合、[**サイトの選択**] にはサイトは表示されませんので注意してください。</span><span class="sxs-lookup"><span data-stu-id="369be-119">Note that if a trunk configuration has already been created for a site, the site does not appear in **Select a Site**.</span></span> <span data-ttu-id="369be-120">このトランク構成は、サイト内のすべてのトランクに適用されます。</span><span class="sxs-lookup"><span data-stu-id="369be-120">This trunk configuration will be applied to all trunks in the site.</span></span>
        
          - <span data-ttu-id="369be-121">**プールトランク:** このトランク構成が適用されるトランクの名前を選択します。**サービスを選択**して、 **「OK」** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="369be-121">**Pool trunk:** Choose the name of the trunk that this trunk configuration applies to in **Select a Service** and click **OK**.</span></span> <span data-ttu-id="369be-122">このトランクは、ルートトランク、または Topology Builder で定義されたその他の trunks にすることができます。</span><span class="sxs-lookup"><span data-stu-id="369be-122">This trunk can be the root trunk, or any additional trunks defined in Topology Builder.</span></span> <span data-ttu-id="369be-123">特定のトランクに対してトランク構成が既に作成されている場合、[**サービスの選択**] にはトランクは表示されませんので注意してください。</span><span class="sxs-lookup"><span data-stu-id="369be-123">Note that if a trunk configuration has already been created for a specific trunk, the trunk does not appear in **Select a Service**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="369be-124">トランク構成のスコープは、選択後に変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="369be-124">After you select the scope of the trunk configuration, it cannot be changed.</span></span><BR><span data-ttu-id="369be-125">[<STRONG>名前</STRONG>] フィールドには、トランク構成の関連付けられたサイトまたはサービスの名前が事前に入力されており、変更できません。</span><span class="sxs-lookup"><span data-stu-id="369be-125">The <STRONG>Name</STRONG> field is prepopulated with the name of the trunk configuration’s associated site or service and cannot be changed.</span></span>

    
    </div>

5.  <span data-ttu-id="369be-126">次のいずれかの [**暗号化サポート レベル**] オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="369be-126">Select one of the following **Encryption support level** options:</span></span>
    
      - <span data-ttu-id="369be-127">**必須:** セキュリティで保護されたリアルタイムトランスポートプロトコル (SRTP) 暗号化は、仲介サーバーとゲートウェイまたはプライベートブランチ exchange (PBX) 間のトラフィックを保護するために使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="369be-127">**Required:** Secure real-time transport protocol (SRTP) encryption must be used to help protect traffic between the Mediation Server and the gateway or private branch exchange (PBX).</span></span>
    
      - <span data-ttu-id="369be-128">**オプション:** SRTP 暗号化は、サービスプロバイダーまたは機器の製造元がサポートしている場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="369be-128">**Optional:** SRTP encryption will be used if the service provider or equipment manufacturer supports it.</span></span>
    
      - <span data-ttu-id="369be-129">**サポートされていない:** SRTP 暗号化は、サービスプロバイダーまたは機器の製造元によってサポートされていないため、使用されません。</span><span class="sxs-lookup"><span data-stu-id="369be-129">**Not Supported:** SRTP encryption is not supported by the service provider or equipment manufacturer and therefore will not be used.</span></span>

6.  <span data-ttu-id="369be-130">[**メディア バイパスを有効にする**] チェック ボックスがオフになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="369be-130">Be sure that the **Enable media bypass** check box is cleared.</span></span>

7.  <span data-ttu-id="369be-131">既知のメディアの終了ポイントがある場合 (たとえば、公衆交換電話網 (PSTN) ゲートウェイなど、メディアの終了点がシグナリングの終了と同じである) 場合は、[**集中メディア処理**] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="369be-131">Select the **Centralized media processing** check box if there is a well-known media termination point (for example, a public switched telephone network (PSTN) gateway where the media termination has the same IP as the signaling termination).</span></span> <span data-ttu-id="369be-132">トランクに既知のメディア終端ポイントがない場合は、このチェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="369be-132">Clear this check box if the trunk does not have a well-known media termination point.</span></span>

8.  <span data-ttu-id="369be-133">トランクピアが仲介サーバーからの SIP 参照要求の受信をサポートしている場合は、[**ゲートウェイへの参照を有効に**する] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="369be-133">If the trunk peer supports receiving SIP REFER requests from the Mediation Server, select the **Enable sending refer to the gateway** check box.</span></span>

9.  <span data-ttu-id="369be-134">(オプション) トランク間ルーティングを有効にするには、このトランク構成に PSTN 使用法レコードを関連付けて構成します。</span><span class="sxs-lookup"><span data-stu-id="369be-134">(Optional) To enable inter-trunk routing, associate and configure PSTN usage records to this trunk configuration.</span></span> <span data-ttu-id="369be-135">このトランク構成に関連付けられている PSTN 使用状況は、Lync エンドポイントから送信されていないトランク経由のすべての着信に適用されます。</span><span class="sxs-lookup"><span data-stu-id="369be-135">The PSTN usages associated to this trunk configuration will be applied for all incoming calls through the trunk that is not originating from a Lync endpoint.</span></span> <span data-ttu-id="369be-136">トランク構成に関連付けられた PSTN 使用法レコードを管理するには、次のいずれかの方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="369be-136">To manage PSTN usage records associated to a trunk configuration, use one of the following methods:</span></span>
    
      - <span data-ttu-id="369be-137">エンタープライズ Voip 展開で利用できるすべての PSTN 利用状況レコードの一覧から1つまたは複数のレコードを選択するには、[**選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="369be-137">To select one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="369be-138">このトランク構成に関連付けるレコードを選択状態にし、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="369be-138">Highlight the records you want to associate with this trunk configuration and then click **OK**.</span></span>
    
      - <span data-ttu-id="369be-139">PSTN 使用法レコードをこのトランク構成から削除するには、レコードを選択して [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="369be-139">To remove a PSTN usage record from this trunk configuration, select the record and click **Remove**.</span></span>
    
      - <span data-ttu-id="369be-140">新しい PSTN 使用法レコードを定義してこのトランク構成に関連付けるには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="369be-140">To define a new PSTN usage record and associate it with this trunk configuration, do the following:</span></span>
        
        1.  <span data-ttu-id="369be-141">[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="369be-141">Click **New**.</span></span>
        
        2.  <span data-ttu-id="369be-142">[**名前**] フィールドに、レコードを説明する一意の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="369be-142">In the **Name** field, specify a descriptive name for the record that is unique.</span></span>
            
            <div>
            

            > [!NOTE]  
            > <span data-ttu-id="369be-p110">PSTN 使用法レコードの名前は、エンタープライズ VoIP 展開内で一意である必要があります。レコードの保存後、"<STRONG>名前</STRONG>" フィールドを編集することはできません。</span><span class="sxs-lookup"><span data-stu-id="369be-p110">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

            
            </div>
        
        3.  <span data-ttu-id="369be-145">次のいずれかの方法を使用して、この PSTN 使用法レコードのルートの関連付けと構成を行います。</span><span class="sxs-lookup"><span data-stu-id="369be-145">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="369be-146">エンタープライズ Voip 展開で利用可能なすべてのルートの一覧から1つ以上のルートを選ぶには、[**選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="369be-146">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="369be-147">この PSTN 使用状況レコードと関連付けるルートを強調表示し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="369be-147">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>
            
              - <span data-ttu-id="369be-148">PSTN 使用法レコードからルートを削除するには、ルートを選択して [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="369be-148">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>
            
              - <span data-ttu-id="369be-149">新しいルートを定義してこの PSTN 使用法レコードに関連付けるには、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="369be-149">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="369be-150">詳細については、「 [Lync Server 2013 での音声ルートの作成](lync-server-2013-create-a-voice-route.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="369be-150">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="369be-151">この PSTN 使用法レコードに関連付けられているルートを編集するには、ルートを選択して [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="369be-151">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span> <span data-ttu-id="369be-152">詳細については、「 [Lync Server 2013 での音声ルートの変更](lync-server-2013-modify-a-voice-route.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="369be-152">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        4.  <span data-ttu-id="369be-153">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="369be-153">Click **OK**.</span></span>
    
      - <span data-ttu-id="369be-154">このトランク構成に既に関連付けられている PSTN 使用法レコードを編集するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="369be-154">To edit a PSTN usage record that is already associated with this trunk configuration, do the following:</span></span>
        
        1.  <span data-ttu-id="369be-155">編集する PSTN 使用法レコードを選択し、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="369be-155">Select the PSTN usage record you want to edit, and click **Show details**.</span></span>
        
        2.  <span data-ttu-id="369be-156">次のいずれかの方法を使用して、この PSTN 使用法レコードのルートの関連付けと構成を行います。</span><span class="sxs-lookup"><span data-stu-id="369be-156">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="369be-157">エンタープライズ Voip 展開で利用可能なすべてのルートの一覧から1つ以上のルートを選ぶには、[**選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="369be-157">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="369be-158">この PSTN 使用状況レコードと関連付けるルートを強調表示し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="369be-158">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>
            
              - <span data-ttu-id="369be-159">PSTN 使用法レコードからルートを削除するには、ルートを選択して [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="369be-159">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>
            
              - <span data-ttu-id="369be-160">新しいルートを定義してこの PSTN 使用法レコードに関連付けるには、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="369be-160">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="369be-161">詳細については、「 [Lync Server 2013 での音声ルートの作成](lync-server-2013-create-a-voice-route.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="369be-161">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="369be-162">この PSTN 使用法レコードに関連付けられているルートを編集するには、ルートを選択して [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="369be-162">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span> <span data-ttu-id="369be-163">詳細については、「 [Lync Server 2013 での音声ルートの変更](lync-server-2013-modify-a-voice-route.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="369be-163">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        3.  <span data-ttu-id="369be-164">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="369be-164">Click **OK**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="369be-165">構成されているトランクに関連付けられている仲介サーバーピアに従って PSTN 使用状況レコードを関連付けることが重要です。</span><span class="sxs-lookup"><span data-stu-id="369be-165">It important to associate PSTN usage records according to the Mediation Server peer that is associated to the trunk being configured.</span></span> <span data-ttu-id="369be-166">仲介サーバーのピアが PSTN ゲートウェイまたはセッション境界コントローラー (SBC) である場合は、pstn の接続先または Lync 経由で接続されている他の下流システムにルーティングする PSTN 使用状況レコードに、トランク構成が関連付けられていないことを強くお勧めします。Server.</span><span class="sxs-lookup"><span data-stu-id="369be-166">If the Mediation Server peer is a PSTN gateway or a Session Border Controller (SBC), it is strongly recommended that the trunk configuration is not associated to a PSTN usage record that routes to a PSTN destination or any other downstream systems connected via Lync Server.</span></span>

    
    </div>

10. <span data-ttu-id="369be-p118">最適なパフォーマンスを得るために、PSTN 使用法レコードを並べ替えます。一覧内でのレコードの位置を変更するには、PSTN 使用法レコードを選択して、上矢印または下矢印をクリックします。</span><span class="sxs-lookup"><span data-stu-id="369be-p118">Arrange the PSTN usage records for optimum performance. To change a record’s position in the list, select the PSTN usage record, and click the up or down arrows.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="369be-169">トランク構成内の一覧における PSTN 使用法レコードの順序は重要です。</span><span class="sxs-lookup"><span data-stu-id="369be-169">The order in which PSTN usage records are listed in the trunk configuration is significant.</span></span> <span data-ttu-id="369be-170">Lync Server は、リストを上から下に移動します。</span><span class="sxs-lookup"><span data-stu-id="369be-170">Lync Server traverses the list from top to down.</span></span>

    
    </div>

11. <span data-ttu-id="369be-171">[**RTP ラッチを有効にする**] は、NAT またはファイアウォール背後のクライアントと、ラッチングをサポートする SBC のバイパス メディアを有効にする場合に選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="369be-171">**Enable RTP Latching** should be selected to enable bypass media for clients behind a NAT or firewall and an SBC that supports latching.</span></span>

12. <span data-ttu-id="369be-172">仲介サーバーのゲートウェイピアへの通話履歴情報の送信を有効にするには、[転送中の**通話履歴を有効**にする] をオンにします。</span><span class="sxs-lookup"><span data-stu-id="369be-172">**Enable forward call history** should be selected to enable sending of call history information to the gateway peer of the Mediation Server.</span></span>

13. <span data-ttu-id="369be-173">[**転送を有効**にする]-[指定した id データを有効にする] をオンにすると、pai を有効にするには、送信者の情報が仲介サーバー側とゲートウェイ側の間で転送されるようにする必要があります (その逆も可能)。</span><span class="sxs-lookup"><span data-stu-id="369be-173">**Enable forward P-Asserted-Identity data** should be selected to enable PAI call originator information to be forwarded between the Mediation Server side and gateway side (and vice versa), when present.</span></span>

14. <span data-ttu-id="369be-174">高速フェールオーバーを有効にするには、[**送信ルーティング フェールオーバー タイマーを有効にする**] を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="369be-174">**Enable outbound routing failover timer** should be selected to enable fast failover.</span></span> <span data-ttu-id="369be-175">このトランクに関連付けられているゲートウェイは、発信通話を処理しているという通知を 10 秒以内に送信できます。</span><span class="sxs-lookup"><span data-stu-id="369be-175">The gateway associated with this trunk can give notification within 10 seconds that it is processing an outbound call.</span></span> <span data-ttu-id="369be-176">この通知が仲介サーバーによって受信されない場合は、別のトランクへの再ルーティングが行われます。</span><span class="sxs-lookup"><span data-stu-id="369be-176">Rerouting to another trunk will occur if this notification is not received by the Mediation Server.</span></span> <span data-ttu-id="369be-177">ネットワークの待機時間によって応答が遅れる可能性がある場合や、ゲートウェイが 10 秒以内に応答できない場合は、高速フェールオーバーを無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="369be-177">On networks where latency may delay the response time or the gateway takes longer than 10 seconds to respond, the fast failover should be disabled.</span></span>

15. <span data-ttu-id="369be-178">(オプション) トランクの**発信側電話番号変換ルール**を関連付けて構成します。</span><span class="sxs-lookup"><span data-stu-id="369be-178">(Optional) Associate and configure **calling number translation rules** for the trunk.</span></span> <span data-ttu-id="369be-179">これらの変換ルールは、発信通話の発信側電話番号に適用されます。</span><span class="sxs-lookup"><span data-stu-id="369be-179">These translation rules apply to the calling number for outbound calls</span></span>
    
      - <span data-ttu-id="369be-180">エンタープライズ Voip 展開で利用できるすべての翻訳ルールの一覧から1つ以上のルールを選択するには、[**選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="369be-180">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="369be-181">[**変換ルールの選択**] で、トランクに関連付けるルールをクリックして、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="369be-181">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>
    
      - <span data-ttu-id="369be-182">新しい変換ルールを定義してトランクに関連付ける場合は、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="369be-182">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="369be-183">新しいルールの定義の詳細については、展開ドキュメントの「 [Lync Server 2013 で翻訳ルールを定義](lync-server-2013-defining-translation-rules.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="369be-183">For details about defining a new rule, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="369be-184">既にトランクに関連付けられている変換ルールを編集するには、ルールの名前をクリックして、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="369be-184">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> <span data-ttu-id="369be-185">詳細については、展開ドキュメントの「 [Lync Server 2013 で翻訳ルールを定義](lync-server-2013-defining-translation-rules.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="369be-185">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="369be-186">既存の変換ルールをコピーしてそれを基に新しいルールを定義するには、ルールの名前をクリックして [**コピー**] をクリックし、[**貼り付け**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="369be-186">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="369be-187">詳細については、「 [Lync Server 2013 で翻訳ルールを定義](lync-server-2013-defining-translation-rules.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="369be-187">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span></span>
    
      - <span data-ttu-id="369be-188">トランクから変換ルールを削除するには、ルールの名前を選択状態にして、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="369be-188">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398321.security(OCS.15).gif" title="証券" alt="security" /><span data-ttu-id="369be-190">セキュリティメモ:</span><span class="sxs-lookup"><span data-stu-id="369be-190">Security Note:</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><span data-ttu-id="369be-191">関連付けられたトランク ピアに対して変換ルールを構成している場合は、2 つのルールが競合する危険があるため、変換ルールをトランクに関連付けないでください。</span><span class="sxs-lookup"><span data-stu-id="369be-191">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span></td>
    </tr>
    </tbody>
    </table>
    
    </div>

16. <span data-ttu-id="369be-p126">(オプション) トランクの**着信側電話番号変換ルール**を関連付けて構成します。これらの変換ルールは、発信通話の着信側電話番号に適用されます。</span><span class="sxs-lookup"><span data-stu-id="369be-p126">(Optional) Associate and configure **called number translation rules** for the trunk. The translation rules apply to the called number in an outbound call.</span></span>
    
      - <span data-ttu-id="369be-194">エンタープライズ Voip 展開で利用できるすべての翻訳ルールの一覧から1つ以上のルールを選択するには、[**選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="369be-194">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="369be-195">[**変換ルールの選択**] で、トランクに関連付けるルールをクリックして、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="369be-195">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>
    
      - <span data-ttu-id="369be-196">新しい変換ルールを定義してトランクに関連付ける場合は、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="369be-196">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="369be-197">新しいルールの定義の詳細については、展開ドキュメントの「 [Lync Server 2013 で翻訳ルールを定義](lync-server-2013-defining-translation-rules.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="369be-197">For details about defining a new rule, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="369be-198">既にトランクに関連付けられている変換ルールを編集するには、ルールの名前をクリックして、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="369be-198">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> <span data-ttu-id="369be-199">詳細については、展開ドキュメントの「 [Lync Server 2013 で翻訳ルールを定義](lync-server-2013-defining-translation-rules.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="369be-199">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="369be-200">既存の変換ルールをコピーしてそれを基に新しいルールを定義するには、ルールの名前をクリックして [**コピー**] をクリックし、[**貼り付け**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="369be-200">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="369be-201">詳細については、「 [Lync Server 2013 で翻訳ルールを定義](lync-server-2013-defining-translation-rules.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="369be-201">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span></span>
    
      - <span data-ttu-id="369be-202">トランクから変換ルールを削除するには、ルールの名前を選択状態にして、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="369be-202">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="369be-203">関連付けられたトランク ピアに対して変換ルールを構成している場合は、2 つのルールが競合する危険があるため、変換ルールをトランクに関連付けないでください。</span><span class="sxs-lookup"><span data-stu-id="369be-203">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>

    
    </div>

17. <span data-ttu-id="369be-p131">トランクの変換ルールが正しい順序で並んでいることを確認します。一覧内でのルールの位置を変更するには、ルールの名前を選択状態にして、上矢印または下矢印をクリックします。</span><span class="sxs-lookup"><span data-stu-id="369be-p131">Make sure that the trunk’s translation rules are arranged in the correct order. To change a rule’s position in the list, highlight the rule name, and then click the up or down arrow.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="369be-206">Lync Server は、翻訳ルールリストを上から下に移動し、ダイヤルされた番号に一致する最初のルールを使用します。</span><span class="sxs-lookup"><span data-stu-id="369be-206">Lync Server traverses the translation rule list from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="369be-207">トランクを構成し、その結果ダイヤルされる番号が複数の変換ルールと一致する可能性がある場合は、制限の厳しいルールを制限の緩いルールよりも上に並べ替えてください。</span><span class="sxs-lookup"><span data-stu-id="369be-207">If you configure a trunk so that a dialed number can match more than one translation rule, be sure that the more restrictive rules are sorted above the less restrictive rules.</span></span> <span data-ttu-id="369be-208">たとえば、任意の 11 桁の番号と一致する変換ルールと +1425 で始まる 11 桁の番号だけと一致する変換ルールを組み込んでいる場合、任意の 11 桁の番号と一致する変換ルールは、必ず、制限が厳しい方のルールの<EM>下に</EM>並べ替えてください。</span><span class="sxs-lookup"><span data-stu-id="369be-208">For example, if you have included a translation rule that matches any 11-digit number and a translation rule that matches only 11-digit numbers that start with +1425, be sure that the rule that matches any 11-digit number is sorted <EM>below</EM> the more restrictive rule.</span></span>

    
    </div>

18. <span data-ttu-id="369be-209">トランクの構成が終了したら、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="369be-209">When you are finished configuring the trunk, click **OK**.</span></span>

19. <span data-ttu-id="369be-210">[**トランク構成**] ページで [**確定**] をクリックして、[**すべて確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="369be-210">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="369be-211">トランクの構成を作成または変更するときは常に、[<STRONG>すべて確定</STRONG>] コマンドを実行して、構成の変更を公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="369be-211">Whenever you create or modify a trunk configuration, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="369be-212">詳細については、「操作のドキュメントで「 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 のボイスルーティング構成に保留中の変更を発行する</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="369be-212">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="369be-213">関連項目</span><span class="sxs-lookup"><span data-stu-id="369be-213">See Also</span></span>


[<span data-ttu-id="369be-214">Configure a trunk with media bypass in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="369be-214">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  


[<span data-ttu-id="369be-215">Lync Server 2013 での変換ルールの定義</span><span class="sxs-lookup"><span data-stu-id="369be-215">Defining translation rules in Lync Server 2013</span></span>](lync-server-2013-defining-translation-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

