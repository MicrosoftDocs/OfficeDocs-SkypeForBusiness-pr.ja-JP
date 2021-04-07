---
title: 全般会議ポリシーを管理する
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
- ms.teamsadmincenter.meetingpolicies.general
- seo-marvel-apr2020
description: Teams で一般的な会議ポリシー設定を管理する方法について学習します。
ms.openlocfilehash: fb5f537e5cc96ba363fb4aa68bbfff2af513db6b
ms.sourcegitcommit: 2d725b9925696e61e3e7338f890f086e009c28f2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/06/2021
ms.locfileid: "51598766"
---
# <a name="meeting-policy-settings---general"></a><span data-ttu-id="f37c7-103">会議ポリシーの設定 - 全般</span><span class="sxs-lookup"><span data-stu-id="f37c7-103">Meeting policy settings - General</span></span>

<span data-ttu-id="f37c7-104"><a name="bkgeneral"> </a></span><span class="sxs-lookup"><span data-stu-id="f37c7-104"><a name="bkgeneral"> </a></span></span>

<span data-ttu-id="f37c7-105">この記事では、Teams 会議の次の一般的なポリシー設定について説明します。</span><span class="sxs-lookup"><span data-stu-id="f37c7-105">This article describes the following general policy settings for Teams meetings:</span></span>

