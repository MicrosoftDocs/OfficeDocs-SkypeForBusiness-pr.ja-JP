---
title: 電話会議ブリッジで電話番号を変更する
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6403f6d1-c05a-44ab-a6e0-558000e246f4
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 新しいサービス電話番号を会議ブリッジに割り当て、ユーザーの範囲を拡大するために必要な手順について説明します。
ms.openlocfilehash: e2e1aa3d5626f6592f22e0850a8c7419d7549b38
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569189"
---
# <a name="change-the-phone-numbers-on-your-audio-conferencing-bridge"></a><span data-ttu-id="d0bed-103">電話会議ブリッジの電話番号を変更する</span><span class="sxs-lookup"><span data-stu-id="d0bed-103">Change the phone numbers on your Audio Conferencing bridge</span></span>

<span data-ttu-id="d0bed-104">電話会議ライセンス **を購入すると** 、Microsoft は組織の電話会議ブリッジをホストしています。</span><span class="sxs-lookup"><span data-stu-id="d0bed-104">When you buy **Audio Conferencing** licenses, Microsoft is hosting your audio conferencing bridge for your organization.</span></span> <span data-ttu-id="d0bed-105">電話会議ブリッジは、さまざまな場所からダイヤルイン電話番号を提供し、会議の開催者と参加者が電話を使って Skype for Business 会議または Microsoft Teams 会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="d0bed-105">The audio conferencing bridge gives out dial-in phone numbers from different locations so that meeting organizers and participants can use them to join Skype for Business or Microsoft Teams meetings using a phone.</span></span>
  
<span data-ttu-id="d0bed-106">会議ブリッジに既に割り当てられている電話番号に加えて、他の場所から追加のサービス番号 [(電話](/microsoftteams/getting-service-phone-numbers) 会議に使用される有料電話番号と無料電話番号) を取得し、会議ブリッジに割り当てると、ユーザーの範囲を拡大できます。</span><span class="sxs-lookup"><span data-stu-id="d0bed-106">In addition to the phone numbers already assigned to your conferencing bridge, you can [get additional service numbers](/microsoftteams/getting-service-phone-numbers) (toll and toll-free numbers used for audio conferencing) from other locations, and then assign them to the conferencing bridge so you can expand coverage for your users.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d0bed-107">会議ブリッジの電話番号を割り当て/割り当て解除するには、電話番号が ' サービス ' 番号 *である* 必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0bed-107">To be able to assign/unassign a phone number for a conferencing bridge, the phone number must be a '*service*' number.</span></span> <span data-ttu-id="d0bed-108">Microsoft Teams 管理センターで音声電話番号に移動し、[番号の種類] 列を見て、その番号の種類  >  を **確認** できます。</span><span class="sxs-lookup"><span data-stu-id="d0bed-108">You can see the type of number it is by navigating to **Voice** > **Phone numbers** in the Microsoft Teams admin center and looking in the **Number Type** column.</span></span> <span data-ttu-id="d0bed-109">ユーザーが無料電話番号でブリッジにダイヤルインするには、Microsoft 365 または Office 365 コミュニケーション クレジットを最初に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0bed-109">Microsoft 365 or Office 365 Communications Credits must be set up first in order for users to dial into the bridge on a toll-free number.</span></span>

## <a name="steps-when-you-are-assigning-a-new-service-phone-number-to-your-conference-bridge"></a><span data-ttu-id="d0bed-110">会議ブリッジに新しいサービス電話番号を割り当てる手順</span><span class="sxs-lookup"><span data-stu-id="d0bed-110">Steps when you are assigning a new service phone number to your conference bridge</span></span>

### <a name="step-1---assign-the-new-phone-number-to-your-audio-conferencing-bridge"></a><span data-ttu-id="d0bed-111">手順 1 - 新しい電話番号を電話会議ブリッジに割り当てる</span><span class="sxs-lookup"><span data-stu-id="d0bed-111">Step 1 - Assign the new phone number to your audio conferencing bridge</span></span>

