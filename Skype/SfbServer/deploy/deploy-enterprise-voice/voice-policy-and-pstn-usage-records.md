---
title: 作成し、音声ポリシーを変更または Skype ビジネスのために PSTN 使用法レコードを構成します。
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e6ff27e0-e2d1-4445-840f-08f738200c20
description: '概要: は、作成および音声ポリシーを変更またはビジネス サーバーのコントロール パネルの Skype を使用して、PSTN 使用法レコードを構成します。'
ms.openlocfilehash: 9a5e65e3d281a9cb902699b3b31068ea28831bb4
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/28/2018
ms.locfileid: "23253263"
---
# <a name="create-or-modify-a-voice-policy-and-configure-pstn-usage-records-in-skype-for-business"></a><span data-ttu-id="55274-103">作成し、音声ポリシーを変更または Skype ビジネスのために PSTN 使用法レコードを構成します。</span><span class="sxs-lookup"><span data-stu-id="55274-103">Create or modify a voice policy and configure PSTN usage records in Skype for Business</span></span>

<span data-ttu-id="55274-104">**の概要:** 作成し、音声ポリシーを変更またはビジネス サーバーのコントロール パネルの Skype を使用して、PSTN 使用法レコードを構成します。</span><span class="sxs-lookup"><span data-stu-id="55274-104">**Summary:** Create or modify voice policies and configure PSTN usage records by using the Skype for Business Server Control Panel.</span></span>

