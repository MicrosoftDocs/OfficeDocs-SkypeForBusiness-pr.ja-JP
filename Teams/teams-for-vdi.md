---
title: 仮想デスクトップ インフラストラクチャのチーム
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 04/10/2019
ms.topic: article
ms.service: msteams
ms.reviewer: ''
description: 仮想デスクトップ インフラストラクチャ (VDI) 環境でマイクロソフトのチームを実行する方法について説明します。
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1491932206812f81843c784274ffc7ea4102ee0b
ms.sourcegitcommit: 7fe8daf07013d7c532f128a3ae3bbf51d1b2aac9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/11/2019
ms.locfileid: "31808071"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a><span data-ttu-id="37f65-103">仮想デスクトップ インフラストラクチャのチーム</span><span class="sxs-lookup"><span data-stu-id="37f65-103">Teams for Virtualized Desktop Infrastructure</span></span>

<span data-ttu-id="37f65-104">この資料では、仮想化環境でマイクロソフトのチームを使用するための制限事項と要件について説明します。</span><span class="sxs-lookup"><span data-stu-id="37f65-104">This article describes the requirements and limitations for using Microsoft Teams in a virtualized environment.</span></span>

## <a name="what-is-vdi"></a><span data-ttu-id="37f65-105">VDI とは何ですか。</span><span class="sxs-lookup"><span data-stu-id="37f65-105">What is VDI?</span></span>

<span data-ttu-id="37f65-106">仮想デスクトップ インフラストラクチャ (VDI) は、デスクトップ オペレーティング システムおよびデータ センターに集中化されたサーバー上でアプリケーションをホストしている仮想化テクノロジです。</span><span class="sxs-lookup"><span data-stu-id="37f65-106">Virtual Desktop Infrastructure (VDI) is virtualization technology that hosts a desktop operating system and applications on a centralized server in a data center.</span></span> <span data-ttu-id="37f65-107">これは、完全にセキュリティで保護された、準拠の一元的なソースを持つユーザーに完全にカスタマイズされたデスクトップのエクスペリエンスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="37f65-107">This enables a fully personalized desktop experience to users with a fully secured and compliant centralized source.</span></span> 
 
<span data-ttu-id="37f65-108">現在、仮想化環境のチームでは専用の永続的な仮想マシン (VM) とのコラボレーションやチャット機能をサポートします。</span><span class="sxs-lookup"><span data-stu-id="37f65-108">Currently, Teams in a virtualized environment is available with support for collaboration and chat functionality with a dedicated persistent virtualized machine (VM).</span></span> <span data-ttu-id="37f65-109">最適なユーザー エクスペリエンスを確実に、この資料では説明に従います。</span><span class="sxs-lookup"><span data-stu-id="37f65-109">To ensure an optimal user experience, follow the guidance in this article.</span></span> 

## <a name="teams-requirements"></a><span data-ttu-id="37f65-110">チームの要件</span><span class="sxs-lookup"><span data-stu-id="37f65-110">Teams requirements</span></span>

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality-in-teams"></a><span data-ttu-id="37f65-111">呼び出すと、会議のチームの機能を無効にするポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="37f65-111">Set policies to turn off calling and meeting functionality in Teams</span></span>

<span data-ttu-id="37f65-112">チームを呼び出すと、会議の経験はない (準備中)、VDI 環境を最適化されています。</span><span class="sxs-lookup"><span data-stu-id="37f65-112">The Teams calling and meeting experience isn't optimized for a VDI environment (coming soon).</span></span> <span data-ttu-id="37f65-113">呼び出すと、会議のチームの機能を無効にするユーザー レベルのポリシーを設定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="37f65-113">We recommend you set user-level policies to turn off calling and meeting functionality in Teams.</span></span>

<span data-ttu-id="37f65-114">チームのデスクトップ アプリケーションまたは web アプリケーションのいずれかを使用して VDI でチームを完全に実行するのには選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="37f65-114">You can still choose to run Teams fully in VDI using either the Teams desktop app or web app.</span></span> <span data-ttu-id="37f65-115">ただし、ユーザーの操作性を犠牲にすることを避けるためにポリシーを設定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="37f65-115">However, we recommend that you set the policies to avoid compromising the user experience.</span></span>  

<span data-ttu-id="37f65-116">ポリシーの変更を伝達する (数時間) 時間がかかることができます。</span><span class="sxs-lookup"><span data-stu-id="37f65-116">It can take some time (a few hours) for the policy changes to propagate.</span></span> <span data-ttu-id="37f65-117">指定したアカウントの変更がすぐに表示されない場合、は、数時間でもう一度してみてください。</span><span class="sxs-lookup"><span data-stu-id="37f65-117">If you don’t see changes for a given account immediately, try again in a few hours.</span></span>

