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
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: Meeting Migration Service (MMS) は、バックグラウンドで実行され、ユーザーの会議のSkype for BusinessおよびMicrosoft Teams更新するサービスです。 MMS はユーザーが会議移行ツールを実行して Skype for Business および Microsoft Teams 会議を更新しなくても済むように設計されています。
ms.openlocfilehash: db4889bb30ec453a64bfcf760a1233fbc7c1e2f5
ms.sourcegitcommit: 32e3bb588abcbeded2d885483384c06706b280eb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2021
ms.locfileid: "52282114"
---
# <a name="using-the-meeting-migration-service-mms"></a><span data-ttu-id="c4d94-104">会議移行サービス (MMS) を使用する</span><span class="sxs-lookup"><span data-stu-id="c4d94-104">Using the Meeting Migration Service (MMS)</span></span>

<span data-ttu-id="c4d94-105">Meeting Migration Service (MMS) は、次のシナリオでユーザーの既存の会議を更新するサービスです。</span><span class="sxs-lookup"><span data-stu-id="c4d94-105">The Meeting Migration Service (MMS) is a service that updates a user’s existing meetings in the following scenarios:</span></span>

- <span data-ttu-id="c4d94-106">ユーザーがオンプレミスからクラウドに移行された場合 (オンラインまたは TeamsOnly Skype for Businessに移行する場合)。</span><span class="sxs-lookup"><span data-stu-id="c4d94-106">When a user is migrated from on-premises to the cloud (whether to Skype for Business Online or to TeamsOnly).</span></span>
- <span data-ttu-id="c4d94-107">管理者がユーザーの電話会議設定に変更を行った場合</span><span class="sxs-lookup"><span data-stu-id="c4d94-107">When an admin makes a change to the user’s audio conferencing settings</span></span> 
- <span data-ttu-id="c4d94-108">オンライン ユーザーが Teams にのみアップグレードされている場合、または TeamsUpgradePolicy のユーザー モードが SfBwithTeamsCollabAndMeetings に設定されている場合</span><span class="sxs-lookup"><span data-stu-id="c4d94-108">When an online user is upgraded to Teams only, or when a user's mode in TeamsUpgradePolicy is set to SfBwithTeamsCollabAndMeetings</span></span>
- <span data-ttu-id="c4d94-109">PowerShell を使用する場合</span><span class="sxs-lookup"><span data-stu-id="c4d94-109">When you use PowerShell</span></span> 


<span data-ttu-id="c4d94-110">既定では、これらの各ケースで MMS が自動的にトリガーされます。ただし、管理者はテナント レベルで無効にできます。</span><span class="sxs-lookup"><span data-stu-id="c4d94-110">By default, MMS is automatically triggered in each of these cases, although admins can disable it at the tenant level.</span></span> <span data-ttu-id="c4d94-111">さらに、管理者は PowerShell コマンドレットを使用して、特定のユーザーの会議の移行を手動でトリガーできます。</span><span class="sxs-lookup"><span data-stu-id="c4d94-111">In addition, admins can use a PowerShell cmdlet to manually trigger meeting migration for a given user.</span></span>


<span data-ttu-id="c4d94-112">**制限事項**: 次の条件が適用される場合、会議移行サービスを使用できません。</span><span class="sxs-lookup"><span data-stu-id="c4d94-112">**Limitations**: The meeting migration service can't be used if any of the following apply:</span></span>

- <span data-ttu-id="c4d94-113">ユーザーのメールボックスは、オンプレミスのExchangeホストされます。</span><span class="sxs-lookup"><span data-stu-id="c4d94-113">The user’s mailbox is hosted in Exchange on-premises.</span></span>
- <span data-ttu-id="c4d94-114">ユーザーは、クラウドからオンプレミスにSkype for Business Serverされます。</span><span class="sxs-lookup"><span data-stu-id="c4d94-114">The user is being migrated from the cloud to Skype for Business Server on-premises.</span></span>


## <a name="how-mms-works"></a><span data-ttu-id="c4d94-115">MMS のしくみ</span><span class="sxs-lookup"><span data-stu-id="c4d94-115">How MMS works</span></span>

<span data-ttu-id="c4d94-116">特定のユーザーに対して MMS がトリガーされると、そのユーザーに対する移行要求がキューに配置されます。</span><span class="sxs-lookup"><span data-stu-id="c4d94-116">When MMS is triggered for a given user, a migration request for that user is placed in a queue.</span></span> <span data-ttu-id="c4d94-117">競争状態を回避するために、キューに入っている要求は、少なくとも 90 分が過ぎるまで意図的に処理されません。</span><span class="sxs-lookup"><span data-stu-id="c4d94-117">To avoid any race conditions, the queued request is deliberately not processed until at least 90 minutes have gone by.</span></span> <span data-ttu-id="c4d94-118">MMS は、要求を処理すると、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="c4d94-118">Once MMS processes the request, it performs the following tasks:</span></span>

