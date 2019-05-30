---
title: Teams のクライアント エクスペリエンスおよび共存モードへの準拠
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
description: Teams のクライアントエクスペリエンスと comformance の共存モード
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 08bc09ac316a41dfe7ff39bc741dbaa514f30044
ms.sourcegitcommit: b5949233f8080a6cf0edb4b5e27272214feb1c22
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "34548654"
---
<a name="about-upgrade-basic"></a>

# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a><span data-ttu-id="41494-103">Teams のクライアント エクスペリエンスおよび共存モードへの準拠</span><span class="sxs-lookup"><span data-stu-id="41494-103">Teams client experience and conformance to coexistence modes</span></span>

> [!NOTE]
> <span data-ttu-id="41494-104">このページでは、ユーザーが Skype for Business モード (SfBOnly、Sfbwithteams、SfBWithTeamsCollabAndMeetings) に参加しているときに、Teams クライアントの動作について最近公開された重要な変更点について説明します。</span><span class="sxs-lookup"><span data-stu-id="41494-104">This page describes important, recently released changes in the behavior of Teams client when users are in any of the Skype for Business modes (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings).</span></span>


<span data-ttu-id="41494-105">共存モードの目的は、組織が Skype for Business から Teams に移行するときに、エンドユーザーが簡単で予測可能なエクスペリエンスを提供することです。</span><span class="sxs-lookup"><span data-stu-id="41494-105">The purpose of co-existence modes is to provide a simple, predictable experience for end users as organizations transition from Skype for Business to Teams.</span></span>  <span data-ttu-id="41494-106">チームに移行する組織の場合、Teams Sonly モードは各ユーザーの最終的な送信先です。ただし、すべてのユーザーが同時に Teams Sonly (または他のモード) を割り当てる必要はありません。</span><span class="sxs-lookup"><span data-stu-id="41494-106">For an organization moving to Teams, the TeamsOnly mode is the final destination for each user, though not all users need to be assigned TeamsOnly (or any other mode) at the same time.</span></span>  <span data-ttu-id="41494-107">ユーザーが TeamsOnly モードに到達する前に、組織は Skype for Business の任意のモード (SfBOnly、SfBWithTeamsCollab、SfBWithTeamsCollabAndMeetings) を使用して、TeamsOnly であるユーザーとまだ TeamsOnly ではないユーザー間の予測可能な通信を確保することができます。</span><span class="sxs-lookup"><span data-stu-id="41494-107">Prior to users reaching TeamsOnly mode, organizations can use any of the Skype for Business modes (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) to ensure predictable communication between users who are TeamsOnly and those who aren’t yet.</span></span> 

<span data-ttu-id="41494-108">ユーザーが Skype for Business モードのいずれかに入っている場合、着信するすべてのチャットと通話はユーザーの Skype for Business クライアントにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="41494-108">When a user is in any of the Skype for Business modes, all incoming chats and calls are routed to the user’s Skype for Business client.</span></span> <span data-ttu-id="41494-109">ユーザーが Skype for Business モードのいずれかを使用している場合、エンドユーザーの混乱を回避して、適切なルーティング、チームクライアントの通話、チャット機能を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="41494-109">To avoid end user confusion and ensure proper routing, calling and chat functionality in the Teams client is disabled when a user is in any of the Skype for Business modes.</span></span> <span data-ttu-id="41494-110">同様に、Teams での会議のスケジュール設定は、ユーザーが SfBOnly または Sfbwithteams・ SfBWithTeamsCollabAndMeetings モードになっているときに明示的に無効にし、ユーザーがモードにあるときに明示的に有効にします。</span><span class="sxs-lookup"><span data-stu-id="41494-110">Similarly, meeting scheduling in Teams is explicitly disabled when users are in the SfBOnly or SfBWithTeamsCollab modes, and explicitly enabled when a user is in the SfBWithTeamsCollabAndMeetings mode.</span></span>   

