---
title: Teams のクライアント エクスペリエンスおよび共存モードへの準拠
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
audience: admin
description: Teams のクライアント エクスペリエンスおよび共存モードへの準拠
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6e05a95871dbe36f969c048f32d9bca99fec5d45
ms.sourcegitcommit: de7e0afbd40bbe52994ab99d85cf9e95ecbc4a6c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/09/2019
ms.locfileid: "37435241"
---
<a name="about-upgrade-basic"></a>

# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a><span data-ttu-id="b346b-103">Teams のクライアント エクスペリエンスおよび共存モードへの準拠</span><span class="sxs-lookup"><span data-stu-id="b346b-103">Teams client experience and conformance to coexistence modes</span></span>


<span data-ttu-id="b346b-104">Skype for Business の共存モード (SfBOnly、Sfbwithteams での共同作業、SfBWithTeamsCollabAndMeetings) の目的は、エンドユーザーが Skype for Business からチームに移行するときに、簡単で予測可能なエクスペリエンスを提供することです。</span><span class="sxs-lookup"><span data-stu-id="b346b-104">The purpose of the Skype for Business coexistence modes (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) is to provide a simple, predictable experience for end users as organizations transition from Skype for Business to Teams.</span></span>  <span data-ttu-id="b346b-105">チームに移行する組織の場合、**チームのみ**のモードは各ユーザーの最終的な送信先ですが、すべてのユーザーが**チームのみ**(または他のモード) に同時に割り当てる必要はありません。</span><span class="sxs-lookup"><span data-stu-id="b346b-105">For an organization moving to Teams, the **Teams Only** mode is the final destination for each user, though not all users need to be assigned **Teams Only** (or any other mode) at the same time.</span></span>  <span data-ttu-id="b346b-106">ユーザーが Teams の唯一のモードに到達する前に、組織は Skype for Business の共存モードのいずれかを使用して、**チームのみ**で、かつまだお持ちではないユーザー間で一貫した通信を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="b346b-106">Prior to users reaching TeamsOnly mode, organizations can use any of the Skype for Business coexistence modes to ensure predictable communication between users who are **Teams Only** and those who aren’t yet.</span></span> 

<span data-ttu-id="b346b-107">ユーザーが Skype for Business モードのいずれかに入っている場合、着信するすべてのチャットと通話はユーザーの Skype for Business クライアントにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="b346b-107">When a user is in any of the Skype for Business modes, all incoming chats and calls are routed to the user’s Skype for Business client.</span></span> <span data-ttu-id="b346b-108">ユーザーが Skype for Business モードのいずれかを使用している場合、エンドユーザーの混乱を回避して、適切なルーティング、チームクライアントの通話、チャット機能を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="b346b-108">To avoid end user confusion and ensure proper routing, calling and chat functionality in the Teams client is disabled when a user is in any of the Skype for Business modes.</span></span> <span data-ttu-id="b346b-109">同様に、Teams での会議のスケジュール設定は、ユーザーが SfBOnly または Sfbwithteams・ SfBWithTeamsCollabAndMeetings モードになっているときに明示的に無効にし、ユーザーがモードにあるときに明示的に有効にします。</span><span class="sxs-lookup"><span data-stu-id="b346b-109">Similarly, meeting scheduling in Teams is explicitly disabled when users are in the SfBOnly or SfBWithTeamsCollab modes, and explicitly enabled when a user is in the SfBWithTeamsCollabAndMeetings mode.</span></span>

<span data-ttu-id="b346b-110">プレゼンスはチャットと通話での到達可能性を示しているため、チャットや通話が無効になっていると、Teams での自己プレゼンス (つまり、ユーザーの写真の Teams クライアントでの1つのプレゼンスの表示) も非表示になります。</span><span class="sxs-lookup"><span data-stu-id="b346b-110">Because presence is an indication of reachability through chat and calling, when chat and calling are disabled, self-presence in Teams (that is, the display of one’s own presence in the Teams client in the user’s picture) is also hidden.</span></span> 

