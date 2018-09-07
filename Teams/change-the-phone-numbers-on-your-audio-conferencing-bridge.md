---
title: 電話会議ブリッジの電話番号を変更する
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6403f6d1-c05a-44ab-a6e0-558000e246f4
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
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 電話会議ライセンスをご購入いただく場合、Microsoft はお客様の組織の電話会議ブリッジ をホストします。電話会議ブリッジではさまざまな場所からダイヤルイン電話番号を受け取るため、会議の開催者や参加者はそれらの番号を使用して電話で Skype for Business 会議または Microsoft Teams 会議に参加できます。
ms.openlocfilehash: 3de53df00f364a4aad6efe416a83e5389cc0b8ef
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23852084"
---
# <a name="change-the-phone-numbers-on-your-audio-conferencing-bridge"></a><span data-ttu-id="cba9d-104">電話会議ブリッジの電話番号を変更する</span><span class="sxs-lookup"><span data-stu-id="cba9d-104">Change the phone numbers on your Audio Conferencing bridge</span></span>

<span data-ttu-id="cba9d-p102">[] **電話会議**ライセンスをご購入いただく場合、Microsoft はお客様の組織の *電話会議ブリッジ*  をホストします。電話会議ブリッジではさまざまな場所からダイヤルイン電話番号を受け取るため、会議の開催者や参加者はそれらの番号を使用して電話で Skype for Business 会議または Microsoft Teams 会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="cba9d-p102">When you buy **Audio Conferencing** licenses, Microsoft is hosting your *audio conferencing bridge*  for your organization. The audio conferencing bridge gives out dial-in phone numbers from different locations so meeting organizers and participants can use them to join Skype for Business or Microsoft Teams meetings using a phone.</span></span>
  
<span data-ttu-id="cba9d-107">[その他のサービス番号を取得](/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers)することをだけでなく、会議用ブリッジに既に割り当てられている電話番号、(有料電話番号とフリー ダイヤルの番号を電話会議に使用される) とその他の場所を会議にそれらをブリッジすることができますユーザーのカバレッジを展開します。</span><span class="sxs-lookup"><span data-stu-id="cba9d-107">In addition to the phone numbers already assigned to your conferencing bridge, you can [get additional service numbers](/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers) (toll and toll-free numbers used for audio conferencing) from other locations and then assign them to the conferencing bridge so you can expand coverage for your users.</span></span>
  
> [!NOTE]
> <span data-ttu-id="cba9d-108">会議用ブリッジ用の電話番号の割り当て/割り当て解除できるようにするには、電話番号は、'*サービス*' の番号をする必要があります。</span><span class="sxs-lookup"><span data-stu-id="cba9d-108">To be able to assign/unassign a phone number for a conferencing bridge, the phone number must be a '*service*' number.</span></span> <span data-ttu-id="cba9d-109">You can see the type of number it is by navigating to **Voice** > **Phone numbers** and looking in the **Number Type** column.</span><span class="sxs-lookup"><span data-stu-id="cba9d-109">You can see the type of number it is by navigating to **Voice** > **Phone numbers** and looking in the **Number Type** column.</span></span> <span data-ttu-id="cba9d-110">Office 365 のコミュニケーション クレジットは、ユーザーが無料電話番号のブリッジにダイヤルインできるように、最初にセットアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="cba9d-110">Office 365 Communications Credits must be set up first in order for users to dial into the bridge on a toll free number.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="steps-when-you-are-assigning-a-new-service-phone-number-to-your-conference-bridge"></a><span data-ttu-id="cba9d-111">新しいサービス用電話番号を会議ブリッジに割り当てるときの手順</span><span class="sxs-lookup"><span data-stu-id="cba9d-111">Steps when you are assigning a new service phone number to your conference bridge</span></span>

