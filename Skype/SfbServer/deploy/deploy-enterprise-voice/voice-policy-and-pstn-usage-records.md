---
title: 音声ポリシーを作成または変更し、Skype for Business で PSTN 使用法レコードを構成する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e6ff27e0-e2d1-4445-840f-08f738200c20
description: '概要: Skype for Business Server コントロール パネルを使用して、音声ポリシーを作成または変更し、PSTN 使用法レコードを構成します。'
ms.openlocfilehash: ca97c4c75004849f2ea404c083878da6c726c2e6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51105763"
---
# <a name="create-or-modify-a-voice-policy-and-configure-pstn-usage-records-in-skype-for-business"></a><span data-ttu-id="c776f-103">音声ポリシーを作成または変更し、Skype for Business で PSTN 使用法レコードを構成する</span><span class="sxs-lookup"><span data-stu-id="c776f-103">Create or modify a voice policy and configure PSTN usage records in Skype for Business</span></span>

<span data-ttu-id="c776f-104">**概要:** Skype for Business Server コントロール パネルを使用して、音声ポリシーを作成または変更し、PSTN 使用法レコードを構成します。</span><span class="sxs-lookup"><span data-stu-id="c776f-104">**Summary:** Create or modify voice policies and configure PSTN usage records by using the Skype for Business Server Control Panel.</span></span>

> [!NOTE]
> <span data-ttu-id="c776f-105">各音声ポリシーには、少なくとも 1 つの関連付けられた公衆交換電話網 (PSTN) 使用法レコードが必要です。</span><span class="sxs-lookup"><span data-stu-id="c776f-105">Each voice policy must have at least one associated Public Switched Telephone Network (PSTN) usage record.</span></span> <span data-ttu-id="c776f-106">展開で使用可能なすべての PSTN 使用法レコードの一覧を表示し、エンタープライズ VoIPプロパティを表示するには、「Skype for Business で PSTN 使用法レコードを表示する [」を参照してください](view-pstn-usage-records.md)。</span><span class="sxs-lookup"><span data-stu-id="c776f-106">To see a listing of all PSTN usage records available in your Enterprise Voice deployment and view their properties, see [View PSTN usage records in Skype for Business](view-pstn-usage-records.md).</span></span>

### <a name="to-create-a-voice-policy"></a><span data-ttu-id="c776f-107">音声ポリシーを作成するには</span><span class="sxs-lookup"><span data-stu-id="c776f-107">To create a voice policy</span></span>