## <a name="how-the-available-functionality-in-teams-client-changes-based-on-mode"></a><span data-ttu-id="b346b-111">チームクライアントで利用できる機能がモードに基づいてどのように変化するか</span><span class="sxs-lookup"><span data-stu-id="b346b-111">How the available functionality in Teams client changes based on mode</span></span>

<span data-ttu-id="b346b-112">Teams で利用できる機能は、TeamsUpgradePolicy によって設定されるユーザーの共存モードによって異なります。</span><span class="sxs-lookup"><span data-stu-id="b346b-112">The available functionality in Teams depends on the user's coexistence mode, as set by TeamsUpgradePolicy.</span></span> <span data-ttu-id="b346b-113">次の表は、この動作をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="b346b-113">The following table summarizes the behavior:</span></span>

|<span data-ttu-id="b346b-114">ユーザーの有効モード</span><span class="sxs-lookup"><span data-stu-id="b346b-114">User's effective mode</span></span>|<span data-ttu-id="b346b-115">Teams クライアントでの操作</span><span class="sxs-lookup"><span data-stu-id="b346b-115">Experience in Teams client</span></span>|
|---|---|
|<span data-ttu-id="b346b-116">任意の Skype for Business モード</span><span class="sxs-lookup"><span data-stu-id="b346b-116">Any Skype for Business mode</span></span>|<span data-ttu-id="b346b-117">通話、チャット、および自己プレゼンスは無効になります。</span><span class="sxs-lookup"><span data-stu-id="b346b-117">Calling, Chat, and self-presence are disabled.</span></span>|
|<span data-ttu-id="b346b-118">SfBWithTeamsCollabAndMeetings</span><span class="sxs-lookup"><span data-stu-id="b346b-118">SfBWithTeamsCollabAndMeetings</span></span>|<span data-ttu-id="b346b-119">会議のスケジュールを使用できます</span><span class="sxs-lookup"><span data-stu-id="b346b-119">Meeting scheduling is available</span></span>|
|<span data-ttu-id="b346b-120">Sfbwithteamsの小条件<sup>1</sup>または Sfbのみ</span><span class="sxs-lookup"><span data-stu-id="b346b-120">SfBWithTeamsCollab or SfBOnly<sup>1</sup></span></span>|<span data-ttu-id="b346b-121">会議のスケジュールを使用できない</span><span class="sxs-lookup"><span data-stu-id="b346b-121">Meeting scheduling is not available</span></span>|
|||

<span data-ttu-id="b346b-122">次のスクリーンショットは、 **Teams**モードとその他のすべて**のモードの**違いを示しています。</span><span class="sxs-lookup"><span data-stu-id="b346b-122">The following screenshots illustrate the difference between **Teams Only** or **Islands** mode and all other modes.</span></span> <span data-ttu-id="b346b-123">チャットと通話のアイコンは、既定では、 **Teams のみ**または**諸島**モード (左のスクリーンショット) で利用できますが、他のモード (右のスクリーンショット) では使用できません。</span><span class="sxs-lookup"><span data-stu-id="b346b-123">Note that the chat and calling icons are available by default with **Teams Only** or **Islands** mode (left screenshot), but not with the other modes (right screenshot):</span></span>

![Teams のモードの並列比較](media/teams-mode-comparison.png)

<span data-ttu-id="b346b-125">さらに、次に示すように、他のモードでは自己プレゼンスは使用できません。</span><span class="sxs-lookup"><span data-stu-id="b346b-125">In addition, self presence is not available in the other modes, as shown here.</span></span>

![最初に会議の自分のプレゼンスのスクリーンショット](media/meetings-first-no-self-presence-general.png)
 
<span data-ttu-id="b346b-127">**注:**
この時点では、sfbwithteamscollab と sfbonly は<sup>同じように</sup>動作しますが、sfbonly モードの場合は、Teams のチャネルとファイルの機能も無効にします。</span><span class="sxs-lookup"><span data-stu-id="b346b-127">**Note:**
<sup>1</sup> At this time, SfBwithTeamsCollab and SfBOnly behave the same, but the intent is for SfBOnly mode to also disable Channels and Files functionality in Teams.</span></span> <span data-ttu-id="b346b-128">中間では、アプリのアクセス許可ポリシーを使ってチャネルを非表示にすることができます。</span><span class="sxs-lookup"><span data-stu-id="b346b-128">In the interim, Channels can be hidden using the App Permissions policy.</span></span>