1. <span data-ttu-id="c4d94-119">そのユーザーのメールボックスを検索し、そのユーザーによって開催され、今後スケジュールされた既存のすべての会議を検索します。</span><span class="sxs-lookup"><span data-stu-id="c4d94-119">It searches that user’s mailbox for all existing meetings organized by that user and scheduled in the future.</span></span>
2. <span data-ttu-id="c4d94-120">ユーザーのメールボックスにある情報に基づいて、正確なシナリオに応じて、そのユーザーの Teams または Skype for Business Online で新しい会議を更新またはスケジュールします。</span><span class="sxs-lookup"><span data-stu-id="c4d94-120">Based on the information found in the user’s mailbox, it either updates or schedules new meetings in either Teams or Skype for Business Online for that user, depending on the exact scenario.</span></span>
3. <span data-ttu-id="c4d94-121">メール メッセージでは、会議の詳細のオンライン会議ブロックが置き換えされます。</span><span class="sxs-lookup"><span data-stu-id="c4d94-121">In the email message, it replaces the online meeting block in the meeting details.</span></span>
4. <span data-ttu-id="c4d94-122">会議の開催者に代わって、その会議の更新されたバージョンがすべての会議の受信者に送信されます。</span><span class="sxs-lookup"><span data-stu-id="c4d94-122">It sends the updated version of that meeting to all meeting recipients on behalf of the meeting organizer.</span></span> <span data-ttu-id="c4d94-123">会議の招待者には、更新された会議の座標を含む会議の更新がメールで送信されます。</span><span class="sxs-lookup"><span data-stu-id="c4d94-123">Meeting invitees will receive a meeting update with updated meeting coordinates in their email.</span></span> 

    ![MMS で更新される会議ブロック。](../images/210a03ee-30c1-46f3-808f-4c2ebdaa3ea1.png)

<span data-ttu-id="c4d94-125">MMS がトリガーされるまで、通常、ユーザーの会議が移行されるまで約 2 時間かかります。</span><span class="sxs-lookup"><span data-stu-id="c4d94-125">From the time MMS is triggered, it typically takes about 2 hours until the user’s meetings are migrated.</span></span> <span data-ttu-id="c4d94-126">ただし、ユーザーの会議の数が多い場合は、時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="c4d94-126">However, if the user has a large number of meetings, it might take longer.</span></span> <span data-ttu-id="c4d94-127">MMS でユーザーの 1 つ以上の会議の移行でエラーが発生した場合、24 時間の間に最大 9 回、定期的に再試行されます。</span><span class="sxs-lookup"><span data-stu-id="c4d94-127">If MMS encounters an error migrating one or more meetings for the user, it will periodically retry up to 9 times over the span of 24 hours.</span></span>

<span data-ttu-id="c4d94-128">**注**:</span><span class="sxs-lookup"><span data-stu-id="c4d94-128">**Notes**:</span></span>

- <span data-ttu-id="c4d94-129">MMS は会議が移行されるときにオンライン会議の情報ブロックのすべてを置き換えます。</span><span class="sxs-lookup"><span data-stu-id="c4d94-129">MMS replaces everything in the online meeting information block when a meeting is migrated.</span></span> <span data-ttu-id="c4d94-130">このため、ユーザーがそのブロックを編集した場合は、それらの変更は上書きされます。</span><span class="sxs-lookup"><span data-stu-id="c4d94-130">Therefore, if a user has edited that block, their changes will be overwritten.</span></span> <span data-ttu-id="c4d94-131">オンライン会議の情報ブロック以外の会議の詳細に含まれているコンテンツは影響しません。</span><span class="sxs-lookup"><span data-stu-id="c4d94-131">Any content they have in the meeting details outside of the online meeting information block won't be affected.</span></span> <span data-ttu-id="c4d94-132">つまり、会議出席招待に添付されているファイルは引き続き含まれます。</span><span class="sxs-lookup"><span data-stu-id="c4d94-132">This means any files attached to the meeting invite will still be included.</span></span> 
- <span data-ttu-id="c4d94-133">Outlook on the Web で [ **Skype 会議の追加**] ボタンをクリックして、または Outlook 用の Skype 会議アドインを使用してスケジュールされた Skype for Business 会議および Microsoft Teams 会議のみが移行されます。</span><span class="sxs-lookup"><span data-stu-id="c4d94-133">Only the Skype for Business or Microsoft Teams meetings that were scheduled by clicking the **Add Skype meeting** button in Outlook on the Web or by using the Skype Meeting add-in for Outlook are migrated.</span></span> <span data-ttu-id="c4d94-134">ユーザーが Skype のオンライン会議情報をコピーして 1 つの会議から新しい会議に貼り付ける場合、元のサービスに会議が存在しなから、その新しい会議は更新されません。</span><span class="sxs-lookup"><span data-stu-id="c4d94-134">If a user copies and pastes the Skype online meeting information from one meeting to a new meeting, that new meeting won't be updated since there is no meeting in the original service.</span></span>
- <span data-ttu-id="c4d94-135">会議に作成または添付された会議コンテンツ (ホワイトボード、投票など) は、MMS の実行後も保持されません。</span><span class="sxs-lookup"><span data-stu-id="c4d94-135">Meeting content that was created or attached to the meeting (whiteboards, polls, and so on) won't be retained after MMS runs.</span></span> <span data-ttu-id="c4d94-136">会議の開催者が事前にコンテンツを会議に添付している場合、そのコンテンツは MMS の動作後に再作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4d94-136">If your meeting organizers have attached content to the meetings in advance, the content will need to be recreated after MMS runs.</span></span>
- <span data-ttu-id="c4d94-137">予定表の項目内、および Skype 会議からの共有の会議ノートへのリンクも上書きされます。</span><span class="sxs-lookup"><span data-stu-id="c4d94-137">The link to the shared meeting notes in the calendar item and also from within the Skype meeting also will be overwritten.</span></span> <span data-ttu-id="c4d94-138">この場所に保存されている実際の会議OneNoteは引き続き存在します。上書きされた共有ノートへのリンクのみです。</span><span class="sxs-lookup"><span data-stu-id="c4d94-138">Note that the actual meeting notes stored in OneNote will still be there; it is only the link to the shared notes that is overwritten.</span></span>
- <span data-ttu-id="c4d94-139">(開催者を含めて) 250 人を超える参加者がいる会議は移行できません。</span><span class="sxs-lookup"><span data-stu-id="c4d94-139">Meetings with more than 250 attendees (including the organizer) won't be migrated.</span></span>
- <span data-ttu-id="c4d94-140">招待の本文の一部の UNICODE 文字が、次のいずれかの特殊文字 (ï、年 1/2、) に誤って更新される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c4d94-140">Some UNICODE characters in the body of the invite might be incorrectly updated to one of the following special characters: ï, ¿, ½, �.</span></span>

