---
title: Microsoft Teams の発信通話制限ポリシー
author: LolaJacobsen
ms.author: tonysmit
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: jastark
audience: admin
search.appverid: MET150
description: Microsoft Teams のカスタムの通話ポリシーや、さまざまな通話ポリシーの設定に対してユーザーを作成、変更、および追加する方法について説明します。
localization_priority: Normal
ms.custom:
- ms.teamsadmincenter.callingpolicies.overview
- seo-marvel-apr2020
ms.collection:
- M365-voice
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7a67952854f608512e88786c2b49d1e2ad8dfcf9
ms.sourcegitcommit: 184f4f61a3e739a1cfa533c6d95d405d887ea25d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "44592936"
---
<a name="calling-policies-in-microsoft-teams"></a><span data-ttu-id="939a9-103">Microsoft Teams の発信通話制限ポリシー</span><span class="sxs-lookup"><span data-stu-id="939a9-103">Calling policies in Microsoft Teams</span></span>
===================================

<span data-ttu-id="939a9-104">Microsoft Teams では、通話ポリシーによって、ユーザーが使用できる通話と通話転送機能が制御されます。</span><span class="sxs-lookup"><span data-stu-id="939a9-104">In Microsoft Teams, calling policies control which calling and call forwarding features are available to users.</span></span> <span data-ttu-id="939a9-105">通話ポリシーは、ユーザーがプライベートな通話を行うことができるかどうかを決定します。着信の転送や、他のユーザーや外部の電話番号への同時呼び出し、ボイスメールへの通話のルーティング、通話グループへの通話の送信、受信と発信などの呼び出しに委任を使用するなどを行います。</span><span class="sxs-lookup"><span data-stu-id="939a9-105">Calling policies determine whether a user can make private calls, use call forwarding or simultaneous ringing to other users or external phone numbers, route calls to voicemail, send calls to Call Groups, use delegation for inbound and outbound calls, and so on.</span></span> <span data-ttu-id="939a9-106">既定のグローバルポリシーは自動的に作成されますが、管理者はカスタムの通話ポリシーを作成して割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="939a9-106">A default global policy is created automatically, but admins can also create and assign custom calling policies.</span></span>

## <a name="create-a-custom-calling-policy"></a><span data-ttu-id="939a9-107">カスタム通話ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="939a9-107">Create a custom calling policy</span></span>

<span data-ttu-id="939a9-108">カスタムの通話ポリシーを作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="939a9-108">Follow these steps to create a custom calling policy.</span></span>

