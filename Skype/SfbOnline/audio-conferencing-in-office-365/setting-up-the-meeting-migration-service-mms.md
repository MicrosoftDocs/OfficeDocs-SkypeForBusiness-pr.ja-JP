---
title: 会議移行サービス (MMS) を使用する
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 031f09c0-9d2a-487a-b6db-b5d4bed6d16a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 会議移行サービス (MMS) は、バックグラウンドで実行されるサービスで、Skype for Business および Microsoft Teams の会議を自動的に更新します。 MMS はユーザーが会議移行ツールを実行して Skype for Business および Microsoft Teams 会議を更新しなくても済むように設計されています。
ms.openlocfilehash: 187e1e7dbedc57249c2e2cc3c60ea4c365f470c1
ms.sourcegitcommit: afc7edd03f4baa1d75f9642d4dbce767fec69b00
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "40962545"
---
# <a name="using-the-meeting-migration-service-mms"></a><span data-ttu-id="fe366-104">会議移行サービス (MMS) を使用する</span><span class="sxs-lookup"><span data-stu-id="fe366-104">Using the Meeting Migration Service (MMS)</span></span>

<span data-ttu-id="fe366-105">会議移行サービス (MMS) は、次のシナリオでユーザーの既存の会議を更新するサービスです。</span><span class="sxs-lookup"><span data-stu-id="fe366-105">The Meeting Migration Service (MMS) is service that updates a user’s existing meetings in the following scenarios:</span></span>

- <span data-ttu-id="fe366-106">ユーザーがオンプレミスからクラウドに移行される場合 (Skype for Business Online か、または teams のみ)。</span><span class="sxs-lookup"><span data-stu-id="fe366-106">When a user is migrated from on-premises to the cloud (whether to Skype for Business Online or to TeamsOnly).</span></span>
- <span data-ttu-id="fe366-107">管理者がユーザーの電話会議設定に変更を加えた場合</span><span class="sxs-lookup"><span data-stu-id="fe366-107">When an admin makes a change to the user’s audio conferencing settings</span></span> 
- <span data-ttu-id="fe366-108">オンラインユーザーが Teams のみにアップグレードされた場合、または TeamsUpgradePolicy のユーザーのモードが SfBwithTeamsCollabAndMeetings に設定されている場合</span><span class="sxs-lookup"><span data-stu-id="fe366-108">When an online user is upgraded to Teams only, or when a user's mode in TeamsUpgradePolicy is set to SfBwithTeamsCollabAndMeetings</span></span>
- <span data-ttu-id="fe366-109">PowerShell を使用する場合</span><span class="sxs-lookup"><span data-stu-id="fe366-109">When you use PowerShell</span></span> 


<span data-ttu-id="fe366-110">既定では、これらの場合、MMS は各ケースで自動的にトリガーされますが、管理者はテナントレベルで無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="fe366-110">By default, MMS is automatically triggered in each of these cases, although admins can disable it at the tenant level.</span></span> <span data-ttu-id="fe366-111">さらに、管理者は PowerShell コマンドレットを使って、特定のユーザーの会議の移行を手動でトリガーすることもできます。</span><span class="sxs-lookup"><span data-stu-id="fe366-111">In addition, admins can use a PowerShell cmdlet to manually trigger meeting migration for a given user.</span></span>


<span data-ttu-id="fe366-112">**制限**: 次のいずれかが該当する場合、会議移行サービスは使用できません。</span><span class="sxs-lookup"><span data-stu-id="fe366-112">**Limitations**: The meeting migration service can't be used if any of the following apply:</span></span>

- <span data-ttu-id="fe366-113">ユーザーのメールボックスは、オンプレミスの Exchange でホストされています。</span><span class="sxs-lookup"><span data-stu-id="fe366-113">The user’s mailbox is hosted in Exchange on-premises.</span></span>
- <span data-ttu-id="fe366-114">ユーザーはクラウドから Skype for Business Server のオンプレミスに移行されています。</span><span class="sxs-lookup"><span data-stu-id="fe366-114">The user is being migrated from the cloud to Skype for Business Server on-premises.</span></span>