## <a name="triggering-mms-for-a-user"></a><span data-ttu-id="c4d94-141">ユーザーの MMS のトリガー</span><span class="sxs-lookup"><span data-stu-id="c4d94-141">Triggering MMS for a user</span></span>

<span data-ttu-id="c4d94-142">このセクションでは、次の各ケースで MMS がトリガーされた場合の動作について説明します。</span><span class="sxs-lookup"><span data-stu-id="c4d94-142">This section describes what happens when MMS is triggered in each of the following cases:</span></span>

- <span data-ttu-id="c4d94-143">ユーザーをオンプレミスからクラウドに移行する場合</span><span class="sxs-lookup"><span data-stu-id="c4d94-143">When a user is migrated from on-premises to the cloud</span></span>
- <span data-ttu-id="c4d94-144">管理者がユーザーの電話会議設定に変更を行った場合</span><span class="sxs-lookup"><span data-stu-id="c4d94-144">When an admin makes a change to the user’s audio conferencing settings</span></span> 
- <span data-ttu-id="c4d94-145">TeamsUpgradePolicy でユーザーのモードが TeamsOnly または SfBWithTeamsCollabAndMeetings に設定されている場合 (Powershell または Teams 管理ポータルを使用)</span><span class="sxs-lookup"><span data-stu-id="c4d94-145">When the user's mode in TeamsUpgradePolicy is set to either TeamsOnly or SfBWithTeamsCollabAndMeetings (using either Powershell or the Teams Admin Portal)</span></span>
- <span data-ttu-id="c4d94-146">PowerShell コマンドレットを使用する場合は、次Start-CsExMeetingMigration</span><span class="sxs-lookup"><span data-stu-id="c4d94-146">When you use the PowerShell cmdlet, Start-CsExMeetingMigration</span></span>

### <a name="updating-meetings-when-you-move-an-on-premises-user-to-the-cloud"></a><span data-ttu-id="c4d94-147">オンプレミス ユーザーをクラウドに移動するときに会議を更新する</span><span class="sxs-lookup"><span data-stu-id="c4d94-147">Updating meetings when you move an on-premises user to the cloud</span></span>

<span data-ttu-id="c4d94-148">これは、MMS がユーザーのスムーズな切り替えの作成に役立つ最も一般的なシナリオです。</span><span class="sxs-lookup"><span data-stu-id="c4d94-148">This is the most common scenario where MMS helps create a smoother transition for your users.</span></span> <span data-ttu-id="c4d94-149">会議の移行がない場合、オンプレミスのユーザーがSkype for Business Serverオンラインに移動すると、既存の会議は機能しなくなりました。</span><span class="sxs-lookup"><span data-stu-id="c4d94-149">Without meeting migration, existing meetings organized by a user in Skype for Business Server on-premises would no longer work once the user is moved online.</span></span> <span data-ttu-id="c4d94-150">そのため、オンプレミスの管理ツール (または管理者コントロール パネル) を使用してユーザーをクラウドに移動すると、既存の会議は次のように自動的にクラウド `Move-CsUser` に移動されます。</span><span class="sxs-lookup"><span data-stu-id="c4d94-150">Therefore, when you use the on-premises admin tools (either `Move-CsUser` or the Admin Control Panel) to move a user to the cloud, existing meetings are automatically moved to the cloud as follows:</span></span>

