---
title: Teams のクライアント エクスペリエンスおよび共存モードへの準拠
author: dearbeen
ms.author: bjwhalen
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
description: クライアント エクスペリエンスのチームとの共存モードに comformance
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6972a09a169560d255c2bb118f80dbbdfb2c7f4f
ms.sourcegitcommit: 8e5fc1d8c19a7f26f53e40b23dd6476a8c6d805f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/26/2019
ms.locfileid: "30800133"
---
<a name="about-upgrade-basic"></a>

# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a><span data-ttu-id="31cd9-103">Teams のクライアント エクスペリエンスおよび共存モードへの準拠</span><span class="sxs-lookup"><span data-stu-id="31cd9-103">Teams client experience and conformance to coexistence modes</span></span>

> [!NOTE]
> <span data-ttu-id="31cd9-104">このページは、ユーザーは、Skype のビジネス ・ モード (SfBOnly、SfBWithTeamsCollab、SfBWithTeamsCollabAndMeetings) のいずれかで、時に、チームのクライアントの動作に重要な今後の変更点を説明します。</span><span class="sxs-lookup"><span data-stu-id="31cd9-104">This page describes important upcoming changes in the behavior of Teams client when users are in any of the Skype for Business modes (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings).</span></span>


<span data-ttu-id="31cd9-105">共存モードの目的は、エクスペリエンスを提供する単純かつ予測可能なエンド ・ ユーザーの組織の移行とビジネス用の Skype からのチームには。</span><span class="sxs-lookup"><span data-stu-id="31cd9-105">The purpose of co-existence modes is to provide a simple, predictable experience for end users as organizations transition from Skype for Business to Teams.</span></span>  <span data-ttu-id="31cd9-106">チームに移動する組織、TeamsOnly モードは、各ユーザーの最終的な宛先を同時に TeamsOnly (または他のモード) に割り当てられる必要はないすべてのユーザーです。</span><span class="sxs-lookup"><span data-stu-id="31cd9-106">For an organization moving to Teams, the TeamsOnly mode is the final destination for each user, though not all users need to be assigned TeamsOnly (or any other mode) at the same time.</span></span>  <span data-ttu-id="31cd9-107">ユーザーが TeamsOnly モードに到達する前に、組織は Skype for Business の任意のモード (SfBOnly、SfBWithTeamsCollab、SfBWithTeamsCollabAndMeetings) を使用して、TeamsOnly であるユーザーとまだ TeamsOnly ではないユーザー間の予測可能な通信を確保することができます。</span><span class="sxs-lookup"><span data-stu-id="31cd9-107">Prior to users reaching TeamsOnly mode, organizations can use any of the Skype for Business modes (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) to ensure predictable communication between users who are TeamsOnly and those who aren’t yet.</span></span> 

<span data-ttu-id="31cd9-108">ユーザーは、Skype のビジネス モードのいずれかでは、ビジネスのクライアントのユーザーの Skype にすべての着信のチャットや通話がルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="31cd9-108">When a user is in any of the Skype for Business modes, all incoming chats and calls are routed to the user’s Skype for Business client.</span></span> <span data-ttu-id="31cd9-109">エンド ユーザーが混乱することを回避し、適切なルーティングを実現するため、Teams クライアントの通話とチャット機能は、ユーザーがいずれかの Skype for Business モードにある場合は無効になるように意図されています。</span><span class="sxs-lookup"><span data-stu-id="31cd9-109">To avoid end user confusion and ensure proper routing, calling and chat functionality in the Teams client is intended to be disabled when a user is in any of the Skype for Business modes.</span></span> <span data-ttu-id="31cd9-110">同様に、Teams での会議のスケジュールも、ユーザーが SfBOnly または SfBWithTeamsCollab モードの場合は明示的に無効になるように、そしてユーザーが SfBWithTeamsCollabAndMeetings の場合に明示的に有効になるように意図されています。</span><span class="sxs-lookup"><span data-stu-id="31cd9-110">Similarly, meeting scheduling in Teams is intended to be explicitly disabled when users are in the SfBOnly or SfBWithTeamsCollab modes, and explicitly enabled when a user is in the SfBWithTeamsCollabAndMeetings mode.</span></span>  <span data-ttu-id="31cd9-111">自動的に無効にする機能チャットし、機能を呼び出す会議のモードに基づいてスケジュール設定を有効または無効とは今すぐ開始タップの顧客に公開します。</span><span class="sxs-lookup"><span data-stu-id="31cd9-111">The functionality to automatically disable chat and calling functionality, as well as enable/disable meeting scheduling based on mode is now starting to rollout to TAP customers.</span></span>  

