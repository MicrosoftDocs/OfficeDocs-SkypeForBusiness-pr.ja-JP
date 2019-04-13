---
title: 会議の移行サービス (MMS) を使用してください。
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
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 会議の移行サービス (MMS) は、バック グラウンドで実行され、ユーザーのビジネスおよびマイクロソフトのチームの会議に Skype が自動的に更新するサービスです。 MMS is designed to eliminate the need for users to run the Meeting Migration Tool to update their Skype for Business and Microsoft Teams meetings.
ms.openlocfilehash: 90953f1352f54a8411513a78ccfda8bfb5356883
ms.sourcegitcommit: 004d9475aa704779f8f70adeaf2db9b36c6828cc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/12/2019
ms.locfileid: "31836858"
---
# <a name="using-the-meeting-migration-service-mms"></a><span data-ttu-id="404a1-104">会議の移行サービス (MMS) を使用してください。</span><span class="sxs-lookup"><span data-stu-id="404a1-104">Using the Meeting Migration Service (MMS)</span></span>

<span data-ttu-id="404a1-105">会議の移行サービス (MMS) は、次のシナリオで、ユーザーの既存の会議を更新するサービスです。</span><span class="sxs-lookup"><span data-stu-id="404a1-105">The Meeting Migration Service (MMS) is service that updates a user’s existing meetings in the following scenarios:</span></span>

- <span data-ttu-id="404a1-106">ユーザーを移行するとき、オンプレミス (Skype のビジネスをオンラインにするか TeamsOnly) クラウドに移行します。</span><span class="sxs-lookup"><span data-stu-id="404a1-106">When a user is migrated from on-premises to the cloud (whether to Skype for Business Online or to TeamsOnly).</span></span>
- <span data-ttu-id="404a1-107">管理者がユーザーの電話会議の設定に変更を行う場合</span><span class="sxs-lookup"><span data-stu-id="404a1-107">When an admin makes a change to the user’s audio conferencing settings</span></span> 
- <span data-ttu-id="404a1-108">チームのみ、または TeamsUpgradePolicy で、ユーザーのモードは SfBwithTeamsCollabAndMeetings (タップのお客様のみ) に設定されている場合に、オンラインのユーザーをアップグレードするとき</span><span class="sxs-lookup"><span data-stu-id="404a1-108">When an online user is upgraded to Teams only, or when a user's mode in TeamsUpgradePolicy is set to SfBwithTeamsCollabAndMeetings (TAP customers only)</span></span>
- <span data-ttu-id="404a1-109">PowerShell を使用する場合</span><span class="sxs-lookup"><span data-stu-id="404a1-109">When you use PowerShell</span></span> 


<span data-ttu-id="404a1-110">既定では、MMS 自動的にトリガーのような場合、管理者が無効にする、テナントのレベルがされます。</span><span class="sxs-lookup"><span data-stu-id="404a1-110">By default, MMS is automatically triggered in each of these cases, although admins can disable it at the tenant level.</span></span> <span data-ttu-id="404a1-111">さらに、管理者は、手動で特定のユーザーの会議の移行を開始するのに PowerShell コマンドレットを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="404a1-111">In addition, admins can use a PowerShell cmdlet to manually trigger meeting migration for a given user.</span></span>

> [!NOTE]
> <span data-ttu-id="404a1-112">チームの会議に会議の Skype を変換する機能と電話会議の設定を変更するのには既存のチーム ミーティングを更新する機能は、タップのお客様のみに制限されて。</span><span class="sxs-lookup"><span data-stu-id="404a1-112">The ability to convert Skype for Business meetings to Teams meetings and the ability to update existing Teams meetings to modify audio-conferencing settings is currently limited to TAP customers only.</span></span> <span data-ttu-id="404a1-113">マイクロソフトでは、月 2019年のいずれかの時点にこの機能をすべてのお客様に利用できるようにするのには期待しています。</span><span class="sxs-lookup"><span data-stu-id="404a1-113">Microsoft expects to make this functionality available to all customers sometime in May 2019.</span></span>

<span data-ttu-id="404a1-114">**制限**: 会議次のいずれかの場合、移行サービスを使用できません。</span><span class="sxs-lookup"><span data-stu-id="404a1-114">**Limitations**: The meeting migration service can't be used if any of the following apply:</span></span>

- <span data-ttu-id="404a1-115">ユーザーのメールボックスは、Exchange、オンプレミスでホストされています。</span><span class="sxs-lookup"><span data-stu-id="404a1-115">The user’s mailbox is hosted in Exchange on-premises.</span></span>
- <span data-ttu-id="404a1-116">ユーザー クラウドからに移行 Skype ビジネス サーバー設置型です。</span><span class="sxs-lookup"><span data-stu-id="404a1-116">The user is being migrated from the cloud to Skype for Business Server on-premises.</span></span>

