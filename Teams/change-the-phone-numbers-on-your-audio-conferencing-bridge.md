---
title: 電話会議ブリッジの電話番号を変更する
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
description: 電話会議ライセンスを購入するときに、Microsoft は組織の電話会議ブリッジをホストしています。 電話会議ブリッジは、さまざまな場所からダイヤルイン電話番号を提供します。これにより、会議の開催者と参加者は、電話を使って Skype for Business または Microsoft Teams の会議に参加できるようになります。
ms.openlocfilehash: 54662b34f5b8b1f56aceffb2294801a485bc26ae
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41825205"
---
# <a name="change-the-phone-numbers-on-your-audio-conferencing-bridge"></a><span data-ttu-id="ef2ae-104">電話会議ブリッジの電話番号を変更する</span><span class="sxs-lookup"><span data-stu-id="ef2ae-104">Change the phone numbers on your Audio Conferencing bridge</span></span>

<span data-ttu-id="ef2ae-105">**電話会議**ライセンスを購入するときに、Microsoft は組織の電話会議ブリッジをホストしています。</span><span class="sxs-lookup"><span data-stu-id="ef2ae-105">When you buy **Audio Conferencing** licenses, Microsoft is hosting your audio conferencing bridge for your organization.</span></span> <span data-ttu-id="ef2ae-106">電話会議ブリッジは、さまざまな場所からダイヤルイン電話番号を提供します。これにより、会議の開催者と参加者は、電話を使って Skype for Business または Microsoft Teams の会議に参加することができます。</span><span class="sxs-lookup"><span data-stu-id="ef2ae-106">The audio conferencing bridge gives out dial-in phone numbers from different locations so that meeting organizers and participants can use them to join Skype for Business or Microsoft Teams meetings using a phone.</span></span>
  
<span data-ttu-id="ef2ae-107">会議ブリッジに既に割り当てられている電話番号に加えて、他の場所から[サービス番号](/microsoftteams/getting-service-phone-numbers)(電話会議に使用されている有料または無料の電話番号) を取得して、ユーザーのために範囲を広げることができます。</span><span class="sxs-lookup"><span data-stu-id="ef2ae-107">In addition to the phone numbers already assigned to your conferencing bridge, you can [get additional service numbers](/microsoftteams/getting-service-phone-numbers) (toll and toll-free numbers used for audio conferencing) from other locations, and then assign them to the conferencing bridge so you can expand coverage for your users.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ef2ae-108">会議ブリッジの電話番号の割り当て/割り当て解除を行うには、電話番号は「*サービス*」番号でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="ef2ae-108">To be able to assign/unassign a phone number for a conferencing bridge, the phone number must be a '*service*' number.</span></span> <span data-ttu-id="ef2ae-109">番号の種類は、従来のポータルで [ > **電話番号** **] に移動**し、[番号の**種類**] 列で確認できます。</span><span class="sxs-lookup"><span data-stu-id="ef2ae-109">You can see the type of number it is by navigating to **Voice** > **Phone numbers** in the legacy portal and looking in the **Number Type** column.</span></span> <span data-ttu-id="ef2ae-110">ユーザーが無料電話番号を使用してブリッジにダイヤルインするためには、Office 365 通信クレジットを最初に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef2ae-110">Office 365 Communications Credits must be set up first in order for users to dial into the bridge on a toll free number.</span></span>

## <a name="steps-when-you-are-assigning-a-new-service-phone-number-to-your-conference-bridge"></a><span data-ttu-id="ef2ae-111">新しいサービス電話番号を電話会議ブリッジに割り当てるときの手順</span><span class="sxs-lookup"><span data-stu-id="ef2ae-111">Steps when you are assigning a new service phone number to your conference bridge</span></span>

### <a name="step-1---assign-the-new-phone-number-to-your-audio-conferencing-bridge"></a><span data-ttu-id="ef2ae-112">手順 1-新しい電話番号を電話会議ブリッジに割り当てる</span><span class="sxs-lookup"><span data-stu-id="ef2ae-112">Step 1 - Assign the new phone number to your audio conferencing bridge</span></span>