### <a name="step-1---assign-the-new-phone-number-to-your-audio-conferencing-bridge"></a><span data-ttu-id="cba9d-112">手順 1 - 新しい電話番号を電話会議ブリッジに割り当てる</span><span class="sxs-lookup"><span data-stu-id="cba9d-112">Step 1 - Assign the new phone number to your audio conferencing bridge</span></span>

1. <span data-ttu-id="cba9d-113">自分の職場のアカウントで Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="cba9d-113">Sign in to Office 365 with your work account.</span></span>

2. <span data-ttu-id="cba9d-114">[**Office 365 管理センター**]  >  [**管理センター**]  >  [**Skype for Business**]  >  [**音声**]  >  [**電話番号**] の順に開きます。</span><span class="sxs-lookup"><span data-stu-id="cba9d-114">Go to the **Office 365 admin center** > **Admin centers** > **Skype for Business** > **Voice** > **Phone numbers**.</span></span>

3. <span data-ttu-id="cba9d-115">リストから電話番号を選択し、[操作] ウィンドウで [ **割り当て**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cba9d-115">Select the phone number from the list, and in the Action pane, click **Assign**.</span></span>

4. <span data-ttu-id="cba9d-116">[ **割り当て**] ページで、[ **保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cba9d-116">On the **Assign** page, click **Save**.</span></span>

    <span data-ttu-id="cba9d-p104">1 つのサービス有料電話番号のみを会議ブリッジの既定の番号として設定できます。 **サービス無料電話番号は会議ブリッジの既定の番号として設定できません** 。サービス有料電話番号を割り当て、それを電話会議ブリッジの新しい既定の番号として設定する場合は、[ **この番号を既定値として使用**] をオンにします。</span><span class="sxs-lookup"><span data-stu-id="cba9d-p104">Only a service toll number can be set as the default number for your conferencing bridge; **service toll-free numbers can't be set as the default number of your conferencing bridge**. If you are assigning a service toll number and you would like to set it as the new default number for your audio conferencing bridge, select **Use this number as the default**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="cba9d-119">新しい電話番号を割り当てた後その番号が新しい既定の番号になった場合でも、既存ユーザーの既定の番号は変わりません。</span><span class="sxs-lookup"><span data-stu-id="cba9d-119">After a new phone number has been assigned, even if the number became the new default number, the default number for existing users won't change.</span></span> <span data-ttu-id="cba9d-120">既定の有料または無料電話の番号を追加するを設定するのには開催者がミーティングの招待には、[マイクロソフトのチーム](set-the-phone-numbers-included-on-invites-in-teams.md)の指示または[Skype](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)オンライン ビジネスのための指示が参照してください。</span><span class="sxs-lookup"><span data-stu-id="cba9d-120">To set the default toll or a toll-free number that is added to an organizer's meeting invites, see the instructions for [Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) or the instructions for [Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites).</span></span> 
  


### <a name="step-2---change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users-optional"></a><span data-ttu-id="cba9d-121">手順 2 - ユーザーの会議の出席依頼に記載されている既定の電話番号を変更する (オプション)</span><span class="sxs-lookup"><span data-stu-id="cba9d-121">Step 2 - Change the default phone numbers that are included in the meeting invites of users (optional)</span></span>

<span data-ttu-id="cba9d-122">ユーザーの既定の電話番号は、会議をスケジュールすると会議の出席依頼に記載される番号です。</span><span class="sxs-lookup"><span data-stu-id="cba9d-122">The default phone numbers for user are the ones that are included on their meeting invites when they schedule a meeting.</span></span> <span data-ttu-id="cba9d-123">詳細については、[携帯電話に含まれている番号は、マイクロソフトのチームで招待を設定](set-the-phone-numbers-included-on-invites-in-teams.md)したり、[オンライン ビジネスの Skype で招待に含まれている番号の電話の設定](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cba9d-123">For more information, see [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) or [Set the phone numbers included on invites in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites).</span></span>
  
1. <span data-ttu-id="cba9d-124">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="cba9d-124">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="cba9d-125">[**Office 365 管理センター**]  >  [**管理センター**]  >  [**Skype for Business**]  >  [**電話会議**]  >  [**ユーザー**] の順に開き、リスト内のユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="cba9d-125">Go to the **Office 365 admin center** > **Admin centers** > **Skype for Business** > **Audio conferencing** > **Users** and select the users in the list.</span></span>

3. <span data-ttu-id="cba9d-126">[操作] ウィンドウで [ **編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cba9d-126">Click **Edit** in the action pane.</span></span>

4. <span data-ttu-id="cba9d-127">[ **既定の有料電話番号**] または [ **既定のフリーダイヤル番号**] の下で、リストから番号を選択して [ **保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cba9d-127">Under **Default toll number** or **Default toll-free number**, select the number in the list and click **Save**.</span></span>

<span data-ttu-id="cba9d-128">変更が保存されると、次回新しい会議をスケジュールするときに新しい既定の電話番号が開催者の会議の出席依頼に記載されます。</span><span class="sxs-lookup"><span data-stu-id="cba9d-128">After the changes have been saved, the new default phone numbers will be included on the meeting invites of organizers the next time they schedule a new meeting.</span></span>

### <a name="step-3---update-existing-meeting-invites-of-users-using-the-meeting-migration-service-optional"></a><span data-ttu-id="cba9d-129">手順 3 - Meeting Migration Service を使用してユーザーの既存の会議の出席依頼を更新する (オプション)</span><span class="sxs-lookup"><span data-stu-id="cba9d-129">Step 3 - Update existing meeting invites of users using the Meeting Migration Service (optional)</span></span>

<span data-ttu-id="cba9d-130">次の 2 つの手順では、Windows PowerShell を開始することが必要になります。</span><span class="sxs-lookup"><span data-stu-id="cba9d-130">For the next two steps, you will need to start Windows PowerShell.</span></span>
  
<span data-ttu-id="cba9d-p107">Meeting Migration Service を使用して、ユーザーの既定の電話番号が変更される前に、組織内のユーザーに送信済みの会議の出席依頼をオプションで更新できます。詳細については、「[Meeting Migration Service (MMS) のセットアップ](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="cba9d-p107">Using the Meeting Migration Service, you can optionally update meeting invites that were already sent to users in your organization before their default phone numbers were changed. For additional information, see [Setting up the Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span></span>
  
- <span data-ttu-id="cba9d-p108">手順 2 で既定の電話番号を変更したユーザーに対して、Meeting Migration Service (MMS) を実行します。これを実行するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="cba9d-p108">Run the Meeting Migration Service (MMS) for the users who had their default phone numbers changed in Step 2. To do this, run the following command:</span></span>

```
    Start-CsExMeetingMigration user@contoso.com
```

- <span data-ttu-id="cba9d-p109">会議の移行の状態を確認することもできます。[ *保留*  ] または [ *進行中*  ] の状態で操作が行われなくなると、すべての会議のスケジュールが変更されることがあります。</span><span class="sxs-lookup"><span data-stu-id="cba9d-p109">You can also view the meeting migration status. All meetings would be rescheduled once there are no operations in  *Pending*  or *In-Progress*  state.</span></span>

```
    Get-CsMeetingMigrationStatus -SummaryOnly
```

## <a name="steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge"></a><span data-ttu-id="cba9d-137">会議ブリッジのサービス用電話番号の割り当てを解除するときの手順</span><span class="sxs-lookup"><span data-stu-id="cba9d-137">Steps when you are unassigning a service phone number for a conferencing bridge</span></span>


<span data-ttu-id="cba9d-p110">電話番号を会議ブリッジから割り当て解除すると、ユーザーは今後その電話番号を使用して会議に参加することができなくなります。電話番号が変更されているため、電話会議ブリッジから電話番号が割り当て解除される前に、既定の番号として電話番号を設定しているすべてのユーザーを更新することと、会議の既存の出席依頼を更新することが重要です。</span><span class="sxs-lookup"><span data-stu-id="cba9d-p110">When you unassign a phone number from a conferencing bridge, users won't be able to join any meetings using that phone number anymore. Because the phone number is changing, it's important to update all users that could have a phone number as their default number (if any) and to update their existing meeting invites before the phone number is unassigned from the audio conferencing bridge.</span></span>

<span data-ttu-id="cba9d-140">ユーザー、およびユーザーの会議を更新する前に電話番号が削除されると、既存の会議の出席依頼には、会議に参加するために使用できない電話番号が記載されてしまいます。</span><span class="sxs-lookup"><span data-stu-id="cba9d-140">If the phone number is removed without updating the users and their meetings, their existing meeting invites could contain a phone number that won't work for joining their meetings anymore.</span></span>

<span data-ttu-id="cba9d-141">最初の 3 つの手順では、Windows PowerShell を開始することが必要になります。</span><span class="sxs-lookup"><span data-stu-id="cba9d-141">For the first three steps, you will need to start Windows PowerShell.</span></span> <span data-ttu-id="cba9d-142">これを行う方法を表示するをクリックして[Windows PowerShell を使用して管理する方法を知りたいのですか?](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#bkPowerShell)</span><span class="sxs-lookup"><span data-stu-id="cba9d-142">To see how to do this, click [Want to know how to manage with Windows PowerShell?](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#bkPowerShell)</span></span>

### <a name="step-1---update-users-that-have-the-phone-number-to-be-unassigned-as-one-of-their-default-numbers"></a><span data-ttu-id="cba9d-143">手順 1 - 既定の番号の 1 つとしての割り当てが解除される電話番号があるユーザーを更新する</span><span class="sxs-lookup"><span data-stu-id="cba9d-143">Step 1 - Update users that have the phone number to be unassigned as one of their default numbers</span></span>

<span data-ttu-id="cba9d-p112">既定の番号としての割り当てが解除される番号があるすべてのユーザーについて、既定の有料または無料電話番号を置き換えて、会議のスケジュール変更のプロセスを開始します。これを実行するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="cba9d-p112">Replace the default toll or toll-free number for all users that have the number to be unassigned as a default number and start the process of rescheduling their meetings. To do this, run the following command:</span></span>

```
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```
 > [!IMPORTANT] 
 ><span data-ttu-id="cba9d-p113">Skype for Business 管理センターでユーザーの既定の有料または無料電話番号を変更することもできます。ただし、これにより自動的に会議のスケジュールが変更されることはありません 。</span><span class="sxs-lookup"><span data-stu-id="cba9d-p113">You can also change the default toll or toll-free number of users in the Skype for Business admin center. However, this won't automatically reschedule their meetings.</span></span> 
 
 <span data-ttu-id="cba9d-148">詳細については、[携帯電話に含まれている番号は、マイクロソフトのチームで招待を設定](set-the-phone-numbers-included-on-invites-in-teams.md)したり、[オンライン ビジネスの Skype で招待に含まれている番号の電話の設定](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cba9d-148">For additional information, see [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) or [Set the phone numbers included on invites in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites).</span></span>

  > [!NOTE]
  > <span data-ttu-id="cba9d-149">所属する組織の規模に応じて、完了するまで時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="cba9d-149">Depending on the size of your organization, this could take some time to complete.</span></span>

### <a name="step-2---view-meeting-migration-status-using-windows-powershell"></a><span data-ttu-id="cba9d-150">手順 2 - Windows PowerShell を使用して会議の移行状態を表示する</span><span class="sxs-lookup"><span data-stu-id="cba9d-150">Step 2 - View meeting migration status using Windows PowerShell</span></span>

<span data-ttu-id="cba9d-151">*保留中*または*実行中*の状態にする工程がないと、すべての会議を再スケジュールされます。</span><span class="sxs-lookup"><span data-stu-id="cba9d-151">All meetings will be rescheduled once there are no operations in *Pending* or *In-Progress* state.</span></span>

```
Get-CsMeetingMigrationStatus -SummaryOnly
```

<span data-ttu-id="cba9d-152">Meeting Migration Service の詳細については、「 [Meeting Migration Service (MMS) のセットアップ](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="cba9d-152">For more information about the Meeting Migration Service, see [Setting up the Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span></span>
  
### <a name="step-3---unassign-the-old-phone-number-from-the-audio-conferencing-bridge"></a><span data-ttu-id="cba9d-153">手順 3 - 古い電話番号を電話会議ブリッジから割り当て解除する</span><span class="sxs-lookup"><span data-stu-id="cba9d-153">Step 3 - Unassign the old phone number from the audio conferencing bridge</span></span>

1. <span data-ttu-id="cba9d-154">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="cba9d-154">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="cba9d-155">[**Office 365 管理センター**]  >  [**管理センター**]  >  [**Skype for Business**]  >  [**音声**]  >  [**電話番号**] の順に開きます。</span><span class="sxs-lookup"><span data-stu-id="cba9d-155">Go to the **Office 365 admin center** > **Admin centers** > **Skype for Business** > **Voice** > **Phone numbers**.</span></span>

3. <span data-ttu-id="cba9d-156">リストから電話番号を選択し、[操作] ウィンドウで [ **割り当てを解除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cba9d-156">Select the phone number from the list, and in the Action pane, click **Unassign**.</span></span>

4. <span data-ttu-id="cba9d-157">確認ウィンドウで、[ **はい**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cba9d-157">In the confirmation window, click **Yes**.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="cba9d-158">電話会議ブリッジから電話番号の割り当てを解除すると、ユーザーはその電話番号を使用して新規または既存の会議に参加できなくなります。</span><span class="sxs-lookup"><span data-stu-id="cba9d-158">After a phone number is unassigned from an audio conferencing bridge, the phone number will no longer be available for users to join new or existing meetings.</span></span>

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="cba9d-159">Windows PowerShell で管理する方法</span><span class="sxs-lookup"><span data-stu-id="cba9d-159">Want to know how to manage with Windows PowerShell?</span></span>
<span data-ttu-id="cba9d-160"><a name="bkPowerShell"> </a></span><span class="sxs-lookup"><span data-stu-id="cba9d-160"><a name="bkPowerShell"> </a></span></span>

### <a name="to-verify-that-windows-powershell-is-ready-to-go"></a><span data-ttu-id="cba9d-161">Windows PowerShell が使用できる状態かを確認する場合</span><span class="sxs-lookup"><span data-stu-id="cba9d-161">To verify that Windows PowerShell is ready to go</span></span>

 <span data-ttu-id="cba9d-162">次の手順では、3.0 またはそれ以降のバージョンの Windows PowerShell が実行していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="cba9d-162">These steps check that you are running Windows PowerShell version 3.0 or higher.</span></span>

1. <span data-ttu-id="cba9d-163">[**スタート メニュー**]  >  [**Windows PowerShell**] と入力します。</span><span class="sxs-lookup"><span data-stu-id="cba9d-163">Type **Start Menu** > **Windows PowerShell**.</span></span>

2. <span data-ttu-id="cba9d-164">**Windows PowerShell** のウィンドウで _Get-Host_ と入力し、バージョンを確認します。</span><span class="sxs-lookup"><span data-stu-id="cba9d-164">Type _Get-Host_ in the **Windows PowerShell** window to check the version.</span></span>

3. <span data-ttu-id="cba9d-p114">バージョン 3.0 以降を使用していない場合は、Windows PowerShell の更新プログラムをダウンロードおよびインストールする必要があります。Windows PowerShell をダウンロードして、バージョン 4.0 に更新するには、「[Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845)」を参照してください。メッセージが表示されたら、コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="cba9d-p114">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>

4. <span data-ttu-id="cba9d-168">また、Skype のビジネス オンライン ビジネス オンラインの Skype に接続するリモートの Windows PowerShell セッションを作成することを可能にするため Windows PowerShell モジュールをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="cba9d-168">You also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="cba9d-169">このモジュールでは、64 ビット コンピューターでのみサポートされ、[オンライン ビジネスの Skype のモジュールを Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=294688)に Microsoft ダウンロード センターからダウンロードすることができます。</span><span class="sxs-lookup"><span data-stu-id="cba9d-169">This module is supported only on 64-bit computers and can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span></span>
<span data-ttu-id="cba9d-170">メッセージが表示されたら、コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="cba9d-170">Restart your computer if you are prompted.</span></span>

<span data-ttu-id="cba9d-171">詳細については、「[単一の Windows PowerShell ウィンドウですべての Office 365 サービスに接続する](https://technet.microsoft.com/library/dn568015.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cba9d-171">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>

### <a name="to-start-windows-powershell"></a><span data-ttu-id="cba9d-172">Windows PowerShell を開始する場合</span><span class="sxs-lookup"><span data-stu-id="cba9d-172">To start Windows PowerShell</span></span>

 <span data-ttu-id="cba9d-173">**Windows PowerShell セッションを開始する**</span><span class="sxs-lookup"><span data-stu-id="cba9d-173">**Start a Windows PowerShell session**</span></span>

1. <span data-ttu-id="cba9d-174">[**スタート メニュー**]  >  [**Windows PowerShell**] から開きます。</span><span class="sxs-lookup"><span data-stu-id="cba9d-174">From the **Start Menu** > **Windows PowerShell**.</span></span>

2. <span data-ttu-id="cba9d-175">[ **Windows PowerShell**] ウィンドウで、次を実行して、Office 365 の組織に接続します。</span><span class="sxs-lookup"><span data-stu-id="cba9d-175">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>

    > [!NOTE]
    > <span data-ttu-id="cba9d-176">Skype for Business Online Windows PowerShell モジュールを初めて使用するときに、 **Import-Module** コマンドを実行するだけです。</span><span class="sxs-lookup"><span data-stu-id="cba9d-176">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>

>
  ```
    Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

<span data-ttu-id="cba9d-177">Windows PowerShell を開始する方法の詳細を設定する場合は、 [1 つの Windows PowerShell のウィンドウ内のすべての Office 365 サービスに接続する](https://technet.microsoft.com/library/dn568015.aspx)か、 [Windows PowerShell を使用して、オンライン ビジネスの Skype への接続](https://technet.microsoft.com/library/dn362795%28v=ocs.15%29.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cba9d-177">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/library/dn362795%28v=ocs.15%29.aspx).</span></span>

### <a name="save-time-and-automate"></a><span data-ttu-id="cba9d-178">自動化して時間を節約</span><span class="sxs-lookup"><span data-stu-id="cba9d-178">Save time and automate</span></span>

<span data-ttu-id="cba9d-179">このプロセスを自動化することにより時間を節約するには、[セット CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688)または**セット CsOnlineDialInConferencingUserDefaultNumber**コマンドレットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="cba9d-179">To save time by automating this process, you can use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) or the **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlets.</span></span>

- <span data-ttu-id="cba9d-180">特定ユーザーのデフォルトの有料または無料電話番号を変更するには、[[Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688)] コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="cba9d-180">Use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) cmdlet to change the default toll or toll-free number for specific users.</span></span>

  - <span data-ttu-id="cba9d-181">ユーザーのデフォルトの無料電話番号を変更するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="cba9d-181">To change the default toll-free number for a user, run:</span></span>

  ```
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   80045551234
  ```

- <span data-ttu-id="cba9d-182">ユーザーの元の既定の電話番号または所在地に基づいて既定の有料または無料電話番号を変更するには、 **Set-CsOnlineDialInConferencingUserDefaultNumber** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="cba9d-182">Use the **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlet to change the default toll or toll-free number of users based on their original default number or their location.</span></span>

    > [!NOTE]
    > <span data-ttu-id="cba9d-183">BridgeID を探すには、 **Get-CsOnlineDialInConferencingBridge** を使用します。</span><span class="sxs-lookup"><span data-stu-id="cba9d-183">To find the BridgeID, use the **Get-CsOnlineDialInConferencingBridge**.</span></span>

  - <span data-ttu-id="cba9d-184">デフォルトの無料電話番号がないユーザー全員のデフォルト無料電話番号を 8005551234 に設定するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="cba9d-184">To set the default toll-free number for all users without one to 8005551234, run:</span></span>

  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```

  - <span data-ttu-id="cba9d-185">デフォルトの無料電話番号が 8005551234 のユーザー全員のデフォルト無料電話番号を 8005551239 に変更し、会議のスケジュールを自動的に変更するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="cba9d-185">To change the default toll-free number of all users that have 8005551234 as their default toll-free number to 8005551239 and automatically reschedule their meetings, run:</span></span>

  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber 8005551234 -ToNumber 8005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

  - <span data-ttu-id="cba9d-186">所在地が米国内のユーザー全員のデフォルト無料電話番号を 8005551234 に設定し、会議のスケジュールを自動的に変更するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="cba9d-186">To set the default toll-free number of all users located in the U.S. to 8005551234 and automatically reschedule their meetings, run:</span></span>

  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

    > [!NOTE]
    > <span data-ttu-id="cba9d-187">上記で使用される場所は、Office 365 管理センターに設定されているユーザーの連絡先情報と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cba9d-187">The location that is used above needs to match the contact information of user(s) that is set in the Office 365 admin center.</span></span>

## <a name="about-windows-powershell"></a><span data-ttu-id="cba9d-188">Windows PowerShell について</span><span class="sxs-lookup"><span data-stu-id="cba9d-188">About Windows PowerShell</span></span>

<span data-ttu-id="cba9d-189">Windows PowerShell では、ユーザーと、ユーザーに許可されていることと許可されていないことを管理します。</span><span class="sxs-lookup"><span data-stu-id="cba9d-189">With Windows PowerShell you can manage users and what they are or are not allowed to do.</span></span> <span data-ttu-id="cba9d-190">Windows PowerShell では、ビジネス オンラインを行う複数のタスクがあれば、特に、日常的な作業を簡素化する管理の単一ポイントを使用して Office 365 と Skype を管理できます。</span><span class="sxs-lookup"><span data-stu-id="cba9d-190">Windows PowerShell  can help you manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, especially when you've got multiple tasks to do.</span></span> <span data-ttu-id="cba9d-191">Windows PowerShell の使用を開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cba9d-191">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="cba9d-192">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="cba9d-192">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [<span data-ttu-id="cba9d-193">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="cba9d-193">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

<span data-ttu-id="cba9d-p117">Windows PowerShell には、ただ Office 365 管理センターを使用するだけではなく、速度、単純さ、生産性において多くの利点があります。次のトピックでこれらの利点について説明します。</span><span class="sxs-lookup"><span data-stu-id="cba9d-p117">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="cba9d-196">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="cba9d-196">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [<span data-ttu-id="cba9d-197">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="cba9d-197">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [<span data-ttu-id="cba9d-198">クイック リファレンス: Windows PowerShell を使用した一般的な Lync Online の管理タスクの実行</span><span class="sxs-lookup"><span data-stu-id="cba9d-198">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="cba9d-199">See also</span><span class="sxs-lookup"><span data-stu-id="cba9d-199">Related topics</span></span>
[<span data-ttu-id="cba9d-200">電話会議ブリッジの設定を変更する</span><span class="sxs-lookup"><span data-stu-id="cba9d-200">Change the settings for an Audio Conferencing bridge</span></span>](change-the-settings-for-an-audio-conferencing-bridge.md)