<span data-ttu-id="31cd9-112">この機能では、前にマイクロソフトのガイダンスは、メッセージングの呼び出し、およびミーティングのポリシーに対応する設定を設定することによって適切なユーザー エクスペリエンスを確実にしました。</span><span class="sxs-lookup"><span data-stu-id="31cd9-112">Prior to this functionality, Microsoft’s guidance was to ensure the proper user experience by setting the corresponding settings in Messaging, Calling and Meeting policies.</span></span> <span data-ttu-id="31cd9-113">ただしの仮の強制がなかったし、チーム クライアント内のすべての機能へのフル アクセスがあるユーザーは既定であるため一部のユーザーでそのモードに関係なく、チーム クライアントでこれらのエクスペリエンスの一部またはすべてへのアクセスが保持している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="31cd9-113">However, there was no formal enforcement of this, and since users by default had full access to all functionality in the Teams client, some users may have retained access to some or all of these  experiences in the Teams client, regardless of their mode.</span></span>  <span data-ttu-id="31cd9-114">その結果、この機能を発表と一部のユーザー可能性がありますを参照してくださいチーム クライアントで自分の経験では変更・ モードに準拠するようにユーザーの操作が開始されます。</span><span class="sxs-lookup"><span data-stu-id="31cd9-114">As a result, as this functionality rolls out, some users may see a change in their experience in the Teams client as the user experience begins to conform to their mode.</span></span>  <span data-ttu-id="31cd9-115">次の表は、新しい動作を示しています。</span><span class="sxs-lookup"><span data-stu-id="31cd9-115">The table below shows the new behavior:</span></span>


|<span data-ttu-id="31cd9-116">ユーザーの有効なモード</span><span class="sxs-lookup"><span data-stu-id="31cd9-116">User's effective mode</span></span>|<span data-ttu-id="31cd9-117">チームのクライアントで発生します。</span><span class="sxs-lookup"><span data-stu-id="31cd9-117">Experience in Teams client</span></span>|
|---|---|
|<span data-ttu-id="31cd9-118">ビジネス モードでは、Skype</span><span class="sxs-lookup"><span data-stu-id="31cd9-118">Any Skype for Business mode</span></span>|<span data-ttu-id="31cd9-119">通話とチャット<sup>1</sup>が無効になります。</span><span class="sxs-lookup"><span data-stu-id="31cd9-119">Calling and Chat<sup>1</sup> are disabled.</span></span>|
|<span data-ttu-id="31cd9-120">SfBWithTeamsCollabAndMeetings</span><span class="sxs-lookup"><span data-stu-id="31cd9-120">SfBWithTeamsCollabAndMeetings</span></span>|<span data-ttu-id="31cd9-121">会議のスケジュール設定があります。</span><span class="sxs-lookup"><span data-stu-id="31cd9-121">Meeting scheduling is available</span></span>|
|<span data-ttu-id="31cd9-122">SfBWithTeamsCollab または SfBOnly の<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="31cd9-122">SfBWithTeamsCollab or SfBOnly<sup>2</sup></span></span>|<span data-ttu-id="31cd9-123">会議のスケジュール設定は使用できません。</span><span class="sxs-lookup"><span data-stu-id="31cd9-123">Meeting scheduling is not available</span></span>|
|||

<span data-ttu-id="31cd9-124">**メモ:**
<sup>1</sup>会議チャットが利用できます。</span><span class="sxs-lookup"><span data-stu-id="31cd9-124">**Notes:**
<sup>1</sup> Meeting chat is still available.</span></span>

