---
title: 仮想デスクトップ インフラストラクチャ用の Teams
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 04/10/2019
ms.topic: article
ms.service: msteams
ms.reviewer: rafarhi
audience: admin
description: 仮想化されたデスクトップインフラストラクチャ (VDI) 環境で Microsoft Teams を実行する方法について説明します。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 450fd98d65d092f3cbc684e4efd90691b5e389a1
ms.sourcegitcommit: 69217fb6d6b71081386364db58083eb5d1932c07
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2019
ms.locfileid: "38638807"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a><span data-ttu-id="d6440-103">仮想デスクトップ インフラストラクチャ用の Teams</span><span class="sxs-lookup"><span data-stu-id="d6440-103">Teams for Virtualized Desktop Infrastructure</span></span>

<span data-ttu-id="d6440-104">この記事では、仮想化された環境で Microsoft Teams を使用する場合の要件と制限について説明します。</span><span class="sxs-lookup"><span data-stu-id="d6440-104">This article describes the requirements and limitations for using Microsoft Teams in a virtualized environment.</span></span>

## <a name="what-is-vdi"></a><span data-ttu-id="d6440-105">VDI とは</span><span class="sxs-lookup"><span data-stu-id="d6440-105">What is VDI?</span></span>

<span data-ttu-id="d6440-106">仮想デスクトップインフラストラクチャ (VDI) は、デスクトップオペレーティングシステムと、データセンターの中央サーバー上のアプリケーションをホストする仮想化テクノロジです。</span><span class="sxs-lookup"><span data-stu-id="d6440-106">Virtual Desktop Infrastructure (VDI) is virtualization technology that hosts a desktop operating system and applications on a centralized server in a data center.</span></span> <span data-ttu-id="d6440-107">これにより、完全にセキュリティが設定された一元的な中央集中ソースを持つユーザーに、完全にカスタマイズされたデスクトップエクスペリエンスを提供できます。</span><span class="sxs-lookup"><span data-stu-id="d6440-107">This enables a fully personalized desktop experience to users with a fully secured and compliant centralized source.</span></span> 
 
<span data-ttu-id="d6440-108">現時点では、仮想化された環境内の Teams は、専用の永続的仮想化マシン (VM) での共同作業とチャット機能のサポートによって提供されています。</span><span class="sxs-lookup"><span data-stu-id="d6440-108">Currently, Teams in a virtualized environment is available with support for collaboration and chat functionality with a dedicated persistent virtualized machine (VM).</span></span> <span data-ttu-id="d6440-109">最適なユーザーエクスペリエンスを実現するには、この記事のガイダンスに従ってください。</span><span class="sxs-lookup"><span data-stu-id="d6440-109">To ensure an optimal user experience, follow the guidance in this article.</span></span> 

## <a name="teams-requirements"></a><span data-ttu-id="d6440-110">Teams の要件</span><span class="sxs-lookup"><span data-stu-id="d6440-110">Teams requirements</span></span>

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality-in-teams"></a><span data-ttu-id="d6440-111">チームの呼び出しと会議の機能を無効にするポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="d6440-111">Set policies to turn off calling and meeting functionality in Teams</span></span>

<span data-ttu-id="d6440-112">チームの通話と会議のエクスペリエンスは、VDI 環境 (近日公開) に合わせて最適化されていません。</span><span class="sxs-lookup"><span data-stu-id="d6440-112">The Teams calling and meeting experience isn't optimized for a VDI environment (coming soon).</span></span> <span data-ttu-id="d6440-113">チームの呼び出しと会議の機能を無効にするために、ユーザーレベルのポリシーを設定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d6440-113">We recommend you set user-level policies to turn off calling and meeting functionality in Teams.</span></span>

<span data-ttu-id="d6440-114">また、Teams デスクトップアプリまたは web アプリのいずれかを使用して、VDI で完全にチームを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="d6440-114">You can still choose to run Teams fully in VDI using either the Teams desktop app or web app.</span></span> <span data-ttu-id="d6440-115">ただし、ユーザーエクスペリエンスが侵害されないようにポリシーを設定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d6440-115">However, we recommend that you set the policies to avoid compromising the user experience.</span></span>  

<span data-ttu-id="d6440-116">ポリシーの変更が反映されるまでには、多少時間がかかることがあります。</span><span class="sxs-lookup"><span data-stu-id="d6440-116">It can take some time (a few hours) for the policy changes to propagate.</span></span> <span data-ttu-id="d6440-117">特定のアカウントの変更がすぐに表示されない場合は、数時間後にもう一度お試しください。</span><span class="sxs-lookup"><span data-stu-id="d6440-117">If you don’t see changes for a given account immediately, try again in a few hours.</span></span>

