---
title: 'Lync Server 2013: 音声ポリシーの変更と PSTN 使用法レコードの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify a voice policy and configure PSTN usage records
ms:assetid: 6c53aaf5-218b-4bd4-8cea-31bc9d53f1bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398511(v=OCS.15)
ms:contentKeyID: 48184419
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2e198158c60b7605ee78179e4a4e74c86791dfa1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42217400"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="modify-a-voice-policy-and-configure-pstn-usage-records-in-lync-server-2013"></a><span data-ttu-id="c1741-102">Lync Server 2013 での音声ポリシーの変更と PSTN 使用法レコードの構成</span><span class="sxs-lookup"><span data-stu-id="c1741-102">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c1741-103">_**トピックの最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="c1741-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="c1741-104">音声ポリシーを変更する場合は、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="c1741-104">Follow these steps if you want to modify a voice policy.</span></span> <span data-ttu-id="c1741-105">新しい音声ポリシーを作成する場合は、手順について「 [create a voice policy and CONFIGURE PSTN usage records In Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c1741-105">If you want to create a new voice policy, see [Create a voice policy and configure PSTN usage records in Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md) for the procedure.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c1741-106">公衆交換電話網 (PSTN) 使用法レコードが関連付けられていない音声ポリシーに割り当てられているユーザーは、通話を発信できません。</span><span class="sxs-lookup"><span data-stu-id="c1741-106">If a user is assigned to a voice policy has no associated public switched telephone network (PSTN) usage records, the user cannot place outbound calls.</span></span> <span data-ttu-id="c1741-107">エンタープライズ Voip 展開で使用可能なすべての PSTN 使用法レコードの一覧を示し、そのプロパティを表示するには、「 <A href="lync-server-2013-view-pstn-usage-records.md">Lync Server 2013 で pstn 使用法レコードを表示</A>する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c1741-107">For a listing of all PSTN usage records available in your Enterprise Voice deployment and view their properties, see <A href="lync-server-2013-view-pstn-usage-records.md">View PSTN usage records in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-modify-a-voice-policy"></a><span data-ttu-id="c1741-108">音声ポリシーを変更するには</span><span class="sxs-lookup"><span data-stu-id="c1741-108">To modify a voice policy</span></span>