<span data-ttu-id="31cd9-125"><sup>2</sup>ここでは、SfBwithTeamsCollab と SfBOnly の動作は同じですが、SfBOnly モードでもチームでのチャネル、およびファイルの機能を無効にすることが目的ただし、設定されていない現在無効にするチームでこの機能を可能にします。</span><span class="sxs-lookup"><span data-stu-id="31cd9-125"><sup>2</sup> For now, SfBwithTeamsCollab and SfBOnly behave the same, but the intent is for SfBOnly mode to also disable Channels and Files functionality in Teams; however, there is currently no setting that allows this functionality in Teams to be disabled.</span></span>


## <a name="how-organizations-can-prepare-for-automatic-ux-conformance-to-modes"></a><span data-ttu-id="31cd9-126">モード自動ユーザー エクスペリエンスへの準拠の組織をどのように準備することができます。</span><span class="sxs-lookup"><span data-stu-id="31cd9-126">How organizations can prepare for automatic UX conformance to modes</span></span>

<span data-ttu-id="31cd9-127">この変更を展開する前に組織は、このセクションで説明したように追加のポリシーを使用してチームのクライアントで必要なエクスペリエンスを実現できます。</span><span class="sxs-lookup"><span data-stu-id="31cd9-127">Prior to this change rolling out, organizations can achieve the desired experience in the Teams client using additional policies as described in this section.</span></span> <span data-ttu-id="31cd9-128">これにより、展開では、エンド ・ ユーザーのシームレスです。</span><span class="sxs-lookup"><span data-stu-id="31cd9-128">This ensures the rollout is seamless for end users.</span></span> <span data-ttu-id="31cd9-129">変更を発表、これらのポリシーを設定しないことを必要に注意してください。</span><span class="sxs-lookup"><span data-stu-id="31cd9-129">Note that once the change rolls out, setting these policies will NOT be required.</span></span>  <span data-ttu-id="31cd9-130">同様のルーティングに影響をユーザーのチームのクライアントで機能が制限するためにしないようにしている組織は島モードを TeamsOnly モードでは、ユーザーを移動できます。</span><span class="sxs-lookup"><span data-stu-id="31cd9-130">Alternatively, organizations that do not wish for users to have reduced functionality in the Teams client can shift their users to Islands mode or TeamsOnly mode, however that will impact routing as well.</span></span>

<span data-ttu-id="31cd9-131">エンド ユーザー エクスペリエンスを手動で構成するには、管理者は、以下のポリシー設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="31cd9-131">To manually configure the end user experience, administrators use the following policies and settings:</span></span>


|<span data-ttu-id="31cd9-132">**モーダルかどうか (アプリケーション)**</span><span class="sxs-lookup"><span data-stu-id="31cd9-132">**Modality (App)**</span></span>|<span data-ttu-id="31cd9-133">**Policy.Setting**</span><span class="sxs-lookup"><span data-stu-id="31cd9-133">**Policy.Setting**</span></span>|
|---|---|
|<span data-ttu-id="31cd9-134">チャット</span><span class="sxs-lookup"><span data-stu-id="31cd9-134">Chat</span></span>|<span data-ttu-id="31cd9-135">TeamsMessagingPolicy.AllowUserChat</span><span class="sxs-lookup"><span data-stu-id="31cd9-135">TeamsMessagingPolicy.AllowUserChat</span></span>|
|<span data-ttu-id="31cd9-136">通話</span><span class="sxs-lookup"><span data-stu-id="31cd9-136">Calling</span></span>|<span data-ttu-id="31cd9-137">TeamsCallingPolicy.AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="31cd9-137">TeamsCallingPolicy.AllowPrivateCalling</span></span>|
|<span data-ttu-id="31cd9-138">会議のスケジュール</span><span class="sxs-lookup"><span data-stu-id="31cd9-138">Meeting scheduling</span></span>|<span data-ttu-id="31cd9-139">TeamsMeetingPolicy.AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="31cd9-139">TeamsMeetingPolicy.AllowPrivateMeetingScheduling</span></span></br><span data-ttu-id="31cd9-140">TeamsMeetingPolicy.AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="31cd9-140">TeamsMeetingPolicy.AllowChannelMeetingScheduling</span></span>|
|||