## <a name="impact-of-mode-on-other-policy-settings"></a><span data-ttu-id="b346b-129">他のポリシー設定でのモードの影響</span><span class="sxs-lookup"><span data-stu-id="b346b-129">Impact of Mode on other policy settings</span></span>
<span data-ttu-id="b346b-130">上で説明したように、ユーザーの共存モードの影響は、ユーザーのチームクライアントで利用できる機能です。</span><span class="sxs-lookup"><span data-stu-id="b346b-130">As described above, a user's coexistence mode impact's what functionality is available in the user's Teams client.</span></span> <span data-ttu-id="b346b-131">これは、モードに応じて、他のポリシー設定の値よりもモードの値が優先されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="b346b-131">This means that the value of mode can take precedence over the value of other policy settings, depending on the mode.</span></span> <span data-ttu-id="b346b-132">特に、共存モードでは、次のポリシー設定が有効になっているかどうかが影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="b346b-132">Specifically,  coexistence mode impacts whether the following policy settings are honored:</span></span>

|<span data-ttu-id="b346b-133">**モダリティ (アプリ)**</span><span class="sxs-lookup"><span data-stu-id="b346b-133">**Modality (App)**</span></span>|<span data-ttu-id="b346b-134">**ポリシー。設定**</span><span class="sxs-lookup"><span data-stu-id="b346b-134">**Policy.Setting**</span></span>|
|---|---|
|<span data-ttu-id="b346b-135">チャット</span><span class="sxs-lookup"><span data-stu-id="b346b-135">Chat</span></span>|<span data-ttu-id="b346b-136">Teams の Messagingポリシー AllowUserChat</span><span class="sxs-lookup"><span data-stu-id="b346b-136">TeamsMessagingPolicy.AllowUserChat</span></span>|
|<span data-ttu-id="b346b-137">通話</span><span class="sxs-lookup"><span data-stu-id="b346b-137">Calling</span></span>|<span data-ttu-id="b346b-138">TeamAllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="b346b-138">TeamsCallingPolicy.AllowPrivateCalling</span></span>|
|<span data-ttu-id="b346b-139">会議のスケジュール</span><span class="sxs-lookup"><span data-stu-id="b346b-139">Meeting scheduling</span></span>|<span data-ttu-id="b346b-140">TeamsMeetingPolicy.AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="b346b-140">TeamsMeetingPolicy.AllowPrivateMeetingScheduling</span></span></br><span data-ttu-id="b346b-141">TeamsMeetingPolicy の会議のスケジュール</span><span class="sxs-lookup"><span data-stu-id="b346b-141">TeamsMeetingPolicy.AllowChannelMeetingScheduling</span></span>|
|||

<span data-ttu-id="b346b-142">管理者は、共存モードの使用時にこれらのポリシー設定を明示的に設定する必要はあり*ません*が、これらの設定が特定のモードで次のように効率的に動作することを理解しておくことが重要です。</span><span class="sxs-lookup"><span data-stu-id="b346b-142">Administrators need *not* explicitly set these policy settings when using co-existence mode, but it's important to understand that these settings effectively behave as follows for a given mode.</span></span> 