1. <span data-ttu-id="c776f-108">Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="c776f-108">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="c776f-109">左側のナビゲーション バーで [**音声ルーティング**] をクリックし、[**音声ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c776f-109">In the left navigation bar, click **Voice Routing** and then click **Voice Policy**.</span></span>

3. <span data-ttu-id="c776f-110">[**音声ポリシー**] ページで [**新規**] をクリックし、新しいポリシーのスコープを選択します。</span><span class="sxs-lookup"><span data-stu-id="c776f-110">On the **Voice Policy** page, click **New** and then select a scope for the new policy:</span></span>

   - <span data-ttu-id="c776f-p102">[**サイト ポリシー**] は、ユーザー ポリシーに割り当てられているユーザーまたはグループを除いて、サイト全体に適用されます。 ポリシー スコープとしてサイトを選択する場合は、[**サイトの選択**] ダイアログ ボックスでサイトを選択します。 サイトで音声ポリシーが既に作成されている場合、そのサイトは [**サイトの選択**] ダイアログ ボックスに表示されません。</span><span class="sxs-lookup"><span data-stu-id="c776f-p102">**Site policy** applies to an entire site, except any users or groups that are assigned to a user policy. If you select Site for a policy scope, choose the site from the **Select a Site** dialog box. If a voice policy has already been created for a site, the site does not appear in the **Select a Site** dialog box.</span></span>

   - <span data-ttu-id="c776f-114">[**ユーザー ポリシー**] は、指定したユーザーまたはグループに適用できます。</span><span class="sxs-lookup"><span data-stu-id="c776f-114">**User policy** can be applied to specified users or groups.</span></span>

4. <span data-ttu-id="c776f-115">音声ポリシーのスコープがユーザーの場合は、そのポリシーのわかりやすい名前を [**名前**] フィールドに入力します。</span><span class="sxs-lookup"><span data-stu-id="c776f-115">If the voice policy scope is User, enter a descriptive name for the policy in the **Name** field.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c776f-116">音声ポリシー スコープがサイトの場合は、[**新しい音声ポリシー**] の [**名前**] フィールドにサイト名が事前に入力されており、変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="c776f-116">If the voice policy scope is Site, the **Name** field in **New Voice Policy** is prepopulated with the site name and cannot be changed.</span></span>

5. <span data-ttu-id="c776f-117">(オプション) その音声ポリシーについての追加説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="c776f-117">(Optional) Enter additional descriptive information for the voice policy.</span></span>

6. <span data-ttu-id="c776f-118">次のチェック ボックスをオンまたはオフにして、この音声ポリシーの各 [**通話機能**] を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="c776f-118">Select or clear the following check boxes to enable or disable each of the **Calling features** for this voice policy:</span></span>

   - <span data-ttu-id="c776f-119">**ボイス メール エスケープ** を使用すると、同時呼び出しが構成され、電話がオフ、バッテリー切れ、または範囲外のときに、通話がユーザーの携帯電話ボイス メール システムに直ちにルーティングされるのを防ぐ。</span><span class="sxs-lookup"><span data-stu-id="c776f-119">**Voice mail escape** prevents calls from being immediately routed to the user's mobile phone voice mail system when simultaneous ringing is configured and the phone is turned off, out of battery, or out of range.</span></span>

     > [!NOTE]
     > <span data-ttu-id="c776f-120">この機能は、Skype for Business Server 管理シェルを通じてのみ構成できます。</span><span class="sxs-lookup"><span data-stu-id="c776f-120">This feature is only configurable through the Skype for Business Server Management Shell</span></span>

   - <span data-ttu-id="c776f-121">[**着信の転送**] では、他の電話機やクライアント デバイスに通話を転送できます。</span><span class="sxs-lookup"><span data-stu-id="c776f-121">**Call forwarding** enables users to forward calls to other phones and client devices.</span></span> <span data-ttu-id="c776f-122">Skype for Business Server では、通話転送の構成オプションの範囲が大幅に広がります。</span><span class="sxs-lookup"><span data-stu-id="c776f-122">Skype for Business Server provides a significantly wider range of configuration options for call forwarding.</span></span> <span data-ttu-id="c776f-123">たとえば、着信が外部で PSTN に転送されることを組織が許可しない方針の場合、管理者は特殊な音声ポリシーを適用して、この制限を展開することができます。</span><span class="sxs-lookup"><span data-stu-id="c776f-123">For example, if an organization does not want to allow incoming calls to be forwarded externally to the PSTN, an administrator can apply a special voice policy to deploy this restriction.</span></span> <span data-ttu-id="c776f-124">既定では有効です。</span><span class="sxs-lookup"><span data-stu-id="c776f-124">Enabled by default.</span></span>

   - <span data-ttu-id="c776f-125">[**委任**] では、代わりに通話を送受信する他のユーザーを指定できます。</span><span class="sxs-lookup"><span data-stu-id="c776f-125">**Delegation** enables users to specify other users to send and receive calls on their behalf.</span></span> <span data-ttu-id="c776f-126">Skype for Business Server では、代理人は同時呼び出しを構成して、マネージャーへの着信呼び出しで代理人のすべての同時呼び出し先を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="c776f-126">In Skype for Business Server, a delegate can configure simultaneous ringing that enables incoming calls to his or her manager to ring all of the delegate's simultaneous ringing targets.</span></span> <span data-ttu-id="c776f-127">これにより、代理人は、マネージャーに向けられた呼び出しに柔軟に対応できます。</span><span class="sxs-lookup"><span data-stu-id="c776f-127">This provides the delegate with greater flexibility in responding to calls directed to the manager.</span></span> <span data-ttu-id="c776f-128">既定では有効です。</span><span class="sxs-lookup"><span data-stu-id="c776f-128">Enabled by default.</span></span>

   - <span data-ttu-id="c776f-p105">[**通話の転送**] では、他のユーザーに通話を転送できます。 既定では有効です。</span><span class="sxs-lookup"><span data-stu-id="c776f-p105">**Call transfer** enables users to transfer calls to other users. Enabled by default.</span></span>

   - <span data-ttu-id="c776f-p106">[**コール パーク**] では、通話を保留 (パーク) し、別の電話機やクライアントで受けることができます。 既定では無効です。</span><span class="sxs-lookup"><span data-stu-id="c776f-p106">**Call park** enables users to park calls on hold and then pick up the call from a different phone or client. Disabled by default.</span></span>

   - <span data-ttu-id="c776f-133">[**同時呼び出し**] では、追加の電話機 (携帯電話など) や他のエンドポイント デバイスで、着信の呼び出し音を鳴らすことができます。</span><span class="sxs-lookup"><span data-stu-id="c776f-133">**Simultaneous ringing** enables incoming calls to ring on additional phones (for example, a mobile phone) or other endpoint devices.</span></span> <span data-ttu-id="c776f-134">Skype for Business Server では、同時呼び出し用の構成オプションが大幅に広がります。</span><span class="sxs-lookup"><span data-stu-id="c776f-134">Skype for Business Server provides a significantly wider range of configuration options for simultaneous ringing.</span></span> <span data-ttu-id="c776f-135">既定では有効です。</span><span class="sxs-lookup"><span data-stu-id="c776f-135">Enabled by default.</span></span>

   - <span data-ttu-id="c776f-136">[**チーム呼び出し**] では、定義したチームのユーザーがチームの他のメンバーの呼び出しに応答できます。</span><span class="sxs-lookup"><span data-stu-id="c776f-136">**Team call** enables users on a defined team to answer calls for other members of the team.</span></span> <span data-ttu-id="c776f-137">既定では有効です。</span><span class="sxs-lookup"><span data-stu-id="c776f-137">Enabled by default.</span></span>

   - <span data-ttu-id="c776f-138">**PSTN の再ルーティング** では、このポリシーを他のエンタープライズ ユーザーに割り当てられているユーザーが発信した通話を、WAN が混雑しているか使用できない場合に PSTN で再ルーティングできます。</span><span class="sxs-lookup"><span data-stu-id="c776f-138">**PSTN re-route** enables calls made by users who are assigned this policy to other enterprise users to be rerouted on the PSTN if the WAN is congested or unavailable.</span></span> <span data-ttu-id="c776f-139">既定では有効です。</span><span class="sxs-lookup"><span data-stu-id="c776f-139">Enabled by default.</span></span>

   - <span data-ttu-id="c776f-p110">[**帯域幅ポリシーの上書き**] により管理者は、特定のユーザーに関する通話受付管理ポリシーによる決定を上書きできます。 既定では無効です。</span><span class="sxs-lookup"><span data-stu-id="c776f-p110">**Bandwidth policy override** enables administrators to override call admission control policy decisions for a particular user. Disabled by default.</span></span>

     > [!NOTE]
     > <span data-ttu-id="c776f-p111">ポリシーが上書きされるのはユーザーに着信する通話のみです。ユーザーが発信する通話は上書きされません。セッションの確立後、使用帯域幅は正確に記録されます。この設定は慎重に使用し、適切な通話受付管理の決定に対しては使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="c776f-p111">The policy will be overridden only for incoming calls to the user and not for outgoing calls that are placed by the user. After the session is established, the bandwidth consumption will be accurately recorded. This setting should be used sparingly and should be reserved for appropriate call admission control decisions.</span></span>

   - <span data-ttu-id="c776f-145">**悪意のある呼び出** しトレースを使用すると、ユーザーはクライアント UI を使用して悪意のある呼び出し (脅威など) を報告できます。これにより、通話詳細レコード (CDRs) の呼び出しにフラグが設定されます。</span><span class="sxs-lookup"><span data-stu-id="c776f-145">**Malicious call tracing** enables users to report malicious calls (such as threats) by using the client UI, which in turn flags the calls in the Call Detail Records (CDRs).</span></span> <span data-ttu-id="c776f-146">既定では無効です。</span><span class="sxs-lookup"><span data-stu-id="c776f-146">Disabled by default.</span></span>

   - <span data-ttu-id="c776f-147">**ビジー オプション** は、指定された音声ポリシーのビジー オプションを有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="c776f-147">**Busy options** enables or disables Busy Options for the specified voice policy.</span></span> <span data-ttu-id="c776f-148">ビジー オプションを使用すると、通話のターゲット ユーザーが電話を使用している場合に、着信呼び出しをボイス メールにルーティングしたり、ビジー信号で拒否したりできます。</span><span class="sxs-lookup"><span data-stu-id="c776f-148">Busy Options allows incoming calls to be routed to voice mail or rejected with a busy signal when the call's target user is on the phone.</span></span> <span data-ttu-id="c776f-149">ビジー オプションは、2016 年 7 月の累積的な更新プログラムで導入された新しい音声ポリシーです。</span><span class="sxs-lookup"><span data-stu-id="c776f-149">Busy Options is a new voice policy introduced in the July 2016 Cumulative Update.</span></span> <span data-ttu-id="c776f-150">このパラメーターをオンにすると、ビジー オプションが有効にされ、オフにすると、ビジー オプションが無効にされます。</span><span class="sxs-lookup"><span data-stu-id="c776f-150">Checking this parameter enables Busy Options, and unchecking it disables Busy Options.</span></span> <span data-ttu-id="c776f-151">詳細については [、「Plan for Busy Options for Skype for Business Server」および「Install and](../../plan-your-deployment/enterprise-voice-solution/busy-options.md) configure Busy [Options for Skype for Business Server」を参照してください](install-and-configure-busy-options.md)。</span><span class="sxs-lookup"><span data-stu-id="c776f-151">For more information, see [Plan for Busy Options for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/busy-options.md) and [Install and configure Busy Options for Skype for Business Server](install-and-configure-busy-options.md).</span></span>

7. <span data-ttu-id="c776f-152">この音声ポリシーの PSTN 使用法レコードの関連付けと構成を行うには、次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="c776f-152">To associate and configure PSTN usage records for this voice policy, do any of the following:</span></span>

   - <span data-ttu-id="c776f-p114">エンタープライズ VoIP 展開で利用できるすべての PSTN 使用法レコードの一覧から 1 つ以上のレコードを選択するには、[**選択**] をクリックします。この音声ポリシーに関連付けるレコードを選択状態にし、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c776f-p114">To choose one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**. Highlight the records that you want to associate with this voice policy, and then click **OK**.</span></span>

   - <span data-ttu-id="c776f-155">PSTN 使用法レコードをこの音声ポリシーから削除するには、レコードを選択状態にして [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c776f-155">To remove a PSTN usage record from this voice policy, highlight the record and click **Remove**.</span></span>

   - <span data-ttu-id="c776f-156">新しい PSTN 使用法レコードを定義してこの音声ポリシーに関連付けるには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="c776f-156">To define a new PSTN usage record and associate it with this voice policy, do the following:</span></span>

     <span data-ttu-id="c776f-157">a.</span><span class="sxs-lookup"><span data-stu-id="c776f-157">a.</span></span> <span data-ttu-id="c776f-158">**[新規作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c776f-158">Click **New**.</span></span>

     <span data-ttu-id="c776f-159">b.</span><span class="sxs-lookup"><span data-stu-id="c776f-159">b.</span></span> <span data-ttu-id="c776f-160">[**名前**] フィールドに、レコードを説明する一意の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="c776f-160">In the **Name** field, enter a unique descriptive name for the record.</span></span> <span data-ttu-id="c776f-161">たとえば、Redmond に位置するフルタイムの従業員に対してRedmond という PSTN 使用法レコードを作成し、もう 1 つの名前付きRedmondTemps を臨時従業員に作成できます。</span><span class="sxs-lookup"><span data-stu-id="c776f-161">For example, you may want to create a PSTN usage record namedRedmond for full-time employees located in Redmond, and another namedRedmondTemps for temporary employees.</span></span>

     > [!NOTE]
     > <span data-ttu-id="c776f-p117">PSTN 使用法レコードの名前は、エンタープライズ VoIP 展開内で一意である必要があります。レコードの保存後、[**名前**] フィールドを編集することはできません。</span><span class="sxs-lookup"><span data-stu-id="c776f-p117">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the **Name** field cannot be edited.</span></span>

     <span data-ttu-id="c776f-164">c.</span><span class="sxs-lookup"><span data-stu-id="c776f-164">c.</span></span> <span data-ttu-id="c776f-165">次のいずれかの方法を使用して、この PSTN 使用法レコードのルートの関連付けと構成を行います。</span><span class="sxs-lookup"><span data-stu-id="c776f-165">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>

   - <span data-ttu-id="c776f-166">エンタープライズ VoIP 展開で利用できるすべてのルートの一覧から、1 つ以上のルートを選択するには、[**選択**] をクリックし、この PSTN 使用法レコードに関連付けるルートを選択状態にして、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c776f-166">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>

   - <span data-ttu-id="c776f-167">PSTN 使用法レコードからルートを削除するには、ルートを選択状態にして [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c776f-167">To remove a route from the PSTN usage record, highlight the route, and then click **Remove**.</span></span>

   - <span data-ttu-id="c776f-168">新しいルートを定義してこの PSTN 使用法レコードに関連付けるには、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c776f-168">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="c776f-169">詳細については、「Create or modify a [voice route in Skype for Business」を参照してください](create-or-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="c776f-169">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

   - <span data-ttu-id="c776f-170">この PSTN 使用法レコードに既に関連付けられているルートを編集するには、ルートを選択状態にして [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c776f-170">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span>

     <span data-ttu-id="c776f-171">d.</span><span class="sxs-lookup"><span data-stu-id="c776f-171">d.</span></span> <span data-ttu-id="c776f-172">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c776f-172">Click **OK**.</span></span>

   - <span data-ttu-id="c776f-173">この音声ポリシーに既に関連付けられている PSTN 使用法レコードを編集するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="c776f-173">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>

     <span data-ttu-id="c776f-174">a.</span><span class="sxs-lookup"><span data-stu-id="c776f-174">a.</span></span> <span data-ttu-id="c776f-175">編集する PSTN 使用法レコードを選択状態にし、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c776f-175">Highlight the PSTN usage record that you want to edit, and then click **Show details**.</span></span>

     <span data-ttu-id="c776f-176">b.</span><span class="sxs-lookup"><span data-stu-id="c776f-176">b.</span></span> <span data-ttu-id="c776f-177">次のいずれかの方法を使用して、この PSTN 使用法レコードのルートの関連付けと構成を行います。</span><span class="sxs-lookup"><span data-stu-id="c776f-177">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>

   - <span data-ttu-id="c776f-178">エンタープライズ VoIP 展開で利用できるすべてのルートの一覧から、1 つ以上のルートを選択するには、[**選択**] をクリックし、この PSTN 使用法レコードに関連付けるルートを選択状態にして、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c776f-178">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes you want to associate with this PSTN usage record, and then click **OK**.</span></span>

   - <span data-ttu-id="c776f-179">この PSTN 使用法レコードからルートを削除するには、ルートを選択状態にして [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c776f-179">To remove a route from this PSTN usage record, highlight the route, and then click **Remove**.</span></span>

   - <span data-ttu-id="c776f-180">新しいルートを定義してこの PSTN 使用法レコードに関連付けるには、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c776f-180">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="c776f-181">詳細については、「Create or modify a [voice route in Skype for Business」を参照してください](create-or-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="c776f-181">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

   - <span data-ttu-id="c776f-182">この PSTN 使用法レコードに既に関連付けられているルートを編集するには、ルートを選択状態にして [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c776f-182">To edit a route that is already associated with this PSTN usage record, highlight the route and lick **Show details**.</span></span>

     <span data-ttu-id="c776f-183">c.</span><span class="sxs-lookup"><span data-stu-id="c776f-183">c.</span></span> <span data-ttu-id="c776f-184">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c776f-184">Click **OK**.</span></span>

8. <span data-ttu-id="c776f-185">最適なパフォーマンスを得るために、PSTN 使用法レコードを並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="c776f-185">Arrange the PSTN usage records for optimum performance.</span></span> <span data-ttu-id="c776f-186">リスト内のレコードの位置を変更するには、レコード名を強調表示し、上矢印または下矢印をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c776f-186">To change a record's position in the list, highlight the record name and click the up or down arrow.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="c776f-187">音声ポリシーに PSTN 使用法レコードを表示する順序は重要です。</span><span class="sxs-lookup"><span data-stu-id="c776f-187">The order in which PSTN usage records are listed in the voice policy is significant.</span></span> <span data-ttu-id="c776f-188">Skype for Business Server は、リストを上から下に移動します。</span><span class="sxs-lookup"><span data-stu-id="c776f-188">Skype for Business Server traverses the list from the top down.</span></span> <span data-ttu-id="c776f-189">RedmondLocal、RedmondLongDist、RedmondInternational、RedmondBackup など、使用頻度別にリストを整理することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c776f-189">We recommend that you organize the list by frequency of use, for example: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span></span>

9. <span data-ttu-id="c776f-190">この音声ポリシーの着信の転送および同時呼び出しに対する PSTN 使用法レコードの関連付けと構成を行うには、次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="c776f-190">To associate and configure PSTN usage records for call forwarding and simultaneous ringing in this voice policy, do any of the following:</span></span>

   - <span data-ttu-id="c776f-191">この音声ポリシーと同じ PSTN 使用法レコードを着信の転送と同時呼び出しに使用する場合は、ドロップダウン メニューから [**呼び出し PSTN 使用法を使用したルーティング**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c776f-191">To use the same PSTN usage records for call forwarding and simultaneous ringing as this voice policy, select the option **Route using the call PSTN usages** from the drop-down menu.</span></span>

   - <span data-ttu-id="c776f-192">内部 Skype for Business ユーザーへの通話転送と同時呼び出しのみを許可するには、ドロップダウン メニューから [ **内部 Skype for Business** ユーザーへのルーティング] オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="c776f-192">To allow call forwarding and simultaneous ringing to internal Skype for Business users only, select the option **Route to internal Skype for Business users only** from the drop-down menu.</span></span> <span data-ttu-id="c776f-193">着信は、外部 PSTN 番号に転送されません。</span><span class="sxs-lookup"><span data-stu-id="c776f-193">Calls will not be forwarded to external PSTN numbers.</span></span>

   - <span data-ttu-id="c776f-p128">この音声ポリシーでの使用とは異なり、着信転送および同時呼び出しに対して異なる PSTN 使用法レコードを指定するには、ドロップダウン メニューから [**カスタムの PSTN 使用法を使用したルーティング**] オプションを選択します。このオプションでは、既存の PSTN 使用法レコードを選択するか、または着信転送および同時呼び出し用の特別な新しい PSTN 使用法レコードを作成するコントロールが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c776f-p128">To specify different PSTN usage records for call forwarding and simultaneous ringing than used for this voice policy, select the option **Route using custom PSTN usages** from the drop-down menu. This option displays a control to select existing PSTN usage records or create new PSTN usage records specifically for call forwarding and simultaneous ringing.</span></span>

   - <span data-ttu-id="c776f-p129">着信転送および同時呼び出しの PSTN 使用法レコードの一覧から、1 つ以上のレコードを選択するには、[**選択**] をクリックします。この着信転送および同時呼び出しポリシーに関連付けるレコードを選択状態にし、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c776f-p129">To choose one or more records from a list of PSTN usage records for call forwarding and simultaneous ringing, click **Select**. Highlight the records that you want to associate with this call forwarding and simultaneous ringing policy, and then click **OK**.</span></span>

   - <span data-ttu-id="c776f-198">この着信の転送と同時呼び出しのポリシーから PSTN 使用法レコードを削除するには、レコードを選択状態にして [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c776f-198">To remove a PSTN usage record from this call forwarding and simultaneous ringing policy, highlight the record and click **Remove**.</span></span>

   - <span data-ttu-id="c776f-199">新しい PSTN 使用法レコードを定義してこの着信の転送と同時呼び出しのポリシーに関連付けるには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="c776f-199">To define a new PSTN usage record and associate it with this call forwarding and simultaneous ringing policy, do the following:</span></span>

     <span data-ttu-id="c776f-200">a.</span><span class="sxs-lookup"><span data-stu-id="c776f-200">a.</span></span> <span data-ttu-id="c776f-201">**[新規作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c776f-201">Click **New**.</span></span>

     <span data-ttu-id="c776f-202">b.</span><span class="sxs-lookup"><span data-stu-id="c776f-202">b.</span></span> <span data-ttu-id="c776f-203">[**名前**] フィールドに、レコードを説明する一意の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="c776f-203">In the **Name** field, enter a unique descriptive name for the record.</span></span>

     > [!NOTE]
     > <span data-ttu-id="c776f-p132">PSTN 使用法レコードの名前は、エンタープライズ VoIP 展開内で一意である必要があります。レコードの保存後、[**名前**] フィールドを編集することはできません。</span><span class="sxs-lookup"><span data-stu-id="c776f-p132">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the **Name** field cannot be edited.</span></span>

     <span data-ttu-id="c776f-206">c.</span><span class="sxs-lookup"><span data-stu-id="c776f-206">c.</span></span> <span data-ttu-id="c776f-207">次のいずれかの方法を使用して、この PSTN 使用法レコードのルートの関連付けと構成を行います。</span><span class="sxs-lookup"><span data-stu-id="c776f-207">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>

   - <span data-ttu-id="c776f-208">エンタープライズ VoIP 展開で利用できるすべてのルートの一覧から 1 つ以上のルートを選択するには、[**選択**] をクリックし、この PSTN 使用法レコードに関連付けるルートを選択状態にして、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c776f-208">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>

   - <span data-ttu-id="c776f-209">PSTN 使用法レコードからルートを削除するには、ルートを選択状態にして [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c776f-209">To remove a route from the PSTN usage record, highlight the route and click **Remove**.</span></span>

   - <span data-ttu-id="c776f-210">新しいルートを定義してこの PSTN 使用法レコードに関連付けるには、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c776f-210">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="c776f-211">詳細については、「Create or modify a [voice route in Skype for Business」を参照してください](create-or-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="c776f-211">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

   - <span data-ttu-id="c776f-212">この PSTN 使用法レコードに既に関連付けられているルートを編集するには、ルートを選択状態にして [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c776f-212">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span>

     <span data-ttu-id="c776f-213">d.</span><span class="sxs-lookup"><span data-stu-id="c776f-213">d.</span></span> <span data-ttu-id="c776f-214">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c776f-214">Click **OK**.</span></span>

   - <span data-ttu-id="c776f-215">この音声ポリシーに既に関連付けられている PSTN 使用法レコードを編集するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="c776f-215">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>

     <span data-ttu-id="c776f-216">a.</span><span class="sxs-lookup"><span data-stu-id="c776f-216">a.</span></span> <span data-ttu-id="c776f-217">編集する PSTN 使用法レコードを選択状態にし、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c776f-217">Highlight the PSTN usage record you want to edit and click **Show details**.</span></span>

     <span data-ttu-id="c776f-218">b.</span><span class="sxs-lookup"><span data-stu-id="c776f-218">b.</span></span> <span data-ttu-id="c776f-219">次のいずれかの方法を使用して、この PSTN 使用法レコードのルートの関連付けと構成を行います。</span><span class="sxs-lookup"><span data-stu-id="c776f-219">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>

   - <span data-ttu-id="c776f-220">エンタープライズ VoIP 展開で利用できるすべてのルートの一覧から 1 つ以上のルートを選択するには、[**選択**] をクリックし、この PSTN 使用法レコードに関連付けるルートを選択状態にして、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c776f-220">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>

   - <span data-ttu-id="c776f-221">この PSTN 使用法レコードからルートを削除するには、ルートを選択状態にして [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c776f-221">To remove a route from this PSTN usage record, highlight the route and click **Remove**.</span></span>

   - <span data-ttu-id="c776f-222">新しいルートを定義してこの PSTN 使用法レコードに関連付けるには、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c776f-222">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="c776f-223">詳細については、「Create or modify a [voice route in Skype for Business」を参照してください](create-or-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="c776f-223">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

   - <span data-ttu-id="c776f-224">この PSTN 使用法レコードに既に関連付けられているルートを編集するには、ルートを選択状態にして [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c776f-224">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span>

     <span data-ttu-id="c776f-225">c.</span><span class="sxs-lookup"><span data-stu-id="c776f-225">c.</span></span> <span data-ttu-id="c776f-226">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c776f-226">Click **OK**.</span></span>

10. <span data-ttu-id="c776f-227">(オプション) 音声ポリシーをテストする番号を入力して、[**実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c776f-227">(Optional) Enter a number to test the voice policy and click **Go**.</span></span> <span data-ttu-id="c776f-228">テスト結果は、[**テストする変換後の番号**] の下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="c776f-228">The test results are displayed under **Translated number to test**.</span></span>

11. <span data-ttu-id="c776f-229">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c776f-229">Click **OK**.</span></span>

12. <span data-ttu-id="c776f-230">[**音声ポリシー**] ページで [**確定**] をクリックし、[**すべて確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c776f-230">On the **Voice Policy** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c776f-231">音声ポリシーを作成または変更したときは常に、[**すべて確定**] コマンドを実行して、構成の変更を公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c776f-231">Any time you create or modify a voice policy, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="c776f-232">詳細については、「操作」の [ドキュメントの「Skype for Business](voice-route-config-changes.md) の音声ルーティング構成に保留中の変更を公開する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c776f-232">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

13. <span data-ttu-id="c776f-233">(省略可能)ボイスメール エスケープは、通話がユーザーの携帯電話ボイス メールによって直ちに応答されたのを検出し、携帯電話ボイス メールへの通話を切断します。</span><span class="sxs-lookup"><span data-stu-id="c776f-233">(Optional) Voicemail Escape detects that a call was immediately answered by the user's mobile phone voice mail, and disconnects the call to the mobile phone voice mail.</span></span> <span data-ttu-id="c776f-234">これにより、ユーザーの他のエンドポイントで通話が引き続き呼び出され、ユーザーは通話に応答できます。</span><span class="sxs-lookup"><span data-stu-id="c776f-234">This allows the call to continue to ring on the user's other endpoints giving the user the opportunity to answer the call.</span></span> <span data-ttu-id="c776f-235">ボイス メール ポリシーを構成する方法の詳細については [、「Configure voice mail escape in Skype for Business」を参照してください](configure-voice-mail-escape.md)。</span><span class="sxs-lookup"><span data-stu-id="c776f-235">For details on how to configure a voice mail policy, see [Configure voice mail escape in Skype for Business](configure-voice-mail-escape.md).</span></span>

### <a name="to-modify-a-voice-policy"></a><span data-ttu-id="c776f-236">音声ポリシーを変更するには</span><span class="sxs-lookup"><span data-stu-id="c776f-236">To modify a voice policy</span></span>

1. <span data-ttu-id="c776f-237">Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="c776f-237">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="c776f-238">左側のナビゲーション バーで [**音声ルーティング**] をクリックし、[**音声ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c776f-238">In the left navigation bar, click **Voice Routing**, and then click **Voice Policy**.</span></span>

3. <span data-ttu-id="c776f-239">[**音声ポリシー**] ページで、音声ポリシー名をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="c776f-239">On the **Voice Policy** page, double-click a voice policy name.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c776f-p143">スコープと名前は、音声ポリシーの作成時に設定されています。 これらは変更できません。</span><span class="sxs-lookup"><span data-stu-id="c776f-p143">The scope and name were set when the voice policy was created. They cannot be changed.</span></span>

4. <span data-ttu-id="c776f-242">(オプション) [**音声ポリシーの編集**] に、音声ポリシーの説明情報を追加で入力します。</span><span class="sxs-lookup"><span data-stu-id="c776f-242">(Optional) In **Edit Voice Policy**, enter additional descriptive information for the voice policy.</span></span>

5. <span data-ttu-id="c776f-243">次のチェック ボックスをオンまたはオフにして、[**通話機能**] をそれぞれ有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="c776f-243">Select or clear the following check boxes to enable or disable each of the **Calling features**:</span></span>

   - <span data-ttu-id="c776f-244">**ボイス メール エスケープ** を使用すると、同時呼び出しが構成され、電話がオフ、バッテリー切れ、または範囲外のときに、通話がユーザーの携帯電話ボイス メール システムに直ちにルーティングされるのを防ぐ。</span><span class="sxs-lookup"><span data-stu-id="c776f-244">**Voice mail escape** prevents calls from being immediately routed to the user's mobile phone voice mail system when simultaneous ringing is configured and the phone is turned off, out of battery, or out of range.</span></span>

     > [!NOTE]
     > <span data-ttu-id="c776f-245">この機能は、Skype for Business Server 管理シェルを通じてのみ構成できます。</span><span class="sxs-lookup"><span data-stu-id="c776f-245">This feature is only configurable through the Skype for Business Server Management Shell</span></span>

   - <span data-ttu-id="c776f-246">[**着信の転送**] では、他の電話機やクライアント デバイスに通話を転送できます。</span><span class="sxs-lookup"><span data-stu-id="c776f-246">**Call forwarding** enables users to forward calls to other phones and client devices.</span></span> <span data-ttu-id="c776f-247">Skype for Business Server では、通話転送の構成オプションの範囲が大幅に広がります。</span><span class="sxs-lookup"><span data-stu-id="c776f-247">Skype for Business Server provides a significantly wider range of configuration options for call forwarding.</span></span> <span data-ttu-id="c776f-248">たとえば、着信が外部で PSTN に転送されることを組織が許可しない方針の場合、管理者は特殊な音声ポリシーを適用して、この制限を展開することができます。</span><span class="sxs-lookup"><span data-stu-id="c776f-248">For example, if an organization does not want to allow incoming calls to be forwarded externally to the PSTN, an administrator can apply a special voice policy to deploy this restriction.</span></span> <span data-ttu-id="c776f-249">既定では有効です。</span><span class="sxs-lookup"><span data-stu-id="c776f-249">Enabled by default.</span></span>

   - <span data-ttu-id="c776f-250">[**委任**] では、代わりに通話を送受信する他のユーザーを指定できます。</span><span class="sxs-lookup"><span data-stu-id="c776f-250">**Delegation** enables users to specify other users to send and receive calls on their behalf.</span></span> <span data-ttu-id="c776f-251">Skype for Business Server では、代理人は同時呼び出しを構成して、マネージャーへの着信呼び出しで代理人のすべての同時呼び出し先を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="c776f-251">In Skype for Business Server, a delegate can configure simultaneous ringing that enables incoming calls to his or her manager to ring all of the delegate's simultaneous ringing targets.</span></span> <span data-ttu-id="c776f-252">これにより、代理人は、マネージャーに向けられた呼び出しに柔軟に対応できます。</span><span class="sxs-lookup"><span data-stu-id="c776f-252">This provides the delegate with greater flexibility in responding to calls directed to the manager.</span></span> <span data-ttu-id="c776f-253">既定では有効です。</span><span class="sxs-lookup"><span data-stu-id="c776f-253">Enabled by default.</span></span>

   - <span data-ttu-id="c776f-p146">**[通話の転送]** では、他のユーザーに通話を転送できます。 既定では有効です。</span><span class="sxs-lookup"><span data-stu-id="c776f-p146">**Call transfer** enables users to transfer calls to other users. Enabled by default.</span></span>

   - <span data-ttu-id="c776f-p147">[**コール パーク**] では、通話を保留 (パーク) し、別の電話機やクライアントで受けることができます。既定では無効です。</span><span class="sxs-lookup"><span data-stu-id="c776f-p147">**Call park** enables users to park calls on hold, and then pick up the call from a different phone or client. Disabled by default.</span></span>

   - <span data-ttu-id="c776f-258">[**同時呼び出し**] では、追加の電話機 (携帯電話など) や他のエンドポイント デバイスで、着信の呼び出し音を鳴らすことができます。</span><span class="sxs-lookup"><span data-stu-id="c776f-258">**Simultaneous ringing** enables incoming calls to ring on additional phones (for example, a mobile phone) or other endpoint devices.</span></span> <span data-ttu-id="c776f-259">Skype for Business Server では、同時呼び出し用の構成オプションが大幅に広がります。</span><span class="sxs-lookup"><span data-stu-id="c776f-259">Skype for Business Server provides a significantly wider range of configuration options for simultaneous ringing.</span></span> <span data-ttu-id="c776f-260">既定では有効です。</span><span class="sxs-lookup"><span data-stu-id="c776f-260">Enabled by default.</span></span>

   - <span data-ttu-id="c776f-261">[**チーム呼び出し**] では、定義したチームのユーザーがチームの他のメンバーの呼び出しに応答できます。</span><span class="sxs-lookup"><span data-stu-id="c776f-261">**Team call** enables users on a defined team to answer calls for other members of the team.</span></span> <span data-ttu-id="c776f-262">既定では有効です。</span><span class="sxs-lookup"><span data-stu-id="c776f-262">Enabled by default.</span></span>

   - <span data-ttu-id="c776f-263">**PSTN の再ルーティング** では、このポリシーを他のエンタープライズ ユーザーに割り当てられているユーザーが発信した通話を、WAN が混雑しているか使用できない場合に PSTN で再ルーティングできます。</span><span class="sxs-lookup"><span data-stu-id="c776f-263">**PSTN re-route** enables calls made by users who are assigned this policy to other enterprise users to be rerouted on the PSTN if the WAN is congested or unavailable.</span></span> <span data-ttu-id="c776f-264">既定では有効です。</span><span class="sxs-lookup"><span data-stu-id="c776f-264">Enabled by default.</span></span>

   - <span data-ttu-id="c776f-265">**帯域幅ポリシーの上書** きにより、管理者は特定のユーザーに対する CAC ポリシーの決定を上書きできます。</span><span class="sxs-lookup"><span data-stu-id="c776f-265">**Bandwidth policy override** enables administrators to override CAC policy decisions for a particular user.</span></span> <span data-ttu-id="c776f-266">既定では無効です。</span><span class="sxs-lookup"><span data-stu-id="c776f-266">Disabled by default.</span></span>

     > [!NOTE]
     > <span data-ttu-id="c776f-p152">ポリシーが上書きされるのはユーザーに着信する通話のみです。ユーザーが発信する通話は上書きされません。セッションの確立後、使用帯域幅は正確に記録されます。この設定は慎重に使用してください。</span><span class="sxs-lookup"><span data-stu-id="c776f-p152">The policy will be overridden only for incoming calls to the user and not for outgoing calls that are placed by the user. After the session is established, the bandwidth consumption will be accurately recorded. This setting should be used sparingly.</span></span>

   - <span data-ttu-id="c776f-270">**悪意のある呼び出** しトレースを使用すると、ユーザーはクライアント UI を使用して悪意のある呼び出し (脅威など) を報告できます。これにより、CDRs の呼び出しにフラグが設定されます。</span><span class="sxs-lookup"><span data-stu-id="c776f-270">**Malicious call tracing** enables users to report malicious calls (such as threats) using the client UI, which in turn flags the calls in the CDRs.</span></span> <span data-ttu-id="c776f-271">既定では無効です。</span><span class="sxs-lookup"><span data-stu-id="c776f-271">Disabled by default.</span></span>

6. <span data-ttu-id="c776f-272">この音声ポリシーの PSTN 使用法レコードの関連付けと構成を行うには、次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="c776f-272">To associate and configure PSTN usage records for this voice policy, do any of the following:</span></span>

   - <span data-ttu-id="c776f-p154">エンタープライズ VoIP 展開で利用できるすべての PSTN 使用法レコードの一覧から 1 つ以上のレコードを選択するには、[**選択**] をクリックします。この音声ポリシーに関連付けるレコードを選択状態にし、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c776f-p154">To choose one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**. Highlight the records that you want to associate with this voice policy, and then click **OK**.</span></span>

   - <span data-ttu-id="c776f-275">PSTN 使用法レコードをこの音声ポリシーから削除するには、レコードを選択状態にして [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c776f-275">To remove a PSTN usage record from this voice policy, highlight the record and click **Remove**.</span></span>

   - <span data-ttu-id="c776f-276">新しい PSTN 使用法レコードを定義してこの音声ポリシーに関連付けるには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="c776f-276">To define a new PSTN usage record and associate it with this voice policy, do the following:</span></span>

     <span data-ttu-id="c776f-277">a.</span><span class="sxs-lookup"><span data-stu-id="c776f-277">a.</span></span> <span data-ttu-id="c776f-278">**[新規作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c776f-278">Click **New**.</span></span>

     <span data-ttu-id="c776f-279">b.</span><span class="sxs-lookup"><span data-stu-id="c776f-279">b.</span></span> <span data-ttu-id="c776f-280">[**名前**] フィールドに、レコードを説明する一意の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="c776f-280">In the **Name** field, enter a unique descriptive name for the record.</span></span> <span data-ttu-id="c776f-281">たとえば、Redmond に位置する正社員の PSTN 使用法レコードRedmond と、臨時従業員のRedmondTemps という名前の別のレコードを作成できます。</span><span class="sxs-lookup"><span data-stu-id="c776f-281">For example, you may want to create a PSTN usage record namedRedmond for full-time employees located in Redmond, and another record namedRedmondTemps for temporary employees.</span></span>

     > [!NOTE]
     > <span data-ttu-id="c776f-p157">PSTN 使用法レコードの名前は、エンタープライズ VoIP 展開内で一意である必要があります。レコードの保存後、[**名前**] フィールドを編集することはできません。</span><span class="sxs-lookup"><span data-stu-id="c776f-p157">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the **Name** field cannot be edited.</span></span>

     <span data-ttu-id="c776f-284">c.</span><span class="sxs-lookup"><span data-stu-id="c776f-284">c.</span></span> <span data-ttu-id="c776f-285">次のいずれかの方法を使用して、この PSTN 使用法レコードのルートの関連付けと構成を行います。</span><span class="sxs-lookup"><span data-stu-id="c776f-285">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>

   - <span data-ttu-id="c776f-286">エンタープライズ VoIP 展開で利用できるすべてのルートの一覧から 1 つ以上のルートを選択するには、[**選択**] をクリックし、この PSTN 使用法レコードに関連付けるルートを選択状態にして、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c776f-286">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>

   - <span data-ttu-id="c776f-287">PSTN 使用法レコードからルートを削除するには、ルートを選択状態にして [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c776f-287">To remove a route from the PSTN usage record, highlight the route and click **Remove**.</span></span>

   - <span data-ttu-id="c776f-288">新しいルートを定義してこの PSTN 使用法レコードに関連付けるには、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c776f-288">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="c776f-289">詳細については、「Create or modify a [voice route in Skype for Business」を参照してください](create-or-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="c776f-289">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

   - <span data-ttu-id="c776f-290">この PSTN 使用法レコードに既に関連付けられているルートを編集するには、ルートを選択状態にして [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c776f-290">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span>

     <span data-ttu-id="c776f-291">d.</span><span class="sxs-lookup"><span data-stu-id="c776f-291">d.</span></span> <span data-ttu-id="c776f-292">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c776f-292">Click **OK**.</span></span>

   - <span data-ttu-id="c776f-293">この音声ポリシーに既に関連付けられている PSTN 使用法レコードを編集するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="c776f-293">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>

     <span data-ttu-id="c776f-294">a.</span><span class="sxs-lookup"><span data-stu-id="c776f-294">a.</span></span> <span data-ttu-id="c776f-295">編集する PSTN 使用法レコードを選択状態にし、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c776f-295">Highlight the PSTN usage record that you want to edit and click **Show details**.</span></span>

     <span data-ttu-id="c776f-296">b.</span><span class="sxs-lookup"><span data-stu-id="c776f-296">b.</span></span> <span data-ttu-id="c776f-297">次のいずれかの方法を使用して、この PSTN 使用法レコードのルートの関連付けと構成を行います。</span><span class="sxs-lookup"><span data-stu-id="c776f-297">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>

   - <span data-ttu-id="c776f-298">エンタープライズ VoIP 展開で利用できるすべてのルートの一覧から 1 つ以上のルートを選択するには、[**選択**] をクリックし、この PSTN 使用法レコードに関連付けるルートを選択状態にして、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c776f-298">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>

   - <span data-ttu-id="c776f-299">この PSTN 使用法レコードからルートを削除するには、ルートを選択状態にして [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c776f-299">To remove a route from this PSTN usage record, highlight the route and click **Remove**.</span></span>

   - <span data-ttu-id="c776f-300">新しいルートを定義してこの PSTN 使用法レコードに関連付けるには、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c776f-300">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="c776f-301">詳細については、「Create or modify a [voice route in Skype for Business」を参照してください](create-or-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="c776f-301">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

   - <span data-ttu-id="c776f-302">この PSTN 使用法レコードに既に関連付けられているルートを編集するには、ルートを選択状態にして [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c776f-302">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span>

     <span data-ttu-id="c776f-303">c.</span><span class="sxs-lookup"><span data-stu-id="c776f-303">c.</span></span> <span data-ttu-id="c776f-304">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c776f-304">Click **OK**.</span></span>

7. <span data-ttu-id="c776f-305">最適なパフォーマンスを得るために、PSTN 使用法レコードを並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="c776f-305">Arrange the PSTN usage records for optimum performance.</span></span> <span data-ttu-id="c776f-306">リスト内のレコードの位置を変更するには、レコード名を強調表示し、上矢印または下矢印をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c776f-306">To change a record's position in the list, highlight the record name and click the up or down arrow.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c776f-307">音声ポリシーに PSTN 使用法レコードを表示する順序は重要です。</span><span class="sxs-lookup"><span data-stu-id="c776f-307">The order in which PSTN usage records are listed in the voice policy is significant.</span></span> <span data-ttu-id="c776f-308">Skype for Business Server は、リストを上から下に移動します。</span><span class="sxs-lookup"><span data-stu-id="c776f-308">Skype for Business Server traverses the list from the top down.</span></span> <span data-ttu-id="c776f-309">RedmondLocal、RedmondLongDist、RedmondInternational、RedmondBackup など、使用頻度別にリストを整理することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c776f-309">We recommend that you organize the list by frequency of use, for example: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span></span>

8. <span data-ttu-id="c776f-310">この音声ポリシーの着信の転送および同時呼び出しに対する PSTN 使用法レコードの関連付けと構成を行うには、次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="c776f-310">To associate and configure PSTN usage records for call forwarding and simultaneous ringing in this voice policy, do any of the following:</span></span>

   - <span data-ttu-id="c776f-311">この音声ポリシーと同じ PSTN 使用法レコードを着信の転送と同時呼び出しに使用する場合は、ドロップダウン メニューから [**呼び出し PSTN 使用法を使用したルーティング**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c776f-311">To use the same PSTN usage records for call forwarding and simultaneous ringing as this voice policy, select the option **Route using the call PSTN usages** from the drop-down menu.</span></span>

   - <span data-ttu-id="c776f-312">内部 Skype for Business ユーザーへの通話転送と同時呼び出しのみを許可するには、ドロップダウン メニューから [ **内部の Skype for Business** ユーザーにのみルーティング] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c776f-312">To allow call forwarding and simultaneous ringing to internal Skype for Business users only, select **Route to internal Skype for Business users only** from the drop-down menu.</span></span> <span data-ttu-id="c776f-313">通話は外部の PSTN 番号には転送されません。</span><span class="sxs-lookup"><span data-stu-id="c776f-313">Calls will not be forwarded to external PSTN numbers.</span></span>

   - <span data-ttu-id="c776f-p168">この音声ポリシーに使用されているのとは別の PTSN 使用法レコードを着信の転送と同時呼び出しに指定する場合は、ドロップダウン メニューから [**カスタムの PSTN 使用法を使用したルーティング**] を選択します。このオプションを選択するとコントロールが表示され、着信の転送と同時呼び出しに対して、既存の PSTN 使用法レコードを選択するかまたは新しい PSTN 使用法レコードを作成できます。</span><span class="sxs-lookup"><span data-stu-id="c776f-p168">To specify different PSTN usage records for call forwarding and simultaneous ringing than those used for this voice policy, select the option **Route using custom PSTN usages** from the drop-down menu. This option displays a control to select existing PSTN usage records or to create new PSTN usage records, specifically for call forwarding and simultaneous ringing.</span></span>

   - <span data-ttu-id="c776f-p169">着信の転送と同時呼び出しのために PSTN 使用法レコードの一覧から 1 つ以上のレコードを選択するには、[**選択**] をクリックします。この着信の転送と同時呼び出しのポリシーに関連付けるレコードを選択状態にし、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c776f-p169">To choose one or more records from a list of PSTN usage records for call forwarding and simultaneous ringing, click **Select**. Highlight the records that you want to associate with this call forwarding and simultaneous ringing policy, and then click **OK**.</span></span>

   - <span data-ttu-id="c776f-318">この着信の転送と同時呼び出しのポリシーから PSTN 使用法レコードを削除するには、レコードを選択状態にして [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c776f-318">To remove a PSTN usage record from this call forwarding and simultaneous ringing policy, highlight the record and click **Remove**.</span></span>

   - <span data-ttu-id="c776f-319">新しい PSTN 使用法レコードを定義してこの着信の転送と同時呼び出しのポリシーに関連付けるには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="c776f-319">To define a new PSTN usage record and associate it with this call forwarding and simultaneous ringing policy, do the following:</span></span>

     <span data-ttu-id="c776f-320">a.</span><span class="sxs-lookup"><span data-stu-id="c776f-320">a.</span></span> <span data-ttu-id="c776f-321">**[新規作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c776f-321">Click **New**.</span></span>

     <span data-ttu-id="c776f-322">b.</span><span class="sxs-lookup"><span data-stu-id="c776f-322">b.</span></span> <span data-ttu-id="c776f-323">[**名前**] フィールドに、レコードを説明する一意の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="c776f-323">In the **Name** field, enter a unique descriptive name for the record.</span></span>

     > [!NOTE]
     > <span data-ttu-id="c776f-p172">PSTN 使用法レコードの名前は、エンタープライズ VoIP 展開内で一意である必要があります。レコードの保存後、[**名前**] フィールドを編集することはできません。</span><span class="sxs-lookup"><span data-stu-id="c776f-p172">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the **Name** field cannot be edited.</span></span>

     <span data-ttu-id="c776f-326">c.</span><span class="sxs-lookup"><span data-stu-id="c776f-326">c.</span></span> <span data-ttu-id="c776f-327">次のいずれかの方法を使用して、この PSTN 使用法レコードのルートの関連付けと構成を行います。</span><span class="sxs-lookup"><span data-stu-id="c776f-327">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>

   - <span data-ttu-id="c776f-328">エンタープライズ VoIP 展開で利用できるすべてのルートの一覧から 1 つ以上のルートを選択するには、[**選択**] をクリックし、この PSTN 使用法レコードに関連付けるルートを選択状態にして、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c776f-328">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>

   - <span data-ttu-id="c776f-329">PSTN 使用法レコードからルートを削除するには、ルートを選択状態にして [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c776f-329">To remove a route from the PSTN usage record, highlight the route and click **Remove**.</span></span>

   - <span data-ttu-id="c776f-330">新しいルートを定義してこの PSTN 使用法レコードに関連付けるには、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c776f-330">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="c776f-331">詳細については、「Create or modify a [voice route in Skype for Business」を参照してください](create-or-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="c776f-331">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

   - <span data-ttu-id="c776f-332">この PSTN 使用法レコードに既に関連付けられているルートを編集するには、ルートを選択状態にして [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c776f-332">To edit a route that is already associated with this PSTN usage record, highlight the route, and then click **Show details**.</span></span> <span data-ttu-id="c776f-333">詳細については、「[Modify a Voice Route](/previous-versions/office/lync-server-2013/lync-server-2013-modify-a-voice-route)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c776f-333">For details, see [Modify a Voice Route](/previous-versions/office/lync-server-2013/lync-server-2013-modify-a-voice-route).</span></span>

     <span data-ttu-id="c776f-334">d.</span><span class="sxs-lookup"><span data-stu-id="c776f-334">d.</span></span> <span data-ttu-id="c776f-335">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c776f-335">Click **OK**.</span></span>

   - <span data-ttu-id="c776f-336">この音声ポリシーに既に関連付けられている PSTN 使用法レコードを編集するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="c776f-336">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>

     <span data-ttu-id="c776f-337">a.</span><span class="sxs-lookup"><span data-stu-id="c776f-337">a.</span></span> <span data-ttu-id="c776f-338">編集する PSTN 使用法レコードを選択状態にし、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c776f-338">Highlight the PSTN usage record that you want to edit and click **Show details**.</span></span>

     <span data-ttu-id="c776f-339">b.</span><span class="sxs-lookup"><span data-stu-id="c776f-339">b.</span></span> <span data-ttu-id="c776f-340">次のいずれかの方法を使用して、この PSTN 使用法レコードのルートの関連付けと構成を行います。</span><span class="sxs-lookup"><span data-stu-id="c776f-340">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>

     - <span data-ttu-id="c776f-341">エンタープライズ VoIP 展開で利用できるすべてのルートの一覧から、1 つ以上のルートを選択するには、[**選択**] をクリックし、この PSTN 使用法レコードに関連付けるルートを選択状態にして、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c776f-341">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes you want to associate with this PSTN usage record, and then click **OK**.</span></span>

     - <span data-ttu-id="c776f-342">この PSTN 使用法レコードからルートを削除するには、ルートを選択状態にして [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c776f-342">To remove a route from this PSTN usage record, highlight the route and click **Remove**.</span></span>

     - <span data-ttu-id="c776f-343">新しいルートを定義してこの PSTN 使用法レコードに関連付けるには、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c776f-343">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="c776f-344">詳細については、「Create or modify a [voice route in Skype for Business」を参照してください](create-or-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="c776f-344">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

     - <span data-ttu-id="c776f-345">この PSTN 使用法レコードに既に関連付けられているルートを編集するには、ルートを選択状態にして [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c776f-345">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="c776f-346">詳細については、「[Modify a Voice Route](/previous-versions/office/lync-server-2013/lync-server-2013-modify-a-voice-route)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c776f-346">For details, see [Modify a Voice Route](/previous-versions/office/lync-server-2013/lync-server-2013-modify-a-voice-route).</span></span>

     <span data-ttu-id="c776f-347">c.</span><span class="sxs-lookup"><span data-stu-id="c776f-347">c.</span></span> <span data-ttu-id="c776f-348">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c776f-348">Click **OK**.</span></span>

9. <span data-ttu-id="c776f-349">(オプション) 音声ポリシーをテストする番号を入力して、[**実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c776f-349">(Optional) Enter a number to test the voice policy and click **Go**.</span></span> <span data-ttu-id="c776f-350">テスト結果は、[**テストする変換後の番号**] の下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="c776f-350">The test results are displayed under **Translated number to test**.</span></span>

10. <span data-ttu-id="c776f-351">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c776f-351">Click **OK**.</span></span>

11. <span data-ttu-id="c776f-352">[**音声ポリシー**] ページで [**確定**] をクリックし、[**すべて確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c776f-352">On the **Voice Policy** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c776f-353">音声ポリシーを作成または変更したときは常に、[**すべて確定**] コマンドを実行して、構成の変更を公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c776f-353">Whenever you create or modify a voice policy, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="c776f-354">詳細については、「操作」の [ドキュメントの「Skype for Business](voice-route-config-changes.md) の音声ルーティング構成に保留中の変更を公開する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c776f-354">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

12. <span data-ttu-id="c776f-355">(省略可能)ボイスメール エスケープは、通話がユーザーの携帯電話ボイス メールによって直ちに応答されたのを検出し、携帯電話ボイス メールへの通話を切断します。</span><span class="sxs-lookup"><span data-stu-id="c776f-355">(Optional) Voicemail Escape detects that a call was immediately answered by the user's mobile phone voice mail, and disconnects the call to the mobile phone voice mail.</span></span> <span data-ttu-id="c776f-356">これにより、ユーザーの他のエンドポイントで通話が引き続き呼び出され、ユーザーは通話に応答できます。</span><span class="sxs-lookup"><span data-stu-id="c776f-356">This allows the call to continue to ring on the user's other endpoints giving the user the opportunity to answer the call.</span></span> <span data-ttu-id="c776f-357">ボイス メール ポリシーを構成する方法の詳細については [、「Configure voice mail escape in Skype for Business」を参照してください](configure-voice-mail-escape.md)。</span><span class="sxs-lookup"><span data-stu-id="c776f-357">For details about how to configure a voice mail policy, see [Configure voice mail escape in Skype for Business](configure-voice-mail-escape.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c776f-358">関連項目</span><span class="sxs-lookup"><span data-stu-id="c776f-358">See also</span></span>

[<span data-ttu-id="c776f-359">Skype for Business で PSTN 使用法レコードを表示する</span><span class="sxs-lookup"><span data-stu-id="c776f-359">View PSTN usage records in Skype for Business</span></span>](view-pstn-usage-records.md)

[<span data-ttu-id="c776f-360">Skype for Business で音声ルートを作成または変更する</span><span class="sxs-lookup"><span data-stu-id="c776f-360">Create or modify a voice route in Skype for Business</span></span>](create-or-modify-a-voice-route.md)

[<span data-ttu-id="c776f-361">Skype for Business の音声ルーティング構成に対する保留中の変更を公開する</span><span class="sxs-lookup"><span data-stu-id="c776f-361">Publish pending changes to the voice routing configuration in Skype for Business</span></span>](voice-route-config-changes.md)

[<span data-ttu-id="c776f-362">Skype for Business でボイス メール エスケープを構成する</span><span class="sxs-lookup"><span data-stu-id="c776f-362">Configure voice mail escape in Skype for Business</span></span>](configure-voice-mail-escape.md)