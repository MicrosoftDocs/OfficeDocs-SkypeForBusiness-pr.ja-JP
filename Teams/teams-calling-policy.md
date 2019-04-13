---
title: マイクロソフト チームのポリシーを呼び出す
author: LolaJacobsen
ms.author: tonysmit
manager: serdars
ms.date: 04/12/2019
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
ms.openlocfilehash: c97fd5ff9228d0761f55f2f56b9a908cc3861c29
ms.sourcegitcommit: 82490c2ef74900c348c14968b605a313b5bf3078
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2019
ms.locfileid: "31860264"
---
<a name="calling-policy-in-microsoft-teams"></a><span data-ttu-id="d9e18-103">マイクロソフト チームのポリシーを呼び出す</span><span class="sxs-lookup"><span data-stu-id="d9e18-103">Calling policy in Microsoft Teams</span></span>
==========================================

<span data-ttu-id="d9e18-104">マイクロソフト チーム、ポリシー制御、通話の呼び出しと呼び出しの転送機能ユーザーが利用できます。</span><span class="sxs-lookup"><span data-stu-id="d9e18-104">In Microsoft Teams, calling policies control which calling and call forwarding features are available to users.</span></span> <span data-ttu-id="d9e18-105">通話ポリシー呼び出しの転送を使用して、または同時に他のユーザーまたは外部の電話番号が鳴ってボイスメール、電話のグループでは、送信呼び出しに呼び出しをルートを使用して着信および発信呼び出しのための委任のユーザーは、秘密の呼び出しを行うことができます、かどうかを判断していうようにします。</span><span class="sxs-lookup"><span data-stu-id="d9e18-105">Calling policies determine whether a user can make private calls, use call forwarding or  simultaneous ringing to other users or external phone numbers, route calls to voicemail, send calls to Call Groups, use delegation for inbound and outbound calls, and so on.</span></span> <span data-ttu-id="d9e18-106">既定のグローバル ポリシーは自動的に作成されますが、管理者の作成し呼び出し元のユーザー設定のポリシーを割り当てることができますもします。</span><span class="sxs-lookup"><span data-stu-id="d9e18-106">A default global policy is created automatically, but admins can also create and assign custom calling policies.</span></span>

## <a name="calling-policy-settings"></a><span data-ttu-id="d9e18-107">ポリシーの設定を呼び出す</span><span class="sxs-lookup"><span data-stu-id="d9e18-107">Calling policy settings</span></span>