<span data-ttu-id="fe366-115">このような場合、エンドユーザーは[会議移行ツール](https://www.microsoft.com/en-us/download/details.aspx?id=51659)を使用して、代わりに自分の会議を移行することができます。</span><span class="sxs-lookup"><span data-stu-id="fe366-115">In these situations, end users can use the [Meeting Migration Tool](https://www.microsoft.com/en-us/download/details.aspx?id=51659) to migrate their own meetings instead.</span></span>

## <a name="how-mms-works"></a><span data-ttu-id="fe366-116">MMS のしくみ</span><span class="sxs-lookup"><span data-stu-id="fe366-116">How MMS works</span></span>

<span data-ttu-id="fe366-117">特定のユーザーに対して MMS がトリガーされると、そのユーザーへの移行要求がキューに格納されます。</span><span class="sxs-lookup"><span data-stu-id="fe366-117">When MMS is triggered for a given user, a migration request for that user is placed in a queue.</span></span> <span data-ttu-id="fe366-118">競合状態を回避するために、キュー要求は、少なくとも90分が経過するまで処理されません。</span><span class="sxs-lookup"><span data-stu-id="fe366-118">To avoid any race conditions, the queued request is deliberately not processed until at least 90 minutes have gone by.</span></span> <span data-ttu-id="fe366-119">MMS は、要求を処理すると、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="fe366-119">Once MMS processes the request, it performs the following tasks:</span></span>

1. <span data-ttu-id="fe366-120">ユーザーのメールボックスが、そのユーザーによって開催され、今後スケジュールされているすべての既存の会議に対して検索されます。</span><span class="sxs-lookup"><span data-stu-id="fe366-120">It searches that user’s mailbox for all existing meetings organized by that user and scheduled in the future.</span></span>
2. <span data-ttu-id="fe366-121">ユーザーのメールボックスに記載されている情報に基づいて、そのユーザーのチームまたは Skype for Business Online の新しい会議を更新またはスケジュールします。</span><span class="sxs-lookup"><span data-stu-id="fe366-121">Based on the information found in the user’s mailbox, it either updates or schedules new meetings in either Teams or Skype for Business Online for that user, depending on the exact scenario.</span></span>
3. <span data-ttu-id="fe366-122">メールメッセージで、会議の詳細のオンライン会議ブロックを置き換えます。</span><span class="sxs-lookup"><span data-stu-id="fe366-122">In the email message, it replaces the online meeting block in the meeting details.</span></span>
4. <span data-ttu-id="fe366-123">その会議の更新されたバージョンは、会議の開催者の代理としてすべての会議の受信者に送信されます。</span><span class="sxs-lookup"><span data-stu-id="fe366-123">It sends the updated version of that meeting to all meeting recipients on behalf of the meeting organizer.</span></span> <span data-ttu-id="fe366-124">会議の出席者は、更新された会議の座標をメールで受け取ります。</span><span class="sxs-lookup"><span data-stu-id="fe366-124">Meeting invitees will receive a meeting update with updated meeting coordinates in their email.</span></span> 

    ![MMS で更新される会議ブロック。](../images/210a03ee-30c1-46f3-808f-4c2ebdaa3ea1.png)

<span data-ttu-id="fe366-126">MMS がトリガーされた時点では、通常、ユーザーの会議が移行されるまでに約2時間かかります。</span><span class="sxs-lookup"><span data-stu-id="fe366-126">From the time MMS is triggered, it typically takes about 2 hours until the user’s meetings are migrated.</span></span> <span data-ttu-id="fe366-127">ただし、ユーザーの会議数が多い場合は、時間がかかることがあります。</span><span class="sxs-lookup"><span data-stu-id="fe366-127">However, if the user has a large number of meetings, it might take longer.</span></span> <span data-ttu-id="fe366-128">MMS でユーザーの会議の移行中にエラーが発生した場合、24時間の間に、定期的に最大9回再試行されます。</span><span class="sxs-lookup"><span data-stu-id="fe366-128">If MMS encounters an error migrating one or more meetings for the user, it will periodically retry up to 9 times over the span of 24 hours.</span></span>

<span data-ttu-id="fe366-129">**注**:</span><span class="sxs-lookup"><span data-stu-id="fe366-129">**Notes**:</span></span>

- <span data-ttu-id="fe366-p106">MMS は会議が移行されるときにオンライン会議の情報ブロックのすべてを置き換えます。このため、ユーザーがそのブロックを編集した場合は、それらの変更は上書きされます。オンライン会議の情報ブロック以外の会議の詳細に含まれているコンテンツは影響しません。</span><span class="sxs-lookup"><span data-stu-id="fe366-p106">MMS replaces everything in the online meeting information block when a meeting is migrated. Therefore, if a user has edited that block, their changes will be overwritten. Any content they have in the meeting details outside of the online meeting information block won't be affected.</span></span>
- <span data-ttu-id="fe366-133">Outlook on the Web で [ **Skype 会議の追加**] ボタンをクリックして、または Outlook 用の Skype 会議アドインを使用してスケジュールされた Skype for Business 会議および Microsoft Teams 会議のみが移行されます。</span><span class="sxs-lookup"><span data-stu-id="fe366-133">Only the Skype for Business or Microsoft Teams meetings that were scheduled by clicking the **Add Skype meeting** button in Outlook on the Web or by using the Skype Meeting add-in for Outlook are migrated.</span></span> <span data-ttu-id="fe366-134">ある会議から新しい会議に Skype オンライン会議の情報をコピーして貼り付けると、元のサービスに会議がないため、新しい会議は更新されません。</span><span class="sxs-lookup"><span data-stu-id="fe366-134">If a user copies and pastes the Skype online meeting information from one meeting to a new meeting, that new meeting won't be updated since there is no meeting in the original service.</span></span>
- <span data-ttu-id="fe366-135">会議に作成または添付された会議コンテンツ (ホワイトボード、投票など) は、MMS の実行後も保持されません。</span><span class="sxs-lookup"><span data-stu-id="fe366-135">Meeting content that was created or attached to the meeting (whiteboards, polls, and so on) won't be retained after MMS runs.</span></span> <span data-ttu-id="fe366-136">会議の開催者が事前にコンテンツを会議に添付している場合、そのコンテンツは MMS の動作後に再作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe366-136">If your meeting organizers have attached content to the meetings in advance, the content will need to be recreated after MMS runs.</span></span>
- <span data-ttu-id="fe366-137">予定表の項目内、および Skype 会議からの共有の会議ノートへのリンクも上書きされます。</span><span class="sxs-lookup"><span data-stu-id="fe366-137">The link to the shared meeting notes in the calendar item and also from within the Skype meeting also will be overwritten.</span></span> <span data-ttu-id="fe366-138">OneNote に保存されている実際の会議ノートはそのまま残ります。これは、上書きされた共有ノートへのリンクにすぎません。</span><span class="sxs-lookup"><span data-stu-id="fe366-138">Note that the actual meeting notes stored in OneNote will still be there; it is only the link to the shared notes that is overwritten.</span></span>
- <span data-ttu-id="fe366-139">(開催者を含めて) 250 人を超える参加者がいる会議は移行できません。</span><span class="sxs-lookup"><span data-stu-id="fe366-139">Meetings with more than 250 attendees (including the organizer) won't be migrated.</span></span>
- <span data-ttu-id="fe366-140">招待状の本文に含まれる一部の UNICODE 文字が誤って、ï、¿、1/2、のいずれかの特殊文字に更新されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fe366-140">Some UNICODE characters in the body of the invite might be incorrectly updated to one of the following special characters: ï, ¿, ½, �.</span></span>

## <a name="triggering-mms-for-a-user"></a><span data-ttu-id="fe366-141">ユーザー向けの MMS のトリガー</span><span class="sxs-lookup"><span data-stu-id="fe366-141">Triggering MMS for a user</span></span>

<span data-ttu-id="fe366-142">このセクションでは、次のいずれかの場合に MMS がトリガーされた場合の動作について説明します。</span><span class="sxs-lookup"><span data-stu-id="fe366-142">This section describes what happens when MMS is triggered in each of the following cases:</span></span>

- <span data-ttu-id="fe366-143">ユーザーがオンプレミスからクラウドに移行される場合</span><span class="sxs-lookup"><span data-stu-id="fe366-143">When a user is migrated from on-premises to the cloud</span></span>
- <span data-ttu-id="fe366-144">管理者がユーザーの電話会議設定に変更を加えた場合</span><span class="sxs-lookup"><span data-stu-id="fe366-144">When an admin makes a change to the user’s audio conferencing settings</span></span> 
- <span data-ttu-id="fe366-145">TeamsUpgradePolicy でユーザーのモードが TeamsOnly または SfBWithTeamsCollabAndMeetings (Powershell または Teams 管理ポータルを使って) に設定されている場合</span><span class="sxs-lookup"><span data-stu-id="fe366-145">When the user's mode in TeamsUpgradePolicy is set to either TeamsOnly or SfBWithTeamsCollabAndMeetings (using either Powershell or the Teams Admin Portal)</span></span>
- <span data-ttu-id="fe366-146">PowerShell コマンドレットを使用する場合は、スタート-Csexmigration の移行</span><span class="sxs-lookup"><span data-stu-id="fe366-146">When you use the PowerShell cmdlet, Start-CsExMeetingMigration</span></span>

### <a name="updating-meetings-when-you-move-an-on-premises-user-to-the-cloud"></a><span data-ttu-id="fe366-147">オンプレミスユーザーをクラウドに移行したときの会議の更新</span><span class="sxs-lookup"><span data-stu-id="fe366-147">Updating meetings when you move an on-premises user to the cloud</span></span>

<span data-ttu-id="fe366-148">これは、MMS がユーザーにより円滑な切り替えを作成できる最も一般的なシナリオです。</span><span class="sxs-lookup"><span data-stu-id="fe366-148">This is the most common scenario where MMS helps create a smoother transition for your users.</span></span> <span data-ttu-id="fe366-149">会議の移行を行わなければ、オンプレミスの Skype for Business Server のユーザーによって開催された既存の会議は、ユーザーがオンラインに移行した後は機能しなくなります。</span><span class="sxs-lookup"><span data-stu-id="fe366-149">Without meeting migration, existing meetings organized by a user in Skype for Business Server on-premises would no longer work once the user is moved online.</span></span> <span data-ttu-id="fe366-150">そのため、オンプレミスの管理ツール ( `Move-CsUser`または [管理者] コントロールパネル) を使用してユーザーをクラウドに移動すると、既存の会議は次のように自動的にクラウドに移動されます。</span><span class="sxs-lookup"><span data-stu-id="fe366-150">Therefore, when you use the on-premises admin tools (either `Move-CsUser` or the Admin Control Panel) to move a user to the cloud, existing meetings are automatically moved to the cloud as follows:</span></span>

- <span data-ttu-id="fe366-151">`MoveToTeams`スイッチ`Move-CsUser`が指定されている場合、会議はチームに直接移行され、ユーザーは Teams の唯一のモードになります。</span><span class="sxs-lookup"><span data-stu-id="fe366-151">If the `MoveToTeams` switch in `Move-CsUser` is specified, meetings are migrated directly to Teams and the user will be in TeamsOnly mode.</span></span> <span data-ttu-id="fe366-152">このスイッチを使用するには、CU8 以降の Skype for Business Server 2015 が必要です。</span><span class="sxs-lookup"><span data-stu-id="fe366-152">Use of this switch requires Skype for Business Server 2015 with CU8 or later.</span></span> <span data-ttu-id="fe366-153">これらのユーザーは、skype for business クライアントまたは Skype 会議アプリを使用して、招待されている可能性のある Skype for Business 会議に引き続き参加できます。</span><span class="sxs-lookup"><span data-stu-id="fe366-153">These users can still join any Skype for Business meeting they may be invited to, using either the Skype for Business client or the Skype Meeting App.</span></span>
- <span data-ttu-id="fe366-154">それ以外の場合、会議は Skype for Business Online に移行されます。</span><span class="sxs-lookup"><span data-stu-id="fe366-154">Otherwise meetings are migrated to Skype for Business Online.</span></span>

<span data-ttu-id="fe366-155">どちらの場合も、ユーザーに電話会議ライセンスが割り当てられてからクラウドに移動された場合、会議はダイヤルイン座標で作成されます。</span><span class="sxs-lookup"><span data-stu-id="fe366-155">In either case, if the user has been assigned an Audio Conferencing license before being moved to the cloud, the meetings will be created with dial-in coordinates.</span></span> <span data-ttu-id="fe366-156">ユーザーをオンプレミスからクラウドに移動し、そのユーザーが電話会議を使用するようにする場合は、最初に電話会議を割り当てることをお勧めします。これにより、1つの会議の移行のみが開始されるようになります。</span><span class="sxs-lookup"><span data-stu-id="fe366-156">If you move a user from on-premises to the cloud and you intend for that user to use Audio Conferencing, we recommend that you first assign the audio conference before you move the user so that only 1 meeting migration is triggered.</span></span>


### <a name="updating-meetings-when-a-users-audio-conferencing-settings-change"></a><span data-ttu-id="fe366-157">ユーザーの電話会議の設定が変更されるときの会議の更新</span><span class="sxs-lookup"><span data-stu-id="fe366-157">Updating meetings when a user's audio conferencing settings change</span></span>

<span data-ttu-id="fe366-158">次のような場合、MMS は既存の Skype for Business および Microsoft Teams の会議を更新して、ダイヤルインの調整を追加、削除、または変更します。</span><span class="sxs-lookup"><span data-stu-id="fe366-158">In the following cases, MMS will update existing Skype for Business and Microsoft Teams meetings to add, remove, or modify dial-in coordinates:</span></span>

- <span data-ttu-id="fe366-159">Microsoft 電話会議サービスライセンスをユーザーに割り当てたり、削除したりする場合、そのユーザーはサードパーティの電話会議プロバイダーに対して有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="fe366-159">When you assign or remove a Microsoft Audio Conferencing service license to a user, and that user is not enabled for a third-party audio conferencing provider.</span></span>
- <span data-ttu-id="fe366-160">ユーザーの電話会議プロバイダーを他のプロバイダーから Microsoft に変更すると、そのユーザーに Microsoft 電話会議ライセンスが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="fe366-160">When you change the audio conferencing provider of a user from any other provider to Microsoft, provided the user is assigned a Microsoft Audio Conferencing license.</span></span> <span data-ttu-id="fe366-161">詳細については、「 [Microsoft を電話会議プロバイダーとして割り当てる](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe366-161">For more information, see [Assign Microsoft as the audio conferencing provider](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).</span></span> <span data-ttu-id="fe366-162">また、サードパーティの電話会議プロバイダー (ACP) のサポートは、[前に発表](https://docs.microsoft.com/skypeforbusiness/legal-and-regulatory/end-of-integration-with-3rd-party-providers)した2019年4月1日に終了する予定です。</span><span class="sxs-lookup"><span data-stu-id="fe366-162">Also note that support for third party audio conferencing providers [ACP] is scheduled for end of life on April 1, 2019, as [previously announced](https://docs.microsoft.com/skypeforbusiness/legal-and-regulatory/end-of-integration-with-3rd-party-providers).</span></span>
- <span data-ttu-id="fe366-163">ユーザーの電話会議を有効または無効にする場合。</span><span class="sxs-lookup"><span data-stu-id="fe366-163">When you enable or disable audio conferencing for a user.</span></span>
- <span data-ttu-id="fe366-164">パブリック会議を使用するように構成されたユーザーの会議 ID を変更またはリセットする場合。</span><span class="sxs-lookup"><span data-stu-id="fe366-164">When you change or reset the conference ID for a user configured to use public meetings.</span></span>
- <span data-ttu-id="fe366-165">ユーザーを新しい電話会議ブリッジに移行する場合</span><span class="sxs-lookup"><span data-stu-id="fe366-165">When you move the user to a new audio conferencing bridge.</span></span>
- <span data-ttu-id="fe366-166">電話会議ブリッジの電話番号が割り当てられていない場合。</span><span class="sxs-lookup"><span data-stu-id="fe366-166">When a phone number from a audio conferencing bridge is unassigned.</span></span> <span data-ttu-id="fe366-167">これは、追加の手順が必要な複雑なシナリオです。</span><span class="sxs-lookup"><span data-stu-id="fe366-167">This is a complex scenario that requires additional steps.</span></span> <span data-ttu-id="fe366-168">詳細については、「[電話会議ブリッジの電話番号を変更](https://docs.microsoft.com/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe366-168">For more information, see [Change the phone numbers on your audio conferencing bridge](https://docs.microsoft.com/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).</span></span>

<span data-ttu-id="fe366-p115">ユーザーの電話会議の設定に対する変更の一部は、MMS をトリガーしません。特に、次の 2 つの変更では、MMS によって会議が更新されません。</span><span class="sxs-lookup"><span data-stu-id="fe366-p115">Not all changes to a user's audio conferencing settings trigger MMS. Specifically, the following two changes won't result in MMS updating meetings:</span></span>

- <span data-ttu-id="fe366-171">会議の開催者の SIP アドレスを変更する場合 (SIP ユーザー名または SIP ドメインのいずれか)</span><span class="sxs-lookup"><span data-stu-id="fe366-171">When you change the SIP address for the meeting organizer (either their SIP user name or their SIP domain)</span></span>
- <span data-ttu-id="fe366-172">`Update-CsTenantMeetingUrl`コマンドを使用して組織の会議 URL を変更した場合。</span><span class="sxs-lookup"><span data-stu-id="fe366-172">When you change your organization's meeting URL using the `Update-CsTenantMeetingUrl` command.</span></span>


### <a name="updating-meetings-when-assigning-teamsupgradepolicy"></a><span data-ttu-id="fe366-173">TeamsUpgradePolicy を割り当てたときの会議の更新</span><span class="sxs-lookup"><span data-stu-id="fe366-173">Updating meetings when assigning TeamsUpgradePolicy</span></span>

<span data-ttu-id="fe366-174">既定では、ユーザーに with `TeamsUpgradePolicy` `mode=TeamsOnly`または`mode= SfBWithTeamsCollabAndMeetings`のインスタンスが付与されると、会議の移行が自動的にトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="fe366-174">By default, meeting migration is automatically triggered when a user is granted an instance of `TeamsUpgradePolicy` with `mode=TeamsOnly` or `mode= SfBWithTeamsCollabAndMeetings`.</span></span> <span data-ttu-id="fe366-175">これらのモードのいずれかを使用して会議を移行したくない場合`MigrateMeetingsToTeams $false`は`Grant-CsTeamsUpgradePolicy` 、(PowerShell を使用する場合) を指定するか、ユーザーの共存モード (Teams 管理ポータルを使用している場合) を設定するときに [会議を移行する] チェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="fe366-175">If you do not want to migrate meetings when granting either of these modes, then specify `MigrateMeetingsToTeams $false` in `Grant-CsTeamsUpgradePolicy` (if using PowerShell) or uncheck the box to migrate meetings when setting a user's coexistence mode (if using the Teams admin portal).</span></span>

<span data-ttu-id="fe366-176">次の点にも注意してください。</span><span class="sxs-lookup"><span data-stu-id="fe366-176">Also note the following:</span></span>

- <span data-ttu-id="fe366-177">会議の移行は、特定のユーザー `TeamsUpgradePolicy`に付与した場合にのみ呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="fe366-177">Meeting migration is only invoked when you grant `TeamsUpgradePolicy` for a specific user.</span></span> <span data-ttu-id="fe366-178">*テナント全体*に`TeamsUpgradePolicy`対し`mode=TeamsOnly`て`mode=SfBWithTeamsCollabAndMeetings`付与した場合、会議の移行は呼び出されません。</span><span class="sxs-lookup"><span data-stu-id="fe366-178">If you grant `TeamsUpgradePolicy` with `mode=TeamsOnly` or `mode=SfBWithTeamsCollabAndMeetings` on a *tenant-wide* basis, meeting migration is not invoked.</span></span>
- <span data-ttu-id="fe366-179">ユーザーは、ユーザーがオンラインになっている場合にのみ、teams Sonly モードを許可されます。</span><span class="sxs-lookup"><span data-stu-id="fe366-179">A user can only be granted TeamsOnly mode if the user is homed online.</span></span> <span data-ttu-id="fe366-180">ホームオンプレミスのユーザーは、前の説明`Move-CsUser`に従って移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe366-180">Users that are homed on-premises must be moved using `Move-CsUser` as previously described.</span></span>
- <span data-ttu-id="fe366-181">TeamsOnly または SfBWithTeamsCollabAndMeetings 以外のモードを付与しても、既存の Teams 会議を Skype for Business 会議に変換することはできません。</span><span class="sxs-lookup"><span data-stu-id="fe366-181">Granting a mode other than TeamsOnly or SfBWithTeamsCollabAndMeetings does not convert existing Teams meetings to Skype for Business meetings.</span></span>

### <a name="trigger-meeting-migration-manually-via-powershell-cmdlet"></a><span data-ttu-id="fe366-182">PowerShell コマンドレットを使用して手動で会議移行を開始する</span><span class="sxs-lookup"><span data-stu-id="fe366-182">Trigger Meeting Migration manually via PowerShell cmdlet</span></span>

<span data-ttu-id="fe366-183">自動会議の移行に加えて、管理者は、コマンドレット`Start-CsExMeetingMigration`を実行することで、ユーザーの会議の移行を手動でトリガーすることができます。</span><span class="sxs-lookup"><span data-stu-id="fe366-183">In addition to automatic meeting migrations, admins can manually trigger meeting migration for a user by running the cmdlet `Start-CsExMeetingMigration`.</span></span> <span data-ttu-id="fe366-184">このコマンドレットは、指定したユーザーの移行要求をキューに出します。</span><span class="sxs-lookup"><span data-stu-id="fe366-184">This cmdlet queues a migration request for the specified user.</span></span>  <span data-ttu-id="fe366-185">必須のパラメーターに加え`Identity`て、次の2つのパラメーター `SourceMeetingType`を`TargetMeetingType`指定する必要があります。これにより、会議の移行方法を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="fe366-185">In addition to the required `Identity` parameter, it takes two optional parameters, `SourceMeetingType` and `TargetMeetingType`, which allow you to specify how to migrate meetings:</span></span>

<span data-ttu-id="fe366-186">**Target会議の種類:**</span><span class="sxs-lookup"><span data-stu-id="fe366-186">**TargetMeetingType:**</span></span>

- <span data-ttu-id="fe366-187">を`TargetMeetingType Current`使用すると、Skype for business 会議は Skype for business 会議のままであり、teams 会議も teams 会議のままになります。</span><span class="sxs-lookup"><span data-stu-id="fe366-187">Using `TargetMeetingType Current` specifies that Skype for Business meetings remain Skype for Business meetings and Teams meetings remain Teams meetings.</span></span> <span data-ttu-id="fe366-188">ただし、電話会議の座標が変更され、オンプレミスの Skype for Business 会議が Skype for Business Online に移行される場合があります。</span><span class="sxs-lookup"><span data-stu-id="fe366-188">However audio conferencing coordinates might be changed, and any on-premises Skype for Business meetings would be migrated to Skype for Business Online.</span></span> <span data-ttu-id="fe366-189">これは、Target会議の種類の既定値です。</span><span class="sxs-lookup"><span data-stu-id="fe366-189">This is the default value for TargetMeetingType.</span></span>
- <span data-ttu-id="fe366-190">[ `TargetMeetingType Teams`使用] では、会議が Skype for business online とオンプレミスのどちらでホストされているかにかかわらず、どの電話会議の更新が必要かに関係なく、既存の会議を Teams に移行する必要があることを指定します。</span><span class="sxs-lookup"><span data-stu-id="fe366-190">Using `TargetMeetingType Teams` specifies that any existing meeting must be migrated to Teams, regardless of whether the meeting is hosted in Skype for Business online or on-premises, and regardless of whether any audio conferencing updates are required.</span></span> 

<span data-ttu-id="fe366-191">**SourceMeetingType:**</span><span class="sxs-lookup"><span data-stu-id="fe366-191">**SourceMeetingType:**</span></span>
- <span data-ttu-id="fe366-192">[ `SourceMeetingType SfB`使用] は、Skype for business 会議 (オンプレミスまたはオンライン) のみを更新する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="fe366-192">Using `SourceMeetingType SfB` indicates that only Skype for Business meetings (whether on-premises or online) should be updated.</span></span>
- <span data-ttu-id="fe366-193">は`SourceMeetingType Teams` 、Teams 会議のみを更新する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="fe366-193">Using `SourceMeetingType Teams` indicates that only Teams meetings should be updated.</span></span>
- <span data-ttu-id="fe366-194">[ `SourceMeetingType All`使用] は、Skype for business 会議と Teams 会議の両方を更新する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="fe366-194">Using `SourceMeetingType All` indicates that both Skype for Business meetings and Teams meetings should be updated.</span></span> <span data-ttu-id="fe366-195">これは、SourceMeetingType の既定値です。</span><span class="sxs-lookup"><span data-stu-id="fe366-195">This is the default value for SourceMeetingType.</span></span>
    

<span data-ttu-id="fe366-196">次の例は、ユーザー ashaw@contoso.com の会議の移行を開始して、すべての会議を Teams に移行できるようにする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="fe366-196">The example below shows how to initiate meeting migration for user ashaw@contoso.com so that all meetings are migrated to Teams:</span></span>

```PowerShell
Start-CsExMeetingMigration -Identity ashaw@contoso.com -TargetMeetingType Teams
```



## <a name="managing-mms"></a><span data-ttu-id="fe366-197">MMS の管理</span><span class="sxs-lookup"><span data-stu-id="fe366-197">Managing MMS</span></span>

<span data-ttu-id="fe366-198">Windows PowerShell を使用すると、進行中の移行の状態を確認し、会議の移行を手動でトリガーして、移行を完全に無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="fe366-198">Using Windows PowerShell, you can check the status of ongoing migrations, manually trigger meeting migration, and disable migration altogether.</span></span> 

### <a name="check-the-status-of-meeting-migrations"></a><span data-ttu-id="fe366-199">会議の移行の状態を確認する</span><span class="sxs-lookup"><span data-stu-id="fe366-199">Check the status of meeting migrations</span></span>

<span data-ttu-id="fe366-200">この`Get-CsMeetingMigrationStatus`コマンドレットを使用して、会議の移行の状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="fe366-200">You use the `Get-CsMeetingMigrationStatus` cmdlet to check the status of meeting migrations.</span></span> <span data-ttu-id="fe366-201">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="fe366-201">Below are some examples.</span></span>

- <span data-ttu-id="fe366-202">すべての MMS の移行の概要ステータスを取得するには、次のコマンドを実行して、すべての移行状態を示す表形式のビューを提供します。</span><span class="sxs-lookup"><span data-stu-id="fe366-202">To get a summary status of all MMS migrations, run the following command which provides a tabular view of all migration states:</span></span>

    ```PowerShell
    Get-CsMeetingMigrationStatus -SummaryOnly

    State      UserCount
    ------     ---------
    Pending      21
    InProgress    6
    Failed            2 
    Succeeded   131
    ```
- <span data-ttu-id="fe366-203">指定した期間内のすべての移行の詳細情報を取得する`StartTime`に`EndTime`は、and パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="fe366-203">To get full details of all migrations within a specific time period, use the `StartTime` and `EndTime` parameters.</span></span> <span data-ttu-id="fe366-204">たとえば、次のコマンドは、2018年10月1日から2018年10月8日までに発生したすべての移行に関する完全な詳細情報を返します。</span><span class="sxs-lookup"><span data-stu-id="fe366-204">For example, the following command will return full details on all migrations that occurred from October 1, 2018 to October 8, 2018.</span></span>

    ```PowerShell
    Get-CsMeetingMigrationStatus -StartTime "10/1/2018" -EndTime "10/8/2018"
    ```
- <span data-ttu-id="fe366-205">特定のユーザーの移行の状態を確認するには、 `Identity`パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="fe366-205">To check the status of migration for a specific user, use the `Identity` parameter.</span></span> <span data-ttu-id="fe366-206">たとえば、次のコマンドは、ユーザー ashaw@contoso.com の状態を返します。</span><span class="sxs-lookup"><span data-stu-id="fe366-206">For example, the following command will return the status for the user ashaw@contoso.com:</span></span>

    ```PowerShell
    Get-CsMeetingMigrationStatus -Identity ashaw@contoso.com
    ```
<span data-ttu-id="fe366-207">失敗した移行が表示される場合は、問題を解決するまで、ユーザーが開催した会議にダイヤルインできないため、できるだけ早くこの問題を解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe366-207">If you see any migrations that have failed, take action to resolve these issues as soon as possible, since people won't be able to dial-in to the meetings organized by those users until you resolve them.</span></span> <span data-ttu-id="fe366-208">失敗`Get-CsMeetingMigrationStatus`状態の移行が表示された場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="fe366-208">If `Get-CsMeetingMigrationStatus` shows any migrations in a failed state, perform these steps:</span></span>
 
1. <span data-ttu-id="fe366-209">影響を受けているユーザーを特定します。</span><span class="sxs-lookup"><span data-stu-id="fe366-209">Determine which users are affected.</span></span> <span data-ttu-id="fe366-210">次のコマンドを実行して、影響を受けているユーザーと、報告された特定のエラーのリストを取得します。</span><span class="sxs-lookup"><span data-stu-id="fe366-210">Run the following command to get the list of affected users, and the specific error that was reported:</span></span>

    ```PowerShell
    Get-CsMeetingMigrationStatus| Where {$_.State -eq "Failed"}| Format-Table UserPrincipalName, LastMessage
    ```
2. <span data-ttu-id="fe366-211">影響を受けるユーザーごとに、会議移行ツールを実行して、手動で会議を移行します。</span><span class="sxs-lookup"><span data-stu-id="fe366-211">For each affected user, run the Meeting Migration Tool to manually migrate their meetings.</span></span>

3. <span data-ttu-id="fe366-212">会議移行ツールを使用しても移行が機能しない場合には、次の 2 つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="fe366-212">If migration still doesn't work with the Meeting Migration Tool, you have two options:</span></span>

    - <span data-ttu-id="fe366-213">ユーザーに新しい Skype 会議を作成してもらいます。</span><span class="sxs-lookup"><span data-stu-id="fe366-213">Have the users create new Skype meetings.</span></span>
    - <span data-ttu-id="fe366-214">[サポートに問い合わせます](https://go.microsoft.com/fwlink/p/?LinkID=518322)。</span><span class="sxs-lookup"><span data-stu-id="fe366-214">[Contact support](https://go.microsoft.com/fwlink/p/?LinkID=518322).</span></span>


### <a name="enabling-and-disabling-mms"></a><span data-ttu-id="fe366-215">MMS の有効化と無効化</span><span class="sxs-lookup"><span data-stu-id="fe366-215">Enabling and disabling MMS</span></span>

<span data-ttu-id="fe366-216">MMS は、すべての組織に対して既定で有効になっていますが、次の方法で無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="fe366-216">MMS is enabled by default for all organizations, but it can be disabled as follows:</span></span>

- <span data-ttu-id="fe366-217">テナントに対して完全に無効にします。</span><span class="sxs-lookup"><span data-stu-id="fe366-217">Disable entirely for the tenant.</span></span> 
- <span data-ttu-id="fe366-218">電話会議に関連する変更についてのみ無効にします。</span><span class="sxs-lookup"><span data-stu-id="fe366-218">Disable only for changes related to audio conferencing.</span></span> <span data-ttu-id="fe366-219">この場合でも、ユーザーがオンプレミスからクラウドに移行された場合、またはで`TeamsUpgradePolicy`Teams sonly モードまたは SfBWithTeamsCollabAndMeetings モードを許可している場合は、MMS が実行されます。</span><span class="sxs-lookup"><span data-stu-id="fe366-219">In this case, MMS will still run when a user is migrated from on-premises to the cloud or when you grant TeamsOnly mode or SfBWithTeamsCollabAndMeetings mode in `TeamsUpgradePolicy`.</span></span>

<span data-ttu-id="fe366-220">たとえば、組織の電話会議の設定に大幅な変更を加えながら、すべての会議を手動で移行するか、または MMS を一時的に無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="fe366-220">For example, you may want to manually migrate all meetings or temporarily disable MMS while making substantial changes to the audio conferencing settings for your organization</span></span>

<span data-ttu-id="fe366-221">組織で MMS が有効になっているかどうかを確認するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="fe366-221">To see if MMS is enabled for your organization, run the following command.</span></span> <span data-ttu-id="fe366-222">パラメーターが`$true`の場合は`MeetingMigrationEnabled` 、MMS が有効になります。</span><span class="sxs-lookup"><span data-stu-id="fe366-222">MMS is enabled if the `MeetingMigrationEnabled` parameter is `$true`.</span></span>
```PowerShell
Get-CsTenantMigrationConfiguration
```
<span data-ttu-id="fe366-223">MMS を有効または無効にするに`Set-CsTenantMigrationConfiguration`は、コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="fe366-223">To enable or disable MMS entirely, use the `Set-CsTenantMigrationConfiguration` command.</span></span> <span data-ttu-id="fe366-224">たとえば、MMS を無効にするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="fe366-224">For example, to disable MMS, run the following command:</span></span>

```PowerShell
Set-CsTenantMigrationConfiguration -MeetingMigrationEnabled $false
```
<span data-ttu-id="fe366-225">組織で MMS が有効になっていて、電話会議の更新プログラムが有効になっているかどうかを`AutomaticallyMigrateUserMeetings`確認する場合は、 `Get-CsOnlineDialInConferencingTenantSettings`[出力元] のパラメーターの値を確認します。</span><span class="sxs-lookup"><span data-stu-id="fe366-225">If MMS is enabled in the organization and you want to check if it is enabled for audio conferencing updates, check the value of the `AutomaticallyMigrateUserMeetings` parameter in the output from `Get-CsOnlineDialInConferencingTenantSettings`.</span></span> <span data-ttu-id="fe366-226">電話会議の MMS を有効または無効に`Set-CsOnlineDialInConferencingTenantSettings`するには、を使用します。</span><span class="sxs-lookup"><span data-stu-id="fe366-226">To enable or disable MMS for audio conferencing, use `Set-CsOnlineDialInConferencingTenantSettings`.</span></span> <span data-ttu-id="fe366-227">たとえば、電話会議の MMS を無効にするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="fe366-227">For example, to disable MMS for audio conferencing, run the following command:</span></span>

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings  -AutomaticallyMigrateUserMeetings $false
```

## <a name="related-topics"></a><span data-ttu-id="fe366-228">関連項目</span><span class="sxs-lookup"><span data-stu-id="fe366-228">Related topics</span></span>

[<span data-ttu-id="fe366-229">Office 365 での電話会議を試用または購入する</span><span class="sxs-lookup"><span data-stu-id="fe366-229">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

[<span data-ttu-id="fe366-230">オンプレミスとクラウドの間でユーザーを移動する</span><span class="sxs-lookup"><span data-stu-id="fe366-230">Move users between on-premises and cloud</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)