> [!NOTE]
> <span data-ttu-id="d6440-118">仮想デスクトップ環境で使用するためにチームの呼び出しと会議が最適化されている場合は、これらのポリシーを元に戻すことができます。また、ユーザーはチームを通常どおりに使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="d6440-118">When Teams calling and meetings are optimized for use in virtual desktop environments, you can revert these policies and allow users to use Teams as they normally would.</span></span> 

#### <a name="calling"></a><span data-ttu-id="d6440-119">通話</span><span class="sxs-lookup"><span data-stu-id="d6440-119">Calling</span></span>

<span data-ttu-id="d6440-120">**Csteamのポリシー**コマンドレットを使用して、ユーザーがプライベートおよびグループチャットでの呼び出しと呼び出しのオプションを使用できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="d6440-120">Use the **CSTeamsCallingPolicy** cmdlets to control whether users are allowed to use calling and calling options in private and group chats.</span></span> <span data-ttu-id="d6440-121">ポリシー設定と推奨値の一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="d6440-121">Here's the list of policy settings and recommended values.</span></span>

|<span data-ttu-id="d6440-122">ポリシー名</span><span class="sxs-lookup"><span data-stu-id="d6440-122">Policy name</span></span>  |<span data-ttu-id="d6440-123">説明</span><span class="sxs-lookup"><span data-stu-id="d6440-123">Description</span></span> |<span data-ttu-id="d6440-124">推奨値</span><span class="sxs-lookup"><span data-stu-id="d6440-124">Recommended value</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="d6440-125">AllowCalling</span><span class="sxs-lookup"><span data-stu-id="d6440-125">AllowCalling</span></span>    |<span data-ttu-id="d6440-126">相互運用機能呼び出し機能を制御します。</span><span class="sxs-lookup"><span data-stu-id="d6440-126">Controls interop calling capabilities.</span></span> <span data-ttu-id="d6440-127">この機能を有効にすると、Skype for Business ユーザーは Teams ユーザーと1対1の通話を行うことができます。また、その逆も可能です。</span><span class="sxs-lookup"><span data-stu-id="d6440-127">Turning this on allows Skype for Business users to have one-on-one calls with Teams users and vice versa.</span></span>         |<span data-ttu-id="d6440-128">Teams での Skype for Business ユーザーからの通話を防ぐには、False に設定します。</span><span class="sxs-lookup"><span data-stu-id="d6440-128">Set to False to prevent calls from Skype for Business users landing in Teams.</span></span>          |
|<span data-ttu-id="d6440-129">AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="d6440-129">AllowPrivateCalling</span></span>     | <span data-ttu-id="d6440-130">チームクライアントの左側のアプリバーで呼び出し元のアプリを使用できるかどうか、およびプライベートチャットでの通話とビデオ通話のオプションをユーザーに表示するかどうかを制御します</span><span class="sxs-lookup"><span data-stu-id="d6440-130">Controls whether the Calling app is available in the app bar on the left side of the Teams client and whether users see Calling and Video call options in private chat</span></span>         |<span data-ttu-id="d6440-131">[いいえ] に設定すると、チームの左側のアプリバーから呼び出し元アプリが削除され、プライベートチャットで通話とビデオ通話のオプションが削除されます。</span><span class="sxs-lookup"><span data-stu-id="d6440-131">Set to False to remove the Calling app from the app bar on the left side of Teams and to remove the Calling and Video call options in private chat.</span></span>          |

#### <a name="create-and-assign-a-calling-policy"></a><span data-ttu-id="d6440-132">通話ポリシーを作成して割り当てる</span><span class="sxs-lookup"><span data-stu-id="d6440-132">Create and assign a calling policy</span></span>