<span data-ttu-id="31cd9-141">管理者は、特定のモードには、次の値にこれらの設定を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="31cd9-141">Administrators should set each of these settings to the following values for a given mode:</span></span>

|<span data-ttu-id="31cd9-142">Mode</span><span class="sxs-lookup"><span data-stu-id="31cd9-142">Mode</span></span>|<span data-ttu-id="31cd9-143">AllowUserChat</span><span class="sxs-lookup"><span data-stu-id="31cd9-143">AllowUserChat</span></span>|<span data-ttu-id="31cd9-144">AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="31cd9-144">AllowPrivateCalling</span></span>|<span data-ttu-id="31cd9-145">AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="31cd9-145">AllowPrivateMeetingScheduling</span></span>|<span data-ttu-id="31cd9-146">AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="31cd9-146">AllowChannelMeetingScheduling</span></span>|
|---|---|---|---|---|
|<span data-ttu-id="31cd9-147">TeamsOnly または諸島</span><span class="sxs-lookup"><span data-stu-id="31cd9-147">TeamsOnly or Islands</span></span>|<span data-ttu-id="31cd9-148">有効</span><span class="sxs-lookup"><span data-stu-id="31cd9-148">Enabled</span></span>|<span data-ttu-id="31cd9-149">有効</span><span class="sxs-lookup"><span data-stu-id="31cd9-149">Enabled</span></span>|<span data-ttu-id="31cd9-150">有効</span><span class="sxs-lookup"><span data-stu-id="31cd9-150">Enabled</span></span>|<span data-ttu-id="31cd9-151">有効</span><span class="sxs-lookup"><span data-stu-id="31cd9-151">Enabled</span></span>|
|<span data-ttu-id="31cd9-152">SfBWithTeamsCollabAndMeetings</span><span class="sxs-lookup"><span data-stu-id="31cd9-152">SfBWithTeamsCollabAndMeetings</span></span>|<span data-ttu-id="31cd9-153">無効</span><span class="sxs-lookup"><span data-stu-id="31cd9-153">Disabled</span></span>|<span data-ttu-id="31cd9-154">無効</span><span class="sxs-lookup"><span data-stu-id="31cd9-154">Disabled</span></span>|<span data-ttu-id="31cd9-155">有効</span><span class="sxs-lookup"><span data-stu-id="31cd9-155">Enabled</span></span>|<span data-ttu-id="31cd9-156">有効</span><span class="sxs-lookup"><span data-stu-id="31cd9-156">Enabled</span></span>|
|<span data-ttu-id="31cd9-157">SfBWithTeamsCollab または SfBOnly</span><span class="sxs-lookup"><span data-stu-id="31cd9-157">SfBWithTeamsCollab or SfBOnly</span></span>|<span data-ttu-id="31cd9-158">無効</span><span class="sxs-lookup"><span data-stu-id="31cd9-158">Disabled</span></span>|<span data-ttu-id="31cd9-159">無効</span><span class="sxs-lookup"><span data-stu-id="31cd9-159">Disabled</span></span>|<span data-ttu-id="31cd9-160">無効</span><span class="sxs-lookup"><span data-stu-id="31cd9-160">Disabled</span></span>|<span data-ttu-id="31cd9-161">無効</span><span class="sxs-lookup"><span data-stu-id="31cd9-161">Disabled</span></span>|
||||||

