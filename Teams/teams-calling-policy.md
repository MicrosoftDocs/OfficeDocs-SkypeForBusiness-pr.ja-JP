---
title: Microsoft Teams の発信通話制限ポリシー
author: LolaJacobsen
ms.author: tonysmit
manager: serdars
ms.date: 05/06/2019
ms.topic: conceptual
ms.service: msteams
ms.reviewer: jastark
audience: admin
search.appverid: MET150
description: Microsoft Teams での通話ポリシー設定について説明します。
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
f1keywords:
- ms.teamsadmincenter.callingpolicies.overview
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2e97f16097a30172a2ea56eb7fc9808042055f0e
ms.sourcegitcommit: d4e69d46de564c445feb855cbee55954a7063bba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2019
ms.locfileid: "36483685"
---
<a name="calling-policies-in-microsoft-teams"></a><span data-ttu-id="c00c6-103">Microsoft Teams の発信通話制限ポリシー</span><span class="sxs-lookup"><span data-stu-id="c00c6-103">Calling policies in Microsoft Teams</span></span>
===================================

<span data-ttu-id="c00c6-104">Microsoft Teams では、通話ポリシーによって、ユーザーが使用できる通話と通話転送機能が制御されます。</span><span class="sxs-lookup"><span data-stu-id="c00c6-104">In Microsoft Teams, calling policies control which calling and call forwarding features are available to users.</span></span> <span data-ttu-id="c00c6-105">通話ポリシーは、ユーザーがプライベートな通話を行うことができるかどうかを決定します。着信の転送や、他のユーザーや外部の電話番号への同時呼び出し、ボイスメールへの通話のルーティング、通話グループへの通話の送信、受信と発信などの呼び出しに委任を使用するなどを行います。</span><span class="sxs-lookup"><span data-stu-id="c00c6-105">Calling policies determine whether a user can make private calls, use call forwarding or  simultaneous ringing to other users or external phone numbers, route calls to voicemail, send calls to Call Groups, use delegation for inbound and outbound calls, and so on.</span></span> <span data-ttu-id="c00c6-106">既定のグローバルポリシーは自動的に作成されますが、管理者はカスタムの通話ポリシーを作成して割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="c00c6-106">A default global policy is created automatically, but admins can also create and assign custom calling policies.</span></span>

## <a name="create-a-custom-calling-policy"></a><span data-ttu-id="c00c6-107">カスタム通話ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="c00c6-107">Create a custom calling policy</span></span>

<span data-ttu-id="c00c6-108">カスタムの通話ポリシーを作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c00c6-108">Follow these steps to create a custom calling policy.</span></span>

