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
ms.openlocfilehash: 363da62c378a60cb85a9544339dbf7ccd699b7c0
ms.sourcegitcommit: 58fec9aebd80029e1f1e71376efe222f9abf707e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "31517080"
---
<a name="about-upgrade-basic"></a>

# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a><span data-ttu-id="da561-103">Teams のクライアント エクスペリエンスおよび共存モードへの準拠</span><span class="sxs-lookup"><span data-stu-id="da561-103">Teams client experience and conformance to coexistence modes</span></span>

> [!NOTE]
> <span data-ttu-id="da561-104">このページは、ユーザーは、Skype のビジネス ・ モード (SfBOnly、SfBWithTeamsCollab、SfBWithTeamsCollabAndMeetings) のいずれかで、時に、チームのクライアントの動作で、最近リリースされた重要な変更の内容を説明します。</span><span class="sxs-lookup"><span data-stu-id="da561-104">This page describes important, recently released changes in the behavior of Teams client when users are in any of the Skype for Business modes (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings).</span></span>


<span data-ttu-id="da561-105">共存モードの目的は、エクスペリエンスを提供する単純かつ予測可能なエンド ・ ユーザーの組織の移行とビジネス用の Skype からのチームには。</span><span class="sxs-lookup"><span data-stu-id="da561-105">The purpose of co-existence modes is to provide a simple, predictable experience for end users as organizations transition from Skype for Business to Teams.</span></span>  <span data-ttu-id="da561-106">チームに移動する組織、TeamsOnly モードは、各ユーザーの最終的な宛先を同時に TeamsOnly (または他のモード) に割り当てられる必要はないすべてのユーザーです。</span><span class="sxs-lookup"><span data-stu-id="da561-106">For an organization moving to Teams, the TeamsOnly mode is the final destination for each user, though not all users need to be assigned TeamsOnly (or any other mode) at the same time.</span></span>  <span data-ttu-id="da561-107">ユーザーが TeamsOnly モードに到達する前に、組織は Skype for Business の任意のモード (SfBOnly、SfBWithTeamsCollab、SfBWithTeamsCollabAndMeetings) を使用して、TeamsOnly であるユーザーとまだ TeamsOnly ではないユーザー間の予測可能な通信を確保することができます。</span><span class="sxs-lookup"><span data-stu-id="da561-107">Prior to users reaching TeamsOnly mode, organizations can use any of the Skype for Business modes (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) to ensure predictable communication between users who are TeamsOnly and those who aren’t yet.</span></span> 

<span data-ttu-id="da561-108">ユーザーは、Skype のビジネス モードのいずれかでは、ビジネスのクライアントのユーザーの Skype にすべての着信のチャットや通話がルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="da561-108">When a user is in any of the Skype for Business modes, all incoming chats and calls are routed to the user’s Skype for Business client.</span></span> <span data-ttu-id="da561-109">エンド ・ ユーザーの混乱を防止し、適切なルーティングを確保する、ユーザーは、Skype のビジネス モードのいずれかで、チームのクライアントでの通話やチャットの機能が無効になります。</span><span class="sxs-lookup"><span data-stu-id="da561-109">To avoid end user confusion and ensure proper routing, calling and chat functionality in the Teams client is disabled when a user is in any of the Skype for Business modes.</span></span> <span data-ttu-id="da561-110">同様に、チームでミーティングのスケジュール設定は SfBOnly または SfBWithTeamsCollab モードでは、ユーザーがいる場合は明示的に無効になってし、SfBWithTeamsCollabAndMeetings モードでは、ユーザーとを明示的に有効にします。</span><span class="sxs-lookup"><span data-stu-id="da561-110">Similarly, meeting scheduling in Teams is explicitly disabled when users are in the SfBOnly or SfBWithTeamsCollab modes, and explicitly enabled when a user is in the SfBWithTeamsCollabAndMeetings mode.</span></span>   

