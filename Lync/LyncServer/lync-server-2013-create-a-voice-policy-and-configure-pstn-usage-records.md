---
title: 'Lync Server 2013: 音声ポリシーを作成し、PSTN 使用状況レコードを構成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a voice policy and configure PSTN usage records
ms:assetid: e6ff27e0-e2d1-4445-840f-08f738200c20
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399027(v=OCS.15)
ms:contentKeyID: 48185693
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 80537aabe132f1b83714d42244409224ca53f72d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756291"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-voice-policy-and-configure-pstn-usage-records-in-lync-server-2013"></a><span data-ttu-id="7a113-102">Lync Server 2013 で音声ポリシーを作成し、PSTN 使用状況レコードを構成する</span><span class="sxs-lookup"><span data-stu-id="7a113-102">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7a113-103">_**最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="7a113-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="7a113-104">新しいボイスポリシーを作成する場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="7a113-104">Follow these steps if you want to create a new voice policy.</span></span> <span data-ttu-id="7a113-105">音声ポリシーを編集する場合は、「 [Lync Server 2013 で音声ポリシーを変更し、PSTN 使用状況レコードを構成](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a113-105">If you want to edit a voice policy, see [Modify a voice policy and configure PSTN usage records in Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md) for the procedure.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7a113-106">各ボイスポリシーには、少なくとも1つの公衆交換電話網 (PSTN) 利用状況レコードが必要です。</span><span class="sxs-lookup"><span data-stu-id="7a113-106">Each voice policy must have at least one associated public switched telephone network (PSTN) usage record.</span></span> <span data-ttu-id="7a113-107">エンタープライズ Voip 展開で利用できるすべての PSTN 利用状況レコードの一覧を表示し、そのプロパティを表示するには、「 <A href="lync-server-2013-view-pstn-usage-records.md">Lync Server 2013 で pstn 使用状況レコードを表示</A>する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a113-107">To see a listing of all PSTN usage records available in your Enterprise Voice deployment and view their properties, see <A href="lync-server-2013-view-pstn-usage-records.md">View PSTN usage records in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-create-a-voice-policy"></a><span data-ttu-id="7a113-108">音声ポリシーを作成するには</span><span class="sxs-lookup"><span data-stu-id="7a113-108">To create a voice policy</span></span>

1.  <span data-ttu-id="7a113-109">RTCUniversalServerAdmins グループのメンバーとして、あるいは CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="7a113-109">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="7a113-110">詳細については、「 [Lync Server 2013 でセットアップのアクセス許可を委任](lync-server-2013-delegate-setup-permissions.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a113-110">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="7a113-111">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="7a113-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="7a113-112">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7a113-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="7a113-113">左側のナビゲーション バーで [**音声のルーティング**] をクリックし、[**音声ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7a113-113">In the left navigation bar, click **Voice Routing** and then click **Voice Policy**.</span></span>

4.  <span data-ttu-id="7a113-114">[**音声ポリシー**] ページで [**新規**] をクリックし、新しいポリシーのスコープを選択します。</span><span class="sxs-lookup"><span data-stu-id="7a113-114">On the **Voice Policy** page, click **New** and then select a scope for the new policy:</span></span>
    
      - <span data-ttu-id="7a113-p105">[**サイト ポリシー**] は、ユーザー ポリシーに割り当てられているユーザーまたはグループを除いて、サイト全体に適用されます。ポリシー スコープとしてサイトを選択する場合は、[**サイトの選択**] ダイアログ ボックスでサイトを選択します。サイトで音声ポリシーが既に作成されている場合、そのサイトは [**サイトの選択**] ダイアログ ボックスに表示されません。</span><span class="sxs-lookup"><span data-stu-id="7a113-p105">**Site policy** applies to an entire site, except any users or groups that are assigned to a user policy. If you select Site for a policy scope, choose the site from the **Select a Site** dialog box. If a voice policy has already been created for a site, the site does not appear in the **Select a Site** dialog box.</span></span>
    
      - <span data-ttu-id="7a113-118">[**ユーザー ポリシー**] は、指定したユーザーまたはグループに適用できます。</span><span class="sxs-lookup"><span data-stu-id="7a113-118">**User policy** can be applied to specified users or groups.</span></span>

5.  <span data-ttu-id="7a113-119">音声ポリシー スコープがユーザーの場合は、そのポリシーのわかりやすい名前を "**名前**" フィールドに入力します。</span><span class="sxs-lookup"><span data-stu-id="7a113-119">If the voice policy scope is User, enter a descriptive name for the policy in the **Name** field.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7a113-120">音声ポリシー スコープがサイトの場合は、[<STRONG>新しい音声ポリシー</STRONG>] の "<STRONG>名前</STRONG>" フィールドにサイト名が事前に入力されており、変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="7a113-120">If the voice policy scope is Site, the <STRONG>Name</STRONG> field in <STRONG>New Voice Policy</STRONG> is prepopulated with the site name and cannot be changed.</span></span>

    
    </div>

6.  <span data-ttu-id="7a113-121">(オプション) その音声ポリシーについての追加説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="7a113-121">(Optional) Enter additional descriptive information for the voice policy.</span></span>

7.  <span data-ttu-id="7a113-122">次のチェック ボックスをオンまたはオフにして、この音声ポリシーの各 [**通話機能**] を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="7a113-122">Select or clear the following check boxes to enable or disable each of the **Calling features** for this voice policy:</span></span>
    
      - <span data-ttu-id="7a113-123">[**ボイス メール エスケープ**] は、同時呼び出しが構成されている場合に、電話が電源オフ、電池切れ、または圏外になっているときに、通話がユーザーの携帯電話のボイス メール システムにすぐにルーティングされることを防ぎます。</span><span class="sxs-lookup"><span data-stu-id="7a113-123">**Voice mail escape** prevents calls from being immediately routed to the user’s mobile phone voice mail system when simultaneous ringing is configured and the phone is turned off, out of battery, or out of range.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="7a113-124">この機能を構成できるのは、Lync Server 管理シェルを使用した場合のみです。</span><span class="sxs-lookup"><span data-stu-id="7a113-124">This feature is only configurable through the Lync Server Management Shell</span></span>

        
        </div>
    
      - <span data-ttu-id="7a113-125">[**着信の転送**] では、他の電話機やクライアント デバイスに通話を転送できます。</span><span class="sxs-lookup"><span data-stu-id="7a113-125">**Call forwarding** enables users to forward calls to other phones and client devices.</span></span> <span data-ttu-id="7a113-126">Lync Server 2013 には、通話転送に関するさまざまな構成オプションが用意されています。</span><span class="sxs-lookup"><span data-stu-id="7a113-126">Lync Server 2013 provides a significantly wider range of configuration options for call forwarding.</span></span> <span data-ttu-id="7a113-127">たとえば、着信が外部で PSTN に転送されることを組織が許可しない方針の場合、管理者は特殊な音声ポリシーを適用して、この制限を展開することができます。</span><span class="sxs-lookup"><span data-stu-id="7a113-127">For example, if an organization does not want to allow incoming calls to be forwarded externally to the PSTN, an administrator can apply a special voice policy to deploy this restriction.</span></span> <span data-ttu-id="7a113-128">既定では有効です。</span><span class="sxs-lookup"><span data-stu-id="7a113-128">Enabled by default.</span></span>
    
      - <span data-ttu-id="7a113-129">[**委任**] では、代わりに通話を送受信する他のユーザーを指定できます。</span><span class="sxs-lookup"><span data-stu-id="7a113-129">**Delegation** enables users to specify other users to send and receive calls on their behalf.</span></span> <span data-ttu-id="7a113-130">Lync Server 2013 では、代理人が同時呼び出しを設定することで、そのマネージャーが着信したときに、すべての代理人の同時呼び出し先が呼び出されるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="7a113-130">In Lync Server 2013, a delegate can configure simultaneous ringing that enables incoming calls to his or her manager to ring all of the delegate’s simultaneous ringing targets.</span></span> <span data-ttu-id="7a113-131">これにより、上司に転送された通話に応答するときの柔軟性を高めることができます。</span><span class="sxs-lookup"><span data-stu-id="7a113-131">This provides the delegate with greater flexibility in responding to calls directed to the manager.</span></span> <span data-ttu-id="7a113-132">既定では有効です。</span><span class="sxs-lookup"><span data-stu-id="7a113-132">Enabled by default.</span></span>
    
      - <span data-ttu-id="7a113-p108">[**通話の転送**] では、他のユーザーに通話を転送できます。既定では有効です。</span><span class="sxs-lookup"><span data-stu-id="7a113-p108">**Call transfer** enables users to transfer calls to other users. Enabled by default.</span></span>
    
      - <span data-ttu-id="7a113-p109">[**コール パーク**] では、通話を保留 (パーク) し、別の電話機やクライアントで受けることができます。既定では無効です。</span><span class="sxs-lookup"><span data-stu-id="7a113-p109">**Call park** enables users to park calls on hold and then pick up the call from a different phone or client. Disabled by default.</span></span>
    
      - <span data-ttu-id="7a113-137">[**同時呼び出し**] では、追加の電話機 (携帯電話など) や他のエンドポイント デバイスで、着信の呼び出し音を鳴らすことができます。</span><span class="sxs-lookup"><span data-stu-id="7a113-137">**Simultaneous ringing** enables incoming calls to ring on additional phones (for example, a mobile phone) or other endpoint devices.</span></span> <span data-ttu-id="7a113-138">Lync Server 2013 では、同時呼び出しの構成オプションが大きく広がります。</span><span class="sxs-lookup"><span data-stu-id="7a113-138">Lync Server 2013 provides a significantly wider range of configuration options for simultaneous ringing.</span></span> <span data-ttu-id="7a113-139">既定では有効です。</span><span class="sxs-lookup"><span data-stu-id="7a113-139">Enabled by default.</span></span>
    
      - <span data-ttu-id="7a113-140">[**チーム呼び出し**] では、定義したチームのユーザーがチームの他のメンバーの呼び出しに応答できます。</span><span class="sxs-lookup"><span data-stu-id="7a113-140">**Team call** enables users on a defined team to answer calls for other members of the team.</span></span> <span data-ttu-id="7a113-141">既定では有効です。</span><span class="sxs-lookup"><span data-stu-id="7a113-141">Enabled by default.</span></span>
    
      - <span data-ttu-id="7a113-142">**Pstn の再ルーティング**では、WAN が混雑しているか利用できない場合は、このポリシーが割り当てられているユーザーによる電話による公衆交換電話網 (PSTN) の再ルーティングが可能になります。</span><span class="sxs-lookup"><span data-stu-id="7a113-142">**PSTN re-route** enables calls made by users who are assigned this policy to other enterprise users to be rerouted on the public switched telephone network (PSTN) if the WAN is congested or unavailable.</span></span> <span data-ttu-id="7a113-143">既定では有効です。</span><span class="sxs-lookup"><span data-stu-id="7a113-143">Enabled by default.</span></span>
    
      - <span data-ttu-id="7a113-p113">[**帯域幅ポリシーの上書き**] により管理者は、特定のユーザーに関する通話受付管理ポリシーによる決定を上書きできます。既定では無効です。</span><span class="sxs-lookup"><span data-stu-id="7a113-p113">**Bandwidth policy override** enables administrators to override call admission control policy decisions for a particular user. Disabled by default.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="7a113-p114">ポリシーが上書きされるのはユーザーに着信する通話のみです。ユーザーが発信する通話は上書きされません。セッションの確立後、使用帯域幅は正確に記録されます。この設定は慎重に使用し、適切な通話受付管理の決定に対しては使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="7a113-p114">The policy will be overridden only for incoming calls to the user and not for outgoing calls that are placed by the user. After the session is established, the bandwidth consumption will be accurately recorded. This setting should be used sparingly and should be reserved for appropriate call admission control decisions.</span></span>

        
        </div>
    
      - <span data-ttu-id="7a113-149">**悪意のある通話トレース**を使用すると、ユーザーはクライアント UI を使って悪意のある通話 (爆弾の脅威など) を報告することができます。これは、通話の詳細レコード (CDRs) の呼び出しにフラグを付けます。</span><span class="sxs-lookup"><span data-stu-id="7a113-149">**Malicious call tracing** enables users to report malicious calls (such as bomb threats) by using the client UI, which in turn flags the calls in the call detail records (CDRs).</span></span> <span data-ttu-id="7a113-150">既定では無効です。</span><span class="sxs-lookup"><span data-stu-id="7a113-150">Disabled by default.</span></span>

8.  <span data-ttu-id="7a113-151">この音声ポリシーの PSTN 使用法レコードの関連付けと構成を行うには、次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="7a113-151">To associate and configure PSTN usage records for this voice policy, do any of the following:</span></span>
    
      - <span data-ttu-id="7a113-p116">エンタープライズ VoIP 展開で利用できるすべての PSTN 使用法レコードの一覧から、1 つ以上のレコードを選択するには、[**選択**] をクリックします。この音声ポリシーに関連付けるレコードを選択状態にし、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7a113-p116">To choose one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**. Highlight the records that you want to associate with this voice policy, and then click **OK**.</span></span>
    
      - <span data-ttu-id="7a113-154">PSTN 使用法レコードをこの音声ポリシーから削除するには、レコードを選択状態にして [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7a113-154">To remove a PSTN usage record from this voice policy, highlight the record and click **Remove**.</span></span>
    
      - <span data-ttu-id="7a113-155">新しい PSTN 使用法レコードを定義してこの音声ポリシーに関連付けるには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="7a113-155">To define a new PSTN usage record and associate it with this voice policy, do the following:</span></span>
        
        1.  <span data-ttu-id="7a113-156">[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7a113-156">Click **New**.</span></span>
        
        2.  <span data-ttu-id="7a113-p117">"**名前**" フィールドに、レコードを説明する一意の名前を入力します。たとえば、Redmond で勤務しているフルタイム従業員用に **Redmond** という名前の PSTN 使用法レコードを作成し、パートタイム従業員用に **RedmondTemps** という別の名前の PSTN 使用法レコードを作成できます。</span><span class="sxs-lookup"><span data-stu-id="7a113-p117">In the **Name** field, enter a unique descriptive name for the record. For example, you may want to create a PSTN usage record named **Redmond** for full-time employees located in Redmond, and another named **RedmondTemps** for temporary employees.</span></span>
            
            <div>
            

            > [!NOTE]  
            > <span data-ttu-id="7a113-p118">PSTN 使用法レコードの名前は、エンタープライズ VoIP 展開内で一意である必要があります。レコードの保存後、"<STRONG>名前</STRONG>" フィールドを編集することはできません。</span><span class="sxs-lookup"><span data-stu-id="7a113-p118">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

            
            </div>
        
        3.  <span data-ttu-id="7a113-161">次のいずれかの方法を使用して、この PSTN 使用法レコードのルートの関連付けと構成を行います。</span><span class="sxs-lookup"><span data-stu-id="7a113-161">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="7a113-162">エンタープライズ VoIP 展開で利用できるすべてのルートの一覧から、1 つ以上のルートを選択するには、[**選択**] をクリックし、この PSTN 使用法レコードに関連付けるルートを選択状態にして、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7a113-162">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>
            
              - <span data-ttu-id="7a113-163">PSTN 使用法レコードからルートを削除するには、ルートを選択状態にして [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7a113-163">To remove a route from the PSTN usage record, highlight the route, and then click **Remove**.</span></span>
            
              - <span data-ttu-id="7a113-164">新しいルートを定義してこの PSTN 使用法レコードに関連付けるには、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7a113-164">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="7a113-165">詳細については、「 [Lync Server 2013 での音声ルートの作成](lync-server-2013-create-a-voice-route.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a113-165">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="7a113-166">この PSTN 使用法レコードに既に関連付けられているルートを編集するには、ルートを選択状態にして [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7a113-166">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="7a113-167">詳細については、「 [Lync Server 2013 での音声ルートの変更](lync-server-2013-modify-a-voice-route.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a113-167">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        4.  <span data-ttu-id="7a113-168">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7a113-168">Click **OK**.</span></span>
    
      - <span data-ttu-id="7a113-169">この音声ポリシーに既に関連付けられている PSTN 使用法レコードを編集するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="7a113-169">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>
        
        1.  <span data-ttu-id="7a113-170">編集する PSTN 使用法レコードを選択状態にし、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7a113-170">Highlight the PSTN usage record that you want to edit, and then click **Show details**.</span></span>
        
        2.  <span data-ttu-id="7a113-171">次のいずれかの方法を使用して、この PSTN 使用法レコードのルートの関連付けと構成を行います。</span><span class="sxs-lookup"><span data-stu-id="7a113-171">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="7a113-172">エンタープライズ VoIP 展開で利用できるすべてのルートの一覧から、1 つ以上のルートを選択するには、[**選択**] をクリックし、この PSTN 使用法レコードに関連付けるルートを選択状態にして、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7a113-172">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes you want to associate with this PSTN usage record, and then click **OK**.</span></span>
            
              - <span data-ttu-id="7a113-173">この PSTN 使用法レコードからルートを削除するには、ルートを選択状態にして [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7a113-173">To remove a route from this PSTN usage record, highlight the route, and then click **Remove**.</span></span>
            
              - <span data-ttu-id="7a113-174">新しいルートを定義してこの PSTN 使用法レコードに関連付けるには、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7a113-174">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="7a113-175">詳細については、「 [Lync Server 2013 での音声ルートの作成](lync-server-2013-create-a-voice-route.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a113-175">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="7a113-176">この PSTN 使用法レコードに既に関連付けられているルートを編集するには、ルートを選択状態にして [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7a113-176">To edit a route that is already associated with this PSTN usage record, highlight the route and lick **Show details**.</span></span> <span data-ttu-id="7a113-177">詳細については、「 [Lync Server 2013 での音声ルートの変更](lync-server-2013-modify-a-voice-route.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a113-177">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        3.  <span data-ttu-id="7a113-178">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7a113-178">Click **OK**.</span></span>

9.  <span data-ttu-id="7a113-p123">最適なパフォーマンスを得るために、PSTN 使用法レコードを並べ替えます。一覧内でのレコードの位置を変更するには、レコードの名前を選択状態にして、上矢印または下矢印をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7a113-p123">Arrange the PSTN usage records for optimum performance. To change a record’s position in the list, highlight the record name and click the up or down arrow.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="7a113-181">ボイスポリシーに表示される PSTN 使用状況レコードの順序は重要です。</span><span class="sxs-lookup"><span data-stu-id="7a113-181">The order in which PSTN usage records are listed in the voice policy is significant.</span></span> <span data-ttu-id="7a113-182">Lync Server は、一覧を上から下に移動します。</span><span class="sxs-lookup"><span data-stu-id="7a113-182">Lync Server traverses the list from the top down.</span></span> <span data-ttu-id="7a113-183">リストを使用頻度で整理することをお勧めします。例: RedmondLocal、RedmondLongDist、Redmondlocal、Redmondlocal。</span><span class="sxs-lookup"><span data-stu-id="7a113-183">We recommend that you organize the list by frequency of use, for example: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span></span>

    
    </div>

10. <span data-ttu-id="7a113-184">この音声ポリシーの着信転送および同時呼び出しの PSTN 使用法レコードの関連付けと構成を行うには、次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="7a113-184">To associate and configure PSTN usage records for call forwarding and simultaneous ringing in this voice policy, do any of the following:</span></span>
    
      - <span data-ttu-id="7a113-185">この音声ポリシーのように着信の転送および同時呼び出しに対して同じ PSTN 使用法レコードを使用するには、ドロップダウン メニューから [**呼び出し PSTN 使用法を使用したルーティング**] オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="7a113-185">To use the same PSTN usage records for call forwarding and simultaneous ringing as this voice policy, select the option **Route using the call PSTN usages** from the drop-down menu.</span></span>
    
      - <span data-ttu-id="7a113-186">着信の転送と同時呼び出しを内部の Lync ユーザーのみに許可するには、ドロップダウンメニューから [**内部の lync ユーザーにのみルーティング**する] オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="7a113-186">To allow call forwarding and simultaneous ringing to internal Lync users only, select the option **Route to internal Lync users only** from the drop-down menu.</span></span> <span data-ttu-id="7a113-187">Calls will not be forwarded to external PSTN numbers.</span><span class="sxs-lookup"><span data-stu-id="7a113-187">Calls will not be forwarded to external PSTN numbers.</span></span>
    
      - <span data-ttu-id="7a113-p126">着信の転送および同時呼び出しに対して、この音声ポリシーでの使用とは異なる PSTN 使用法レコードを指定するには、ドロップダウン メニューから [**カスタムの PSTN 使用法を使用したルーティング**] オプションを選択します。このオプションでは、既存の PSTN 使用法レコードを選択するか、または着信の転送および同時呼び出し用の特別な新しい PSTN 使用法レコードを作成するコントロールが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7a113-p126">To specify different PSTN usage records for call forwarding and simultaneous ringing than used for this voice policy, select the option **Route using custom PSTN usages** from the drop-down menu. This option displays a control to select existing PSTN usage records or create new PSTN usage records specifically for call forwarding and simultaneous ringing.</span></span>
        
          - <span data-ttu-id="7a113-p127">着信の転送および同時呼び出しの PSTN 使用法レコードの一覧から、1 つ以上のレコードを選択するには、[**選択**] をクリックします。この着信の転送および同時呼び出しポリシーに関連付けるレコードを選択状態にし、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7a113-p127">To choose one or more records from a list of PSTN usage records for call forwarding and simultaneous ringing, click **Select**. Highlight the records that you want to associate with this call forwarding and simultaneous ringing policy, and then click **OK**.</span></span>
        
          - <span data-ttu-id="7a113-192">PSTN 使用法レコードをこの着信の転送および同時呼び出しポリシーから削除するには、レコードを選択状態にして [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7a113-192">To remove a PSTN usage record from this call forwarding and simultaneous ringing policy, highlight the record and click **Remove**.</span></span>
        
          - <span data-ttu-id="7a113-193">新しい PSTN 使用法レコードを定義してこの着信の転送および同時呼び出しポリシーに関連付けるには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="7a113-193">To define a new PSTN usage record and associate it with this call forwarding and simultaneous ringing policy, do the following:</span></span>
            
            1.  <span data-ttu-id="7a113-194">[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7a113-194">Click **New**.</span></span>
            
            2.  <span data-ttu-id="7a113-195">"**名前**" フィールドに、レコードを説明する一意の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="7a113-195">In the **Name** field, enter a unique descriptive name for the record.</span></span>
                
                <div>
                

                > [!NOTE]  
                > <span data-ttu-id="7a113-p128">PSTN 使用法レコードの名前は、エンタープライズ VoIP 展開内で一意である必要があります。レコードの保存後、"<STRONG>名前</STRONG>" フィールドを編集することはできません。</span><span class="sxs-lookup"><span data-stu-id="7a113-p128">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

                
                </div>
            
            3.  <span data-ttu-id="7a113-198">次のいずれかの方法を使用して、この PSTN 使用法レコードのルートの関連付けと構成を行います。</span><span class="sxs-lookup"><span data-stu-id="7a113-198">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
                
                  - <span data-ttu-id="7a113-199">エンタープライズ VoIP 展開で利用できるすべてのルートの一覧から、1 つ以上のルートを選択するには、[**選択**] をクリックし、この PSTN 使用法レコードに関連付けるルートを選択状態にして、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7a113-199">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>
                
                  - <span data-ttu-id="7a113-200">PSTN 使用法レコードからルートを削除するには、ルートを選択状態にして [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7a113-200">To remove a route from the PSTN usage record, highlight the route and click **Remove**.</span></span>
                
                  - <span data-ttu-id="7a113-201">新しいルートを定義してこの PSTN 使用法レコードに関連付けるには、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7a113-201">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="7a113-202">詳細については、「 [Lync Server 2013 での音声ルートの作成](lync-server-2013-create-a-voice-route.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a113-202">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
                
                  - <span data-ttu-id="7a113-203">この PSTN 使用法レコードに既に関連付けられているルートを編集するには、ルートを選択状態にして [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7a113-203">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="7a113-204">詳細については、「 [Lync Server 2013 での音声ルートの変更](lync-server-2013-modify-a-voice-route.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a113-204">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
            
            4.  <span data-ttu-id="7a113-205">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7a113-205">Click **OK**.</span></span>
        
          - <span data-ttu-id="7a113-206">この音声ポリシーに既に関連付けられている PSTN 使用法レコードを編集するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="7a113-206">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>
            
            1.  <span data-ttu-id="7a113-207">編集する PSTN 使用法レコードを選択状態にし、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7a113-207">Highlight the PSTN usage record you want to edit and click **Show details**.</span></span>
            
            2.  <span data-ttu-id="7a113-208">次のいずれかの方法を使用して、この PSTN 使用法レコードのルートの関連付けと構成を行います。</span><span class="sxs-lookup"><span data-stu-id="7a113-208">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
                
                  - <span data-ttu-id="7a113-209">エンタープライズ VoIP 展開で利用できるすべてのルートの一覧から、1 つ以上のルートを選択するには、[**選択**] をクリックし、この PSTN 使用法レコードに関連付けるルートを選択状態にして、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7a113-209">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>
                
                  - <span data-ttu-id="7a113-210">この PSTN 使用法レコードからルートを削除するには、ルートを選択状態にして [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7a113-210">To remove a route from this PSTN usage record, highlight the route and click **Remove**.</span></span>
                
                  - <span data-ttu-id="7a113-211">新しいルートを定義してこの PSTN 使用法レコードに関連付けるには、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7a113-211">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="7a113-212">詳細については、「 [Lync Server 2013 での音声ルートの作成](lync-server-2013-create-a-voice-route.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a113-212">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
                
                  - <span data-ttu-id="7a113-213">この PSTN 使用法レコードに既に関連付けられているルートを編集するには、ルートを選択状態にして [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7a113-213">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="7a113-214">詳細については、「 [Lync Server 2013 での音声ルートの変更](lync-server-2013-modify-a-voice-route.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a113-214">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
            
            3.  <span data-ttu-id="7a113-215">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7a113-215">Click **OK**.</span></span>

11. <span data-ttu-id="7a113-p133">(オプション) 音声ポリシーをテストする番号を入力して、[**実行**] をクリックします。テスト結果は、[**テストする変換後の番号**] の下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="7a113-p133">(Optional) Enter a number to test the voice policy and click **Go**. The test results are displayed under **Translated number to test**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7a113-218">まだテストに合格しない音声ポリシーを保存し、後で再構成することができます。</span><span class="sxs-lookup"><span data-stu-id="7a113-218">You can save a voice policy that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="7a113-219">詳細については、「 <A href="lync-server-2013-test-voice-routing.md">Lync Server 2013 での音声ルーティングのテスト</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a113-219">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

12. <span data-ttu-id="7a113-220">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7a113-220">Click **OK**.</span></span>

13. <span data-ttu-id="7a113-221">[**音声ポリシー**] ページで [**確定**] をクリックし、[**すべて確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7a113-221">On the **Voice Policy** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7a113-222">音声ポリシーを作成または変更したときは常に、[<STRONG>すべて確定</STRONG>] コマンドを実行して、構成の変更を公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7a113-222">Any time you create or modify a voice policy, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="7a113-223">詳細については、「操作のドキュメントで「 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 のボイスルーティング構成に保留中の変更を発行する</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a113-223">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

14. <span data-ttu-id="7a113-224">(オプション) ボイスメール エスケープは、着信がユーザーの携帯電話のボイス メールによって即座に応答されたことを検出し、携帯電話のボイス メールへの通話を切断します。</span><span class="sxs-lookup"><span data-stu-id="7a113-224">(Optional) Voicemail Escape detects that a call was immediately answered by the user’s mobile phone voice mail, and disconnects the call to the mobile phone voice mail.</span></span> <span data-ttu-id="7a113-225">これにより、ユーザーの他のエンドポイントで着信の呼び出しが続けられるので、ユーザーは着信に応答できるようになります。</span><span class="sxs-lookup"><span data-stu-id="7a113-225">This allows the call to continue to ring on the user’s other endpoints giving the user the opportunity to answer the call.</span></span> <span data-ttu-id="7a113-226">ボイスメールのポリシーを構成する方法の詳細については、「 [Lync Server 2013 でボイスメールのエスケープを構成](lync-server-2013-configuring-voice-mail-escape.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a113-226">For details on how to configure a voice mail policy, see [Configuring voice mail escape in Lync Server 2013](lync-server-2013-configuring-voice-mail-escape.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7a113-227">関連項目</span><span class="sxs-lookup"><span data-stu-id="7a113-227">See Also</span></span>


[<span data-ttu-id="7a113-228">Lync Server 2013 で音声ポリシーを変更し、PSTN 使用状況レコードを構成する</span><span class="sxs-lookup"><span data-stu-id="7a113-228">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="7a113-229">Lync Server 2013 での PSTN 使用状況レコードの表示</span><span class="sxs-lookup"><span data-stu-id="7a113-229">View PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-view-pstn-usage-records.md)  
[<span data-ttu-id="7a113-230">Lync Server 2013 での音声ルートの作成</span><span class="sxs-lookup"><span data-stu-id="7a113-230">Create a voice route in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-route.md)  
[<span data-ttu-id="7a113-231">Lync Server 2013 での音声ルートの変更</span><span class="sxs-lookup"><span data-stu-id="7a113-231">Modify a voice route in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-route.md)  
[<span data-ttu-id="7a113-232">Lync Server 2013 の音声ルーティング構成に保留中の変更を発行する</span><span class="sxs-lookup"><span data-stu-id="7a113-232">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  
[<span data-ttu-id="7a113-233">Lync Server 2013 でボイスメールのエスケープを構成する</span><span class="sxs-lookup"><span data-stu-id="7a113-233">Configuring voice mail escape in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-mail-escape.md)  


[<span data-ttu-id="7a113-234">Lync Server 2013 での音声ルーティングのテスト</span><span class="sxs-lookup"><span data-stu-id="7a113-234">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

