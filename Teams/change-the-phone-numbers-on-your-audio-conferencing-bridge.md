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
description: 新しいサービス電話番号を会議ブリッジに割り当て、ユーザーの対象範囲を拡大するために必要な手順について説明します。
ms.openlocfilehash: f477c583db36e6dee514a84f32de202361d01c11
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102663"
---
# <a name="change-the-phone-numbers-on-your-audio-conferencing-bridge"></a><span data-ttu-id="20454-103">電話会議ブリッジの電話番号を変更する</span><span class="sxs-lookup"><span data-stu-id="20454-103">Change the phone numbers on your Audio Conferencing bridge</span></span>

<span data-ttu-id="20454-104">電話会議ライセンス **を購入すると** 、Microsoft は組織の電話会議ブリッジをホストしています。</span><span class="sxs-lookup"><span data-stu-id="20454-104">When you buy **Audio Conferencing** licenses, Microsoft is hosting your audio conferencing bridge for your organization.</span></span> <span data-ttu-id="20454-105">電話会議ブリッジでは、会議の開催者と参加者が電話を使って Skype for Business または Microsoft Teams 会議に参加するために、さまざまな場所からダイヤルイン電話番号を提供します。</span><span class="sxs-lookup"><span data-stu-id="20454-105">The audio conferencing bridge gives out dial-in phone numbers from different locations so that meeting organizers and participants can use them to join Skype for Business or Microsoft Teams meetings using a phone.</span></span>
  
<span data-ttu-id="20454-106">会議ブリッジに既に割り当てられている電話番号に加えて、他の場所から追加のサービス番号 [(電話](./getting-service-phone-numbers.md) 会議に使用される有料電話番号と無料電話番号) を取得し、会議ブリッジに割り当て、ユーザーの範囲を拡大できます。</span><span class="sxs-lookup"><span data-stu-id="20454-106">In addition to the phone numbers already assigned to your conferencing bridge, you can [get additional service numbers](./getting-service-phone-numbers.md) (toll and toll-free numbers used for audio conferencing) from other locations, and then assign them to the conferencing bridge so you can expand coverage for your users.</span></span>
  
> [!NOTE]
> <span data-ttu-id="20454-107">会議ブリッジの電話番号を割り当て/割り当て解除するには、電話番号がサービス ' 番号 *である* 必要があります。</span><span class="sxs-lookup"><span data-stu-id="20454-107">To be able to assign/unassign a phone number for a conferencing bridge, the phone number must be a '*service*' number.</span></span> <span data-ttu-id="20454-108">番号の種類を確認するには、Microsoft Teams 管理センターで[Voice 電話 number] に移動し、[数値の種類] 列  >  **を確認** します。</span><span class="sxs-lookup"><span data-stu-id="20454-108">You can see the type of number it is by navigating to **Voice** > **Phone numbers** in the Microsoft Teams admin center and looking in the **Number Type** column.</span></span> <span data-ttu-id="20454-109">Microsoft 365またはOffice 365通信クレジットは、ユーザーが無料電話番号でブリッジにダイヤルインするために、最初に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="20454-109">Microsoft 365 or Office 365 Communications Credits must be set up first in order for users to dial into the bridge on a toll-free number.</span></span>

## <a name="steps-when-you-are-assigning-a-new-service-phone-number-to-your-conference-bridge"></a><span data-ttu-id="20454-110">会議ブリッジに新しいサービス電話番号を割り当てる手順</span><span class="sxs-lookup"><span data-stu-id="20454-110">Steps when you are assigning a new service phone number to your conference bridge</span></span>

### <a name="step-1---assign-the-new-phone-number-to-your-audio-conferencing-bridge"></a><span data-ttu-id="20454-111">手順 1 - 新しい電話番号を電話会議ブリッジに割り当てる</span><span class="sxs-lookup"><span data-stu-id="20454-111">Step 1 - Assign the new phone number to your audio conferencing bridge</span></span>