|<span data-ttu-id="b346b-143">Mode</span><span class="sxs-lookup"><span data-stu-id="b346b-143">Mode</span></span>|<span data-ttu-id="b346b-144">AllowUserChat</span><span class="sxs-lookup"><span data-stu-id="b346b-144">AllowUserChat</span></span>|<span data-ttu-id="b346b-145">AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="b346b-145">AllowPrivateCalling</span></span>|<span data-ttu-id="b346b-146">AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="b346b-146">AllowPrivateMeetingScheduling</span></span>|<span data-ttu-id="b346b-147">Allowchannel会議のスケジュール</span><span class="sxs-lookup"><span data-stu-id="b346b-147">AllowChannelMeetingScheduling</span></span>|
|---|---|---|---|---|
|<span data-ttu-id="b346b-148">TeamsOnly または諸島</span><span class="sxs-lookup"><span data-stu-id="b346b-148">TeamsOnly or Islands</span></span>|<span data-ttu-id="b346b-149">有効</span><span class="sxs-lookup"><span data-stu-id="b346b-149">Enabled</span></span>|<span data-ttu-id="b346b-150">有効</span><span class="sxs-lookup"><span data-stu-id="b346b-150">Enabled</span></span>|<span data-ttu-id="b346b-151">有効</span><span class="sxs-lookup"><span data-stu-id="b346b-151">Enabled</span></span>|<span data-ttu-id="b346b-152">有効</span><span class="sxs-lookup"><span data-stu-id="b346b-152">Enabled</span></span>|
|<span data-ttu-id="b346b-153">SfBWithTeamsCollabAndMeetings</span><span class="sxs-lookup"><span data-stu-id="b346b-153">SfBWithTeamsCollabAndMeetings</span></span>|<span data-ttu-id="b346b-154">無効</span><span class="sxs-lookup"><span data-stu-id="b346b-154">Disabled</span></span>|<span data-ttu-id="b346b-155">無効</span><span class="sxs-lookup"><span data-stu-id="b346b-155">Disabled</span></span>|<span data-ttu-id="b346b-156">有効</span><span class="sxs-lookup"><span data-stu-id="b346b-156">Enabled</span></span>|<span data-ttu-id="b346b-157">有効</span><span class="sxs-lookup"><span data-stu-id="b346b-157">Enabled</span></span>|
|<span data-ttu-id="b346b-158">Sfbwithteamsの各アシスタントまたは Sfbのみ</span><span class="sxs-lookup"><span data-stu-id="b346b-158">SfBWithTeamsCollab or SfBOnly</span></span>|<span data-ttu-id="b346b-159">無効</span><span class="sxs-lookup"><span data-stu-id="b346b-159">Disabled</span></span>|<span data-ttu-id="b346b-160">無効</span><span class="sxs-lookup"><span data-stu-id="b346b-160">Disabled</span></span>|<span data-ttu-id="b346b-161">無効</span><span class="sxs-lookup"><span data-stu-id="b346b-161">Disabled</span></span>|<span data-ttu-id="b346b-162">無効</span><span class="sxs-lookup"><span data-stu-id="b346b-162">Disabled</span></span>|
||||||

<span data-ttu-id="b346b-163">PowerShell を使用して`Grant-CsTeamsUpgradePolicy`いる場合、コマンドレットは、TeamsMessagingPolicy、TeamTeamsMeetingPolicy のポリシー、およびの対応する設定の構成を確認し、それらの設定が TeamsUpgradePolicy によって置き換えられるかどうかを判断します。情報メッセージは PowerShell で提供されます。</span><span class="sxs-lookup"><span data-stu-id="b346b-163">When using PowerShell, the `Grant-CsTeamsUpgradePolicy` cmdlet checks the configuration of the corresponding settings in TeamsMessagingPolicy, TeamsCallingPolicy, and TeamsMeetingPolicy to determine if those settings would be superseded by TeamsUpgradePolicy and if so, an informational message is provided in PowerShell.</span></span>  <span data-ttu-id="b346b-164">上記で説明したように、他のポリシー設定を設定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="b346b-164">As noted above,  is no longer necessary to set these other policy settings.</span></span> <span data-ttu-id="b346b-165">次に示すのは、PowerShell の警告の例です。</span><span class="sxs-lookup"><span data-stu-id="b346b-165">The following is an example of what the PowerShell warning looks like:</span></span>

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling, however these values will be ignored. This is because you are granting this user TeamsUpgradePolicy with mode=SfBWithTeamsCollab, which causes the Teams client to behave as if they are disabled.`



# <a name="related-topics"></a><span data-ttu-id="b346b-166">関連トピック</span><span class="sxs-lookup"><span data-stu-id="b346b-166">Related topics</span></span>

[<span data-ttu-id="b346b-167">Teams を Skype for Business と一緒に使用する組織向けの移行と相互運用に関するガイダンス</span><span class="sxs-lookup"><span data-stu-id="b346b-167">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](https://docs.microsoft.com/en-us/microsoftteams/migration-interop-guidance-for-teams-with-skype)