> [!NOTE]
> <span data-ttu-id="37f65-118">呼び出すチームおよび会議は、仮想デスクトップ環境で使用するために最適化された、ときに、これらのポリシーを元に戻すし、チームを通常どおりに使用するユーザーを許可します。</span><span class="sxs-lookup"><span data-stu-id="37f65-118">When Teams calling and meetings are optimized for use in virtual desktop environments, you can revert these policies and allow users to use Teams as they normally would.</span></span> 

#### <a name="calling"></a><span data-ttu-id="37f65-119">通話</span><span class="sxs-lookup"><span data-stu-id="37f65-119">Calling</span></span>

<span data-ttu-id="37f65-120">呼び出すと、プライベート通話オプションを使用できるユーザーとグループのチャットをするかどうかは、コントロールに**CSTeamsCallingPolicy**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="37f65-120">Use the **CSTeamsCallingPolicy** cmdlets to control whether users are allowed to use calling and calling options in private and group chats.</span></span> <span data-ttu-id="37f65-121">ここでは、ポリシーの設定と推奨される値の一覧です。</span><span class="sxs-lookup"><span data-stu-id="37f65-121">Here's the list of policy settings and recommended values.</span></span>

|<span data-ttu-id="37f65-122">ポリシー名</span><span class="sxs-lookup"><span data-stu-id="37f65-122">Policy name</span></span>  |<span data-ttu-id="37f65-123">Description</span><span class="sxs-lookup"><span data-stu-id="37f65-123">Description</span></span> |<span data-ttu-id="37f65-124">推奨値</span><span class="sxs-lookup"><span data-stu-id="37f65-124">Recommended value</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="37f65-125">AllowCalling</span><span class="sxs-lookup"><span data-stu-id="37f65-125">AllowCalling</span></span>    |<span data-ttu-id="37f65-126">コントロールの相互運用機能を呼び出すことです。</span><span class="sxs-lookup"><span data-stu-id="37f65-126">Controls interop calling capabilities.</span></span> <span data-ttu-id="37f65-127">Skype 通話を 1 対 1 のチームのユーザーと、その逆もビジネス ユーザーには、これをオンにできます。</span><span class="sxs-lookup"><span data-stu-id="37f65-127">Turning this on allows Skype for Business users to have one-on-one calls with Teams users and vice versa.</span></span>         |<span data-ttu-id="37f65-128">ビジネス ユーザーがチームでの着陸の Skype からの通話を禁止するのには、False に設定します。</span><span class="sxs-lookup"><span data-stu-id="37f65-128">Set to False to prevent calls from Skype for Business users landing in Teams.</span></span>          |
|<span data-ttu-id="37f65-129">AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="37f65-129">AllowPrivateCalling</span></span>     | <span data-ttu-id="37f65-130">通話アプリはチームのクライアントの左側にあるバーで、アプリケーションで使用できるかどうかと、ユーザーが通話とビデオのプライベート チャットのオプションを呼び出すを参照してくださいかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="37f65-130">Controls whether the Calling app is available in the app bar on the left side of the Teams client and whether users see Calling and Video call options in private chat</span></span>         |<span data-ttu-id="37f65-131">チームの左側にあるバーで、アプリケーションから呼び出すアプリケーションを削除するのには、プライベート チャットで通話とビデオ通話のオプションを削除するのには False に設定します。</span><span class="sxs-lookup"><span data-stu-id="37f65-131">Set to False to remove the Calling app from the app bar on the left side of Teams and to remove the Calling and Video call options in private chat.</span></span>          |

#### <a name="create-and-assign-a-calling-policy"></a><span data-ttu-id="37f65-132">作成し、呼び出し元のポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="37f65-132">Create and assign a calling policy</span></span>