<span data-ttu-id="404a1-117">このような場合は、エンド ・ ユーザーは、独自の会議を移行するのには[会議の移行ツール](https://www.microsoft.com/en-us/download/details.aspx?id=51659)を使用できます代わりにします。</span><span class="sxs-lookup"><span data-stu-id="404a1-117">In these situations, end users can use the [Meeting Migration Tool](https://www.microsoft.com/en-us/download/details.aspx?id=51659) to migrate their own meetings instead.</span></span>

## <a name="how-mms-works"></a><span data-ttu-id="404a1-118">MMS のしくみ</span><span class="sxs-lookup"><span data-stu-id="404a1-118">How MMS works</span></span>

<span data-ttu-id="404a1-119">MMS がユーザーごとにトリガーされると、そのユーザーの移行要求はキューに配置されます。</span><span class="sxs-lookup"><span data-stu-id="404a1-119">When MMS is triggered for a given user, a migration request for that user is placed in a queue.</span></span> <span data-ttu-id="404a1-120">任意の競合状態を避けるためには、90 分以上が経過するまでは意図的に、キューに入れられた要求が処理されます。</span><span class="sxs-lookup"><span data-stu-id="404a1-120">To avoid any race conditions, the queued request is deliberately not processed until at least 90 minutes have gone by.</span></span> <span data-ttu-id="404a1-121">MMS では、要求を処理すると、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="404a1-121">Once MMS processes the request, it performs the following tasks:</span></span>

1. <span data-ttu-id="404a1-122">ユーザーごとに編成され、今後予定されているすべての既存の会議のユーザーのメールボックスを検索します。</span><span class="sxs-lookup"><span data-stu-id="404a1-122">It searches that user’s mailbox for all existing meetings organized by that user and scheduled in the future.</span></span>
2. <span data-ttu-id="404a1-123">ユーザーのメールボックス内の情報に基づき、いずれかを更新または実際の状況によって、そのユーザーのオンライン ビジネスのチームまたは Skype のいずれかで新しい会議をスケジュールします。</span><span class="sxs-lookup"><span data-stu-id="404a1-123">Based on the information found in the user’s mailbox, it either updates or schedules new meetings in either Teams or Skype for Business Online for that user, depending on the exact scenario.</span></span>
3. <span data-ttu-id="404a1-124">電子メール メッセージでは、[ミーティングの詳細、オンライン会議のブロックに置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="404a1-124">In the email message, it replaces the online meeting block in the meeting details.</span></span>
4. <span data-ttu-id="404a1-125">その会議の更新されたバージョンを会議の開催者の代理として会議のすべての受信者に送信します。</span><span class="sxs-lookup"><span data-stu-id="404a1-125">It sends the updated version of that meeting to all meeting recipients on behalf of the meeting organizer.</span></span> <span data-ttu-id="404a1-126">会議出席者に電子メールで更新された会議出席の座標を使用して会議の更新が表示されます。</span><span class="sxs-lookup"><span data-stu-id="404a1-126">Meeting invitees will receive a meeting update with updated meeting coordinates in their email.</span></span> 

    ![MMS で更新される会議ブロック。](../images/210a03ee-30c1-46f3-808f-4c2ebdaa3ea1.png)

<span data-ttu-id="404a1-128">MMS がトリガーされた場合、通常かかるユーザーの会議は、移行するまで、約 2 時間です。</span><span class="sxs-lookup"><span data-stu-id="404a1-128">From the time MMS is triggered, it typically takes about 2 hours until the user’s meetings are migrated.</span></span> <span data-ttu-id="404a1-129">ただし、ユーザーが会議の数が多い場合、長くかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="404a1-129">However, if the user has a large number of meetings, it might take longer.</span></span> <span data-ttu-id="404a1-130">MMS では、ユーザーの会議を 1 つまたは複数の移行エラーが発生すると、それによって定期的に再試行最大 9 倍 24 時間の範囲で。</span><span class="sxs-lookup"><span data-stu-id="404a1-130">If MMS encounters an error migrating one or more meetings for the user, it will periodically retry up to 9 times over the span of 24 hours.</span></span>

<span data-ttu-id="404a1-131">**メモ**:</span><span class="sxs-lookup"><span data-stu-id="404a1-131">**Notes**:</span></span>

- <span data-ttu-id="404a1-p107">MMS は会議が移行されるときにオンライン会議の情報ブロックのすべてを置き換えます。このため、ユーザーがそのブロックを編集した場合は、それらの変更は上書きされます。オンライン会議の情報ブロック以外の会議の詳細に含まれているコンテンツは影響しません。</span><span class="sxs-lookup"><span data-stu-id="404a1-p107">MMS replaces everything in the online meeting information block when a meeting is migrated. Therefore, if a user has edited that block, their changes will be overwritten. Any content they have in the meeting details outside of the online meeting information block won't be affected.</span></span>
- <span data-ttu-id="404a1-135">Outlook on the Web で [ **Skype 会議の追加**] ボタンをクリックして、または Outlook 用の Skype 会議アドインを使用してスケジュールされた Skype for Business 会議および Microsoft Teams 会議のみが移行されます。</span><span class="sxs-lookup"><span data-stu-id="404a1-135">Only the Skype for Business or Microsoft Teams meetings that were scheduled by clicking the **Add Skype meeting** button in Outlook on the Web or by using the Skype Meeting add-in for Outlook are migrated.</span></span> <span data-ttu-id="404a1-136">ユーザーは、コピーし、新しい会議を 1 つの会議から Skype のオンライン会議の情報を貼り付けます、会議サービスではないのでその他の会議は更新されません。</span><span class="sxs-lookup"><span data-stu-id="404a1-136">If a user copies and pastes the Skype online meeting information from one meeting to a new meeting, that new meeting won't be updated since there is no meeting in the original service.</span></span>
- <span data-ttu-id="404a1-137">MMS を実行した後、会議の作成または会議 (ホワイト ボードや投票など) に接続されているコンテンツは保持されません。</span><span class="sxs-lookup"><span data-stu-id="404a1-137">Meeting content that was created or attached to the meeting (whiteboards, polls, and so on) won't be retained after MMS runs.</span></span> <span data-ttu-id="404a1-138">会議の開催者が事前にコンテンツを会議に添付している場合、そのコンテンツは MMS の動作後に再作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="404a1-138">If your meeting organizers have attached content to the meetings in advance, the content will need to be recreated after MMS runs.</span></span>
- <span data-ttu-id="404a1-139">予定表の項目内、および Skype 会議からの共有の会議ノートへのリンクも上書きされます。</span><span class="sxs-lookup"><span data-stu-id="404a1-139">The link to the shared meeting notes in the calendar item and also from within the Skype meeting also will be overwritten.</span></span> <span data-ttu-id="404a1-140">OneNote に保存されている実際の会議の記録があることに注意があります。上書きされる共有のノートにリンクだけすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="404a1-140">Note that the actual meeting notes stored in OneNote will still be there; it is only the link to the shared notes that is overwritten.</span></span>
- <span data-ttu-id="404a1-141">(開催者を含めて) 250 人を超える参加者がいる会議は移行できません。</span><span class="sxs-lookup"><span data-stu-id="404a1-141">Meetings with more than 250 attendees (including the organizer) won't be migrated.</span></span>
- <span data-ttu-id="404a1-142">招待状の本文にいくつかの UNICODE 文字がありますが正しく更新されません次の特殊文字のいずれかに: ï、¿、½、します。</span><span class="sxs-lookup"><span data-stu-id="404a1-142">Some UNICODE characters in the body of the invite might be incorrectly updated to one of the following special characters: ï, ¿, ½, �.</span></span>

## <a name="triggering-mms-for-a-user"></a><span data-ttu-id="404a1-143">ユーザーが MMS をトリガーします。</span><span class="sxs-lookup"><span data-stu-id="404a1-143">Triggering MMS for a user</span></span>

<span data-ttu-id="404a1-144">このセクションでは、次の場合のそれぞれで MMS がトリガーされたときの動作について説明します。</span><span class="sxs-lookup"><span data-stu-id="404a1-144">This section describes what happens when MMS is triggered in each of the following cases:</span></span>

- <span data-ttu-id="404a1-145">クラウドへの設置からユーザーが移行されるとき</span><span class="sxs-lookup"><span data-stu-id="404a1-145">When a user is migrated from on-premises to the cloud</span></span>
- <span data-ttu-id="404a1-146">管理者がユーザーの電話会議の設定に変更を行う場合</span><span class="sxs-lookup"><span data-stu-id="404a1-146">When an admin makes a change to the user’s audio conferencing settings</span></span> 
- <span data-ttu-id="404a1-147">TeamsUpgradePolicy でユーザーのモードが TeamsOnly または SfBWithTeamsCollabAndMeetings (タップのお客様のみ) のいずれかに設定されている場合</span><span class="sxs-lookup"><span data-stu-id="404a1-147">When the user's mode in TeamsUpgradePolicy is set to either TeamsOnly or SfBWithTeamsCollabAndMeetings (TAP customers only)</span></span>
- <span data-ttu-id="404a1-148">PowerShell を使用する場合</span><span class="sxs-lookup"><span data-stu-id="404a1-148">When you use PowerShell</span></span> 

### <a name="updating-meetings-when-you-move-an-on-premises-user-to-the-cloud"></a><span data-ttu-id="404a1-149">オンプレミスのユーザーをクラウドに移行するときに、会議を更新</span><span class="sxs-lookup"><span data-stu-id="404a1-149">Updating meetings when you move an on-premises user to the cloud</span></span>

<span data-ttu-id="404a1-150">これは、MMS により、ユーザーのスムーズなトランジションを作成する最も一般的なシナリオです。</span><span class="sxs-lookup"><span data-stu-id="404a1-150">This is the most common scenario where MMS helps create a smoother transition for your users.</span></span> <span data-ttu-id="404a1-151">会議の移行せずユーザーがオンラインに移動すると Skype のビジネス サーバー設置型のユーザーが既存のミーティングは動作しなく。</span><span class="sxs-lookup"><span data-stu-id="404a1-151">Without meeting migration, existing meetings organized by a user in Skype for Business Server on-premises would no longer work once the user is moved online.</span></span> <span data-ttu-id="404a1-152">したがって、設置型の管理ツールを使用する (か、`Move-CsUser`またはコントロール パネルの [管理者) ユーザーをクラウドに移動するに既存の会議は自動的に移動、クラウドに次のように。</span><span class="sxs-lookup"><span data-stu-id="404a1-152">Therefore, when you use the on-premises admin tools (either `Move-CsUser` or the Admin Control Panel) to move a user to the cloud, existing meetings are automatically moved to the cloud as follows:</span></span>

- <span data-ttu-id="404a1-153">場合、`MoveToTeams`でスイッチを`Move-CsUser`が指定されている会議は、チームに直接移行できます。</span><span class="sxs-lookup"><span data-stu-id="404a1-153">If the `MoveToTeams` switch in `Move-CsUser` is specified, meetings are migrated directly to Teams.</span></span> <span data-ttu-id="404a1-154">このスイッチを使用するには、CU8 を持つサーバーをビジネスの Skype が必要です。</span><span class="sxs-lookup"><span data-stu-id="404a1-154">Use of this switch requires Skype for Business Server with CU8 or later.</span></span>
- <span data-ttu-id="404a1-155">それ以外の場合の会議は、ビジネス オンラインの Skype に移行されます。</span><span class="sxs-lookup"><span data-stu-id="404a1-155">Otherwise meetings are migrated to Skype for Business Online.</span></span>

<span data-ttu-id="404a1-156">どちらの場合も、[ユーザー割り当てられている場合、オーディオ会議のライセンスをクラウドに移動する前に、会議は、ダイヤルインの座標を使用して作成されます。</span><span class="sxs-lookup"><span data-stu-id="404a1-156">In either case, if the user has been assigned an Audio Conferencing license before being moved to the cloud, the meetings will be created with dial-in coordinates.</span></span> <span data-ttu-id="404a1-157">オンプレミスからクラウドに移行するユーザーを移動すると、そのユーザーの音声会議を使用する、1 つだけの会議の移行をトリガーするためにユーザーを移動する前にまず、オーディオ会議を割り当てることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="404a1-157">If you move a user from on-premises to the cloud and you intend for that user to use Audio Conferencing, we recommend that you first assign the audio conference before you move the user so that only 1 meeting migration is triggered.</span></span>

> [!NOTE]
> <span data-ttu-id="404a1-158">現在の会議を MoveToTeams スイッチを使用してチームに直接移行することは、タップでできるだけです。</span><span class="sxs-lookup"><span data-stu-id="404a1-158">Currently the ability to migrate meetings directly to Teams via the MoveToTeams switch is only available in TAP.</span></span> <span data-ttu-id="404a1-159">タップのお客様が、MoveToTeams スイッチを指定する場合は、ユーザーは、TeamsOnly モードに移動されますが、会議は、ビジネス オンラインの Skype に移動されます。</span><span class="sxs-lookup"><span data-stu-id="404a1-159">If you are not a TAP customer and the MoveToTeams switch is specified, the user will be moved to TeamsOnly mode, but the meetings will be moved to Skype for Business Online.</span></span> <span data-ttu-id="404a1-160">場合でも、ユーザーは、TeamsOnly モードに参加できますビジネス会議のため、Skype。</span><span class="sxs-lookup"><span data-stu-id="404a1-160">Even though the user is in TeamsOnly mode, they can still join any Skype for Business meeting.</span></span>

### <a name="updating-meetings-when-a-users-audio-conferencing-settings-change"></a><span data-ttu-id="404a1-161">ユーザーの電話会議の設定が変更されるときの会議の更新</span><span class="sxs-lookup"><span data-stu-id="404a1-161">Updating meetings when a user's audio conferencing settings change</span></span>

<span data-ttu-id="404a1-162">MMS では以下の場合では、ビジネスおよびマイクロソフトのチーム会議の追加、削除、またはダイヤルインの座標を変更する既存の Skype が更新されます。</span><span class="sxs-lookup"><span data-stu-id="404a1-162">In the following cases, MMS will update existing Skype for Business and Microsoft Teams meetings to add, remove, or modify dial-in coordinates:</span></span>

- <span data-ttu-id="404a1-163">サード ・ パーティ製のオーディオ会議プロバイダーを割り当てるか、ユーザー、およびそのユーザーにマイクロソフトの電話会議サービスのライセンスを削除するは使用できません。</span><span class="sxs-lookup"><span data-stu-id="404a1-163">When you assign or remove a Microsoft Audio Conferencing service license to a user, and that user is not enabled for a third-party audio conferencing provider.</span></span>
- <span data-ttu-id="404a1-164">変更すると、ユーザーのオーディオ会議プロバイダー、他のプロバイダーからマイクロソフトでは、ユーザーに提供される、マイクロソフトの音声会議のライセンスが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="404a1-164">When you change the audio conferencing provider of a user from any other provider to Microsoft, provided the user is assigned a Microsoft Audio Conferencing license.</span></span> <span data-ttu-id="404a1-165">詳細については、[オーディオ会議プロバイダーとしてのマイクロソフトの割り当て](https://docs.microsoft.com/en-us/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="404a1-165">For more information, see [Assign Microsoft as the audio conferencing provider](https://docs.microsoft.com/en-us/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).</span></span> <span data-ttu-id="404a1-166">[ACP]、サード パーティのオーディオ会議プロバイダーのサポートがスケジュールされる寿命の 2019 年 4 月 1日のとして[発表されていた](https://docs.microsoft.com/skypeforbusiness/legal-and-regulatory/end-of-integration-with-3rd-party-providers)にも注意してください。</span><span class="sxs-lookup"><span data-stu-id="404a1-166">Also note that support for third party audio conferencing providers [ACP] is scheduled for end of life on April 1, 2019, as [previously announced](https://docs.microsoft.com/skypeforbusiness/legal-and-regulatory/end-of-integration-with-3rd-party-providers).</span></span>
- <span data-ttu-id="404a1-167">有効または無効にするユーザーの電話会議。</span><span class="sxs-lookup"><span data-stu-id="404a1-167">When you enable or disable audio conferencing for a user.</span></span>
- <span data-ttu-id="404a1-168">変更するか、パブリック ・ ミーティングを使用するように構成するユーザーの会議 ID をリセットします。</span><span class="sxs-lookup"><span data-stu-id="404a1-168">When you change or reset the conference ID for a user configured to use public meetings.</span></span>
- <span data-ttu-id="404a1-169">ユーザーを新しい電話会議ブリッジに移行する場合</span><span class="sxs-lookup"><span data-stu-id="404a1-169">When you move the user to a new audio conferencing bridge.</span></span>
- <span data-ttu-id="404a1-170">オーディオ会議ブリッジからの電話番号が割り当てられていません。</span><span class="sxs-lookup"><span data-stu-id="404a1-170">When a phone number from a audio conferencing bridge is unassigned.</span></span> <span data-ttu-id="404a1-171">これは、追加の手順を必要とする複雑なシナリオです。</span><span class="sxs-lookup"><span data-stu-id="404a1-171">This is a complex scenario that requires additional steps.</span></span> <span data-ttu-id="404a1-172">詳細については、[変更オーディオ会議ブリッジの電話番号](https://docs.microsoft.com/en-us/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="404a1-172">For more information, see [Change the phone numbers on your audio conferencing bridge](https://docs.microsoft.com/en-us/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).</span></span>

<span data-ttu-id="404a1-p117">ユーザーの電話会議の設定に対する変更の一部は、MMS をトリガーしません。特に、次の 2 つの変更では、MMS によって会議が更新されません。</span><span class="sxs-lookup"><span data-stu-id="404a1-p117">Not all changes to a user's audio conferencing settings trigger MMS. Specifically, the following two changes won't result in MMS updating meetings:</span></span>

- <span data-ttu-id="404a1-175">会議の開催者の SIP アドレスを変更する場合 (SIP ユーザー名または SIP ドメインのいずれか)</span><span class="sxs-lookup"><span data-stu-id="404a1-175">When you change the SIP address for the meeting organizer (either their SIP user name or their SIP domain)</span></span>
- <span data-ttu-id="404a1-176">組織の URL を使用しての会議を変更すると、`Update-CsTenantMeetingUrl`コマンドです。</span><span class="sxs-lookup"><span data-stu-id="404a1-176">When you change your organization's meeting URL using the `Update-CsTenantMeetingUrl` command.</span></span>


### <a name="updating-meetings-when-assigning-teamsupgradepolicy"></a><span data-ttu-id="404a1-177">TeamsUpgradePolicy を割り当てる場合は、会議を更新</span><span class="sxs-lookup"><span data-stu-id="404a1-177">Updating meetings when assigning TeamsUpgradePolicy</span></span>

> [!NOTE]
> <span data-ttu-id="404a1-178">だけがタップの顧客に利用できる現在の機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="404a1-178">This section describes functionality that is currently only available to TAP customers.</span></span> <span data-ttu-id="404a1-179">マイクロソフトでは、月 2019年のいずれかの時点にこの機能をすべてのお客様に利用できるようにするのには期待しています。</span><span class="sxs-lookup"><span data-stu-id="404a1-179">Microsoft expects to make this functionality available to all customers sometime in May 2019.</span></span>

<span data-ttu-id="404a1-180">既定では、会議の移行は、自動的に起動のインスタンスがユーザーに付与されると`TeamsUpgradePolicy`と`mode=TeamsOnly`または`mode= SfBWithTeamsCollabAndMeetings`。</span><span class="sxs-lookup"><span data-stu-id="404a1-180">By default, meeting migration will be automatically triggered when a user is granted an instance of `TeamsUpgradePolicy` with `mode=TeamsOnly` or `mode= SfBWithTeamsCollabAndMeetings`.</span></span> <span data-ttu-id="404a1-181">これらのモードのいずれかを付与する場合は、会議を移行し、指定しない場合は、`MigrateMeetingsToTeams $false`の`Grant-CsTeamsUpgradePolicy`。</span><span class="sxs-lookup"><span data-stu-id="404a1-181">If you do not want to migrate meetings when granting either of these modes, then specify `MigrateMeetingsToTeams $false` in `Grant-CsTeamsUpgradePolicy`.</span></span>

<span data-ttu-id="404a1-182">また、次の点を注意してください。</span><span class="sxs-lookup"><span data-stu-id="404a1-182">Also note the following:</span></span>

- <span data-ttu-id="404a1-183">会議の移行のみ呼び出されるを与えるときに`TeamsUpgradePolicy`の特定のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="404a1-183">Meeting migration is only invoked when you grant `TeamsUpgradePolicy` for a specific user.</span></span> <span data-ttu-id="404a1-184">付与する場合は`TeamsUpgradePolicy`と`mode=TeamsOnly`または`mode=SfBWithTeamsCollabAndMeetings`テナント単位で会議の移行は呼び出されません。</span><span class="sxs-lookup"><span data-stu-id="404a1-184">If you grant `TeamsUpgradePolicy` with `mode=TeamsOnly` or `mode=SfBWithTeamsCollabAndMeetings` on a tenant-wide basis, meeting migration is not invoked.</span></span>
- <span data-ttu-id="404a1-185">ユーザーことができますだけに付与する TeamsOnly モードの場合は、ユーザーのオンライン ホームします。</span><span class="sxs-lookup"><span data-stu-id="404a1-185">A user can only be granted TeamsOnly mode if the user is homed online.</span></span> <span data-ttu-id="404a1-186">使用してホーム設置型ではユーザーを移動する必要があります`Move-CsUser`、上記のとおりです。</span><span class="sxs-lookup"><span data-stu-id="404a1-186">Users that are homed on-premises must be moved using `Move-CsUser` as previously described.</span></span>
- <span data-ttu-id="404a1-187">TeamsOnly または SfBWithTeamsCollabAndMeetings 以外のモードを許可する変換されません既存のチーム ミーティング Skype をビジネス ・ ミーティングの。</span><span class="sxs-lookup"><span data-stu-id="404a1-187">Granting a mode other than TeamsOnly or SfBWithTeamsCollabAndMeetings does not convert existing Teams meetings to Skype for Business meetings.</span></span>

### <a name="trigger-meeting-migration-manually-via-powershell"></a><span data-ttu-id="404a1-188">PowerShell を使用して手動でトリガー会議の移行</span><span class="sxs-lookup"><span data-stu-id="404a1-188">Trigger Meeting Migration manually via PowerShell</span></span>

<span data-ttu-id="404a1-189">会議予定の自動移行の場合、だけでなく管理者手動でトリガーできますユーザーの会議の移行コマンドレットを実行して`Start-CsExMeetingMigration`。</span><span class="sxs-lookup"><span data-stu-id="404a1-189">In addition to automatic meeting migrations, admins can manually trigger meeting migration for a user by running the cmdlet `Start-CsExMeetingMigration`.</span></span> <span data-ttu-id="404a1-190">このコマンドレットは、指定したユーザーの移行要求をキューします。</span><span class="sxs-lookup"><span data-stu-id="404a1-190">This cmdlet queues a migration request for the specified user.</span></span> <span data-ttu-id="404a1-191">新しい`TargetMeetingType`は技術導入プログラムの参加者に制限されて) パラメーターを使用すると、会議を移行する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="404a1-191">The new `TargetMeetingType` parameter (which is currently limited to participants in the Technology Adoption Program) allows you to specify how to migrate the meetings:</span></span> 

- <span data-ttu-id="404a1-192">使用して`TargetMeetingType Current`、ビジネス会議のための Skype は、ビジネス ・ ミーティングの Skype を維持され、チームの会議のチーム会議を維持するを指定します。</span><span class="sxs-lookup"><span data-stu-id="404a1-192">Using `TargetMeetingType Current` specifies that Skype for Business meetings remain Skype for Business meetings and Teams meetings remain Teams meetings.</span></span> <span data-ttu-id="404a1-193">ただしオーディオ会議の調整を変更する可能性があり、ビジネス会議のため、設置型の Skype は、ビジネス オンラインの Skype に移行するとします。</span><span class="sxs-lookup"><span data-stu-id="404a1-193">However audio conferencing coordinates might be changed, and any on-premises Skype for Business meetings would be migrated to Skype for Business Online.</span></span>
- <span data-ttu-id="404a1-194">使用して`TargetMeetingType Teams`のチームに、既存の会議を移行する必要がある、オンライン ビジネスの設置、Skype で会議がホストされるかどうかに関係なくとかどうかに関係なく、オーディオ会議の更新プログラムは、必要を指定します。</span><span class="sxs-lookup"><span data-stu-id="404a1-194">Using `TargetMeetingType Teams` specifies that any existing meeting must be migrated to Teams, regardless of whether the meeting is hosted in Skype for Business online or on-premises, and regardless of whether any audio conferencing updates are required.</span></span> 

<span data-ttu-id="404a1-195">次の例は、すべての会議は、チームに移行できるように、ユーザーの ashaw@contoso.com の会議の移行を開始する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="404a1-195">The example below shows how to initiate meeting migration for user ashaw@contoso.com so that all meetings are migrated to Teams:</span></span>

```
Start-CsExMeetingMigration -Identity ashaw@contoso.com -TargetMeetingType Teams
```

> [!NOTE]
> <span data-ttu-id="404a1-196">開始 CsExMeetingMigration コマンドレットは、すべての顧客に利用可能ですが、新しい TargetMeetingTypeParameter 現在のみタップの顧客の機能です。</span><span class="sxs-lookup"><span data-stu-id="404a1-196">The Start-CsExMeetingMigration cmdlet is available to all customers, but the new TargetMeetingTypeParameter is currently only functional for TAP customers.</span></span> 


## <a name="managing-mms"></a><span data-ttu-id="404a1-197">MMS の管理</span><span class="sxs-lookup"><span data-stu-id="404a1-197">Managing MMS</span></span>

<span data-ttu-id="404a1-198">Windows PowerShell を使用すると、継続的な移行の状態を確認して、手動で会議の移行をトリガーして移行を完全に無効にできます。</span><span class="sxs-lookup"><span data-stu-id="404a1-198">Using Windows PowerShell, you can check the status of ongoing migrations, manually trigger meeting migration, and disable migration altogether.</span></span> 

### <a name="check-the-status-of-meeting-migrations"></a><span data-ttu-id="404a1-199">会議の移行の状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="404a1-199">Check the status of meeting migrations</span></span>

<span data-ttu-id="404a1-200">使用する、`Get-CsMeetingMigrationStatus`会議の移行の状態を確認するコマンドレットです。</span><span class="sxs-lookup"><span data-stu-id="404a1-200">You use the `Get-CsMeetingMigrationStatus` cmdlet to check the status of meeting migrations.</span></span> <span data-ttu-id="404a1-201">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="404a1-201">Below are some examples.</span></span>

- <span data-ttu-id="404a1-202">MMS のすべてのマイグレーション処理のステータスの概要を取得するには、移行の状態のすべての表形式のビューを提供する次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="404a1-202">To get a summary status of all MMS migrations, run the following command which provides a tabular view of all migration states:</span></span>

    ```
    Get-CsMeetingMigrationStatus -SummaryOnly

    State      UserCount
    ------     ---------
    Pending      21
    InProgress    6
    Failed            2 
    Succeeded   131
    ```
- <span data-ttu-id="404a1-203">特定の期間内ですべての移行の完全な詳細情報を取得するには、`StartTime`と`EndTime`のパラメーター。</span><span class="sxs-lookup"><span data-stu-id="404a1-203">To get full details of all migrations within a specific time period, use the `StartTime` and `EndTime` parameters.</span></span> <span data-ttu-id="404a1-204">などの次のコマンドは完全な詳細情報が発生したすべての移行で、2018 年 10 月 1 日からに戻る 2018 年 10 月 8日</span><span class="sxs-lookup"><span data-stu-id="404a1-204">For example, the following command will return full details on all migrations that occurred from October 1, 2018 to October 8, 2018.</span></span>

    ```
    Get-CsMeetingMigrationStatus -StartTime "10/1/2018" -EndTime "10/8/2018"
    ```
- <span data-ttu-id="404a1-205">特定のユーザーの移行の状態を確認するを使用して、`Identity`のパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="404a1-205">To check the status of migration for a specific user, use the `Identity` parameter.</span></span> <span data-ttu-id="404a1-206">たとえば、次のコマンドには、ユーザー ashaw@contoso.com のステータスが返されます。</span><span class="sxs-lookup"><span data-stu-id="404a1-206">For example, the following command will return the status for the user ashaw@contoso.com:</span></span>

    ```
    Get-CsMeetingMigrationStatus -Identity ashaw@contoso.com
    ```
<span data-ttu-id="404a1-207">移行に失敗した場合は、人々 はそれらを解決するまでは、ユーザーが開催する会議にダイヤルインすることができませんので、できるだけ早く、これらの問題を解決するのにはアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="404a1-207">If you see any migrations that have failed, take action to resolve these issues as soon as possible, since people won't be able to dial-in to the meetings organized by those users until you resolve them.</span></span> <span data-ttu-id="404a1-208">場合`Get-CsMeetingMigrationStatus`の移行を示しています。 障害が発生した状態でこれらの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="404a1-208">If `Get-CsMeetingMigrationStatus` shows any migrations in a failed state, perform these steps:</span></span>
 
1. <span data-ttu-id="404a1-209">影響を受けているユーザーを特定します。</span><span class="sxs-lookup"><span data-stu-id="404a1-209">Determine which users are affected.</span></span> <span data-ttu-id="404a1-210">次のコマンドを実行して、影響を受けているユーザーと、報告された特定のエラーのリストを取得します。</span><span class="sxs-lookup"><span data-stu-id="404a1-210">Run the following command to get the list of affected users, and the specific error that was reported:</span></span>

    ```
    Get-CsMeetingMigrationStatus| Where {$_.State -eq "Failed"}| Format-Table Identity, LastMessage
    ```
2. <span data-ttu-id="404a1-211">、影響を受けるユーザーごとに、会議を手動で移行するのには会議の移行ツールを実行します。</span><span class="sxs-lookup"><span data-stu-id="404a1-211">For each affected user, run the Meeting Migration Tool to manually migrate their meetings.</span></span>

3. <span data-ttu-id="404a1-212">会議移行ツールを使用しても移行が機能しない場合には、次の 2 つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="404a1-212">If migration still doesn't work with the Meeting Migration Tool, you have two options:</span></span>

    - <span data-ttu-id="404a1-213">ユーザーに新しい Skype 会議を作成してもらいます。</span><span class="sxs-lookup"><span data-stu-id="404a1-213">Have the users create new Skype meetings.</span></span>
    - <span data-ttu-id="404a1-214">[サポートに問い合わせます](https://go.microsoft.com/fwlink/p/?LinkID=518322)。</span><span class="sxs-lookup"><span data-stu-id="404a1-214">[Contact support](https://go.microsoft.com/fwlink/p/?LinkID=518322).</span></span>


### <a name="enabling-and-disabling-mms"></a><span data-ttu-id="404a1-215">MMS の有効化と無効化</span><span class="sxs-lookup"><span data-stu-id="404a1-215">Enabling and disabling MMS</span></span>

<span data-ttu-id="404a1-216">MMS がすべての組織では、既定で有効になっているが、次のように無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="404a1-216">MMS is enabled by default for all organizations, but it can be disabled as follows:</span></span>

- <span data-ttu-id="404a1-217">テナントのすべてを無効にします。</span><span class="sxs-lookup"><span data-stu-id="404a1-217">Disable entirely for the tenant.</span></span> 
- <span data-ttu-id="404a1-218">音声会議に関連する変更だけを無効にします。</span><span class="sxs-lookup"><span data-stu-id="404a1-218">Disable only for changes related to audio conferencing.</span></span> <span data-ttu-id="404a1-219">MMS をクラウドに移行する、または TeamsOnly モードで SfBWithTeamsCollabAndMeetings モードを付与する設置型からユーザーを移行するとき実行もここでは、 `TeamsUpgradePolicy`。</span><span class="sxs-lookup"><span data-stu-id="404a1-219">In this case, MMS will still run when a user is migrated from on-premises to the cloud or when you grant TeamsOnly mode or SfBWithTeamsCollabAndMeetings mode in `TeamsUpgradePolicy`.</span></span>

<span data-ttu-id="404a1-220">などを手動ですべての会議を移行または組織の電話会議の設定に大幅な変更を加えるときに、MMS を一時的に無効にすることがあります。</span><span class="sxs-lookup"><span data-stu-id="404a1-220">For example, you may want to manually migrate all meetings or temporarily disable MMS while making substantial changes to the audio conferencing settings for your organization</span></span>

<span data-ttu-id="404a1-221">MMS が組織で有効になっているかどうかを表示するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="404a1-221">To see if MMS is enabled for your organization, run the following command.</span></span> <span data-ttu-id="404a1-222">MMS を有効にすると、場合は、`MeetingMigrationEnabled`のパラメーターは、 `$true`。</span><span class="sxs-lookup"><span data-stu-id="404a1-222">MMS is enabled if the `MeetingMigrationEnabled` parameter is `$true`.</span></span>
```
Get-CsTenantMigrationConfiguration
```
<span data-ttu-id="404a1-223">有効にするか、MMS を完全に無効にするには、`Set-CsTenantMigrationConfiguration`コマンドです。</span><span class="sxs-lookup"><span data-stu-id="404a1-223">To enable or disable MMS entirely, use the `Set-CsTenantMigrationConfiguration` command.</span></span> <span data-ttu-id="404a1-224">たとえば、MMS を無効にするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="404a1-224">For example, to disable MMS, run the following command:</span></span>

```
Set-CsTenantMigrationConfiguration -MeetingMigrationEnabled $false
```
<span data-ttu-id="404a1-225">MMS が組織で有効になっている、オーディオ会議の更新が有効なかどうかを確認する場合は、値を確認して、`AutomaticallyMigrateUserMeetings`からの出力パラメーター `Get-CsOnlineDialInConferencingTenantSettings`。</span><span class="sxs-lookup"><span data-stu-id="404a1-225">If MMS is enabled in the organization and you want to check if it is enabled for audio conferencing updates, check the value of the `AutomaticallyMigrateUserMeetings` parameter in the output from `Get-CsOnlineDialInConferencingTenantSettings`.</span></span> <span data-ttu-id="404a1-226">オーディオ会議の MMS を無効にするを有効またはを使用して、 `Set-CsOnlineDialInConferencingTenantSettings`。</span><span class="sxs-lookup"><span data-stu-id="404a1-226">To enable or disable MMS for audio conferencing, use `Set-CsOnlineDialInConferencingTenantSettings`.</span></span> <span data-ttu-id="404a1-227">たとえば、オーディオ会議のための MMS を無効にするするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="404a1-227">For example, to disable MMS for audio conferencing, run the following command:</span></span>

```
Set-CsOnlineDialInConferencingTenantSettings  -AutomaticallyMigrateUserMeetings $false
```

## <a name="related-topics"></a><span data-ttu-id="404a1-228">関連項目</span><span class="sxs-lookup"><span data-stu-id="404a1-228">Related topics</span></span>

[<span data-ttu-id="404a1-229">Office 365 での電話会議を試用または購入する</span><span class="sxs-lookup"><span data-stu-id="404a1-229">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

[<span data-ttu-id="404a1-230">オンプレミスとクラウドの間でユーザーの移動</span><span class="sxs-lookup"><span data-stu-id="404a1-230">Move users between on-premises and cloud</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)
