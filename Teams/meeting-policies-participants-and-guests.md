---
title: 参加者とゲストの会議ポリシーを管理する
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
- ms.teamsadmincenter.meetingpolicies.participantandguests
- seo-marvel-apr2020
description: 参加者とゲストを対象にTeams設定を管理する方法について学習します。
ms.openlocfilehash: 51d121ab9c537e6ba304045e47b6e875cd98afd6
ms.sourcegitcommit: 2d725b9925696e61e3e7338f890f086e009c28f2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/06/2021
ms.locfileid: "51598725"
---
# <a name="meeting-policy-settings---participants--guests"></a><span data-ttu-id="e1e9f-103">会議ポリシーの設定 - 参加者とゲスト</span><span class="sxs-lookup"><span data-stu-id="e1e9f-103">Meeting policy settings - Participants & guests</span></span>

<span data-ttu-id="e1e9f-104"><a name="bkmeetingparticipants"> </a></span><span class="sxs-lookup"><span data-stu-id="e1e9f-104"><a name="bkmeetingparticipants"> </a></span></span>

<span data-ttu-id="e1e9f-105">これらの設定では、会議への入室が許可されるまでロビーで待機する必要がある会議参加者およびそれらの参加者に許可する会議への参加レベルが制御されます。</span><span class="sxs-lookup"><span data-stu-id="e1e9f-105">These settings control which meeting participants wait in the lobby before they are admitted to the meeting and the level of participation they are allowed in a meeting.</span></span>

