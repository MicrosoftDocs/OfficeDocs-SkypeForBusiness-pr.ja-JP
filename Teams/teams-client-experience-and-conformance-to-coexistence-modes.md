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
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: eea9d83a582bfe463233cfafe9564a238e00e198
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837377"
---
<a name="about-upgrade-basic"></a>

# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a><span data-ttu-id="05d66-103">Teams のクライアント エクスペリエンスおよび共存モードへの準拠</span><span class="sxs-lookup"><span data-stu-id="05d66-103">Teams client experience and conformance to coexistence modes</span></span>


<span data-ttu-id="05d66-104">Skype for Business 共存モード (SfBOnly、SfBWithTeamsCollab、SfBWithTeamsCollabAndMeetings) の目的は、組織が Skype for Business から Teams に移行する際に、シンプルで予測可能なエクスペリエンスをエンド ユーザーに提供することです。</span><span class="sxs-lookup"><span data-stu-id="05d66-104">The purpose of the Skype for Business coexistence modes (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) is to provide a simple, predictable experience for end users as organizations transition from Skype for Business to Teams.</span></span>  <span data-ttu-id="05d66-105">Teams に移行する組織にとって、最終的にはすべてのユーザーを **TeamsOnly** モードにすることが目標ですが、**TeamsOnly** (またはその他のモード) を全員に同時に割り当てる必要はありません。</span><span class="sxs-lookup"><span data-stu-id="05d66-105">For an organization moving to Teams, the **Teams Only** mode is the final destination for each user, though not all users need to be assigned **Teams Only** (or any other mode) at the same time.</span></span>  <span data-ttu-id="05d66-106">ユーザーが TeamsOnly モードに到達するまでは、組織は Skype for Business 共存モードのいずれかのモードを使用でき、こうすることで、**TeamsOnly** モードのユーザーとまだこのモードに設定されていないユーザーの間で、安定した通信を確保できます。</span><span class="sxs-lookup"><span data-stu-id="05d66-106">Prior to users reaching TeamsOnly mode, organizations can use any of the Skype for Business coexistence modes to ensure predictable communication between users who are **Teams Only** and those who aren’t yet.</span></span> 

<span data-ttu-id="05d66-107">ユーザーがいずれかの Skype for Business モードを使用している場合、受信するすべてのチャットと通話は、ユーザーの Skype for Business クライアントにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="05d66-107">When a user is in any of the Skype for Business modes, all incoming chats and calls are routed to the user’s Skype for Business client.</span></span> <span data-ttu-id="05d66-108">ユーザーがいずれかの Skype for Business モードに設定されている場合、エンド ユーザーを混乱させない適切なルーティングを確保するために、Teams クライアントの通話とチャット機能は無効化されます。</span><span class="sxs-lookup"><span data-stu-id="05d66-108">To avoid end user confusion and ensure proper routing, calling and chat functionality in the Teams client is disabled when a user is in any of the Skype for Business modes.</span></span> <span data-ttu-id="05d66-109">同様に、Teams での会議のスケジュールも、ユーザーが SfBOnly または SfBWithTeamsCollab モードの場合は明示的に無効化され、ユーザーが SfBWithTeamsCollabAndMeetings の場合には明示的に有効化されます。</span><span class="sxs-lookup"><span data-stu-id="05d66-109">Similarly, meeting scheduling in Teams is explicitly disabled when users are in the SfBOnly or SfBWithTeamsCollab modes, and explicitly enabled when a user is in the SfBWithTeamsCollabAndMeetings mode.</span></span>

<span data-ttu-id="05d66-110">プレゼンスはチャットと通話による到達可能性を示す指標です。そのため、チャットと通話が無効になっている場合は、Teams の自己プレゼンス (Teams クライアントでの自分のプレゼンスをユーザーの写真に表示するもの) も非表示になります。</span><span class="sxs-lookup"><span data-stu-id="05d66-110">Because presence is an indication of reachability through chat and calling, when chat and calling are disabled, self-presence in Teams (that is, the display of one’s own presence in the Teams client in the user’s picture) is also hidden.</span></span> 