<span data-ttu-id="d0bed-112">![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**</span><span class="sxs-lookup"><span data-stu-id="d0bed-112">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="d0bed-113">左側のナビゲーション ウィンドウで、[音声電話番号 **] に**  >  **移動します**。</span><span class="sxs-lookup"><span data-stu-id="d0bed-113">On the left navigation pane, go to **Voice** > **Phone numbers**.</span></span>

2. <span data-ttu-id="d0bed-114">一覧から電話番号を選び、[編集] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="d0bed-114">Select the phone number from the list, and click **Edit**.</span></span>

3. <span data-ttu-id="d0bed-115">[編集]**ページの [** 割り当 **て済み**] で、ドロップダウンを展開し、[会議ブリッジ **の適用] を選択**  >  **します**。</span><span class="sxs-lookup"><span data-stu-id="d0bed-115">On the **Edit** page, under **Assigned to**, expand the dropdown and then select **Conference bridge** > **Apply**.</span></span>

### <a name="step-2---change-the-default-phone-number-of-your-conference-bridge-optional"></a><span data-ttu-id="d0bed-116">手順 2 - 会議ブリッジの既定の電話番号を変更する (オプション)</span><span class="sxs-lookup"><span data-stu-id="d0bed-116">Step 2 - Change the default phone number of your conference bridge (optional)</span></span>

<span data-ttu-id="d0bed-117">会議ブリッジの既定の電話番号は、会議内から発信通話が参加者または開催者によって発信された場合に使用される発信者番号を定義します。</span><span class="sxs-lookup"><span data-stu-id="d0bed-117">The default phone number of your conference bridge defines the caller ID that will be used when an outbound call is placed by a participant or the organizer from within a meeting.</span></span>

<span data-ttu-id="d0bed-118">会議ブリッジの既定の番号として設定できるのはサービス有料電話番号のみです。 **サービスの無料電話番号を会議ブリッジの既定の番号として設定できない**。</span><span class="sxs-lookup"><span data-stu-id="d0bed-118">Only a service toll number can be set as the default number for your conferencing bridge; **service toll-free numbers can't be set as the default number of your conferencing bridge**.</span></span> <span data-ttu-id="d0bed-119">サービス有料電話番号を割り当て、それを電話会議ブリッジの新しい既定の番号として設定する場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="d0bed-119">If you are assigning a service toll number and you would like to set it as the new default number for your audio conferencing bridge, perform these steps:</span></span>

<span data-ttu-id="d0bed-120">![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**</span><span class="sxs-lookup"><span data-stu-id="d0bed-120">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="d0bed-121">左側のナビゲーション ウィンドウで、[会議会議ブリッジ **]**  >  **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="d0bed-121">On the left navigation pane, go to **Meetings** > **Conference bridges**.</span></span>

2. <span data-ttu-id="d0bed-122">既定として構成するサービス有料電話番号を強調表示します。</span><span class="sxs-lookup"><span data-stu-id="d0bed-122">Highlight the service toll number that you want to configure as the default.</span></span>

3. <span data-ttu-id="d0bed-123">[**既定に設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d0bed-123">Select **Set as default**.</span></span>
 
### <a name="step-3---change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users-optional"></a><span data-ttu-id="d0bed-124">手順 3 - ユーザーの会議出席招待に含まれる既定の電話番号を変更する (オプション)</span><span class="sxs-lookup"><span data-stu-id="d0bed-124">Step 3 - Change the default phone numbers that are included in the meeting invites of users (optional)</span></span>

<span data-ttu-id="d0bed-125">ユーザーの既定の電話番号は、会議のスケジュールを設定するときに会議の招待に含まれます。</span><span class="sxs-lookup"><span data-stu-id="d0bed-125">The default phone numbers of a user are the ones that are included on their meeting invites when they schedule a meeting.</span></span> <span data-ttu-id="d0bed-126">新しいユーザーに既定の電話番号を割り当てる方法など、詳細については [、「Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) の招待に含まれる電話番号を設定する」または [「Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)の招待に含まれる電話番号を設定する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0bed-126">For more information, including how the default phone numbers are assigned for new users, see [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) or [Set the phone numbers included on invites in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites).</span></span>

<span data-ttu-id="d0bed-127">![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**</span><span class="sxs-lookup"><span data-stu-id="d0bed-127">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="d0bed-128">左側のナビゲーション ウィンドウで、[ユーザー  ] に移動し、一覧で目的のユーザーの表示名をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d0bed-128">On the left navigation pane, go to **Users** and click the Display name of the desired user on the list.</span></span>

2. <span data-ttu-id="d0bed-129">電話会議の **横にある [編集**] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="d0bed-129">Next to **Audio conferencing**, click on **Edit**.</span></span>

3. <span data-ttu-id="d0bed-130">[ **有料電話番号] または** **[フリーダイヤル番号**] で、ドロップダウンから番号を選び、[適用] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="d0bed-130">Under **Toll number** or **Toll-free number**, select the number from the dropdown and click **Apply**.</span></span>

<span data-ttu-id="d0bed-131">変更が適用されると、次回新しい会議をスケジュールする場合、新しい既定の電話番号が開催者の会議の招待に含まれます。</span><span class="sxs-lookup"><span data-stu-id="d0bed-131">After the changes have been applied, the new default phone numbers will be included on the meeting invites of organizers the next time they schedule a new meeting.</span></span>

### <a name="step-4---update-existing-meeting-invites-of-users-using-the-meeting-migration-service-optional"></a><span data-ttu-id="d0bed-132">手順 4 - Meeting Migration Service を使用してユーザーの既存の会議出席招待を更新する (オプション)</span><span class="sxs-lookup"><span data-stu-id="d0bed-132">Step 4 - Update existing meeting invites of users using the Meeting Migration Service (optional)</span></span>

<span data-ttu-id="d0bed-133">次の 2 つの手順では、次の手順をWindows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="d0bed-133">For the next two steps, you will need to start Windows PowerShell.</span></span>
  
<span data-ttu-id="d0bed-134">一部またはすべてのユーザーの会議出席招待に含まれる既定の電話番号を更新した場合は、必要に応じて、Meeting Migration Service を使用して既定の電話番号を変更する前に組織内のユーザーに送信された会議出席招待を更新できます。</span><span class="sxs-lookup"><span data-stu-id="d0bed-134">If you updated the default phone numbers that are included in the meeting invites for some or all of your users, you can optionally update meeting invites that were already sent to users in your organization before their default phone numbers were changed using the Meeting Migration Service.</span></span> <span data-ttu-id="d0bed-135">詳細については [、「Meeting Migration Service (MMS) のセットアップ」を参照してください](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)。</span><span class="sxs-lookup"><span data-stu-id="d0bed-135">For additional information, see [Setting up the Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span></span>
  
- <span data-ttu-id="d0bed-136">手順 2 で既定の電話番号を変更したユーザーの Meeting Migration Service (MMS) を実行します。</span><span class="sxs-lookup"><span data-stu-id="d0bed-136">Run the Meeting Migration Service (MMS) for the users who had their default phone numbers changed in Step 2.</span></span> <span data-ttu-id="d0bed-137">これを行うには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="d0bed-137">To do this, run the following command:</span></span>

```PowerShell
    Start-CsExMeetingMigration user@contoso.com
```

- <span data-ttu-id="d0bed-138">会議の移行の状態を表示できます。</span><span class="sxs-lookup"><span data-stu-id="d0bed-138">You can also view the meeting migration status.</span></span> <span data-ttu-id="d0bed-139">保留中または進行中の状態で操作が行えな場合、すべての会議のスケジュール *が変更* されます。</span><span class="sxs-lookup"><span data-stu-id="d0bed-139">All meetings would be rescheduled once there are no operations in  *Pending*  or *In-Progress*  state.</span></span>

```PowerShell
    Get-CsMeetingMigrationStatus -SummaryOnly
```

## <a name="steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge"></a><span data-ttu-id="d0bed-140">会議ブリッジのサービス電話番号の割り当てを解除する場合の手順</span><span class="sxs-lookup"><span data-stu-id="d0bed-140">Steps when you are unassigning a service phone number for a conferencing bridge</span></span>


<span data-ttu-id="d0bed-141">会議ブリッジから電話番号の割り当てを解除すると、ユーザーは、その電話番号を使用して会議に参加できなくなります。</span><span class="sxs-lookup"><span data-stu-id="d0bed-141">When you unassign a phone number from a conferencing bridge, users won't be able to join any meetings using that phone number anymore.</span></span> <span data-ttu-id="d0bed-142">電話番号は変更中なので、電話番号が電話会議ブリッジから割り当て解除される前に、電話番号を既定の番号 (存在する場合) として持つ可能性があるすべてのユーザーを更新し、既存の会議出席招待を更新することが重要です。</span><span class="sxs-lookup"><span data-stu-id="d0bed-142">Because the phone number is changing, it's important to update all users who could have a phone number as their default number (if any) and to update their existing meeting invites before the phone number is unassigned from the audio conferencing bridge.</span></span>

<span data-ttu-id="d0bed-143">ユーザーと会議を更新せずに電話番号が削除された場合、既存の会議の招待には、会議に参加できない電話番号が含まれている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d0bed-143">If the phone number is removed without updating the users and their meetings, their existing meeting invites could contain a phone number that won't work for joining their meetings.</span></span>

<span data-ttu-id="d0bed-144">最初の 3 つの手順では、次の手順をWindows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="d0bed-144">For the first three steps, you will need to start Windows PowerShell.</span></span> <span data-ttu-id="d0bed-145">この方法を確認するには、[アカウントを使って管理する方法を知りたい [Windows PowerShell。](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#about-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="d0bed-145">To see how to do this, click [Want to know how to manage with Windows PowerShell?](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#about-windows-powershell)</span></span>

### <a name="step-1---update-users-who-have-the-phone-number-to-be-unassigned-as-one-of-their-default-numbers"></a><span data-ttu-id="d0bed-146">手順 1 - 既定の番号の 1 つとして割り当てられていない電話番号を持つユーザーを更新する</span><span class="sxs-lookup"><span data-stu-id="d0bed-146">Step 1 - Update users who have the phone number to be unassigned as one of their default numbers</span></span>

<span data-ttu-id="d0bed-147">既定の番号として割り当て解除する番号を持つすべてのユーザーの既定の有料電話番号または無料電話番号を置き換え、会議のスケジュールを変更するプロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="d0bed-147">Replace the default toll or toll-free number for all users who have the number to be unassigned as a default number and start the process of rescheduling their meetings.</span></span> <span data-ttu-id="d0bed-148">これを行うには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="d0bed-148">To do this, run the following command:</span></span>

```PowerShell
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```
 > [!IMPORTANT] 
 ><span data-ttu-id="d0bed-149">Microsoft Teams 管理センターで、既定の有料または無料のユーザー数を変更できます。</span><span class="sxs-lookup"><span data-stu-id="d0bed-149">You can also change the default toll or toll-free number of users in the Microsoft Teams admin center.</span></span> <span data-ttu-id="d0bed-150">ただし、これにより自動的に会議のスケジュールが変更されるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="d0bed-150">However, this won't automatically reschedule their meetings.</span></span> 
 
 <span data-ttu-id="d0bed-151">詳細については [、「Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) の招待に含まれる電話番号を設定する」または「Skype for Business Online の招待に含まれる電話番号 [を設定する」を参照してください](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)。</span><span class="sxs-lookup"><span data-stu-id="d0bed-151">For additional information, see [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) or [Set the phone numbers included on invites in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites).</span></span>

  > [!NOTE]
  > <span data-ttu-id="d0bed-152">組織の規模によっては、完了に時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="d0bed-152">Depending on the size of your organization, this could take some time to complete.</span></span>

### <a name="step-2---view-meeting-migration-status-using-windows-powershell"></a><span data-ttu-id="d0bed-153">手順 2 - 会議の移行の状態を次の手順でWindows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d0bed-153">Step 2 - View meeting migration status using Windows PowerShell</span></span>

<span data-ttu-id="d0bed-154">保留中または進行中の状態で操作が行えな場合、すべての会議のスケジュール *が変更* されます。</span><span class="sxs-lookup"><span data-stu-id="d0bed-154">All meetings will be rescheduled once there are no operations in *Pending* or *In-Progress* state.</span></span>

```PowerShell
Get-CsMeetingMigrationStatus -SummaryOnly
```

<span data-ttu-id="d0bed-155">Meeting Migration Service の詳細については、「Meeting Migration [Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)をセットアップする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0bed-155">For more information about the Meeting Migration Service, see [Setting up the Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span></span>
  
### <a name="step-3---unassign-the-old-phone-number-from-the-audio-conferencing-bridge"></a><span data-ttu-id="d0bed-156">手順 3 - 電話会議ブリッジから古い電話番号の割り当てを解除する</span><span class="sxs-lookup"><span data-stu-id="d0bed-156">Step 3 - Unassign the old phone number from the audio conferencing bridge</span></span>

<span data-ttu-id="d0bed-157">![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**</span><span class="sxs-lookup"><span data-stu-id="d0bed-157">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="d0bed-158">In the left navigation, go to **Voice** > **Phone numbers**.</span><span class="sxs-lookup"><span data-stu-id="d0bed-158">In the left navigation, go to **Voice** > **Phone numbers**.</span></span>

2. <span data-ttu-id="d0bed-159">電話番号がフリーダイヤル番号の場合は、一覧から電話番号を選び、[リリース] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="d0bed-159">If the phone number is a toll-free number, select the phone number from the list, and click **Release**.</span></span> <span data-ttu-id="d0bed-160">電話番号が有料電話番号の場合は [、Microsoft](https://go.microsoft.com/fwlink/?linkid=2091806) サポートに問い合わせ、電話番号を割り当て解除してください。</span><span class="sxs-lookup"><span data-stu-id="d0bed-160">If the phone number is a toll number, please contact [Microsoft support](https://go.microsoft.com/fwlink/?linkid=2091806) to have the phone number unassigned.</span></span>

3. <span data-ttu-id="d0bed-161">電話番号がフリーダイヤル番号の場合は、確認ウィンドウで **[** はい] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d0bed-161">If the phone number is a toll-free number, click **Yes** in the confirmation window.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="d0bed-162">電話番号が電話会議ブリッジから割り当て解除された後、ユーザーは電話番号を使用して新規または既存の会議に参加できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="d0bed-162">After a phone number is unassigned from an audio conferencing bridge, the phone number will no longer be available for users to join new or existing meetings.</span></span>

### <a name="save-time-and-automate"></a><span data-ttu-id="d0bed-163">時間を節約して自動化する</span><span class="sxs-lookup"><span data-stu-id="d0bed-163">Save time and automate</span></span>

<span data-ttu-id="d0bed-164">このプロセスを自動化して時間を節約するために [、Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) または **Set-CsOnlineDialInConferencingUserDefaultNumber** コマンドレットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="d0bed-164">To save time by automating this process, you can use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) or the **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlets.</span></span>

- <span data-ttu-id="d0bed-165">特定ユーザーのデフォルトの有料または無料電話番号を変更するには、[[Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688)] コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="d0bed-165">Use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) cmdlet to change the default toll or toll-free number for specific users.</span></span>

  - <span data-ttu-id="d0bed-166">ユーザーのデフォルトの無料電話番号を変更するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="d0bed-166">To change the default toll-free number for a user, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   80045551234
  ```

- <span data-ttu-id="d0bed-167">ユーザーの元の既定の電話番号または所在地に基づいて既定の有料または無料電話番号を変更するには、 **Set-CsOnlineDialInConferencingUserDefaultNumber** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="d0bed-167">Use the **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlet to change the default toll or toll-free number of users based on their original default number or their location.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d0bed-168">BridgeID を探すには、 **Get-CsOnlineDialInConferencingBridge** を使用します。</span><span class="sxs-lookup"><span data-stu-id="d0bed-168">To find the BridgeID, use the **Get-CsOnlineDialInConferencingBridge**.</span></span>

  - <span data-ttu-id="d0bed-169">既定の無料電話番号を 8005551234 に設定するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="d0bed-169">To set the default toll-free number for all users without one to 8005551234, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```

  - <span data-ttu-id="d0bed-170">既定の無料電話番号が 8005551234 であるすべてのユーザーの既定の無料電話番号を 8005551239 に変更し、会議のスケジュールを自動的に変更するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="d0bed-170">To change the default toll-free number of all users that have 8005551234 as their default toll-free number to 8005551239 and automatically reschedule their meetings, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber 8005551234 -ToNumber 8005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

  - <span data-ttu-id="d0bed-171">米国内のすべてのユーザーの既定の無料電話番号を 8005551234 に設定し、会議のスケジュールを自動的に変更するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="d0bed-171">To set the default toll-free number of all users located in the U.S. to 8005551234 and automatically reschedule their meetings, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

    > [!NOTE]
    > <span data-ttu-id="d0bed-172">上記で使用する場所は、Microsoft 365 管理センターで設定されているユーザーの連絡先情報と一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0bed-172">The location that is used above needs to match the contact information of user(s) that is set in the Microsoft 365 admin center.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="d0bed-173">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="d0bed-173">Troubleshooting</span></span>

<span data-ttu-id="d0bed-174">**[割り当て解除] ボタンが使用できない**</span><span class="sxs-lookup"><span data-stu-id="d0bed-174">**Unassign button isn't available**</span></span>

<span data-ttu-id="d0bed-175">番号の割り当てを解除したいが、ボタンを使用できない場合、その上にマウス ポインターを置くと、サポートに連絡するためにリダイレクトされ、次のメッセージが表示されます。"既定の番号または共有番号はブリッジから割り当て解除できません。 _専用の有料電話番号の割り当てを解除するには、サポートにお問い合わせください。_</span><span class="sxs-lookup"><span data-stu-id="d0bed-175">You want to Unassign a number but the button isn't available, and if while hovering over it, you are redirected to contact Support with the following message _"Default or shared numbers can´t be unassigned from the bridge. To unassign dedicated toll numbers, please contact support._".</span></span>

<span data-ttu-id="d0bed-176">ブリッジの詳細を取得するには、次の PowerShell を実行します。</span><span class="sxs-lookup"><span data-stu-id="d0bed-176">To obtain more information about the bridge(s), run the following Powershell :</span></span>
```PowerShell
Get-CsOnlineDialInConferencingBridge -Name "Conference Bridge"
```

<span data-ttu-id="d0bed-177">結果には、Identity、Name、Region などの他の情報を除いて、DefaultServiceNumber も含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0bed-177">The result, aside other information like Identity, Name and Region, should also contain the DefaultServiceNumber.</span></span>

<span data-ttu-id="d0bed-178">**DefaultServiceNumber**"8005551234" の割り当てを解除する例</span><span class="sxs-lookup"><span data-stu-id="d0bed-178">**Example**, to unassign, the DefaultServiceNumber "8005551234"</span></span>
```PowerShell
Unregister-CsOnlineDialInConferencingServiceNumber -BridgeName "Conference Bridge" -RemoveDefaultServiceNumber 8005551234 
```

## <a name="about-windows-powershell"></a><span data-ttu-id="d0bed-179">概要Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d0bed-179">About Windows PowerShell</span></span>

<span data-ttu-id="d0bed-180">ユーザー Windows PowerShell、ユーザーの管理や許可されていない操作を管理できます。</span><span class="sxs-lookup"><span data-stu-id="d0bed-180">With Windows PowerShell you can manage users and what they are or are not allowed to do.</span></span> <span data-ttu-id="d0bed-181">Windows PowerShellは、1 つの管理ポイントを使用して Microsoft 365 または Office 365 と Skype for Business Online を管理し、毎日の作業を簡素化することができます。特に、複数のタスクを実行する必要がある場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d0bed-181">Windows PowerShell  can help you manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, especially when you've got multiple tasks to do.</span></span> <span data-ttu-id="d0bed-182">Windows PowerShell の使用を開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0bed-182">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="d0bed-183">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="d0bed-183">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [<span data-ttu-id="d0bed-184">Office 365 PowerShell を使用する必要がある理由</span><span class="sxs-lookup"><span data-stu-id="d0bed-184">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

<span data-ttu-id="d0bed-185">Windows PowerShellは、多くのユーザーに対して同時に設定変更を行う場合など、Microsoft 365 管理センターを使用する場合に限って、速度、シンプルさ、生産性の点で多くの利点があります。</span><span class="sxs-lookup"><span data-stu-id="d0bed-185">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="d0bed-186">次のトピックでこれらの利点について説明します。</span><span class="sxs-lookup"><span data-stu-id="d0bed-186">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="d0bed-187">Microsoft 365 または Office 365 を管理するための最適Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d0bed-187">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [<span data-ttu-id="d0bed-188">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="d0bed-188">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [<span data-ttu-id="d0bed-189">Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行</span><span class="sxs-lookup"><span data-stu-id="d0bed-189">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="d0bed-190">関連項目</span><span class="sxs-lookup"><span data-stu-id="d0bed-190">Related topics</span></span>
[<span data-ttu-id="d0bed-191">電話会議ブリッジの設定を変更する</span><span class="sxs-lookup"><span data-stu-id="d0bed-191">Change the settings for an Audio Conferencing bridge</span></span>](change-the-settings-for-an-audio-conferencing-bridge.md)
