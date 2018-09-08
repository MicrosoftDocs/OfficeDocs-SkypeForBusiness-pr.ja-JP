---
title: マイクロソフトのチームで、組織内でのオーディオ会議設定を管理します。
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: bc9bd328-c5b2-44e5-af15-e02bf00e1c81
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'ユーザーおよびその他のダイヤルイン会議の設定に、ダイヤルイン会議のライセンスおよび会議 ID を割り当てるには、マイクロソフトのチームの手順を参照してください。 '
ms.openlocfilehash: 7af89da74b0b83872954444a847d40f0d7851087
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23884706"
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization-in-microsoft-teams"></a><span data-ttu-id="f83c9-103">マイクロソフトのチームで、組織内でのオーディオ会議設定を管理します。</span><span class="sxs-lookup"><span data-stu-id="f83c9-103">Manage the Audio Conferencing settings for my organization in Microsoft Teams</span></span>

<span data-ttu-id="f83c9-104">マイクロソフト チームの 1 つの場所で電話会議の設定をすべて表示することが容易になりますがある場合があります。</span><span class="sxs-lookup"><span data-stu-id="f83c9-104">It might be easier for you to see all of the audio conferencing settings for Microsoft Teams in one place.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="assign-an-audio-conferencing-license"></a><span data-ttu-id="f83c9-105">電話会議のライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="f83c9-105">Assign an Audio Conferencing license</span></span>

> [!NOTE]
> <span data-ttu-id="f83c9-106">チームを使用してライセンスを割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="f83c9-106">You can't assign licenses using Teams.</span></span> <span data-ttu-id="f83c9-107">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="f83c9-107">You must use the Office 365 admin center.</span></span> <span data-ttu-id="f83c9-108">In the left navigation of the Office 365 admin center, go to UsersActive users > and then select the user or users from the list of available users.</span><span class="sxs-lookup"><span data-stu-id="f83c9-108">See [Assign Skype for Business and Microsoft Teams licenses](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).</span></span> 
  
 <span data-ttu-id="f83c9-109">最大 20 人までのライセンスを同時に割り当てている場合は、[ ビューの選択] ボックスを使用していずれかのオプションを選択するか、独自のビューを作成することができます。次に [ 編集]、[ 次へ] を 2 回クリックし、ライセンスを選択して、[ 送信] をクリックします。また、Windows Powershell を使用してライセンスを複数のユーザーに割り当てることもできます。操作手順と PowerShell のサンプル スクリプトについては、「Skype for Business と Microsoft Teams のライセンスを割り当てる」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f83c9-109">**To assign a license for a user**</span></span>
  
1. <span data-ttu-id="f83c9-110">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="f83c9-110">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="f83c9-111">次に [ **編集**]、[ **次へ**] を 2 回クリックし、ライセンスを選択して、[  > ] をクリックします。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="f83c9-111">In the left navigation of the **Office 365 admin center**, go to **Users** > **Active users**, and then select the user or users from the list of available users.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f83c9-112">操作手順と PowerShell のサンプル スクリプトについては、「**Skype for Business と Microsoft Teams のライセンスを割り当てる**」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f83c9-112">If you are assigning licenses to up to 20 users at the same time, you can use the **Select a view** drop-down then choose one of the options or create your own view.</span></span> <span data-ttu-id="f83c9-113">操作ウィンドウの [ **製品ライセンス**] で [ **編集**] をクリックします。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="f83c9-113">Then click **Edit**, **Next** twice then select the license and click **Submit**.</span></span>  
  
3. <span data-ttu-id="f83c9-114">ライセンスの詳細については、「**Skype for Business と Microsoft Teams のアドオン ライセンス**」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f83c9-114">In the Action pane under **Product licenses**, click **Edit**.</span></span> 
    