## <a name="how-the-available-functionality-in-teams-client-changes-based-on-mode"></a><span data-ttu-id="41494-111">チームクライアントで利用できる機能がモードに基づいてどのように変化するか</span><span class="sxs-lookup"><span data-stu-id="41494-111">How the available functionality in Teams client changes based on mode</span></span>
<span data-ttu-id="41494-112">Teams で利用できる機能は、TeamsUpgradePolicy によって設定されるユーザーの共存モードによって異なります。</span><span class="sxs-lookup"><span data-stu-id="41494-112">The available functionality in Teams depends on the user's coexistence mode, as set by TeamsUpgradePolicy.</span></span> <span data-ttu-id="41494-113">次の表は、動作をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="41494-113">The table below summarizes the  behavior:</span></span>

|<span data-ttu-id="41494-114">ユーザーの有効モード</span><span class="sxs-lookup"><span data-stu-id="41494-114">User's effective mode</span></span>|<span data-ttu-id="41494-115">Teams クライアントでの操作</span><span class="sxs-lookup"><span data-stu-id="41494-115">Experience in Teams client</span></span>|
|---|---|
|<span data-ttu-id="41494-116">任意の Skype for Business モード</span><span class="sxs-lookup"><span data-stu-id="41494-116">Any Skype for Business mode</span></span>|<span data-ttu-id="41494-117">通話とチャットは使用できません。</span><span class="sxs-lookup"><span data-stu-id="41494-117">Calling and Chat are disabled.</span></span>|
|<span data-ttu-id="41494-118">SfBWithTeamsCollabAndMeetings</span><span class="sxs-lookup"><span data-stu-id="41494-118">SfBWithTeamsCollabAndMeetings</span></span>|<span data-ttu-id="41494-119">会議のスケジュールを使用できます</span><span class="sxs-lookup"><span data-stu-id="41494-119">Meeting scheduling is available</span></span>|
|<span data-ttu-id="41494-120">Sfbwithteamsの小条件<sup>1</sup>または Sfbのみ</span><span class="sxs-lookup"><span data-stu-id="41494-120">SfBWithTeamsCollab or SfBOnly<sup>1</sup></span></span>|<span data-ttu-id="41494-121">会議のスケジュールを使用できない</span><span class="sxs-lookup"><span data-stu-id="41494-121">Meeting scheduling is not available</span></span>|
|||

<span data-ttu-id="41494-122">次のスクリーンショットは、TeamsOnly モードとその他のすべてのモードの違いを示しています。</span><span class="sxs-lookup"><span data-stu-id="41494-122">The following screenshots illustrate the difference between TeamsOnly or Islands mode and all other modes.</span></span> <span data-ttu-id="41494-123">チャットと通話のアイコンは、TeamsOnly または諸島モード (左のスクリーンショット) で利用できますが、その他のモード (右のスクリーンショット) では使用できません。</span><span class="sxs-lookup"><span data-stu-id="41494-123">Note that the chat and calling icons are available with TeamsOnly or Islands mode (left screenshot), but not with the other modes (right screenshot):</span></span>

![Teams のモードの並列比較](media/teams-mode-comparison.png)


 
<span data-ttu-id="41494-125">**注:**
<sup></sup>現時点では、sfbwithteamscollab と sfbは同じように動作しますが、sfbonly モードの場合は、Teams のチャネルとファイルの機能も無効にすることを目的としています。ただし、現在のところ、Teams でこの機能を無効にできる設定はありません。</span><span class="sxs-lookup"><span data-stu-id="41494-125">**Note:**
<sup>1</sup> For now, SfBwithTeamsCollab and SfBOnly behave the same, but the intent is for SfBOnly mode to also disable Channels and Files functionality in Teams; however, there is currently no setting that allows this functionality in Teams to be disabled.</span></span>