|<span data-ttu-id="d9e18-108">ポリシーの設定を呼び出す</span><span class="sxs-lookup"><span data-stu-id="d9e18-108">Calling policy setting</span></span> | <span data-ttu-id="d9e18-109">説明</span><span class="sxs-lookup"><span data-stu-id="d9e18-109">Description</span></span> |
|-----------------------|-------------|
|<span data-ttu-id="d9e18-110">ユーザーがプライベートの呼び出しを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="d9e18-110">User can make private calls</span></span> | <span data-ttu-id="d9e18-111">チーム内のすべての呼び出し機能を制御します。</span><span class="sxs-lookup"><span data-stu-id="d9e18-111">Controls all calling capabilities in Teams.</span></span> <span data-ttu-id="d9e18-112">チーム内のすべての呼び出し機能をオフにこれをオフします。</span><span class="sxs-lookup"><span data-stu-id="d9e18-112">Turning this off will turn off all calling functionality in Teams.</span></span>|
|<span data-ttu-id="d9e18-113">着信の転送およびその他のユーザーに同時呼び出し</span><span class="sxs-lookup"><span data-stu-id="d9e18-113">Call forwarding and simultaneous ringing to other users</span></span> | <span data-ttu-id="d9e18-114">他のユーザーに転送することができますまたは同時に他の人をリングが着信呼び出しの合計かどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="d9e18-114">Controls whether incoming calls can be forwarded to other users or can ring another person at the same time.</span></span> |
|<span data-ttu-id="d9e18-115">着信の転送および外部の電話番号に同時に呼び出し</span><span class="sxs-lookup"><span data-stu-id="d9e18-115">Call forwarding and simultaneous ringing to external phone numbers</span></span> | <span data-ttu-id="d9e18-116">着信呼び出しの合計かどうか、外部の番号に転送することができますコントロール、またはコントロールを同時に、外部の数をリングすることができます。</span><span class="sxs-lookup"><span data-stu-id="d9e18-116">Controls whether incoming calls can be forwarded to an external number or can ring an external number at the same time.</span></span>|
|<span data-ttu-id="d9e18-117">ボイスメールは、ユーザーへの着信通話のルーティングの使用</span><span class="sxs-lookup"><span data-stu-id="d9e18-117">Voicemail is available for routing inbound calls to users</span></span> | <span data-ttu-id="d9e18-118">ボイスメールに送信する着信呼び出しを有効にします。</span><span class="sxs-lookup"><span data-stu-id="d9e18-118">Enables inbound calls to be sent to voicemail.</span></span> <span data-ttu-id="d9e18-119">有効なオプションは、**常に有効になっている**、**常に無効になっている**、または**ユーザーを制御**します。</span><span class="sxs-lookup"><span data-stu-id="d9e18-119">Valid options are **Always enabled**, **Always disabled**, or **User controlled**.</span></span> |
|<span data-ttu-id="d9e18-120">グループを呼び出すに着信呼び出しをルーティングすることができます。</span><span class="sxs-lookup"><span data-stu-id="d9e18-120">Inbound calls can be routed to call groups</span></span> | <span data-ttu-id="d9e18-121">呼び出しグループに着信を転送できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="d9e18-121">Controls whether incoming calls can be forwarded to a call group.</span></span>  |
|<span data-ttu-id="d9e18-122">着信および発信通話の委任を許可します。</span><span class="sxs-lookup"><span data-stu-id="d9e18-122">Allow delegation for inbound and outbound calls</span></span> | <span data-ttu-id="d9e18-123">デリゲートを使用してルーティングする着信呼び出しを有効に対象のアクセス許可を委任するがユーザーのための発信呼び出しを行うためのデリゲートを使用できます。</span><span class="sxs-lookup"><span data-stu-id="d9e18-123">Enables inbound calls to be routed to delegates; allows delegates to make outbound calls on behalf of the users for whom they have delegated permissions.</span></span> |
|<span data-ttu-id="d9e18-124">有料のバイパスを防止し、PSTN 経由で呼び出しを送信します。</span><span class="sxs-lookup"><span data-stu-id="d9e18-124">Prevent toll bypass and send calls through the PSTN</span></span> | <span data-ttu-id="d9e18-125">これを**On**に設定、PSTN 経由で呼び出しを送信して発生する費用ではなく、ネットワークを経由して迂回すること、通行料がかかる。</span><span class="sxs-lookup"><span data-stu-id="d9e18-125">Setting this to **On** will send calls through PSTN and incur charges rather than going through the network and bypassing the tolls.</span></span> |
|<span data-ttu-id="d9e18-126">呼び出し中に使用可能な時間の時間です。</span><span class="sxs-lookup"><span data-stu-id="d9e18-126">Busy on Busy is available while in a call.</span></span>| <span data-ttu-id="d9e18-127">着信呼び出しを構成するユーザーが通話や会議である場合に処理されます。</span><span class="sxs-lookup"><span data-stu-id="d9e18-127">Configures how incoming calls are handled when a user is already in a call or conference.</span></span> <span data-ttu-id="d9e18-128">ビジー信号を新規または着信呼び出しを拒否できます。</span><span class="sxs-lookup"><span data-stu-id="d9e18-128">New or incoming calls can be rejected with a busy signal.</span></span> |

## <a name="create-a-custom-calling-policy"></a><span data-ttu-id="d9e18-129">カスタムの呼び出し元のポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="d9e18-129">Create a custom calling policy</span></span>

<span data-ttu-id="d9e18-130">この手順では、呼び出し元のユーザー設定の新しいポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="d9e18-130">Follow these steps to create a new custom calling policy.</span></span>

1. <span data-ttu-id="d9e18-131">マイクロソフトのチーム管理センターで、**音声**を選択します > **ポリシーを呼び出すこと**です。</span><span class="sxs-lookup"><span data-stu-id="d9e18-131">In the Microsoft Teams admin center, select **Voice** > **Calling policy**.</span></span>
2. <span data-ttu-id="d9e18-132">**新しいポリシー**を選択します。</span><span class="sxs-lookup"><span data-stu-id="d9e18-132">Select **New policy**.</span></span>
3. <span data-ttu-id="d9e18-133">呼び出し元のポリシーで使用する機能をオンにします。</span><span class="sxs-lookup"><span data-stu-id="d9e18-133">Turn on the features that you want to use in your calling policy.</span></span> <span data-ttu-id="d9e18-134">すべての選択は、既定で**オフ**します。</span><span class="sxs-lookup"><span data-stu-id="d9e18-134">All selections are **Off** by default.</span></span>
4. <span data-ttu-id="d9e18-135">ユーザーが着信通話をボイスメールにルーティングできるかどうかを制御するには、**常に有効になっている**か、**ユーザーが制御**を選択します。</span><span class="sxs-lookup"><span data-stu-id="d9e18-135">To control whether users can route inbound calls to voicemail, select **Always enabled** or **User controlled**.</span></span> <span data-ttu-id="d9e18-136">ボイスメールにルーティングするには、**常に無効になっている**を選択します。</span><span class="sxs-lookup"><span data-stu-id="d9e18-136">To prevent routing to voicemail, select **Always disabled**.</span></span>
5. <span data-ttu-id="d9e18-137">**保存**を選択します。</span><span class="sxs-lookup"><span data-stu-id="d9e18-137">Select **Save**.</span></span>