1. <span data-ttu-id="37f65-133">管理者として Windows PowerShell セッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="37f65-133">Start a Windows PowerShell session as an administrator.</span></span>
2. <span data-ttu-id="37f65-134">Skype オンライン コネクタに接続します。</span><span class="sxs-lookup"><span data-stu-id="37f65-134">Connect to the Skype Online Connector.</span></span>

        # Set Office 365 User Name and Password
        $username = “admin email address”
        password = ConvertTo-SecureString "password" -AsPlainText -Force
        $LiveCred = new-object -typename System.Management.Automation.PSCredential -argumentlist $username, $password
        # Connect to Skype Online
        Import-Module SkypeOnlineConnector
        $sfboSession = New-CsOnlineSession -Credential $LiveCred
        Import-PSSession $sfboSession```

3. <span data-ttu-id="37f65-135">通話ポリシー オプションの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="37f65-135">View a list of calling policy options.</span></span>

       Get-CsTeamsCallingPolicy
 
4. <span data-ttu-id="37f65-136">呼び出し元のすべてのポリシーが無効になっている組み込みのポリシー オプションを確認します。</span><span class="sxs-lookup"><span data-stu-id="37f65-136">Look for the built-in policy option where all calling policies are disabled.</span></span> <span data-ttu-id="37f65-137">次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="37f65-137">It looks like this.</span></span>
   
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

5. <span data-ttu-id="37f65-138">DisallowCalling の組み込みのポリシー オプションを仮想化環境でチームを使用するすべてのユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="37f65-138">Apply the DisallowCalling built-in policy option to all users who will be using Teams in a virtualized environment.</span></span>

        Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity “user email id”

<span data-ttu-id="37f65-139">チームのポリシーの呼び出しの詳細については、[一連の CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="37f65-139">For more information about Teams calling policies, see [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy).</span></span>

#### <a name="meetings"></a><span data-ttu-id="37f65-140">会議</span><span class="sxs-lookup"><span data-stu-id="37f65-140">Meetings</span></span>

<span data-ttu-id="37f65-141">**CsTeamsMeetingPolicy**コマンドレットを使用して、ユーザーが作成した会議、会議中にアクセスできる機能、匿名ユーザーおよび外部ユーザーに利用可能な会議の機能の種類を制御します。</span><span class="sxs-lookup"><span data-stu-id="37f65-141">Use the **CsTeamsMeetingPolicy** cmdlets to control the type of meetings that users can create, the features that they can access while in a meeting, and the meeting features that are available to anonymous and external users.</span></span> <span data-ttu-id="37f65-142">ここでは、ポリシーの設定と推奨される値の一覧です。</span><span class="sxs-lookup"><span data-stu-id="37f65-142">Here's the list of policy settings and recommended values.</span></span>

|<span data-ttu-id="37f65-143">ポリシー名</span><span class="sxs-lookup"><span data-stu-id="37f65-143">Policy Name</span></span> |<span data-ttu-id="37f65-144">Description</span><span class="sxs-lookup"><span data-stu-id="37f65-144">Description</span></span>|<span data-ttu-id="37f65-145">推奨値</span><span class="sxs-lookup"><span data-stu-id="37f65-145">Recommended Value</span></span>                   |
|-------------------|-----------------|-----------------------|
|<span data-ttu-id="37f65-146">AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="37f65-146">AllowPrivateMeetingScheduling</span></span>  | <span data-ttu-id="37f65-147">秘密の会議をスケジュールするユーザーに許可するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="37f65-147">Determines whether a user is allowed to schedule private meetings.</span></span>| <span data-ttu-id="37f65-148">秘密の会議をスケジュールすることからユーザーを禁止するのには False に設定します。</span><span class="sxs-lookup"><span data-stu-id="37f65-148">Set to False to prohibit the user from being able to schedule private meetings.</span></span>  |
|<span data-ttu-id="37f65-149">AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="37f65-149">AllowChannelMeetingScheduling</span></span>  | <span data-ttu-id="37f65-150">チャネルの会議をスケジュールするユーザーに許可するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="37f65-150">Determines whether a user is allowed to schedule channel meetings.</span></span> | <span data-ttu-id="37f65-151">チャネルの会議をスケジュールすることからユーザーを禁止する False に設定します。</span><span class="sxs-lookup"><span data-stu-id="37f65-151">Set to False to prohibit the user from being able to schedule channel meetings.</span></span>                       |
|<span data-ttu-id="37f65-152">AllowMeetNow</span><span class="sxs-lookup"><span data-stu-id="37f65-152">AllowMeetNow</span></span> |<span data-ttu-id="37f65-153">ユーザーが作成または、臨時会議を開始できるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="37f65-153">Determines whether a user is allowed to create or start ad-hoc meetings.</span></span>              |  <span data-ttu-id="37f65-154">この設定を false に設定すると、臨時の会議を開始することを禁止します。</span><span class="sxs-lookup"><span data-stu-id="37f65-154">Set this to False to prohibit the user from being able to start ad-hoc meetings.</span></span>                     |
|<span data-ttu-id="37f65-155">ScreenSharingMode</span><span class="sxs-lookup"><span data-stu-id="37f65-155">ScreenSharingMode</span></span> | <span data-ttu-id="37f65-156">通話や会議で画面を共有するユーザーに許可されるモードを決定します。</span><span class="sxs-lookup"><span data-stu-id="37f65-156">Determines the mode in which a user is allowed to share their screen in calls or meetings.</span></span> | <span data-ttu-id="37f65-157">無効に設定すると、画面の共有からユーザーを禁止します。</span><span class="sxs-lookup"><span data-stu-id="37f65-157">Set to Disabled to prohibit the user from sharing their screens</span></span>                          |
|<span data-ttu-id="37f65-158">AllowIPVideo</span><span class="sxs-lookup"><span data-stu-id="37f65-158">AllowIPVideo</span></span> |<span data-ttu-id="37f65-159">ユーザーの会議または呼び出しにビデオが有効になっているかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="37f65-159">Determines whether video is enabled in a user's meetings or calls.</span></span>                  |    <span data-ttu-id="37f65-160">ユーザーが、ビデオを共有することを禁止するのには False に設定します。</span><span class="sxs-lookup"><span data-stu-id="37f65-160">Set to False to prohibit the user from sharing their video</span></span>                                         |
| <span data-ttu-id="37f65-161">AllowAnonymousUsersToDialOut</span><span class="sxs-lookup"><span data-stu-id="37f65-161">AllowAnonymousUsersToDialOut</span></span> | <span data-ttu-id="37f65-162">匿名ユーザーが PSTN 番号にダイアル アウトできるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="37f65-162">Determines whether anonymous users are allowed to dial out to a PSTN number.</span></span> | <span data-ttu-id="37f65-163">匿名ユーザーがダイヤルアウトするを禁止するのには False に設定します。</span><span class="sxs-lookup"><span data-stu-id="37f65-163">Set to False to prohibit anonymous users from dialing out</span></span>                                  |
| <span data-ttu-id="37f65-164">AllowAnonymousUsersToStartMeeting</span><span class="sxs-lookup"><span data-stu-id="37f65-164">AllowAnonymousUsersToStartMeeting</span></span> | <span data-ttu-id="37f65-165">匿名ユーザーが会議を開始できるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="37f65-165">Determines whether anonymous users can start a meeting.</span></span>     |  <span data-ttu-id="37f65-166">ユーザーが会議を開始することを禁止するのには False に設定します。</span><span class="sxs-lookup"><span data-stu-id="37f65-166">Set to False to prohibit users from starting a meeting</span></span>                                            |
| <span data-ttu-id="37f65-167">AllowOutlookAddIn</span><span class="sxs-lookup"><span data-stu-id="37f65-167">AllowOutlookAddIn</span></span> |<span data-ttu-id="37f65-168">ユーザーがチーム会議は、Outlook のデスクトップ クライアントでのスケジュールを設定できるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="37f65-168">Determines whether a user can schedule Teams meetings in the Outlook desktop client.</span></span>| <span data-ttu-id="37f65-169">ユーザーが Outlook のデスクトップ クライアントでのチーム会議をスケジュールすることを禁止するのには False に設定します。</span><span class="sxs-lookup"><span data-stu-id="37f65-169">Set to False to prohibit a user from  scheduling Teams meetings in the Outlook desktop client</span></span>|
| <span data-ttu-id="37f65-170">AllowParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="37f65-170">AllowParticipantGiveRequestControl</span></span>|<span data-ttu-id="37f65-171">参加者が要求または、画面の共有を制御できるようにするかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="37f65-171">Determines whether participants can request or give control of screen sharing.</span></span>| <span data-ttu-id="37f65-172">与え、その会議内のコントロールを要求するユーザーを禁止するのには False に設定します。</span><span class="sxs-lookup"><span data-stu-id="37f65-172">Set to False to prohibit the user from giving and requesting control in a meeting</span></span>    |
| <span data-ttu-id="37f65-173">AllowExternalParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="37f65-173">AllowExternalParticipantGiveRequestControl</span></span> | <span data-ttu-id="37f65-174">外部の参加者が要求または、画面の共有を制御できるようにするかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="37f65-174">Determines whether external participants can request or give control of screen sharing.</span></span>| <span data-ttu-id="37f65-175">False に設定されてから、外部のユーザーを禁止するミーティングの制御を要求します。</span><span class="sxs-lookup"><span data-stu-id="37f65-175">Set to False to prohibit an external user from giving, requesting control in a meeting</span></span>|
|<span data-ttu-id="37f65-176">AllowPowerPointSharing</span><span class="sxs-lookup"><span data-stu-id="37f65-176">AllowPowerPointSharing</span></span>|<span data-ttu-id="37f65-177">ユーザーの会議で PowerPoint の共有を許可するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="37f65-177">Determines whether PowerPoint sharing is allowed in a user’s meetings.</span></span> |<span data-ttu-id="37f65-178">ユーザーが会議中の PowerPoint ファイルを共有することを禁止するのには False に設定します。</span><span class="sxs-lookup"><span data-stu-id="37f65-178">Set to False to prohibit a user from sharing PowerPoint files in a meeting</span></span>  |
|<span data-ttu-id="37f65-179">AllowWhiteboard</span><span class="sxs-lookup"><span data-stu-id="37f65-179">AllowWhiteboard</span></span> | <span data-ttu-id="37f65-180">ユーザーの会議でホワイト ボードを許可するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="37f65-180">Determines whether whiteboard is allowed in a user’s meetings.</span></span> |   <span data-ttu-id="37f65-181">False に設定すると、会議でホワイト ボードを禁止します。</span><span class="sxs-lookup"><span data-stu-id="37f65-181">Set to False to prohibit whiteboard in a meeting</span></span> |
| <span data-ttu-id="37f65-182">AllowTranscription</span><span class="sxs-lookup"><span data-stu-id="37f65-182">AllowTranscription</span></span> |<span data-ttu-id="37f65-183">ユーザーの会議で、リアルタイムまたは会議後のキャプションおよびトランスクリプションができるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="37f65-183">Determines whether real-time and/or post-meeting captions and transcriptions are allowed in a user's meetings.</span></span>|    <span data-ttu-id="37f65-184">議事録と会議内のキャプションを禁止するのには False に設定します。</span><span class="sxs-lookup"><span data-stu-id="37f65-184">Set to False to prohibit transcription  and captions in a meeting</span></span>  |  
| <span data-ttu-id="37f65-185">AllowSharedNotes</span><span class="sxs-lookup"><span data-stu-id="37f65-185">AllowSharedNotes</span></span> | <span data-ttu-id="37f65-186">共有ノートを取ることを許可されているかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="37f65-186">Determines whether users are allowed to take shared notes.</span></span> | <span data-ttu-id="37f65-187">False に設定すると、共有のノートを取ることを禁止します。</span><span class="sxs-lookup"><span data-stu-id="37f65-187">Set to False to prohibit users from taking shared notes</span></span> |
|<span data-ttu-id="37f65-188">MediaBitRateKB</span><span class="sxs-lookup"><span data-stu-id="37f65-188">MediaBitRateKB</span></span> |<span data-ttu-id="37f65-189">オーディオ/ビデオ/アプリケーションの会議での転送を共有するためのメディアのビット レートを決定します。</span><span class="sxs-lookup"><span data-stu-id="37f65-189">Determines the media bit rate for audio/video/app sharing transmissions in meetings</span></span>  | <span data-ttu-id="37f65-190">推奨値は、5000 (5 MB) です。</span><span class="sxs-lookup"><span data-stu-id="37f65-190">Suggested value is 5000 (5 MB).</span></span> <span data-ttu-id="37f65-191">組織のニーズに基づいて変更できます。</span><span class="sxs-lookup"><span data-stu-id="37f65-191">You can change it based on your organization’s needs.</span></span>| 

#### <a name="create-and-assign-a-meeting-policy"></a><span data-ttu-id="37f65-192">作成し、ミーティングのポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="37f65-192">Create and assign a meeting policy</span></span>

1. <span data-ttu-id="37f65-193">管理者として Windows PowerShell セッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="37f65-193">Start a Windows PowerShell session as an administrator.</span></span>
2. <span data-ttu-id="37f65-194">Skype オンライン コネクタに接続します。</span><span class="sxs-lookup"><span data-stu-id="37f65-194">Connect to the Skype Online Connector.</span></span>

        # Set Office 365 User Name and Password
        $username = “admin email address”
        password = ConvertTo-SecureString "password" -AsPlainText -Force
        $LiveCred = new-object -typename System.Management.Automation.PSCredential -argumentlist $username, $password
        # Connect to Skype Online
        Import-Module SkypeOnlineConnector
        $sfboSession = New-CsOnlineSession -Credential $LiveCred
        Import-PSSession $sfboSession```

