---
title: Microsoft Teams の発信通話制限ポリシー
author: SerdarSoysal
ms.author: tonysmit
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: jastark
audience: admin
search.appverid: MET150
description: Microsoft Teams のカスタム通話ポリシーとさまざまな通話ポリシー設定を作成、変更、追加する方法について説明します。
localization_priority: Normal
ms.collection:
- M365-voice
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.callingpolicies.overview
- seo-marvel-apr2020
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6cfa0043b4da6c3087c0e144bb0759ed5b87f01c
ms.sourcegitcommit: d62e6cefceebe481eb207c59872f1aa67f0fc528
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2021
ms.locfileid: "50465476"
---
<a name="calling-policies-in-microsoft-teams"></a><span data-ttu-id="a6a3d-103">Microsoft Teams の発信通話制限ポリシー</span><span class="sxs-lookup"><span data-stu-id="a6a3d-103">Calling policies in Microsoft Teams</span></span>
===================================

<span data-ttu-id="a6a3d-104">Microsoft Teams では、ユーザーが使用できる通話と通話の転送機能を通話ポリシーで制御します。</span><span class="sxs-lookup"><span data-stu-id="a6a3d-104">In Microsoft Teams, calling policies control which calling and call forwarding features are available to users.</span></span> <span data-ttu-id="a6a3d-105">通話ポリシーは、ユーザーがプライベート通話を行う、他のユーザーまたは外部の電話番号への着信の転送または同時呼び出しを使用できるかどうか、通話をボイスメールにルーティングする、通話グループに通話を送信する、着信通話と発信通話の委任を使用できるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="a6a3d-105">Calling policies determine whether a user can make private calls, use call forwarding or simultaneous ringing to other users or external phone numbers, route calls to voicemail, send calls to call groups, use delegation for inbound and outbound calls, and so on.</span></span>

<span data-ttu-id="a6a3d-106">自動的に作成されるグローバル (組織全体の既定) ポリシーを使用するか、カスタム ポリシーを作成して割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="a6a3d-106">You can use the global (Org-wide default) policy that's created automatically or create and assign custom policies.</span></span>

## <a name="create-a-custom-calling-policy"></a><span data-ttu-id="a6a3d-107">カスタム通話ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="a6a3d-107">Create a custom calling policy</span></span>

<span data-ttu-id="a6a3d-108">カスタム通話ポリシーを作成するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="a6a3d-108">Follow these steps to create a custom calling policy.</span></span>

1. <span data-ttu-id="a6a3d-109">Microsoft Teams 管理センターの左側のナビゲーションで、[音声通話ポリシー **]**  >  **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="a6a3d-109">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Calling policies**.</span></span>
2. <span data-ttu-id="a6a3d-110">**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a6a3d-110">Select **Add**.</span></span>
3. <span data-ttu-id="a6a3d-111">通話ポリシーで使用する機能をオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="a6a3d-111">Turn on or turn off the features that you want to use in your calling policy.</span></span>
4. <span data-ttu-id="a6a3d-112">ユーザーが着信通話をボイスメールにルーティングできるかどうかを制御するには、[有効] または [ユーザー制御]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="a6a3d-112">To control whether users can route inbound calls to voicemail, select **Enabled** or **User controlled**.</span></span> <span data-ttu-id="a6a3d-113">ボイスメールへのルーティングを防止するには、[無効] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="a6a3d-113">To prevent routing to voicemail, select **Disabled**.</span></span>
5. <span data-ttu-id="a6a3d-114">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a6a3d-114">Select **Save**.</span></span>

## <a name="edit-a-calling-policy"></a><span data-ttu-id="a6a3d-115">通話ポリシーを編集する</span><span class="sxs-lookup"><span data-stu-id="a6a3d-115">Edit a calling policy</span></span>

<span data-ttu-id="a6a3d-116">既存の通話ポリシーを編集するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="a6a3d-116">Follow these steps to edit an existing calling policy.</span></span>

1. <span data-ttu-id="a6a3d-117">Microsoft Teams 管理センターの左側のナビゲーションで、[音声通話ポリシー **]**  >  **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="a6a3d-117">In the left navigation of the Microsoft Teams admin center, select **Voice** > **Calling policies**.</span></span>
2. <span data-ttu-id="a6a3d-118">変更するポリシーの横をクリックし、[編集] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="a6a3d-118">Click next to the policy that you want to modify, and then select **Edit**.</span></span>
3. <span data-ttu-id="a6a3d-119">必要な変更を行い、[保存] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="a6a3d-119">Make the changes that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-calling-policy-to-users"></a><span data-ttu-id="a6a3d-120">カスタム通話ポリシーをユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="a6a3d-120">Assign a custom calling policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="calling-policy-settings"></a><span data-ttu-id="a6a3d-121">通話ポリシーの設定</span><span class="sxs-lookup"><span data-stu-id="a6a3d-121">Calling policy settings</span></span>