## <a name="impact-of-mode-on-other-policy-settings"></a><span data-ttu-id="41494-126">他のポリシー設定でのモードの影響</span><span class="sxs-lookup"><span data-stu-id="41494-126">Impact of Mode on other policy settings</span></span>
<span data-ttu-id="41494-127">上で説明したように、ユーザーの共存モードの影響は、ユーザーのチームクライアントで利用できる機能です。</span><span class="sxs-lookup"><span data-stu-id="41494-127">As described above, a user's coexistence mode impact's what functionality is available in the user's Teams client.</span></span> <span data-ttu-id="41494-128">これは、モードに応じて、他のポリシー設定の値よりもモードの値が優先されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="41494-128">This means that the value of mode can take precedence over the value of other policy settings, depending on the mode.</span></span> <span data-ttu-id="41494-129">特に、共存モードでは、次のポリシー設定が有効になっているかどうかが影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="41494-129">Specifically,  coexistence mode impacts whether the following policy settings are honored:</span></span>

|<span data-ttu-id="41494-130">**モダリティ (アプリ)**</span><span class="sxs-lookup"><span data-stu-id="41494-130">**Modality (App)**</span></span>|<span data-ttu-id="41494-131">**ポリシー。設定**</span><span class="sxs-lookup"><span data-stu-id="41494-131">**Policy.Setting**</span></span>|
|---|---|
|<span data-ttu-id="41494-132">チャット</span><span class="sxs-lookup"><span data-stu-id="41494-132">Chat</span></span>|<span data-ttu-id="41494-133">Teams の Messagingポリシー AllowUserChat</span><span class="sxs-lookup"><span data-stu-id="41494-133">TeamsMessagingPolicy.AllowUserChat</span></span>|
|<span data-ttu-id="41494-134">通話</span><span class="sxs-lookup"><span data-stu-id="41494-134">Calling</span></span>|<span data-ttu-id="41494-135">TeamAllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="41494-135">TeamsCallingPolicy.AllowPrivateCalling</span></span>|
|<span data-ttu-id="41494-136">会議のスケジュール</span><span class="sxs-lookup"><span data-stu-id="41494-136">Meeting scheduling</span></span>|<span data-ttu-id="41494-137">TeamsMeetingPolicy.AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="41494-137">TeamsMeetingPolicy.AllowPrivateMeetingScheduling</span></span></br><span data-ttu-id="41494-138">TeamsMeetingPolicy の会議のスケジュール</span><span class="sxs-lookup"><span data-stu-id="41494-138">TeamsMeetingPolicy.AllowChannelMeetingScheduling</span></span>|
|||

<span data-ttu-id="41494-139">管理者は、共存モードの使用時にこれらのポリシー設定を明示的に設定する必要はあり*ません*が、これらの設定が特定のモードで次のように効率的に動作することを理解しておくことが重要です。</span><span class="sxs-lookup"><span data-stu-id="41494-139">Administrators need *not* explicitly set these policy settings when using co-existence mode, but it's important to understand that these settings effectively behave as follows for a given mode.</span></span> 