4. <span data-ttu-id="f83c9-p103">ライセンスを割り当てると、電話会議プロバイダーのリストに Microsoft が表示されなくなることがあります。この場合は、Office 365 管理センターからログアウトするか、CTRL キーを押しながら F5 キーを押してブラウザーのウィンドウを更新します。</span><span class="sxs-lookup"><span data-stu-id="f83c9-p103">On the **Product Licenses** page, turn on **Audio Conferencing** and then click **Save**. For more on licensing, see [Skype for Business and Microsoft Teams add-on licensing](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing).</span></span>
    
> [!NOTE]
> <span data-ttu-id="f83c9-p104">ユーザーに会議 ID を割り当てる</span><span class="sxs-lookup"><span data-stu-id="f83c9-p104">After you assign the license, Microsoft might not appear initially in the list as an audio conferencing provider. If this happens, either log out of the Office 365 admin center or press CTRL+F5 to refresh the browser window.</span></span> 
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a><span data-ttu-id="f83c9-119">Skype for Business 管理センターまたは Windows PowerShell を使用すると、ユーザーへのメール送信を有効または無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="f83c9-119">Enable or disable emails sent to audio conferencing users</span></span>

<span data-ttu-id="f83c9-120">![チーム ・ ロゴ ・ 30x30.png](media/teams-logo-30x30.png) **、マイクロソフトのチームとビジネス管理センターの Skype を使用します。**</span><span class="sxs-lookup"><span data-stu-id="f83c9-120">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="f83c9-121">左側のナビゲーションでは、**会議**に移動 > **会議ブリッジ**です。</span><span class="sxs-lookup"><span data-stu-id="f83c9-121">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="f83c9-122">**会議ブリッジ**のページの上部には、**ブリッジの設定**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f83c9-122">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="f83c9-123">**ブリッジの設定**ウィンドウで、有効または、**ユーザーのダイヤルインの設定を変更する場合に e メールを自動的に送信**を無効にします。</span><span class="sxs-lookup"><span data-stu-id="f83c9-123">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="f83c9-124">[ **保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f83c9-124">Click **Save**.</span></span>

    
<span data-ttu-id="f83c9-125">**The conference ID and default dial-in conferencing phone number is included on the meeting invite but not the PIN.**</span><span class="sxs-lookup"><span data-stu-id="f83c9-125">**Using Windows PowerShell**</span></span>
  
<span data-ttu-id="f83c9-126">詳細については[マイクロソフト チームの PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f83c9-126">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a><span data-ttu-id="f83c9-127">You can also use the Windows PowerShell and run:</span><span class="sxs-lookup"><span data-stu-id="f83c9-127">Change the sender's contact information in email messages sent to users</span></span>

<span data-ttu-id="f83c9-128">Change the senders contact information of email messages sent to users</span><span class="sxs-lookup"><span data-stu-id="f83c9-128">You can make changes to the email that is automatically sent to your users, including the actual email address and the display name of the sender's contact information.</span></span> <span data-ttu-id="f83c9-129">既定では、Office 365 は、電子メールの送信者が電子メール アドレスを変更し、Windows PowerShell を使用して名前を表示できます。</span><span class="sxs-lookup"><span data-stu-id="f83c9-129">By default, the sender of the emails is Office 365, but you can change the email address and display name using Windows PowerShell.</span></span> <span data-ttu-id="f83c9-130">詳細については[マイクロソフト チームの PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f83c9-130">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="reset-the-meeting-conference-id"></a><span data-ttu-id="f83c9-131">Sign in to Office 365 with your work or school account.</span><span class="sxs-lookup"><span data-stu-id="f83c9-131">Reset the meeting conference ID</span></span>

1. <span data-ttu-id="f83c9-132">左側のナビゲーションでは、**ユーザー**] をクリックしてで使用可能なユーザーの一覧からユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="f83c9-132">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="f83c9-133">ページの上部で、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f83c9-133">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="f83c9-134">[**オーディオ会議**、**会議 ID のリセット**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f83c9-134">Under **Audio Conferencing**, click **Reset conference ID**.</span></span>  