1.  <span data-ttu-id="c1741-109">RTCUniversalServerAdmins グループのメンバーとして、または CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="c1741-109">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="c1741-110">詳細については、「 [Lync Server 2013 でのセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c1741-110">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="c1741-111">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="c1741-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c1741-112">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c1741-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c1741-113">左側のナビゲーション バーで [**音声ルーティング**] をクリックし、[**音声ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c1741-113">In the left navigation bar, click **Voice Routing**, and then click **Voice Policy**.</span></span>

4.  <span data-ttu-id="c1741-114">[**音声ポリシー**] ページで、音声ポリシー名をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="c1741-114">On the **Voice Policy** page, double-click a voice policy name.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c1741-p105">スコープと名前は、音声ポリシーの作成時に設定されています。 これらは変更できません。</span><span class="sxs-lookup"><span data-stu-id="c1741-p105">The scope and name were set when the voice policy was created. They cannot be changed.</span></span>

    
    </div>

5.  <span data-ttu-id="c1741-117">(オプション) [**音声ポリシーの編集**] に、音声ポリシーの説明情報を追加で入力します。</span><span class="sxs-lookup"><span data-stu-id="c1741-117">(Optional) In **Edit Voice Policy**, enter additional descriptive information for the voice policy.</span></span>

6.  <span data-ttu-id="c1741-118">次のチェック ボックスをオンまたはオフにして、[**通話機能**] をそれぞれ有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="c1741-118">Select or clear the following check boxes to enable or disable each of the **Calling features**:</span></span>
    
      - <span data-ttu-id="c1741-119">[**ボイス メールのエスケープ**] は、同時呼び出しが構成されていて、携帯電話がオフになっている、バッテリーが切れている、または圏外になっている場合に、通話が即座にユーザーの携帯電話のボイス メール システムに転送されないようにします。</span><span class="sxs-lookup"><span data-stu-id="c1741-119">**Voice mail escape** prevents calls from being immediately routed to the user’s mobile phone voice mail system when simultaneous ringing is configured and the phone is turned off, out of battery, or out of range.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="c1741-120">この機能は、Lync Server 管理シェルを使用してのみ構成できます。</span><span class="sxs-lookup"><span data-stu-id="c1741-120">This feature is only configurable through the Lync Server Management Shell</span></span>

        
        </div>
    
      - <span data-ttu-id="c1741-121">[**着信の転送**] では、他の電話機やクライアント デバイスに通話を転送できます。</span><span class="sxs-lookup"><span data-stu-id="c1741-121">**Call forwarding** enables users to forward calls to other phones and client devices.</span></span> <span data-ttu-id="c1741-122">Lync Server 2013 は、着信転送用の構成オプションを非常に広範囲に提供しています。</span><span class="sxs-lookup"><span data-stu-id="c1741-122">Lync Server 2013 provides a significantly wider range of configuration options for call forwarding.</span></span> <span data-ttu-id="c1741-123">たとえば、着信が外部で PSTN に転送されることを組織が許可しない方針の場合、管理者は特殊な音声ポリシーを適用して、この制限を展開することができます。</span><span class="sxs-lookup"><span data-stu-id="c1741-123">For example, if an organization does not want to allow incoming calls to be forwarded externally to the PSTN, an administrator can apply a special voice policy to deploy this restriction.</span></span> <span data-ttu-id="c1741-124">既定では有効です。</span><span class="sxs-lookup"><span data-stu-id="c1741-124">Enabled by default.</span></span>
    
      - <span data-ttu-id="c1741-125">[**委任**] では、代わりに通話を送受信する他のユーザーを指定できます。</span><span class="sxs-lookup"><span data-stu-id="c1741-125">**Delegation** enables users to specify other users to send and receive calls on their behalf.</span></span> <span data-ttu-id="c1741-126">Lync Server 2013 では、代理人が同時呼び出しを構成して、自分の上司への着信呼び出しによって、すべての代理人の同時呼び出し対象を着信させることができます。</span><span class="sxs-lookup"><span data-stu-id="c1741-126">In Lync Server 2013, a delegate can configure simultaneous ringing that enables incoming calls to his or her manager to ring all of the delegate’s simultaneous ringing targets.</span></span> <span data-ttu-id="c1741-127">これにより、管理者に向けられた通話に応答して、代理人の柔軟性が向上します。</span><span class="sxs-lookup"><span data-stu-id="c1741-127">This provides the delegate with greater flexibility in responding to calls directed to the manager.</span></span> <span data-ttu-id="c1741-128">既定では有効です。</span><span class="sxs-lookup"><span data-stu-id="c1741-128">Enabled by default.</span></span>
    
      - <span data-ttu-id="c1741-p108">**[通話の転送]** では、他のユーザーに通話を転送できます。 既定では有効です。</span><span class="sxs-lookup"><span data-stu-id="c1741-p108">**Call transfer** enables users to transfer calls to other users. Enabled by default.</span></span>
    
      - <span data-ttu-id="c1741-p109">[**コール パーク**] では、通話を保留 (パーク) し、別の電話機やクライアントで受けることができます。既定では無効です。</span><span class="sxs-lookup"><span data-stu-id="c1741-p109">**Call park** enables users to park calls on hold, and then pick up the call from a different phone or client. Disabled by default.</span></span>
    
      - <span data-ttu-id="c1741-133">[**同時呼び出し**] では、追加の電話機 (携帯電話など) や他のエンドポイント デバイスで、着信の呼び出し音を鳴らすことができます。</span><span class="sxs-lookup"><span data-stu-id="c1741-133">**Simultaneous ringing** enables incoming calls to ring on additional phones (for example, a mobile phone) or other endpoint devices.</span></span> <span data-ttu-id="c1741-134">Lync Server 2013 では、同時呼び出しの構成オプションが非常に広範囲に提供されています。</span><span class="sxs-lookup"><span data-stu-id="c1741-134">Lync Server 2013 provides a significantly wider range of configuration options for simultaneous ringing.</span></span> <span data-ttu-id="c1741-135">既定では有効です。</span><span class="sxs-lookup"><span data-stu-id="c1741-135">Enabled by default.</span></span>
    
      - <span data-ttu-id="c1741-p111">**[チーム呼び出し]** では、定義したチームのユーザーがチームの他のメンバーの呼び出しに応答できます。 既定では有効です。</span><span class="sxs-lookup"><span data-stu-id="c1741-p111">**Team call** enables users on a defined team to answer calls for other members of the team. Enabled by default.</span></span>
    
      - <span data-ttu-id="c1741-p112">[**PSTN 再ルート**] では、WAN が混雑していたり利用できない場合に、このポリシーを割り当てられているユーザーが他のエンタープライズ ユーザーに掛けた通話を、公衆交換電話網 (PSTN) で再ルートできます。既定では有効です。</span><span class="sxs-lookup"><span data-stu-id="c1741-p112">**PSTN re-route** enables calls made by users who are assigned this policy to other enterprise users to be rerouted on the public switched telephone network (PSTN) if the WAN is congested or unavailable. Enabled by default.</span></span>
    
      - <span data-ttu-id="c1741-p113">**[帯域幅ポリシーの上書き]** では、特定のユーザーに対する通話受付管理 (CAC) ポリシーの決定を、管理者が上書きできます。 既定では無効です。</span><span class="sxs-lookup"><span data-stu-id="c1741-p113">**Bandwidth policy override** enables administrators to override call admission control (CAC) policy decisions for a particular user. Disabled by default.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="c1741-p114">ポリシーが上書きされるのはユーザーに着信する通話のみです。ユーザーが発信する通話は上書きされません。セッションの確立後、使用帯域幅は正確に記録されます。この設定は慎重に使用してください。</span><span class="sxs-lookup"><span data-stu-id="c1741-p114">The policy will be overridden only for incoming calls to the user and not for outgoing calls that are placed by the user. After the session is established, the bandwidth consumption will be accurately recorded. This setting should be used sparingly.</span></span>

        
        </div>
    
      - <span data-ttu-id="c1741-p115">[**悪意のある通話のトレース**] では、ユーザーがクライアントの UI を使用して、悪意のある通話 (爆弾脅迫など) を報告できます。報告されると、通話詳細記録 (CDR) 内のその通話にフラグが付けられます。既定では無効です。</span><span class="sxs-lookup"><span data-stu-id="c1741-p115">**Malicious call tracing** enables users to report malicious calls (such as bomb threats) using the client UI, which in turn flags the calls in the call detail records (CDRs). Disabled by default.</span></span>

7.  <span data-ttu-id="c1741-147">この音声ポリシーの PSTN 使用法レコードの関連付けと構成を行うには、次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="c1741-147">To associate and configure PSTN usage records for this voice policy, do any of the following:</span></span>
    
      - <span data-ttu-id="c1741-p116">エンタープライズ VoIP 展開で利用できるすべての PSTN 使用法レコードの一覧から 1 つ以上のレコードを選択するには、[**選択**] をクリックします。この音声ポリシーに関連付けるレコードを選択状態にし、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c1741-p116">To choose one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**. Highlight the records that you want to associate with this voice policy, and then click **OK**.</span></span>
    
      - <span data-ttu-id="c1741-150">PSTN 使用法レコードをこの音声ポリシーから削除するには、レコードを選択状態にして [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c1741-150">To remove a PSTN usage record from this voice policy, highlight the record and click **Remove**.</span></span>
    
      - <span data-ttu-id="c1741-151">新しい PSTN 使用法レコードを定義してこの音声ポリシーに関連付けるには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="c1741-151">To define a new PSTN usage record and associate it with this voice policy, do the following:</span></span>
        
        1.  <span data-ttu-id="c1741-152">[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c1741-152">Click **New**.</span></span>
        
        2.  <span data-ttu-id="c1741-p117">[**名前**] フィールドに、レコードを説明する一意の名前を入力します。たとえば、Redmond で勤務しているフルタイム従業員用に **Redmond** という名前の PSTN 使用法レコードを作成し、パートタイム従業員用に **RedmondTemps** という名前の別のレコードを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="c1741-p117">In the **Name** field, enter a unique descriptive name for the record. For example, you may want to create a PSTN usage record named **Redmond** for full-time employees located in Redmond, and another record named **RedmondTemps** for temporary employees.</span></span>
            
            <div>
            

            > [!NOTE]  
            > <span data-ttu-id="c1741-p118">PSTN 使用法レコードの名前は、エンタープライズ VoIP 展開内で一意である必要があります。 レコードの保存後、[<STRONG>名前</STRONG>] フィールドを編集することはできません。</span><span class="sxs-lookup"><span data-stu-id="c1741-p118">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

            
            </div>
        
        3.  <span data-ttu-id="c1741-157">次のいずれかの方法を使用して、この PSTN 使用法レコードのルートの関連付けと構成を行います。</span><span class="sxs-lookup"><span data-stu-id="c1741-157">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="c1741-158">エンタープライズ VoIP 展開で利用できるすべてのルートの一覧から 1 つ以上のルートを選択するには、[**選択**] をクリックし、この PSTN 使用法レコードに関連付けるルートを選択状態にして、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c1741-158">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>
            
              - <span data-ttu-id="c1741-159">PSTN 使用法レコードからルートを削除するには、ルートを選択状態にして [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c1741-159">To remove a route from the PSTN usage record, highlight the route and click **Remove**.</span></span>
            
              - <span data-ttu-id="c1741-160">新しいルートを定義してこの PSTN 使用法レコードに関連付けるには、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c1741-160">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="c1741-161">詳細については、「 [Lync Server 2013 で音声ルートを作成する](lync-server-2013-create-a-voice-route.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c1741-161">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="c1741-162">この PSTN 使用法レコードに既に関連付けられているルートを編集するには、ルートを選択状態にして [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c1741-162">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="c1741-163">詳細については、「 [Modify a voice route In Lync Server 2013](lync-server-2013-modify-a-voice-route.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c1741-163">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        4.  <span data-ttu-id="c1741-164">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c1741-164">Click **OK**.</span></span>
    
      - <span data-ttu-id="c1741-165">この音声ポリシーに既に関連付けられている PSTN 使用法レコードを編集するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="c1741-165">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>
        
        1.  <span data-ttu-id="c1741-166">編集する PSTN 使用法レコードを選択状態にし、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c1741-166">Highlight the PSTN usage record that you want to edit and click **Show details**.</span></span>
        
        2.  <span data-ttu-id="c1741-167">次のいずれかの方法を使用して、この PSTN 使用法レコードのルートの関連付けと構成を行います。</span><span class="sxs-lookup"><span data-stu-id="c1741-167">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="c1741-168">エンタープライズ VoIP 展開で利用できるすべてのルートの一覧から 1 つ以上のルートを選択するには、[**選択**] をクリックし、この PSTN 使用法レコードに関連付けるルートを選択状態にして、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c1741-168">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>
            
              - <span data-ttu-id="c1741-169">この PSTN 使用法レコードからルートを削除するには、ルートを選択状態にして [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c1741-169">To remove a route from this PSTN usage record, highlight the route and click **Remove**.</span></span>
            
              - <span data-ttu-id="c1741-170">新しいルートを定義してこの PSTN 使用法レコードに関連付けるには、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c1741-170">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="c1741-171">詳細については、「 [Lync Server 2013 で音声ルートを作成する](lync-server-2013-create-a-voice-route.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c1741-171">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="c1741-172">この PSTN 使用法レコードに既に関連付けられているルートを編集するには、ルートを選択状態にして [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c1741-172">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="c1741-173">詳細については、「 [Modify a voice route In Lync Server 2013](lync-server-2013-modify-a-voice-route.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c1741-173">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        3.  <span data-ttu-id="c1741-174">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c1741-174">Click **OK**.</span></span>

8.  <span data-ttu-id="c1741-p123">最適なパフォーマンスを得るために、PSTN 使用法レコードを並べ替えます。 一覧内でのレコードの位置を変更するには、レコードの名前を選択状態にして、上矢印または下矢印をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c1741-p123">Arrange the PSTN usage records for optimum performance. To change a record’s position in the list, highlight the record name and click the up or down arrow.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c1741-177">音声ポリシーで PSTN 使用法レコードが表示される順序は重要です。</span><span class="sxs-lookup"><span data-stu-id="c1741-177">The order in which PSTN usage records are listed in the voice policy is significant.</span></span> <span data-ttu-id="c1741-178">Lync Server は、リストを上から下に移動します。</span><span class="sxs-lookup"><span data-stu-id="c1741-178">Lync Server traverses the list from the top down.</span></span> <span data-ttu-id="c1741-179">リストを使用頻度で整理することをお勧めします。例: RedmondLocal、RedmondLongDist、Redmondlocal、Redmondlocal。</span><span class="sxs-lookup"><span data-stu-id="c1741-179">We recommend that you organize the list by frequency of use, for example: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span></span>

    
    </div>

9.  <span data-ttu-id="c1741-180">この音声ポリシーの着信の転送および同時呼び出しに対する PSTN 使用法レコードの関連付けと構成を行うには、次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="c1741-180">To associate and configure PSTN usage records for call forwarding and simultaneous ringing in this voice policy, do any of the following:</span></span>
    
      - <span data-ttu-id="c1741-181">この音声ポリシーと同じ PSTN 使用法レコードを着信の転送と同時呼び出しに使用する場合は、ドロップダウン メニューから [**呼び出し PSTN 使用法を使用したルーティング**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c1741-181">To use the same PSTN usage records for call forwarding and simultaneous ringing as this voice policy, select the option **Route using the call PSTN usages** from the drop-down menu.</span></span>
    
      - <span data-ttu-id="c1741-182">内部 Lync ユーザーのみに着信の転送および同時呼び出しを許可するには、ドロップダウンメニューから [**内部 lync ユーザーにのみルーティング**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c1741-182">To allow call forwarding and simultaneous ringing to internal Lync users only, select **Route to internal Lync users only** from the drop-down menu.</span></span> <span data-ttu-id="c1741-183">通話は外部の PSTN 番号には転送されません。</span><span class="sxs-lookup"><span data-stu-id="c1741-183">Calls will not be forwarded to external PSTN numbers.</span></span>
    
      - <span data-ttu-id="c1741-p126">この音声ポリシーに使用されているのとは別の PTSN 使用法レコードを着信の転送と同時呼び出しに指定する場合は、ドロップダウン メニューから [**カスタムの PSTN 使用法を使用したルーティング**] を選択します。このオプションを選択するとコントロールが表示され、着信の転送と同時呼び出しに対して、既存の PSTN 使用法レコードを選択するかまたは新しい PSTN 使用法レコードを作成できます。</span><span class="sxs-lookup"><span data-stu-id="c1741-p126">To specify different PSTN usage records for call forwarding and simultaneous ringing than those used for this voice policy, select the option **Route using custom PSTN usages** from the drop-down menu. This option displays a control to select existing PSTN usage records or to create new PSTN usage records, specifically for call forwarding and simultaneous ringing.</span></span>
        
          - <span data-ttu-id="c1741-p127">着信の転送と同時呼び出しのために PSTN 使用法レコードの一覧から 1 つ以上のレコードを選択するには、[**選択**] をクリックします。この着信の転送と同時呼び出しのポリシーに関連付けるレコードを選択状態にし、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c1741-p127">To choose one or more records from a list of PSTN usage records for call forwarding and simultaneous ringing, click **Select**. Highlight the records that you want to associate with this call forwarding and simultaneous ringing policy, and then click **OK**.</span></span>
        
          - <span data-ttu-id="c1741-188">この着信の転送と同時呼び出しのポリシーから PSTN 使用法レコードを削除するには、レコードを選択状態にして [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c1741-188">To remove a PSTN usage record from this call forwarding and simultaneous ringing policy, highlight the record and click **Remove**.</span></span>
        
          - <span data-ttu-id="c1741-189">新しい PSTN 使用法レコードを定義してこの着信の転送と同時呼び出しのポリシーに関連付けるには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="c1741-189">To define a new PSTN usage record and associate it with this call forwarding and simultaneous ringing policy, do the following:</span></span>
            
            1.  <span data-ttu-id="c1741-190">[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c1741-190">Click **New**.</span></span>
            
            2.  <span data-ttu-id="c1741-191">[**名前**] フィールドに、レコードを説明する一意の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="c1741-191">In the **Name** field, enter a unique descriptive name for the record.</span></span>
                
                <div>
                

                > [!NOTE]  
                > <span data-ttu-id="c1741-p128">PSTN 使用法レコードの名前は、エンタープライズ VoIP 展開内で一意である必要があります。レコードの保存後、[<STRONG>名前</STRONG>] フィールドを編集することはできません。</span><span class="sxs-lookup"><span data-stu-id="c1741-p128">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

                
                </div>
            
            3.  <span data-ttu-id="c1741-194">次のいずれかの方法を使用して、この PSTN 使用法レコードのルートの関連付けと構成を行います。</span><span class="sxs-lookup"><span data-stu-id="c1741-194">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
                
                  - <span data-ttu-id="c1741-195">エンタープライズ VoIP 展開で利用できるすべてのルートの一覧から 1 つ以上のルートを選択するには、[**選択**] をクリックし、この PSTN 使用法レコードに関連付けるルートを選択状態にして、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c1741-195">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>
                
                  - <span data-ttu-id="c1741-196">PSTN 使用法レコードからルートを削除するには、ルートを選択状態にして [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c1741-196">To remove a route from the PSTN usage record, highlight the route and click **Remove**.</span></span>
                
                  - <span data-ttu-id="c1741-197">新しいルートを定義してこの PSTN 使用法レコードに関連付けるには、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c1741-197">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="c1741-198">詳細については、「 [Lync Server 2013 で音声ルートを作成する](lync-server-2013-create-a-voice-route.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c1741-198">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
                
                  - <span data-ttu-id="c1741-199">この PSTN 使用法レコードに既に関連付けられているルートを編集するには、ルートを選択状態にして [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c1741-199">To edit a route that is already associated with this PSTN usage record, highlight the route, and then click **Show details**.</span></span> <span data-ttu-id="c1741-200">詳細については、「 [Modify a voice route In Lync Server 2013](lync-server-2013-modify-a-voice-route.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c1741-200">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
            
            4.  <span data-ttu-id="c1741-201">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c1741-201">Click **OK**.</span></span>
        
          - <span data-ttu-id="c1741-202">この音声ポリシーに既に関連付けられている PSTN 使用法レコードを編集するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="c1741-202">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>
            
            1.  <span data-ttu-id="c1741-203">編集する PSTN 使用法レコードを選択状態にし、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c1741-203">Highlight the PSTN usage record that you want to edit and click **Show details**.</span></span>
            
            2.  <span data-ttu-id="c1741-204">次のいずれかの方法を使用して、この PSTN 使用法レコードのルートの関連付けと構成を行います。</span><span class="sxs-lookup"><span data-stu-id="c1741-204">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
                
                  - <span data-ttu-id="c1741-205">エンタープライズ VoIP 展開で利用できるすべてのルートの一覧から、1 つ以上のルートを選択するには、[**選択**] をクリックし、この PSTN 使用法レコードに関連付けるルートを選択状態にして、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c1741-205">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes you want to associate with this PSTN usage record, and then click **OK**.</span></span>
                
                  - <span data-ttu-id="c1741-206">この PSTN 使用法レコードからルートを削除するには、ルートを選択状態にして [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c1741-206">To remove a route from this PSTN usage record, highlight the route and click **Remove**.</span></span>
                
                  - <span data-ttu-id="c1741-207">新しいルートを定義してこの PSTN 使用法レコードに関連付けるには、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c1741-207">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="c1741-208">詳細については、「 [Lync Server 2013 で音声ルートを作成する](lync-server-2013-create-a-voice-route.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c1741-208">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
                
                  - <span data-ttu-id="c1741-209">この PSTN 使用法レコードに既に関連付けられているルートを編集するには、ルートを選択状態にして [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c1741-209">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="c1741-210">詳細については、「 [Modify a voice route In Lync Server 2013](lync-server-2013-modify-a-voice-route.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c1741-210">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
            
            3.  <span data-ttu-id="c1741-211">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c1741-211">Click **OK**.</span></span>

10. <span data-ttu-id="c1741-p133">(オプション) 音声ポリシーをテストする番号を入力して、[**実行**] をクリックします。テスト結果は、[**テストする変換後の番号**] の下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="c1741-p133">(Optional) Enter a number to test the voice policy and click **Go**. The test results are displayed under **Translated number to test**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c1741-214">まだテストに成功していない音声ポリシーを保存して、後で再構成することができます。</span><span class="sxs-lookup"><span data-stu-id="c1741-214">You can save a voice policy that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="c1741-215">詳細については、「 <A href="lync-server-2013-test-voice-routing.md">Lync Server 2013 での音声ルーティングのテスト</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c1741-215">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

11. <span data-ttu-id="c1741-216">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c1741-216">Click **OK**.</span></span>

12. <span data-ttu-id="c1741-217">[**音声ポリシー**] ページで [**確定**] をクリックし、[**すべて確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c1741-217">On the **Voice Policy** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c1741-218">音声ポリシーを作成または変更したときは常に、[<STRONG>すべて確定</STRONG>] コマンドを実行して、構成の変更を公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c1741-218">Whenever you create or modify a voice policy, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="c1741-219">詳細については、「操作」のドキュメントの「 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 での音声ルーティング構成に対する保留中の変更の公開</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c1741-219">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

13. <span data-ttu-id="c1741-220">(オプション) [ボイス メールのエスケープ] で、ユーザーの携帯電話のボイス メールが通話に即座に応答したことを検出して、携帯電話のボイス メールへの通話を切断するように設定できます。</span><span class="sxs-lookup"><span data-stu-id="c1741-220">(Optional) Voicemail Escape detects that a call was immediately answered by the user’s mobile phone voice mail, and disconnects the call to the mobile phone voice mail.</span></span> <span data-ttu-id="c1741-221">これにより、通話はユーザーの他のエンドポイントで呼び出しを続行できるため、ユーザーが通話に応答できます。</span><span class="sxs-lookup"><span data-stu-id="c1741-221">This allows the call to continue to ring on the user’s other endpoints giving the user the opportunity to answer the call.</span></span> <span data-ttu-id="c1741-222">ボイスメールポリシーの構成方法の詳細については、「 [Lync Server 2013 でボイスメールエスケープを構成](lync-server-2013-configuring-voice-mail-escape.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c1741-222">For details about how to configure a voice mail policy, see [Configuring voice mail escape in Lync Server 2013](lync-server-2013-configuring-voice-mail-escape.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c1741-223">関連項目</span><span class="sxs-lookup"><span data-stu-id="c1741-223">See Also</span></span>


[<span data-ttu-id="c1741-224">Lync Server 2013 で音声ポリシーを作成し、PSTN 使用法レコードを構成する</span><span class="sxs-lookup"><span data-stu-id="c1741-224">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="c1741-225">Lync Server 2013 での PSTN 使用法レコードの表示</span><span class="sxs-lookup"><span data-stu-id="c1741-225">View PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-view-pstn-usage-records.md)  
[<span data-ttu-id="c1741-226">Lync Server 2013 での音声ルートの作成</span><span class="sxs-lookup"><span data-stu-id="c1741-226">Create a voice route in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-route.md)  
[<span data-ttu-id="c1741-227">Lync Server 2013 での音声ルートの変更</span><span class="sxs-lookup"><span data-stu-id="c1741-227">Modify a voice route in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-route.md)  
[<span data-ttu-id="c1741-228">Lync Server 2013 で保留中の変更を音声ルーティング構成に公開する</span><span class="sxs-lookup"><span data-stu-id="c1741-228">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  
[<span data-ttu-id="c1741-229">Lync Server 2013 でのボイスメールエスケープの構成</span><span class="sxs-lookup"><span data-stu-id="c1741-229">Configuring voice mail escape in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-mail-escape.md)  


[<span data-ttu-id="c1741-230">Lync Server 2013 での音声ルーティングのテスト</span><span class="sxs-lookup"><span data-stu-id="c1741-230">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