<span data-ttu-id="31cd9-162">モードに基づいてユーザー エクスペリエンスの自動準拠のロールアウトする前に、`Grant-CsTeamsUpgradePolicy`コマンドレットの場合は、これらを決定するには、TeamsMessagingPolicy、TeamsCallingPolicy、および TeamsMeetingPolicy に対応する設定の構成をチェックします。設定は、指定したモードと互換性があります。</span><span class="sxs-lookup"><span data-stu-id="31cd9-162">Prior to the rollout of automatic conformance of the user experience based on modes, the `Grant-CsTeamsUpgradePolicy` cmdlet checks the configuration of the corresponding settings in TeamsMessagingPolicy, TeamsCallingPolicy, and TeamsMeetingPolicy to determine if these settings are compatible with the specified mode.</span></span> <span data-ttu-id="31cd9-163">いずれかが正しく構成されていません場合、は、補助金は成功しますが、警告が行われます PowerShell でどの特定の設定が正しく構成されていないことを示します。</span><span class="sxs-lookup"><span data-stu-id="31cd9-163">If any are not configured properly, the grant will succeed but a warning will be provided in PowerShell indicating which specific settings are not configured properly.</span></span> <span data-ttu-id="31cd9-164">以下のようになりますが、PowerShell の警告の例に示します。</span><span class="sxs-lookup"><span data-stu-id="31cd9-164">Below is an example of what the PowerShell warning could look like:</span></span>

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has effective policy enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling. In the near term, when granting TeamsUpgradePolicy with mode=SfBWithTeamsCollab to a user, you must also separately assign policy to ensure the user has effective policy disabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling. In the future, the capability will automatically honor TeamsUpgradePolicy.`

<span data-ttu-id="31cd9-165">このような警告を表示するには、時に、管理者はチームで互換性のあるエンド ユーザー エクスペリエンスを提供するのには示されているポリシーを後で更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="31cd9-165">Upon seeing such a warning, the administrator should subsequently update the indicated policies to deliver a compatible end user experience in Teams.</span></span> <span data-ttu-id="31cd9-166">管理者が警告の結果として何も対応しないことを決めた場合でも、TeamsMessagingPolicy、TeamsCallingPolicy、TeamsMeetingPolicy の値に応じて、ユーザーは Teams のチャット、通話、会議スケジュール機能を利用できますが、エンド ユーザー エクスペリエンスがわかりにくくなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="31cd9-166">If the administrator decides to take no action as a result of the warning, users may still have access to chat, calling, and/or meeting scheduling capabilities in Teams depending on the values of TeamsMessagingPolicy, TeamsCallingPolicy, and TeamsMeetingPolicy, which may result in a confusing end user experience.</span></span>

<span data-ttu-id="31cd9-167">TeamsUpgradePolicy モードに基づくチーム クライアント エクスペリエンスの自動適合性が利用できると、不要になった必要がありますこれらのポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="31cd9-167">Once automatic conformance of the Teams client experience based on TeamsUpgradePolicy mode is available, it will no longer be necessary to set these policies.</span></span> <span data-ttu-id="31cd9-168">TeamsUpgradePolicy モードの値が優先されますこれらの特定の設定の値をします。</span><span class="sxs-lookup"><span data-stu-id="31cd9-168">The value of TeamsUpgradePolicy mode will take precedence over the values of these specific settings.</span></span> <span data-ttu-id="31cd9-169">自動準拠は、ポリシーの解決中にポリシーのインフラストラクチャで実現します。</span><span class="sxs-lookup"><span data-stu-id="31cd9-169">Automatic conformance is achieved during policy resolution by the policy infrastructure.</span></span> <span data-ttu-id="31cd9-170">さまざまな設定の競合が発生した場合は、AllowUserChat、AllowPrivateCalling、AllowPrivateMeetingScheduling および AllowChannelMeetingScheduling の値をモードに基づいた動作が優先されます。</span><span class="sxs-lookup"><span data-stu-id="31cd9-170">In case of conflict of the different settings, the behavior based on mode will win over the values of AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling and AllowChannelMeetingScheduling.</span></span> <span data-ttu-id="31cd9-171">自動適合性を提供すると後、は、クライアント エクスペリエンスが自動的に適用される、TeamsMessagingPolicy、TeamsCallingPolicy、および TeamsMeetingPolicy の値にかかわらず、管理者に通知する PowerShell の警告が更新されます。</span><span class="sxs-lookup"><span data-stu-id="31cd9-171">Once automatic conformance is delivered, the PowerShell warnings will be updated to inform the administrator that the client experience will automatically apply, despite any values of TeamsMessagingPolicy, TeamsCallingPolicy, and TeamsMeetingPolicy.</span></span>







