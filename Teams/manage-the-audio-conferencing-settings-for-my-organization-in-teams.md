---
title: Microsoft Teams で組織の電話会議の設定を管理する
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: bc9bd328-c5b2-44e5-af15-e02bf00e1c81
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'ダイヤルイン電話会議ライセンスと会議 ID をユーザーおよびその他の多くのダイヤルイン電話会議の設定に割り当てるための Microsoft Teams での手順を確認します。 '
ms.openlocfilehash: 40a6dd3e545e913a134ae7bac80b5ec3085dc96a
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2018
ms.locfileid: "25015334"
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization-in-microsoft-teams"></a><span data-ttu-id="bd7bb-103">Microsoft Teams で組織の電話会議の設定を管理する</span><span class="sxs-lookup"><span data-stu-id="bd7bb-103">Manage the Audio Conferencing settings for my organization in Microsoft Teams</span></span>

<span data-ttu-id="bd7bb-104">1 つの場所で Microsoft Teams のすべての電話会議設定を確認することが、より簡単になります。</span><span class="sxs-lookup"><span data-stu-id="bd7bb-104">It might be easier for you to see all of the audio conferencing settings for Microsoft Teams in one place.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="assign-an-audio-conferencing-license"></a><span data-ttu-id="bd7bb-105">電話会議のライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="bd7bb-105">Assign an Audio Conferencing license</span></span>

> [!NOTE]
> <span data-ttu-id="bd7bb-106">チームを使用してライセンスを割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="bd7bb-106">You can't assign licenses using Teams.</span></span> <span data-ttu-id="bd7bb-107">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="bd7bb-107">You must use the Office 365 admin center.</span></span> <span data-ttu-id="bd7bb-108">In the left navigation of the Office 365 admin center, go to UsersActive users > and then select the user or users from the list of available users.</span><span class="sxs-lookup"><span data-stu-id="bd7bb-108">See [Assign Skype for Business and Microsoft Teams licenses](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).</span></span> 
  
 <span data-ttu-id="bd7bb-109">最大 20 人までのライセンスを同時に割り当てている場合は、[ ビューの選択] ボックスを使用していずれかのオプションを選択するか、独自のビューを作成することができます。次に [ 編集]、[ 次へ] を 2 回クリックし、ライセンスを選択して、[ 送信] をクリックします。また、Windows Powershell を使用してライセンスを複数のユーザーに割り当てることもできます。操作手順と PowerShell のサンプル スクリプトについては、「Skype for Business と Microsoft Teams のライセンスを割り当てる」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="bd7bb-109">**To assign a license for a user**</span></span>
  
1. <span data-ttu-id="bd7bb-110">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="bd7bb-110">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="bd7bb-111">次に [ **編集**]、[ **次へ**] を 2 回クリックし、ライセンスを選択して、[  > ] をクリックします。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="bd7bb-111">In the left navigation of the **Office 365 admin center**, go to **Users** > **Active users**, and then select the user or users from the list of available users.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="bd7bb-112">操作手順と PowerShell のサンプル スクリプトについては、「**Skype for Business と Microsoft Teams のライセンスを割り当てる**」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="bd7bb-112">If you are assigning licenses to up to 20 users at the same time, you can use the **Select a view** drop-down then choose one of the options or create your own view.</span></span> <span data-ttu-id="bd7bb-113">操作ウィンドウの [ **製品ライセンス**] で [ **編集**] をクリックします。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="bd7bb-113">Then click **Edit**, **Next** twice then select the license and click **Submit**.</span></span>  
  