- <span data-ttu-id="c4d94-151">の切り替えが指定されている場合、会議は直接 Teamsに移行され、ユーザーは `MoveToTeams` `Move-CsUser` TeamsOnly モードになります。</span><span class="sxs-lookup"><span data-stu-id="c4d94-151">If the `MoveToTeams` switch in `Move-CsUser` is specified, meetings are migrated directly to Teams and the user will be in TeamsOnly mode.</span></span> <span data-ttu-id="c4d94-152">このスイッチを使用するには、CU8 以降Skype for Business Server 2015 を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4d94-152">Use of this switch requires Skype for Business Server 2015 with CU8 or later.</span></span> <span data-ttu-id="c4d94-153">これらのユーザーは、引き続きSkype for Businessクライアントまたは会議アプリを使用して、招待される可能性がある任意のSkype for Business会議Skype参加できます。</span><span class="sxs-lookup"><span data-stu-id="c4d94-153">These users can still join any Skype for Business meeting they may be invited to, using either the Skype for Business client or the Skype Meeting App.</span></span>
- <span data-ttu-id="c4d94-154">それ以外の場合、会議は Skype for Businessされます。</span><span class="sxs-lookup"><span data-stu-id="c4d94-154">Otherwise meetings are migrated to Skype for Business Online.</span></span>

<span data-ttu-id="c4d94-155">いずれの場合も、ユーザーがクラウドに移動する前に電話会議ライセンスが割り当てられている場合、会議はダイヤルイン座標で作成されます。</span><span class="sxs-lookup"><span data-stu-id="c4d94-155">In either case, if the user has been assigned an Audio Conferencing license before being moved to the cloud, the meetings will be created with dial-in coordinates.</span></span> <span data-ttu-id="c4d94-156">ユーザーをオンプレミスからクラウドに移動し、そのユーザーが電話会議を使用する場合は、最初に電話会議を割り当てしてからユーザーを移動し、1 つの会議移行だけがトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="c4d94-156">If you move a user from on-premises to the cloud and you intend for that user to use Audio Conferencing, we recommend that you first assign the audio conference before you move the user so that only 1 meeting migration is triggered.</span></span>


### <a name="updating-meetings-when-a-users-audio-conferencing-settings-change"></a><span data-ttu-id="c4d94-157">ユーザーの電話会議の設定が変更されるときの会議の更新</span><span class="sxs-lookup"><span data-stu-id="c4d94-157">Updating meetings when a user's audio conferencing settings change</span></span>

<span data-ttu-id="c4d94-158">次の場合、MMS は、ダイヤルイン座標を追加、削除、または変更Skype for Business会議Microsoft Teams既存の会議と会議を更新します。</span><span class="sxs-lookup"><span data-stu-id="c4d94-158">In the following cases, MMS will update existing Skype for Business and Microsoft Teams meetings to add, remove, or modify dial-in coordinates:</span></span>