1. <span data-ttu-id="d6440-133">管理者として Windows PowerShell セッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="d6440-133">Start a Windows PowerShell session as an administrator.</span></span>
2. <span data-ttu-id="d6440-134">Skype オンラインコネクタに接続します。</span><span class="sxs-lookup"><span data-stu-id="d6440-134">Connect to the Skype Online Connector.</span></span>

        # Set Office 365 User Name and Password
        $username = “admin email address”
        password = ConvertTo-SecureString "password" -AsPlainText -Force
        $LiveCred = new-object -typename System.Management.Automation.PSCredential -argumentlist $username, $password
        # Connect to Skype Online
        Import-Module SkypeOnlineConnector
        $sfboSession = New-CsOnlineSession -Credential $LiveCred
        Import-PSSession $sfboSession```

3. <span data-ttu-id="d6440-135">通話ポリシーのオプションの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="d6440-135">View a list of calling policy options.</span></span>

       Get-CsTeamsCallingPolicy
 
4. <span data-ttu-id="d6440-136">すべての通話ポリシーが無効になっているビルトインポリシーオプションを探します。</span><span class="sxs-lookup"><span data-stu-id="d6440-136">Look for the built-in policy option where all calling policies are disabled.</span></span> <span data-ttu-id="d6440-137">次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="d6440-137">It looks like this.</span></span>
   
        Identity                        : Tag:DisallowCalling
        AllowCalling                    : False
        AllowPrivateCalling             : False
        AllowVoicemail                  : False
        AllowCallGroups                 : False
        AllowDelegation                 : False
        AllowUserControl                : False
        AllowCallForwardingToUser       : False
        AllowCallForwardingToPhone      : False
        PreventTollBypass               : False

5. <span data-ttu-id="d6440-138">仮想化された環境で Teams を使用するすべてのユーザーに、DisallowCalling 組み込みポリシーオプションを適用します。</span><span class="sxs-lookup"><span data-stu-id="d6440-138">Apply the DisallowCalling built-in policy option to all users who will be using Teams in a virtualized environment.</span></span>

        Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity “user email id”

<span data-ttu-id="d6440-139">Teams の通話ポリシーの詳細については、「 [Set-Csteamのポリシー](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d6440-139">For more information about Teams calling policies, see [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy).</span></span>

#### <a name="meetings"></a><span data-ttu-id="d6440-140">会議</span><span class="sxs-lookup"><span data-stu-id="d6440-140">Meetings</span></span>

<span data-ttu-id="d6440-141">**CsTeamsMeetingPolicy**コマンドレットを使用して、ユーザーが作成できる会議の種類、会議中にアクセスできる機能、匿名ユーザーと外部ユーザーが使用できる会議機能を制御します。</span><span class="sxs-lookup"><span data-stu-id="d6440-141">Use the **CsTeamsMeetingPolicy** cmdlets to control the type of meetings that users can create, the features that they can access while in a meeting, and the meeting features that are available to anonymous and external users.</span></span> <span data-ttu-id="d6440-142">ポリシー設定と推奨値の一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="d6440-142">Here's the list of policy settings and recommended values.</span></span>

|<span data-ttu-id="d6440-143">ポリシー名</span><span class="sxs-lookup"><span data-stu-id="d6440-143">Policy Name</span></span> |<span data-ttu-id="d6440-144">説明</span><span class="sxs-lookup"><span data-stu-id="d6440-144">Description</span></span>|<span data-ttu-id="d6440-145">推奨値</span><span class="sxs-lookup"><span data-stu-id="d6440-145">Recommended Value</span></span>                   |
|-------------------|-----------------|-----------------------|
|<span data-ttu-id="d6440-146">AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="d6440-146">AllowPrivateMeetingScheduling</span></span>  | <span data-ttu-id="d6440-147">ユーザーがプライベート会議のスケジュールを許可されているかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="d6440-147">Determines whether a user is allowed to schedule private meetings.</span></span>| <span data-ttu-id="d6440-148">ユーザーがプライベート会議をスケジュールできないようにするには、False に設定します。</span><span class="sxs-lookup"><span data-stu-id="d6440-148">Set to False to prohibit the user from being able to schedule private meetings.</span></span>  |
|<span data-ttu-id="d6440-149">Allowchannel会議のスケジュール</span><span class="sxs-lookup"><span data-stu-id="d6440-149">AllowChannelMeetingScheduling</span></span>  | <span data-ttu-id="d6440-150">ユーザーがチャネル会議のスケジュールを許可するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="d6440-150">Determines whether a user is allowed to schedule channel meetings.</span></span> | <span data-ttu-id="d6440-151">ユーザーがチャネル会議のスケジュールを設定できないようにするには、False に設定します。</span><span class="sxs-lookup"><span data-stu-id="d6440-151">Set to False to prohibit the user from being able to schedule channel meetings.</span></span>                       |
|<span data-ttu-id="d6440-152">AllowMeetNow</span><span class="sxs-lookup"><span data-stu-id="d6440-152">AllowMeetNow</span></span> |<span data-ttu-id="d6440-153">ユーザーが臨時の会議の作成または開始を許可されているかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="d6440-153">Determines whether a user is allowed to create or start ad-hoc meetings.</span></span>              |  <span data-ttu-id="d6440-154">ユーザーが臨時の会議を開始できないようにするには、False に設定します。</span><span class="sxs-lookup"><span data-stu-id="d6440-154">Set this to False to prohibit the user from being able to start ad-hoc meetings.</span></span>                     |
|<span data-ttu-id="d6440-155">ScreenSharingMode</span><span class="sxs-lookup"><span data-stu-id="d6440-155">ScreenSharingMode</span></span> | <span data-ttu-id="d6440-156">通話または会議でユーザーが画面を共有できるモードを決定します。</span><span class="sxs-lookup"><span data-stu-id="d6440-156">Determines the mode in which a user is allowed to share their screen in calls or meetings.</span></span> | <span data-ttu-id="d6440-157">ユーザーが画面を共有することを禁止するには、[無効」に設定します。</span><span class="sxs-lookup"><span data-stu-id="d6440-157">Set to Disabled to prohibit the user from sharing their screens</span></span>                          |
|<span data-ttu-id="d6440-158">AllowIPVideo</span><span class="sxs-lookup"><span data-stu-id="d6440-158">AllowIPVideo</span></span> |<span data-ttu-id="d6440-159">ユーザーの会議または通話でビデオが有効になっているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="d6440-159">Determines whether video is enabled in a user's meetings or calls.</span></span>                  |    <span data-ttu-id="d6440-160">ユーザーがビデオを共有することを禁止するには、False に設定します。</span><span class="sxs-lookup"><span data-stu-id="d6440-160">Set to False to prohibit the user from sharing their video</span></span>                                         |
| <span data-ttu-id="d6440-161">AllowAnonymousUsersToDialOut</span><span class="sxs-lookup"><span data-stu-id="d6440-161">AllowAnonymousUsersToDialOut</span></span> | <span data-ttu-id="d6440-162">匿名ユーザーが PSTN 番号へのダイヤルアウトを許可するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="d6440-162">Determines whether anonymous users are allowed to dial out to a PSTN number.</span></span> | <span data-ttu-id="d6440-163">匿名ユーザーによるダイヤルアウトを禁止するには、False に設定します。</span><span class="sxs-lookup"><span data-stu-id="d6440-163">Set to False to prohibit anonymous users from dialing out</span></span>                                  |
| <span data-ttu-id="d6440-164">AllowAnonymousUsersToStartMeeting</span><span class="sxs-lookup"><span data-stu-id="d6440-164">AllowAnonymousUsersToStartMeeting</span></span> | <span data-ttu-id="d6440-165">匿名ユーザーが会議を開始できるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="d6440-165">Determines whether anonymous users can start a meeting.</span></span>     |  <span data-ttu-id="d6440-166">ユーザーが会議を開始することを禁止するには False に設定します。</span><span class="sxs-lookup"><span data-stu-id="d6440-166">Set to False to prohibit users from starting a meeting</span></span>                                            |
| <span data-ttu-id="d6440-167">AllowOutlookAddIn</span><span class="sxs-lookup"><span data-stu-id="d6440-167">AllowOutlookAddIn</span></span> |<span data-ttu-id="d6440-168">ユーザーが Outlook デスクトップクライアントで Teams 会議をスケジュールできるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="d6440-168">Determines whether a user can schedule Teams meetings in the Outlook desktop client.</span></span>| <span data-ttu-id="d6440-169">ユーザーが Outlook デスクトップクライアントで Teams 会議のスケジュールを設定することを禁止するには、False に設定します。</span><span class="sxs-lookup"><span data-stu-id="d6440-169">Set to False to prohibit a user from  scheduling Teams meetings in the Outlook desktop client</span></span>|
| <span data-ttu-id="d6440-170">AllowParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="d6440-170">AllowParticipantGiveRequestControl</span></span>|<span data-ttu-id="d6440-171">参加者が画面共有の制御を要求できるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="d6440-171">Determines whether participants can request or give control of screen sharing.</span></span>| <span data-ttu-id="d6440-172">ユーザーが会議に参加してコントロールを要求することを禁止するには、False に設定します。</span><span class="sxs-lookup"><span data-stu-id="d6440-172">Set to False to prohibit the user from giving and requesting control in a meeting</span></span>    |
| <span data-ttu-id="d6440-173">AllowExternalParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="d6440-173">AllowExternalParticipantGiveRequestControl</span></span> | <span data-ttu-id="d6440-174">外部の参加者が画面共有を要求できるか、制御するかを指定します。</span><span class="sxs-lookup"><span data-stu-id="d6440-174">Determines whether external participants can request or give control of screen sharing.</span></span>| <span data-ttu-id="d6440-175">外部ユーザーによる会議の制御の要求を禁止するには、False に設定します。</span><span class="sxs-lookup"><span data-stu-id="d6440-175">Set to False to prohibit an external user from giving, requesting control in a meeting</span></span>|
|<span data-ttu-id="d6440-176">AllowPowerPointSharing</span><span class="sxs-lookup"><span data-stu-id="d6440-176">AllowPowerPointSharing</span></span>|<span data-ttu-id="d6440-177">ユーザーの会議で PowerPoint での共有が許可されているかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="d6440-177">Determines whether PowerPoint sharing is allowed in a user’s meetings.</span></span> |<span data-ttu-id="d6440-178">ユーザーが会議で PowerPoint ファイルを共有することを禁止するには、False に設定します。</span><span class="sxs-lookup"><span data-stu-id="d6440-178">Set to False to prohibit a user from sharing PowerPoint files in a meeting</span></span>  |
|<span data-ttu-id="d6440-179">AllowWhiteboard</span><span class="sxs-lookup"><span data-stu-id="d6440-179">AllowWhiteboard</span></span> | <span data-ttu-id="d6440-180">ユーザーの会議でホワイトボードが許可されているかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="d6440-180">Determines whether whiteboard is allowed in a user’s meetings.</span></span> |   <span data-ttu-id="d6440-181">会議でホワイトボードを禁止するには False に設定します。</span><span class="sxs-lookup"><span data-stu-id="d6440-181">Set to False to prohibit whiteboard in a meeting</span></span> |
| <span data-ttu-id="d6440-182">AllowTranscription</span><span class="sxs-lookup"><span data-stu-id="d6440-182">AllowTranscription</span></span> |<span data-ttu-id="d6440-183">ユーザーの会議で、リアルタイムまたはポスト会議のキャプションと表記を許可するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="d6440-183">Determines whether real-time and/or post-meeting captions and transcriptions are allowed in a user's meetings.</span></span>|    <span data-ttu-id="d6440-184">会議の議事録とキャプションを禁止するには、False に設定します。</span><span class="sxs-lookup"><span data-stu-id="d6440-184">Set to False to prohibit transcription  and captions in a meeting</span></span>  |  
| <span data-ttu-id="d6440-185">AllowSharedNotes</span><span class="sxs-lookup"><span data-stu-id="d6440-185">AllowSharedNotes</span></span> | <span data-ttu-id="d6440-186">ユーザーが共有ノートを取ることを許可されているかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="d6440-186">Determines whether users are allowed to take shared notes.</span></span> | <span data-ttu-id="d6440-187">ユーザーが共有のノートを取ることを禁止するには False に設定します。</span><span class="sxs-lookup"><span data-stu-id="d6440-187">Set to False to prohibit users from taking shared notes</span></span> |
|<span data-ttu-id="d6440-188">MediaBitRateKB</span><span class="sxs-lookup"><span data-stu-id="d6440-188">MediaBitRateKB</span></span> |<span data-ttu-id="d6440-189">会議でのオーディオ/ビデオ/アプリ共有転送のメディアビットレートを決定します</span><span class="sxs-lookup"><span data-stu-id="d6440-189">Determines the media bit rate for audio/video/app sharing transmissions in meetings</span></span>  | <span data-ttu-id="d6440-190">推奨される値は、5000 (5 MB) です。</span><span class="sxs-lookup"><span data-stu-id="d6440-190">Suggested value is 5000 (5 MB).</span></span> <span data-ttu-id="d6440-191">組織のニーズに合わせて変更できます。</span><span class="sxs-lookup"><span data-stu-id="d6440-191">You can change it based on your organization’s needs.</span></span>| 

#### <a name="create-and-assign-a-meeting-policy"></a><span data-ttu-id="d6440-192">会議のポリシーを作成して割り当てる</span><span class="sxs-lookup"><span data-stu-id="d6440-192">Create and assign a meeting policy</span></span>

1. <span data-ttu-id="d6440-193">管理者として Windows PowerShell セッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="d6440-193">Start a Windows PowerShell session as an administrator.</span></span>
2. <span data-ttu-id="d6440-194">Skype オンラインコネクタに接続します。</span><span class="sxs-lookup"><span data-stu-id="d6440-194">Connect to the Skype Online Connector.</span></span>

        # Set Office 365 User Name and Password
        $username = “admin email address”
        password = ConvertTo-SecureString "password" -AsPlainText -Force
        $LiveCred = new-object -typename System.Management.Automation.PSCredential -argumentlist $username, $password
        # Connect to Skype Online
        Import-Module SkypeOnlineConnector
        $sfboSession = New-CsOnlineSession -Credential $LiveCred
        Import-PSSession $sfboSession```