1. <span data-ttu-id="c00c6-109">Microsoft Teams 管理センターで、[**音声** > **通話のポリシー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c00c6-109">In the Microsoft Teams admin center, select **Voice** > **Calling policy**.</span></span>
2. <span data-ttu-id="c00c6-110">[**新しいポリシー**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="c00c6-110">Select **New policy**.</span></span>
3. <span data-ttu-id="c00c6-111">通話ポリシーで使用する機能を有効にします。</span><span class="sxs-lookup"><span data-stu-id="c00c6-111">Turn on the features that you want to use in your calling policy.</span></span> <span data-ttu-id="c00c6-112">すべての選択は既定で**オフ**になっています。</span><span class="sxs-lookup"><span data-stu-id="c00c6-112">All selections are **Off** by default.</span></span>
4. <span data-ttu-id="c00c6-113">着信通話をボイスメールにルーティングできるかどうかを制御するには、[**常に有効**] または [**ユーザー管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c00c6-113">To control whether users can route inbound calls to voicemail, select **Always enabled** or **User controlled**.</span></span> <span data-ttu-id="c00c6-114">ボイスメールへのルーティングを禁止するには、[**常に無効**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="c00c6-114">To prevent routing to voicemail, select **Always disabled**.</span></span>
5. <span data-ttu-id="c00c6-115">[**保存**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="c00c6-115">Select **Save**.</span></span>

## <a name="modify-an-existing-calling-policy"></a><span data-ttu-id="c00c6-116">既存の通話ポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="c00c6-116">Modify an existing calling policy</span></span>

<span data-ttu-id="c00c6-117">既存の通話ポリシーを変更するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c00c6-117">Follow these steps to modify an existing calling policy.</span></span>

1. <span data-ttu-id="c00c6-118">Microsoft Teams 管理センターで、[**音声** > **通話のポリシー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c00c6-118">In the Microsoft Teams admin center, select **Voice** > **Calling policy**.</span></span>
2. <span data-ttu-id="c00c6-119">変更するポリシーの横にあるをクリックし、[**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c00c6-119">Click next to the policy that you want to modify, and then select **Edit**.</span></span>
3. <span data-ttu-id="c00c6-120">通話ポリシーで使用する機能を有効にします。</span><span class="sxs-lookup"><span data-stu-id="c00c6-120">Turn on the features that you want to use in your calling policy.</span></span> <span data-ttu-id="c00c6-121">すべての選択は既定で**オフ**になっています。</span><span class="sxs-lookup"><span data-stu-id="c00c6-121">All selections are **Off** by default.</span></span>
4. <span data-ttu-id="c00c6-122">着信通話をボイスメールにルーティングできるかどうかを制御するには、[**常に有効**] または [**ユーザー管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c00c6-122">To control whether users can route inbound calls to voicemail, select **Always enabled** or **User controlled**.</span></span> <span data-ttu-id="c00c6-123">ボイスメールへのルーティングを禁止するには、[**常に無効**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="c00c6-123">To prevent routing to voicemail, select **Always disabled**.</span></span>
5. <span data-ttu-id="c00c6-124">[**保存**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="c00c6-124">Select **Save**.</span></span>

## <a name="assign-a-calling-policy-to-a-user"></a><span data-ttu-id="c00c6-125">ユーザーに通話ポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="c00c6-125">Assign a calling policy to a user</span></span>

<span data-ttu-id="c00c6-126">ユーザーにカスタムの通話ポリシーを割り当てるには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c00c6-126">Follow these steps to assign a custom calling policy to a user.</span></span>

1. <span data-ttu-id="c00c6-127">Microsoft Teams 管理センターで、[**音声** > **通話のポリシー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c00c6-127">In the Microsoft Teams admin center, select **Voice** > **Calling policy**.</span></span>
2. <span data-ttu-id="c00c6-128">ポリシー名の横にあるをクリックして選択し、[**ユーザーの管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c00c6-128">Click next to the policy name to select it, and then select **Manage users**.</span></span>
3. <span data-ttu-id="c00c6-129">[**ユーザーの管理**] ウィンドウで、ユーザーの名前を検索します。</span><span class="sxs-lookup"><span data-stu-id="c00c6-129">In the **Manage users** pane, search for the user’s name.</span></span> <span data-ttu-id="c00c6-130">(少なくとも3文字を入力する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="c00c6-130">(You must enter at least three characters.)</span></span>
4. <span data-ttu-id="c00c6-131">ユーザー名を選択し、[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c00c6-131">Select the user’s name, and then select **Add**.</span></span>
5. <span data-ttu-id="c00c6-132">[**保存**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="c00c6-132">Select **Save**.</span></span>

## <a name="calling-policy-settings"></a><span data-ttu-id="c00c6-133">通話ポリシーの設定</span><span class="sxs-lookup"><span data-stu-id="c00c6-133">Calling policy settings</span></span>

<span data-ttu-id="c00c6-134">カスタムの通話ポリシーを作成するには、次の設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="c00c6-134">Use the following settings to create a custom calling policy.</span></span>

### <a name="user-can-make-private-calls"></a><span data-ttu-id="c00c6-135">ユーザはプライベートな通話を発信できます</span><span class="sxs-lookup"><span data-stu-id="c00c6-135">User can make private calls</span></span>

<span data-ttu-id="c00c6-136">この設定により、Teams のすべての通話機能が制御されます。</span><span class="sxs-lookup"><span data-stu-id="c00c6-136">This setting controls all calling capabilities in Teams.</span></span> <span data-ttu-id="c00c6-137">Teams のすべての通話機能を無効にするには、このオプションをオフにします。</span><span class="sxs-lookup"><span data-stu-id="c00c6-137">Turn this off to turn off all calling functionality in Teams.</span></span>

### <a name="call-forwarding-and-simultaneous-ringing-to-other-users"></a><span data-ttu-id="c00c6-138">他のユーザーとの着信の転送と同時呼び出し</span><span class="sxs-lookup"><span data-stu-id="c00c6-138">Call forwarding and simultaneous ringing to other users</span></span>

<span data-ttu-id="c00c6-139">この設定では、着信通話を他のユーザーに転送できるか、または他の人を同時に呼び出すことができるかを制御します。</span><span class="sxs-lookup"><span data-stu-id="c00c6-139">This setting controls whether incoming calls can be forwarded to other users or can ring another person at the same time.</span></span> 

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a><span data-ttu-id="c00c6-140">着信の転送と同時呼び出しを外部電話番号に転送する</span><span class="sxs-lookup"><span data-stu-id="c00c6-140">Call forwarding and simultaneous ringing to external phone numbers</span></span>

<span data-ttu-id="c00c6-141">この設定は、着信通話を外部番号に転送できるか、外部番号を同時に呼び出すことができるかを制御します。</span><span class="sxs-lookup"><span data-stu-id="c00c6-141">This setting controls whether incoming calls can be forwarded to an external number or can ring an external number at the same time.</span></span>

### <a name="voicemail-is-available-for-routing-inbound-calls-to-users"></a><span data-ttu-id="c00c6-142">着信通話をユーザにルーティングするためにボイスメールを利用できます</span><span class="sxs-lookup"><span data-stu-id="c00c6-142">Voicemail is available for routing inbound calls to users</span></span>

<span data-ttu-id="c00c6-143">この設定では、着信通話をボイスメールに送信できます。</span><span class="sxs-lookup"><span data-stu-id="c00c6-143">This setting enables inbound calls to be sent to voicemail.</span></span> <span data-ttu-id="c00c6-144">有効なオプションは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c00c6-144">Valid options are:</span></span>

   - <span data-ttu-id="c00c6-145">**常に有効**ボイスメールは、着信通話にいつでも利用できます。</span><span class="sxs-lookup"><span data-stu-id="c00c6-145">**Always enabled** Voicemail is always available for inbound calls.</span></span> 
   - <span data-ttu-id="c00c6-146">**常に無効** 着信通話でボイスメールを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="c00c6-146">**Always disabled**  Voicemail is not available for inbound calls.</span></span> 
   - <span data-ttu-id="c00c6-147">**ユーザー制御**。</span><span class="sxs-lookup"><span data-stu-id="c00c6-147">**User controlled**.</span></span> <span data-ttu-id="c00c6-148">ユーザーはボイスメールを利用できるようにするかどうかを決定できます。</span><span class="sxs-lookup"><span data-stu-id="c00c6-148">Users can determine whether they want voicemail to be available.</span></span>

### <a name="inbound-calls-can-be-routed-to-call-groups"></a><span data-ttu-id="c00c6-149">着信通話を通話グループにルーティングできる</span><span class="sxs-lookup"><span data-stu-id="c00c6-149">Inbound calls can be routed to call groups</span></span> 

> [!Include [feature preview](includes/preview-feature.md)]

<span data-ttu-id="c00c6-150">この設定は、着信通話を通話グループに転送できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="c00c6-150">This setting controls whether incoming calls can be forwarded to a call group.</span></span>

### <a name="allow-delegation-for-inbound-and-outbound-calls"></a><span data-ttu-id="c00c6-151">着信と発信の通話の委任を許可する</span><span class="sxs-lookup"><span data-stu-id="c00c6-151">Allow delegation for inbound and outbound calls</span></span>

> [!Include [feature preview](includes/preview-feature.md)]

<span data-ttu-id="c00c6-152">この設定を有効にすると、着信の代理人へのルーティングが許可され、代理人がアクセス権を委任したユーザーの代わりに発信通話を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="c00c6-152">This setting enables inbound calls to be routed to delegates, allowing delegates to make outbound calls on behalf of the users for whom they have delegated permissions.</span></span> <span data-ttu-id="c00c6-153">詳細については、「[代理人と電話回線を共有](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c00c6-153">For more information, see [Share a phone line with a delegate](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8).</span></span>


### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a><span data-ttu-id="c00c6-154">通話を発信したり、PSTN 経由で通話を送信したりする</span><span class="sxs-lookup"><span data-stu-id="c00c6-154">Prevent toll bypass and send calls through the PSTN</span></span> 

<span data-ttu-id="c00c6-155">この設定**で**は、ネットワーク経由での送信と、tolls のバイパスではなく、PSTN 経由で通話が送信され、料金が発生します。</span><span class="sxs-lookup"><span data-stu-id="c00c6-155">Setting this to **On** will send calls through the PSTN and incur charges rather than sending them through the network and bypassing the tolls.</span></span>

### <a name="busy-on-busy-is-available-while-in-a-call"></a><span data-ttu-id="c00c6-156">通話中に取り込み中</span><span class="sxs-lookup"><span data-stu-id="c00c6-156">Busy on Busy is available while in a call</span></span>

<span data-ttu-id="c00c6-157">[取り込み中] (取り込み中)) は、ユーザーが既に通話または会議に参加している場合や、通話が保留になっている場合に、着信通話の処理方法を構成できる、チーム呼び出しポリシーの新しい設定です。</span><span class="sxs-lookup"><span data-stu-id="c00c6-157">Busy on Busy (Busy Options)) is a new setting in Teams calling policies that lets you configure how incoming calls are handled when a user is already in a call or conference or has a call placed on hold.</span></span> <span data-ttu-id="c00c6-158">新規または着信通話は、取り込み中の信号で拒否することができます。</span><span class="sxs-lookup"><span data-stu-id="c00c6-158">New or incoming calls can be rejected with a busy signal.</span></span> <span data-ttu-id="c00c6-159">[取り込み] オプションは、テナントレベルまたはユーザーレベルで有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="c00c6-159">You can enable busy options at the tenant level or at the user level.</span></span> <span data-ttu-id="c00c6-160">通話や電話会議のユーザー、または通話を保留しているユーザーは、会議中の通話や会議の開始を防ぐことはできません。</span><span class="sxs-lookup"><span data-stu-id="c00c6-160">Regardless of how their busy options are configured, users in a call or conference or those with a call on hold are not prevented from initiating new calls or conferences.</span></span> <span data-ttu-id="c00c6-161">この設定は、既定では無効になっています。</span><span class="sxs-lookup"><span data-stu-id="c00c6-161">This setting is disabled by default.</span></span>

## <a name="see-also"></a><span data-ttu-id="c00c6-162">関連項目</span><span class="sxs-lookup"><span data-stu-id="c00c6-162">See also</span></span>

[<span data-ttu-id="c00c6-163">Set-Csteam拡張性のポリシー</span><span class="sxs-lookup"><span data-stu-id="c00c6-163">Set-CSTeamsCallingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)