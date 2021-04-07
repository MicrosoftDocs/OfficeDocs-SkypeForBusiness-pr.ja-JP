---
title: コンテンツ共有の会議ポリシーを管理する
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: sonua, shalenc
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingpolicies.contentsharing
- seo-marvel-apr2020
description: コンテンツ共有用の Teams で会議ポリシー設定を管理する方法について学習します。
ms.openlocfilehash: 7b318ad0025d6c68b041c65d8fbb78cbfbc87723
ms.sourcegitcommit: 2d725b9925696e61e3e7338f890f086e009c28f2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/06/2021
ms.locfileid: "51598774"
---
# <a name="meeting-policy-settings---content-sharing"></a><span data-ttu-id="d4e6a-103">会議ポリシーの設定 - コンテンツの共有</span><span class="sxs-lookup"><span data-stu-id="d4e6a-103">Meeting policy settings - Content sharing</span></span>

<span data-ttu-id="d4e6a-104"><a name="bkcontentsharing"> </a></span><span class="sxs-lookup"><span data-stu-id="d4e6a-104"><a name="bkcontentsharing"> </a></span></span>

<span data-ttu-id="d4e6a-105">この記事では、コンテンツ共有に関連する次の会議ポリシー設定について説明します。</span><span class="sxs-lookup"><span data-stu-id="d4e6a-105">This article describes the following meeting policy settings related to content sharing:</span></span>