- <span data-ttu-id="c4d94-159">Microsoft 電話会議サービス のライセンスをユーザーに割り当てまたは削除した場合、そのユーザーがサードパーティの電話会議プロバイダーに対して有効になっていない場合。</span><span class="sxs-lookup"><span data-stu-id="c4d94-159">When you assign or remove a Microsoft Audio Conferencing service license to a user, and that user is not enabled for a third-party audio conferencing provider.</span></span>
- <span data-ttu-id="c4d94-160">ユーザーに Microsoft 電話会議ライセンスが割り当てられている場合に、ユーザーの電話会議プロバイダーを他のプロバイダーから Microsoft に変更する場合。</span><span class="sxs-lookup"><span data-stu-id="c4d94-160">When you change the audio conferencing provider of a user from any other provider to Microsoft, provided the user is assigned a Microsoft Audio Conferencing license.</span></span> <span data-ttu-id="c4d94-161">詳細については、「電話会議プロバイダーとして [Microsoft を割り当てる」を参照してください](./assign-microsoft-as-the-audio-conferencing-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="c4d94-161">For more information, see [Assign Microsoft as the audio conferencing provider](./assign-microsoft-as-the-audio-conferencing-provider.md).</span></span> <span data-ttu-id="c4d94-162">また、サード パーティの電話会議プロバイダー [ACP] のサポートは、前に発表した 2019 年 4 月 1 日に終了する [予定](../legal-and-regulatory/end-of-integration-with-3rd-party-providers.md)です。</span><span class="sxs-lookup"><span data-stu-id="c4d94-162">Also note that support for third party audio conferencing providers [ACP] is scheduled for end of life on April 1, 2019, as [previously announced](../legal-and-regulatory/end-of-integration-with-3rd-party-providers.md).</span></span>
- <span data-ttu-id="c4d94-163">ユーザーの電話会議を有効または無効にする場合。</span><span class="sxs-lookup"><span data-stu-id="c4d94-163">When you enable or disable audio conferencing for a user.</span></span>
- <span data-ttu-id="c4d94-164">パブリック会議を使用するように構成されたユーザーの会議 ID を変更またはリセットする場合。</span><span class="sxs-lookup"><span data-stu-id="c4d94-164">When you change or reset the conference ID for a user configured to use public meetings.</span></span>
- <span data-ttu-id="c4d94-165">ユーザーを新しい電話会議ブリッジに移行する場合</span><span class="sxs-lookup"><span data-stu-id="c4d94-165">When you move the user to a new audio conferencing bridge.</span></span>
- <span data-ttu-id="c4d94-166">電話会議ブリッジからの電話番号が割り当てられていない場合。</span><span class="sxs-lookup"><span data-stu-id="c4d94-166">When a phone number from a audio conferencing bridge is unassigned.</span></span> <span data-ttu-id="c4d94-167">これは、追加の手順が必要な複雑なシナリオです。</span><span class="sxs-lookup"><span data-stu-id="c4d94-167">This is a complex scenario that requires additional steps.</span></span> <span data-ttu-id="c4d94-168">詳細については、「電話会議ブリッジ [で電話番号を変更する」を参照してください](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge)。</span><span class="sxs-lookup"><span data-stu-id="c4d94-168">For more information, see [Change the phone numbers on your audio conferencing bridge](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).</span></span>

<span data-ttu-id="c4d94-p115">ユーザーの電話会議の設定に対する変更の一部は、MMS をトリガーしません。特に、次の 2 つの変更では、MMS によって会議が更新されません。</span><span class="sxs-lookup"><span data-stu-id="c4d94-p115">Not all changes to a user's audio conferencing settings trigger MMS. Specifically, the following two changes won't result in MMS updating meetings:</span></span>

- <span data-ttu-id="c4d94-171">会議の開催者の SIP アドレスを変更する場合 (SIP ユーザー名または SIP ドメインのいずれか)</span><span class="sxs-lookup"><span data-stu-id="c4d94-171">When you change the SIP address for the meeting organizer (either their SIP user name or their SIP domain)</span></span>
- <span data-ttu-id="c4d94-172">コマンドを使用して組織の会議 URL を変更 `Update-CsTenantMeetingUrl` する場合。</span><span class="sxs-lookup"><span data-stu-id="c4d94-172">When you change your organization's meeting URL using the `Update-CsTenantMeetingUrl` command.</span></span>


### <a name="updating-meetings-when-assigning-teamsupgradepolicy"></a><span data-ttu-id="c4d94-173">TeamsUpgradePolicy を割り当てるときに会議を更新する</span><span class="sxs-lookup"><span data-stu-id="c4d94-173">Updating meetings when assigning TeamsUpgradePolicy</span></span>

<span data-ttu-id="c4d94-174">既定では、 または のインスタンスがユーザーに付与されると、会議の移行が自動的に `TeamsUpgradePolicy` `mode=TeamsOnly` トリガーされます `mode= SfBWithTeamsCollabAndMeetings` 。</span><span class="sxs-lookup"><span data-stu-id="c4d94-174">By default, meeting migration is automatically triggered when a user is granted an instance of `TeamsUpgradePolicy` with `mode=TeamsOnly` or `mode= SfBWithTeamsCollabAndMeetings`.</span></span> <span data-ttu-id="c4d94-175">これらのモードのいずれかを許可するときに会議を移行しない場合は、 をで指定するか (PowerShell を使用している場合)、ユーザーの共存モードを設定するときに (Teams 管理ポータルを使用している場合) 会議を移行するボックスをオフにします `MigrateMeetingsToTeams $false` `Grant-CsTeamsUpgradePolicy` 。</span><span class="sxs-lookup"><span data-stu-id="c4d94-175">If you do not want to migrate meetings when granting either of these modes, then specify `MigrateMeetingsToTeams $false` in `Grant-CsTeamsUpgradePolicy` (if using PowerShell) or uncheck the box to migrate meetings when setting a user's coexistence mode (if using the Teams admin portal).</span></span>

<span data-ttu-id="c4d94-176">また、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="c4d94-176">Also note the following:</span></span>

- <span data-ttu-id="c4d94-177">会議の移行は、特定のユーザーに許可する `TeamsUpgradePolicy` 場合にのみ呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="c4d94-177">Meeting migration is only invoked when you grant `TeamsUpgradePolicy` for a specific user.</span></span> <span data-ttu-id="c4d94-178">または をテナント `TeamsUpgradePolicy` 全体 `mode=TeamsOnly` に付与した場合 `mode=SfBWithTeamsCollabAndMeetings` *、* 会議の移行は呼び出されません。</span><span class="sxs-lookup"><span data-stu-id="c4d94-178">If you grant `TeamsUpgradePolicy` with `mode=TeamsOnly` or `mode=SfBWithTeamsCollabAndMeetings` on a *tenant-wide* basis, meeting migration is not invoked.</span></span>
- <span data-ttu-id="c4d94-179">ユーザーに TeamsOnly モードを付与できるのは、ユーザーがオンラインでホームに設定されている場合のみです。</span><span class="sxs-lookup"><span data-stu-id="c4d94-179">A user can only be granted TeamsOnly mode if the user is homed online.</span></span> <span data-ttu-id="c4d94-180">オンプレミスにホームされているユーザーは、前に説明したように を使用 `Move-CsUser` して移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4d94-180">Users that are homed on-premises must be moved using `Move-CsUser` as previously described.</span></span>
- <span data-ttu-id="c4d94-181">TeamsOnly または SfBWithTeamsCollabAndMeetings 以外のモードを付与しても、既存の会議はTeams会議Skype for Businessされません。</span><span class="sxs-lookup"><span data-stu-id="c4d94-181">Granting a mode other than TeamsOnly or SfBWithTeamsCollabAndMeetings does not convert existing Teams meetings to Skype for Business meetings.</span></span>

### <a name="trigger-meeting-migration-manually-via-powershell-cmdlet"></a><span data-ttu-id="c4d94-182">PowerShell コマンドレットを使用して手動で会議移行をトリガーする</span><span class="sxs-lookup"><span data-stu-id="c4d94-182">Trigger Meeting Migration manually via PowerShell cmdlet</span></span>

<span data-ttu-id="c4d94-183">管理者は、自動会議の移行に加えて、 コマンドレット を実行して、ユーザーの会議の移行を手動でトリガーできます `Start-CsExMeetingMigration` 。</span><span class="sxs-lookup"><span data-stu-id="c4d94-183">In addition to automatic meeting migrations, admins can manually trigger meeting migration for a user by running the cmdlet `Start-CsExMeetingMigration`.</span></span> <span data-ttu-id="c4d94-184">このコマンドレットは、指定されたユーザーの移行要求をキューに入れられます。</span><span class="sxs-lookup"><span data-stu-id="c4d94-184">This cmdlet queues a migration request for the specified user.</span></span>  <span data-ttu-id="c4d94-185">必須パラメーターに加えて、2 つの省略可能なパラメーター と を使用して、会議を移行 `Identity` `SourceMeetingType` `TargetMeetingType` する方法を指定できます。</span><span class="sxs-lookup"><span data-stu-id="c4d94-185">In addition to the required `Identity` parameter, it takes two optional parameters, `SourceMeetingType` and `TargetMeetingType`, which allow you to specify how to migrate meetings:</span></span>

<span data-ttu-id="c4d94-186">**TargetMeetingType:**</span><span class="sxs-lookup"><span data-stu-id="c4d94-186">**TargetMeetingType:**</span></span>

- <span data-ttu-id="c4d94-187">を `TargetMeetingType Current` 使用すると、会議Skype for Business会議Skype for Business残り、Teams会議Teamsされます。</span><span class="sxs-lookup"><span data-stu-id="c4d94-187">Using `TargetMeetingType Current` specifies that Skype for Business meetings remain Skype for Business meetings and Teams meetings remain Teams meetings.</span></span> <span data-ttu-id="c4d94-188">ただし、電話会議の調整が変更される可能性があります。また、オンプレミスの会議Skype for Businessは、Skype for Business Online に移行されます。</span><span class="sxs-lookup"><span data-stu-id="c4d94-188">However audio conferencing coordinates might be changed, and any on-premises Skype for Business meetings would be migrated to Skype for Business Online.</span></span> <span data-ttu-id="c4d94-189">これは TargetMeetingType の既定値です。</span><span class="sxs-lookup"><span data-stu-id="c4d94-189">This is the default value for TargetMeetingType.</span></span>
- <span data-ttu-id="c4d94-190">を使用すると、会議がオンラインまたはオンプレミスの Skype for Business でホストされているかどうか、および電話会議の更新が必要かどうかに関係なく、既存の会議を Teams に移行する必要があります `TargetMeetingType Teams` 。</span><span class="sxs-lookup"><span data-stu-id="c4d94-190">Using `TargetMeetingType Teams` specifies that any existing meeting must be migrated to Teams, regardless of whether the meeting is hosted in Skype for Business online or on-premises, and regardless of whether any audio conferencing updates are required.</span></span> 

<span data-ttu-id="c4d94-191">**SourceMeetingType:**</span><span class="sxs-lookup"><span data-stu-id="c4d94-191">**SourceMeetingType:**</span></span>
- <span data-ttu-id="c4d94-192">を `SourceMeetingType SfB` 使用すると、(オンプレミスSkype for Businessオンラインの) 会議のみを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4d94-192">Using `SourceMeetingType SfB` indicates that only Skype for Business meetings (whether on-premises or online) should be updated.</span></span>
- <span data-ttu-id="c4d94-193">を `SourceMeetingType Teams` 使用すると、会議Teams更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4d94-193">Using `SourceMeetingType Teams` indicates that only Teams meetings should be updated.</span></span>
- <span data-ttu-id="c4d94-194">を `SourceMeetingType All` 使用すると、会議Skype for BusinessとTeams両方を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4d94-194">Using `SourceMeetingType All` indicates that both Skype for Business meetings and Teams meetings should be updated.</span></span> <span data-ttu-id="c4d94-195">これは SourceMeetingType の既定値です。</span><span class="sxs-lookup"><span data-stu-id="c4d94-195">This is the default value for SourceMeetingType.</span></span>
    

<span data-ttu-id="c4d94-196">次の例は、すべての会議がユーザーアカウントに移行 ashaw@contoso.com 会議の移行を開始する方法を示Teams。</span><span class="sxs-lookup"><span data-stu-id="c4d94-196">The example below shows how to initiate meeting migration for user ashaw@contoso.com so that all meetings are migrated to Teams:</span></span>

```PowerShell
Start-CsExMeetingMigration -Identity ashaw@contoso.com -TargetMeetingType Teams
```



## <a name="managing-mms"></a><span data-ttu-id="c4d94-197">MMS の管理</span><span class="sxs-lookup"><span data-stu-id="c4d94-197">Managing MMS</span></span>

<span data-ttu-id="c4d94-198">このWindows PowerShell、進行中の移行の状態を確認し、会議の移行を手動でトリガーし、移行を完全に無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="c4d94-198">Using Windows PowerShell, you can check the status of ongoing migrations, manually trigger meeting migration, and disable migration altogether.</span></span> 

### <a name="check-the-status-of-meeting-migrations"></a><span data-ttu-id="c4d94-199">会議の移行の状態を確認する</span><span class="sxs-lookup"><span data-stu-id="c4d94-199">Check the status of meeting migrations</span></span>

<span data-ttu-id="c4d94-200">コマンドレットを使用 `Get-CsMeetingMigrationStatus` して、会議の移行の状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="c4d94-200">You use the `Get-CsMeetingMigrationStatus` cmdlet to check the status of meeting migrations.</span></span> <span data-ttu-id="c4d94-201">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="c4d94-201">Below are some examples.</span></span>

- <span data-ttu-id="c4d94-202">すべての MMS 移行の概要状態を取得するには、次のコマンドを実行して、すべての移行状態を表形式で表示します。</span><span class="sxs-lookup"><span data-stu-id="c4d94-202">To get a summary status of all MMS migrations, run the following command which provides a tabular view of all migration states:</span></span>

    ```PowerShell
    Get-CsMeetingMigrationStatus -SummaryOnly

    State      UserCount
    ------     ---------
    Pending      21
    InProgress    6
    Failed            2 
    Succeeded   131
    ```
- <span data-ttu-id="c4d94-203">特定の期間のすべての移行の詳細を取得するには、 パラメーターと パラメーター `StartTime` を使用 `EndTime` します。</span><span class="sxs-lookup"><span data-stu-id="c4d94-203">To get full details of all migrations within a specific time period, use the `StartTime` and `EndTime` parameters.</span></span> <span data-ttu-id="c4d94-204">たとえば、次のコマンドは、2018 年 10 月 1 日から 2018 年 10 月 8 日まで発生した移行の詳細を返します。</span><span class="sxs-lookup"><span data-stu-id="c4d94-204">For example, the following command will return full details on all migrations that occurred from October 1, 2018 to October 8, 2018.</span></span>

    ```PowerShell
    Get-CsMeetingMigrationStatus -StartTime "10/1/2018" -EndTime "10/8/2018"
    ```
- <span data-ttu-id="c4d94-205">特定のユーザーの移行の状態を確認するには、 パラメーターを使用 `Identity` します。</span><span class="sxs-lookup"><span data-stu-id="c4d94-205">To check the status of migration for a specific user, use the `Identity` parameter.</span></span> <span data-ttu-id="c4d94-206">たとえば、次のコマンドは、ユーザー アカウントの状態を返 ashaw@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="c4d94-206">For example, the following command will return the status for the user ashaw@contoso.com:</span></span>

    ```PowerShell
    Get-CsMeetingMigrationStatus -Identity ashaw@contoso.com
    ```
<span data-ttu-id="c4d94-207">移行に失敗した場合は、ユーザーが解決するまでそれらのユーザーが開催した会議にダイヤルインできないので、これらの問題をできるだけ早く解決するアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="c4d94-207">If you see any migrations that have failed, take action to resolve these issues as soon as possible, since people won't be able to dial-in to the meetings organized by those users until you resolve them.</span></span> <span data-ttu-id="c4d94-208">失敗 `Get-CsMeetingMigrationStatus` した状態の移行が表示された場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c4d94-208">If `Get-CsMeetingMigrationStatus` shows any migrations in a failed state, perform these steps:</span></span>
 
1. <span data-ttu-id="c4d94-p126">影響を受けているユーザーを特定します。次のコマンドを実行して、影響を受けているユーザーと、報告された特定のエラーのリストを取得します。</span><span class="sxs-lookup"><span data-stu-id="c4d94-p126">Determine which users are affected. Run the following command to get the list of affected users, and the specific error that was reported:</span></span>

    ```PowerShell
    Get-CsMeetingMigrationStatus| Where {$_.State -eq "Failed"}| Format-Table UserPrincipalName, LastMessage
    ```
2. <span data-ttu-id="c4d94-211">影響を受ける各ユーザーについて、会議移行ツールを実行して、手動で会議を移行します。</span><span class="sxs-lookup"><span data-stu-id="c4d94-211">For each affected user, run the Meeting Migration Tool to manually migrate their meetings.</span></span>

3. <span data-ttu-id="c4d94-212">会議移行ツールを使用しても移行が機能しない場合には、次の 2 つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="c4d94-212">If migration still doesn't work with the Meeting Migration Tool, you have two options:</span></span>

    - <span data-ttu-id="c4d94-213">ユーザーに新しい Skype 会議を作成してもらいます。</span><span class="sxs-lookup"><span data-stu-id="c4d94-213">Have the users create new Skype meetings.</span></span>
    - <span data-ttu-id="c4d94-214">[サポートに問い合わせます](/microsoft-365/Admin/contact-support-for-business-products)。</span><span class="sxs-lookup"><span data-stu-id="c4d94-214">[Contact support](/microsoft-365/Admin/contact-support-for-business-products).</span></span>


### <a name="enabling-and-disabling-mms"></a><span data-ttu-id="c4d94-215">MMS の有効化と無効化</span><span class="sxs-lookup"><span data-stu-id="c4d94-215">Enabling and disabling MMS</span></span>

<span data-ttu-id="c4d94-216">MMS は、すべての組織で既定で有効になっていますが、次のように無効にできます。</span><span class="sxs-lookup"><span data-stu-id="c4d94-216">MMS is enabled by default for all organizations, but it can be disabled as follows:</span></span>

- <span data-ttu-id="c4d94-217">テナントに対して完全に無効にします。</span><span class="sxs-lookup"><span data-stu-id="c4d94-217">Disable entirely for the tenant.</span></span> 
- <span data-ttu-id="c4d94-218">電話会議に関連する変更の場合にのみ無効にします。</span><span class="sxs-lookup"><span data-stu-id="c4d94-218">Disable only for changes related to audio conferencing.</span></span> <span data-ttu-id="c4d94-219">この場合、MMS は、ユーザーがオンプレミスからクラウドに移行された場合、または TeamsOnly モードまたは SfBWithTeamsCollabAndMeetings モードを で許可するときに実行されます `TeamsUpgradePolicy` 。</span><span class="sxs-lookup"><span data-stu-id="c4d94-219">In this case, MMS will still run when a user is migrated from on-premises to the cloud or when you grant TeamsOnly mode or SfBWithTeamsCollabAndMeetings mode in `TeamsUpgradePolicy`.</span></span>

<span data-ttu-id="c4d94-220">たとえば、組織の電話会議設定を大幅に変更しながら、すべての会議を手動で移行したり、MMS を一時的に無効にしたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="c4d94-220">For example, you may want to manually migrate all meetings or temporarily disable MMS while making substantial changes to the audio conferencing settings for your organization</span></span>

<span data-ttu-id="c4d94-221">組織で MMS が有効になっているか確認するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c4d94-221">To see if MMS is enabled for your organization, run the following command.</span></span> <span data-ttu-id="c4d94-222">MMS は、 パラメーターが の `MeetingMigrationEnabled` 場合に有効になります `$true` 。</span><span class="sxs-lookup"><span data-stu-id="c4d94-222">MMS is enabled if the `MeetingMigrationEnabled` parameter is `$true`.</span></span>
```PowerShell
Get-CsTenantMigrationConfiguration
```
<span data-ttu-id="c4d94-223">MMS を完全に有効または無効にするには、 コマンドを使用 `Set-CsTenantMigrationConfiguration` します。</span><span class="sxs-lookup"><span data-stu-id="c4d94-223">To enable or disable MMS entirely, use the `Set-CsTenantMigrationConfiguration` command.</span></span> <span data-ttu-id="c4d94-224">たとえば、MMS を無効にするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c4d94-224">For example, to disable MMS, run the following command:</span></span>

```PowerShell
Set-CsTenantMigrationConfiguration -MeetingMigrationEnabled $false
```
<span data-ttu-id="c4d94-225">組織で MMS が有効で、電話会議の更新が有効になっている場合は、 からの出力で パラメーターの値 `AutomaticallyMigrateUserMeetings` を確認します `Get-CsOnlineDialInConferencingTenantSettings` 。</span><span class="sxs-lookup"><span data-stu-id="c4d94-225">If MMS is enabled in the organization and you want to check if it is enabled for audio conferencing updates, check the value of the `AutomaticallyMigrateUserMeetings` parameter in the output from `Get-CsOnlineDialInConferencingTenantSettings`.</span></span> <span data-ttu-id="c4d94-226">電話会議で MMS を有効または無効にするには、 を使用します `Set-CsOnlineDialInConferencingTenantSettings` 。</span><span class="sxs-lookup"><span data-stu-id="c4d94-226">To enable or disable MMS for audio conferencing, use `Set-CsOnlineDialInConferencingTenantSettings`.</span></span> <span data-ttu-id="c4d94-227">たとえば、電話会議で MMS を無効にするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c4d94-227">For example, to disable MMS for audio conferencing, run the following command:</span></span>

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings  -AutomaticallyMigrateUserMeetings $false
```

## <a name="related-topics"></a><span data-ttu-id="c4d94-228">関連トピック</span><span class="sxs-lookup"><span data-stu-id="c4d94-228">Related topics</span></span>

[<span data-ttu-id="c4d94-229">電話会議を試用または購入するには、Microsoft 365またはOffice 365</span><span class="sxs-lookup"><span data-stu-id="c4d94-229">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

[<span data-ttu-id="c4d94-230">オンプレミスとクラウドの間でユーザーを移動する</span><span class="sxs-lookup"><span data-stu-id="c4d94-230">Move users between on-premises and cloud</span></span>](../../SfbHybrid/hybrid/move-users-between-on-premises-and-cloud.md)