4. <span data-ttu-id="f83c9-135">**会議 ID をリセットしますか?** ] ウィンドウで、[**リセット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f83c9-135">In the **Reset conference ID?** window, click **Reset**.</span></span> <span data-ttu-id="f83c9-136">It's enabled by default.</span><span class="sxs-lookup"><span data-stu-id="f83c9-136">A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled.</span></span> <span data-ttu-id="f83c9-137">After a new conference ID is created, the old conference ID can't be used by callers. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. The users can use Skype for Business Meeting Migration Tool to update their existing meetings. To see how to download, install and run the Lync Meeting Update Tool, see:> Meeting Update Tool for Skype for Business and LyncSkype for Business Online, Meeting Migration Tool (64-bit)Skype for Business Online, Meeting Migration Tool (32-bit)</span><span class="sxs-lookup"><span data-stu-id="f83c9-137">It's enabled by default.</span></span>

<span data-ttu-id="f83c9-138">[](reset-a-conference-id-for-a-user-in-teams.md)Reset a conference organizer's PIN</span><span class="sxs-lookup"><span data-stu-id="f83c9-138">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user-in-teams.md).</span></span>
  
## <a name="reset-a-conference-organizers-pin"></a><span data-ttu-id="f83c9-139">静的会議 ID は自動的に作成されユーザーに割り当てられますが、ユーザーがそれを使いたくないため特定の番号に設定しようと考える場合や、ユーザーが会議 ID を覚えられない、または紛失してしまう場合があります。Skype for Business 管理センターおよび Windows PowerShell を使用すると、ユーザーの会議 ID を表示、変更、リセットすることができます。</span><span class="sxs-lookup"><span data-stu-id="f83c9-139">Reset a conference organizer's PIN</span></span>

<span data-ttu-id="f83c9-140">ユーザーをスケジュールする会議ごとに固有の会議 ID が割り当てられますを取得</span><span class="sxs-lookup"><span data-stu-id="f83c9-140">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="f83c9-141">会議 ID が自動的に作成され、ユーザーに割り当てられているがあります、ユーザーは、この 1 つを使用する場合は、特定の数に設定するとユーザーが覚えられないか、会議 ID が失われています。</span><span class="sxs-lookup"><span data-stu-id="f83c9-141">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or your users can't remember or have lost their conference ID.</span></span> 

1. <span data-ttu-id="f83c9-142">左側のナビゲーションでは、**ユーザー**] をクリックしてで使用可能なユーザーの一覧からユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="f83c9-142">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="f83c9-143">ページの上部で、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f83c9-143">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="f83c9-144">**オーディオ会議**では、[ **PIN のリセット**] をクリックし、[**リセット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f83c9-144">Under **Audio Conferencing**, click **Reset PIN**, and then click **Reset**.</span></span> 
  
    
<span data-ttu-id="f83c9-p108">リセットの直後に 1 回表示された後は、ユーザーのプロパティには PIN に代わって "\*\*\*\*\*" が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f83c9-p108">Users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset. But if you have disabled automatically sending emails, a PIN reset email won't be sent and you will have to manually send the PIN to the user. The PIN will only be shown once after it has been reset. After it's displayed just after being reset, the PIN won't be shown anymore on the user properties; instead, \*\*\*\*\* will be shown.</span></span> 
  
<span data-ttu-id="f83c9-149">[オーディオ会議の PIN のリセット](reset-the-audio-conferencing-pin-in-teams.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f83c9-149">See [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin-in-teams.md).</span></span>
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="f83c9-150">電話会議の情報が記載されたメールをユーザーに送信する</span><span class="sxs-lookup"><span data-stu-id="f83c9-150">Send an email with Audio Conferencing information to a user</span></span>

1. <span data-ttu-id="f83c9-151">左側のナビゲーションでは、**ユーザー**] をクリックしてで使用可能なユーザーの一覧からユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="f83c9-151">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="f83c9-152">ページの上部で、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f83c9-152">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="f83c9-153">[**電話会議**] の [**電話会議情報をメールで送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f83c9-153">Under **Audio Conferencing**, click **Send conference info in email**.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="f83c9-154">この操作を行っても、電話会議の PIN はユーザーに送信されません。</span><span class="sxs-lookup"><span data-stu-id="f83c9-154">When you do this, the audio conferencing PIN isn't sent to the user.</span></span> 

  
<span data-ttu-id="f83c9-155">When you do this, the dial-in conferencing PIN isn't sent to the user.</span><span class="sxs-lookup"><span data-stu-id="f83c9-155">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).</span></span>
  