1. <span data-ttu-id="939a9-109">Microsoft Teams 管理センターの左のナビゲーションで、[**音声**通話のポリシー] に移動し  >  **Calling policies**ます。</span><span class="sxs-lookup"><span data-stu-id="939a9-109">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Calling policies**.</span></span>
2. <span data-ttu-id="939a9-110">[**追加**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="939a9-110">Select **Add**.</span></span>
3. <span data-ttu-id="939a9-111">通話ポリシーで使用する機能を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="939a9-111">Turn on or turn off the features that you want to use in your calling policy.</span></span>
4. <span data-ttu-id="939a9-112">着信通話をボイスメールにルーティングできるかどうかを制御するには、[**有効**] または [**ユーザー管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="939a9-112">To control whether users can route inbound calls to voicemail, select **Enabled** or **User controlled**.</span></span> <span data-ttu-id="939a9-113">ボイスメールへのルーティングを禁止するには、[**無効**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="939a9-113">To prevent routing to voicemail, select **Disabled**.</span></span>
5. <span data-ttu-id="939a9-114">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="939a9-114">Select **Save**.</span></span>

## <a name="modify-an-existing-calling-policy"></a><span data-ttu-id="939a9-115">既存の通話ポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="939a9-115">Modify an existing calling policy</span></span>

<span data-ttu-id="939a9-116">既存の通話ポリシーを変更するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="939a9-116">Follow these steps to modify an existing calling policy.</span></span>

1. <span data-ttu-id="939a9-117">Microsoft Teams 管理センターの左のナビゲーションで、[**音声**  >  **通話のポリシー**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="939a9-117">In the left navigation of the Microsoft Teams admin center, select **Voice** > **Calling policies**.</span></span>
2. <span data-ttu-id="939a9-118">変更するポリシーの横にあるをクリックし、[**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="939a9-118">Click next to the policy that you want to modify, and then select **Edit**.</span></span>
3. <span data-ttu-id="939a9-119">必要な変更を加えて、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="939a9-119">Make the changes that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-calling-policy-to-users"></a><span data-ttu-id="939a9-120">ユーザーにカスタムの通話ポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="939a9-120">Assign a custom calling policy to users</span></span>

<span data-ttu-id="939a9-121">1人のユーザーにポリシーを割り当てるには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="939a9-121">To assign a policy to one user:</span></span>

1. <span data-ttu-id="939a9-122">Microsoft Teams 管理センターの左側のナビゲーションで、**[ユーザー]** に移動してユーザーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="939a9-122">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="939a9-123">ユーザー名の左側をクリックしてユーザーを選択し、[**編集を設定する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="939a9-123">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="939a9-124">[**通話ポリシー**] で、割り当てる通話ポリシーを選択し、[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="939a9-124">Under **Calling policy**, select the calling policy you want to assign, and then click **Apply**.</span></span>

<span data-ttu-id="939a9-125">複数のユーザーに同時にポリシーを割り当てるには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="939a9-125">To assign a policy to multiple users at a time:</span></span>

1. <span data-ttu-id="939a9-126">Microsoft Teams 管理センターの左側のナビゲーションで、**[ユーザー]** に移動し、ユーザーを検索するか、表示にフィルターを適用してユーザーを表示します。</span><span class="sxs-lookup"><span data-stu-id="939a9-126">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then search for the users or filter the view to show the users you want.</span></span>
2. <span data-ttu-id="939a9-127">[**&#x2713;** (チェックマーク)] の列からユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="939a9-127">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="939a9-128">すべてのユーザーを選択するには、表の上部にある [&#x2713; (チェックマーク)] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="939a9-128">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
3. <span data-ttu-id="939a9-129">[**設定の編集**] をクリックし、必要な変更を行い、[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="939a9-129">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>  

<span data-ttu-id="939a9-130">または、次の操作も実行できます。</span><span class="sxs-lookup"><span data-stu-id="939a9-130">Or, you can also do the following:</span></span>

1. <span data-ttu-id="939a9-131">Microsoft Teams 管理センターの左のナビゲーションで、[**音声**通話のポリシー] に移動し  >  **Calling policies**ます。</span><span class="sxs-lookup"><span data-stu-id="939a9-131">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Calling policies**.</span></span>
2. <span data-ttu-id="939a9-132">ポリシー名の左側をクリックしてポリシーを選びます。</span><span class="sxs-lookup"><span data-stu-id="939a9-132">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="939a9-133">[**ユーザーを管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="939a9-133">Select **Manage users**.</span></span>
4. <span data-ttu-id="939a9-134">[**ユーザーを管理**] ウィンドウで、表示名またはユーザー名でユーザーを検索し、名前を選択して [**追加**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="939a9-134">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="939a9-135">追加するユーザーごとに、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="939a9-135">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="939a9-136">ユーザーの追加が完了したら、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="939a9-136">After you finish adding users, select **Save**.</span></span>

## <a name="calling-policy-settings"></a><span data-ttu-id="939a9-137">通話ポリシーの設定</span><span class="sxs-lookup"><span data-stu-id="939a9-137">Calling policy settings</span></span>

<span data-ttu-id="939a9-138">次に、ポリシーを呼び出すために構成できる設定を示します。</span><span class="sxs-lookup"><span data-stu-id="939a9-138">Here's the settings that you can configure for calling policies.</span></span>

### <a name="make-private-calls"></a><span data-ttu-id="939a9-139">プライベート通話をする</span><span class="sxs-lookup"><span data-stu-id="939a9-139">Make private calls</span></span>

<span data-ttu-id="939a9-140">この設定により、Teams のすべての通話機能が制御されます。</span><span class="sxs-lookup"><span data-stu-id="939a9-140">This setting controls all calling capabilities in Teams.</span></span> <span data-ttu-id="939a9-141">Teams のすべての通話機能を無効にするには、このオプションをオフにします。</span><span class="sxs-lookup"><span data-stu-id="939a9-141">Turn this off to turn off all calling functionality in Teams.</span></span>

### <a name="call-forwarding-and-simultaneous-ringing-to-people-in-your-organization"></a><span data-ttu-id="939a9-142">組織内のユーザーとの着信の転送と同時呼び出し</span><span class="sxs-lookup"><span data-stu-id="939a9-142">Call forwarding and simultaneous ringing to people in your organization</span></span>

<span data-ttu-id="939a9-143">この設定では、着信通話を他のユーザーに転送できるか、または他の人を同時に呼び出すことができるかを制御します。</span><span class="sxs-lookup"><span data-stu-id="939a9-143">This setting controls whether incoming calls can be forwarded to other users or can ring another person at the same time.</span></span> 

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a><span data-ttu-id="939a9-144">着信の転送と同時呼び出しを外部電話番号に転送する</span><span class="sxs-lookup"><span data-stu-id="939a9-144">Call forwarding and simultaneous ringing to external phone numbers</span></span>

<span data-ttu-id="939a9-145">この設定は、着信通話を外部番号に転送できるか、外部番号を同時に呼び出すことができるかを制御します。</span><span class="sxs-lookup"><span data-stu-id="939a9-145">This setting controls whether incoming calls can be forwarded to an external number or can ring an external number at the same time.</span></span>

### <a name="voicemail-is-available-for-routing-inbound-calls"></a><span data-ttu-id="939a9-146">着信通話の転送にはボイスメールが利用可能</span><span class="sxs-lookup"><span data-stu-id="939a9-146">Voicemail is available for routing inbound calls</span></span>

<span data-ttu-id="939a9-147">この設定では、着信通話をボイスメールに送信できます。</span><span class="sxs-lookup"><span data-stu-id="939a9-147">This setting enables inbound calls to be sent to voicemail.</span></span> <span data-ttu-id="939a9-148">有効なオプションは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="939a9-148">Valid options are:</span></span>

- <span data-ttu-id="939a9-149">**有効**ボイスメールは、着信通話にいつでも利用できます。</span><span class="sxs-lookup"><span data-stu-id="939a9-149">**Enabled** Voicemail is always available for inbound calls.</span></span> 
- <span data-ttu-id="939a9-150">**無効** 着信通話でボイスメールを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="939a9-150">**Disabled**  Voicemail is not available for inbound calls.</span></span> 
- <span data-ttu-id="939a9-151">**ユーザー**による制御ユーザーはボイスメールを利用できるようにするかどうかを決定できます。</span><span class="sxs-lookup"><span data-stu-id="939a9-151">**User controlled** Users can determine whether they want voicemail to be available.</span></span>

### <a name="inbound-calls-can-be-routed-to-call-groups"></a><span data-ttu-id="939a9-152">着信通話を通話グループにルーティングできる</span><span class="sxs-lookup"><span data-stu-id="939a9-152">Inbound calls can be routed to call groups</span></span> 

> [!Include [feature preview](includes/preview-feature.md)]

<span data-ttu-id="939a9-153">この設定は、着信通話を通話グループに転送できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="939a9-153">This setting controls whether incoming calls can be forwarded to a call group.</span></span>

### <a name="allow-delegation-for-inbound-and-outbound-calls"></a><span data-ttu-id="939a9-154">着信と発信の通話の委任を許可する</span><span class="sxs-lookup"><span data-stu-id="939a9-154">Allow delegation for inbound and outbound calls</span></span>

> [!Include [feature preview](includes/preview-feature.md)]

<span data-ttu-id="939a9-155">この設定を有効にすると、着信の代理人へのルーティングが許可され、代理人がアクセス権を委任したユーザーの代わりに発信通話を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="939a9-155">This setting enables inbound calls to be routed to delegates, allowing delegates to make outbound calls on behalf of the users for whom they have delegated permissions.</span></span> <span data-ttu-id="939a9-156">詳細については、「[代理人と電話回線を共有](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="939a9-156">For more information, see [Share a phone line with a delegate](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8).</span></span>

### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a><span data-ttu-id="939a9-157">通話を発信したり、PSTN 経由で通話を送信したりする</span><span class="sxs-lookup"><span data-stu-id="939a9-157">Prevent toll bypass and send calls through the PSTN</span></span> 

<span data-ttu-id="939a9-158">この設定**で**は、ネットワーク経由での送信と、tolls のバイパスではなく、PSTN 経由で通話が送信され、料金が発生します。</span><span class="sxs-lookup"><span data-stu-id="939a9-158">Setting this to **On** will send calls through the PSTN and incur charges rather than sending them through the network and bypassing the tolls.</span></span>

### <a name="busy-on-busy-is-available-while-in-a-call"></a><span data-ttu-id="939a9-159">通話中に取り込み中</span><span class="sxs-lookup"><span data-stu-id="939a9-159">Busy on Busy is available while in a call</span></span>

<span data-ttu-id="939a9-160">[取り込み中] (取り込み中) は、ユーザーが既に通話または会議に参加している場合や、通話が保留になっている場合に、着信通話の処理方法を構成できる新しい設定です。</span><span class="sxs-lookup"><span data-stu-id="939a9-160">Busy on Busy (Busy Options) is a new setting that lets you configure how incoming calls are handled when a user is already in a call or conference or has a call placed on hold.</span></span> <span data-ttu-id="939a9-161">新規または着信通話は、取り込み中の信号で拒否することができます。</span><span class="sxs-lookup"><span data-stu-id="939a9-161">New or incoming calls can be rejected with a busy signal.</span></span> <span data-ttu-id="939a9-162">[取り込み] オプションは、テナントレベルまたはユーザーレベルで有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="939a9-162">You can enable busy options at the tenant level or at the user level.</span></span> <span data-ttu-id="939a9-163">通話や電話会議のユーザー、または通話を保留しているユーザーは、会議中の通話や会議の開始を防ぐことはできません。</span><span class="sxs-lookup"><span data-stu-id="939a9-163">Regardless of how their busy options are configured, users in a call or conference or those with a call on hold are not prevented from initiating new calls or conferences.</span></span> <span data-ttu-id="939a9-164">この設定は、既定では無効になっています。</span><span class="sxs-lookup"><span data-stu-id="939a9-164">This setting is disabled by default.</span></span>

### <a name="allow-web-pstn-calling"></a><span data-ttu-id="939a9-165">Web PSTN 通話を許可する</span><span class="sxs-lookup"><span data-stu-id="939a9-165">Allow web PSTN calling</span></span>

<span data-ttu-id="939a9-166">この設定により、ユーザーは Teams web クライアントを使って PSTN 番号に通話を発信できます。</span><span class="sxs-lookup"><span data-stu-id="939a9-166">This setting enables users to call PSTN numbers using the Teams web client.</span></span>

### <a name="allow-music-on-hold"></a><span data-ttu-id="939a9-167">保留中の音楽を許可する</span><span class="sxs-lookup"><span data-stu-id="939a9-167">Allow music on hold</span></span>

<span data-ttu-id="939a9-168">この設定では、PSTN の発信者が保留になっているときに、保留中の音楽をオンまたはオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="939a9-168">This setting allows you to turn on or turn off music on hold when a PSTN caller is placed on hold.</span></span> <span data-ttu-id="939a9-169">これは既定でオンになっています。</span><span class="sxs-lookup"><span data-stu-id="939a9-169">It's turned on by default.</span></span> <span data-ttu-id="939a9-170">この設定は、コールパークと上司のデリゲート機能には適用されず、現在、PowerShell でのみ利用可能です。</span><span class="sxs-lookup"><span data-stu-id="939a9-170">This setting doesn't apply to call park and boss delegate features, and is currently only available via PowerShell.</span></span>

## <a name="see-also"></a><span data-ttu-id="939a9-171">関連項目</span><span class="sxs-lookup"><span data-stu-id="939a9-171">See also</span></span>

[<span data-ttu-id="939a9-172">Set-Csteam拡張性のポリシー</span><span class="sxs-lookup"><span data-stu-id="939a9-172">Set-CSTeamsCallingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)
