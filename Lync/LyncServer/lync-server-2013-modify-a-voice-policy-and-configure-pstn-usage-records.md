---
title: 'Lync Server 2013: 音声ポリシーを変更し、PSTN 使用状況レコードを構成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Modify a voice policy and configure PSTN usage records
ms:assetid: 6c53aaf5-218b-4bd4-8cea-31bc9d53f1bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398511(v=OCS.15)
ms:contentKeyID: 48184419
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bb7c4cdc47c0624b3d94d0dc52c527310f803d83
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827187"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-a-voice-policy-and-configure-pstn-usage-records-in-lync-server-2013"></a><span data-ttu-id="b0963-102">Lync Server 2013 で音声ポリシーを変更し、PSTN 使用状況レコードを構成する</span><span class="sxs-lookup"><span data-stu-id="b0963-102">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b0963-103">_**最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="b0963-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="b0963-104">音声ポリシーを変更する場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="b0963-104">Follow these steps if you want to modify a voice policy.</span></span> <span data-ttu-id="b0963-105">新しい音声ポリシーを作成する場合は、手順について「 [Lync Server 2013 で音声ポリシーを作成し、PSTN 使用状況レコードを構成](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0963-105">If you want to create a new voice policy, see [Create a voice policy and configure PSTN usage records in Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md) for the procedure.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b0963-106">ボイスポリシーにユーザーが割り当てられている場合、公衆交換電話網 (PSTN) 利用状況レコードが関連付けられていない場合、ユーザーは送信通話を発信できません。</span><span class="sxs-lookup"><span data-stu-id="b0963-106">If a user is assigned to a voice policy has no associated public switched telephone network (PSTN) usage records, the user cannot place outbound calls.</span></span> <span data-ttu-id="b0963-107">エンタープライズ Voip 展開で利用できるすべての PSTN 使用状況レコードの一覧を表示してプロパティを表示するには、「 <A href="lync-server-2013-view-pstn-usage-records.md">Lync Server 2013 で pstn 使用状況レコードを表示</A>する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0963-107">For a listing of all PSTN usage records available in your Enterprise Voice deployment and view their properties, see <A href="lync-server-2013-view-pstn-usage-records.md">View PSTN usage records in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-modify-a-voice-policy"></a><span data-ttu-id="b0963-108">音声ポリシーを変更するには</span><span class="sxs-lookup"><span data-stu-id="b0963-108">To modify a voice policy</span></span>

1.  <span data-ttu-id="b0963-109">RTCUniversalServerAdmins グループのメンバーとして、あるいは CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="b0963-109">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="b0963-110">詳細については、「 [Lync Server 2013 でセットアップのアクセス許可を委任](lync-server-2013-delegate-setup-permissions.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0963-110">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="b0963-111">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="b0963-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b0963-112">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b0963-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b0963-113">左側のナビゲーション バーで [**音声のルーティング**] をクリックし、[**音声ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0963-113">In the left navigation bar, click **Voice Routing**, and then click **Voice Policy**.</span></span>

4.  <span data-ttu-id="b0963-114">[**音声ポリシー**] ページで、音声ポリシー名をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0963-114">On the **Voice Policy** page, double-click a voice policy name.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b0963-p105">スコープと名前は、音声ポリシーの作成時に設定されています。これらは変更できません。</span><span class="sxs-lookup"><span data-stu-id="b0963-p105">The scope and name were set when the voice policy was created. They cannot be changed.</span></span>

    
    </div>

5.  <span data-ttu-id="b0963-117">(オプション) [**音声ポリシーの編集**] に、音声ポリシーの説明情報を追加で入力します。</span><span class="sxs-lookup"><span data-stu-id="b0963-117">(Optional) In **Edit Voice Policy**, enter additional descriptive information for the voice policy.</span></span>

6.  <span data-ttu-id="b0963-118">次のチェック ボックスをオンまたはオフにして、[**通話機能**] をそれぞれ有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="b0963-118">Select or clear the following check boxes to enable or disable each of the **Calling features**:</span></span>
    
      - <span data-ttu-id="b0963-119">[**ボイス メール エスケープ**] は、同時呼び出しが構成されている場合に、電話が電源オフ、電池切れ、または圏外になっているときに、通話がユーザーの携帯電話のボイス メール システムにすぐにルーティングされることを防ぎます。</span><span class="sxs-lookup"><span data-stu-id="b0963-119">**Voice mail escape** prevents calls from being immediately routed to the user’s mobile phone voice mail system when simultaneous ringing is configured and the phone is turned off, out of battery, or out of range.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="b0963-120">この機能を構成できるのは、Lync Server 管理シェルを使用した場合のみです。</span><span class="sxs-lookup"><span data-stu-id="b0963-120">This feature is only configurable through the Lync Server Management Shell</span></span>

        
        </div>
    
      - <span data-ttu-id="b0963-121">[**着信の転送**] では、他の電話機やクライアント デバイスに通話を転送できます。</span><span class="sxs-lookup"><span data-stu-id="b0963-121">**Call forwarding** enables users to forward calls to other phones and client devices.</span></span> <span data-ttu-id="b0963-122">Lync Server 2013 には、通話転送に関するさまざまな構成オプションが用意されています。</span><span class="sxs-lookup"><span data-stu-id="b0963-122">Lync Server 2013 provides a significantly wider range of configuration options for call forwarding.</span></span> <span data-ttu-id="b0963-123">たとえば、着信が外部で PSTN に転送されることを組織が許可しない方針の場合、管理者は特殊な音声ポリシーを適用して、この制限を展開することができます。</span><span class="sxs-lookup"><span data-stu-id="b0963-123">For example, if an organization does not want to allow incoming calls to be forwarded externally to the PSTN, an administrator can apply a special voice policy to deploy this restriction.</span></span> <span data-ttu-id="b0963-124">既定では有効です。</span><span class="sxs-lookup"><span data-stu-id="b0963-124">Enabled by default.</span></span>
    
      - <span data-ttu-id="b0963-125">[**委任**] では、代わりに通話を送受信する他のユーザーを指定できます。</span><span class="sxs-lookup"><span data-stu-id="b0963-125">**Delegation** enables users to specify other users to send and receive calls on their behalf.</span></span> <span data-ttu-id="b0963-126">Lync Server 2013 では、代理人が同時呼び出しを設定することで、そのマネージャーが着信したときに、すべての代理人の同時呼び出し先が呼び出されるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="b0963-126">In Lync Server 2013, a delegate can configure simultaneous ringing that enables incoming calls to his or her manager to ring all of the delegate’s simultaneous ringing targets.</span></span> <span data-ttu-id="b0963-127">これにより、上司に転送された通話に応答するときの柔軟性を高めることができます。</span><span class="sxs-lookup"><span data-stu-id="b0963-127">This provides the delegate with greater flexibility in responding to calls directed to the manager.</span></span> <span data-ttu-id="b0963-128">既定では有効です。</span><span class="sxs-lookup"><span data-stu-id="b0963-128">Enabled by default.</span></span>
    
      - <span data-ttu-id="b0963-p108">[**通話の転送**] では、他のユーザーに通話を転送できます。既定では有効です。</span><span class="sxs-lookup"><span data-stu-id="b0963-p108">**Call transfer** enables users to transfer calls to other users. Enabled by default.</span></span>
    
      - <span data-ttu-id="b0963-p109">[**コール パーク**] では、通話を保留 (パーク) し、別の電話機やクライアントで受けることができます。既定では無効です。</span><span class="sxs-lookup"><span data-stu-id="b0963-p109">**Call park** enables users to park calls on hold, and then pick up the call from a different phone or client. Disabled by default.</span></span>
    
      - <span data-ttu-id="b0963-133">[**同時呼び出し**] では、追加の電話機 (携帯電話など) や他のエンドポイント デバイスで、着信の呼び出し音を鳴らすことができます。</span><span class="sxs-lookup"><span data-stu-id="b0963-133">**Simultaneous ringing** enables incoming calls to ring on additional phones (for example, a mobile phone) or other endpoint devices.</span></span> <span data-ttu-id="b0963-134">Lync Server 2013 では、同時呼び出しの構成オプションが大きく広がります。</span><span class="sxs-lookup"><span data-stu-id="b0963-134">Lync Server 2013 provides a significantly wider range of configuration options for simultaneous ringing.</span></span> <span data-ttu-id="b0963-135">既定では有効です。</span><span class="sxs-lookup"><span data-stu-id="b0963-135">Enabled by default.</span></span>
    
      - <span data-ttu-id="b0963-136">[**チーム呼び出し**] では、定義したチームのユーザーがチームの他のメンバーの呼び出しに応答できます。</span><span class="sxs-lookup"><span data-stu-id="b0963-136">**Team call** enables users on a defined team to answer calls for other members of the team.</span></span> <span data-ttu-id="b0963-137">既定では有効です。</span><span class="sxs-lookup"><span data-stu-id="b0963-137">Enabled by default.</span></span>
    
      - <span data-ttu-id="b0963-138">**Pstn の再ルーティング**では、WAN が混雑しているか利用できない場合は、このポリシーが割り当てられているユーザーによる電話による公衆交換電話網 (PSTN) の再ルーティングが可能になります。</span><span class="sxs-lookup"><span data-stu-id="b0963-138">**PSTN re-route** enables calls made by users who are assigned this policy to other enterprise users to be rerouted on the public switched telephone network (PSTN) if the WAN is congested or unavailable.</span></span> <span data-ttu-id="b0963-139">既定では有効です。</span><span class="sxs-lookup"><span data-stu-id="b0963-139">Enabled by default.</span></span>
    
      - <span data-ttu-id="b0963-140">**帯域幅ポリシー上書き**により、管理者は、特定のユーザーに対して通話受付制御 (CAC) ポリシーの決定を上書きすることができます。</span><span class="sxs-lookup"><span data-stu-id="b0963-140">**Bandwidth policy override** enables administrators to override call admission control (CAC) policy decisions for a particular user.</span></span> <span data-ttu-id="b0963-141">既定では無効です。</span><span class="sxs-lookup"><span data-stu-id="b0963-141">Disabled by default.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="b0963-p114">ポリシーが上書きされるのはユーザーに着信する通話のみです。ユーザーが発信する通話は上書きされません。セッションの確立後、使用帯域幅は正確に記録されます。この設定は慎重に使用してください。</span><span class="sxs-lookup"><span data-stu-id="b0963-p114">The policy will be overridden only for incoming calls to the user and not for outgoing calls that are placed by the user. After the session is established, the bandwidth consumption will be accurately recorded. This setting should be used sparingly.</span></span>

        
        </div>
    
      - <span data-ttu-id="b0963-145">**悪意のある通話トレース**を使用すると、ユーザーはクライアント UI を使って悪意のある呼び出し (爆弾の脅威など) を報告することができます。これは、呼び出しの詳細レコード (CDRs) の呼び出しにフラグを付けます。</span><span class="sxs-lookup"><span data-stu-id="b0963-145">**Malicious call tracing** enables users to report malicious calls (such as bomb threats) using the client UI, which in turn flags the calls in the call detail records (CDRs).</span></span> <span data-ttu-id="b0963-146">既定では無効です。</span><span class="sxs-lookup"><span data-stu-id="b0963-146">Disabled by default.</span></span>

7.  <span data-ttu-id="b0963-147">この音声ポリシーの PSTN 使用法レコードの関連付けと構成を行うには、次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="b0963-147">To associate and configure PSTN usage records for this voice policy, do any of the following:</span></span>
    
      - <span data-ttu-id="b0963-p116">エンタープライズ VoIP 展開で利用できるすべての PSTN 使用法レコードの一覧から、1 つ以上のレコードを選択するには、[**選択**] をクリックします。この音声ポリシーに関連付けるレコードを選択状態にし、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0963-p116">To choose one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**. Highlight the records that you want to associate with this voice policy, and then click **OK**.</span></span>
    
      - <span data-ttu-id="b0963-150">PSTN 使用法レコードをこの音声ポリシーから削除するには、レコードを選択状態にして [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0963-150">To remove a PSTN usage record from this voice policy, highlight the record and click **Remove**.</span></span>
    
      - <span data-ttu-id="b0963-151">新しい PSTN 使用法レコードを定義してこの音声ポリシーに関連付けるには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="b0963-151">To define a new PSTN usage record and associate it with this voice policy, do the following:</span></span>
        
        1.  <span data-ttu-id="b0963-152">[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0963-152">Click **New**.</span></span>
        
        2.  <span data-ttu-id="b0963-p117">"**名前**" フィールドに、レコードを説明する一意の名前を入力します。たとえば、Redmond で勤務しているフルタイム従業員用に **Redmond** という名前の PSTN 使用法レコードを作成し、パートタイム従業員用に **RedmondTemps** という別の名前の PSTN 使用法レコードを作成できます。</span><span class="sxs-lookup"><span data-stu-id="b0963-p117">In the **Name** field, enter a unique descriptive name for the record. For example, you may want to create a PSTN usage record named **Redmond** for full-time employees located in Redmond, and another record named **RedmondTemps** for temporary employees.</span></span>
            
            <div>
            

            > [!NOTE]  
            > <span data-ttu-id="b0963-p118">PSTN 使用法レコードの名前は、エンタープライズ VoIP 展開内で一意である必要があります。レコードの保存後、"<STRONG>名前</STRONG>" フィールドを編集することはできません。</span><span class="sxs-lookup"><span data-stu-id="b0963-p118">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

            
            </div>
        
        3.  <span data-ttu-id="b0963-157">次のいずれかの方法を使用して、この PSTN 使用法レコードのルートの関連付けと構成を行います。</span><span class="sxs-lookup"><span data-stu-id="b0963-157">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="b0963-158">エンタープライズ VoIP 展開で利用できるすべてのルートの一覧から、1 つ以上のルートを選択するには、[**選択**] をクリックし、この PSTN 使用法レコードに関連付けるルートを選択状態にして、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0963-158">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>
            
              - <span data-ttu-id="b0963-159">PSTN 使用法レコードからルートを削除するには、ルートを選択状態にして [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0963-159">To remove a route from the PSTN usage record, highlight the route and click **Remove**.</span></span>
            
              - <span data-ttu-id="b0963-160">新しいルートを定義してこの PSTN 使用法レコードに関連付けるには、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0963-160">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="b0963-161">詳細については、「 [Lync Server 2013 での音声ルートの作成](lync-server-2013-create-a-voice-route.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0963-161">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="b0963-162">この PSTN 使用法レコードに既に関連付けられているルートを編集するには、ルートを選択状態にして [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0963-162">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="b0963-163">詳細については、「 [Lync Server 2013 での音声ルートの変更](lync-server-2013-modify-a-voice-route.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0963-163">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        4.  <span data-ttu-id="b0963-164">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0963-164">Click **OK**.</span></span>
    
      - <span data-ttu-id="b0963-165">この音声ポリシーに既に関連付けられている PSTN 使用法レコードを編集するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="b0963-165">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>
        
        1.  <span data-ttu-id="b0963-166">編集する PSTN 使用法レコードを選択状態にし、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0963-166">Highlight the PSTN usage record that you want to edit and click **Show details**.</span></span>
        
        2.  <span data-ttu-id="b0963-167">次のいずれかの方法を使用して、この PSTN 使用法レコードのルートの関連付けと構成を行います。</span><span class="sxs-lookup"><span data-stu-id="b0963-167">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="b0963-168">エンタープライズ VoIP 展開で利用できるすべてのルートの一覧から、1 つ以上のルートを選択するには、[**選択**] をクリックし、この PSTN 使用法レコードに関連付けるルートを選択状態にして、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0963-168">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>
            
              - <span data-ttu-id="b0963-169">この PSTN 使用法レコードからルートを削除するには、ルートを選択状態にして [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0963-169">To remove a route from this PSTN usage record, highlight the route and click **Remove**.</span></span>
            
              - <span data-ttu-id="b0963-170">新しいルートを定義してこの PSTN 使用法レコードに関連付けるには、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0963-170">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="b0963-171">詳細については、「 [Lync Server 2013 での音声ルートの作成](lync-server-2013-create-a-voice-route.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0963-171">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="b0963-172">この PSTN 使用法レコードに既に関連付けられているルートを編集するには、ルートを選択状態にして [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0963-172">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="b0963-173">詳細については、「 [Lync Server 2013 での音声ルートの変更](lync-server-2013-modify-a-voice-route.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0963-173">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        3.  <span data-ttu-id="b0963-174">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0963-174">Click **OK**.</span></span>

8.  <span data-ttu-id="b0963-p123">最適なパフォーマンスを得るために、PSTN 使用法レコードを並べ替えます。一覧内でのレコードの位置を変更するには、レコードの名前を選択状態にして、上矢印または下矢印をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0963-p123">Arrange the PSTN usage records for optimum performance. To change a record’s position in the list, highlight the record name and click the up or down arrow.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b0963-177">ボイスポリシーに表示される PSTN 使用状況レコードの順序は重要です。</span><span class="sxs-lookup"><span data-stu-id="b0963-177">The order in which PSTN usage records are listed in the voice policy is significant.</span></span> <span data-ttu-id="b0963-178">Lync Server は、一覧を上から下に移動します。</span><span class="sxs-lookup"><span data-stu-id="b0963-178">Lync Server traverses the list from the top down.</span></span> <span data-ttu-id="b0963-179">リストを使用頻度で整理することをお勧めします。例: RedmondLocal、RedmondLongDist、Redmondlocal、Redmondlocal。</span><span class="sxs-lookup"><span data-stu-id="b0963-179">We recommend that you organize the list by frequency of use, for example: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span></span>

    
    </div>

9.  <span data-ttu-id="b0963-180">この音声ポリシーの着信転送および同時呼び出しの PSTN 使用法レコードの関連付けと構成を行うには、次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="b0963-180">To associate and configure PSTN usage records for call forwarding and simultaneous ringing in this voice policy, do any of the following:</span></span>
    
      - <span data-ttu-id="b0963-181">この音声ポリシーのように着信の転送および同時呼び出しに対して同じ PSTN 使用法レコードを使用するには、ドロップダウン メニューから [**呼び出し PSTN 使用法を使用したルーティング**] オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="b0963-181">To use the same PSTN usage records for call forwarding and simultaneous ringing as this voice policy, select the option **Route using the call PSTN usages** from the drop-down menu.</span></span>
    
      - <span data-ttu-id="b0963-182">着信の転送と同時呼び出しを内部の Lync ユーザーのみに許可するには、ドロップダウンメニューから [**内部の lync ユーザーへのルーティングのみ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b0963-182">To allow call forwarding and simultaneous ringing to internal Lync users only, select **Route to internal Lync users only** from the drop-down menu.</span></span> <span data-ttu-id="b0963-183">Calls will not be forwarded to external PSTN numbers.</span><span class="sxs-lookup"><span data-stu-id="b0963-183">Calls will not be forwarded to external PSTN numbers.</span></span>
    
      - <span data-ttu-id="b0963-p126">この音声ポリシーに使用されているのとは別の PTSN 使用法レコードを着信の転送と同時呼び出しに指定する場合は、ドロップダウン メニューから [**カスタムの PSTN 使用法を使用したルーティング**] を選択します。このオプションを選択するとコントロールが表示され、着信の転送と同時呼び出しに対して、既存の PSTN 使用法レコードを選択するかまたは新しい PSTN 使用法レコードを作成できます。</span><span class="sxs-lookup"><span data-stu-id="b0963-p126">To specify different PSTN usage records for call forwarding and simultaneous ringing than those used for this voice policy, select the option **Route using custom PSTN usages** from the drop-down menu. This option displays a control to select existing PSTN usage records or to create new PSTN usage records, specifically for call forwarding and simultaneous ringing.</span></span>
        
          - <span data-ttu-id="b0963-p127">着信の転送および同時呼び出しの PSTN 使用法レコードの一覧から、1 つ以上のレコードを選択するには、[**選択**] をクリックします。この着信の転送および同時呼び出しポリシーに関連付けるレコードを選択状態にし、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0963-p127">To choose one or more records from a list of PSTN usage records for call forwarding and simultaneous ringing, click **Select**. Highlight the records that you want to associate with this call forwarding and simultaneous ringing policy, and then click **OK**.</span></span>
        
          - <span data-ttu-id="b0963-188">PSTN 使用法レコードをこの着信の転送および同時呼び出しポリシーから削除するには、レコードを選択状態にして [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0963-188">To remove a PSTN usage record from this call forwarding and simultaneous ringing policy, highlight the record and click **Remove**.</span></span>
        
          - <span data-ttu-id="b0963-189">新しい PSTN 使用法レコードを定義してこの着信の転送および同時呼び出しポリシーに関連付けるには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="b0963-189">To define a new PSTN usage record and associate it with this call forwarding and simultaneous ringing policy, do the following:</span></span>
            
            1.  <span data-ttu-id="b0963-190">[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0963-190">Click **New**.</span></span>
            
            2.  <span data-ttu-id="b0963-191">"**名前**" フィールドに、レコードを説明する一意の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="b0963-191">In the **Name** field, enter a unique descriptive name for the record.</span></span>
                
                <div>
                

                > [!NOTE]  
                > <span data-ttu-id="b0963-p128">PSTN 使用法レコードの名前は、エンタープライズ VoIP 展開内で一意である必要があります。レコードの保存後、"<STRONG>名前</STRONG>" フィールドを編集することはできません。</span><span class="sxs-lookup"><span data-stu-id="b0963-p128">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

                
                </div>
            
            3.  <span data-ttu-id="b0963-194">次のいずれかの方法を使用して、この PSTN 使用法レコードのルートの関連付けと構成を行います。</span><span class="sxs-lookup"><span data-stu-id="b0963-194">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
                
                  - <span data-ttu-id="b0963-195">エンタープライズ VoIP 展開で利用できるすべてのルートの一覧から、1 つ以上のルートを選択するには、[**選択**] をクリックし、この PSTN 使用法レコードに関連付けるルートを選択状態にして、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0963-195">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>
                
                  - <span data-ttu-id="b0963-196">PSTN 使用法レコードからルートを削除するには、ルートを選択状態にして [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0963-196">To remove a route from the PSTN usage record, highlight the route and click **Remove**.</span></span>
                
                  - <span data-ttu-id="b0963-197">新しいルートを定義してこの PSTN 使用法レコードに関連付けるには、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0963-197">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="b0963-198">詳細については、「 [Lync Server 2013 での音声ルートの作成](lync-server-2013-create-a-voice-route.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0963-198">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
                
                  - <span data-ttu-id="b0963-199">この PSTN 使用法レコードに既に関連付けられているルートを編集するには、ルートを選択状態にして [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0963-199">To edit a route that is already associated with this PSTN usage record, highlight the route, and then click **Show details**.</span></span> <span data-ttu-id="b0963-200">詳細については、「 [Lync Server 2013 での音声ルートの変更](lync-server-2013-modify-a-voice-route.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0963-200">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
            
            4.  <span data-ttu-id="b0963-201">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0963-201">Click **OK**.</span></span>
        
          - <span data-ttu-id="b0963-202">この音声ポリシーに既に関連付けられている PSTN 使用法レコードを編集するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="b0963-202">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>
            
            1.  <span data-ttu-id="b0963-203">編集する PSTN 使用法レコードを選択状態にし、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0963-203">Highlight the PSTN usage record that you want to edit and click **Show details**.</span></span>
            
            2.  <span data-ttu-id="b0963-204">次のいずれかの方法を使用して、この PSTN 使用法レコードのルートの関連付けと構成を行います。</span><span class="sxs-lookup"><span data-stu-id="b0963-204">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
                
                  - <span data-ttu-id="b0963-205">エンタープライズ VoIP 展開で利用できるすべてのルートの一覧から、1 つ以上のルートを選択するには、[**選択**] をクリックし、この PSTN 使用法レコードに関連付けるルートを選択状態にして、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0963-205">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes you want to associate with this PSTN usage record, and then click **OK**.</span></span>
                
                  - <span data-ttu-id="b0963-206">この PSTN 使用法レコードからルートを削除するには、ルートを選択状態にして [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0963-206">To remove a route from this PSTN usage record, highlight the route and click **Remove**.</span></span>
                
                  - <span data-ttu-id="b0963-207">新しいルートを定義してこの PSTN 使用法レコードに関連付けるには、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0963-207">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="b0963-208">詳細については、「 [Lync Server 2013 での音声ルートの作成](lync-server-2013-create-a-voice-route.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0963-208">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
                
                  - <span data-ttu-id="b0963-209">この PSTN 使用法レコードに既に関連付けられているルートを編集するには、ルートを選択状態にして [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0963-209">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="b0963-210">詳細については、「 [Lync Server 2013 での音声ルートの変更](lync-server-2013-modify-a-voice-route.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0963-210">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
            
            3.  <span data-ttu-id="b0963-211">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0963-211">Click **OK**.</span></span>

10. <span data-ttu-id="b0963-p133">(オプション) 音声ポリシーをテストする番号を入力して、[**実行**] をクリックします。テスト結果は、[**テストする変換後の番号**] の下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="b0963-p133">(Optional) Enter a number to test the voice policy and click **Go**. The test results are displayed under **Translated number to test**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b0963-214">まだテストに合格しない音声ポリシーを保存し、後で再構成することができます。</span><span class="sxs-lookup"><span data-stu-id="b0963-214">You can save a voice policy that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="b0963-215">詳細については、「 <A href="lync-server-2013-test-voice-routing.md">Lync Server 2013 での音声ルーティングのテスト</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0963-215">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

11. <span data-ttu-id="b0963-216">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0963-216">Click **OK**.</span></span>

12. <span data-ttu-id="b0963-217">[**音声ポリシー**] ページで [**確定**] をクリックし、[**すべて確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0963-217">On the **Voice Policy** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b0963-218">音声ポリシーを作成または変更するときは常に、[<STRONG>すべて確定</STRONG>] コマンドを実行して、構成の変更を公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b0963-218">Whenever you create or modify a voice policy, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="b0963-219">詳細については、「操作のドキュメントで「 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 のボイスルーティング構成に保留中の変更を発行する</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0963-219">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

13. <span data-ttu-id="b0963-220">(オプション) ボイスメール エスケープは、着信がユーザーの携帯電話のボイス メールによって即座に応答されたことを検出し、携帯電話のボイス メールへの通話を切断します。</span><span class="sxs-lookup"><span data-stu-id="b0963-220">(Optional) Voicemail Escape detects that a call was immediately answered by the user’s mobile phone voice mail, and disconnects the call to the mobile phone voice mail.</span></span> <span data-ttu-id="b0963-221">これにより、ユーザーの他のエンドポイントで着信の呼び出しが続けられるので、ユーザーは着信に応答できるようになります。</span><span class="sxs-lookup"><span data-stu-id="b0963-221">This allows the call to continue to ring on the user’s other endpoints giving the user the opportunity to answer the call.</span></span> <span data-ttu-id="b0963-222">ボイスメールのポリシーを構成する方法の詳細については、「 [Lync Server 2013 でボイスメールのエスケープを構成](lync-server-2013-configuring-voice-mail-escape.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0963-222">For details about how to configure a voice mail policy, see [Configuring voice mail escape in Lync Server 2013](lync-server-2013-configuring-voice-mail-escape.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b0963-223">関連項目</span><span class="sxs-lookup"><span data-stu-id="b0963-223">See Also</span></span>


[<span data-ttu-id="b0963-224">Lync Server 2013 で音声ポリシーを作成し、PSTN 使用状況レコードを構成する</span><span class="sxs-lookup"><span data-stu-id="b0963-224">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="b0963-225">Lync Server 2013 での PSTN 使用状況レコードの表示</span><span class="sxs-lookup"><span data-stu-id="b0963-225">View PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-view-pstn-usage-records.md)  
[<span data-ttu-id="b0963-226">Lync Server 2013 での音声ルートの作成</span><span class="sxs-lookup"><span data-stu-id="b0963-226">Create a voice route in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-route.md)  
[<span data-ttu-id="b0963-227">Lync Server 2013 での音声ルートの変更</span><span class="sxs-lookup"><span data-stu-id="b0963-227">Modify a voice route in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-route.md)  
[<span data-ttu-id="b0963-228">Lync Server 2013 の音声ルーティング構成に保留中の変更を発行する</span><span class="sxs-lookup"><span data-stu-id="b0963-228">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  
[<span data-ttu-id="b0963-229">Lync Server 2013 でボイスメールのエスケープを構成する</span><span class="sxs-lookup"><span data-stu-id="b0963-229">Configuring voice mail escape in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-mail-escape.md)  


[<span data-ttu-id="b0963-230">Lync Server 2013 での音声ルーティングのテスト</span><span class="sxs-lookup"><span data-stu-id="b0963-230">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

