---
title: Microsoft Teams の発信通話制限ポリシー
author: LolaJacobsen
ms.author: tonysmit
manager: serdars
ms.date: 04/15/2019
ms.topic: conceptual
ms.service: msteams
ms.reviewer: jastark
search.appverid: MET150
description: マイクロソフト チームのポリシーの設定を呼び出す方法の詳細について説明します。
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6e56f0c89859b940a82e76f8de35ff524a757ec9
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32225001"
---
<a name="calling-policies-in-microsoft-teams"></a><span data-ttu-id="63420-103">Microsoft Teams の発信通話制限ポリシー</span><span class="sxs-lookup"><span data-stu-id="63420-103">Calling policies in Microsoft Teams</span></span>
==========================================

<span data-ttu-id="63420-104">マイクロソフト チーム、ポリシー制御、通話の呼び出しと呼び出しの転送機能ユーザーが利用できます。</span><span class="sxs-lookup"><span data-stu-id="63420-104">In Microsoft Teams, calling policies control which calling and call forwarding features are available to users.</span></span> <span data-ttu-id="63420-105">通話ポリシー呼び出しの転送を使用して、または同時に他のユーザーまたは外部の電話番号が鳴ってボイスメール、電話のグループでは、送信呼び出しに呼び出しをルートを使用して着信および発信呼び出しのための委任のユーザーは、秘密の呼び出しを行うことができます、かどうかを判断していうようにします。</span><span class="sxs-lookup"><span data-stu-id="63420-105">Calling policies determine whether a user can make private calls, use call forwarding or  simultaneous ringing to other users or external phone numbers, route calls to voicemail, send calls to Call Groups, use delegation for inbound and outbound calls, and so on.</span></span> <span data-ttu-id="63420-106">既定のグローバル ポリシーは自動的に作成されますが、管理者の作成し呼び出し元のユーザー設定のポリシーを割り当てることができますもします。</span><span class="sxs-lookup"><span data-stu-id="63420-106">A default global policy is created automatically, but admins can also create and assign custom calling policies.</span></span>

## <a name="create-a-custom-calling-policy"></a><span data-ttu-id="63420-107">カスタムの呼び出し元のポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="63420-107">Create a custom calling policy</span></span>

<span data-ttu-id="63420-108">この手順では、カスタムの呼び出し元のポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="63420-108">Follow these steps to create a custom calling policy.</span></span>

1. <span data-ttu-id="63420-109">マイクロソフトのチーム管理センターで、**音声**を選択します > **ポリシーを呼び出すこと**です。</span><span class="sxs-lookup"><span data-stu-id="63420-109">In the Microsoft Teams admin center, select **Voice** > **Calling policy**.</span></span>
2. <span data-ttu-id="63420-110">**新しいポリシー**を選択します。</span><span class="sxs-lookup"><span data-stu-id="63420-110">Select **New policy**.</span></span>
3. <span data-ttu-id="63420-111">呼び出し元のポリシーで使用する機能をオンにします。</span><span class="sxs-lookup"><span data-stu-id="63420-111">Turn on the features that you want to use in your calling policy.</span></span> <span data-ttu-id="63420-112">すべての選択は、既定で**オフ**します。</span><span class="sxs-lookup"><span data-stu-id="63420-112">All selections are **Off** by default.</span></span>
4. <span data-ttu-id="63420-113">ユーザーが着信通話をボイスメールにルーティングできるかどうかを制御するには、**常に有効になっている**か、**ユーザーが制御**を選択します。</span><span class="sxs-lookup"><span data-stu-id="63420-113">To control whether users can route inbound calls to voicemail, select **Always enabled** or **User controlled**.</span></span> <span data-ttu-id="63420-114">ボイスメールにルーティングするには、**常に無効になっている**を選択します。</span><span class="sxs-lookup"><span data-stu-id="63420-114">To prevent routing to voicemail, select **Always disabled**.</span></span>
5. <span data-ttu-id="63420-115">**保存**を選択します。</span><span class="sxs-lookup"><span data-stu-id="63420-115">Select **Save**.</span></span>

## <a name="modify-an-existing-calling-policy"></a><span data-ttu-id="63420-116">既存のポリシーの呼び出しを変更します。</span><span class="sxs-lookup"><span data-stu-id="63420-116">Modify an existing calling policy</span></span>

<span data-ttu-id="63420-117">既存のポリシーの呼び出しを変更するのにはこれらの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="63420-117">Follow these steps to modify an existing calling policy.</span></span>