## <a name="how-the-available-functionality-in-teams-client-changes-based-on-mode"></a><span data-ttu-id="05d66-111">Teams クライアントで使用可能な機能がモードによってどのように変化するか</span><span class="sxs-lookup"><span data-stu-id="05d66-111">How the available functionality in Teams client changes based on mode</span></span>

<span data-ttu-id="05d66-112">Teams で使用できる機能は、TeamsUpgradePolicy で設定されているユーザーの共存モードによって異なります。</span><span class="sxs-lookup"><span data-stu-id="05d66-112">The available functionality in Teams depends on the user's coexistence mode, as set by TeamsUpgradePolicy.</span></span> <span data-ttu-id="05d66-113">次の表は、動作をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="05d66-113">The following table summarizes the behavior:</span></span>

|<span data-ttu-id="05d66-114">ユーザーの有効なモード</span><span class="sxs-lookup"><span data-stu-id="05d66-114">User's effective mode</span></span>|<span data-ttu-id="05d66-115">Teams クライアントでのエクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="05d66-115">Experience in Teams client</span></span>|
|---|---|
|<span data-ttu-id="05d66-116">任意の Skype for Business モード</span><span class="sxs-lookup"><span data-stu-id="05d66-116">Any Skype for Business mode</span></span>|<span data-ttu-id="05d66-117">通話、チャット、および自己プレゼンスは無効です。</span><span class="sxs-lookup"><span data-stu-id="05d66-117">Calling, Chat, and self-presence are disabled.</span></span>|
|<span data-ttu-id="05d66-118">SfBWithTeamsCollabAndMeetings</span><span class="sxs-lookup"><span data-stu-id="05d66-118">SfBWithTeamsCollabAndMeetings</span></span>|<span data-ttu-id="05d66-119">会議のスケジュールを利用できます</span><span class="sxs-lookup"><span data-stu-id="05d66-119">Meeting scheduling is available</span></span>|
|<span data-ttu-id="05d66-120">SfBWithTeamsCollab または SfBOnly<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="05d66-120">SfBWithTeamsCollab or SfBOnly<sup>1</sup></span></span>|<span data-ttu-id="05d66-121">会議のスケジュールは利用できません</span><span class="sxs-lookup"><span data-stu-id="05d66-121">Meeting scheduling is not available</span></span>|
|||

<span data-ttu-id="05d66-122">次のスクリーンショットでは、**TeamsOnly** または**アイランド** モードと、その他のすべてのモードとの違いを示しています。</span><span class="sxs-lookup"><span data-stu-id="05d66-122">The following screenshots illustrate the difference between **Teams Only** or **Islands** mode and all other modes.</span></span> <span data-ttu-id="05d66-123">**TeamsOnly** または**アイランド** モード (左側のスクリーンショット) を使用する場合、既定ではチャットと通話のアイコンが表示されますが、他のモード (右のスクリーンショット) では表示されません。</span><span class="sxs-lookup"><span data-stu-id="05d66-123">Note that the chat and calling icons are available by default with **Teams Only** or **Islands** mode (left screenshot), but not with the other modes (right screenshot):</span></span>

![Teams モードを並べて比較](media/teams-mode-comparison.png)

<span data-ttu-id="05d66-125">また、次に示すように、他のモードでは自己プレゼンスを使用できません。</span><span class="sxs-lookup"><span data-stu-id="05d66-125">In addition, self presence is not available in the other modes, as shown here.</span></span>

![会議を初めて利用したときの自己プレゼンスのスクリーンショット](media/meetings-first-no-self-presence-general.png)
 
<span data-ttu-id="05d66-127">**注:**
<sup>1</sup> 現時点では、SfBwithTeamsCollab と SfBOnly は同じように動作しますが、SfBOnly モードでは、Teams のチャネルとファイル機能も無効にします。</span><span class="sxs-lookup"><span data-stu-id="05d66-127">**Note:**
<sup>1</sup> At this time, SfBwithTeamsCollab and SfBOnly behave the same, but the intent is for SfBOnly mode to also disable Channels and Files functionality in Teams.</span></span> <span data-ttu-id="05d66-128">その間、アプリの権限ポリシーを使用してチャネルを非表示にできます。</span><span class="sxs-lookup"><span data-stu-id="05d66-128">In the interim, Channels can be hidden using the App Permissions policy.</span></span>