<span data-ttu-id="20454-112">![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**</span><span class="sxs-lookup"><span data-stu-id="20454-112">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="20454-113">左側のナビゲーション ウィンドウで、[Voice電話  >  **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="20454-113">On the left navigation pane, go to **Voice** > **Phone numbers**.</span></span>

2. <span data-ttu-id="20454-114">一覧から電話番号を選択し、[編集] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="20454-114">Select the phone number from the list, and click **Edit**.</span></span>

3. <span data-ttu-id="20454-115">[編集]**ページの**[割り当て **]** でドロップダウンを展開し、[会議ブリッジの適用 **] を**  >  **選択します**。</span><span class="sxs-lookup"><span data-stu-id="20454-115">On the **Edit** page, under **Assigned to**, expand the dropdown and then select **Conference bridge** > **Apply**.</span></span>

### <a name="step-2---change-the-default-phone-number-of-your-conference-bridge-optional"></a><span data-ttu-id="20454-116">手順 2 - 会議ブリッジの既定の電話番号を変更する (省略可能)</span><span class="sxs-lookup"><span data-stu-id="20454-116">Step 2 - Change the default phone number of your conference bridge (optional)</span></span>

<span data-ttu-id="20454-117">会議ブリッジの既定の電話番号は、会議内から参加者または開催者によって発信通話が行われるときに使用される発信者 ID を定義します。</span><span class="sxs-lookup"><span data-stu-id="20454-117">The default phone number of your conference bridge defines the caller ID that will be used when an outbound call is placed by a participant or the organizer from within a meeting.</span></span>

<span data-ttu-id="20454-118">会議ブリッジの既定の番号として設定できるのは、サービスの有料電話番号のみです。 **サービスの無料電話番号を会議ブリッジの既定の番号として設定できない**。</span><span class="sxs-lookup"><span data-stu-id="20454-118">Only a service toll number can be set as the default number for your conferencing bridge; **service toll-free numbers can't be set as the default number of your conferencing bridge**.</span></span> <span data-ttu-id="20454-119">サービスの有料電話番号を割り当て、それを電話会議ブリッジの新しい既定の番号として設定する場合は、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="20454-119">If you are assigning a service toll number and you would like to set it as the new default number for your audio conferencing bridge, perform these steps:</span></span>

<span data-ttu-id="20454-120">![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**</span><span class="sxs-lookup"><span data-stu-id="20454-120">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="20454-121">左側のナビゲーション ウィンドウで、[会議会議ブリッジ]  >  **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="20454-121">On the left navigation pane, go to **Meetings** > **Conference bridges**.</span></span>

2. <span data-ttu-id="20454-122">既定として構成するサービスの有料電話番号を強調表示します。</span><span class="sxs-lookup"><span data-stu-id="20454-122">Highlight the service toll number that you want to configure as the default.</span></span>

3. <span data-ttu-id="20454-123">[**既定に設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="20454-123">Select **Set as default**.</span></span>
 
### <a name="step-3---change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users-optional"></a><span data-ttu-id="20454-124">手順 3 - ユーザーの会議出席招待に含まれる既定の電話番号を変更する (省略可能)</span><span class="sxs-lookup"><span data-stu-id="20454-124">Step 3 - Change the default phone numbers that are included in the meeting invites of users (optional)</span></span>

<span data-ttu-id="20454-125">ユーザーの既定の電話番号は、会議のスケジュールを設定するときに会議の招待に含まれる電話番号です。</span><span class="sxs-lookup"><span data-stu-id="20454-125">The default phone numbers of a user are the ones that are included on their meeting invites when they schedule a meeting.</span></span> <span data-ttu-id="20454-126">新しいユーザーに既定の電話番号を割り当てる方法など、詳細については[、「Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md)の招待に含まれる電話番号を設定する」または「Skype for Business Online の招待に含まれる電話番号を設定する[」を参照](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)してください。</span><span class="sxs-lookup"><span data-stu-id="20454-126">For more information, including how the default phone numbers are assigned for new users, see [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) or [Set the phone numbers included on invites in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites).</span></span>

<span data-ttu-id="20454-127">![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**</span><span class="sxs-lookup"><span data-stu-id="20454-127">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="20454-128">左側のナビゲーション ウィンドウで、[ユーザー] に **移動** し、一覧で目的のユーザーの [表示名] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="20454-128">On the left navigation pane, go to **Users** and click the Display name of the desired user on the list.</span></span>

2. <span data-ttu-id="20454-129">[電話会議 **] の横にある [** 編集] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="20454-129">Next to **Audio conferencing**, click on **Edit**.</span></span>

3. <span data-ttu-id="20454-130">[ **有料電話番号] または** **[無料電話番号**] で、ドロップダウンから番号を選択し、[適用] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="20454-130">Under **Toll number** or **Toll-free number**, select the number from the dropdown and click **Apply**.</span></span>

<span data-ttu-id="20454-131">変更が適用されると、次回新しい会議をスケジュールする場合、新しい既定の電話番号が開催者の会議の招待に含まれます。</span><span class="sxs-lookup"><span data-stu-id="20454-131">After the changes have been applied, the new default phone numbers will be included on the meeting invites of organizers the next time they schedule a new meeting.</span></span>

### <a name="step-4---update-existing-meeting-invites-of-users-using-the-meeting-migration-service-optional"></a><span data-ttu-id="20454-132">手順 4 - Meeting Migration Service を使用してユーザーの既存の会議出席招待を更新する (省略可能)</span><span class="sxs-lookup"><span data-stu-id="20454-132">Step 4 - Update existing meeting invites of users using the Meeting Migration Service (optional)</span></span>

<span data-ttu-id="20454-133">次の 2 つの手順では、次の手順を開始Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="20454-133">For the next two steps, you will need to start Windows PowerShell.</span></span>
  
<span data-ttu-id="20454-134">一部またはすべてのユーザーの会議出席招待に含まれる既定の電話番号を更新した場合は、必要に応じて、Meeting Migration Service を使用して既定の電話番号が変更される前に組織内のユーザーに送信された会議出席許可を更新できます。</span><span class="sxs-lookup"><span data-stu-id="20454-134">If you updated the default phone numbers that are included in the meeting invites for some or all of your users, you can optionally update meeting invites that were already sent to users in your organization before their default phone numbers were changed using the Meeting Migration Service.</span></span> <span data-ttu-id="20454-135">詳細については [、「Meeting Migration Service (MMS) の設定」を参照してください](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)。</span><span class="sxs-lookup"><span data-stu-id="20454-135">For additional information, see [Setting up the Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span></span>
  
- <span data-ttu-id="20454-136">手順 2 で既定の電話番号を変更したユーザーに対して、Meeting Migration Service (MMS) を実行します。</span><span class="sxs-lookup"><span data-stu-id="20454-136">Run the Meeting Migration Service (MMS) for the users who had their default phone numbers changed in Step 2.</span></span> <span data-ttu-id="20454-137">これを行うには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="20454-137">To do this, run the following command:</span></span>

```PowerShell
    Start-CsExMeetingMigration user@contoso.com
```

- <span data-ttu-id="20454-138">会議の移行の状態を表示できます。</span><span class="sxs-lookup"><span data-stu-id="20454-138">You can also view the meeting migration status.</span></span> <span data-ttu-id="20454-139">[保留中] または [進行中] 状態の操作がない場合は、すべての *会議のスケジュール\*\*が変更* されます。</span><span class="sxs-lookup"><span data-stu-id="20454-139">All meetings would be rescheduled once there are no operations in  *Pending*  or *In-Progress*  state.</span></span>

```PowerShell
    Get-CsMeetingMigrationStatus -SummaryOnly
```

## <a name="steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge"></a><span data-ttu-id="20454-140">会議ブリッジのサービス電話番号の割り当てを解除する手順</span><span class="sxs-lookup"><span data-stu-id="20454-140">Steps when you are unassigning a service phone number for a conferencing bridge</span></span>


<span data-ttu-id="20454-141">会議ブリッジから電話番号の割り当てを解除すると、ユーザーは、その電話番号を使用して会議に参加できなくなります。</span><span class="sxs-lookup"><span data-stu-id="20454-141">When you unassign a phone number from a conferencing bridge, users won't be able to join any meetings using that phone number anymore.</span></span> <span data-ttu-id="20454-142">電話番号は変更中なので、電話番号が既定の番号 (存在する場合) である可能性があるすべてのユーザーを更新し、電話番号が電話会議ブリッジから割り当て解除される前に、既存の会議出席招待を更新することが重要です。</span><span class="sxs-lookup"><span data-stu-id="20454-142">Because the phone number is changing, it's important to update all users who could have a phone number as their default number (if any) and to update their existing meeting invites before the phone number is unassigned from the audio conferencing bridge.</span></span>

<span data-ttu-id="20454-143">ユーザーと会議を更新せずに電話番号が削除された場合、既存の会議出席許可には、会議に参加するために機能しない電話番号が含まれている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="20454-143">If the phone number is removed without updating the users and their meetings, their existing meeting invites could contain a phone number that won't work for joining their meetings.</span></span>

<span data-ttu-id="20454-144">最初の 3 つの手順では、最初の手順を開始Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="20454-144">For the first three steps, you will need to start Windows PowerShell.</span></span> <span data-ttu-id="20454-145">これを行う方法を確認するには、[管理方法を知りたい] をクリック[Windows PowerShell。](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#about-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="20454-145">To see how to do this, click [Want to know how to manage with Windows PowerShell?](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#about-windows-powershell)</span></span>

### <a name="step-1---update-users-who-have-the-phone-number-to-be-unassigned-as-one-of-their-default-numbers"></a><span data-ttu-id="20454-146">手順 1 - 既定の番号の 1 つとして割り当て解除する電話番号を持つユーザーを更新する</span><span class="sxs-lookup"><span data-stu-id="20454-146">Step 1 - Update users who have the phone number to be unassigned as one of their default numbers</span></span>

<span data-ttu-id="20454-147">既定の番号として割り当てられていない番号を持つすべてのユーザーの既定の有料電話番号または無料電話番号を置き換え、会議のスケジュールを変更するプロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="20454-147">Replace the default toll or toll-free number for all users who have the number to be unassigned as a default number and start the process of rescheduling their meetings.</span></span> <span data-ttu-id="20454-148">これを行うには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="20454-148">To do this, run the following command:</span></span>

```PowerShell
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```
 > [!IMPORTANT] 
 ><span data-ttu-id="20454-149">また、管理センターで既定の有料または無料のユーザー数Microsoft Teams変更できます。</span><span class="sxs-lookup"><span data-stu-id="20454-149">You can also change the default toll or toll-free number of users in the Microsoft Teams admin center.</span></span> <span data-ttu-id="20454-150">ただし、会議のスケジュールが自動的に変更されるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="20454-150">However, this won't automatically reschedule their meetings.</span></span> 
 
 <span data-ttu-id="20454-151">詳細については、「Microsoft Teams[](set-the-phone-numbers-included-on-invites-in-teams.md)の招待に含まれる電話番号を設定する」または「Microsoft Teams Online の招待に含まれる電話番号を[設定する」をSkype for Businessしてください](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)。</span><span class="sxs-lookup"><span data-stu-id="20454-151">For additional information, see [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) or [Set the phone numbers included on invites in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites).</span></span>

  > [!NOTE]
  > <span data-ttu-id="20454-152">組織の規模によっては、完了に時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="20454-152">Depending on the size of your organization, this could take some time to complete.</span></span>

### <a name="step-2---view-meeting-migration-status-using-windows-powershell"></a><span data-ttu-id="20454-153">手順 2 - 会議の移行の状態を表示するには、Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="20454-153">Step 2 - View meeting migration status using Windows PowerShell</span></span>

<span data-ttu-id="20454-154">[保留中] または [進行中] 状態の操作がない場合は、すべての会議 *のスケジュールが変更* されます。</span><span class="sxs-lookup"><span data-stu-id="20454-154">All meetings will be rescheduled once there are no operations in *Pending* or *In-Progress* state.</span></span>

```PowerShell
Get-CsMeetingMigrationStatus -SummaryOnly
```

<span data-ttu-id="20454-155">Meeting Migration Service の詳細については、「Meeting [Migration Service (MMS) の設定」を参照してください](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)。</span><span class="sxs-lookup"><span data-stu-id="20454-155">For more information about the Meeting Migration Service, see [Setting up the Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span></span>
  
### <a name="step-3---unassign-the-old-phone-number-from-the-audio-conferencing-bridge"></a><span data-ttu-id="20454-156">手順 3 - 電話会議ブリッジから古い電話番号の割り当てを解除する</span><span class="sxs-lookup"><span data-stu-id="20454-156">Step 3 - Unassign the old phone number from the audio conferencing bridge</span></span>

<span data-ttu-id="20454-157">![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**</span><span class="sxs-lookup"><span data-stu-id="20454-157">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="20454-158">In the left navigation, go to **Voice** > **Phone numbers**.</span><span class="sxs-lookup"><span data-stu-id="20454-158">In the left navigation, go to **Voice** > **Phone numbers**.</span></span>

2. <span data-ttu-id="20454-159">電話番号が無料電話番号の場合は、一覧から電話番号を選択し、[リリース] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="20454-159">If the phone number is a toll-free number, select the phone number from the list, and click **Release**.</span></span> <span data-ttu-id="20454-160">電話番号が有料電話番号の場合は [、Microsoft](/microsoft-365/admin/contact-support-for-business-products) サポートに問い合わせ、電話番号を割り当て解除してください。</span><span class="sxs-lookup"><span data-stu-id="20454-160">If the phone number is a toll number, please contact [Microsoft support](/microsoft-365/admin/contact-support-for-business-products) to have the phone number unassigned.</span></span>

3. <span data-ttu-id="20454-161">電話番号が無料電話番号の場合は、確認ウィンドウで **[は** い] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="20454-161">If the phone number is a toll-free number, click **Yes** in the confirmation window.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="20454-162">電話番号が電話会議ブリッジから割り当て解除された後は、ユーザーが新規または既存の会議に参加するために電話番号を使用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="20454-162">After a phone number is unassigned from an audio conferencing bridge, the phone number will no longer be available for users to join new or existing meetings.</span></span>

### <a name="save-time-and-automate"></a><span data-ttu-id="20454-163">時間を節約して自動化する</span><span class="sxs-lookup"><span data-stu-id="20454-163">Save time and automate</span></span>

<span data-ttu-id="20454-164">このプロセスを自動化して時間を節約するには [、Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) コマンドレットまたは **Set-CsOnlineDialInConferencingUserDefaultNumber** コマンドレットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="20454-164">To save time by automating this process, you can use the [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) or the **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlets.</span></span>

- <span data-ttu-id="20454-165">特定ユーザーのデフォルトの有料または無料電話番号を変更するには、[[Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser)] コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="20454-165">Use the [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) cmdlet to change the default toll or toll-free number for specific users.</span></span>

  - <span data-ttu-id="20454-166">ユーザーのデフォルトの無料電話番号を変更するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="20454-166">To change the default toll-free number for a user, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   80045551234
  ```

- <span data-ttu-id="20454-167">ユーザーの元の既定の電話番号または所在地に基づいて既定の有料または無料電話番号を変更するには、 **Set-CsOnlineDialInConferencingUserDefaultNumber** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="20454-167">Use the **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlet to change the default toll or toll-free number of users based on their original default number or their location.</span></span>

    > [!NOTE]
    > <span data-ttu-id="20454-168">BridgeID を探すには、 **Get-CsOnlineDialInConferencingBridge** を使用します。</span><span class="sxs-lookup"><span data-stu-id="20454-168">To find the BridgeID, use the **Get-CsOnlineDialInConferencingBridge**.</span></span>

  - <span data-ttu-id="20454-169">1 人を含めずにすべてのユーザーの既定の無料電話番号を 8005551234 に設定するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="20454-169">To set the default toll-free number for all users without one to 8005551234, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```

  - <span data-ttu-id="20454-170">既定のフリーダイヤル番号として 8005551234 を持つすべてのユーザーの既定のフリーダイヤル番号を 8005551239 に変更し、会議のスケジュールを自動的に変更するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="20454-170">To change the default toll-free number of all users that have 8005551234 as their default toll-free number to 8005551239 and automatically reschedule their meetings, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber 8005551234 -ToNumber 8005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

  - <span data-ttu-id="20454-171">米国内のすべてのユーザーの既定の無料電話番号を 8005551234 に設定し、会議のスケジュールを自動的に変更するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="20454-171">To set the default toll-free number of all users located in the U.S. to 8005551234 and automatically reschedule their meetings, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

    > [!NOTE]
    > <span data-ttu-id="20454-172">上記で使用する場所は、管理センターで設定されているユーザーの連絡先情報と一Microsoft 365必要があります。</span><span class="sxs-lookup"><span data-stu-id="20454-172">The location that is used above needs to match the contact information of user(s) that is set in the Microsoft 365 admin center.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="20454-173">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="20454-173">Troubleshooting</span></span>

<span data-ttu-id="20454-174">**[割り当て解除] ボタンを使用できない**</span><span class="sxs-lookup"><span data-stu-id="20454-174">**Unassign button isn't available**</span></span>

<span data-ttu-id="20454-175">番号の割り当てを解除するが、ボタンを使用できない場合、その上にマウス ポインターを置くと、サポートに問い合わせにリダイレクトされ、"既定または共有の番号はブリッジから割り当て解除できません。 _専用の有料電話番号の割り当てを解除するには、サポートにお問い合わせください。_</span><span class="sxs-lookup"><span data-stu-id="20454-175">You want to Unassign a number but the button isn't available, and if while hovering over it, you are redirected to contact Support with the following message _"Default or shared numbers can´t be unassigned from the bridge. To unassign dedicated toll numbers, please contact support._".</span></span>

<span data-ttu-id="20454-176">ブリッジの詳細を取得するには、次の Powershell を実行します。</span><span class="sxs-lookup"><span data-stu-id="20454-176">To obtain more information about the bridge(s), run the following Powershell :</span></span>
```PowerShell
Get-CsOnlineDialInConferencingBridge -Name "Conference Bridge"
```

<span data-ttu-id="20454-177">結果には、Identity、Name、Region などの他の情報を除き、DefaultServiceNumber も含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="20454-177">The result, aside other information like Identity, Name and Region, should also contain the DefaultServiceNumber.</span></span>

<span data-ttu-id="20454-178">**割** り当てを解除する例、DefaultServiceNumber "8005551234"</span><span class="sxs-lookup"><span data-stu-id="20454-178">**Example**, to unassign, the DefaultServiceNumber "8005551234"</span></span>
```PowerShell
Unregister-CsOnlineDialInConferencingServiceNumber -BridgeName "Conference Bridge" -RemoveDefaultServiceNumber 8005551234 
```

## <a name="about-windows-powershell"></a><span data-ttu-id="20454-179">概要 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="20454-179">About Windows PowerShell</span></span>

<span data-ttu-id="20454-180">このWindows PowerShell、ユーザーの管理、ユーザーの操作、または許可されていない操作を管理できます。</span><span class="sxs-lookup"><span data-stu-id="20454-180">With Windows PowerShell you can manage users and what they are or are not allowed to do.</span></span> <span data-ttu-id="20454-181">Windows PowerShell 1 つの管理ポイントを使用して Microsoft 365 または Office 365 および Skype for Business Online を管理し、毎日の作業を簡略化できます。特に、複数のタスクを実行する必要がある場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="20454-181">Windows PowerShell  can help you manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, especially when you've got multiple tasks to do.</span></span> <span data-ttu-id="20454-182">Windows PowerShell の使用を開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="20454-182">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="20454-183">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="20454-183">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [<span data-ttu-id="20454-184">Office 365 PowerShell を使用する必要がある理由</span><span class="sxs-lookup"><span data-stu-id="20454-184">Why you need to use Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

<span data-ttu-id="20454-185">Windows PowerShell多くのユーザーに対して一度に設定を変更する場合など、Microsoft 365 管理センターを使用する場合に限って、速度、シンプルさ、生産性に多くの利点があります。</span><span class="sxs-lookup"><span data-stu-id="20454-185">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="20454-186">次のトピックでこれらの利点について説明します。</span><span class="sxs-lookup"><span data-stu-id="20454-186">Learn about these advantages in the following topics:</span></span>

  - <span data-ttu-id="20454-187">[アプリを使用してMicrosoft 365またはOffice 365を管理Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="20454-187">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>

  - [<span data-ttu-id="20454-188">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="20454-188">Using Windows PowerShell to manage Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [<span data-ttu-id="20454-189">Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行</span><span class="sxs-lookup"><span data-stu-id="20454-189">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a><span data-ttu-id="20454-190">関連トピック</span><span class="sxs-lookup"><span data-stu-id="20454-190">Related topics</span></span>
[<span data-ttu-id="20454-191">電話会議ブリッジの設定を変更する</span><span class="sxs-lookup"><span data-stu-id="20454-191">Change the settings for an Audio Conferencing bridge</span></span>](change-the-settings-for-an-audio-conferencing-bridge.md)