## <a name="how-the-available-functionality-in-teams-client-changes-based-on-mode"></a><span data-ttu-id="da561-111">モードに基づくチームのクライアントで利用可能な機能がどのように変化するか</span><span class="sxs-lookup"><span data-stu-id="da561-111">How the available functionality in Teams client changes based on mode</span></span>
<span data-ttu-id="da561-112">チームで利用可能な機能は、TeamsUpgradePolicy によって設定されるユーザーの共存モードとは異なります。</span><span class="sxs-lookup"><span data-stu-id="da561-112">The available functionality in Teams depends on the user's coexistence mode, as set by TeamsUpgradePolicy.</span></span> <span data-ttu-id="da561-113">次の表は、動作をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="da561-113">The table below summarizes the  behavior:</span></span>

|<span data-ttu-id="da561-114">ユーザーの有効なモード</span><span class="sxs-lookup"><span data-stu-id="da561-114">User's effective mode</span></span>|<span data-ttu-id="da561-115">チームのクライアントで発生します。</span><span class="sxs-lookup"><span data-stu-id="da561-115">Experience in Teams client</span></span>|
|---|---|
|<span data-ttu-id="da561-116">ビジネス モードでは、Skype</span><span class="sxs-lookup"><span data-stu-id="da561-116">Any Skype for Business mode</span></span>|<span data-ttu-id="da561-117">通話とチャット<sup>1</sup>が無効になります。</span><span class="sxs-lookup"><span data-stu-id="da561-117">Calling and Chat<sup>1</sup> are disabled.</span></span>|
|<span data-ttu-id="da561-118">SfBWithTeamsCollabAndMeetings</span><span class="sxs-lookup"><span data-stu-id="da561-118">SfBWithTeamsCollabAndMeetings</span></span>|<span data-ttu-id="da561-119">会議のスケジュール設定があります。</span><span class="sxs-lookup"><span data-stu-id="da561-119">Meeting scheduling is available</span></span>|
|<span data-ttu-id="da561-120">SfBWithTeamsCollab または SfBOnly の<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="da561-120">SfBWithTeamsCollab or SfBOnly<sup>2</sup></span></span>|<span data-ttu-id="da561-121">会議のスケジュール設定は使用できません。</span><span class="sxs-lookup"><span data-stu-id="da561-121">Meeting scheduling is not available</span></span>|
|||

<span data-ttu-id="da561-122">次のスクリーン ショットは、TeamsOnly または島のモードとその他のすべてのモードの違いを示しています。</span><span class="sxs-lookup"><span data-stu-id="da561-122">The following screenshots illustrate the difference between TeamsOnly or Islands mode and all other modes.</span></span> <span data-ttu-id="da561-123">チャットと通話のアイコンは、TeamsOnly または島モード (スクリーン ショットを左)、しない場合は、その他のモード (右のスクリーン ショット) で使用に注意してください。</span><span class="sxs-lookup"><span data-stu-id="da561-123">Note that the chat and calling icons are available with TeamsOnly or Islands mode (left screenshot), but not with the other modes (right screenshot):</span></span>

![チーム モードの比較を示しています。](media/teams-mode-comparison.png)


 
<span data-ttu-id="da561-125">**メモ:**
<sup>1</sup>会議チャットが利用できます。</span><span class="sxs-lookup"><span data-stu-id="da561-125">**Notes:**
<sup>1</sup> Meeting chat is still available.</span></span>

<span data-ttu-id="da561-126"><sup>2</sup>ここでは、SfBwithTeamsCollab と SfBOnly の動作は同じですが、SfBOnly モードでもチームでのチャネル、およびファイルの機能を無効にすることが目的ただし、設定されていない現在無効にするチームでこの機能を可能にします。</span><span class="sxs-lookup"><span data-stu-id="da561-126"><sup>2</sup> For now, SfBwithTeamsCollab and SfBOnly behave the same, but the intent is for SfBOnly mode to also disable Channels and Files functionality in Teams; however, there is currently no setting that allows this functionality in Teams to be disabled.</span></span>