|<span data-ttu-id="41494-140">Mode</span><span class="sxs-lookup"><span data-stu-id="41494-140">Mode</span></span>|<span data-ttu-id="41494-141">AllowUserChat</span><span class="sxs-lookup"><span data-stu-id="41494-141">AllowUserChat</span></span>|<span data-ttu-id="41494-142">AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="41494-142">AllowPrivateCalling</span></span>|<span data-ttu-id="41494-143">AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="41494-143">AllowPrivateMeetingScheduling</span></span>|<span data-ttu-id="41494-144">Allowchannel会議のスケジュール</span><span class="sxs-lookup"><span data-stu-id="41494-144">AllowChannelMeetingScheduling</span></span>|
|---|---|---|---|---|
|<span data-ttu-id="41494-145">TeamsOnly または諸島</span><span class="sxs-lookup"><span data-stu-id="41494-145">TeamsOnly or Islands</span></span>|<span data-ttu-id="41494-146">有効</span><span class="sxs-lookup"><span data-stu-id="41494-146">Enabled</span></span>|<span data-ttu-id="41494-147">有効</span><span class="sxs-lookup"><span data-stu-id="41494-147">Enabled</span></span>|<span data-ttu-id="41494-148">有効</span><span class="sxs-lookup"><span data-stu-id="41494-148">Enabled</span></span>|<span data-ttu-id="41494-149">有効</span><span class="sxs-lookup"><span data-stu-id="41494-149">Enabled</span></span>|
|<span data-ttu-id="41494-150">SfBWithTeamsCollabAndMeetings</span><span class="sxs-lookup"><span data-stu-id="41494-150">SfBWithTeamsCollabAndMeetings</span></span>|<span data-ttu-id="41494-151">無効</span><span class="sxs-lookup"><span data-stu-id="41494-151">Disabled</span></span>|<span data-ttu-id="41494-152">無効</span><span class="sxs-lookup"><span data-stu-id="41494-152">Disabled</span></span>|<span data-ttu-id="41494-153">有効</span><span class="sxs-lookup"><span data-stu-id="41494-153">Enabled</span></span>|<span data-ttu-id="41494-154">有効</span><span class="sxs-lookup"><span data-stu-id="41494-154">Enabled</span></span>|
|<span data-ttu-id="41494-155">Sfbwithteamsの各アシスタントまたは Sfbのみ</span><span class="sxs-lookup"><span data-stu-id="41494-155">SfBWithTeamsCollab or SfBOnly</span></span>|<span data-ttu-id="41494-156">無効</span><span class="sxs-lookup"><span data-stu-id="41494-156">Disabled</span></span>|<span data-ttu-id="41494-157">無効</span><span class="sxs-lookup"><span data-stu-id="41494-157">Disabled</span></span>|<span data-ttu-id="41494-158">無効</span><span class="sxs-lookup"><span data-stu-id="41494-158">Disabled</span></span>|<span data-ttu-id="41494-159">無効</span><span class="sxs-lookup"><span data-stu-id="41494-159">Disabled</span></span>|
||||||

<span data-ttu-id="41494-160">PowerShell を使用して`Grant-CsTeamsUpgradePolicy`いる場合、コマンドレットは、TeamsMessagingPolicy、TeamTeamsMeetingPolicy のポリシー、およびの対応する設定の構成を確認し、それらの設定が TeamsUpgradePolicy によって置き換えられるかどうかを判断します。情報メッセージは PowerShell で提供されます。</span><span class="sxs-lookup"><span data-stu-id="41494-160">When using PowerShell, the `Grant-CsTeamsUpgradePolicy` cmdlet checks the configuration of the corresponding settings in TeamsMessagingPolicy, TeamsCallingPolicy, and TeamsMeetingPolicy to determine if those settings would be superceded by TeamsUpgradePolicy and if so, an informational message is provided in PowerShell.</span></span>  <span data-ttu-id="41494-161">上記で説明したように、他のポリシー設定を設定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="41494-161">As noted above,  is no longer necessary to set these other policy settings.</span></span> <span data-ttu-id="41494-162">以下に、PowerShell の警告の例を示します。</span><span class="sxs-lookup"><span data-stu-id="41494-162">Below is an example of what the PowerShell warning looks like:</span></span>

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling, however these values will be ignored. This is because you are granting this user TeamsUpgradePolicy with mode=SfBWithTeamsCollab, which causes the Teams client to behave as if they are disabled.`



# <a name="related-topics"></a><span data-ttu-id="41494-163">関連トピック</span><span class="sxs-lookup"><span data-stu-id="41494-163">Related topics</span></span>

[<span data-ttu-id="41494-164">Teams を Skype for Business と一緒に使用する組織向けの移行と相互運用に関するガイダンス</span><span class="sxs-lookup"><span data-stu-id="41494-164">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](https://docs.microsoft.com/en-us/microsoftteams/migration-interop-guidance-for-teams-with-skype)