1. <span data-ttu-id="63420-118">マイクロソフトのチーム管理センターで、**音声**を選択します > **ポリシーを呼び出すこと**です。</span><span class="sxs-lookup"><span data-stu-id="63420-118">In the Microsoft Teams admin center, select **Voice** > **Calling policy**.</span></span>
2. <span data-ttu-id="63420-119">ポリシーを変更して、[**編集**] を選択するをクリックします。</span><span class="sxs-lookup"><span data-stu-id="63420-119">Click next to the policy that you want to modify, and then select **Edit**.</span></span>
3. <span data-ttu-id="63420-120">呼び出し元のポリシーで使用する機能をオンにします。</span><span class="sxs-lookup"><span data-stu-id="63420-120">Turn on the features that you want to use in your calling policy.</span></span> <span data-ttu-id="63420-121">すべての選択は、既定で**オフ**します。</span><span class="sxs-lookup"><span data-stu-id="63420-121">All selections are **Off** by default.</span></span>
4. <span data-ttu-id="63420-122">ユーザーが着信通話をボイスメールにルーティングできるかどうかを制御するには、**常に有効になっている**か、**ユーザーが制御**を選択します。</span><span class="sxs-lookup"><span data-stu-id="63420-122">To control whether users can route inbound calls to voicemail, select **Always enabled** or **User controlled**.</span></span> <span data-ttu-id="63420-123">ボイスメールにルーティングするには、**常に無効になっている**を選択します。</span><span class="sxs-lookup"><span data-stu-id="63420-123">To prevent routing to voicemail, select **Always disabled**.</span></span>
5. <span data-ttu-id="63420-124">**保存**を選択します。</span><span class="sxs-lookup"><span data-stu-id="63420-124">Select **Save**.</span></span>

## <a name="assign-a-calling-policy-to-a-user"></a><span data-ttu-id="63420-125">呼び出し元のポリシーをユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="63420-125">Assign a calling policy to a user</span></span>

<span data-ttu-id="63420-126">カスタムの呼び出し元のポリシーをユーザーに割り当てるにはこれらの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="63420-126">Follow these steps to assign a custom calling policy to a user.</span></span>