3. <span data-ttu-id="bd7bb-114">操作ウィンドウの [**製品ライセンス**] で [ **編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bd7bb-114">In the Action pane under **Product licenses**, click **Edit**.</span></span> 
    
4. <span data-ttu-id="bd7bb-p103">ライセンスを割り当てると、電話会議プロバイダーのリストに Microsoft が表示されなくなることがあります。この場合は、Office 365 管理センターからログアウトするか、CTRL キーを押しながら F5 キーを押してブラウザーのウィンドウを更新します。</span><span class="sxs-lookup"><span data-stu-id="bd7bb-p103">On the **Product Licenses** page, turn on **Audio Conferencing** and then click **Save**. For more on licensing, see [Skype for Business and Microsoft Teams add-on licensing](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing).</span></span>
    
> [!NOTE]
> <span data-ttu-id="bd7bb-p104">ユーザーに会議 ID を割り当てる</span><span class="sxs-lookup"><span data-stu-id="bd7bb-p104">After you assign the license, Microsoft might not appear initially in the list as an audio conferencing provider. If this happens, either log out of the Office 365 admin center or press CTRL+F5 to refresh the browser window.</span></span> 
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a><span data-ttu-id="bd7bb-119">電話会議ユーザーに送信されたメールを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="bd7bb-119">Enable or disable emails sent to audio conferencing users</span></span>

<span data-ttu-id="bd7bb-120">![teams-logo-30x30.png](media/teams-logo-30x30.png) \*\*Microsoft Teams と Skype for Business 管理センターを使用する: \*\*</span><span class="sxs-lookup"><span data-stu-id="bd7bb-120">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="bd7bb-121">左側のナビゲーションで、[**会議**]  >  [**会議ブリッジ**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="bd7bb-121">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="bd7bb-122">[**会議ブリッジ**] ページの最上部で、[**ブリッジの設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bd7bb-122">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="bd7bb-123">[**ブリッジの設定**] ペインで、[**ダイヤルイン設定が変わると、ユーザーに自動的に電子メールが送信されます**] を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="bd7bb-123">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="bd7bb-124">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bd7bb-124">Click **Save**.</span></span>

    
<span data-ttu-id="bd7bb-125">**Windows PowerShell を使用する**</span><span class="sxs-lookup"><span data-stu-id="bd7bb-125">**Using Windows PowerShell**</span></span>
  
<span data-ttu-id="bd7bb-126">詳細については、[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="bd7bb-126">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a><span data-ttu-id="bd7bb-127">ユーザーに送信された、送信者のメール メッセージ内の連絡先情報を変更する</span><span class="sxs-lookup"><span data-stu-id="bd7bb-127">Change the sender's contact information in email messages sent to users</span></span>

<span data-ttu-id="bd7bb-128">Change the senders contact information of email messages sent to users</span><span class="sxs-lookup"><span data-stu-id="bd7bb-128">You can make changes to the email that is automatically sent to your users, including the actual email address and the display name of the sender's contact information.</span></span> <span data-ttu-id="bd7bb-129">既定では、Office 365 は、電子メールの送信者が電子メール アドレスを変更し、Windows PowerShell を使用して名前を表示できます。</span><span class="sxs-lookup"><span data-stu-id="bd7bb-129">By default, the sender of the emails is Office 365, but you can change the email address and display name using Windows PowerShell.</span></span> <span data-ttu-id="bd7bb-130">詳細については[マイクロソフト チームの PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd7bb-130">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="reset-the-meeting-conference-id"></a><span data-ttu-id="bd7bb-131">会議 ID をリセットする</span><span class="sxs-lookup"><span data-stu-id="bd7bb-131">Reset the meeting conference ID</span></span>

1. <span data-ttu-id="bd7bb-132">左側のナビゲーションで、[**ユーザー**] をクリックしてから、空いているユーザーのリストからユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="bd7bb-132">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="bd7bb-133">ページの上部で、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bd7bb-133">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="bd7bb-134">[**電話会議**] の下で、[**会議 ID のリセット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bd7bb-134">Under **Audio Conferencing**, click **Reset conference ID**.</span></span>  

4. <span data-ttu-id="bd7bb-135">**会議 ID をリセットしますか?** ] ウィンドウで、[**リセット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bd7bb-135">In the **Reset conference ID?** window, click **Reset**.</span></span> <span data-ttu-id="bd7bb-136">It's enabled by default.</span><span class="sxs-lookup"><span data-stu-id="bd7bb-136">A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled.</span></span> <span data-ttu-id="bd7bb-137">After a new conference ID is created, the old conference ID can't be used by callers. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. The users can use Skype for Business Meeting Migration Tool to update their existing meetings. To see how to download, install and run the Lync Meeting Update Tool, see:> Meeting Update Tool for Skype for Business and LyncSkype for Business Online, Meeting Migration Tool (64-bit)Skype for Business Online, Meeting Migration Tool (32-bit)</span><span class="sxs-lookup"><span data-stu-id="bd7bb-137">It's enabled by default.</span></span>

<span data-ttu-id="bd7bb-138">「[ユーザーのために会議 ID をリセットする](reset-a-conference-id-for-a-user-in-teams.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="bd7bb-138">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user-in-teams.md).</span></span>
  
## <a name="reset-a-conference-organizers-pin"></a><span data-ttu-id="bd7bb-139">電話会議の開催者の PIN をリセットする</span><span class="sxs-lookup"><span data-stu-id="bd7bb-139">Reset a conference organizer's PIN</span></span>

<span data-ttu-id="bd7bb-140">ユーザーをスケジュールする会議ごとに固有の会議 ID が割り当てられますを取得</span><span class="sxs-lookup"><span data-stu-id="bd7bb-140">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="bd7bb-141">会議 ID が自動的に作成され、ユーザーに割り当てられているがあります、ユーザーは、この 1 つを使用する場合は、特定の数に設定するとユーザーが覚えられないか、会議 ID が失われています。</span><span class="sxs-lookup"><span data-stu-id="bd7bb-141">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or your users can't remember or have lost their conference ID.</span></span> 

1. <span data-ttu-id="bd7bb-142">左側のナビゲーションで、[**ユーザー**] をクリックしてから、空いているユーザーのリストからユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="bd7bb-142">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="bd7bb-143">ページの上部で、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bd7bb-143">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="bd7bb-144">[**電話会議**] の下で、[**PIN のリセット**] をクリックしてから、[**リセット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bd7bb-144">Under **Audio Conferencing**, click **Reset PIN**, and then click **Reset**.</span></span> 
  
    
<span data-ttu-id="bd7bb-p108">リセットの直後に 1 回表示された後は、ユーザーのプロパティには PIN に代わって "\*\*\*\*\*" が表示されます。</span><span class="sxs-lookup"><span data-stu-id="bd7bb-p108">Users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset. But if you have disabled automatically sending emails, a PIN reset email won't be sent and you will have to manually send the PIN to the user. The PIN will only be shown once after it has been reset. After it's displayed just after being reset, the PIN won't be shown anymore on the user properties; instead, \*\*\*\*\* will be shown.</span></span> 
  
<span data-ttu-id="bd7bb-149">「[電話会議の PIN をリセットする](reset-the-audio-conferencing-pin-in-teams.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="bd7bb-149">See [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin-in-teams.md).</span></span>
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="bd7bb-150">電話会議の情報が記載されたメールをユーザーに送信する</span><span class="sxs-lookup"><span data-stu-id="bd7bb-150">Send an email with Audio Conferencing information to a user</span></span>

1. <span data-ttu-id="bd7bb-151">左側のナビゲーションで、[**ユーザー**] をクリックしてから、空いているユーザーのリストからユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="bd7bb-151">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="bd7bb-152">ページの上部で、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bd7bb-152">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="bd7bb-153">[**電話会議**] の下で、[**電話会議情報をメールで送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bd7bb-153">Under **Audio Conferencing**, click **Send conference info in email**.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="bd7bb-154">この操作を行っても、電話会議の PIN はユーザーに送信されません。</span><span class="sxs-lookup"><span data-stu-id="bd7bb-154">When you do this, the audio conferencing PIN isn't sent to the user.</span></span> 

  
<span data-ttu-id="bd7bb-155">「[電話会議の情報が記載されたメールをユーザーに送信する](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="bd7bb-155">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).</span></span>
  
## <a name="setting-the-phone-numbers-included-on-invites"></a><span data-ttu-id="bd7bb-156">招待状に含まれている電話番号を設定する</span><span class="sxs-lookup"><span data-stu-id="bd7bb-156">Setting the phone numbers included on invites</span></span>

1. <span data-ttu-id="bd7bb-157">左側のナビゲーションで、[**ユーザー**] をクリックしてから、空いているユーザーのリストからユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="bd7bb-157">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="bd7bb-158">[**電話会議**] の隣で、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bd7bb-158">Next to **Audio Conferencing**, click **Edit**.</span></span>
 
3. <span data-ttu-id="bd7bb-159">[**電話会議**] ウィンドウで、[**有料電話番号**] と、可能な場合は [**フリーダイヤル番号**] を設定することができます。</span><span class="sxs-lookup"><span data-stu-id="bd7bb-159">In the **Audio Conferencing** pane, you can set the **Toll number** and, if allowed, the **Toll-free number**.</span></span>

4. <span data-ttu-id="bd7bb-160">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bd7bb-160">Click **Save**.</span></span>
    
<span data-ttu-id="bd7bb-161">「[招待状に含まれている電話番号を設定する](set-the-phone-numbers-included-on-invites-in-teams.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="bd7bb-161">See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites-in-teams.md).</span></span>
  
  
## <a name="choosing-audio-conferencing-bridge-settings"></a><span data-ttu-id="bd7bb-162">電話会議ブリッジの設定を選ぶ</span><span class="sxs-lookup"><span data-stu-id="bd7bb-162">Choosing audio conferencing bridge settings</span></span>

<span data-ttu-id="bd7bb-163">**発信者が会議に参加するときの会議エクスペリエンスを設定する**</span><span class="sxs-lookup"><span data-stu-id="bd7bb-163">**Set the meeting experience when callers join a meeting**</span></span>


1. <span data-ttu-id="bd7bb-164">左側のナビゲーションで、[**会議**]  >  [**会議ブリッジ**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="bd7bb-164">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="bd7bb-165">[**会議ブリッジ**] ページの最上部で、[**ブリッジの設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bd7bb-165">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="bd7bb-166">[**ブリッジ設定**] ウィンドウで、[**会議の開始と終了の通知**] を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="bd7bb-166">In the **Bridge settings** pane, enable or disable **Meeting entry and exit notifications**.</span></span>

    <span data-ttu-id="bd7bb-167">これは既定で有効になります。</span><span class="sxs-lookup"><span data-stu-id="bd7bb-167">This is enabled by default.</span></span> <span data-ttu-id="bd7bb-168">このオプションを無効にした場合データを入力したり、会議を離れるときに既定では、会議に参加しているユーザーが通知されません。</span><span class="sxs-lookup"><span data-stu-id="bd7bb-168">If you disable this option, users who have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span></span>

4. <span data-ttu-id="bd7bb-169">[**開始/終了のお知らせの種類**] で、[**トーン**] または [**名前または電話番号**] のどちらかを選びます。</span><span class="sxs-lookup"><span data-stu-id="bd7bb-169">Under **Entry/exit announcement type**, choose either **Tones** or **Names or phone numbers**.</span></span> 

    <span data-ttu-id="bd7bb-170">[**名前または電話番号**] を選ぶと、[**発信者に、会議に参加する前に自分の名前を記録するように要求します**] を有効または無効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="bd7bb-170">If you choose **Names or phone numbers**, you can also choose to enable or disable **Ask callers to record their name before joining the meeting**.</span></span> 

5. <span data-ttu-id="bd7bb-171">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bd7bb-171">Click **Save**.</span></span>

    
<span data-ttu-id="bd7bb-172">[](change-the-settings-for-an-audio-conferencing-bridge.md)職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="bd7bb-172">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>
  
 <span data-ttu-id="bd7bb-173">**会議の PIN の長さサイズを設定する**</span><span class="sxs-lookup"><span data-stu-id="bd7bb-173">**Set the PIN length for meetings**</span></span>

1. <span data-ttu-id="bd7bb-174">左側のナビゲーションで、[**会議**]  >  [**会議ブリッジ**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="bd7bb-174">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="bd7bb-175">[**会議ブリッジ**] ページの最上部で、[**ブリッジの設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bd7bb-175">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="bd7bb-176">[**ブリッジの設定**] ウィンドウで、[**PIN の長さ**] リストに PIN の桁数を入力し、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bd7bb-176">In the **Bridge settings** pane, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>

    <span data-ttu-id="bd7bb-p110">PIN は 4 桁から 12 桁の間の値にする必要があります。既定値は 5 桁です。</span><span class="sxs-lookup"><span data-stu-id="bd7bb-p110">The PIN must be between 4 and 12 digits. The default is 5.</span></span>

    
<span data-ttu-id="bd7bb-179">職場または学校のアカウントを使用して、Office 365 にサインインします。[](change-the-settings-for-an-audio-conferencing-bridge.md)</span><span class="sxs-lookup"><span data-stu-id="bd7bb-179">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>
  
 <span data-ttu-id="bd7bb-180">**電話会議ユーザーに送信されているメールを有効または無効にする**</span><span class="sxs-lookup"><span data-stu-id="bd7bb-180">**Enable or disable email from being sent to audio users**</span></span>


1. <span data-ttu-id="bd7bb-181">左側のナビゲーションで、[**会議**]  >  [**会議ブリッジ**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="bd7bb-181">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="bd7bb-182">[**会議ブリッジ**] ページの最上部で、[**ブリッジの設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bd7bb-182">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="bd7bb-183">[**ブリッジの設定**] ペインで、[**電話会議設定が変わると、ユーザーに自動的に電子メールが送信されます**] を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="bd7bb-183">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their audio conferencing settings change**.</span></span>

4. <span data-ttu-id="bd7bb-184">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bd7bb-184">Click **Save**.</span></span> 
 
    <span data-ttu-id="bd7bb-185">電話会議設定をメールでユーザーに送ることもできます。その場合は、ユーザーの電話会議プロパティに移動して、[ **電話会議情報をメールで送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bd7bb-185">You can also send email to the user with the audio conferencing settings, by going to the user's audio conferencing properties and clicking **Send conference info in email**.</span></span>
    
    <span data-ttu-id="bd7bb-186">この操作を行うと、会議 ID と電話会議の番号のみが含まれるメールが送信されますが、そのメールに PIN は含まれません。</span><span class="sxs-lookup"><span data-stu-id="bd7bb-186">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span></span>

<span data-ttu-id="bd7bb-187">「[電話会議の情報が記載されたメールをユーザーに送信する](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="bd7bb-187">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).</span></span>
    
## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a><span data-ttu-id="bd7bb-188">電話会議ブリッジの第 1 (既定) 言語と第 2 (代替) 言語を表示および設定する</span><span class="sxs-lookup"><span data-stu-id="bd7bb-188">See and set the primary (default) and secondary (alternate) languages on an audio conferencing bridge</span></span>

1. <span data-ttu-id="bd7bb-189">左側のナビゲーションで、[**会議**]  >  [**会議ブリッジ**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="bd7bb-189">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="bd7bb-190">リストから電話番号を選択し、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bd7bb-190">Select a phone number from the list and click **Edit**.</span></span>

3. <span data-ttu-id="bd7bb-191">[**既定の言語**] と [**代替言語 (オプション)**] で必要な言語を選びます。</span><span class="sxs-lookup"><span data-stu-id="bd7bb-191">Choose the languages you want under **Default language** and **Alternate languages (optional)**.</span></span>

4. <span data-ttu-id="bd7bb-192">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bd7bb-192">Click **Save**.</span></span>


<span data-ttu-id="bd7bb-193">You can also set the primary and secondary languages that are supported when you select Microsoft as the dial-in conferencing provider. The order that you select in the drop-downs will be the order of the languages that will be presented to the callers.[](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="bd7bb-193">See [Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span></span>
  
## <a name="see-audio-conferencing-dial-in-numbers"></a><span data-ttu-id="bd7bb-194">You can also set the primary and secondary languages that are supported when you select Microsoft as the dial-in conferencing provider.</span><span class="sxs-lookup"><span data-stu-id="bd7bb-194">See audio conferencing dial-in numbers</span></span>


1. <span data-ttu-id="bd7bb-195">左側のナビゲーションで、[**会議**]  >  [**会議ブリッジ**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="bd7bb-195">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="bd7bb-196">リストから電話番号を選択し、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bd7bb-196">Select a phone number from the list and click **Edit**.</span></span> <span data-ttu-id="bd7bb-197">Go to the Office 365 admin centerSkype for Business.</span><span class="sxs-lookup"><span data-stu-id="bd7bb-197">Here you can:</span></span>
    
  - <span data-ttu-id="bd7bb-198">電話会議で使うために Office 365 によって設定された電話番号を表示する。</span><span class="sxs-lookup"><span data-stu-id="bd7bb-198">View the phone numbers that are set by Office 365 to be used for Audio Conferencing.</span></span> 
    
  - <span data-ttu-id="bd7bb-199">場所、およびオーディオ会議自動アテンダントによって使用される主言語を表示します。</span><span class="sxs-lookup"><span data-stu-id="bd7bb-199">View the location, and the primary language, that will be used by the Audio Conferencing auto attendant.</span></span>

  
<span data-ttu-id="bd7bb-200">You can select the dial-in conferencing default phone number that will be given to users when they are enabled for dial-in conferencing.[](see-a-list-of-audio-conferencing-numbers-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="bd7bb-200">See [See a list of Audio Conferencing numbers](see-a-list-of-audio-conferencing-numbers-in-teams.md).</span></span>
  

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="bd7bb-201">Windows PowerShell の詳細情報</span><span class="sxs-lookup"><span data-stu-id="bd7bb-201">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="bd7bb-p112">Windows PowerShell は、ユーザーと、ユーザーに許可されていることと許可されていないことを管理するためにあるということです。Windows PowerShell があれば、一元管理を使用して Office 365 を管理し、複数のタスクを抱えているときに、日常の仕事を簡素化することができます。Windows PowerShell を開始するには、これらのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd7bb-p112">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="bd7bb-205">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="bd7bb-205">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="bd7bb-206">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="bd7bb-206">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="bd7bb-207">Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="bd7bb-207">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
    
## <a name="related-topics"></a><span data-ttu-id="bd7bb-208">関連トピック</span><span class="sxs-lookup"><span data-stu-id="bd7bb-208">Related topics</span></span>

<span data-ttu-id="bd7bb-209">See also</span><span class="sxs-lookup"><span data-stu-id="bd7bb-209">[Manage the Audio Conferencing settings for a user](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)</span></span>