## <a name="impact-of-mode-on-other-policy-settings"></a><span data-ttu-id="05d66-129">他のポリシー設定に対するモードの影響</span><span class="sxs-lookup"><span data-stu-id="05d66-129">Impact of Mode on other policy settings</span></span>
<span data-ttu-id="05d66-130">上記のように、ユーザーの共存モードは、ユーザーの Teams クライアントで使用可能な機能に影響を与えます。</span><span class="sxs-lookup"><span data-stu-id="05d66-130">As described above, a user's coexistence mode impact's what functionality is available in the user's Teams client.</span></span> <span data-ttu-id="05d66-131">つまり、モードによっては、モードの値が他のポリシー設定の値よりも優先される場合があります。</span><span class="sxs-lookup"><span data-stu-id="05d66-131">This means that the value of mode can take precedence over the value of other policy settings, depending on the mode.</span></span> <span data-ttu-id="05d66-132">特に、共存モードは、次のポリシー設定が適用されるかどうかに影響します。</span><span class="sxs-lookup"><span data-stu-id="05d66-132">Specifically,  coexistence mode impacts whether the following policy settings are honored:</span></span>

|<span data-ttu-id="05d66-133">**モダリティ (アプリ)**</span><span class="sxs-lookup"><span data-stu-id="05d66-133">**Modality (App)**</span></span>|<span data-ttu-id="05d66-134">**Policy.Setting**</span><span class="sxs-lookup"><span data-stu-id="05d66-134">**Policy.Setting**</span></span>|
|---|---|
|<span data-ttu-id="05d66-135">チャット</span><span class="sxs-lookup"><span data-stu-id="05d66-135">Chat</span></span>|<span data-ttu-id="05d66-136">TeamsMessagingPolicy.AllowUserChat</span><span class="sxs-lookup"><span data-stu-id="05d66-136">TeamsMessagingPolicy.AllowUserChat</span></span>|
|<span data-ttu-id="05d66-137">通話</span><span class="sxs-lookup"><span data-stu-id="05d66-137">Calling</span></span>|<span data-ttu-id="05d66-138">TeamsCallingPolicy.AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="05d66-138">TeamsCallingPolicy.AllowPrivateCalling</span></span>|
|<span data-ttu-id="05d66-139">会議のスケジュール</span><span class="sxs-lookup"><span data-stu-id="05d66-139">Meeting scheduling</span></span>|<span data-ttu-id="05d66-140">TeamsMeetingPolicy.AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="05d66-140">TeamsMeetingPolicy.AllowPrivateMeetingScheduling</span></span></br><span data-ttu-id="05d66-141">TeamsMeetingPolicy.AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="05d66-141">TeamsMeetingPolicy.AllowChannelMeetingScheduling</span></span>|
|||

<span data-ttu-id="05d66-142">共存モードを使用する場合、管理者はこれらのポリシー設定を明示的に設定する必要は*ありません*が、これらの設定は特定のモードに対して次のように効果的に動作することを理解することが重要です。</span><span class="sxs-lookup"><span data-stu-id="05d66-142">Administrators need *not* explicitly set these policy settings when using co-existence mode, but it's important to understand that these settings effectively behave as follows for a given mode.</span></span> 