## <a name="modify-an-existing-calling-policy"></a><span data-ttu-id="d9e18-138">既存のポリシーの呼び出しを変更します。</span><span class="sxs-lookup"><span data-stu-id="d9e18-138">Modify an existing calling policy</span></span>

<span data-ttu-id="d9e18-139">既存のポリシーの呼び出しを変更するのにはこれらの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="d9e18-139">Follow these steps to modify an existing calling policy.</span></span>

1. <span data-ttu-id="d9e18-140">マイクロソフトのチーム管理センターで、**音声**を選択します > **ポリシーを呼び出すこと**です。</span><span class="sxs-lookup"><span data-stu-id="d9e18-140">In the Microsoft Teams admin center, select **Voice** > **Calling policy**.</span></span>
2. <span data-ttu-id="d9e18-141">ポリシーを変更して、[**編集**] を選択するをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d9e18-141">Click next to the policy that you want to modify, and then select **Edit**.</span></span>
3. <span data-ttu-id="d9e18-142">呼び出し元のポリシーで使用する機能をオンにします。</span><span class="sxs-lookup"><span data-stu-id="d9e18-142">Turn on the features that you want to use in your calling policy.</span></span> <span data-ttu-id="d9e18-143">すべての選択は、既定で**オフ**します。</span><span class="sxs-lookup"><span data-stu-id="d9e18-143">All selections are **Off** by default.</span></span>
4. <span data-ttu-id="d9e18-144">ユーザーが着信通話をボイスメールにルーティングできるかどうかを制御するには、**常に有効になっている**か、**ユーザーが制御**を選択します。</span><span class="sxs-lookup"><span data-stu-id="d9e18-144">To control whether users can route inbound calls to voicemail, select **Always enabled** or **User controlled**.</span></span> <span data-ttu-id="d9e18-145">ボイスメールにルーティングするには、**常に無効になっている**を選択します。</span><span class="sxs-lookup"><span data-stu-id="d9e18-145">To prevent routing to voicemail, select **Always disabled**.</span></span>
5. <span data-ttu-id="d9e18-146">**保存**を選択します。</span><span class="sxs-lookup"><span data-stu-id="d9e18-146">Select **Save**.</span></span>

## <a name="assign-a-calling-policy-to-a-user"></a><span data-ttu-id="d9e18-147">呼び出し元のポリシーをユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="d9e18-147">Assign a calling policy to a user</span></span>

<span data-ttu-id="d9e18-148">カスタムの呼び出し元のポリシーをユーザーに割り当てるにはこれらの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="d9e18-148">Follow these steps to assign a custom calling policy to a user.</span></span>

1. <span data-ttu-id="d9e18-149">マイクロソフトのチーム管理センターで、**音声**を選択します > **ポリシーを呼び出すこと**です。</span><span class="sxs-lookup"><span data-stu-id="d9e18-149">In the Microsoft Teams admin center, select **Voice** > **Calling policy**.</span></span>
2. <span data-ttu-id="d9e18-150">選択し、**ユーザーの管理**を選択し、ポリシー名の横にあるをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d9e18-150">Click next to the policy name to select it, and then select **Manage users**.</span></span>
3. <span data-ttu-id="d9e18-151">**ユーザーの管理**ウィンドウで、ユーザーの名前を探します。</span><span class="sxs-lookup"><span data-stu-id="d9e18-151">In the **Manage users** pane, search for the user’s name.</span></span> <span data-ttu-id="d9e18-152">(3 文字以上を入力する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="d9e18-152">(You must enter at least three characters.)</span></span>
4. <span data-ttu-id="d9e18-153">ユーザーの名を選択し、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d9e18-153">Select the user’s name, and then select **Add**.</span></span>
5. <span data-ttu-id="d9e18-154">**保存**を選択します。</span><span class="sxs-lookup"><span data-stu-id="d9e18-154">Select **Save**.</span></span>