1. <span data-ttu-id="ef2ae-113">職場のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="ef2ae-113">Sign in to Office 365 with your work account.</span></span>

2. <span data-ttu-id="ef2ae-114">**Microsoft 365 管理センター** > **管理** > **Teams & Skype** > **従来のポータル** > **ボイス** > **電話番号**に移動します。</span><span class="sxs-lookup"><span data-stu-id="ef2ae-114">Go to **Microsoft 365 admin center** > **Admin centers** > **Teams & Skype** > **Legacy portal** > **Voice** > **Phone numbers**.</span></span>

3. <span data-ttu-id="ef2ae-115">リストから電話番号を選び、操作ウィンドウで [**割り当て**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ef2ae-115">Select the phone number from the list, and in the Action pane, click **Assign**.</span></span>

4. <span data-ttu-id="ef2ae-116">[**割り当て**] ページで [**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ef2ae-116">On the **Assign** page, click **Save**.</span></span>

### <a name="step-2---change-the-default-phone-number-of-your-conference-bridge-optional"></a><span data-ttu-id="ef2ae-117">手順 2-電話会議ブリッジの既定の電話番号を変更する (オプション)</span><span class="sxs-lookup"><span data-stu-id="ef2ae-117">Step 2 - Change the default phone number of your conference bridge (optional)</span></span>

<span data-ttu-id="ef2ae-118">会議ブリッジの既定の電話番号は、発信時に会議内の参加者または開催者によって発信される場合に使用される発信者番号を定義します。</span><span class="sxs-lookup"><span data-stu-id="ef2ae-118">The default phone number of your conference bridge defines the caller ID that will be used when an outbound call is placed by a participant or the organizer from within a meeting.</span></span>

<span data-ttu-id="ef2ae-119">電話会議ブリッジの既定の番号として設定できるのは、サービスの有料電話番号だけです。**サービスの無料電話番号を電話会議ブリッジの既定の番号として設定することはできません**。</span><span class="sxs-lookup"><span data-stu-id="ef2ae-119">Only a service toll number can be set as the default number for your conferencing bridge; **service toll-free numbers can't be set as the default number of your conferencing bridge**.</span></span> <span data-ttu-id="ef2ae-120">サービスの有料電話番号を割り当てていて、電話会議ブリッジの新しい既定の番号として設定したい場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="ef2ae-120">If you are assigning a service toll number and you would like to set it as the new default number for your audio conferencing bridge, perform these steps:</span></span>

1. <span data-ttu-id="ef2ae-121">職場のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="ef2ae-121">Sign in to Office 365 with your work account.</span></span>

2. <span data-ttu-id="ef2ae-122">**Microsoft 365 管理センター** > の**管理** > センター**チーム & Skype** > **会議** > **会議ブリッジ**に移動します。</span><span class="sxs-lookup"><span data-stu-id="ef2ae-122">Go to **Microsoft 365 admin center** > **Admin centers** > **Teams & Skype** > **Meetings** > **Conference Bridges**.</span></span>

3. <span data-ttu-id="ef2ae-123">既定として構成するサービスの有料電話番号を強調表示します。</span><span class="sxs-lookup"><span data-stu-id="ef2ae-123">Highlight the service toll number that you want to configure as the default.</span></span>

4. <span data-ttu-id="ef2ae-124">[**既定に設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ef2ae-124">Select **Set as default**.</span></span>
 
### <a name="step-3---change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users-optional"></a><span data-ttu-id="ef2ae-125">手順 3-ユーザーの会議出席依頼に含まれている既定の電話番号を変更する (オプション)</span><span class="sxs-lookup"><span data-stu-id="ef2ae-125">Step 3 - Change the default phone numbers that are included in the meeting invites of users (optional)</span></span>

<span data-ttu-id="ef2ae-126">ユーザーの既定の電話番号は、会議のスケジュール時に会議出席依頼に記載されている電話番号です。</span><span class="sxs-lookup"><span data-stu-id="ef2ae-126">The default phone numbers of a user are the ones that are included on their meeting invites when they schedule a meeting.</span></span> <span data-ttu-id="ef2ae-127">新しいユーザーに対して defaul 電話番号を割り当てる方法を含め、詳細については、「 [Microsoft Teams の招待に含まれる電話番号を設定](set-the-phone-numbers-included-on-invites-in-teams.md)する」または「 [Skype for business Online の招待に含まれる電話番号を設定](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ef2ae-127">For more information, including how the defaul phone numbers are assigned for new users, see [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) or [Set the phone numbers included on invites in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites).</span></span>
  
1. <span data-ttu-id="ef2ae-128">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="ef2ae-128">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="ef2ae-129">**Microsoft 365 管理センター** > **管理** > センターの**チーム & Skype** > **従来のポータル** > **電話会議** > **ユーザー**に移動して、リストからユーザーを選びます。</span><span class="sxs-lookup"><span data-stu-id="ef2ae-129">Go to the **Microsoft 365 admin center** > **Admin centers** > **Teams & Skype** > **Legacy portal** > **Audio conferencing** > **Users**, and select the users on the list.</span></span>

3. <span data-ttu-id="ef2ae-130">操作ウィンドウで [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ef2ae-130">Click **Edit** in the action pane.</span></span>

4. <span data-ttu-id="ef2ae-131">[**既定の有料電話番号**] または [**既定の無料電話番号**] の下で、一覧から番号を選び、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ef2ae-131">Under **Default toll number** or **Default toll-free number**, select the number in the list and click **Save**.</span></span>

<span data-ttu-id="ef2ae-132">変更が保存されると、次回新しい会議をスケジュールするときに新しい既定の電話番号が開催者の会議の出席依頼に含まれます。</span><span class="sxs-lookup"><span data-stu-id="ef2ae-132">After the changes have been saved, the new default phone numbers will be included on the meeting invites of organizers the next time they schedule a new meeting.</span></span>

### <a name="step-4---update-existing-meeting-invites-of-users-using-the-meeting-migration-service-optional"></a><span data-ttu-id="ef2ae-133">手順 4-会議移行サービスを使用して、ユーザーの既存の会議出席依頼を更新する (オプション)</span><span class="sxs-lookup"><span data-stu-id="ef2ae-133">Step 4 - Update existing meeting invites of users using the Meeting Migration Service (optional)</span></span>

<span data-ttu-id="ef2ae-134">次の2つの手順については、Windows PowerShell を起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef2ae-134">For the next two steps, you will need to start Windows PowerShell.</span></span>
  
<span data-ttu-id="ef2ae-135">一部またはすべてのユーザーに対して会議の出席依頼に記載されている既定の電話番号を更新した場合、必要に応じて、組織内のユーザーに既に送信された会議出席依頼を更新して、既定の電話番号を変更することができます。会議移行サービス。</span><span class="sxs-lookup"><span data-stu-id="ef2ae-135">If you updated the default phone numbers that are inlcuded in the meeting invites for some or all of your users, you can optionally update meeting invites that were already sent to users in your organization before their default phone numbers were changed using the Meeting Migration Service.</span></span> <span data-ttu-id="ef2ae-136">詳細については、「[会議移行サービス (MMS) の](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)セットアップ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ef2ae-136">For additional information, see [Setting up the Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span></span>
  
- <span data-ttu-id="ef2ae-137">手順2で既定の電話番号を変更したユーザーに対して、会議移行サービス (MMS) を実行します。</span><span class="sxs-lookup"><span data-stu-id="ef2ae-137">Run the Meeting Migration Service (MMS) for the users who had their default phone numbers changed in Step 2.</span></span> <span data-ttu-id="ef2ae-138">これを行うには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="ef2ae-138">To do this, run the following command:</span></span>

```PowerShell
    Start-CsExMeetingMigration user@contoso.com
```

- <span data-ttu-id="ef2ae-139">会議の移行状態を表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="ef2ae-139">You can also view the meeting migration status.</span></span> <span data-ttu-id="ef2ae-140">[*保留中*] または *[進行*中] の状態で操作が行われなくなると、すべての会議がスケジュールされます。</span><span class="sxs-lookup"><span data-stu-id="ef2ae-140">All meetings would be rescheduled once there are no operations in  *Pending*  or *In-Progress*  state.</span></span>

```PowerShell
    Get-CsMeetingMigrationStatus -SummaryOnly
```

## <a name="steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge"></a><span data-ttu-id="ef2ae-141">会議ブリッジのサービスの電話番号の割り当てを解除する場合の手順</span><span class="sxs-lookup"><span data-stu-id="ef2ae-141">Steps when you are unassigning a service phone number for a conferencing bridge</span></span>


<span data-ttu-id="ef2ae-142">会議ブリッジから電話番号の割り当てを解除すると、ユーザーはその電話番号を使って会議に参加できなくなります。</span><span class="sxs-lookup"><span data-stu-id="ef2ae-142">When you unassign a phone number from a conferencing bridge, users won't be able to join any meetings using that phone number anymore.</span></span> <span data-ttu-id="ef2ae-143">電話番号は変更されているため、電話会議ブリッジから電話番号が割り当てられていない場合は、電話番号を既定の番号として (存在する場合) 更新して、既存の会議出席依頼を更新することが重要です。</span><span class="sxs-lookup"><span data-stu-id="ef2ae-143">Because the phone number is changing, it's important to update all users who could have a phone number as their default number (if any) and to update their existing meeting invites before the phone number is unassigned from the audio conferencing bridge.</span></span>

<span data-ttu-id="ef2ae-144">ユーザーとその会議を更新せずに電話番号が削除された場合、既存の会議出席依頼には、会議に参加するために使用できない電話番号が含まれている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ef2ae-144">If the phone number is removed without updating the users and their meetings, their existing meeting invites could contain a phone number that won't work for joining their meetings.</span></span>

<span data-ttu-id="ef2ae-145">最初の3つの手順では、Windows PowerShell を起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef2ae-145">For the first three steps, you will need to start Windows PowerShell.</span></span> <span data-ttu-id="ef2ae-146">この方法については、「 [Windows PowerShell で管理する方法](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#bkPowerShell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ef2ae-146">To see how to do this, click [Want to know how to manage with Windows PowerShell?](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#bkPowerShell)</span></span>

### <a name="step-1---update-users-who-have-the-phone-number-to-be-unassigned-as-one-of-their-default-numbers"></a><span data-ttu-id="ef2ae-147">手順 1-電話番号が既定の番号の1つとして割り当てられていないユーザーを更新する</span><span class="sxs-lookup"><span data-stu-id="ef2ae-147">Step 1 - Update users who have the phone number to be unassigned as one of their default numbers</span></span>

<span data-ttu-id="ef2ae-148">番号が既定の番号として割り当てられていないすべてのユーザーの既定の有料電話番号または無料電話番号を変更して、会議の再スケジュール処理を開始します。</span><span class="sxs-lookup"><span data-stu-id="ef2ae-148">Replace the default toll or toll-free number for all users who have the number to be unassigned as a default number and start the process of rescheduling their meetings.</span></span> <span data-ttu-id="ef2ae-149">これを行うには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="ef2ae-149">To do this, run the following command:</span></span>

```PowerShell
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```
 > [!IMPORTANT] 
 ><span data-ttu-id="ef2ae-150">Skype for Business 管理センターでは、既定の有料または無料のユーザー数を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="ef2ae-150">You can also change the default toll or toll-free number of users in the Skype for Business admin center.</span></span> <span data-ttu-id="ef2ae-151">ただし、会議のスケジュールが自動的に再設定されることはありません。</span><span class="sxs-lookup"><span data-stu-id="ef2ae-151">However, this won't automatically reschedule their meetings.</span></span> 
 
 <span data-ttu-id="ef2ae-152">詳細については、「 [Microsoft Teams の招待に含まれる電話番号を設定する](set-the-phone-numbers-included-on-invites-in-teams.md)」または「 [Skype for business Online の招待に含まれる電話番号を設定](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ef2ae-152">For additional information, see [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) or [Set the phone numbers included on invites in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites).</span></span>

  > [!NOTE]
  > <span data-ttu-id="ef2ae-153">組織の規模によっては、完了までに少し時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="ef2ae-153">Depending on the size of your organization, this could take some time to complete.</span></span>

### <a name="step-2---view-meeting-migration-status-using-windows-powershell"></a><span data-ttu-id="ef2ae-154">手順 2-Windows PowerShell を使用して会議の移行状態を表示する</span><span class="sxs-lookup"><span data-stu-id="ef2ae-154">Step 2 - View meeting migration status using Windows PowerShell</span></span>

<span data-ttu-id="ef2ae-155">[*保留中*] または *[進行*中] の状態で操作が行われなくなると、すべての会議がスケジュールされます。</span><span class="sxs-lookup"><span data-stu-id="ef2ae-155">All meetings will be rescheduled once there are no operations in *Pending* or *In-Progress* state.</span></span>

```PowerShell
Get-CsMeetingMigrationStatus -SummaryOnly
```

<span data-ttu-id="ef2ae-156">会議移行サービスの詳細については、「[会議移行サービス (MMS) の](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)セットアップ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ef2ae-156">For more information about the Meeting Migration Service, see [Setting up the Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span></span>
  
### <a name="step-3---unassign-the-old-phone-number-from-the-audio-conferencing-bridge"></a><span data-ttu-id="ef2ae-157">手順 3-古い電話番号を電話会議ブリッジから割り当て解除する</span><span class="sxs-lookup"><span data-stu-id="ef2ae-157">Step 3 - Unassign the old phone number from the audio conferencing bridge</span></span>

1. <span data-ttu-id="ef2ae-158">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="ef2ae-158">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="ef2ae-159">**Microsoft 365 管理センター** > **管理** > **Teams & Skype** > **従来のポータル** > **ボイス** > **電話番号**に移動します。</span><span class="sxs-lookup"><span data-stu-id="ef2ae-159">Go to the **Microsoft 365 admin center** > **Admin centers** > **Teams & Skype** > **Legacy portal** > **Voice** > **Phone numbers**.</span></span>

3. <span data-ttu-id="ef2ae-160">電話番号がフリーダイヤル番号の場合は、一覧から電話番号を選び、操作ウィンドウで [**割り当てを解除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ef2ae-160">If the phone number is a toll-free number, select the phone number from the list, and in the Action pane, click **Unassign**.</span></span> <span data-ttu-id="ef2ae-161">電話番号が有料番号の場合は、 [Microsoft サポート](https://go.microsoft.com/fwlink/?linkid=2091806)に連絡して電話番号を割り当てていないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="ef2ae-161">If the phone number is a toll-number, please contact [Microsoft support](https://go.microsoft.com/fwlink/?linkid=2091806) to have the phone number unassigned.</span></span>

4. <span data-ttu-id="ef2ae-162">電話番号が有料 fre 番号の場合は、確認ウィンドウで [**はい]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ef2ae-162">If the phone number is a toll-fre number, click **Yes** in the confirmation window.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="ef2ae-163">電話会議ブリッジから電話番号の割り当てを解除すると、ユーザーはその電話番号を使用して新規または既存の会議に参加できなくなります。</span><span class="sxs-lookup"><span data-stu-id="ef2ae-163">After a phone number is unassigned from an audio conferencing bridge, the phone number will no longer be available for users to join new or existing meetings.</span></span>

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="ef2ae-164">Windows PowerShell での管理方法について</span><span class="sxs-lookup"><span data-stu-id="ef2ae-164">Want to know how to manage with Windows PowerShell?</span></span>
<span data-ttu-id="ef2ae-165"><a name="bkPowerShell"> </a></span><span class="sxs-lookup"><span data-stu-id="ef2ae-165"><a name="bkPowerShell"> </a></span></span>

### <a name="to-verify-that-windows-powershell-is-ready-to-go"></a><span data-ttu-id="ef2ae-166">Windows PowerShell の準備が整っていることを確認するには</span><span class="sxs-lookup"><span data-stu-id="ef2ae-166">To verify that Windows PowerShell is ready to go</span></span>

 <span data-ttu-id="ef2ae-167">次の手順では、Windows PowerShell バージョン3.0 以降を実行していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ef2ae-167">These steps check that you are running Windows PowerShell version 3.0 or higher.</span></span>

1. <span data-ttu-id="ef2ae-168">「**スタートメニュー** > **Windows PowerShell**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="ef2ae-168">Type **Start Menu** > **Windows PowerShell**.</span></span>

2. <span data-ttu-id="ef2ae-169">[ **Windows PowerShell** ] ウィンドウで「 _Get Host_ 」と入力して、バージョンを確認します。</span><span class="sxs-lookup"><span data-stu-id="ef2ae-169">Type _Get-Host_ in the **Windows PowerShell** window to check the version.</span></span>

3. <span data-ttu-id="ef2ae-170">バージョン 3.0 以降を使用していない場合は、Windows PowerShell の更新プログラムをダウンロードおよびインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef2ae-170">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="ef2ae-171">Windows PowerShell をバージョン4.0 にダウンロードして更新するには、「 [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ef2ae-171">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span>
<span data-ttu-id="ef2ae-172">メッセージが表示されたら、コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="ef2ae-172">Restart your computer when you are prompted.</span></span>

4. <span data-ttu-id="ef2ae-173">また、skype for business online に接続するリモート Windows PowerShell セッションを作成できるようにする、Skype for Business Online 用の Windows PowerShell モジュールをインストールする必要もあります。</span><span class="sxs-lookup"><span data-stu-id="ef2ae-173">You also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="ef2ae-174">このモジュールは、64ビットのコンピューターでのみサポートされ、 [Skype For Business Online 用の Windows PowerShell モジュール](https://go.microsoft.com/fwlink/?LinkId=294688)で Microsoft ダウンロードセンターからダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="ef2ae-174">This module is supported only on 64-bit computers and can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span></span>
<span data-ttu-id="ef2ae-175">メッセージが表示されたら、コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="ef2ae-175">Restart your computer if you are prompted.</span></span>

<span data-ttu-id="ef2ae-176">詳細については、「[単一の Windows PowerShell ウィンドウですべての Office 365 サービスに接続する](https://technet.microsoft.com/library/dn568015.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ef2ae-176">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>

### <a name="to-start-windows-powershell"></a><span data-ttu-id="ef2ae-177">Windows PowerShell を起動するには</span><span class="sxs-lookup"><span data-stu-id="ef2ae-177">To start Windows PowerShell</span></span>

 <span data-ttu-id="ef2ae-178">**Windows PowerShell セッションを開始する**</span><span class="sxs-lookup"><span data-stu-id="ef2ae-178">**Start a Windows PowerShell session**</span></span>

1. <span data-ttu-id="ef2ae-179">From the **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="ef2ae-179">From the **Start Menu** > **Windows PowerShell**.</span></span>

2. <span data-ttu-id="ef2ae-180">[ **Windows PowerShell**] ウィンドウで、次を実行して、Office 365 の組織に接続します。</span><span class="sxs-lookup"><span data-stu-id="ef2ae-180">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>

>
  ```PowerShell
    Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

> [!NOTE]
> <span data-ttu-id="ef2ae-181">Skype for Business Online Windows PowerShell モジュールを初めて使用するときに、 **Import-Module** コマンドを実行するだけです。</span><span class="sxs-lookup"><span data-stu-id="ef2ae-181">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>
<span data-ttu-id="ef2ae-182">Windows PowerShell の起動の詳細については、「[単一の Windows powershell ウィンドウですべての Office 365 サービスに接続](https://technet.microsoft.com/library/dn568015.aspx)する」または「 [windows powershell を使用して Skype for business Online に](https://technet.microsoft.com/library/dn362795%28v=ocs.15%29.aspx)接続する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ef2ae-182">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/library/dn362795%28v=ocs.15%29.aspx).</span></span>

### <a name="save-time-and-automate"></a><span data-ttu-id="ef2ae-183">時間を節約して自動化する</span><span class="sxs-lookup"><span data-stu-id="ef2ae-183">Save time and automate</span></span>

<span data-ttu-id="ef2ae-184">このプロセスを自動化することで時間を節約するために、 [get-csonlinedialinconferencinguser](https://go.microsoft.com/fwlink/?LinkId=617688)または**set-csonlinedialinconferencinguserdefaultnumber**コマンドレットを使うことができます。</span><span class="sxs-lookup"><span data-stu-id="ef2ae-184">To save time by automating this process, you can use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) or the **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlets.</span></span>

- <span data-ttu-id="ef2ae-185">特定ユーザーのデフォルトの有料または無料電話番号を変更するには、[[Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688)] コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="ef2ae-185">Use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) cmdlet to change the default toll or toll-free number for specific users.</span></span>

  - <span data-ttu-id="ef2ae-186">ユーザーのデフォルトの無料電話番号を変更するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="ef2ae-186">To change the default toll-free number for a user, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   80045551234
  ```

- <span data-ttu-id="ef2ae-187">ユーザーの元の既定の電話番号または所在地に基づいて既定の有料または無料電話番号を変更するには、 **Set-CsOnlineDialInConferencingUserDefaultNumber** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="ef2ae-187">Use the **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlet to change the default toll or toll-free number of users based on their original default number or their location.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ef2ae-188">BridgeID を探すには、 **Get-CsOnlineDialInConferencingBridge** を使用します。</span><span class="sxs-lookup"><span data-stu-id="ef2ae-188">To find the BridgeID, use the **Get-CsOnlineDialInConferencingBridge**.</span></span>

  - <span data-ttu-id="ef2ae-189">既定の無料電話番号がないすべてのユーザーを8005551234に設定するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="ef2ae-189">To set the default toll-free number for all users without one to 8005551234, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```

  - <span data-ttu-id="ef2ae-190">既定の無料電話番号として8005551234を使用しているすべてのユーザーの既定の無料電話番号を8005551239に変更し、自動的に会議のスケジュールを変更するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="ef2ae-190">To change the default toll-free number of all users that have 8005551234 as their default toll-free number to 8005551239 and automatically reschedule their meetings, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber 8005551234 -ToNumber 8005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

  - <span data-ttu-id="ef2ae-191">米国在住のすべてのユーザーの無料電話番号を8005551234に設定して、自動的に会議のスケジュールを再設定するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="ef2ae-191">To set the default toll-free number of all users located in the U.S. to 8005551234 and automatically reschedule their meetings, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

    > [!NOTE]
    > <span data-ttu-id="ef2ae-192">上で使用されている場所は、Microsoft 365 管理センターで設定されているユーザーの連絡先情報と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef2ae-192">The location that is used above needs to match the contact information of user(s) that is set in the Microsoft 365 admin center.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="ef2ae-193">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="ef2ae-193">Troubleshooting</span></span>

<span data-ttu-id="ef2ae-194">**[割り当て解除] ボタンが淡色表示になっている**</span><span class="sxs-lookup"><span data-stu-id="ef2ae-194">**Unassign button is greyed-out**</span></span>

<span data-ttu-id="ef2ae-195">番号の割り当てを解除したいが、ボタンが灰色表示になっていて、それを超えている場合は、次のメッセージが表示され_ます。 "既定または共有の番号は、ブリッジから割り当て解除することができます。́t専用の有料電話番号の割り当てを解除するには、サポートにお問い合わせください。_</span><span class="sxs-lookup"><span data-stu-id="ef2ae-195">You want to Unassign a number but the button is greyed-out and if while hoovering over it, you are redirected to contact Support with the following message _"Default or shared numbers can´t be unassigned from the bridge. To unassign dedicated toll numbers, please contact support._".</span></span>

<span data-ttu-id="ef2ae-196">ブリッジに関する詳細情報を入手するには、次の Powershell を実行します。</span><span class="sxs-lookup"><span data-stu-id="ef2ae-196">To obtain more information about the bridge(s), run the following Powershell :</span></span>
```PowerShell
Get-CsOnlineDialInConferencingBridge -Name "Conference Bridge"
```

<span data-ttu-id="ef2ae-197">その結果、Id、名前、地域などの他の情報にも、DefaultServiceNumber が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef2ae-197">The result, aside other information like Identity, Name and Region, should also contain the DefaultServiceNumber.</span></span>

<span data-ttu-id="ef2ae-198">割り当て解除する**例**DefaultServiceNumber "8005551234"</span><span class="sxs-lookup"><span data-stu-id="ef2ae-198">**Example**, to unassign, the DefaultServiceNumber "8005551234"</span></span>
```PowerShell
Unregister-CsOnlineDialInConferencingServiceNumber -BridgeName “Conference Bridge” -RemoveDefaultServiceNumber 8005551234 
```

## <a name="about-windows-powershell"></a><span data-ttu-id="ef2ae-199">Windows PowerShell について</span><span class="sxs-lookup"><span data-stu-id="ef2ae-199">About Windows PowerShell</span></span>

<span data-ttu-id="ef2ae-200">Windows PowerShell を使用すると、ユーザーとその内容の管理を行うことができます。また、ユーザーの操作は許可されません。</span><span class="sxs-lookup"><span data-stu-id="ef2ae-200">With Windows PowerShell you can manage users and what they are or are not allowed to do.</span></span> <span data-ttu-id="ef2ae-201">Windows PowerShell を使用すると、1つの管理ポイントを使用して Office 365 および Skype for Business Online を管理することができます。特に、複数のタスクがある場合は、日常業務を簡素化できます。</span><span class="sxs-lookup"><span data-stu-id="ef2ae-201">Windows PowerShell  can help you manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, especially when you've got multiple tasks to do.</span></span> <span data-ttu-id="ef2ae-202">Windows PowerShell の使用を開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ef2ae-202">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="ef2ae-203">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="ef2ae-203">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [<span data-ttu-id="ef2ae-204">Office 365 PowerShell を使用する必要がある理由</span><span class="sxs-lookup"><span data-stu-id="ef2ae-204">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

<span data-ttu-id="ef2ae-205">Windows PowerShell には、多くのユーザーについて同時に設定を変更する場合など、Microsoft 365 管理センターを使用する場合にのみ、速度、シンプルさ、生産性を高めることができます。</span><span class="sxs-lookup"><span data-stu-id="ef2ae-205">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="ef2ae-206">次のトピックでこれらの利点について説明します。</span><span class="sxs-lookup"><span data-stu-id="ef2ae-206">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="ef2ae-207">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="ef2ae-207">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [<span data-ttu-id="ef2ae-208">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="ef2ae-208">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [<span data-ttu-id="ef2ae-209">Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行</span><span class="sxs-lookup"><span data-stu-id="ef2ae-209">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="ef2ae-210">関連トピック</span><span class="sxs-lookup"><span data-stu-id="ef2ae-210">Related topics</span></span>
[<span data-ttu-id="ef2ae-211">電話会議ブリッジの設定を変更する</span><span class="sxs-lookup"><span data-stu-id="ef2ae-211">Change the settings for an Audio Conferencing bridge</span></span>](change-the-settings-for-an-audio-conferencing-bridge.md)