## <a name="setting-the-phone-numbers-included-on-invites"></a><span data-ttu-id="f83c9-156">携帯電話への招待に含まれている番号を設定します。</span><span class="sxs-lookup"><span data-stu-id="f83c9-156">Setting the phone numbers included on invites</span></span>

1. <span data-ttu-id="f83c9-157">左側のナビゲーションでは、**ユーザー**] をクリックしてで使用可能なユーザーの一覧からユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="f83c9-157">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="f83c9-158">**オーディオ会議**の横にある [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f83c9-158">Next to **Audio Conferencing**, click **Edit**.</span></span>
 
3. <span data-ttu-id="f83c9-159">**オーディオ会議**のウィンドウで**電話番号**を設定でき、許可された場合、**フリー ダイヤルの番号**です。</span><span class="sxs-lookup"><span data-stu-id="f83c9-159">In the **Audio Conferencing** pane, you can set the **Toll number** and, if allowed, the **Toll-free number**.</span></span>

4. <span data-ttu-id="f83c9-160">The default dial-in conferencing phone number of a user is the number that is shown on the meeting invite when they schedule a meeting.</span><span class="sxs-lookup"><span data-stu-id="f83c9-160">Click **Save**.</span></span>
    
<span data-ttu-id="f83c9-161">「[出席依頼に含まれている会議の開催者のために電話会議の電話番号を設定する](set-the-phone-numbers-included-on-invites-in-teams.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f83c9-161">See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites-in-teams.md).</span></span>
  
  
## <a name="choosing-audio-conferencing-bridge-settings"></a><span data-ttu-id="f83c9-162">オーディオ会議ブリッジの設定を選択します。</span><span class="sxs-lookup"><span data-stu-id="f83c9-162">Choosing audio conferencing bridge settings</span></span>

<span data-ttu-id="f83c9-163">\*\*\*\* Setting dial-in conferencing bridge settings</span><span class="sxs-lookup"><span data-stu-id="f83c9-163">**Set the meeting experience when callers join a meeting**</span></span>


1. <span data-ttu-id="f83c9-164">左側のナビゲーションでは、**会議**に移動 > **会議ブリッジ**です。</span><span class="sxs-lookup"><span data-stu-id="f83c9-164">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="f83c9-165">**会議ブリッジ**のページの上部には、**ブリッジの設定**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f83c9-165">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="f83c9-166">**ブリッジの設定**ウィンドウを有効にするまたは**ミーティングのエントリと終了の通知**を無効にします。</span><span class="sxs-lookup"><span data-stu-id="f83c9-166">In the **Bridge settings** pane, enable or disable **Meeting entry and exit notifications**.</span></span>

    <span data-ttu-id="f83c9-167">これは既定で有効になります。</span><span class="sxs-lookup"><span data-stu-id="f83c9-167">This is enabled by default.</span></span> <span data-ttu-id="f83c9-168">このオプションを無効にした場合データを入力したり、会議を離れるときに既定では、会議に参加しているユーザーが通知されません。</span><span class="sxs-lookup"><span data-stu-id="f83c9-168">If you disable this option, users who have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span></span>

4. <span data-ttu-id="f83c9-169">**開始/終了のお知らせの種類**、[**トーン**] または [**名前または電話番号**を選択します。</span><span class="sxs-lookup"><span data-stu-id="f83c9-169">Under **Entry/exit announcement type**, choose either **Tones** or **Names or phone numbers**.</span></span> 

    <span data-ttu-id="f83c9-170">**名前や電話番号**を選択する場合を有効にするまたは、**ミーティングに参加する前に自分の名前を記録するための呼び出し元の確認**を無効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="f83c9-170">If you choose **Names or phone numbers**, you can also choose to enable or disable **Ask callers to record their name before joining the meeting**.</span></span> 

5. <span data-ttu-id="f83c9-171">[ **保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f83c9-171">Click **Save**.</span></span>

    
<span data-ttu-id="f83c9-172">Go to the Office 365 admin centerSkype for Business.[](change-the-settings-for-an-audio-conferencing-bridge.md)</span><span class="sxs-lookup"><span data-stu-id="f83c9-172">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>
  
 <span data-ttu-id="f83c9-173">**In the Skype for Business admin center, in the left navigation go to dial-in conferencingMicrosoft bridge settings.**</span><span class="sxs-lookup"><span data-stu-id="f83c9-173">**Set the PIN length for meetings**</span></span>

1. <span data-ttu-id="f83c9-174">左側のナビゲーションでは、**会議**に移動 > **会議ブリッジ**です。</span><span class="sxs-lookup"><span data-stu-id="f83c9-174">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="f83c9-175">**会議ブリッジ**のページの上部には、**ブリッジの設定**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f83c9-175">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="f83c9-176">**ブリッジの設定**ウィンドウで、 **PIN の長さ**] ボックスの一覧で、[暗証番号 (pin) に使用桁の番号を入力し、し、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f83c9-176">In the **Bridge settings** pane, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>

    <span data-ttu-id="f83c9-p110">The PIN can only be from 4 to 12 digits.</span><span class="sxs-lookup"><span data-stu-id="f83c9-p110">The PIN must be between 4 and 12 digits. The default is 5.</span></span>

    
<span data-ttu-id="f83c9-179">職場または学校のアカウントを使用して、Office 365 にサインインします。[](change-the-settings-for-an-audio-conferencing-bridge.md)</span><span class="sxs-lookup"><span data-stu-id="f83c9-179">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>
  
 <span data-ttu-id="f83c9-180">**Sign in to Office 365 with your work or school account.**</span><span class="sxs-lookup"><span data-stu-id="f83c9-180">**Enable or disable email from being sent to audio users**</span></span>


1. <span data-ttu-id="f83c9-181">左側のナビゲーションでは、**会議**に移動 > **会議ブリッジ**です。</span><span class="sxs-lookup"><span data-stu-id="f83c9-181">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="f83c9-182">**会議ブリッジ**のページの上部には、**ブリッジの設定**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f83c9-182">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="f83c9-183">**ブリッジの設定**ウィンドウを有効にするか **、オーディオ会議の設定を変更する場合、ユーザーに e メールを自動的に送信**を無効にします。</span><span class="sxs-lookup"><span data-stu-id="f83c9-183">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their audio conferencing settings change**.</span></span>

4. <span data-ttu-id="f83c9-184">[ **保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f83c9-184">Click **Save**.</span></span> 
 
    <span data-ttu-id="f83c9-185">ユーザーのオーディオ会議のプロパティに移動し、**電子メールで会議の情報を送信**] をクリックしてユーザーに、電話会議の設定を使用する電子メールを送信することも。</span><span class="sxs-lookup"><span data-stu-id="f83c9-185">You can also send email to the user with the audio conferencing settings, by going to the user's audio conferencing properties and clicking **Send conference info in email**.</span></span>
    
    <span data-ttu-id="f83c9-186">この操作を行うと、会議 ID と電話会議の番号のみが含まれるメールが送信されますが、そのメールに PIN は含まれません。</span><span class="sxs-lookup"><span data-stu-id="f83c9-186">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span></span>

<span data-ttu-id="f83c9-187">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span><span class="sxs-lookup"><span data-stu-id="f83c9-187">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).</span></span>
    
## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a><span data-ttu-id="f83c9-188">参照してくださいし、オーディオ会議ブリッジに (既定値) をプライマリとセカンダリ (代替) の言語を設定します。</span><span class="sxs-lookup"><span data-stu-id="f83c9-188">See and set the primary (default) and secondary (alternate) languages on an audio conferencing bridge</span></span>

1. <span data-ttu-id="f83c9-189">左側のナビゲーションでは、**会議**に移動 > **会議ブリッジ**です。</span><span class="sxs-lookup"><span data-stu-id="f83c9-189">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="f83c9-190">リストから電話番号を選択し、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f83c9-190">Select a phone number from the list and click **Edit**.</span></span>

3. <span data-ttu-id="f83c9-191">[**既定の言語**および **(省略可能) 別の言語**の言語を選択してください。</span><span class="sxs-lookup"><span data-stu-id="f83c9-191">Choose the languages you want under **Default language** and **Alternate languages (optional)**.</span></span>


<span data-ttu-id="f83c9-192">You can also set the primary and secondary languages that are supported when you select Microsoft as the dial-in conferencing provider. The order that you select in the drop-downs will be the order of the languages that will be presented to the callers.[](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="f83c9-192">See [Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span></span>
  
## <a name="see-audio-conferencing-dial-in-numbers"></a><span data-ttu-id="f83c9-193">You can also set the primary and secondary languages that are supported when you select Microsoft as the dial-in conferencing provider.</span><span class="sxs-lookup"><span data-stu-id="f83c9-193">See audio conferencing dial-in numbers</span></span>


1. <span data-ttu-id="f83c9-194">左側のナビゲーションでは、**会議**に移動 > **会議ブリッジ**です。</span><span class="sxs-lookup"><span data-stu-id="f83c9-194">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="f83c9-195">リストから電話番号を選択し、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f83c9-195">Select a phone number from the list and click **Edit**.</span></span> <span data-ttu-id="f83c9-196">Go to the Office 365 admin centerSkype for Business.</span><span class="sxs-lookup"><span data-stu-id="f83c9-196">Here you can:</span></span>
    
  - <span data-ttu-id="f83c9-197">電話会議で使うために Office 365 によって設定された電話番号を表示する。</span><span class="sxs-lookup"><span data-stu-id="f83c9-197">View the phone numbers that are set by Office 365 to be used for Audio Conferencing.</span></span> 
    
  - <span data-ttu-id="f83c9-198">場所、およびオーディオ会議自動アテンダントによって使用される主言語を表示します。</span><span class="sxs-lookup"><span data-stu-id="f83c9-198">View the location, and the primary language, that will be used by the Audio Conferencing auto attendant.</span></span>

  
<span data-ttu-id="f83c9-199">You can select the dial-in conferencing default phone number that will be given to users when they are enabled for dial-in conferencing.[](see-a-list-of-audio-conferencing-numbers-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="f83c9-199">See [See a list of Audio Conferencing numbers](see-a-list-of-audio-conferencing-numbers-in-teams.md).</span></span>
  

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="f83c9-200">Windows PowerShell の詳細情報</span><span class="sxs-lookup"><span data-stu-id="f83c9-200">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="f83c9-p112">Windows PowerShell は、ユーザーと、ユーザーに許可されていることと許可されていないことを管理するためにあるということです。Windows PowerShell があれば、一元管理を使用して Office 365 を管理し、複数のタスクを抱えているときに、日常の仕事を簡素化することができます。Windows PowerShell を開始するには、これらのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f83c9-p112">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="f83c9-204">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="f83c9-204">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="f83c9-205">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="f83c9-205">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="f83c9-206">Windows PowerShell の詳細については、[マイクロソフト チームの PowerShell の参照](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)の詳細についてを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f83c9-206">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
    
## <a name="related-topics"></a><span data-ttu-id="f83c9-207">このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「Skype for Business Online 用 Windows PowerShell モジュール」からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="f83c9-207">Related topics</span></span>

<span data-ttu-id="f83c9-208">See also</span><span class="sxs-lookup"><span data-stu-id="f83c9-208">[Manage the Audio Conferencing settings for a user](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)</span></span>