1. <span data-ttu-id="63420-127">マイクロソフトのチーム管理センターで、**音声**を選択します > **ポリシーを呼び出すこと**です。</span><span class="sxs-lookup"><span data-stu-id="63420-127">In the Microsoft Teams admin center, select **Voice** > **Calling policy**.</span></span>
2. <span data-ttu-id="63420-128">選択し、**ユーザーの管理**を選択し、ポリシー名の横にあるをクリックします。</span><span class="sxs-lookup"><span data-stu-id="63420-128">Click next to the policy name to select it, and then select **Manage users**.</span></span>
3. <span data-ttu-id="63420-129">**ユーザーの管理**ウィンドウで、ユーザーの名前を探します。</span><span class="sxs-lookup"><span data-stu-id="63420-129">In the **Manage users** pane, search for the user’s name.</span></span> <span data-ttu-id="63420-130">(3 文字以上を入力する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="63420-130">(You must enter at least three characters.)</span></span>
4. <span data-ttu-id="63420-131">ユーザーの名を選択し、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63420-131">Select the user’s name, and then select **Add**.</span></span>
5. <span data-ttu-id="63420-132">**保存**を選択します。</span><span class="sxs-lookup"><span data-stu-id="63420-132">Select **Save**.</span></span>

## <a name="calling-policy-settings"></a><span data-ttu-id="63420-133">ポリシーの設定を呼び出す</span><span class="sxs-lookup"><span data-stu-id="63420-133">Calling policy settings</span></span>

<span data-ttu-id="63420-134">カスタムの呼び出し元のポリシーを作成するのにには、次の設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="63420-134">Use the following settings to create a custom calling policy.</span></span>

### <a name="user-can-make-private-calls"></a><span data-ttu-id="63420-135">ユーザーがプライベートの呼び出しを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="63420-135">User can make private calls</span></span>

<span data-ttu-id="63420-136">この設定は、チーム内のすべての呼び出し機能を制御します。</span><span class="sxs-lookup"><span data-stu-id="63420-136">This setting controls all calling capabilities in Teams.</span></span> <span data-ttu-id="63420-137">チーム内のすべての呼び出し機能を無効にするをオフにします。</span><span class="sxs-lookup"><span data-stu-id="63420-137">Turn this off to turn off all calling functionality in Teams.</span></span>

### <a name="call-forwarding-and-simultaneous-ringing-to-other-users"></a><span data-ttu-id="63420-138">着信の転送およびその他のユーザーに同時呼び出し</span><span class="sxs-lookup"><span data-stu-id="63420-138">Call forwarding and simultaneous ringing to other users</span></span>

<span data-ttu-id="63420-139">この設定は、着信通話が他のユーザーに転送することや、同時に他の人をリングことができるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="63420-139">This setting controls whether incoming calls can be forwarded to other users or can ring another person at the same time.</span></span> 

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a><span data-ttu-id="63420-140">着信の転送および外部の電話番号に同時に呼び出し</span><span class="sxs-lookup"><span data-stu-id="63420-140">Call forwarding and simultaneous ringing to external phone numbers</span></span>

<span data-ttu-id="63420-141">この設定は、着信通話が、外部の番号に転送することや、同時に着信音、外部の数のことができるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="63420-141">This setting controls whether incoming calls can be forwarded to an external number or can ring an external number at the same time.</span></span>

### <a name="voicemail-is-available-for-routing-inbound-calls-to-users"></a><span data-ttu-id="63420-142">ボイスメールは、ユーザーへの着信通話のルーティングの使用</span><span class="sxs-lookup"><span data-stu-id="63420-142">Voicemail is available for routing inbound calls to users</span></span>

<span data-ttu-id="63420-143">この設定により、着信がボイスメールに送信されます。</span><span class="sxs-lookup"><span data-stu-id="63420-143">This setting enables inbound calls to be sent to voicemail.</span></span> <span data-ttu-id="63420-144">有効なオプションは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="63420-144">Valid options are:</span></span>

   - <span data-ttu-id="63420-145">**常に有効になっています。** ボイスメールは、常に着信呼び出しに使用できます。</span><span class="sxs-lookup"><span data-stu-id="63420-145">**Always enabled** Voicemail is always available for inbound calls.</span></span> 
   - <span data-ttu-id="63420-146">**常に無効になっています。** ボイスメールが着信呼び出しに対して使用可能ではありません。</span><span class="sxs-lookup"><span data-stu-id="63420-146">**Always disabled**  Voicemail is not available for inbound calls.</span></span> 
   - <span data-ttu-id="63420-147">**ユーザーが制御**されます。</span><span class="sxs-lookup"><span data-stu-id="63420-147">**User controlled**.</span></span> <span data-ttu-id="63420-148">ユーザーは、ボイスメールを使用するかどうかを決定できます。</span><span class="sxs-lookup"><span data-stu-id="63420-148">Users can determine whether they want voicemail to be available.</span></span>

### <a name="inbound-calls-can-be-routed-to-call-groups"></a><span data-ttu-id="63420-149">グループを呼び出すに着信呼び出しをルーティングすることができます。</span><span class="sxs-lookup"><span data-stu-id="63420-149">Inbound calls can be routed to call groups</span></span> 

<span data-ttu-id="63420-150">この設定は、着信呼び出しを呼び出しグループに転送できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="63420-150">This setting controls whether incoming calls can be forwarded to a call group.</span></span>

### <a name="allow-delegation-for-inbound-and-outbound-calls"></a><span data-ttu-id="63420-151">着信および発信通話の委任を許可します。</span><span class="sxs-lookup"><span data-stu-id="63420-151">Allow delegation for inbound and outbound calls</span></span>

<span data-ttu-id="63420-152">この設定は、対象となるアクセス許可を委任するがユーザーによって送信呼び出しを行うデリゲートを許可する代理人に転送される着信呼び出しを有効にします。</span><span class="sxs-lookup"><span data-stu-id="63420-152">This setting enables inbound calls to be routed to delegates, allowing delegates to make outbound calls on behalf of the users for whom they have delegated permissions.</span></span> <span data-ttu-id="63420-153">詳細については、[代理人に電話回線の共有](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="63420-153">For more information, see [Share a phone line with a delegate](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8).</span></span>

### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a><span data-ttu-id="63420-154">有料のバイパスを防止し、PSTN 経由で呼び出しを送信します。</span><span class="sxs-lookup"><span data-stu-id="63420-154">Prevent toll bypass and send calls through the PSTN</span></span> 

<span data-ttu-id="63420-155">これを**On**に設定、PSTN 経由で呼び出しを送信して発生する料金ではなく、ネットワークを介して送信して、それをバイパスします。</span><span class="sxs-lookup"><span data-stu-id="63420-155">Setting this to **On** will send calls through the PSTN and incur charges rather than sending them through the network and bypassing the tolls.</span></span>

### <a name="busy-on-busy-is-available-while-in-a-call"></a><span data-ttu-id="63420-156">取り込みに時間が通話中に利用可能です</span><span class="sxs-lookup"><span data-stu-id="63420-156">Busy on Busy is available while in a call</span></span>

<span data-ttu-id="63420-157">(使用中のオプション) 取り込み中にビジー状態) は、保留中のユーザーが通話や会議であるかの呼び出しには、着信呼び出しを構成するのには、呼び出し元のポリシーが処理されるチームの新しい設定を配置します。</span><span class="sxs-lookup"><span data-stu-id="63420-157">Busy on Busy (Busy Options)) is a new setting in Teams calling policies that allows you to configure how incoming calls are handled when a user is already in a call or conference or has a call placed on hold.</span></span> <span data-ttu-id="63420-158">ビジー信号を新規または着信呼び出しを拒否できます。</span><span class="sxs-lookup"><span data-stu-id="63420-158">New or incoming calls can be rejected with a busy signal.</span></span> <span data-ttu-id="63420-159">テナント レベルまたはユーザー レベルでの使用中のオプションを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="63420-159">You can enable busy options at a tenant level or at a user level.</span></span> <span data-ttu-id="63420-160">使用中のオプションの構成方法に関係なく電話会議、または保留中の呼び出しを持つユーザーは禁止されません新しい通話や会議を開始します。</span><span class="sxs-lookup"><span data-stu-id="63420-160">Regardless of how their busy options are configured, users in a call or conference or those with a call on hold are not prevented from initiating new calls or conferences.</span></span> <span data-ttu-id="63420-161">この設定は既定で無効になります。</span><span class="sxs-lookup"><span data-stu-id="63420-161">This setting is disabled by default.</span></span>