3. <span data-ttu-id="37f65-195">ミーティングのポリシー オプションの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="37f65-195">View a list of meeting policy options.</span></span>

       Get-CsTeamsMeetingPolicy
 
4. <span data-ttu-id="37f65-196">会議のすべてのポリシーが無効になっている組み込みのポリシー オプションを確認します。</span><span class="sxs-lookup"><span data-stu-id="37f65-196">Look for the built-in policy option where all meeting policies are disabled.</span></span> <span data-ttu-id="37f65-197">次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="37f65-197">It looks like this.</span></span>
   
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
        AlowTranscription                           : False
        MediaBitRateKb                              : False
        ScreenSharingMode                           : False

5. <span data-ttu-id="37f65-198">AllOff の組み込みのポリシー オプションを仮想化環境でチームを使用するすべてのユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="37f65-198">Apply the AllOff built-in policy option to all users who will be using Teams in a virtualized environment.</span></span> 

        Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity “user email id”

 <span data-ttu-id="37f65-199">チームのミーティングのポリシーの詳細については、[一連の CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="37f65-199">For more information about Teams meeting policies, see [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).</span></span>

### <a name="virtualization-provider-requirements"></a><span data-ttu-id="37f65-200">仮想化プロバイダーの要件</span><span class="sxs-lookup"><span data-stu-id="37f65-200">Virtualization provider requirements</span></span>

<span data-ttu-id="37f65-201">チームのアプリケーションは、業界をリードする仮想化ソリューション ・ プロバイダーで検証されました。</span><span class="sxs-lookup"><span data-stu-id="37f65-201">The Teams app has been validated on leading virtualization solution providers.</span></span> <span data-ttu-id="37f65-202">複数の市場のプロバイダーでは、最小要件を満たしていることを確認するのには、仮想化ソリューションのプロバイダーを参照してください。</span><span class="sxs-lookup"><span data-stu-id="37f65-202">With multiple market providers, consult your virtualization solution provider to ensure minimum requirements are met.</span></span>

### <a name="virtual-machine-requirements"></a><span data-ttu-id="37f65-203">仮想マシンの要件</span><span class="sxs-lookup"><span data-stu-id="37f65-203">Virtual Machine requirements</span></span>

<span data-ttu-id="37f65-204">多様なワークロードと仮想化された環境でユーザーのニーズと、次に、最低限の VM の構成を推奨します。</span><span class="sxs-lookup"><span data-stu-id="37f65-204">With the diverse workloads and user needs in a virtualized environment, the following is the minimum recommended VM configuration.</span></span>

|<span data-ttu-id="37f65-205">パラメーター</span><span class="sxs-lookup"><span data-stu-id="37f65-205">Parameter</span></span>  |<span data-ttu-id="37f65-206">メジャー</span><span class="sxs-lookup"><span data-stu-id="37f65-206">Measure</span></span>  |
|---------|---------|
|<span data-ttu-id="37f65-207">vCPU</span><span class="sxs-lookup"><span data-stu-id="37f65-207">vCPU</span></span>    |  <span data-ttu-id="37f65-208">2 コア</span><span class="sxs-lookup"><span data-stu-id="37f65-208">2 cores</span></span>       |
|<span data-ttu-id="37f65-209">RAM</span><span class="sxs-lookup"><span data-stu-id="37f65-209">RAM</span></span>     |  <span data-ttu-id="37f65-210">4 GB</span><span class="sxs-lookup"><span data-stu-id="37f65-210">4 GB</span></span>      |
|<span data-ttu-id="37f65-211">ストレージ</span><span class="sxs-lookup"><span data-stu-id="37f65-211">Storage</span></span>     | <span data-ttu-id="37f65-212">8 GB</span><span class="sxs-lookup"><span data-stu-id="37f65-212">8 GB</span></span>       |

### <a name="virtual-machine-operating-system-requirements"></a><span data-ttu-id="37f65-213">仮想マシンのオペレーティング システムの要件</span><span class="sxs-lookup"><span data-stu-id="37f65-213">Virtual Machine operating system requirements</span></span>

<span data-ttu-id="37f65-214">VM でサポートされているオペレーティング ・ システムは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="37f65-214">The supported operating systems for VM are:</span></span>

- <span data-ttu-id="37f65-215">Windows 10 以降</span><span class="sxs-lookup"><span data-stu-id="37f65-215">Windows 10 and later</span></span>
- <span data-ttu-id="37f65-216">Windows Server 2012 R2 以降では</span><span class="sxs-lookup"><span data-stu-id="37f65-216">Windows Server 2012 R2 and later</span></span>

## <a name="install-teams-on-vdi"></a><span data-ttu-id="37f65-217">VDI にチームをインストールします。</span><span class="sxs-lookup"><span data-stu-id="37f65-217">Install Teams on VDI</span></span>

<span data-ttu-id="37f65-218">ここでは、プロセスとチームのデスクトップ アプリケーションを展開するためのツールです。</span><span class="sxs-lookup"><span data-stu-id="37f65-218">Here's the process and tools to deploy the Teams desktop app.</span></span> 

1. <span data-ttu-id="37f65-219">環境によっては、次のリンクのいずれかを使用してチームの MSI パッケージをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="37f65-219">Download the Teams MSI package using one of the following links depending on the environment.</span></span> <span data-ttu-id="37f65-220">64 ビット バージョンは、64 ビット ・ オペレーティング ・ システムと VDI の VM をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="37f65-220">We recommend the 64-bit version for a VDI VM with a 64-bit operating system.</span></span>

    - [<span data-ttu-id="37f65-221">32 ビット版</span><span class="sxs-lookup"><span data-stu-id="37f65-221">32-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true)
    - [<span data-ttu-id="37f65-222">64 ビット バージョン</span><span class="sxs-lookup"><span data-stu-id="37f65-222">64-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true&arch=x64)

2. <span data-ttu-id="37f65-223">VDI の VM に msi ファイルをインストール (または更新を実行) するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="37f65-223">Run the following command to install the MSI to the VDI VM (or complete updating it).</span></span>

        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1

    <span data-ttu-id="37f65-224">チームのプログラム ファイルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="37f65-224">This installs Teams to Program Files.</span></span> <span data-ttu-id="37f65-225">この時点で、ゴールド ・ イメージのセットアップは完了です。</span><span class="sxs-lookup"><span data-stu-id="37f65-225">At this point, the golden image setup is complete.</span></span>
 
    <span data-ttu-id="37f65-226">次の対話型ログオン セッションでは、チームを起動し、資格情報を要求します。</span><span class="sxs-lookup"><span data-stu-id="37f65-226">The next interactive logon session starts Teams and asks for credentials.</span></span> <span data-ttu-id="37f65-227">チームに VDI の ALLUSER プロパティを使用してインストールする場合は、チームの自動起動を無効にすることがないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="37f65-227">Note that it's not possible to disable auto-launch of Teams when installing Teams on VDI using the ALLUSER property.</span></span> 

3. <span data-ttu-id="37f65-228">VDI の VM から msi ファイルをアンインストールする (またはそれを更新するための準備) するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="37f65-228">Run the following command to uninstall the MSI from the VDI VM (or prepare for updating it).</span></span>

        msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>

    <span data-ttu-id="37f65-229">これは、プログラム ファイルからチームをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="37f65-229">This uninstalls Teams from Program Files.</span></span>

## <a name="known-issues-and-limitations"></a><span data-ttu-id="37f65-230">既知の問題と制限事項</span><span class="sxs-lookup"><span data-stu-id="37f65-230">Known issues and limitations</span></span>

<span data-ttu-id="37f65-231">次のような問題と VDI のチームに制限します。</span><span class="sxs-lookup"><span data-stu-id="37f65-231">The following are known issues and limitations for Teams on VDI.</span></span>

- <span data-ttu-id="37f65-232">**セッション ホスト型環境の共有**: 共有セッションのホスト型環境 (たとえば、共有非永続的な VM 構成) は、スコープに登録されていません。</span><span class="sxs-lookup"><span data-stu-id="37f65-232">**Shared session host type deployments**: Shared session host type deployments (for example, shared non-persistent VM configuration) aren't in scope.</span></span>
- <span data-ttu-id="37f65-233">**通話や会議**を表示します。</span><span class="sxs-lookup"><span data-stu-id="37f65-233">**Calling and meetings**:</span></span>

    - <span data-ttu-id="37f65-234">通話とミーティングの場合は、VDI の最適化されています。</span><span class="sxs-lookup"><span data-stu-id="37f65-234">Calling and meeting scenarios aren't optimized for VDI.</span></span> <span data-ttu-id="37f65-235">これらのシナリオは、適切に実行されます。</span><span class="sxs-lookup"><span data-stu-id="37f65-235">These scenarios will perform poorly.</span></span> <span data-ttu-id="37f65-236">[呼び出すと、会議のチームの機能を無効にするポリシーを設定](#set-policies-to-turn-off-calling-and-meeting-functionality-in-teams)] セクションで説明したようにユーザー レベルのポリシーを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="37f65-236">We recommend using user-level policies as described in the [Set policies to turn off calling and meeting functionality in Teams](#set-policies-to-turn-off-calling-and-meeting-functionality-in-teams) section.</span></span>  
    - <span data-ttu-id="37f65-237">この資料に記載されているポリシーを適用する他のポリシーによって、組織内の他のユーザーに影響を与える可能性があります、および会議を呼び出す機能を使用する機能に影響します。</span><span class="sxs-lookup"><span data-stu-id="37f65-237">Applying the policies described in this article impacts the ability to use calling and meeting functionality, which depending on other policies, may affect other users in your organization.</span></span> <span data-ttu-id="37f65-238">組織内のユーザーは、VDI なしのクライアントを使用している場合、ポリシーを適用しないように選択できます。</span><span class="sxs-lookup"><span data-stu-id="37f65-238">If users in your organization use non-VDI clients, you can choose to not apply the policies.</span></span>  

- <span data-ttu-id="37f65-239">**呼び出しと他のユーザーによって作成されたミーティングへの参加**: ポリシーは、会議の作成からユーザーを制限するに参加できます会議別のユーザーに電話をかけること、会議の場合。</span><span class="sxs-lookup"><span data-stu-id="37f65-239">**Joining calls and meetings created by other users**: Although the policies restrict users from creating meetings, they can still join meetings if another user dials out to them from the meeting.</span></span> <span data-ttu-id="37f65-240">ビデオを共有するユーザーの能力、これらの会議でホワイト ボードの使用およびその他の機能が、TeamsMeetingPolicy を使用してこれらの機能を無効にするかどうかに依存します。</span><span class="sxs-lookup"><span data-stu-id="37f65-240">In these meetings, the user's ability to share video, use whiteboard and other features depend on whether you disabled those features using TeamsMeetingPolicy.</span></span>  
- <span data-ttu-id="37f65-241">**キャッシュされたコンテンツ**: チームで仮想環境の場合、実行が固定されていない (と各ユーザー セッションの最後にデータをクリーンアップ)、ユーザーは、ユーザーが同じにアクセスするかどうかに関係なく、コンテンツの更新に伴うパフォーマンス低下をことがあります前のセッションでのコンテンツです。</span><span class="sxs-lookup"><span data-stu-id="37f65-241">**Cached content**: If the virtual environment in which Teams is running isn't persistent (and data is cleaned up at the end of each user session), users may notice performance degradation due to content refresh, regardless of whether the user accessed the same content in a previous session.</span></span>
- <span data-ttu-id="37f65-242">**クライアント用更新プログラム**: VDI のチームは VDI 以外のチームのクライアントがいることと同じように自動的に更新されません。</span><span class="sxs-lookup"><span data-stu-id="37f65-242">**Client updates**: Teams on VDI isn't automatically updated like the way that non-VDI Teams clients are.</span></span>  <span data-ttu-id="37f65-243">[VDI のチームのインストール](#install-teams-on-vdi)のセクションで説明したように新しい MSI をインストールすると、VM イメージを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="37f65-243">You have to update the VM image by installing a new MSI as described in the [Install Teams on VDI](#install-teams-on-vdi) section.</span></span> <span data-ttu-id="37f65-244">新しいバージョンに更新する現在のバージョンをアンインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="37f65-244">You must uninstall the current version to update to a newer version.</span></span>
- <span data-ttu-id="37f65-245">**ユーザー エクスペリエンス**: VDI 環境で、チームのユーザー エクスペリエンスは、VDI ではない環境とは異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="37f65-245">**User experience**: The Teams user experience in a VDI environment may be different from a non-VDI environment.</span></span> <span data-ttu-id="37f65-246">相違点は、ポリシーの設定が原因であるか、環境内のサポート可能性があります。</span><span class="sxs-lookup"><span data-stu-id="37f65-246">The differences may be because of policy settings and/or feature support in the environment.</span></span>

<span data-ttu-id="37f65-247">チームは既知の VDI に関連しない問題は、[既知の問題に対するマイクロソフトのチーム](Known-issues.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="37f65-247">For Teams known issues that aren't related to VDI, see [Known issues for Microsoft Teams](Known-issues.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="37f65-248">関連トピック</span><span class="sxs-lookup"><span data-stu-id="37f65-248">Related topics</span></span>

- [<span data-ttu-id="37f65-249">MSI を使用して Microsoft Teams をインストールする</span><span class="sxs-lookup"><span data-stu-id="37f65-249">Install Microsoft Teams using MSI</span></span>](msi-deployment.md)