> [!NOTE]
> <span data-ttu-id="55274-105">各音声ポリシーには、少なくとも 1 つの公衆交換電話網 (PSTN) 使用法レコードが関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="55274-105">Each voice policy must have at least one associated Public Switched Telephone Network (PSTN) usage record.</span></span> <span data-ttu-id="55274-106">エンタープライズ VoIP 展開で利用可能なすべての PSTN 使用法レコードの一覧を見るし、そのプロパティを表示、[ビジネスの Skype でのビューの PSTN 使用法レコード](view-pstn-usage-records.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="55274-106">To see a listing of all PSTN usage records available in your Enterprise Voice deployment and view their properties, see [View PSTN usage records in Skype for Business](view-pstn-usage-records.md).</span></span>

### <a name="to-create-a-voice-policy"></a><span data-ttu-id="55274-107">音声ポリシーを作成するには</span><span class="sxs-lookup"><span data-stu-id="55274-107">To create a voice policy</span></span>

1. <span data-ttu-id="55274-108">Skype をビジネス サーバーのコントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="55274-108">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="55274-109">左側のナビゲーション バーで [**音声のルーティング**] をクリックし、[**音声ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55274-109">In the left navigation bar, click **Voice Routing** and then click **Voice Policy**.</span></span>

3. <span data-ttu-id="55274-110">[**音声ポリシー**] ページで [**新規**] をクリックし、新しいポリシーのスコープを選択します。</span><span class="sxs-lookup"><span data-stu-id="55274-110">On the **Voice Policy** page, click **New** and then select a scope for the new policy:</span></span>

   - <span data-ttu-id="55274-p102">[**サイト ポリシー**] は、ユーザー ポリシーに割り当てられているユーザーまたはグループを除いて、サイト全体に適用されます。ポリシー スコープとしてサイトを選択する場合は、[**サイトの選択**] ダイアログ ボックスでサイトを選択します。サイトで音声ポリシーが既に作成されている場合、そのサイトは [**サイトの選択**] ダイアログ ボックスに表示されません。</span><span class="sxs-lookup"><span data-stu-id="55274-p102">**Site policy** applies to an entire site, except any users or groups that are assigned to a user policy. If you select Site for a policy scope, choose the site from the **Select a Site** dialog box. If a voice policy has already been created for a site, the site does not appear in the **Select a Site** dialog box.</span></span>

   - <span data-ttu-id="55274-114">[**ユーザー ポリシー**] は、指定したユーザーまたはグループに適用できます。</span><span class="sxs-lookup"><span data-stu-id="55274-114">**User policy** can be applied to specified users or groups.</span></span>

4. <span data-ttu-id="55274-115">音声ポリシー スコープがユーザーの場合は、そのポリシーのわかりやすい名前を "**名前**" フィールドに入力します。</span><span class="sxs-lookup"><span data-stu-id="55274-115">If the voice policy scope is User, enter a descriptive name for the policy in the **Name** field.</span></span>

    > [!NOTE]
    > <span data-ttu-id="55274-116">音声ポリシー スコープがサイトの場合は、[**新しい音声ポリシー**] の "**名前**" フィールドにサイト名が事前に入力されており、変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="55274-116">If the voice policy scope is Site, the **Name** field in **New Voice Policy** is prepopulated with the site name and cannot be changed.</span></span>

5. <span data-ttu-id="55274-117">(オプション) その音声ポリシーについての追加説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="55274-117">(Optional) Enter additional descriptive information for the voice policy.</span></span>

6. <span data-ttu-id="55274-118">次のチェック ボックスをオンまたはオフにして、この音声ポリシーの各 [**通話機能**] を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="55274-118">Select or clear the following check boxes to enable or disable each of the **Calling features** for this voice policy:</span></span>

   - <span data-ttu-id="55274-119">**ボイス メールのエスケープ**には、同時呼び出しを構成し、携帯電話がオフ、バッテリ、または範囲外になっている場合にユーザーの携帯電話のボイス メール システムにすぐにルーティングされてからの呼び出しができなくなります。</span><span class="sxs-lookup"><span data-stu-id="55274-119">**Voice mail escape** prevents calls from being immediately routed to the user's mobile phone voice mail system when simultaneous ringing is configured and the phone is turned off, out of battery, or out of range.</span></span>

    > [!NOTE]
    > <span data-ttu-id="55274-120">この機能はビジネス サーバー管理シェルの Skype 経由で構成可能なだけです。</span><span class="sxs-lookup"><span data-stu-id="55274-120">This feature is only configurable through the Skype for Business Server Management Shell</span></span>

   - <span data-ttu-id="55274-121">[**着信の転送**] を使用すると、着信を他の電話機またはクライアント デバイスに転送できます。</span><span class="sxs-lookup"><span data-stu-id="55274-121">**Call forwarding** enables users to forward calls to other phones and client devices.</span></span> <span data-ttu-id="55274-122">ビジネス サーバー用の Skype は、非常に広範囲の着信の転送の構成オプションを提供します。</span><span class="sxs-lookup"><span data-stu-id="55274-122">Skype for Business Server provides a significantly wider range of configuration options for call forwarding.</span></span> <span data-ttu-id="55274-123">たとえば、着信が外部で PSTN に転送されることを組織が許可しない方針の場合、管理者は特殊な音声ポリシーを適用して、この制限を展開することができます。</span><span class="sxs-lookup"><span data-stu-id="55274-123">For example, if an organization does not want to allow incoming calls to be forwarded externally to the PSTN, an administrator can apply a special voice policy to deploy this restriction.</span></span> <span data-ttu-id="55274-124">既定では有効です。</span><span class="sxs-lookup"><span data-stu-id="55274-124">Enabled by default.</span></span>

   - <span data-ttu-id="55274-125">[**委任**] では、代わりに通話を送受信する他のユーザーを指定できます。</span><span class="sxs-lookup"><span data-stu-id="55274-125">**Delegation** enables users to specify other users to send and receive calls on their behalf.</span></span> <span data-ttu-id="55274-126">ビジネス サーバーの Skype は、[同時呼び出しにより、すべての代理人の同時着信ターゲット リングに自分のマネージャーに着信するデリゲートを構成できます。</span><span class="sxs-lookup"><span data-stu-id="55274-126">In Skype for Business Server, a delegate can configure simultaneous ringing that enables incoming calls to his or her manager to ring all of the delegate's simultaneous ringing targets.</span></span> <span data-ttu-id="55274-127">これは、管理者宛ての呼び出しに応答するために柔軟性の高いデリゲートを提供します。</span><span class="sxs-lookup"><span data-stu-id="55274-127">This provides the delegate with greater flexibility in responding to calls directed to the manager.</span></span> <span data-ttu-id="55274-128">既定では有効です。</span><span class="sxs-lookup"><span data-stu-id="55274-128">Enabled by default.</span></span>

   - <span data-ttu-id="55274-p105">[**通話の転送**] では、他のユーザーに通話を転送できます。既定では有効です。</span><span class="sxs-lookup"><span data-stu-id="55274-p105">**Call transfer** enables users to transfer calls to other users. Enabled by default.</span></span>

   - <span data-ttu-id="55274-p106">[**コール パーク**] では、通話を保留 (パーク) し、別の電話機やクライアントで受けることができます。既定では無効です。</span><span class="sxs-lookup"><span data-stu-id="55274-p106">**Call park** enables users to park calls on hold and then pick up the call from a different phone or client. Disabled by default.</span></span>

   - <span data-ttu-id="55274-133">[**同時呼び出し**] では、追加の電話機 (携帯電話など) や他のエンドポイント デバイスで、着信の呼び出し音を鳴らすことができます。</span><span class="sxs-lookup"><span data-stu-id="55274-133">**Simultaneous ringing** enables incoming calls to ring on additional phones (for example, a mobile phone) or other endpoint devices.</span></span> <span data-ttu-id="55274-134">ビジネス サーバー用の Skype は、非常に広範囲の同時呼び出しの構成オプションを提供します。</span><span class="sxs-lookup"><span data-stu-id="55274-134">Skype for Business Server provides a significantly wider range of configuration options for simultaneous ringing.</span></span> <span data-ttu-id="55274-135">既定では有効です。</span><span class="sxs-lookup"><span data-stu-id="55274-135">Enabled by default.</span></span>

   - <span data-ttu-id="55274-p108">[**チーム呼び出し**] では、定義したチームのユーザーがチームの他のメンバーの呼び出しに応答できます。既定では有効です。</span><span class="sxs-lookup"><span data-stu-id="55274-p108">**Team call** enables users on a defined team to answer calls for other members of the team. Enabled by default.</span></span>

   - <span data-ttu-id="55274-p109">[**PSTN 再ルート**] では、WAN が混雑していたり利用できなかったりする場合に、このポリシーを割り当てられているユーザーが他のエンタープライズ ユーザーにかけた通話を、PSTN で再ルートできます。既定では有効です。</span><span class="sxs-lookup"><span data-stu-id="55274-p109">**PSTN re-route** enables calls made by users who are assigned this policy to other enterprise users to be rerouted on the PSTN if the WAN is congested or unavailable. Enabled by default.</span></span>

   - <span data-ttu-id="55274-p110">[**帯域幅ポリシーの上書き**] により管理者は、特定のユーザーに関する通話受付管理ポリシーによる決定を上書きできます。既定では無効です。</span><span class="sxs-lookup"><span data-stu-id="55274-p110">**Bandwidth policy override** enables administrators to override call admission control policy decisions for a particular user. Disabled by default.</span></span>

    > [!NOTE]
    > <span data-ttu-id="55274-p111">ポリシーが上書きされるのはユーザーに着信する通話のみです。ユーザーが発信する通話は上書きされません。セッションの確立後、使用帯域幅は正確に記録されます。この設定は慎重に使用し、適切な通話受付管理の決定に対しては使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="55274-p111">The policy will be overridden only for incoming calls to the user and not for outgoing calls that are placed by the user. After the session is established, the bandwidth consumption will be accurately recorded. This setting should be used sparingly and should be reserved for appropriate call admission control decisions.</span></span>

   - <span data-ttu-id="55274-p112">[**悪意のある呼び出しのトレース**] では、ユーザーがクライアントの UI を使用して、悪意のある呼び出し (脅迫など) を報告できます。報告されると、通話詳細記録 (CDR) 内のその呼び出しにフラグが付けられます。既定では無効です。</span><span class="sxs-lookup"><span data-stu-id="55274-p112">**Malicious call tracing** enables users to report malicious calls (such as threats) by using the client UI, which in turn flags the calls in the Call Detail Records (CDRs). Disabled by default.</span></span>

   - <span data-ttu-id="55274-147">[**取り込み中オプション**] では、指定した音声ポリシーの取り込み中オプションを有効または無効にできます。</span><span class="sxs-lookup"><span data-stu-id="55274-147">**Busy options** enables or disables Busy Options for the specified voice policy.</span></span> <span data-ttu-id="55274-148">着信通話をボイス メールにルーティングし、通話先のユーザーが電話中の場合に話中音とともに拒否することができます。</span><span class="sxs-lookup"><span data-stu-id="55274-148">Busy Options allows incoming calls to be routed to voice mail or rejected with a busy signal when the call's target user is on the phone.</span></span> <span data-ttu-id="55274-149">取り込み中オプションは、2016 年 7 月の累積的な更新プログラムで導入された新しい音声ポリシーです。</span><span class="sxs-lookup"><span data-stu-id="55274-149">Busy Options is a new voice policy introduced in the July 2016 Cumulative Update.</span></span> <span data-ttu-id="55274-150">このパラメーターをオンにすると、取り込み中オプションが有効になり、オフライン デポにすると取り込み中オプションが無効になります。</span><span class="sxs-lookup"><span data-stu-id="55274-150">Checking this parameter enables Busy Options, and unchecking it disables Busy Options.</span></span> <span data-ttu-id="55274-151">詳細については、 [Skype のビジネス サーバーのビジー状態のオプションの計画](../../plan-your-deployment/enterprise-voice-solution/busy-options.md)を参照してくださいと[をインストールし、Skype のビジネス サーバーのビジー状態のオプションを構成する](install-and-configure-busy-options.md)です。</span><span class="sxs-lookup"><span data-stu-id="55274-151">For more information, see [Plan for Busy Options for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/busy-options.md) and [Install and configure Busy Options for Skype for Business Server](install-and-configure-busy-options.md).</span></span>

7. <span data-ttu-id="55274-152">この音声ポリシーの PSTN 使用法レコードの関連付けと構成を行うには、次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="55274-152">To associate and configure PSTN usage records for this voice policy, do any of the following:</span></span>

   - <span data-ttu-id="55274-p114">エンタープライズ VoIP 展開で利用できるすべての PSTN 使用法レコードの一覧から、1 つ以上のレコードを選択するには、[**選択**] をクリックします。この音声ポリシーに関連付けるレコードを選択状態にし、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55274-p114">To choose one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**. Highlight the records that you want to associate with this voice policy, and then click **OK**.</span></span>

   - <span data-ttu-id="55274-155">PSTN 使用法レコードをこの音声ポリシーから削除するには、レコードを選択状態にして [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55274-155">To remove a PSTN usage record from this voice policy, highlight the record and click **Remove**.</span></span>

   - <span data-ttu-id="55274-156">新しい PSTN 使用法レコードを定義してこの音声ポリシーに関連付けるには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="55274-156">To define a new PSTN usage record and associate it with this voice policy, do the following:</span></span>

    <span data-ttu-id="55274-157">a.</span><span class="sxs-lookup"><span data-stu-id="55274-157">a.</span></span> <span data-ttu-id="55274-158">[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55274-158">Click **New**.</span></span>

    <span data-ttu-id="55274-159">b.</span><span class="sxs-lookup"><span data-stu-id="55274-159">b.</span></span> <span data-ttu-id="55274-160">"**名前**" フィールドに、レコードを説明する一意の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="55274-160">In the **Name** field, enter a unique descriptive name for the record.</span></span> <span data-ttu-id="55274-161">などの正社員が臨時社員のレッドモンド、および他の namedRedmondTemps にあるため、PSTN 使用法レコードの namedRedmond を作成することがあります。</span><span class="sxs-lookup"><span data-stu-id="55274-161">For example, you may want to create a PSTN usage record namedRedmond for full-time employees located in Redmond, and another namedRedmondTemps for temporary employees.</span></span>

    > [!NOTE]
    > <span data-ttu-id="55274-p117">PSTN 使用法レコードの名前は、エンタープライズ VoIP 展開内で一意である必要があります。レコードの保存後、"**名前**" フィールドを編集することはできません。</span><span class="sxs-lookup"><span data-stu-id="55274-p117">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the **Name** field cannot be edited.</span></span>

    <span data-ttu-id="55274-164">c.</span><span class="sxs-lookup"><span data-stu-id="55274-164">c.</span></span> <span data-ttu-id="55274-165">次のいずれかの方法を使用して、この PSTN 使用法レコードのルートの関連付けと構成を行います。</span><span class="sxs-lookup"><span data-stu-id="55274-165">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>

   - <span data-ttu-id="55274-166">エンタープライズ VoIP 展開で利用できるすべてのルートの一覧から、1 つ以上のルートを選択するには、[**選択**] をクリックし、この PSTN 使用法レコードに関連付けるルートを選択状態にして、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55274-166">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>

   - <span data-ttu-id="55274-167">PSTN 使用法レコードからルートを削除するには、ルートを選択状態にして [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55274-167">To remove a route from the PSTN usage record, highlight the route, and then click **Remove**.</span></span>

   - <span data-ttu-id="55274-168">新しいルートを定義してこの PSTN 使用法レコードに関連付けるには、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55274-168">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="55274-169">詳細についてを参照してください[を作成するまたはビジネス用の Skype でのボイス ルートを変更する](create-or-modify-a-voice-route.md)です。</span><span class="sxs-lookup"><span data-stu-id="55274-169">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

   - <span data-ttu-id="55274-170">この PSTN 使用法レコードに既に関連付けられているルートを編集するには、ルートを選択状態にして [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55274-170">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span>

    <span data-ttu-id="55274-171">d.</span><span class="sxs-lookup"><span data-stu-id="55274-171">d.</span></span> <span data-ttu-id="55274-172">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55274-172">Click **OK**.</span></span>

   - <span data-ttu-id="55274-173">この音声ポリシーに既に関連付けられている PSTN 使用法レコードを編集するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="55274-173">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>

    <span data-ttu-id="55274-174">a.</span><span class="sxs-lookup"><span data-stu-id="55274-174">a.</span></span> <span data-ttu-id="55274-175">編集する PSTN 使用法レコードを選択状態にし、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55274-175">Highlight the PSTN usage record that you want to edit, and then click **Show details**.</span></span>

    <span data-ttu-id="55274-176">b.</span><span class="sxs-lookup"><span data-stu-id="55274-176">b.</span></span> <span data-ttu-id="55274-177">次のいずれかの方法を使用して、この PSTN 使用法レコードのルートの関連付けと構成を行います。</span><span class="sxs-lookup"><span data-stu-id="55274-177">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>

   - <span data-ttu-id="55274-178">エンタープライズ VoIP 展開で利用できるすべてのルートの一覧から、1 つ以上のルートを選択するには、[**選択**] をクリックし、この PSTN 使用法レコードに関連付けるルートを選択状態にして、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55274-178">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes you want to associate with this PSTN usage record, and then click **OK**.</span></span>

   - <span data-ttu-id="55274-179">この PSTN 使用法レコードからルートを削除するには、ルートを選択状態にして [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55274-179">To remove a route from this PSTN usage record, highlight the route, and then click **Remove**.</span></span>

   - <span data-ttu-id="55274-180">新しいルートを定義してこの PSTN 使用法レコードに関連付けるには、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55274-180">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="55274-181">詳細についてを参照してください[を作成するまたはビジネス用の Skype でのボイス ルートを変更する](create-or-modify-a-voice-route.md)です。</span><span class="sxs-lookup"><span data-stu-id="55274-181">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

   - <span data-ttu-id="55274-182">この PSTN 使用法レコードに既に関連付けられているルートを編集するには、ルートを選択状態にして [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55274-182">To edit a route that is already associated with this PSTN usage record, highlight the route and lick **Show details**.</span></span>

    <span data-ttu-id="55274-183">c.</span><span class="sxs-lookup"><span data-stu-id="55274-183">c.</span></span> <span data-ttu-id="55274-184">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55274-184">Click **OK**.</span></span>

8. <span data-ttu-id="55274-185">最適なパフォーマンスを得るために、PSTN 使用法レコードを並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="55274-185">Arrange the PSTN usage records for optimum performance.</span></span> <span data-ttu-id="55274-186">リスト内のレコードの位置を変更するには、レコード名を強調表示しをクリックして印または下矢印。</span><span class="sxs-lookup"><span data-stu-id="55274-186">To change a record's position in the list, highlight the record name and click the up or down arrow.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="55274-187">ボイス ポリシーでどの PSTN の使用法レコードが表示されている順序では、重要です。</span><span class="sxs-lookup"><span data-stu-id="55274-187">The order in which PSTN usage records are listed in the voice policy is significant.</span></span> <span data-ttu-id="55274-188">Skype ビジネス サーバーのダウン、上からリストを走査します。</span><span class="sxs-lookup"><span data-stu-id="55274-188">Skype for Business Server traverses the list from the top down.</span></span> <span data-ttu-id="55274-189">たとえば使用頻度によってリストを整理することをお勧めします。 RedmondLocal、RedmondLongDist、RedmondInternational、RedmondBackup。</span><span class="sxs-lookup"><span data-stu-id="55274-189">We recommend that you organize the list by frequency of use, for example: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span></span>

9. <span data-ttu-id="55274-190">この音声ポリシーの着信転送および同時呼び出しの PSTN 使用法レコードの関連付けと構成を行うには、次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="55274-190">To associate and configure PSTN usage records for call forwarding and simultaneous ringing in this voice policy, do any of the following:</span></span>

   - <span data-ttu-id="55274-191">この音声ポリシーのように着信の転送および同時呼び出しに対して同じ PSTN 使用法レコードを使用するには、ドロップダウン メニューから [**呼び出し PSTN 使用法を使用したルーティング**] オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="55274-191">To use the same PSTN usage records for call forwarding and simultaneous ringing as this voice policy, select the option **Route using the call PSTN usages** from the drop-down menu.</span></span>

   - <span data-ttu-id="55274-192">着信の転送と内部の Skype ビジネス ユーザー向けに同時呼び出しを許可するには、ドロップ ダウン メニューから**内部の Skype のビジネス ・ ユーザーのみへのルート**のオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="55274-192">To allow call forwarding and simultaneous ringing to internal Skype for Business users only, select the option **Route to internal Skype for Business users only** from the drop-down menu.</span></span> <span data-ttu-id="55274-193">着信は、外部 PSTN 番号に転送されません。</span><span class="sxs-lookup"><span data-stu-id="55274-193">Calls will not be forwarded to external PSTN numbers.</span></span>

   - <span data-ttu-id="55274-p128">着信の転送および同時呼び出しに対して、この音声ポリシーでの使用とは異なる PSTN 使用法レコードを指定するには、ドロップダウン メニューから [**カスタムの PSTN 使用法を使用したルーティング**] オプションを選択します。このオプションでは、既存の PSTN 使用法レコードを選択するか、または着信の転送および同時呼び出し用の特別な新しい PSTN 使用法レコードを作成するコントロールが表示されます。</span><span class="sxs-lookup"><span data-stu-id="55274-p128">To specify different PSTN usage records for call forwarding and simultaneous ringing than used for this voice policy, select the option **Route using custom PSTN usages** from the drop-down menu. This option displays a control to select existing PSTN usage records or create new PSTN usage records specifically for call forwarding and simultaneous ringing.</span></span>

   - <span data-ttu-id="55274-p129">着信の転送および同時呼び出しの PSTN 使用法レコードの一覧から、1 つ以上のレコードを選択するには、[**選択**] をクリックします。この着信の転送および同時呼び出しポリシーに関連付けるレコードを選択状態にし、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55274-p129">To choose one or more records from a list of PSTN usage records for call forwarding and simultaneous ringing, click **Select**. Highlight the records that you want to associate with this call forwarding and simultaneous ringing policy, and then click **OK**.</span></span>

   - <span data-ttu-id="55274-198">PSTN 使用法レコードをこの着信の転送および同時呼び出しポリシーから削除するには、レコードを選択状態にして [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55274-198">To remove a PSTN usage record from this call forwarding and simultaneous ringing policy, highlight the record and click **Remove**.</span></span>

   - <span data-ttu-id="55274-199">新しい PSTN 使用法レコードを定義してこの着信の転送および同時呼び出しポリシーに関連付けるには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="55274-199">To define a new PSTN usage record and associate it with this call forwarding and simultaneous ringing policy, do the following:</span></span>

    <span data-ttu-id="55274-200">a.</span><span class="sxs-lookup"><span data-stu-id="55274-200">a.</span></span> <span data-ttu-id="55274-201">[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55274-201">Click **New**.</span></span>

    <span data-ttu-id="55274-202">b.</span><span class="sxs-lookup"><span data-stu-id="55274-202">b.</span></span> <span data-ttu-id="55274-203">"**名前**" フィールドに、レコードを説明する一意の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="55274-203">In the **Name** field, enter a unique descriptive name for the record.</span></span>

    > [!NOTE]
    > <span data-ttu-id="55274-p132">PSTN 使用法レコードの名前は、エンタープライズ VoIP 展開内で一意である必要があります。レコードの保存後、"**名前**" フィールドを編集することはできません。</span><span class="sxs-lookup"><span data-stu-id="55274-p132">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the **Name** field cannot be edited.</span></span>

    <span data-ttu-id="55274-206">c.</span><span class="sxs-lookup"><span data-stu-id="55274-206">c.</span></span> <span data-ttu-id="55274-207">次のいずれかの方法を使用して、この PSTN 使用法レコードのルートの関連付けと構成を行います。</span><span class="sxs-lookup"><span data-stu-id="55274-207">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>

   - <span data-ttu-id="55274-208">エンタープライズ VoIP 展開で利用できるすべてのルートの一覧から、1 つ以上のルートを選択するには、[**選択**] をクリックし、この PSTN 使用法レコードに関連付けるルートを選択状態にして、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55274-208">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>

   - <span data-ttu-id="55274-209">PSTN 使用法レコードからルートを削除するには、ルートを選択状態にして [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55274-209">To remove a route from the PSTN usage record, highlight the route and click **Remove**.</span></span>

   - <span data-ttu-id="55274-210">新しいルートを定義してこの PSTN 使用法レコードに関連付けるには、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55274-210">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="55274-211">詳細についてを参照してください[を作成するまたはビジネス用の Skype でのボイス ルートを変更する](create-or-modify-a-voice-route.md)です。</span><span class="sxs-lookup"><span data-stu-id="55274-211">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

   - <span data-ttu-id="55274-212">この PSTN 使用法レコードに既に関連付けられているルートを編集するには、ルートを選択状態にして [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55274-212">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span>

    <span data-ttu-id="55274-213">d.</span><span class="sxs-lookup"><span data-stu-id="55274-213">d.</span></span> <span data-ttu-id="55274-214">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55274-214">Click **OK**.</span></span>

   - <span data-ttu-id="55274-215">この音声ポリシーに既に関連付けられている PSTN 使用法レコードを編集するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="55274-215">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>

    <span data-ttu-id="55274-216">a.</span><span class="sxs-lookup"><span data-stu-id="55274-216">a.</span></span> <span data-ttu-id="55274-217">編集する PSTN 使用法レコードを選択状態にし、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55274-217">Highlight the PSTN usage record you want to edit and click **Show details**.</span></span>

    <span data-ttu-id="55274-218">b.</span><span class="sxs-lookup"><span data-stu-id="55274-218">b.</span></span> <span data-ttu-id="55274-219">次のいずれかの方法を使用して、この PSTN 使用法レコードのルートの関連付けと構成を行います。</span><span class="sxs-lookup"><span data-stu-id="55274-219">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>

   - <span data-ttu-id="55274-220">エンタープライズ VoIP 展開で利用できるすべてのルートの一覧から、1 つ以上のルートを選択するには、[**選択**] をクリックし、この PSTN 使用法レコードに関連付けるルートを選択状態にして、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55274-220">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>

   - <span data-ttu-id="55274-221">この PSTN 使用法レコードからルートを削除するには、ルートを選択状態にして [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55274-221">To remove a route from this PSTN usage record, highlight the route and click **Remove**.</span></span>

   - <span data-ttu-id="55274-222">新しいルートを定義してこの PSTN 使用法レコードに関連付けるには、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55274-222">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="55274-223">詳細についてを参照してください[を作成するまたはビジネス用の Skype でのボイス ルートを変更する](create-or-modify-a-voice-route.md)です。</span><span class="sxs-lookup"><span data-stu-id="55274-223">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

   - <span data-ttu-id="55274-224">この PSTN 使用法レコードに既に関連付けられているルートを編集するには、ルートを選択状態にして [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55274-224">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span>

    <span data-ttu-id="55274-225">c.</span><span class="sxs-lookup"><span data-stu-id="55274-225">c.</span></span> <span data-ttu-id="55274-226">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55274-226">Click **OK**.</span></span>

10. <span data-ttu-id="55274-p140">(オプション) 音声ポリシーをテストする番号を入力して、[**実行**] をクリックします。テスト結果は、[**テストする変換後の番号**] の下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="55274-p140">(Optional) Enter a number to test the voice policy and click **Go**. The test results are displayed under **Translated number to test**.</span></span>

11. <span data-ttu-id="55274-229">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55274-229">Click **OK**.</span></span>

12. <span data-ttu-id="55274-230">[**音声ポリシー**] ページで [**確定**] をクリックし、[**すべて確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55274-230">On the **Voice Policy** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="55274-231">音声ポリシーを作成または変更したときは常に、[**すべて確定**] コマンドを実行して、構成の変更を公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="55274-231">Any time you create or modify a voice policy, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="55274-232">詳細については、操作マニュアルの[発行保留中のビジネス用の Skype で音声ルーティング構成の変更](voice-route-config-changes.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="55274-232">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

13. <span data-ttu-id="55274-233">(省略可能)ボイスメール エスケープは、呼び出しがユーザーの携帯電話ボイス ・ メールに応答した直後にし、携帯電話のボイス メールの呼び出しの切断を検出します。</span><span class="sxs-lookup"><span data-stu-id="55274-233">(Optional) Voicemail Escape detects that a call was immediately answered by the user's mobile phone voice mail, and disconnects the call to the mobile phone voice mail.</span></span> <span data-ttu-id="55274-234">これにより、呼び出しを続行するのにはユーザーのリングはの他のエンドポイントの呼び出しに応答する機会をユーザーに提供します。</span><span class="sxs-lookup"><span data-stu-id="55274-234">This allows the call to continue to ring on the user's other endpoints giving the user the opportunity to answer the call.</span></span> <span data-ttu-id="55274-235">ボイス メール ポリシーを構成する方法の詳細については、[ビジネス用の Skype でボイス メール エスケープを構成する](configure-voice-mail-escape.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="55274-235">For details on how to configure a voice mail policy, see [Configure voice mail escape in Skype for Business](configure-voice-mail-escape.md).</span></span>

### <a name="to-modify-a-voice-policy"></a><span data-ttu-id="55274-236">音声ポリシーを変更するには</span><span class="sxs-lookup"><span data-stu-id="55274-236">To modify a voice policy</span></span>

1. <span data-ttu-id="55274-237">Skype をビジネス サーバーのコントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="55274-237">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="55274-238">左側のナビゲーション バーで [**音声のルーティング**] をクリックし、[**音声ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55274-238">In the left navigation bar, click **Voice Routing**, and then click **Voice Policy**.</span></span>

3. <span data-ttu-id="55274-239">[**音声ポリシー**] ページで、音声ポリシー名をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="55274-239">On the **Voice Policy** page, double-click a voice policy name.</span></span>

    > [!NOTE]
    > <span data-ttu-id="55274-p143">スコープと名前は、音声ポリシーの作成時に設定されています。これらは変更できません。</span><span class="sxs-lookup"><span data-stu-id="55274-p143">The scope and name were set when the voice policy was created. They cannot be changed.</span></span>

4. <span data-ttu-id="55274-242">(オプション) [**音声ポリシーの編集**] に、音声ポリシーの説明情報を追加で入力します。</span><span class="sxs-lookup"><span data-stu-id="55274-242">(Optional) In **Edit Voice Policy**, enter additional descriptive information for the voice policy.</span></span>

5. <span data-ttu-id="55274-243">次のチェック ボックスをオンまたはオフにして、[**通話機能**] をそれぞれ有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="55274-243">Select or clear the following check boxes to enable or disable each of the **Calling features**:</span></span>

   - <span data-ttu-id="55274-244">**ボイス メールのエスケープ**には、同時呼び出しを構成し、携帯電話がオフ、バッテリ、または範囲外になっている場合にユーザーの携帯電話のボイス メール システムにすぐにルーティングされてからの呼び出しができなくなります。</span><span class="sxs-lookup"><span data-stu-id="55274-244">**Voice mail escape** prevents calls from being immediately routed to the user's mobile phone voice mail system when simultaneous ringing is configured and the phone is turned off, out of battery, or out of range.</span></span>

    > [!NOTE]
    > <span data-ttu-id="55274-245">この機能はビジネス サーバー管理シェルの Skype 経由で構成可能なだけです。</span><span class="sxs-lookup"><span data-stu-id="55274-245">This feature is only configurable through the Skype for Business Server Management Shell</span></span>

   - <span data-ttu-id="55274-246">[**着信の転送**] を使用すると、着信を他の電話機またはクライアント デバイスに転送できます。</span><span class="sxs-lookup"><span data-stu-id="55274-246">**Call forwarding** enables users to forward calls to other phones and client devices.</span></span> <span data-ttu-id="55274-247">ビジネス サーバー用の Skype は、非常に広範囲の着信の転送の構成オプションを提供します。</span><span class="sxs-lookup"><span data-stu-id="55274-247">Skype for Business Server provides a significantly wider range of configuration options for call forwarding.</span></span> <span data-ttu-id="55274-248">たとえば、着信が外部で PSTN に転送されることを組織が許可しない方針の場合、管理者は特殊な音声ポリシーを適用して、この制限を展開することができます。</span><span class="sxs-lookup"><span data-stu-id="55274-248">For example, if an organization does not want to allow incoming calls to be forwarded externally to the PSTN, an administrator can apply a special voice policy to deploy this restriction.</span></span> <span data-ttu-id="55274-249">既定では有効です。</span><span class="sxs-lookup"><span data-stu-id="55274-249">Enabled by default.</span></span>

   - <span data-ttu-id="55274-250">[**委任**] では、代わりに通話を送受信する他のユーザーを指定できます。</span><span class="sxs-lookup"><span data-stu-id="55274-250">**Delegation** enables users to specify other users to send and receive calls on their behalf.</span></span> <span data-ttu-id="55274-251">ビジネス サーバーの Skype は、[同時呼び出しにより、すべての代理人の同時着信ターゲット リングに自分のマネージャーに着信するデリゲートを構成できます。</span><span class="sxs-lookup"><span data-stu-id="55274-251">In Skype for Business Server, a delegate can configure simultaneous ringing that enables incoming calls to his or her manager to ring all of the delegate's simultaneous ringing targets.</span></span> <span data-ttu-id="55274-252">これは、管理者宛ての呼び出しに応答するために柔軟性の高いデリゲートを提供します。</span><span class="sxs-lookup"><span data-stu-id="55274-252">This provides the delegate with greater flexibility in responding to calls directed to the manager.</span></span> <span data-ttu-id="55274-253">既定では有効です。</span><span class="sxs-lookup"><span data-stu-id="55274-253">Enabled by default.</span></span>

   - <span data-ttu-id="55274-p146">[**通話の転送**] では、他のユーザーに通話を転送できます。既定では有効です。</span><span class="sxs-lookup"><span data-stu-id="55274-p146">**Call transfer** enables users to transfer calls to other users. Enabled by default.</span></span>

   - <span data-ttu-id="55274-p147">[**コール パーク**] では、通話を保留 (パーク) し、別の電話機やクライアントで受けることができます。既定では無効です。</span><span class="sxs-lookup"><span data-stu-id="55274-p147">**Call park** enables users to park calls on hold, and then pick up the call from a different phone or client. Disabled by default.</span></span>

   - <span data-ttu-id="55274-258">[**同時呼び出し**] では、追加の電話機 (携帯電話など) や他のエンドポイント デバイスで、着信の呼び出し音を鳴らすことができます。</span><span class="sxs-lookup"><span data-stu-id="55274-258">**Simultaneous ringing** enables incoming calls to ring on additional phones (for example, a mobile phone) or other endpoint devices.</span></span> <span data-ttu-id="55274-259">ビジネス サーバー用の Skype は、非常に広範囲の同時呼び出しの構成オプションを提供します。</span><span class="sxs-lookup"><span data-stu-id="55274-259">Skype for Business Server provides a significantly wider range of configuration options for simultaneous ringing.</span></span> <span data-ttu-id="55274-260">既定では有効です。</span><span class="sxs-lookup"><span data-stu-id="55274-260">Enabled by default.</span></span>

   - <span data-ttu-id="55274-p149">[**チーム呼び出し**] では、定義したチームのユーザーがチームの他のメンバーの呼び出しに応答できます。既定では有効です。</span><span class="sxs-lookup"><span data-stu-id="55274-p149">**Team call** enables users on a defined team to answer calls for other members of the team. Enabled by default.</span></span>

   - <span data-ttu-id="55274-p150">[**PSTN 再ルート**] では、WAN が混雑していたり利用できなかったりする場合に、このポリシーを割り当てられているユーザーが他のエンタープライズ ユーザーにかけた通話を、PSTN で再ルートできます。既定では有効です。</span><span class="sxs-lookup"><span data-stu-id="55274-p150">**PSTN re-route** enables calls made by users who are assigned this policy to other enterprise users to be rerouted on the PSTN if the WAN is congested or unavailable. Enabled by default.</span></span>

   - <span data-ttu-id="55274-p151">[\*\*帯域幅ポリシーの上書き \*\*] により管理者は、特定のユーザーに関する CAC ポリシーによる決定を上書きできます。既定では無効です。</span><span class="sxs-lookup"><span data-stu-id="55274-p151">**Bandwidth policy override** enables administrators to override CAC policy decisions for a particular user. Disabled by default.</span></span>

     > [!NOTE]
     > <span data-ttu-id="55274-p152">ポリシーが上書きされるのはユーザーに着信する通話のみです。ユーザーが発信する通話は上書きされません。セッションの確立後、使用帯域幅は正確に記録されます。この設定は慎重に使用してください。</span><span class="sxs-lookup"><span data-stu-id="55274-p152">The policy will be overridden only for incoming calls to the user and not for outgoing calls that are placed by the user. After the session is established, the bandwidth consumption will be accurately recorded. This setting should be used sparingly.</span></span>

   - <span data-ttu-id="55274-p153">[**悪意のある呼び出しのトレース**] では、ユーザーがクライアントの UI を使用して、悪意のある呼び出し (脅迫など) を報告できます。報告されると、CDR 内のその呼び出しにフラグが付けられます。既定では無効です。</span><span class="sxs-lookup"><span data-stu-id="55274-p153">**Malicious call tracing** enables users to report malicious calls (such as threats) using the client UI, which in turn flags the calls in the CDRs. Disabled by default.</span></span>

6. <span data-ttu-id="55274-272">この音声ポリシーの PSTN 使用法レコードの関連付けと構成を行うには、次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="55274-272">To associate and configure PSTN usage records for this voice policy, do any of the following:</span></span>

   - <span data-ttu-id="55274-p154">エンタープライズ VoIP 展開で利用できるすべての PSTN 使用法レコードの一覧から、1 つ以上のレコードを選択するには、[**選択**] をクリックします。この音声ポリシーに関連付けるレコードを選択状態にし、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55274-p154">To choose one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**. Highlight the records that you want to associate with this voice policy, and then click **OK**.</span></span>

   - <span data-ttu-id="55274-275">PSTN 使用法レコードをこの音声ポリシーから削除するには、レコードを選択状態にして [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55274-275">To remove a PSTN usage record from this voice policy, highlight the record and click **Remove**.</span></span>

   - <span data-ttu-id="55274-276">新しい PSTN 使用法レコードを定義してこの音声ポリシーに関連付けるには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="55274-276">To define a new PSTN usage record and associate it with this voice policy, do the following:</span></span>

    <span data-ttu-id="55274-277">a.</span><span class="sxs-lookup"><span data-stu-id="55274-277">a.</span></span> <span data-ttu-id="55274-278">[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55274-278">Click **New**.</span></span>

    <span data-ttu-id="55274-279">b.</span><span class="sxs-lookup"><span data-stu-id="55274-279">b.</span></span> <span data-ttu-id="55274-280">"**名前**" フィールドに、レコードを説明する一意の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="55274-280">In the **Name** field, enter a unique descriptive name for the record.</span></span> <span data-ttu-id="55274-281">などの正社員が臨時社員のレッドモンド、および別のレコードの namedRedmondTemps にあるため、PSTN 使用法レコードの namedRedmond を作成することがあります。</span><span class="sxs-lookup"><span data-stu-id="55274-281">For example, you may want to create a PSTN usage record namedRedmond for full-time employees located in Redmond, and another record namedRedmondTemps for temporary employees.</span></span>

    > [!NOTE]
    > <span data-ttu-id="55274-p157">PSTN 使用法レコードの名前は、エンタープライズ VoIP 展開内で一意である必要があります。レコードの保存後、"**名前**" フィールドを編集することはできません。</span><span class="sxs-lookup"><span data-stu-id="55274-p157">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the **Name** field cannot be edited.</span></span>

    <span data-ttu-id="55274-284">c.</span><span class="sxs-lookup"><span data-stu-id="55274-284">c.</span></span> <span data-ttu-id="55274-285">次のいずれかの方法を使用して、この PSTN 使用法レコードのルートの関連付けと構成を行います。</span><span class="sxs-lookup"><span data-stu-id="55274-285">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>

   - <span data-ttu-id="55274-286">エンタープライズ VoIP 展開で利用できるすべてのルートの一覧から、1 つ以上のルートを選択するには、[**選択**] をクリックし、この PSTN 使用法レコードに関連付けるルートを選択状態にして、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55274-286">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>

   - <span data-ttu-id="55274-287">PSTN 使用法レコードからルートを削除するには、ルートを選択状態にして [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55274-287">To remove a route from the PSTN usage record, highlight the route and click **Remove**.</span></span>

   - <span data-ttu-id="55274-288">新しいルートを定義してこの PSTN 使用法レコードに関連付けるには、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55274-288">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="55274-289">詳細についてを参照してください[を作成するまたはビジネス用の Skype でのボイス ルートを変更する](create-or-modify-a-voice-route.md)です。</span><span class="sxs-lookup"><span data-stu-id="55274-289">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

   - <span data-ttu-id="55274-290">この PSTN 使用法レコードに既に関連付けられているルートを編集するには、ルートを選択状態にして [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55274-290">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span>

    <span data-ttu-id="55274-291">d.</span><span class="sxs-lookup"><span data-stu-id="55274-291">d.</span></span> <span data-ttu-id="55274-292">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55274-292">Click **OK**.</span></span>

   - <span data-ttu-id="55274-293">この音声ポリシーに既に関連付けられている PSTN 使用法レコードを編集するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="55274-293">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>

    <span data-ttu-id="55274-294">a.</span><span class="sxs-lookup"><span data-stu-id="55274-294">a.</span></span> <span data-ttu-id="55274-295">編集する PSTN 使用法レコードを選択状態にし、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55274-295">Highlight the PSTN usage record that you want to edit and click **Show details**.</span></span>

    <span data-ttu-id="55274-296">b.</span><span class="sxs-lookup"><span data-stu-id="55274-296">b.</span></span> <span data-ttu-id="55274-297">次のいずれかの方法を使用して、この PSTN 使用法レコードのルートの関連付けと構成を行います。</span><span class="sxs-lookup"><span data-stu-id="55274-297">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>

   - <span data-ttu-id="55274-298">エンタープライズ VoIP 展開で利用できるすべてのルートの一覧から、1 つ以上のルートを選択するには、[**選択**] をクリックし、この PSTN 使用法レコードに関連付けるルートを選択状態にして、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55274-298">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>

   - <span data-ttu-id="55274-299">この PSTN 使用法レコードからルートを削除するには、ルートを選択状態にして [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55274-299">To remove a route from this PSTN usage record, highlight the route and click **Remove**.</span></span>

   - <span data-ttu-id="55274-300">新しいルートを定義してこの PSTN 使用法レコードに関連付けるには、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55274-300">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="55274-301">詳細についてを参照してください[を作成するまたはビジネス用の Skype でのボイス ルートを変更する](create-or-modify-a-voice-route.md)です。</span><span class="sxs-lookup"><span data-stu-id="55274-301">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

   - <span data-ttu-id="55274-302">この PSTN 使用法レコードに既に関連付けられているルートを編集するには、ルートを選択状態にして [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55274-302">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span>

    <span data-ttu-id="55274-303">c.</span><span class="sxs-lookup"><span data-stu-id="55274-303">c.</span></span> <span data-ttu-id="55274-304">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55274-304">Click **OK**.</span></span>

7. <span data-ttu-id="55274-305">最適なパフォーマンスを得るために、PSTN 使用法レコードを並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="55274-305">Arrange the PSTN usage records for optimum performance.</span></span> <span data-ttu-id="55274-306">リスト内のレコードの位置を変更するには、レコード名を強調表示しをクリックして印または下矢印。</span><span class="sxs-lookup"><span data-stu-id="55274-306">To change a record's position in the list, highlight the record name and click the up or down arrow.</span></span>

    > [!NOTE]
    > <span data-ttu-id="55274-307">ボイス ポリシーでどの PSTN の使用法レコードが表示されている順序では、重要です。</span><span class="sxs-lookup"><span data-stu-id="55274-307">The order in which PSTN usage records are listed in the voice policy is significant.</span></span> <span data-ttu-id="55274-308">Skype ビジネス サーバーのダウン、上からリストを走査します。</span><span class="sxs-lookup"><span data-stu-id="55274-308">Skype for Business Server traverses the list from the top down.</span></span> <span data-ttu-id="55274-309">たとえば使用頻度によってリストを整理することをお勧めします。 RedmondLocal、RedmondLongDist、RedmondInternational、RedmondBackup。</span><span class="sxs-lookup"><span data-stu-id="55274-309">We recommend that you organize the list by frequency of use, for example: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span></span>

8. <span data-ttu-id="55274-310">この音声ポリシーの着信転送および同時呼び出しの PSTN 使用法レコードの関連付けと構成を行うには、次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="55274-310">To associate and configure PSTN usage records for call forwarding and simultaneous ringing in this voice policy, do any of the following:</span></span>

   - <span data-ttu-id="55274-311">この音声ポリシーのように着信の転送および同時呼び出しに対して同じ PSTN 使用法レコードを使用するには、ドロップダウン メニューから [**呼び出し PSTN 使用法を使用したルーティング**] オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="55274-311">To use the same PSTN usage records for call forwarding and simultaneous ringing as this voice policy, select the option **Route using the call PSTN usages** from the drop-down menu.</span></span>

   - <span data-ttu-id="55274-312">着信の転送と内部の Skype ビジネス ユーザー向けに同時呼び出しを許可するには、ドロップ ダウン メニューから**内部の Skype のビジネス ・ ユーザーのみへのルート**を選択します。</span><span class="sxs-lookup"><span data-stu-id="55274-312">To allow call forwarding and simultaneous ringing to internal Skype for Business users only, select **Route to internal Skype for Business users only** from the drop-down menu.</span></span> <span data-ttu-id="55274-313">着信は、外部 PSTN 番号に転送されません。</span><span class="sxs-lookup"><span data-stu-id="55274-313">Calls will not be forwarded to external PSTN numbers.</span></span>

   - <span data-ttu-id="55274-p168">この音声ポリシーに使用されているのとは別の PTSN 使用法レコードを着信の転送と同時呼び出しに指定する場合は、ドロップダウン メニューから [**カスタムの PSTN 使用法を使用したルーティング**] を選択します。このオプションを選択するとコントロールが表示され、着信の転送と同時呼び出しに対して、既存の PSTN 使用法レコードを選択するかまたは新しい PSTN 使用法レコードを作成できます。</span><span class="sxs-lookup"><span data-stu-id="55274-p168">To specify different PSTN usage records for call forwarding and simultaneous ringing than those used for this voice policy, select the option **Route using custom PSTN usages** from the drop-down menu. This option displays a control to select existing PSTN usage records or to create new PSTN usage records, specifically for call forwarding and simultaneous ringing.</span></span>

   - <span data-ttu-id="55274-p169">着信の転送および同時呼び出しの PSTN 使用法レコードの一覧から、1 つ以上のレコードを選択するには、[**選択**] をクリックします。この着信の転送および同時呼び出しポリシーに関連付けるレコードを選択状態にし、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55274-p169">To choose one or more records from a list of PSTN usage records for call forwarding and simultaneous ringing, click **Select**. Highlight the records that you want to associate with this call forwarding and simultaneous ringing policy, and then click **OK**.</span></span>

   - <span data-ttu-id="55274-318">PSTN 使用法レコードをこの着信の転送および同時呼び出しポリシーから削除するには、レコードを選択状態にして [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55274-318">To remove a PSTN usage record from this call forwarding and simultaneous ringing policy, highlight the record and click **Remove**.</span></span>

   - <span data-ttu-id="55274-319">新しい PSTN 使用法レコードを定義してこの着信の転送および同時呼び出しポリシーに関連付けるには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="55274-319">To define a new PSTN usage record and associate it with this call forwarding and simultaneous ringing policy, do the following:</span></span>

    <span data-ttu-id="55274-320">a.</span><span class="sxs-lookup"><span data-stu-id="55274-320">a.</span></span> <span data-ttu-id="55274-321">[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55274-321">Click **New**.</span></span>

    <span data-ttu-id="55274-322">b.</span><span class="sxs-lookup"><span data-stu-id="55274-322">b.</span></span> <span data-ttu-id="55274-323">"**名前**" フィールドに、レコードを説明する一意の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="55274-323">In the **Name** field, enter a unique descriptive name for the record.</span></span>

    > [!NOTE]
    > <span data-ttu-id="55274-p172">PSTN 使用法レコードの名前は、エンタープライズ VoIP 展開内で一意である必要があります。レコードの保存後、"**名前**" フィールドを編集することはできません。</span><span class="sxs-lookup"><span data-stu-id="55274-p172">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the **Name** field cannot be edited.</span></span>

    <span data-ttu-id="55274-326">c.</span><span class="sxs-lookup"><span data-stu-id="55274-326">c.</span></span> <span data-ttu-id="55274-327">次のいずれかの方法を使用して、この PSTN 使用法レコードのルートの関連付けと構成を行います。</span><span class="sxs-lookup"><span data-stu-id="55274-327">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>

   - <span data-ttu-id="55274-328">エンタープライズ VoIP 展開で利用できるすべてのルートの一覧から、1 つ以上のルートを選択するには、[**選択**] をクリックし、この PSTN 使用法レコードに関連付けるルートを選択状態にして、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55274-328">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>

   - <span data-ttu-id="55274-329">PSTN 使用法レコードからルートを削除するには、ルートを選択状態にして [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55274-329">To remove a route from the PSTN usage record, highlight the route and click **Remove**.</span></span>

   - <span data-ttu-id="55274-330">新しいルートを定義してこの PSTN 使用法レコードに関連付けるには、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55274-330">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="55274-331">詳細についてを参照してください[を作成するまたはビジネス用の Skype でのボイス ルートを変更する](create-or-modify-a-voice-route.md)です。</span><span class="sxs-lookup"><span data-stu-id="55274-331">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

   - <span data-ttu-id="55274-332">この PSTN 使用法レコードに既に関連付けられているルートを編集するには、ルートを選択状態にして [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55274-332">To edit a route that is already associated with this PSTN usage record, highlight the route, and then click **Show details**.</span></span> <span data-ttu-id="55274-333">詳細については、[ボイス ルートの変更](https://technet.microsoft.com/library/afc562cc-8807-489b-8850-dbbe1c1ab9f5.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="55274-333">For details, see [Modify a Voice Route](https://technet.microsoft.com/library/afc562cc-8807-489b-8850-dbbe1c1ab9f5.aspx).</span></span>

    <span data-ttu-id="55274-334">d.</span><span class="sxs-lookup"><span data-stu-id="55274-334">d.</span></span> <span data-ttu-id="55274-335">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55274-335">Click **OK**.</span></span>

   - <span data-ttu-id="55274-336">この音声ポリシーに既に関連付けられている PSTN 使用法レコードを編集するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="55274-336">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>

     <span data-ttu-id="55274-337">a.</span><span class="sxs-lookup"><span data-stu-id="55274-337">a.</span></span> <span data-ttu-id="55274-338">編集する PSTN 使用法レコードを選択状態にし、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55274-338">Highlight the PSTN usage record that you want to edit and click **Show details**.</span></span>

     <span data-ttu-id="55274-339">b.</span><span class="sxs-lookup"><span data-stu-id="55274-339">b.</span></span> <span data-ttu-id="55274-340">次のいずれかの方法を使用して、この PSTN 使用法レコードのルートの関連付けと構成を行います。</span><span class="sxs-lookup"><span data-stu-id="55274-340">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>

     - <span data-ttu-id="55274-341">エンタープライズ VoIP 展開で利用できるすべてのルートの一覧から、1 つ以上のルートを選択するには、[**選択**] をクリックし、この PSTN 使用法レコードに関連付けるルートを選択状態にして、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55274-341">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes you want to associate with this PSTN usage record, and then click **OK**.</span></span>

     - <span data-ttu-id="55274-342">この PSTN 使用法レコードからルートを削除するには、ルートを選択状態にして [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55274-342">To remove a route from this PSTN usage record, highlight the route and click **Remove**.</span></span>

     - <span data-ttu-id="55274-343">新しいルートを定義してこの PSTN 使用法レコードに関連付けるには、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55274-343">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="55274-344">詳細についてを参照してください[を作成するまたはビジネス用の Skype でのボイス ルートを変更する](create-or-modify-a-voice-route.md)です。</span><span class="sxs-lookup"><span data-stu-id="55274-344">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

     - <span data-ttu-id="55274-345">この PSTN 使用法レコードに既に関連付けられているルートを編集するには、ルートを選択状態にして [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55274-345">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="55274-346">詳細については、[ボイス ルートの変更](https://technet.microsoft.com/library/afc562cc-8807-489b-8850-dbbe1c1ab9f5.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="55274-346">For details, see [Modify a Voice Route](https://technet.microsoft.com/library/afc562cc-8807-489b-8850-dbbe1c1ab9f5.aspx).</span></span>

     <span data-ttu-id="55274-347">c.</span><span class="sxs-lookup"><span data-stu-id="55274-347">c.</span></span> <span data-ttu-id="55274-348">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55274-348">Click **OK**.</span></span>

9. <span data-ttu-id="55274-p182">(オプション) 音声ポリシーをテストする番号を入力して、[**実行**] をクリックします。テスト結果は、[**テストする変換後の番号**] の下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="55274-p182">(Optional) Enter a number to test the voice policy and click **Go**. The test results are displayed under **Translated number to test**.</span></span>

10. <span data-ttu-id="55274-351">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55274-351">Click **OK**.</span></span>

11. <span data-ttu-id="55274-352">[**音声ポリシー**] ページで [**確定**] をクリックし、[**すべて確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55274-352">On the **Voice Policy** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="55274-353">音声ポリシーを作成または変更するときは常に、[**すべて確定**] コマンドを実行して、構成の変更を公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="55274-353">Whenever you create or modify a voice policy, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="55274-354">詳細については、操作マニュアルの[発行保留中のビジネス用の Skype で音声ルーティング構成の変更](voice-route-config-changes.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="55274-354">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

12. <span data-ttu-id="55274-355">(省略可能)ボイスメール エスケープは、呼び出しがユーザーの携帯電話ボイス ・ メールに応答した直後にし、携帯電話のボイス メールの呼び出しの切断を検出します。</span><span class="sxs-lookup"><span data-stu-id="55274-355">(Optional) Voicemail Escape detects that a call was immediately answered by the user's mobile phone voice mail, and disconnects the call to the mobile phone voice mail.</span></span> <span data-ttu-id="55274-356">これにより、呼び出しを続行するのにはユーザーのリングはの他のエンドポイントの呼び出しに応答する機会をユーザーに提供します。</span><span class="sxs-lookup"><span data-stu-id="55274-356">This allows the call to continue to ring on the user's other endpoints giving the user the opportunity to answer the call.</span></span> <span data-ttu-id="55274-357">ボイス メール ポリシーを構成する方法の詳細については、[ビジネス用の Skype でボイス メール エスケープを構成する](configure-voice-mail-escape.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="55274-357">For details about how to configure a voice mail policy, see [Configure voice mail escape in Skype for Business](configure-voice-mail-escape.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="55274-358">関連項目</span><span class="sxs-lookup"><span data-stu-id="55274-358">See also</span></span>

[<span data-ttu-id="55274-359">ビジネス用の Skype の PSTN 使用法レコードの表示</span><span class="sxs-lookup"><span data-stu-id="55274-359">View PSTN usage records in Skype for Business</span></span>](view-pstn-usage-records.md)

[<span data-ttu-id="55274-360">作成またはビジネス用の Skype でのボイス ルートを変更します。</span><span class="sxs-lookup"><span data-stu-id="55274-360">Create or modify a voice route in Skype for Business</span></span>](create-or-modify-a-voice-route.md)

[<span data-ttu-id="55274-361">発行保留中のビジネス用の Skype で音声ルーティング構成の変更</span><span class="sxs-lookup"><span data-stu-id="55274-361">Publish pending changes to the voice routing configuration in Skype for Business</span></span>](voice-route-config-changes.md)

[<span data-ttu-id="55274-362">ビジネス用の Skype でボイス メールのエスケープを構成します。</span><span class="sxs-lookup"><span data-stu-id="55274-362">Configure voice mail escape in Skype for Business</span></span>](configure-voice-mail-escape.md)