## <a name="impact-of-mode-on-other-policy-settings"></a><span data-ttu-id="da561-127">モードの他のポリシー設定への影響</span><span class="sxs-lookup"><span data-stu-id="da561-127">Impact of Mode on other policy settings</span></span>
<span data-ttu-id="da561-128">前述のとおり、ユーザーの共存モードへの影響は、ユーザーのチームのクライアントでどのような機能があります。</span><span class="sxs-lookup"><span data-stu-id="da561-128">As described above, a user's coexistence mode impact's what functionality is available in the user's Teams client.</span></span> <span data-ttu-id="da561-129">これは、あるモードの値が優先モードによって、他のポリシー設定の値を意味します。</span><span class="sxs-lookup"><span data-stu-id="da561-129">This means that the value of mode can take precedence over the value of other policy settings, depending on the mode.</span></span> <span data-ttu-id="da561-130">具体的には、共存モードは、次のポリシー設定を有効にするかどうか影響します。</span><span class="sxs-lookup"><span data-stu-id="da561-130">Specifically,  coexistence mode impacts whether the following policy settings are honored:</span></span>

|<span data-ttu-id="da561-131">**モーダルかどうか (アプリケーション)**</span><span class="sxs-lookup"><span data-stu-id="da561-131">**Modality (App)**</span></span>|<span data-ttu-id="da561-132">**Policy.Setting**</span><span class="sxs-lookup"><span data-stu-id="da561-132">**Policy.Setting**</span></span>|
|---|---|
|<span data-ttu-id="da561-133">チャット</span><span class="sxs-lookup"><span data-stu-id="da561-133">Chat</span></span>|<span data-ttu-id="da561-134">TeamsMessagingPolicy.AllowUserChat</span><span class="sxs-lookup"><span data-stu-id="da561-134">TeamsMessagingPolicy.AllowUserChat</span></span>|
|<span data-ttu-id="da561-135">通話</span><span class="sxs-lookup"><span data-stu-id="da561-135">Calling</span></span>|<span data-ttu-id="da561-136">TeamsCallingPolicy.AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="da561-136">TeamsCallingPolicy.AllowPrivateCalling</span></span>|
|<span data-ttu-id="da561-137">会議のスケジュール</span><span class="sxs-lookup"><span data-stu-id="da561-137">Meeting scheduling</span></span>|<span data-ttu-id="da561-138">TeamsMeetingPolicy.AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="da561-138">TeamsMeetingPolicy.AllowPrivateMeetingScheduling</span></span></br><span data-ttu-id="da561-139">TeamsMeetingPolicy.AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="da561-139">TeamsMeetingPolicy.AllowChannelMeetingScheduling</span></span>|
|||

<span data-ttu-id="da561-140">管理者が必要*ない*共存モードが、それが重要であるこれらの設定効果的に動作する次のように特定のモードを理解するときにこれらのポリシー設定を明示的に設定します。</span><span class="sxs-lookup"><span data-stu-id="da561-140">Administrators need *not* explicitly set these policy settings when using co-existence mode, but it's important to understand that these settings effectively behave as follows for a given mode.</span></span> 