3. <span data-ttu-id="d6440-195">会議のポリシーオプションの一覧を表示する。</span><span class="sxs-lookup"><span data-stu-id="d6440-195">View a list of meeting policy options.</span></span>

       Get-CsTeamsMeetingPolicy
 
4. <span data-ttu-id="d6440-196">すべての会議ポリシーが無効になっている組み込みのポリシーオプションを探します。</span><span class="sxs-lookup"><span data-stu-id="d6440-196">Look for the built-in policy option where all meeting policies are disabled.</span></span> <span data-ttu-id="d6440-197">次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="d6440-197">It looks like this.</span></span>
   
        Identity                                    : Tag:AllOff
        Description                                 :
        AllowChannelMeetingScheduling               : False
        AllowMeetNow                                : False
        AllowIPVideo                                : False
        AllowAnonymousUsersToDialOut                : False
        AllowAnonymousUsersToStartMeeting           : False
        AllowPrivateMeetingScheduling               : False
        AutoAdmittedUsers                           : False
        AllowCloudRecording                         : False
        AllowOutlookAddIn                           : False
        AllowPowerPointSharing                      : False
        AllowParticipantGiveRequestControl          : False
        AllowExternalParticipantGiveRequestControl  : False
        AllowSharedNotes                            : False
        AllowWhiteboard                             : False
        AllowTranscription                          : False
        MediaBitRateKb                              : False
        ScreenSharingMode                           : False