- [<span data-ttu-id="d4e6a-106">画面共有モード</span><span class="sxs-lookup"><span data-stu-id="d4e6a-106">Screen sharing mode</span></span>](#screen-sharing-mode)
- [<span data-ttu-id="d4e6a-107">参加者に制御を渡す、または制御を要求する</span><span class="sxs-lookup"><span data-stu-id="d4e6a-107">Allow a participant to give or request control</span></span>](#allow-a-participant-to-give-or-request-control)
- [<span data-ttu-id="d4e6a-108">外部の参加者に制御を渡す、または制御を要求する</span><span class="sxs-lookup"><span data-stu-id="d4e6a-108">Allow an external participant to give or request control</span></span>](#allow-an-external-participant-to-give-or-request-control)
- [<span data-ttu-id="d4e6a-109">PowerPoint の共有を許可する</span><span class="sxs-lookup"><span data-stu-id="d4e6a-109">Allow PowerPoint sharing</span></span>](#allow-powerpoint-sharing)
- [<span data-ttu-id="d4e6a-110">ホワイトボードを許可する</span><span class="sxs-lookup"><span data-stu-id="d4e6a-110">Allow whiteboard</span></span>](#allow-whiteboard)
- [<span data-ttu-id="d4e6a-111">メモの共有を許可する</span><span class="sxs-lookup"><span data-stu-id="d4e6a-111">Allow shared notes</span></span>](#allow-shared-notes)

## <a name="screen-sharing-mode"></a><span data-ttu-id="d4e6a-112">画面共有モード</span><span class="sxs-lookup"><span data-stu-id="d4e6a-112">Screen sharing mode</span></span>

<span data-ttu-id="d4e6a-113">この設定は、開催者ごとのポリシーとユーザーごとのポリシーの組み合わせです。</span><span class="sxs-lookup"><span data-stu-id="d4e6a-113">This setting is a combination of a per-organizer and per-user policies.</span></span> <span data-ttu-id="d4e6a-114">この設定は、ユーザーの会議でデスクトップとウィンドウの共有を許可するかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="d4e6a-114">This setting controls whether desktop and window sharing is allowed in the user's meeting.</span></span> <span data-ttu-id="d4e6a-115">ポリシーが割り当てられていない会議参加者 (匿名参加者、ゲスト参加者、B2B 参加者、フェデレーション参加者など) は、会議開催者のポリシーを継承します。</span><span class="sxs-lookup"><span data-stu-id="d4e6a-115">Meeting participants who don't have any policies assigned (for example, anonymous, guest, B2B, and federated participants) inherit the policy of the meeting organizer.</span></span>

|<span data-ttu-id="d4e6a-116">値を設定する</span><span class="sxs-lookup"><span data-stu-id="d4e6a-116">Setting value</span></span> |<span data-ttu-id="d4e6a-117">動作</span><span class="sxs-lookup"><span data-stu-id="d4e6a-117">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="d4e6a-118">**画面全体**</span><span class="sxs-lookup"><span data-stu-id="d4e6a-118">**Entire screen**</span></span>    | <span data-ttu-id="d4e6a-119">会議では完全なデスクトップ共有とアプリケーション共有が許可されます</span><span class="sxs-lookup"><span data-stu-id="d4e6a-119">Full desktop sharing and application sharing are allowed in the meeting</span></span> |
|<span data-ttu-id="d4e6a-120">**単一アプリケーション**</span><span class="sxs-lookup"><span data-stu-id="d4e6a-120">**Single application**</span></span>   | <span data-ttu-id="d4e6a-121">会議ではアプリケーションの共有が許可されます</span><span class="sxs-lookup"><span data-stu-id="d4e6a-121">Application sharing is allowed in the meeting</span></span>        |
|<span data-ttu-id="d4e6a-122">**無効**</span><span class="sxs-lookup"><span data-stu-id="d4e6a-122">**Disabled**</span></span>     |<span data-ttu-id="d4e6a-123">会議では画面共有とアプリケーション共有が無効になります。</span><span class="sxs-lookup"><span data-stu-id="d4e6a-123">Screen sharing and application sharing turned off in the meeting.</span></span>       |

<span data-ttu-id="d4e6a-124">次の例を見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="d4e6a-124">Let's look at the following example.</span></span>

|<span data-ttu-id="d4e6a-125">ユーザー</span><span class="sxs-lookup"><span data-stu-id="d4e6a-125">User</span></span> |<span data-ttu-id="d4e6a-126">会議ポリシー</span><span class="sxs-lookup"><span data-stu-id="d4e6a-126">Meeting policy</span></span> |<span data-ttu-id="d4e6a-127">画面共有モード</span><span class="sxs-lookup"><span data-stu-id="d4e6a-127">Screen sharing mode</span></span> |
|---------|---------|---------|
|<span data-ttu-id="d4e6a-128">Daniela</span><span class="sxs-lookup"><span data-stu-id="d4e6a-128">Daniela</span></span>  | <span data-ttu-id="d4e6a-129">グローバル</span><span class="sxs-lookup"><span data-stu-id="d4e6a-129">Global</span></span>   | <span data-ttu-id="d4e6a-130">画面全体</span><span class="sxs-lookup"><span data-stu-id="d4e6a-130">Entire screen</span></span> |
|<span data-ttu-id="d4e6a-131">Amanda</span><span class="sxs-lookup"><span data-stu-id="d4e6a-131">Amanda</span></span>   | <span data-ttu-id="d4e6a-132">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="d4e6a-132">Location1MeetingPolicy</span></span>  | <span data-ttu-id="d4e6a-133">無効</span><span class="sxs-lookup"><span data-stu-id="d4e6a-133">Disabled</span></span> |

<span data-ttu-id="d4e6a-134">Daniela が開催する会議では、会議の参加者が画面全体または特定のアプリケーションを共有できます。</span><span class="sxs-lookup"><span data-stu-id="d4e6a-134">Meetings hosted by Daniela allow meeting participants to share their entire screen or a specific application.</span></span> <span data-ttu-id="d4e6a-135">Amanda が Daniela の会議に参加すると、ポリシー設定が無効になっているため、Amanda は自分の画面または特定のアプリケーションを共有できません。</span><span class="sxs-lookup"><span data-stu-id="d4e6a-135">If Amanda joins Daniela's meeting, Amanda can't share her screen or a specific application as her policy setting is disabled.</span></span> <span data-ttu-id="d4e6a-136">Amanda がホストする会議では、割り当てられた画面共有モード ポリシーに関係なく、誰も画面または単一のアプリケーションを共有できません。</span><span class="sxs-lookup"><span data-stu-id="d4e6a-136">In meetings hosted by Amanda, no one is allowed to share their screen or a single application, regardless of the screen sharing mode policy assigned to them.</span></span>  <span data-ttu-id="d4e6a-137">その結果、Daniela は Amanda の会議で画面または 1 つのアプリケーションを共有できないのです。</span><span class="sxs-lookup"><span data-stu-id="d4e6a-137">Consequently, Daniela can't share her screen or a single application in Amanda's meetings.</span></span>  

<span data-ttu-id="d4e6a-138">現在、ユーザーは Google Chrome を使用している場合、Teams 会議でビデオを再生したり画面を共有したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="d4e6a-138">Currently, users can't play video or share their screen in a Teams meeting if they're using Google Chrome.</span></span>

## <a name="allow-a-participant-to-give-or-request-control"></a><span data-ttu-id="d4e6a-139">参加者に制御を渡す、または制御を要求する</span><span class="sxs-lookup"><span data-stu-id="d4e6a-139">Allow a participant to give or request control</span></span>

<span data-ttu-id="d4e6a-140">この設定はユーザーごとのポリシーです。</span><span class="sxs-lookup"><span data-stu-id="d4e6a-140">This setting is a per-user policy.</span></span> <span data-ttu-id="d4e6a-141">この設定は、ユーザーが他の会議参加者に共有デスクトップまたはウィンドウの制御を渡すことができるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="d4e6a-141">This setting controls whether the user can give control of the shared desktop or window to other meeting participants.</span></span> <span data-ttu-id="d4e6a-142">制御を渡すには、画面の上部にカーソルを合わせます。</span><span class="sxs-lookup"><span data-stu-id="d4e6a-142">To give control, hover over the top of the screen.</span></span>

<span data-ttu-id="d4e6a-143">ユーザーに対してこの設定が有効になっている場合、共有セッションの上部のバーに [**制御を渡す**] オプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d4e6a-143">If this setting is turned on for the user, the **Give Control** option is displayed in the top bar in a sharing session.</span></span>

![[制御を渡す] オプションが表示されたスクリーンショット](media/meeting-policies-give-control.png)

<span data-ttu-id="d4e6a-145">ユーザーの設定がオフになっている場合、[ **制御を渡** す] オプションは使用できません。</span><span class="sxs-lookup"><span data-stu-id="d4e6a-145">If the setting is turned off for the user, the **Give Control** option isn't available.</span></span>

![[制御を渡す] オプションが利用できないことを示すスクリーンショット](media/meeting-policies-give-control-not-available.png)

<span data-ttu-id="d4e6a-147">次の例を見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="d4e6a-147">Let's look at the following example.</span></span>

|<span data-ttu-id="d4e6a-148">ユーザー</span><span class="sxs-lookup"><span data-stu-id="d4e6a-148">User</span></span> |<span data-ttu-id="d4e6a-149">会議ポリシー</span><span class="sxs-lookup"><span data-stu-id="d4e6a-149">Meeting policy</span></span>  |<span data-ttu-id="d4e6a-150">参加者に制御を渡す、または制御を要求する</span><span class="sxs-lookup"><span data-stu-id="d4e6a-150">Allow participant to give or request control</span></span> |
|---------|---------|---------|
|<span data-ttu-id="d4e6a-151">Daniela</span><span class="sxs-lookup"><span data-stu-id="d4e6a-151">Daniela</span></span>   | <span data-ttu-id="d4e6a-152">グローバル</span><span class="sxs-lookup"><span data-stu-id="d4e6a-152">Global</span></span>   | <span data-ttu-id="d4e6a-153">オン</span><span class="sxs-lookup"><span data-stu-id="d4e6a-153">On</span></span>       |
|<span data-ttu-id="d4e6a-154">Babek</span><span class="sxs-lookup"><span data-stu-id="d4e6a-154">Babek</span></span>    | <span data-ttu-id="d4e6a-155">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="d4e6a-155">Location1MeetingPolicy</span></span>        | <span data-ttu-id="d4e6a-156">オフ</span><span class="sxs-lookup"><span data-stu-id="d4e6a-156">Off</span></span>   |

<span data-ttu-id="d4e6a-157">Daniela は、分け合ったデスクトップやウィンドウを、分かされた会議の他の参加者に制御できます。</span><span class="sxs-lookup"><span data-stu-id="d4e6a-157">Daniela can give control of the shared desktop or window to other participants in a meeting organized by Babek.</span></span> <span data-ttu-id="d4e6a-158">ただし、分数は他の参加者に制御を渡すのではありません。</span><span class="sxs-lookup"><span data-stu-id="d4e6a-158">However, Babek can't give control to other participants.</span></span>

<span data-ttu-id="d4e6a-159">制御を渡したり、制御要求を受け入れたりすることができるユーザーを PowerShell を使用して制御するには、AllowParticipantGiveRequestControl コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="d4e6a-159">To use PowerShell to control who can give control or accept requests for control, use the AllowParticipantGiveRequestControl cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="d4e6a-160">共有中に共有コンテンツの制御を渡したり受け取ったりするには、両者が Teams デスクトップ クライアントを使用している必要があります。</span><span class="sxs-lookup"><span data-stu-id="d4e6a-160">To give and take control of shared content during sharing, both parties must be using the Teams desktop client.</span></span> <span data-ttu-id="d4e6a-161">いずれかの当事者がブラウザーで Teams を実行している場合、制御はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="d4e6a-161">Control isn't supported when either party is running Teams in a browser.</span></span> <span data-ttu-id="d4e6a-162">これは、修正する予定の技術的制限によるものです。</span><span class="sxs-lookup"><span data-stu-id="d4e6a-162">This is due to a technical limitation that we're planning to fix.</span></span>

## <a name="allow-an-external-participant-to-give-or-request-control"></a><span data-ttu-id="d4e6a-163">外部の参加者に制御を渡す、または制御を要求する</span><span class="sxs-lookup"><span data-stu-id="d4e6a-163">Allow an external participant to give or request control</span></span>

<span data-ttu-id="d4e6a-164">この設定はユーザーごとのポリシーです。</span><span class="sxs-lookup"><span data-stu-id="d4e6a-164">This setting is a per-user policy.</span></span> <span data-ttu-id="d4e6a-165">組織がユーザーに対してこのポリシーを設定したかどうかは、会議の開催者が設定した設定に関係なく、外部参加者が実行できる操作を制御しない。</span><span class="sxs-lookup"><span data-stu-id="d4e6a-165">Whether an organization has set this policy for a user doesn't control what external participants can do, regardless of what the meeting organizer has set.</span></span> <span data-ttu-id="d4e6a-166">このパラメーターは、組織の会議ポリシー内において、共有先が設定した内容に応じて、外部の参加者に共有スクリーンの制御または制御の依頼を許可するかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="d4e6a-166">This parameter controls whether external participants can be given control or request control of the sharer's screen, depending on what the sharer has set within their organization's meeting policies.</span></span> <span data-ttu-id="d4e6a-167">Teams 会議の外部参加者は、次のように分類できます。</span><span class="sxs-lookup"><span data-stu-id="d4e6a-167">External participants in Teams meetings can be categorized as follows:</span></span>  

- <span data-ttu-id="d4e6a-168">匿名ユーザー</span><span class="sxs-lookup"><span data-stu-id="d4e6a-168">Anonymous user</span></span>
- <span data-ttu-id="d4e6a-169">ゲスト ユーザー</span><span class="sxs-lookup"><span data-stu-id="d4e6a-169">Guest users</span></span>  
- <span data-ttu-id="d4e6a-170">B2B ユーザー</span><span class="sxs-lookup"><span data-stu-id="d4e6a-170">B2B user</span></span>
- <span data-ttu-id="d4e6a-171">フェデレーション ユーザー</span><span class="sxs-lookup"><span data-stu-id="d4e6a-171">Federated user</span></span>  

<span data-ttu-id="d4e6a-172">フェデレーション ユーザーが共有中に外部ユーザーに制御を渡すことができるかどうかは、組織の「**外部の参加者に制御を渡す、または制御を要求する**」設定によって制御されます。</span><span class="sxs-lookup"><span data-stu-id="d4e6a-172">Whether federated users can give control to external users while sharing is controlled by the **Allow an external participant to give or request control** setting in their organization.</span></span>

<span data-ttu-id="d4e6a-173">PowerShell を使用して、外部の参加者が制御を渡すことができるか、または制御要求を受け入れることができるかを制御するには、AllowExternalParticipantGiveRequestControl コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="d4e6a-173">To use PowerShell to control whether external participants can give control or accept requests for control, use the AllowExternalParticipantGiveRequestControl cmdlet.</span></span>

### <a name="allow-powerpoint-sharing"></a><span data-ttu-id="d4e6a-174">PowerPoint の共有を許可する</span><span class="sxs-lookup"><span data-stu-id="d4e6a-174">Allow PowerPoint sharing</span></span>

<span data-ttu-id="d4e6a-175">これは、ユーザーごとのポリシーです。</span><span class="sxs-lookup"><span data-stu-id="d4e6a-175">This is a per-user policy.</span></span> <span data-ttu-id="d4e6a-176">この設定は、ユーザーが会議で PowerPoint スライド セットを共有できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="d4e6a-176">This setting controls whether the user can share PowerPoint slide decks in a meeting.</span></span> <span data-ttu-id="d4e6a-177">匿名ユーザー、ゲスト ユーザー、フェデレーション ユーザーを含む外部ユーザーは、会議開催者のポリシーを継承します。</span><span class="sxs-lookup"><span data-stu-id="d4e6a-177">External users, including anonymous, guest, and federated users, inherit the policy of the meeting organizer.</span></span>

<span data-ttu-id="d4e6a-178">次の例を見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="d4e6a-178">Let's look at the following example.</span></span>

|<span data-ttu-id="d4e6a-179">ユーザー</span><span class="sxs-lookup"><span data-stu-id="d4e6a-179">User</span></span> |<span data-ttu-id="d4e6a-180">会議ポリシー</span><span class="sxs-lookup"><span data-stu-id="d4e6a-180">Meeting policy</span></span>  |<span data-ttu-id="d4e6a-181">PowerPoint の共有を許可する</span><span class="sxs-lookup"><span data-stu-id="d4e6a-181">Allow PowerPoint sharing</span></span> |
|---------|---------|---------|
|<span data-ttu-id="d4e6a-182">Daniela</span><span class="sxs-lookup"><span data-stu-id="d4e6a-182">Daniela</span></span>   | <span data-ttu-id="d4e6a-183">グローバル</span><span class="sxs-lookup"><span data-stu-id="d4e6a-183">Global</span></span>   | <span data-ttu-id="d4e6a-184">オン</span><span class="sxs-lookup"><span data-stu-id="d4e6a-184">On</span></span>       |
|<span data-ttu-id="d4e6a-185">Amanda</span><span class="sxs-lookup"><span data-stu-id="d4e6a-185">Amanda</span></span>   | <span data-ttu-id="d4e6a-186">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="d4e6a-186">Location1MeetingPolicy</span></span>        | <span data-ttu-id="d4e6a-187">オフ</span><span class="sxs-lookup"><span data-stu-id="d4e6a-187">Off</span></span>   |

<span data-ttu-id="d4e6a-188">Amanda は、会議の開催者であっても、PowerPoint スライド セットを会議で共有することはできません。</span><span class="sxs-lookup"><span data-stu-id="d4e6a-188">Amanda can't share PowerPoint slide decks in meetings even if she's the meeting organizer.</span></span> <span data-ttu-id="d4e6a-189">Daniela は、会議が Amanda によって開催されている場合でも、PowerPoint スライド セットを共有することができます。</span><span class="sxs-lookup"><span data-stu-id="d4e6a-189">Daniela can share PowerPoint slide decks even if the meeting is organized by Amanda.</span></span> <span data-ttu-id="d4e6a-190">Amanda は、PowerPoint スライド セットを共有できない場合でも、会議の他のユーザーによって共有されている PowerPoint スライド セットを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="d4e6a-190">Amanda can view the PowerPoint slide decks shared by others in the meeting, even though she can't share PowerPoint slide decks.</span></span>

## <a name="allow-whiteboard"></a><span data-ttu-id="d4e6a-191">ホワイトボードを許可する</span><span class="sxs-lookup"><span data-stu-id="d4e6a-191">Allow whiteboard</span></span>

<span data-ttu-id="d4e6a-192">この設定はユーザーごとのポリシーです。</span><span class="sxs-lookup"><span data-stu-id="d4e6a-192">This setting is a per-user policy.</span></span> <span data-ttu-id="d4e6a-193">この設定は、ユーザーが会議でホワイトボードを共有できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="d4e6a-193">This setting controls whether a user can share the whiteboard in a meeting.</span></span> <span data-ttu-id="d4e6a-194">匿名ユーザー、B2B ユーザー、およびフェデレーション ユーザーを含む外部ユーザーは、会議開催者のポリシーを継承します。</span><span class="sxs-lookup"><span data-stu-id="d4e6a-194">External users, including anonymous, B2B, and federated users, inherit the policy of the meeting organizer.</span></span>

<span data-ttu-id="d4e6a-195">次の例を見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="d4e6a-195">Let's look at the following example.</span></span>

|<span data-ttu-id="d4e6a-196">ユーザー</span><span class="sxs-lookup"><span data-stu-id="d4e6a-196">User</span></span> |<span data-ttu-id="d4e6a-197">会議ポリシー</span><span class="sxs-lookup"><span data-stu-id="d4e6a-197">Meeting policy</span></span>  |<span data-ttu-id="d4e6a-198">ホワイトボードを許可する</span><span class="sxs-lookup"><span data-stu-id="d4e6a-198">Allow whiteboard</span></span>|
|---------|---------|---------|
|<span data-ttu-id="d4e6a-199">Daniela</span><span class="sxs-lookup"><span data-stu-id="d4e6a-199">Daniela</span></span>   | <span data-ttu-id="d4e6a-200">グローバル</span><span class="sxs-lookup"><span data-stu-id="d4e6a-200">Global</span></span>   | <span data-ttu-id="d4e6a-201">オン</span><span class="sxs-lookup"><span data-stu-id="d4e6a-201">On</span></span>       |
|<span data-ttu-id="d4e6a-202">Amanda</span><span class="sxs-lookup"><span data-stu-id="d4e6a-202">Amanda</span></span>   | <span data-ttu-id="d4e6a-203">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="d4e6a-203">Location1MeetingPolicy</span></span>        | <span data-ttu-id="d4e6a-204">オフ</span><span class="sxs-lookup"><span data-stu-id="d4e6a-204">Off</span></span>   |

<span data-ttu-id="d4e6a-205">Amanda は、会議の開催者であっても、会議でホワイトボードを共有することはできません。</span><span class="sxs-lookup"><span data-stu-id="d4e6a-205">Amanda can't share the whiteboard in a meeting even if she's the meeting organizer.</span></span> <span data-ttu-id="d4e6a-206">Daniela は、Amanda が会議を開催する場合でも、ホワイトボードを共有することができます。</span><span class="sxs-lookup"><span data-stu-id="d4e6a-206">Daniela can share the whiteboard even if a meeting is organized by Amanda.</span></span>  

## <a name="allow-shared-notes"></a><span data-ttu-id="d4e6a-207">メモの共有を許可する</span><span class="sxs-lookup"><span data-stu-id="d4e6a-207">Allow shared notes</span></span>

<span data-ttu-id="d4e6a-208">この設定はユーザーごとのポリシーです。</span><span class="sxs-lookup"><span data-stu-id="d4e6a-208">This setting is a per-user policy.</span></span> <span data-ttu-id="d4e6a-209">この設定は、ユーザーが会議でメモを作成および共有できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="d4e6a-209">This setting controls whether a user can create and share notes in a meeting.</span></span> <span data-ttu-id="d4e6a-210">匿名ユーザー、B2B ユーザー、およびフェデレーション ユーザーを含む外部ユーザーは、会議開催者のポリシーを継承します。</span><span class="sxs-lookup"><span data-stu-id="d4e6a-210">External users, including anonymous, B2B, and federated users, inherit the policy of the meeting organizer.</span></span> <span data-ttu-id="d4e6a-211">現在、[**会議メモ**] タブは、参加者が 20 人未満の会議でのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="d4e6a-211">The **Meeting Notes** tab is currently only supported in meetings that have fewer than 20 participants.</span></span>

<span data-ttu-id="d4e6a-212">次の例を見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="d4e6a-212">Let's look at the following example.</span></span>

|<span data-ttu-id="d4e6a-213">ユーザー</span><span class="sxs-lookup"><span data-stu-id="d4e6a-213">User</span></span> |<span data-ttu-id="d4e6a-214">会議ポリシー</span><span class="sxs-lookup"><span data-stu-id="d4e6a-214">Meeting policy</span></span>  |<span data-ttu-id="d4e6a-215">メモの共有を許可する</span><span class="sxs-lookup"><span data-stu-id="d4e6a-215">Allow shared notes</span></span> |
|---------|---------|---------|
|<span data-ttu-id="d4e6a-216">Daniela</span><span class="sxs-lookup"><span data-stu-id="d4e6a-216">Daniela</span></span>   | <span data-ttu-id="d4e6a-217">グローバル</span><span class="sxs-lookup"><span data-stu-id="d4e6a-217">Global</span></span>   | <span data-ttu-id="d4e6a-218">オン</span><span class="sxs-lookup"><span data-stu-id="d4e6a-218">On</span></span>       |
|<span data-ttu-id="d4e6a-219">Amanda</span><span class="sxs-lookup"><span data-stu-id="d4e6a-219">Amanda</span></span>   | <span data-ttu-id="d4e6a-220">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="d4e6a-220">Location1MeetingPolicy</span></span> | <span data-ttu-id="d4e6a-221">オフ</span><span class="sxs-lookup"><span data-stu-id="d4e6a-221">Off</span></span> |

<span data-ttu-id="d4e6a-222">Daniela は Amanda の会議でメモを取ることができ、Amanda はすべての会議でメモを取ることができません。</span><span class="sxs-lookup"><span data-stu-id="d4e6a-222">Daniela can take notes in Amanda's meetings and Amanda can't take notes in any meetings.</span></span>




## <a name="related-topics"></a><span data-ttu-id="d4e6a-223">関連項目</span><span class="sxs-lookup"><span data-stu-id="d4e6a-223">Related topics</span></span>

- [<span data-ttu-id="d4e6a-224">Teams での PowerShell の概要</span><span class="sxs-lookup"><span data-stu-id="d4e6a-224">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="d4e6a-225"> Teams でユーザーにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="d4e6a-225">Assign policies to your users in Teams</span></span>](assign-policies.md)
- [<span data-ttu-id="d4e6a-226">ユーザーから RestrictedAnonymousAccess Teams 会議ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="d4e6a-226">Remove the RestrictedAnonymousAccess Teams meeting policy from users</span></span>](meeting-policies-restricted-anonymous-access.md)