|<span data-ttu-id="da561-141">Mode</span><span class="sxs-lookup"><span data-stu-id="da561-141">Mode</span></span>|<span data-ttu-id="da561-142">AllowUserChat</span><span class="sxs-lookup"><span data-stu-id="da561-142">AllowUserChat</span></span>|<span data-ttu-id="da561-143">AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="da561-143">AllowPrivateCalling</span></span>|<span data-ttu-id="da561-144">AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="da561-144">AllowPrivateMeetingScheduling</span></span>|<span data-ttu-id="da561-145">AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="da561-145">AllowChannelMeetingScheduling</span></span>|
|---|---|---|---|---|
|<span data-ttu-id="da561-146">TeamsOnly または諸島</span><span class="sxs-lookup"><span data-stu-id="da561-146">TeamsOnly or Islands</span></span>|<span data-ttu-id="da561-147">有効</span><span class="sxs-lookup"><span data-stu-id="da561-147">Enabled</span></span>|<span data-ttu-id="da561-148">有効</span><span class="sxs-lookup"><span data-stu-id="da561-148">Enabled</span></span>|<span data-ttu-id="da561-149">有効</span><span class="sxs-lookup"><span data-stu-id="da561-149">Enabled</span></span>|<span data-ttu-id="da561-150">有効</span><span class="sxs-lookup"><span data-stu-id="da561-150">Enabled</span></span>|
|<span data-ttu-id="da561-151">SfBWithTeamsCollabAndMeetings</span><span class="sxs-lookup"><span data-stu-id="da561-151">SfBWithTeamsCollabAndMeetings</span></span>|<span data-ttu-id="da561-152">無効</span><span class="sxs-lookup"><span data-stu-id="da561-152">Disabled</span></span>|<span data-ttu-id="da561-153">無効</span><span class="sxs-lookup"><span data-stu-id="da561-153">Disabled</span></span>|<span data-ttu-id="da561-154">有効</span><span class="sxs-lookup"><span data-stu-id="da561-154">Enabled</span></span>|<span data-ttu-id="da561-155">有効</span><span class="sxs-lookup"><span data-stu-id="da561-155">Enabled</span></span>|
|<span data-ttu-id="da561-156">SfBWithTeamsCollab または SfBOnly</span><span class="sxs-lookup"><span data-stu-id="da561-156">SfBWithTeamsCollab or SfBOnly</span></span>|<span data-ttu-id="da561-157">無効</span><span class="sxs-lookup"><span data-stu-id="da561-157">Disabled</span></span>|<span data-ttu-id="da561-158">無効</span><span class="sxs-lookup"><span data-stu-id="da561-158">Disabled</span></span>|<span data-ttu-id="da561-159">無効</span><span class="sxs-lookup"><span data-stu-id="da561-159">Disabled</span></span>|<span data-ttu-id="da561-160">無効</span><span class="sxs-lookup"><span data-stu-id="da561-160">Disabled</span></span>|
||||||

<span data-ttu-id="da561-161">近い将来に、`Grant-CsTeamsUpgradePolicy`コマンドレットがこれらの設定は、TeamsUpgradePolicy によって上書きされますが、その場合を決定するには、TeamsMessagingPolicy、TeamsCallingPolicy、および TeamsMeetingPolicy に対応する設定の構成を確認します。PowerShell では、情報メッセージが提供されます。</span><span class="sxs-lookup"><span data-stu-id="da561-161">In the near future, the `Grant-CsTeamsUpgradePolicy` cmdlet will check the configuration of the corresponding settings in TeamsMessagingPolicy, TeamsCallingPolicy, and TeamsMeetingPolicy to determine if those settings will be superceded by TeamsUpgradePolicy and if so, an informational message is provided in PowerShell.</span></span>  <span data-ttu-id="da561-162">上記で述べたようにこれらのポリシー設定を設定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="da561-162">As noted above,  is no longer necessary to set these other policy settings.</span></span> <span data-ttu-id="da561-163">以下には、次のようにどのような PowerShell の警告の例を示します。</span><span class="sxs-lookup"><span data-stu-id="da561-163">Below is an example of what the PowerShell warning  looks like:</span></span>

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling, however these values will be ignored. This is because you are granting this user TeamsUpgradePolicy with mode=SfBWithTeamsCollab, which causes the Teams client to behave as if they are disabled.`



# <a name="related-topics"></a><span data-ttu-id="da561-164">関連トピック</span><span class="sxs-lookup"><span data-stu-id="da561-164">Related topics</span></span>

[<span data-ttu-id="da561-165">Teams を Skype for Business と一緒に使用する組織向けの移行と相互運用に関するガイダンス</span><span class="sxs-lookup"><span data-stu-id="da561-165">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](https://docs.microsoft.com/en-us/microsoftteams/migration-interop-guidance-for-teams-with-skype)