|<span data-ttu-id="05d66-143">モード</span><span class="sxs-lookup"><span data-stu-id="05d66-143">Mode</span></span>|<span data-ttu-id="05d66-144">AllowUserChat</span><span class="sxs-lookup"><span data-stu-id="05d66-144">AllowUserChat</span></span>|<span data-ttu-id="05d66-145">AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="05d66-145">AllowPrivateCalling</span></span>|<span data-ttu-id="05d66-146">AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="05d66-146">AllowPrivateMeetingScheduling</span></span>|<span data-ttu-id="05d66-147">AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="05d66-147">AllowChannelMeetingScheduling</span></span>|
|---|---|---|---|---|
|<span data-ttu-id="05d66-148">TeamsOnly または アイランド</span><span class="sxs-lookup"><span data-stu-id="05d66-148">TeamsOnly or Islands</span></span>|<span data-ttu-id="05d66-149">有効</span><span class="sxs-lookup"><span data-stu-id="05d66-149">Enabled</span></span>|<span data-ttu-id="05d66-150">有効</span><span class="sxs-lookup"><span data-stu-id="05d66-150">Enabled</span></span>|<span data-ttu-id="05d66-151">有効</span><span class="sxs-lookup"><span data-stu-id="05d66-151">Enabled</span></span>|<span data-ttu-id="05d66-152">有効</span><span class="sxs-lookup"><span data-stu-id="05d66-152">Enabled</span></span>|
|<span data-ttu-id="05d66-153">SfBWithTeamsCollabAndMeetings</span><span class="sxs-lookup"><span data-stu-id="05d66-153">SfBWithTeamsCollabAndMeetings</span></span>|<span data-ttu-id="05d66-154">無効</span><span class="sxs-lookup"><span data-stu-id="05d66-154">Disabled</span></span>|<span data-ttu-id="05d66-155">無効</span><span class="sxs-lookup"><span data-stu-id="05d66-155">Disabled</span></span>|<span data-ttu-id="05d66-156">有効</span><span class="sxs-lookup"><span data-stu-id="05d66-156">Enabled</span></span>|<span data-ttu-id="05d66-157">有効</span><span class="sxs-lookup"><span data-stu-id="05d66-157">Enabled</span></span>|
|<span data-ttu-id="05d66-158">SfBWithTeamsCollab または SfBOnly</span><span class="sxs-lookup"><span data-stu-id="05d66-158">SfBWithTeamsCollab or SfBOnly</span></span>|<span data-ttu-id="05d66-159">無効</span><span class="sxs-lookup"><span data-stu-id="05d66-159">Disabled</span></span>|<span data-ttu-id="05d66-160">無効</span><span class="sxs-lookup"><span data-stu-id="05d66-160">Disabled</span></span>|<span data-ttu-id="05d66-161">無効</span><span class="sxs-lookup"><span data-stu-id="05d66-161">Disabled</span></span>|<span data-ttu-id="05d66-162">無効</span><span class="sxs-lookup"><span data-stu-id="05d66-162">Disabled</span></span>|
||||||

<span data-ttu-id="05d66-163">PowerShell を使用する場合、`Grant-CsTeamsUpgradePolicy` コマンドレットは TeamsMessagingPolicy、TeamsCallingPolicy、および TeamsMeetingPolicy の対応する設定の構成を確認して、これらの設定が TeamsUpgradePolicy によって置き換えられるかどうかを判断し、そうであれば PowerShell で情報メッセージが提供されます。</span><span class="sxs-lookup"><span data-stu-id="05d66-163">When using PowerShell, the `Grant-CsTeamsUpgradePolicy` cmdlet checks the configuration of the corresponding settings in TeamsMessagingPolicy, TeamsCallingPolicy, and TeamsMeetingPolicy to determine if those settings would be superseded by TeamsUpgradePolicy and if so, an informational message is provided in PowerShell.</span></span>  <span data-ttu-id="05d66-164">上記のように、これらの他のポリシー設定を設定する必要はなくなりました。</span><span class="sxs-lookup"><span data-stu-id="05d66-164">As noted above,  is no longer necessary to set these other policy settings.</span></span> <span data-ttu-id="05d66-165">次に、PowerShell の警告の例を示します。</span><span class="sxs-lookup"><span data-stu-id="05d66-165">The following is an example of what the PowerShell warning looks like:</span></span>

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling, however these values will be ignored. This is because you are granting this user TeamsUpgradePolicy with mode=SfBWithTeamsCollab, which causes the Teams client to behave as if they are disabled.`



# <a name="related-topics"></a><span data-ttu-id="05d66-166">関連項目</span><span class="sxs-lookup"><span data-stu-id="05d66-166">Related topics</span></span>

[<span data-ttu-id="05d66-167">Teams を Skype for Business と一緒に使用する組織向けの移行と相互運用に関するガイダンス</span><span class="sxs-lookup"><span data-stu-id="05d66-167">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](https://docs.microsoft.com/en-us/microsoftteams/migration-interop-guidance-for-teams-with-skype)