- [<span data-ttu-id="f37c7-106">チャネルで "今すぐ会議" を許可する</span><span class="sxs-lookup"><span data-stu-id="f37c7-106">Allow Meet now in channels</span></span>](#allow-meet-now-in-channels)
- [<span data-ttu-id="f37c7-107">Outlook アドインを許可する</span><span class="sxs-lookup"><span data-stu-id="f37c7-107">Allow the Outlook add-in</span></span>](#allow-the-outlook-add-in)
- [<span data-ttu-id="f37c7-108">チャネルの会議スケジュールを許可する</span><span class="sxs-lookup"><span data-stu-id="f37c7-108">Allow channel meeting scheduling</span></span>](#allow-channel-meeting-scheduling)
- [<span data-ttu-id="f37c7-109">プライベート会議のスケジュールを許可する</span><span class="sxs-lookup"><span data-stu-id="f37c7-109">Allow scheduling private meetings</span></span>](#allow-scheduling-private-meetings)
- [<span data-ttu-id="f37c7-110">プライベート会議で "今すぐ会議" を許可する</span><span class="sxs-lookup"><span data-stu-id="f37c7-110">Allow Meet now in private meetings</span></span>](#allow-meet-now-in-private-meetings)
- [<span data-ttu-id="f37c7-111">指定された発表者ロール モード</span><span class="sxs-lookup"><span data-stu-id="f37c7-111">Designated presenter role mode</span></span>](#designated-presenter-role-mode)
- [<span data-ttu-id="f37c7-112">会議出席レポート</span><span class="sxs-lookup"><span data-stu-id="f37c7-112">Meeting attendance report</span></span>](#meeting-attendance-report)
- [<span data-ttu-id="f37c7-113">諸島モードの会議プロバイダー</span><span class="sxs-lookup"><span data-stu-id="f37c7-113">Meeting provider for Islands mode</span></span>](#meeting-provider-for-islands-mode)

## <a name="allow-meet-now-in-channels"></a><span data-ttu-id="f37c7-114">チャネルで "今すぐ会議" を許可する</span><span class="sxs-lookup"><span data-stu-id="f37c7-114">Allow Meet now in channels</span></span>

<span data-ttu-id="f37c7-115">これはユーザーごとのポリシーであり、会議が始まる前に適用されます。</span><span class="sxs-lookup"><span data-stu-id="f37c7-115">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="f37c7-116">この設定は、ユーザーが Teams チャネルでアドホック会議を開始できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="f37c7-116">This setting controls whether a user can start an ad hoc meeting in a Teams channel.</span></span> <span data-ttu-id="f37c7-117">この設定をオンにした場合、ユーザーは[会議] ボタンをクリックして臨時の会議を開始したり、チャネルで会議をスケジュールできます。</span><span class="sxs-lookup"><span data-stu-id="f37c7-117">If you turn this on, users can click the **Meet** button to start an ad hoc meeting or schedule a meeting in the channel.</span></span> <span data-ttu-id="f37c7-118">既定値は True です。</span><span class="sxs-lookup"><span data-stu-id="f37c7-118">The default value is True.</span></span>

<span data-ttu-id="f37c7-119">[![メッセージの下に [今すぐ会う] アイコンを示すスクリーンショット ](media/meeting-policies-meet-now.png)](media/meeting-policies-meet-now.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="f37c7-119">[ ![Screenshot showing the Meet now icon below a message](media/meeting-policies-meet-now.png) ](media/meeting-policies-meet-now.png#lightbox)</span></span>

## <a name="allow-the-outlook-add-in"></a><span data-ttu-id="f37c7-120">Outlook アドインを許可する</span><span class="sxs-lookup"><span data-stu-id="f37c7-120">Allow the Outlook add-in</span></span>

<span data-ttu-id="f37c7-121">これはユーザーごとのポリシーであり、会議が始まる前に適用されます。</span><span class="sxs-lookup"><span data-stu-id="f37c7-121">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="f37c7-122">この設定は、Outlook (Windows、Mac、Web、およびモバイル) 内から Teams 会議をスケジュールできるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="f37c7-122">This setting controls whether Teams meetings can be scheduled from within Outlook (Windows, Mac, web, and mobile).</span></span>

![新しい会議をスケジュールする機能が表示されたスクリーンショット](media/meeting-policies-outlook-add-in.png)

<span data-ttu-id="f37c7-124">これをオフにすると、ユーザーは Outlook で新しい会議を作成するときに Teams 会議をスケジュールできなくなります。</span><span class="sxs-lookup"><span data-stu-id="f37c7-124">If you turn this off, users are unable to schedule Teams meetings when they create a new meeting in Outlook.</span></span> <span data-ttu-id="f37c7-125">たとえば、Windows 上の Outlook では、[**新しい Teams 会議**] オプションはリボンに表示されません。</span><span class="sxs-lookup"><span data-stu-id="f37c7-125">For example, in Outlook on Windows, the **New Teams Meeting** option won't show up in the ribbon.</span></span>

## <a name="allow-channel-meeting-scheduling"></a><span data-ttu-id="f37c7-126">チャネルの会議スケジュールを許可する</span><span class="sxs-lookup"><span data-stu-id="f37c7-126">Allow channel meeting scheduling</span></span>

<span data-ttu-id="f37c7-127">既存の[AllowChannelMeetingScheduling] ポリシーを使用して、チームのチャネルの予定表で作成できるイベントの種類を制御します。</span><span class="sxs-lookup"><span data-stu-id="f37c7-127">Use the existing AllowChannelMeetingScheduling policy to control the types of events that can be created on the team channel calendars.</span></span> <span data-ttu-id="f37c7-128">これはユーザーごとのポリシーであり、会議が始まる前に適用されます。</span><span class="sxs-lookup"><span data-stu-id="f37c7-128">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="f37c7-129">この設定は、ユーザーが Teams チャネルで会議をスケジュールできるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="f37c7-129">This setting controls whether users can schedule a meeting in a Teams channel.</span></span> <span data-ttu-id="f37c7-130">既定では、この設定は[オン] に設定されています。</span><span class="sxs-lookup"><span data-stu-id="f37c7-130">By default, this setting is turned on.</span></span> 

<span data-ttu-id="f37c7-131">このポリシーをオフにすると、ユーザーは新しいチャネル会議を作成できます。</span><span class="sxs-lookup"><span data-stu-id="f37c7-131">If this policy is turned off, users will not be able to create new channel meetings.</span></span> <span data-ttu-id="f37c7-132">ただし、既存のチャネル会議は、イベントの開催者が編集できます。</span><span class="sxs-lookup"><span data-stu-id="f37c7-132">However, existing channel meetings can be edited by the organizer of the event.</span></span>

<span data-ttu-id="f37c7-133">会議のスケジュールは無効になります。</span><span class="sxs-lookup"><span data-stu-id="f37c7-133">Schedule a meeting will be disabled.</span></span>

![Teams の [会議の予約] オプションが表示されたスクリーンショット](media/schedule-meeting-option.png)

<span data-ttu-id="f37c7-135">チャネルの選択が無効になっています。</span><span class="sxs-lookup"><span data-stu-id="f37c7-135">Channel selection is disabled.</span></span>

<span data-ttu-id="f37c7-136">[![会議をスケジュールするチャネルを選択する予定表オプションを示すスクリーンショット。 ](media/meeting-policies-select-a-channel-to-meet-in.png)](media/meeting-policies-select-a-channel-to-meet-in.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="f37c7-136">[ ![Screenshot showing the calendar option for selecting a channel that you want to schedule a meeting in.](media/meeting-policies-select-a-channel-to-meet-in.png) ](media/meeting-policies-select-a-channel-to-meet-in.png#lightbox)</span></span>

<span data-ttu-id="f37c7-137">チャネルの投稿ページで、次の機能が無効になります。</span><span class="sxs-lookup"><span data-stu-id="f37c7-137">In the channel posts page, the following will be disabled:</span></span>

- <span data-ttu-id="f37c7-138">[チャネル返信の作成] ボックスの [**会議のスケジュール**] ボタン</span><span class="sxs-lookup"><span data-stu-id="f37c7-138">**Schedule a meeting** button on the channel reply compose box.</span></span>
  <span data-ttu-id="f37c7-139">![会議をスケジュールするチャネルを選択する予定表オプションを示すスクリーンショット。](media/schedule-meeting-disabled-in-chat2.png)</span><span class="sxs-lookup"><span data-stu-id="f37c7-139">![Screenshot showing the calendar option for selecting a channel in which you want to schedule a meeting.](media/schedule-meeting-disabled-in-chat2.png)</span></span>
  
- <span data-ttu-id="f37c7-140">チャネル ヘッダーの [**会議のスケジュール**] ボタン。</span><span class="sxs-lookup"><span data-stu-id="f37c7-140">**Schedule a meeting** button on the channel header.</span></span>
  <span data-ttu-id="f37c7-141">![会議のスケジュールを設定するチャネルを選択する予定表オプションを示すスクリーンショット。](media/schedule-now-in-header.png)</span><span class="sxs-lookup"><span data-stu-id="f37c7-141">![Screenshot showing the calendar option for selecting a channel through which you want to schedule a meeting.](media/schedule-now-in-header.png)</span></span>

<span data-ttu-id="f37c7-142">[チャネル カレンダー] で、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="f37c7-142">In the channel calendar:</span></span>

- <span data-ttu-id="f37c7-143">チャンネル予定表ヘッダーの[**新しいイベントの追加**] ボタンは、無効になります。</span><span class="sxs-lookup"><span data-stu-id="f37c7-143">**Add new event** button on channel calendar header will be disabled.</span></span>
  <span data-ttu-id="f37c7-144">![会議のスケジュールを設定できるチャネルを選択する予定表オプションを示すスクリーンショット。](media/add-new-event-disabled.png)</span><span class="sxs-lookup"><span data-stu-id="f37c7-144">![Screenshot showing the calendar option for selecting a channel that will enable you to schedule a meeting.](media/add-new-event-disabled.png)</span></span>

- <span data-ttu-id="f37c7-145">ユーザーは、チャネル予定表の時間ブロックをドラッグして選択して、チャネル会議を作成できない。</span><span class="sxs-lookup"><span data-stu-id="f37c7-145">Users will not be able to drag and select a time block on the channel calendar to create a channel meeting.</span></span>

- <span data-ttu-id="f37c7-146">ユーザーは、キーボード ショートカットを使用して、チャネル予定表に会議を作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="f37c7-146">Users cannot use Keyboard shortcuts to create a meeting on the channel calendar.</span></span>

<span data-ttu-id="f37c7-147">管理センターにて</span><span class="sxs-lookup"><span data-stu-id="f37c7-147">In the admin center:</span></span>

<span data-ttu-id="f37c7-148">[アプリのアクセス許可ポリシー] ページの [**Microsoft アプリ**] セクションに、チャネル カレンダー アプリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f37c7-148">The channel calendar app will show up in the **Microsoft apps** section on the app permission policies page.</span></span>

![Teams 管理センターのアプリのアクセス許可ポリシーを示すスクリーンショット。](media/manage-microsoft-apps-policy.png)

## <a name="allow-scheduling-private-meetings"></a><span data-ttu-id="f37c7-150">プライベート会議のスケジュールを許可する</span><span class="sxs-lookup"><span data-stu-id="f37c7-150">Allow scheduling private meetings</span></span>

<span data-ttu-id="f37c7-151">これはユーザーごとのポリシーであり、会議が始まる前に適用されます。</span><span class="sxs-lookup"><span data-stu-id="f37c7-151">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="f37c7-152">この設定は、ユーザーが Teams でプライベート会議をスケジュールできるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="f37c7-152">This setting controls whether users can schedule private meetings in Teams.</span></span> <span data-ttu-id="f37c7-153">チームのチャネルに公開されていない会議はプライベートです。</span><span class="sxs-lookup"><span data-stu-id="f37c7-153">A meeting is private when it's not published to a channel in a team.</span></span>

<span data-ttu-id="f37c7-154">[**プライベート会議のスケジュールを許可する**] および [**チャネルの会議スケジュールを許可する**] を無効にすると、Teams のユーザーに対して [**必須出席者の追加**] および [**チャネルの追加**] オプションが無効になります。</span><span class="sxs-lookup"><span data-stu-id="f37c7-154">Note that if you turn off **Allow scheduling private meetings** and **Allow channel meeting scheduling**,  the **Add required attendees** and **Add channel** options are disabled for users in Teams.</span></span> <span data-ttu-id="f37c7-155">既定では、この設定は[オン] に設定されています。</span><span class="sxs-lookup"><span data-stu-id="f37c7-155">By default, this setting is turned on.</span></span>

## <a name="allow-meet-now-in-private-meetings"></a><span data-ttu-id="f37c7-156">プライベート会議で "今すぐ会議" を許可する</span><span class="sxs-lookup"><span data-stu-id="f37c7-156">Allow Meet now in private meetings</span></span>

<span data-ttu-id="f37c7-157">これはユーザーごとのポリシーであり、会議が始まる前に適用されます。</span><span class="sxs-lookup"><span data-stu-id="f37c7-157">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="f37c7-158">この設定は、ユーザーがアドホック プライベート会議を開始できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="f37c7-158">This setting controls whether a user can start an ad hoc private meeting.</span></span>  <span data-ttu-id="f37c7-159">既定では、この設定は[オン] に設定されています。</span><span class="sxs-lookup"><span data-stu-id="f37c7-159">By default, this setting is turned on.</span></span>

## <a name="designated-presenter-role-mode"></a><span data-ttu-id="f37c7-160">指定された発表者ロール モード</span><span class="sxs-lookup"><span data-stu-id="f37c7-160">Designated presenter role mode</span></span>

<span data-ttu-id="f37c7-161">これは、ユーザーごとのポリシーです。</span><span class="sxs-lookup"><span data-stu-id="f37c7-161">This is a per-user policy.</span></span> <span data-ttu-id="f37c7-162">この設定では、Teams クライアントの **会議オプション** の **誰がプレゼンをするか?** の設定の既定値を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="f37c7-162">This setting lets you change the default value of the **Who can present?** setting in **Meeting options** in the Teams client.</span></span> <span data-ttu-id="f37c7-163">このポリシー設定は、Meet Now (今すぐ会議) を含むすべての会議に影響します。</span><span class="sxs-lookup"><span data-stu-id="f37c7-163">This policy setting affects all meetings, including Meet Now meetings.</span></span>

<span data-ttu-id="f37c7-164">**誰がプレゼンをするか?** の設定を使用すると、会議の開催者は会議の発表者を選択することができます。</span><span class="sxs-lookup"><span data-stu-id="f37c7-164">The **Who can present?** setting lets meeting organizers choose who can be presenters in a meeting.</span></span> <span data-ttu-id="f37c7-165">詳細については、「[Teams 会議の参加者設定の変更](https://support.microsoft.com/article/change-participant-settings-for-a-teams-meeting-53261366-dbd5-45f9-aae9-a70e6354f88e)」 と 「[Teams 会議での役割](https://support.microsoft.com/article/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f37c7-165">To learn more, see [Change participant settings for a Teams meeting](https://support.microsoft.com/article/change-participant-settings-for-a-teams-meeting-53261366-dbd5-45f9-aae9-a70e6354f88e) and [Roles in a Teams meeting](https://support.microsoft.com/article/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019).</span></span>

<span data-ttu-id="f37c7-166">現在、このポリシー設定を構成することができるのは、PowerShell を使用した場合のみです。</span><span class="sxs-lookup"><span data-stu-id="f37c7-166">Currently, you can only use PowerShell to configure this policy setting.</span></span> <span data-ttu-id="f37c7-167">[Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) コマンドレットを使用して、既存の Teams 会議ポリシーを編集することができます。</span><span class="sxs-lookup"><span data-stu-id="f37c7-167">You can edit an existing Teams meeting policy by using the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet.</span></span> <span data-ttu-id="f37c7-168">または、[New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) コマンドレットを使用して、新しい Teams の会議ポリシーを作成し、ユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="f37c7-168">Or, create a new Teams meeting policy by using the [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet and assign it to users.</span></span>

<span data-ttu-id="f37c7-169">Teams の **誰がプレゼンをするか?** 設定の既定値を指定するには、**DesignatedPresenterRoleMode** パラメーターを次のいずれかに設定します。</span><span class="sxs-lookup"><span data-stu-id="f37c7-169">To specify the default value of the **Who can present?** setting in Teams, set the **DesignatedPresenterRoleMode** parameter to one of the following:</span></span>

- <span data-ttu-id="f37c7-170">**EveryoneUserOverride**: すべての会議参加者は発表者になることができます。</span><span class="sxs-lookup"><span data-stu-id="f37c7-170">**EveryoneUserOverride**:  All meeting participants can be presenters.</span></span> <span data-ttu-id="f37c7-171">これが既定値です。</span><span class="sxs-lookup"><span data-stu-id="f37c7-171">This is the default value.</span></span> <span data-ttu-id="f37c7-172">このパラメーターは、 Teams 内の **すべてのユーザー** の設定 に呼応します。</span><span class="sxs-lookup"><span data-stu-id="f37c7-172">This parameter corresponds to the **Everyone** setting in Teams.</span></span>
- <span data-ttu-id="f37c7-173">**EveryoneInCompanyUserOverride**: 組織内の認証済みユーザー (ゲスト ユーザーを含む) は、発表者になることができます。</span><span class="sxs-lookup"><span data-stu-id="f37c7-173">**EveryoneInCompanyUserOverride**: Authenticated users in the organization, including guest users, can be presenters.</span></span> <span data-ttu-id="f37c7-174">このパラメーターは、Teams の **組織内の人たち** 設定に呼応します。</span><span class="sxs-lookup"><span data-stu-id="f37c7-174">This parameter corresponds to the **People in my organization** setting in Teams.</span></span>
- <span data-ttu-id="f37c7-175">**OrganizerOnlyUserOverride**: 会議の開催者のみが発表者となり、他のすべての会議参加者が出席者として指定されます。</span><span class="sxs-lookup"><span data-stu-id="f37c7-175">**OrganizerOnlyUserOverride**: Only the meeting organizer can be a presenter and all meeting participants are designated as attendees.</span></span> <span data-ttu-id="f37c7-176">このパラメーターは、Teams の [**私だけ**] 設定に呼応します。</span><span class="sxs-lookup"><span data-stu-id="f37c7-176">This parameter corresponds to the **Only me** setting in Teams.</span></span>

<span data-ttu-id="f37c7-177">既定値を設定した後でも、会議の開催者はチームの設定を変更し、スケジュールした会議での発表者を選ぶことができることにご注意ください。</span><span class="sxs-lookup"><span data-stu-id="f37c7-177">Keep in mind that after you set the default value, meeting organizers can still change this setting in Teams and choose who can present in the meetings that they schedule.</span></span>

## <a name="meeting-attendance-report"></a><span data-ttu-id="f37c7-178">会議出席レポート</span><span class="sxs-lookup"><span data-stu-id="f37c7-178">Meeting attendance report</span></span>

<span data-ttu-id="f37c7-179">これは、ユーザーごとのポリシーです。</span><span class="sxs-lookup"><span data-stu-id="f37c7-179">This is a per-user policy.</span></span> <span data-ttu-id="f37c7-180">この設定では、会議の開催者が [会議出席レポート](teams-analytics-and-reports/meeting-attendance-report.md)をダウンロードできるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="f37c7-180">This setting controls whether meeting organizers can download the [meeting attendance report](teams-analytics-and-reports/meeting-attendance-report.md).</span></span>

<span data-ttu-id="f37c7-181">現在、このポリシー設定を構成することができるのは、PowerShell を使用した場合のみです。</span><span class="sxs-lookup"><span data-stu-id="f37c7-181">Currently, you can only use PowerShell to configure this policy setting.</span></span> <span data-ttu-id="f37c7-182">[Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) コマンドレットを使用して、既存の Teams 会議ポリシーを編集することができます。</span><span class="sxs-lookup"><span data-stu-id="f37c7-182">You can edit an existing Teams meeting policy by using the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet.</span></span> <span data-ttu-id="f37c7-183">または、[New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) コマンドレットを使用して、新しい Teams の会議ポリシーを作成し、ユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="f37c7-183">Or, create a new Teams meeting policy by using the [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet and assign it to users.</span></span>

<span data-ttu-id="f37c7-184">会議の開催者が会議の出席依頼のレポートをダウンロードできるようにするには、**AllowEngagementReport** パラメーターを [**有効**] に設定します。</span><span class="sxs-lookup"><span data-stu-id="f37c7-184">To enable a meeting organizer to download the meeting attendance report, set the **AllowEngagementReport** parameter  to **Enabled**.</span></span> <span data-ttu-id="f37c7-185">有効にすると、**参加者** ウィンドウに、レポートをダウンロードするためのオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f37c7-185">When enabled, the option to download the report is displayed in the **Participants** pane.</span></span>

<span data-ttu-id="f37c7-186">会議の開催者がレポートをダウンロードしないようにするには、パラメーターを [**無効**] に設定します。</span><span class="sxs-lookup"><span data-stu-id="f37c7-186">To prevent a meeting organizer from downloading the report, set the parameter to **Disabled**.</span></span> <span data-ttu-id="f37c7-187">既定では、この設定は無効になっており、レポートをダウンロードするオプションは利用できません。</span><span class="sxs-lookup"><span data-stu-id="f37c7-187">By default, this setting is disabled and the option to download the report isn't available.</span></span>

## <a name="meeting-provider-for-islands-mode"></a><span data-ttu-id="f37c7-188">諸島モードの会議プロバイダー</span><span class="sxs-lookup"><span data-stu-id="f37c7-188">Meeting provider for Islands mode</span></span>

<span data-ttu-id="f37c7-189">これは、ユーザー単位のポリシーです。</span><span class="sxs-lookup"><span data-stu-id="f37c7-189">This is a per-user policy.</span></span> <span data-ttu-id="f37c7-190">この設定は、*アイランド モードのユーザー* がどの Outlook 会議アドインを使用するかを制御できます。</span><span class="sxs-lookup"><span data-stu-id="f37c7-190">This setting controls which Outlook meeting add-in is used for *users who are in Islands mode*.</span></span> <span data-ttu-id="f37c7-191">Teams 会議アドインのみを使用するか、Teams 会議アドインと Skype for Business 会議アドインの両方を使用するかを指定して、Outlook で会議をスケジュールできます。</span><span class="sxs-lookup"><span data-stu-id="f37c7-191">You can specify whether users can only use the Teams Meeting add-in or both the Teams Meeting and Skype for Business Meeting add-ins to schedule meetings in Outlook.</span></span>

<span data-ttu-id="f37c7-192">このポリシーは、アイランドモードで、Teams の会議ポリシーで **AllowOutlookAddIn** パラメーターが **True** に設定されているユーザーにのみ適用できます。</span><span class="sxs-lookup"><span data-stu-id="f37c7-192">You can only apply this policy to users who are in Islands mode and have the **AllowOutlookAddIn** parameter set to **True** in their Teams meeting policy.</span></span>

<span data-ttu-id="f37c7-193">現在、このポリシーを設定するには PowerShell を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f37c7-193">Currently, you can only use PowerShell to set this policy.</span></span> <span data-ttu-id="f37c7-194">[Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) コマンドレットを使用して、既存の Teams 会議ポリシーを編集することができます。</span><span class="sxs-lookup"><span data-stu-id="f37c7-194">You can edit an existing Teams meeting policy by using the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet.</span></span> <span data-ttu-id="f37c7-195">または、[New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) コマンドレットを使用して、新しい Teams の会議ポリシーを作成し、ユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="f37c7-195">Or, create a new Teams meeting policy by using the [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet and assign it to users.</span></span>

<span data-ttu-id="f37c7-196">ユーザーが使用できる会議アドインを指定するには、次のように **PreferredMeetingProviderForIslandsMode** パラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="f37c7-196">To specify which meeting add-in you want to be available to users, set the **PreferredMeetingProviderForIslandsMode** parameter as follows:</span></span>

- <span data-ttu-id="f37c7-197">パラメーターを **TeamsAndSfB** に設定すると、Outlook の Teams 会議アドインと Skype for Business アドインの両方が有効になります。</span><span class="sxs-lookup"><span data-stu-id="f37c7-197">Set the parameter to **TeamsAndSfB** to enable both the Teams Meeting add-in and Skype for Business add-in in Outlook.</span></span> <span data-ttu-id="f37c7-198">これが既定値です。</span><span class="sxs-lookup"><span data-stu-id="f37c7-198">This is the default value.</span></span>
- <span data-ttu-id="f37c7-199">パラメーターを **Teams** に設定すると、Outlook の Teams 会議アドインのみが有効になります。</span><span class="sxs-lookup"><span data-stu-id="f37c7-199">Set the parameter to **Teams** to enable only the Teams Meeting add-in in Outlook.</span></span> <span data-ttu-id="f37c7-200">このポリシー設定では、今後のすべての会議にTeams の会議への参加リンクがあることが確実になります。</span><span class="sxs-lookup"><span data-stu-id="f37c7-200">This policy setting ensures that all future meetings have a Teams meeting join link.</span></span> <span data-ttu-id="f37c7-201">既存の Skype for Business 会議の参加リンクはTeams には移行されません。</span><span class="sxs-lookup"><span data-stu-id="f37c7-201">It doesn't migrate existing Skype for Business meeting join links to Teams.</span></span> <span data-ttu-id="f37c7-202">このポリシー設定は、ユーザーが Skype for Business への参加、チャット、PSTN 通話、その他の機能を使用することに影響を与えません。ユーザーが Skype for Business の機能を引き続き使用できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="f37c7-202">This policy setting doesn't affect presence, chat, PSTN calling, or any other capabilities in Skype for Business, which means that users will continue to use Skype for Business for these capabilities.</span></span>

  <span data-ttu-id="f37c7-203">パラメーターを **Teams** に設定し、**の TeamsAndSfB** に戻すと、両方の会議アドインが有効になります。</span><span class="sxs-lookup"><span data-stu-id="f37c7-203">If you set the parameter to **Teams**, and then switch back to **TeamsAndSfB**, both meeting add-ins are enabled.</span></span> <span data-ttu-id="f37c7-204">ただし、既存の Teams 会議の参加リンクは、Skype for Business に移行されないことにご注意ください。</span><span class="sxs-lookup"><span data-stu-id="f37c7-204">However, note that existing Teams meeting join links won't be migrated to Skype for Business.</span></span> <span data-ttu-id="f37c7-205">変更の後にスケジュールされた Skype for Business の会議のみが、Skype for Business の会議参加リンクを持つようになります。</span><span class="sxs-lookup"><span data-stu-id="f37c7-205">Only Skype for Business meetings scheduled after the change will have a Skype for Business meeting join link.</span></span>

## <a name="meeting-reactions"></a><span data-ttu-id="f37c7-206">会議の反応</span><span class="sxs-lookup"><span data-stu-id="f37c7-206">Meeting reactions</span></span>

<span data-ttu-id="f37c7-207">AllowMeetingReactions の設定は、PowerShell を使用する場合にのみ適用できます。</span><span class="sxs-lookup"><span data-stu-id="f37c7-207">The AllowMeetingReactions setting can only be applied using PowerShell.</span></span> <span data-ttu-id="f37c7-208">Teams 管理センターから AllowMeetingReactions のオンとオフを切り替えるオプションはありません。</span><span class="sxs-lookup"><span data-stu-id="f37c7-208">There is no option to toggle AllowMeetingReactions on or off from the Teams admin center.</span></span>

<span data-ttu-id="f37c7-209">会議の反応は、既定ではオフになっています。</span><span class="sxs-lookup"><span data-stu-id="f37c7-209">Meeting reactions are Off by default.</span></span> <span data-ttu-id="f37c7-210">ユーザーに対する反応をオフにしても、ユーザーがスケジュールした会議でリアクションを使用できないという意味ではない。</span><span class="sxs-lookup"><span data-stu-id="f37c7-210">Turning off reactions for a user doesn't mean that a user can't use reactions in meetings they schedule.</span></span> <span data-ttu-id="f37c7-211">会議の開催者は、既定の設定に関係なく、会議オプション ページからリアクションを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="f37c7-211">The meeting organizer can still turn on reactions from the meeting option page, regardless of the default setting.</span></span>


## <a name="related-topics"></a><span data-ttu-id="f37c7-212">関連項目</span><span class="sxs-lookup"><span data-stu-id="f37c7-212">Related topics</span></span>

- [<span data-ttu-id="f37c7-213">Teams での PowerShell の概要</span><span class="sxs-lookup"><span data-stu-id="f37c7-213">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="f37c7-214"> Teams でユーザーにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="f37c7-214">Assign policies to your users in Teams</span></span>](assign-policies.md)
- [<span data-ttu-id="f37c7-215">ユーザーから RestrictedAnonymousAccess Teams 会議ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="f37c7-215">Remove the RestrictedAnonymousAccess Teams meeting policy from users</span></span>](meeting-policies-restricted-anonymous-access.md)