<span data-ttu-id="a6a3d-122">通話ポリシー用に構成できる設定を次に示します。</span><span class="sxs-lookup"><span data-stu-id="a6a3d-122">Here's the settings that you can configure for calling policies.</span></span>

### <a name="make-private-calls"></a><span data-ttu-id="a6a3d-123">プライベート通話をする</span><span class="sxs-lookup"><span data-stu-id="a6a3d-123">Make private calls</span></span>

<span data-ttu-id="a6a3d-124">この設定は、Teams のすべての通話機能を制御します。</span><span class="sxs-lookup"><span data-stu-id="a6a3d-124">This setting controls all calling capabilities in Teams.</span></span> <span data-ttu-id="a6a3d-125">これをオフにし、Teams のすべての通話機能をオフにします。</span><span class="sxs-lookup"><span data-stu-id="a6a3d-125">Turn this off to turn off all calling functionality in Teams.</span></span>

### <a name="call-forwarding-and-simultaneous-ringing-to-people-in-your-organization"></a><span data-ttu-id="a6a3d-126">組織内のユーザーへの通話の転送と同時呼び出し</span><span class="sxs-lookup"><span data-stu-id="a6a3d-126">Call forwarding and simultaneous ringing to people in your organization</span></span>

<span data-ttu-id="a6a3d-127">この設定では、着信通話を他のユーザーに転送したり、他のユーザーを同時に呼び出したりできるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="a6a3d-127">This setting controls whether incoming calls can be forwarded to other users or can ring another person at the same time.</span></span> 

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a><span data-ttu-id="a6a3d-128">外部の電話番号への通話の転送と同時呼び出し</span><span class="sxs-lookup"><span data-stu-id="a6a3d-128">Call forwarding and simultaneous ringing to external phone numbers</span></span>

<span data-ttu-id="a6a3d-129">この設定では、着信通話を外部番号に転送できるかどうか、または外部番号を同時に呼び出すかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="a6a3d-129">This setting controls whether incoming calls can be forwarded to an external number or can ring an external number at the same time.</span></span>

### <a name="voicemail-is-available-for-routing-inbound-calls"></a><span data-ttu-id="a6a3d-130">ボイスメールは着信通話をルーティングできます</span><span class="sxs-lookup"><span data-stu-id="a6a3d-130">Voicemail is available for routing inbound calls</span></span>

<span data-ttu-id="a6a3d-131">この設定では、受信通話をボイスメールに送信できます。</span><span class="sxs-lookup"><span data-stu-id="a6a3d-131">This setting enables inbound calls to be sent to voicemail.</span></span> <span data-ttu-id="a6a3d-132">有効なオプションは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a6a3d-132">Valid options are:</span></span>

- <span data-ttu-id="a6a3d-133">**有効** ボイスメールは、常に着信通話に使用できます。</span><span class="sxs-lookup"><span data-stu-id="a6a3d-133">**Enabled** Voicemail is always available for inbound calls.</span></span>
- <span data-ttu-id="a6a3d-134">**無効**  ボイスメールは、着信通話では使用できません。</span><span class="sxs-lookup"><span data-stu-id="a6a3d-134">**Disabled**  Voicemail is not available for inbound calls.</span></span>
- <span data-ttu-id="a6a3d-135">**ユーザー制御** ユーザーは、ボイスメールを使用できるかどうかを決定できます。</span><span class="sxs-lookup"><span data-stu-id="a6a3d-135">**User controlled** Users can determine whether they want voicemail to be available.</span></span>

### <a name="inbound-calls-can-be-routed-to-call-groups"></a><span data-ttu-id="a6a3d-136">着信通話を通話グループにルーティングできる</span><span class="sxs-lookup"><span data-stu-id="a6a3d-136">Inbound calls can be routed to call groups</span></span> 

<span data-ttu-id="a6a3d-137">この設定は、着信通話を通話グループに転送できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="a6a3d-137">This setting controls whether incoming calls can be forwarded to a call group.</span></span>

### <a name="allow-delegation-for-inbound-and-outbound-calls"></a><span data-ttu-id="a6a3d-138">着信通話と発信通話の委任を許可する</span><span class="sxs-lookup"><span data-stu-id="a6a3d-138">Allow delegation for inbound and outbound calls</span></span>

<span data-ttu-id="a6a3d-139">この設定では、着信通話を代理人にルーティングし、代理人がアクセス許可を委任したユーザーの代わりに発信通話を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="a6a3d-139">This setting enables inbound calls to be routed to delegates, allowing delegates to make outbound calls on behalf of the users for whom they have delegated permissions.</span></span> <span data-ttu-id="a6a3d-140">詳細については、「代理人と [電話回線を共有する」を参照してください](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)。</span><span class="sxs-lookup"><span data-stu-id="a6a3d-140">For more information, see [Share a phone line with a delegate](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8).</span></span>

### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a><span data-ttu-id="a6a3d-141">有料バイパスを防止し、PSTN 経由で通話を送信する</span><span class="sxs-lookup"><span data-stu-id="a6a3d-141">Prevent toll bypass and send calls through the PSTN</span></span> 

<span data-ttu-id="a6a3d-142">これをオンに **設定** すると、PSTN 経由で通話が送信され、ネットワーク経由で通話を送信して有料通話をバイパスするのではなく、料金が発生します。</span><span class="sxs-lookup"><span data-stu-id="a6a3d-142">Setting this to **On** will send calls through the PSTN and incur charges rather than sending them through the network and bypassing the tolls.</span></span>

### <a name="busy-on-busy-is-available-while-in-a-call"></a><span data-ttu-id="a6a3d-143">通話中に取り込み中の取り込み中</span><span class="sxs-lookup"><span data-stu-id="a6a3d-143">Busy on Busy is available while in a call</span></span>

<span data-ttu-id="a6a3d-144">取り込み中 (取り込み中オプション) は、ユーザーが既に通話または会議に参加している場合、または通話を保留にした場合の着信通話の処理方法を構成できる新しい設定です。</span><span class="sxs-lookup"><span data-stu-id="a6a3d-144">Busy on Busy (Busy Options) is a new setting that lets you configure how incoming calls are handled when a user is already in a call or conference or has a call placed on hold.</span></span> <span data-ttu-id="a6a3d-145">新しい通話または着信通話は、取り込み中の信号で拒否できます。</span><span class="sxs-lookup"><span data-stu-id="a6a3d-145">New or incoming calls can be rejected with a busy signal.</span></span> <span data-ttu-id="a6a3d-146">取り込み中オプションは、テナント レベルまたはユーザー レベルで有効にできます。</span><span class="sxs-lookup"><span data-stu-id="a6a3d-146">You can enable busy options at the tenant level or at the user level.</span></span> <span data-ttu-id="a6a3d-147">取り込み中のオプションの構成方法に関係なく、通話または会議のユーザー、または保留の通話を行っているユーザーは、新しい通話や会議を開始できない状態ではありません。</span><span class="sxs-lookup"><span data-stu-id="a6a3d-147">Regardless of how their busy options are configured, users in a call or conference or those with a call on hold are not prevented from initiating new calls or conferences.</span></span> <span data-ttu-id="a6a3d-148">この設定は、既定では無効になっています。</span><span class="sxs-lookup"><span data-stu-id="a6a3d-148">This setting is disabled by default.</span></span>

### <a name="allow-web-pstn-calling"></a><span data-ttu-id="a6a3d-149">Web PSTN 通話を許可する</span><span class="sxs-lookup"><span data-stu-id="a6a3d-149">Allow web PSTN calling</span></span>

<span data-ttu-id="a6a3d-150">この設定により、ユーザーは Teams Web クライアントを使用して PSTN 番号に通話できます。</span><span class="sxs-lookup"><span data-stu-id="a6a3d-150">This setting enables users to call PSTN numbers using the Teams web client.</span></span>

### <a name="allow-music-on-hold"></a><span data-ttu-id="a6a3d-151">保留音を許可する</span><span class="sxs-lookup"><span data-stu-id="a6a3d-151">Allow music on hold</span></span>

<span data-ttu-id="a6a3d-152">この設定では、PSTN 発信者が保留にされた場合に、保留音のオンとオフを切り替えます。</span><span class="sxs-lookup"><span data-stu-id="a6a3d-152">This setting allows you to turn on or turn off music on hold when a PSTN caller is placed on hold.</span></span> <span data-ttu-id="a6a3d-153">既定ではオンになっています。</span><span class="sxs-lookup"><span data-stu-id="a6a3d-153">It's turned on by default.</span></span> <span data-ttu-id="a6a3d-154">この設定はコール パークや上司の代理人機能には適用されません。現在は PowerShell 経由でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="a6a3d-154">This setting doesn't apply to call park and boss delegate features, and is currently only available via PowerShell.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a6a3d-155">関連トピック</span><span class="sxs-lookup"><span data-stu-id="a6a3d-155">Related topics</span></span>

[<span data-ttu-id="a6a3d-156">Set-CSTeamsCallingPolicy</span><span class="sxs-lookup"><span data-stu-id="a6a3d-156">Set-CSTeamsCallingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)

[<span data-ttu-id="a6a3d-157"> Teams でユーザーにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="a6a3d-157">Assign policies to your users in Teams</span></span>](assign-policies.md)