5. <span data-ttu-id="d6440-198">仮想化された環境で Teams を使用するすべてのユーザーに、[割り当てる] と [ビルトインポリシー] オプションを適用します。</span><span class="sxs-lookup"><span data-stu-id="d6440-198">Apply the AllOff built-in policy option to all users who will be using Teams in a virtualized environment.</span></span> 

        Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity “user email id”

 <span data-ttu-id="d6440-199">Teams 会議ポリシーの詳細については、「 [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d6440-199">For more information about Teams meeting policies, see [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).</span></span>

### <a name="virtualization-provider-requirements"></a><span data-ttu-id="d6440-200">仮想化プロバイダーの要件</span><span class="sxs-lookup"><span data-stu-id="d6440-200">Virtualization provider requirements</span></span>

<span data-ttu-id="d6440-201">Teams アプリは、主要な仮想化ソリューションプロバイダーで検証されています。</span><span class="sxs-lookup"><span data-stu-id="d6440-201">The Teams app has been validated on leading virtualization solution providers.</span></span> <span data-ttu-id="d6440-202">市場プロバイダーが複数ある場合は、仮想化ソリューションプロバイダーに問い合わせて、最小要件を満たしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="d6440-202">With multiple market providers, consult your virtualization solution provider to ensure minimum requirements are met.</span></span>

### <a name="virtual-machine-requirements"></a><span data-ttu-id="d6440-203">仮想マシンの要件</span><span class="sxs-lookup"><span data-stu-id="d6440-203">Virtual Machine requirements</span></span>

> [!NOTE]
> <span data-ttu-id="d6440-204">次の要件は、Teams デスクトップアプリと Teams Web アプリの両方に適用されます。</span><span class="sxs-lookup"><span data-stu-id="d6440-204">The following requirements apply to both the Teams desktop app and the Teams Web app.</span></span>

<span data-ttu-id="d6440-205">さまざまなワークロードとユーザーニーズが仮想化された環境では、次のような最小の VM 構成が推奨されます。</span><span class="sxs-lookup"><span data-stu-id="d6440-205">With the diverse workloads and user needs in a virtualized environment, the following is the minimum recommended VM configuration.</span></span>

|<span data-ttu-id="d6440-206">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d6440-206">Parameter</span></span>  |<span data-ttu-id="d6440-207">指標</span><span class="sxs-lookup"><span data-stu-id="d6440-207">Measure</span></span>  |
|---------|---------|
|<span data-ttu-id="d6440-208">vCPU</span><span class="sxs-lookup"><span data-stu-id="d6440-208">vCPU</span></span>    |  <span data-ttu-id="d6440-209">2コア</span><span class="sxs-lookup"><span data-stu-id="d6440-209">2 cores</span></span>       |
|<span data-ttu-id="d6440-210">RAM</span><span class="sxs-lookup"><span data-stu-id="d6440-210">RAM</span></span>     |  <span data-ttu-id="d6440-211">4 GB</span><span class="sxs-lookup"><span data-stu-id="d6440-211">4 GB</span></span>      |
|<span data-ttu-id="d6440-212">ストレージ</span><span class="sxs-lookup"><span data-stu-id="d6440-212">Storage</span></span>     | <span data-ttu-id="d6440-213">8 GB</span><span class="sxs-lookup"><span data-stu-id="d6440-213">8 GB</span></span>       |

### <a name="virtual-machine-operating-system-requirements"></a><span data-ttu-id="d6440-214">仮想マシンのオペレーティングシステム要件</span><span class="sxs-lookup"><span data-stu-id="d6440-214">Virtual Machine operating system requirements</span></span>

<span data-ttu-id="d6440-215">VM でサポートされているオペレーティングシステムは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d6440-215">The supported operating systems for VM are:</span></span>

- <span data-ttu-id="d6440-216">Windows 10 以降</span><span class="sxs-lookup"><span data-stu-id="d6440-216">Windows 10 and later</span></span>
- <span data-ttu-id="d6440-217">Windows Server 2012 R2 以降</span><span class="sxs-lookup"><span data-stu-id="d6440-217">Windows Server 2012 R2 and later</span></span>

## <a name="install-teams-on-vdi"></a><span data-ttu-id="d6440-218">VDI に Teams をインストールする</span><span class="sxs-lookup"><span data-stu-id="d6440-218">Install Teams on VDI</span></span>

<span data-ttu-id="d6440-219">Teams デスクトップアプリを展開するためのプロセスとツールを次に示します。</span><span class="sxs-lookup"><span data-stu-id="d6440-219">Here's the process and tools to deploy the Teams desktop app.</span></span> 

1. <span data-ttu-id="d6440-220">環境に応じて、次のいずれかのリンクを使用して Teams MSI パッケージをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="d6440-220">Download the Teams MSI package using one of the following links depending on the environment.</span></span> <span data-ttu-id="d6440-221">64ビットのオペレーティングシステムを搭載した VDI VM の64ビットバージョンをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d6440-221">We recommend the 64-bit version for a VDI VM with a 64-bit operating system.</span></span>

    - [<span data-ttu-id="d6440-222">32ビット版</span><span class="sxs-lookup"><span data-stu-id="d6440-222">32-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true)
    - [<span data-ttu-id="d6440-223">64ビット版</span><span class="sxs-lookup"><span data-stu-id="d6440-223">64-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true&arch=x64)

2. <span data-ttu-id="d6440-224">MSI を VDI VM にインストールするには、次のコマンドを実行します (または完全な更新が必要です)。</span><span class="sxs-lookup"><span data-stu-id="d6440-224">Run the following command to install the MSI to the VDI VM (or complete updating it).</span></span>

        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1

    <span data-ttu-id="d6440-225">これにより、チームがプログラムファイルにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="d6440-225">This installs Teams to Program Files.</span></span> <span data-ttu-id="d6440-226">この時点で、ゴールデンイメージのセットアップが完了しています。</span><span class="sxs-lookup"><span data-stu-id="d6440-226">At this point, the golden image setup is complete.</span></span>
 
    <span data-ttu-id="d6440-227">次の対話型ログオンセッションでは、チームが起動し、資格情報を求められます。</span><span class="sxs-lookup"><span data-stu-id="d6440-227">The next interactive logon session starts Teams and asks for credentials.</span></span> <span data-ttu-id="d6440-228">ALLUSER プロパティを使用して VDI に Teams をインストールする場合、Teams の自動起動を無効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="d6440-228">Note that it's not possible to disable auto-launch of Teams when installing Teams on VDI using the ALLUSER property.</span></span> 

3. <span data-ttu-id="d6440-229">次のコマンドを実行して、MSI を VDI VM からアンインストールします (または、更新の準備を行います)。</span><span class="sxs-lookup"><span data-stu-id="d6440-229">Run the following command to uninstall the MSI from the VDI VM (or prepare for updating it).</span></span>

        msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>

    <span data-ttu-id="d6440-230">これにより、プログラムファイルから Teams がアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="d6440-230">This uninstalls Teams from Program Files.</span></span>

## <a name="known-issues-and-limitations"></a><span data-ttu-id="d6440-231">既知の問題と制限事項</span><span class="sxs-lookup"><span data-stu-id="d6440-231">Known issues and limitations</span></span>

<span data-ttu-id="d6440-232">次に示すのは、VDI での Teams の既知の問題と制限です。</span><span class="sxs-lookup"><span data-stu-id="d6440-232">The following are known issues and limitations for Teams on VDI.</span></span>

- <span data-ttu-id="d6440-233">**共有セッションホストの種類の展開**: 共有セッションホストの種類の展開 (たとえば、共有の非永続的な VM 構成) はスコープに含まれません。</span><span class="sxs-lookup"><span data-stu-id="d6440-233">**Shared session host type deployments**: Shared session host type deployments (for example, shared non-persistent VM configuration) aren't in scope.</span></span>
- <span data-ttu-id="d6440-234">**通話と会議**:</span><span class="sxs-lookup"><span data-stu-id="d6440-234">**Calling and meetings**:</span></span>

    - <span data-ttu-id="d6440-235">通話と会議のシナリオは VDI 用に最適化されていません。</span><span class="sxs-lookup"><span data-stu-id="d6440-235">Calling and meeting scenarios aren't optimized for VDI.</span></span> <span data-ttu-id="d6440-236">これらのシナリオでは、パフォーマンスが低下します。</span><span class="sxs-lookup"><span data-stu-id="d6440-236">These scenarios will perform poorly.</span></span> <span data-ttu-id="d6440-237">「 [Teams での通話と会議の機能を無効にするポリシーを設定する](#set-policies-to-turn-off-calling-and-meeting-functionality-in-teams)」セクションの説明に従って、ユーザーレベルのポリシーを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d6440-237">We recommend using user-level policies as described in the [Set policies to turn off calling and meeting functionality in Teams](#set-policies-to-turn-off-calling-and-meeting-functionality-in-teams) section.</span></span>  
    - <span data-ttu-id="d6440-238">この記事で説明されているポリシーを適用することは、他のポリシーによっては、組織内の他のユーザーに影響を与える可能性がある、通話と会議機能の使用に影響します。</span><span class="sxs-lookup"><span data-stu-id="d6440-238">Applying the policies described in this article impacts the ability to use calling and meeting functionality, which depending on other policies, may affect other users in your organization.</span></span> <span data-ttu-id="d6440-239">組織内のユーザーが非 VDI クライアントを使用している場合は、ポリシーを適用しないことを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="d6440-239">If users in your organization use non-VDI clients, you can choose to not apply the policies.</span></span>  

- <span data-ttu-id="d6440-240">**他のユーザーが作成した通話と会議への参加**: ポリシーでは、ユーザーが会議を作成することを制限していますが、他のユーザーが会議からダイヤルアウトした場合でも会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="d6440-240">**Joining calls and meetings created by other users**: Although the policies restrict users from creating meetings, they can still join meetings if another user dials out to them from the meeting.</span></span> <span data-ttu-id="d6440-241">この会議では、ユーザーのビデオ共有機能、ホワイトボードなどの機能は、TeamsMeetingPolicy を使用してこれらの機能を無効にしたかどうかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="d6440-241">In these meetings, the user's ability to share video, use whiteboard and other features depend on whether you disabled those features using TeamsMeetingPolicy.</span></span>  
- <span data-ttu-id="d6440-242">**キャッシュ**されたコンテンツ: Teams が実行されている仮想環境が永続的ではなく (各ユーザーセッションの終了時にデータがクリーンアップされる)、ユーザーは以前のセッションで同じコンテンツにアクセスしたかどうかに関係なく、コンテンツの更新によるパフォーマンスの低下が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d6440-242">**Cached content**: If the virtual environment in which Teams is running isn't persistent (and data is cleaned up at the end of each user session), users may notice performance degradation due to content refresh, regardless of whether the user accessed the same content in a previous session.</span></span>
- <span data-ttu-id="d6440-243">**クライアントの更新**: VDI 上の Teams は、コンピューター単位の MSI インストールによって自動的に更新されることはありません。</span><span class="sxs-lookup"><span data-stu-id="d6440-243">**Client updates**: Teams on VDI isn't automatically updated with per-machine MSI installation.</span></span> <span data-ttu-id="d6440-244">「 [VDI 上の Teams をインストール](#install-teams-on-vdi)する」セクションで説明されているように、新しい MSI をインストールして VM イメージを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6440-244">You have to update the VM image by installing a new MSI as described in the [Install Teams on VDI](#install-teams-on-vdi) section.</span></span> <span data-ttu-id="d6440-245">最新バージョンに更新するには、現在のバージョンをアンインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6440-245">You must uninstall the current version to update to a newer version.</span></span>
- <span data-ttu-id="d6440-246">**ユーザーエクスペリエンス**: vdi 環境での Teams ユーザーエクスペリエンスは、非 VDI 環境とは異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="d6440-246">**User experience**: The Teams user experience in a VDI environment may be different from a non-VDI environment.</span></span> <span data-ttu-id="d6440-247">違いは、ポリシー設定や環境での機能のサポートが原因である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d6440-247">The differences may be because of policy settings and/or feature support in the environment.</span></span>

<span data-ttu-id="d6440-248">VDI に関連していない Teams の既知の問題については、「 [Microsoft teams の既知の問題](Known-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d6440-248">For Teams known issues that aren't related to VDI, see [Known issues for Microsoft Teams](Known-issues.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="d6440-249">関連項目</span><span class="sxs-lookup"><span data-stu-id="d6440-249">Related topics</span></span>

- [<span data-ttu-id="d6440-250">MSI を使用して Microsoft Teams をインストールする</span><span class="sxs-lookup"><span data-stu-id="d6440-250">Install Microsoft Teams using MSI</span></span>](msi-deployment.md)