- [<span data-ttu-id="e1e9f-106">匿名ユーザーが会議を開始できるようにする</span><span class="sxs-lookup"><span data-stu-id="e1e9f-106">Let anonymous people start a meeting</span></span>](#let-anonymous-people-start-a-meeting)
- [<span data-ttu-id="e1e9f-107">ユーザーの参加を自動的に許可する</span><span class="sxs-lookup"><span data-stu-id="e1e9f-107">Automatically admit people</span></span>](#automatically-admit-people)
- [<span data-ttu-id="e1e9f-108">ダイヤルイン ユーザーによるロビーのバイパスを許可する</span><span class="sxs-lookup"><span data-stu-id="e1e9f-108">Allow dial-in users to bypass the lobby</span></span>](#allow-dial-in-users-to-bypass-the-lobby)
- [<span data-ttu-id="e1e9f-109">ライブ キャプションを有効にする</span><span class="sxs-lookup"><span data-stu-id="e1e9f-109">Enable live captions</span></span>](#enable-live-captions)
- [<span data-ttu-id="e1e9f-110">会議でチャットを許可する</span><span class="sxs-lookup"><span data-stu-id="e1e9f-110">Allow chat in meetings</span></span>](#allow-chat-in-meetings)

> [!NOTE]
><span data-ttu-id="e1e9f-111">会議に参加するためのオプションは、各 Teams グループの設定および接続方法によって異なります。</span><span class="sxs-lookup"><span data-stu-id="e1e9f-111">Options to join a meeting will vary, depending on the settings for each Teams group, and the connection method.</span></span> <span data-ttu-id="e1e9f-112">グループに電話会議があり、それを使用して接続する場合は、「[電話会議](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e1e9f-112">If your group has audio conferencing, and uses it to connect, see [Audio Conferencing](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365).</span></span> <span data-ttu-id="e1e9f-113">Teams グループに電話会議がない場合は、「[Teams で会議に参加](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e1e9f-113">If your Teams group doesn't have audio conferencing, refer to [Join a meeting in Teams](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9).</span></span>

## <a name="let-anonymous-people-start-a-meeting"></a><span data-ttu-id="e1e9f-114">匿名ユーザーが会議を開始できるようにする</span><span class="sxs-lookup"><span data-stu-id="e1e9f-114">Let anonymous people start a meeting</span></span>

<span data-ttu-id="e1e9f-115">この設定は、リーダーレスダイヤルイン会議を可能にする開催者ごとのポリシーです。</span><span class="sxs-lookup"><span data-stu-id="e1e9f-115">This setting is a per-organizer policy that allows for leaderless dial-in conferencing meetings.</span></span> <span data-ttu-id="e1e9f-116">この設定は、組織から認証されたユーザーが参加していない場合でも、ダイヤル インのユーザーが会議に参加できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="e1e9f-116">This setting controls whether dial-in users can join the meeting without an authenticated user from the organization in attendance.</span></span> <span data-ttu-id="e1e9f-117">既定では、この設定はオフになっています。つまり、ダイヤルイン ユーザーは、組織の認証されたユーザーが会議に参加するまでロビーで待機します。</span><span class="sxs-lookup"><span data-stu-id="e1e9f-117">By default, this setting is turned off, which means dial-in users will wait in the lobby until an authenticated user from the organization joins the meeting.</span></span>

> [!NOTE]
> <span data-ttu-id="e1e9f-118">この設定がオフになっていて、ダイヤル イン ユーザーが最初に会議に参加していて、ロビーに配置されている場合、組織のユーザーは、Teams クライアントと共に会議に参加して、ユーザーをロビーから会議室への入室を認める必要があります。</span><span class="sxs-lookup"><span data-stu-id="e1e9f-118">If this setting is turned off and a dial-in user joins the meeting first and is placed in the lobby, an organization user must join the meeting with a Teams client to admit the user from the lobby.</span></span> <span data-ttu-id="e1e9f-119">ダイヤル インのユーザーに使用できるロビー コントロールはありません。</span><span class="sxs-lookup"><span data-stu-id="e1e9f-119">There are no lobby controls available for dialed in users.</span></span>

## <a name="automatically-admit-people"></a><span data-ttu-id="e1e9f-120">ユーザーの参加を自動的に許可する</span><span class="sxs-lookup"><span data-stu-id="e1e9f-120">Automatically admit people</span></span>

<span data-ttu-id="e1e9f-121">これは開催者単位のポリシーです。</span><span class="sxs-lookup"><span data-stu-id="e1e9f-121">This is a per-organizer policy.</span></span> <span data-ttu-id="e1e9f-122">この設定は、ユーザーが会議に直接参加するのか、認証ユーザーにより入室が許可されるまでロビーで待機するのかを制御します。</span><span class="sxs-lookup"><span data-stu-id="e1e9f-122">This setting controls whether people join a meeting directly or wait in the lobby until they are admitted by an authenticated user.</span></span> <span data-ttu-id="e1e9f-123">この設定はダイヤルイン ユーザーには適用されません。</span><span class="sxs-lookup"><span data-stu-id="e1e9f-123">This setting does not apply to dial-in users.</span></span>

![ロビーにいるユーザーとの会議を示すスクリーンショット](media/meeting-policies-lobby.png)

 <span data-ttu-id="e1e9f-125">会議の開催者は、会議出席依頼の [**会議オプション**] をクリックして、スケジュールする会議ごとにこの設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="e1e9f-125">Meeting organizers can click **Meeting Options** in the meeting invitation to change this setting for each meeting they schedule.</span></span>

> [!NOTE]
> <span data-ttu-id="e1e9f-126">[会議] のオプションの設定には、"ロビーをバイパスできるユーザー" のラベルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e1e9f-126">In the meeting options the setting is labeled "Who can bypass the lobby".</span></span> <span data-ttu-id="e1e9f-127">ユーザーの既定の設定を変更すると、そのユーザーによって開催されたすべての新しい会議に適用され、ユーザーが会議のオプションを変更していない以前の会議にも適用されます。</span><span class="sxs-lookup"><span data-stu-id="e1e9f-127">If you change the default setting for any user, it will apply to all new meetings organized by that user and any prior meetings where the user didn't modify Meeting options.</span></span>
  
|<span data-ttu-id="e1e9f-128">値を設定する</span><span class="sxs-lookup"><span data-stu-id="e1e9f-128">Setting value</span></span>  |<span data-ttu-id="e1e9f-129">参加動作</span><span class="sxs-lookup"><span data-stu-id="e1e9f-129">Join behavior</span></span> |
|---------|---------|
|<span data-ttu-id="e1e9f-130">**すべてのユーザー**</span><span class="sxs-lookup"><span data-stu-id="e1e9f-130">**Everyone**</span></span>   |<span data-ttu-id="e1e9f-131">すべての会議参加者は、ロビーで待たずに会議に直接参加します。</span><span class="sxs-lookup"><span data-stu-id="e1e9f-131">All meeting participants join the meeting directly without waiting in the lobby.</span></span> <span data-ttu-id="e1e9f-132">これには、認証されたユーザー、信頼された組織の外部ユーザー (フェデレーション)、ゲスト、匿名ユーザーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e1e9f-132">This includes authenticated users, external users from trusted organizations (federated), guests, and anonymous users.</span></span>     |
|<span data-ttu-id="e1e9f-133">**組織内およびフェデレーション組織のすべてのユーザー**</span><span class="sxs-lookup"><span data-stu-id="e1e9f-133">**Everyone in your organization and federated organizations**</span></span>     |<span data-ttu-id="e1e9f-134">ゲスト ユーザーや信頼された組織のユーザーなど、組織内の認証ユーザーは、ロビーで待たずに会議に直接参加します。</span><span class="sxs-lookup"><span data-stu-id="e1e9f-134">Authenticated users within the organization, including guest users and the users from trusted organizations, join the meeting directly without waiting in the lobby.</span></span>  <span data-ttu-id="e1e9f-135">匿名ユーザーは、ロビーで待機します。</span><span class="sxs-lookup"><span data-stu-id="e1e9f-135">Anonymous users wait in the lobby.</span></span>   |
|<span data-ttu-id="e1e9f-136">**組織内のすべてのユーザー**</span><span class="sxs-lookup"><span data-stu-id="e1e9f-136">**Everyone in your organization**</span></span>    |<span data-ttu-id="e1e9f-137">ゲスト ユーザーを含む組織内の認証ユーザーは、ロビーで待たずに会議に直接参加します。</span><span class="sxs-lookup"><span data-stu-id="e1e9f-137">Authenticated users from within the organization, including guest users, join the meeting directly without waiting in the lobby.</span></span>  <span data-ttu-id="e1e9f-138">信頼された組織および匿名ユーザーのユーザーが、ロビーで待機します。</span><span class="sxs-lookup"><span data-stu-id="e1e9f-138">Users from trusted organizations and anonymous users wait in the lobby.</span></span> <span data-ttu-id="e1e9f-139">これは、既定の設定です。</span><span class="sxs-lookup"><span data-stu-id="e1e9f-139">This is the default setting.</span></span>           |
|<span data-ttu-id="e1e9f-140">**開催者のみ**</span><span class="sxs-lookup"><span data-stu-id="e1e9f-140">**Organizer only**</span></span>    |<span data-ttu-id="e1e9f-141">会議の開催者のみが、ロビーで待たずに会議に直接参加します。</span><span class="sxs-lookup"><span data-stu-id="e1e9f-141">Only meeting organizers can join the meeting directly without waiting in the lobby.</span></span> <span data-ttu-id="e1e9f-142">組織内の認証されたユーザー、ゲストユーザー、信頼された組織からのユーザーと匿名ユーザーを含むそれ以外のすべてのユーザーは、ロビーで待機する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e1e9f-142">Everyone else, including authenticated users within the organization, guest users, users from trusted organizations and anonymous users must wait in the lobby.</span></span>           |

## <a name="allow-dial-in-users-to-bypass-the-lobby"></a><span data-ttu-id="e1e9f-143">ダイヤルイン ユーザーによるロビーのバイパスを許可する</span><span class="sxs-lookup"><span data-stu-id="e1e9f-143">Allow dial-in users to bypass the lobby</span></span>

<span data-ttu-id="e1e9f-144">これは開催者単位のポリシーです。</span><span class="sxs-lookup"><span data-stu-id="e1e9f-144">This is a per-organizer policy.</span></span> <span data-ttu-id="e1e9f-145">この設定では、スマートフォンでダイヤル インするユーザーが会議に直接参加するのか、[**ユーザーの参加を自動的に許可する**] の設定に関わらずロビーで待機するのかを制御します。</span><span class="sxs-lookup"><span data-stu-id="e1e9f-145">This setting controls whether people who dial in by phone join the meeting directly or wait in the lobby regardless of the **Automatically admit people** setting.</span></span> <span data-ttu-id="e1e9f-146">既定では、この設定は [オフ] です。</span><span class="sxs-lookup"><span data-stu-id="e1e9f-146">By default, this setting is turned off.</span></span> <span data-ttu-id="e1e9f-147">この設定をオフにすると、組織のユーザーが Teams クライアントで会議に参加し、そのユーザーに入室を許可するまで、ダイヤルイン ユーザーはロビーで待機します。</span><span class="sxs-lookup"><span data-stu-id="e1e9f-147">When this setting is turned off, dial-in users will wait in the lobby until an organization user joins the meeting with a Teams client and admits them.</span></span> <span data-ttu-id="e1e9f-148">この設定をオンにすると、組織のユーザーが会議に参加したときにダイヤルインユーザーが自動的に会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="e1e9f-148">When this setting is turned on, dial-in users will automatically join the meeting when an organization user joins the meeting.</span></span>

> [!NOTE]
> <span data-ttu-id="e1e9f-149">組織のユーザーが会議に参加する前に、ダイヤルイン ユーザーが会議に参加すると、組織のユーザーがチームのクライアントと共に会議に参加して、そのユーザーを入室させるまで、ダイヤルインユーザーはロビーに入ります。</span><span class="sxs-lookup"><span data-stu-id="e1e9f-149">If a dial-in user joins a meeting before an organization user joins the meeting, they will be placed in the lobby until an organization user joins the meeting using a Teams client and admits them.</span></span> <span data-ttu-id="e1e9f-150">ユーザーの既定の設定を変更すると、そのユーザーによって開催されたすべての新しい会議に適用され、ユーザーが会議のオプションを変更していない以前の会議にも適用されます。</span><span class="sxs-lookup"><span data-stu-id="e1e9f-150">If you change the default setting for any user, it will apply to all new meetings organized by that user and any prior meetings where the user didn't modify Meeting options.</span></span>

## <a name="enable-live-captions"></a><span data-ttu-id="e1e9f-151">ライブ キャプションを有効にする</span><span class="sxs-lookup"><span data-stu-id="e1e9f-151">Enable live captions</span></span>

<span data-ttu-id="e1e9f-152">この設定はユーザーごとのポリシーであり、会議中に適用されます。</span><span class="sxs-lookup"><span data-stu-id="e1e9f-152">This setting is a per-user policy and applies during a meeting.</span></span> <span data-ttu-id="e1e9f-153">この設定は、ユーザーが参加する会議でライブ キャプションを有効または無効にするために、[**ライブ キャプションを有効にする**] オプションを使用できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="e1e9f-153">This setting controls whether the **Turn on live captions** option is available for the user to turn on and turn off live captions in meetings that the user attends.</span></span>  

![[ライブ キャプションを有効にする] オプションが表示されたスクリーンショット](media/meeting-policies-live-captions.png)

|<span data-ttu-id="e1e9f-155">値を設定する</span><span class="sxs-lookup"><span data-stu-id="e1e9f-155">Setting value</span></span> |<span data-ttu-id="e1e9f-156">動作</span><span class="sxs-lookup"><span data-stu-id="e1e9f-156">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="e1e9f-157">**無効だが、ユーザーが上書きできる**</span><span class="sxs-lookup"><span data-stu-id="e1e9f-157">**Disabled but the user can override**</span></span>     | <span data-ttu-id="e1e9f-158">会議中にユーザーのライブ キャプションが自動的に有効になることはありません。</span><span class="sxs-lookup"><span data-stu-id="e1e9f-158">Live captions aren't automatically turned on for the user during a meeting.</span></span> <span data-ttu-id="e1e9f-159">オーバーフロー (**...**) メニューに [**ライブ キャプションを有効にする**] オプションが表示され、それらを有効にします。</span><span class="sxs-lookup"><span data-stu-id="e1e9f-159">The user sees the **Turn on live captions** option in the overflow (**...**) menu to turn them on.</span></span> <span data-ttu-id="e1e9f-160">これは、既定の設定です。</span><span class="sxs-lookup"><span data-stu-id="e1e9f-160">This is the default setting.</span></span> |
|<span data-ttu-id="e1e9f-161">**無効**</span><span class="sxs-lookup"><span data-stu-id="e1e9f-161">**Disabled**</span></span>     | <span data-ttu-id="e1e9f-162">会議中、ユーザーのライブ キャプションが無効になります。</span><span class="sxs-lookup"><span data-stu-id="e1e9f-162">Live captions are disabled for the user during a meeting.</span></span> <span data-ttu-id="e1e9f-163">ユーザーには、それらを有効にするオプションはありません。</span><span class="sxs-lookup"><span data-stu-id="e1e9f-163">The user doesn't have the option to turn them on.</span></span>          |

<span data-ttu-id="e1e9f-164"><a name="bkcontentsharing"> </a></span><span class="sxs-lookup"><span data-stu-id="e1e9f-164"><a name="bkcontentsharing"> </a></span></span>

## <a name="allow-chat-in-meetings"></a><span data-ttu-id="e1e9f-165">会議でチャットを許可する</span><span class="sxs-lookup"><span data-stu-id="e1e9f-165">Allow chat in meetings</span></span>

<span data-ttu-id="e1e9f-166">この設定は、参加者ごとの設定です。</span><span class="sxs-lookup"><span data-stu-id="e1e9f-166">This setting is a per-participant setting.</span></span> <span data-ttu-id="e1e9f-167">この設定は、ユーザーの会議で会議チャットを許可するかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="e1e9f-167">This setting controls whether meeting chat is allowed in the user's meeting.</span></span>

<span data-ttu-id="e1e9f-168"><a name="bkparticipantsandguests"> </a></span><span class="sxs-lookup"><span data-stu-id="e1e9f-168"><a name="bkparticipantsandguests"> </a></span></span>






## <a name="related-topics"></a><span data-ttu-id="e1e9f-169">関連項目</span><span class="sxs-lookup"><span data-stu-id="e1e9f-169">Related topics</span></span>

- [<span data-ttu-id="e1e9f-170">Teams での PowerShell の概要</span><span class="sxs-lookup"><span data-stu-id="e1e9f-170">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="e1e9f-171"> Teams でユーザーにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="e1e9f-171">Assign policies to your users in Teams</span></span>](assign-policies.md)
- [<span data-ttu-id="e1e9f-172">ユーザーから RestrictedAnonymousAccess Teams 会議ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="e1e9f-172">Remove the RestrictedAnonymousAccess Teams meeting policy from users</span></span>](meeting-policies-restricted-anonymous-access.md)
