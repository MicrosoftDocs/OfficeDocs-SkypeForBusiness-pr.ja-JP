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
ms.openlocfilehash: b63650833c7c844de11ecb833288b6568604f919
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/13/2018
ms.locfileid: "26296098"
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization-in-microsoft-teams"></a><span data-ttu-id="604fb-103">Microsoft Teams で組織の電話会議の設定を管理する</span><span class="sxs-lookup"><span data-stu-id="604fb-103">Manage the Audio Conferencing settings for my organization in Microsoft Teams</span></span>

<span data-ttu-id="604fb-104">1 つの場所で Microsoft Teams のすべての電話会議設定を確認することが、より簡単になります。</span><span class="sxs-lookup"><span data-stu-id="604fb-104">It might be easier for you to see all of the audio conferencing settings for Microsoft Teams in one place.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="assign-an-audio-conferencing-license"></a><span data-ttu-id="604fb-105">電話会議のライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="604fb-105">Assign an Audio Conferencing license</span></span>

> [!NOTE]
> <span data-ttu-id="604fb-106">Teams を使用してライセンスを割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="604fb-106">You can't assign licenses using Teams.</span></span> <span data-ttu-id="604fb-107">Office 365 管理センターを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="604fb-107">You must use the Office 365 admin center.</span></span> <span data-ttu-id="604fb-108">In the left navigation of the Office 365 admin center, go to UsersActive users > and then select the user or users from the list of available users.</span><span class="sxs-lookup"><span data-stu-id="604fb-108">See [Assign Skype for Business and Microsoft Teams licenses](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).</span></span> 
  
 <span data-ttu-id="604fb-109">最大 20 人までのライセンスを同時に割り当てている場合は、[ ビューの選択] ボックスを使用していずれかのオプションを選択するか、独自のビューを作成することができます。次に [ 編集]、[ 次へ] を 2 回クリックし、ライセンスを選択して、[ 送信] をクリックします。また、Windows Powershell を使用してライセンスを複数のユーザーに割り当てることもできます。操作手順と PowerShell のサンプル スクリプトについては、「Skype for Business と Microsoft Teams のライセンスを割り当てる」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="604fb-109">**To assign a license for a user**</span></span>
  
1. <span data-ttu-id="604fb-110">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="604fb-110">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="604fb-111">次に [ **編集**]、[ **次へ**] を 2 回クリックし、ライセンスを選択して、[  > ] をクリックします。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="604fb-111">In the left navigation of the **Office 365 admin center**, go to **Users** > **Active users**, and then select the user or users from the list of available users.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="604fb-112">操作手順と PowerShell のサンプル スクリプトについては、「**Skype for Business と Microsoft Teams のライセンスを割り当てる**」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="604fb-112">If you are assigning licenses to up to 20 users at the same time, you can use the **Select a view** drop-down then choose one of the options or create your own view.</span></span> <span data-ttu-id="604fb-113">次に [**編集**]、[**次へ**] を 2 回クリックしてからライセンスを選択し、[**送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="604fb-113">Then click **Edit**, **Next** twice then select the license and click **Submit**.</span></span>  
  
3. <span data-ttu-id="604fb-114">操作ウィンドウの [**製品ライセンス**] で [ **編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="604fb-114">In the Action pane under **Product licenses**, click **Edit**.</span></span> 
    
4. <span data-ttu-id="604fb-p103">ライセンスを割り当てると、電話会議プロバイダーのリストに Microsoft が表示されなくなることがあります。この場合は、Office 365 管理センターからログアウトするか、CTRL キーを押しながら F5 キーを押してブラウザーのウィンドウを更新します。</span><span class="sxs-lookup"><span data-stu-id="604fb-p103">On the **Product Licenses** page, turn on **Audio Conferencing** and then click **Save**. For more on licensing, see [Skype for Business and Microsoft Teams add-on licensing](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing).</span></span>
    
> [!NOTE]
> <span data-ttu-id="604fb-p104">ユーザーに会議 ID を割り当てる</span><span class="sxs-lookup"><span data-stu-id="604fb-p104">After you assign the license, Microsoft might not appear initially in the list as an audio conferencing provider. If this happens, either log out of the Office 365 admin center or press CTRL+F5 to refresh the browser window.</span></span> 
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a><span data-ttu-id="604fb-119">電話会議ユーザーに送信されたメールを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="604fb-119">Enable or disable emails sent to audio conferencing users</span></span>

<span data-ttu-id="604fb-120">![teams-logo-30x30.png](media/teams-logo-30x30.png) \*\*Microsoft Teams と Skype for Business 管理センターを使用する: \*\*</span><span class="sxs-lookup"><span data-stu-id="604fb-120">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="604fb-121">左側のナビゲーションで、[**会議**]  >  [**会議ブリッジ**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="604fb-121">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="604fb-122">[**会議ブリッジ**] ページの最上部で、[**ブリッジの設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="604fb-122">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="604fb-123">[**ブリッジの設定**] ペインで、[**ダイヤルイン設定が変わると、ユーザーに自動的に電子メールが送信されます**] を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="604fb-123">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="604fb-124">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="604fb-124">Click **Save**.</span></span>

    
<span data-ttu-id="604fb-125">**Windows PowerShell を使用する**</span><span class="sxs-lookup"><span data-stu-id="604fb-125">**Using Windows PowerShell**</span></span>
  
<span data-ttu-id="604fb-126">詳細については、[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="604fb-126">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a><span data-ttu-id="604fb-127">ユーザーに送信された、送信者のメール メッセージ内の連絡先情報を変更する</span><span class="sxs-lookup"><span data-stu-id="604fb-127">Change the sender's contact information in email messages sent to users</span></span>

<span data-ttu-id="604fb-128">Change the senders contact information of email messages sent to users</span><span class="sxs-lookup"><span data-stu-id="604fb-128">You can make changes to the email that is automatically sent to your users, including the actual email address and the display name of the sender's contact information.</span></span> <span data-ttu-id="604fb-129">既定では、メールの送信者は Office 365 ですが、Windows PowerShell を使用してメール アドレスと表示名を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="604fb-129">By default, the sender of the emails is Office 365, but you can change the email address and display name using Windows PowerShell.</span></span> <span data-ttu-id="604fb-130">詳細については、[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="604fb-130">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="reset-the-meeting-conference-id"></a><span data-ttu-id="604fb-131">会議 ID をリセットする</span><span class="sxs-lookup"><span data-stu-id="604fb-131">Reset the meeting conference ID</span></span>

<span data-ttu-id="604fb-132">![チーム ・ ロゴ ・ 30x30.png](media/teams-logo-30x30.png) **、マイクロソフトのチームとビジネス管理センターの Skype を使用します。**</span><span class="sxs-lookup"><span data-stu-id="604fb-132">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="604fb-133">左側のナビゲーションでは、**ユーザー**] をクリックしてで使用可能なユーザーの一覧からユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="604fb-133">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="604fb-134">[**電話会議**] の下で、[**会議 ID のリセット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="604fb-134">Under **Audio Conferencing**, click **Reset conference ID**.</span></span>  

3. <span data-ttu-id="604fb-135">[**会議 ID をリセットしますか?**] ウィンドウで、[**リセット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="604fb-135">In the **Reset conference ID?** window, click **Reset**.</span></span> <span data-ttu-id="604fb-136">It's enabled by default.</span><span class="sxs-lookup"><span data-stu-id="604fb-136">A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled.</span></span> <span data-ttu-id="604fb-137">これは既定では有効になっています。</span><span class="sxs-lookup"><span data-stu-id="604fb-137">It's enabled by default.</span></span>

<span data-ttu-id="604fb-138">「[ユーザーのために会議 ID をリセットする](reset-a-conference-id-for-a-user-in-teams.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="604fb-138">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user-in-teams.md).</span></span>
  
## <a name="reset-a-conference-organizers-pin"></a><span data-ttu-id="604fb-139">電話会議の開催者の PIN をリセットする</span><span class="sxs-lookup"><span data-stu-id="604fb-139">Reset a conference organizer's PIN</span></span>

<span data-ttu-id="604fb-140">ユーザーがスケジュール設定した各会議には、一意の会議 ID が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="604fb-140">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="604fb-141">会議 ID は自動的に作成されユーザーに割り当てられますが、ユーザーがそれを使いたくないため特定の番号に設定しようと考える場合や、ユーザーが会議 ID を覚えられない、または紛失してしまう場合があります。</span><span class="sxs-lookup"><span data-stu-id="604fb-141">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or your users can't remember or have lost their conference ID.</span></span> 

<span data-ttu-id="604fb-142">![チーム ・ ロゴ ・ 30x30.png](media/teams-logo-30x30.png) **、マイクロソフトのチームとビジネス管理センターの Skype を使用します。**</span><span class="sxs-lookup"><span data-stu-id="604fb-142">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="604fb-143">左側のナビゲーションでは、**ユーザー**] をクリックしてで使用可能なユーザーの一覧からユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="604fb-143">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="604fb-144">[**電話会議**] の下で、[**PIN のリセット**] をクリックしてから、[**リセット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="604fb-144">Under **Audio Conferencing**, click **Reset PIN**, and then click **Reset**.</span></span> 
  
<span data-ttu-id="604fb-p108">リセットの直後に 1 回表示された後は、ユーザーのプロパティには PIN に代わって "\*\*\*\*\*" が表示されます。</span><span class="sxs-lookup"><span data-stu-id="604fb-p108">Users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset. But if you have disabled automatically sending emails, a PIN reset email won't be sent and you will have to manually send the PIN to the user. The PIN will only be shown once after it has been reset. After it's displayed just after being reset, the PIN won't be shown anymore on the user properties; instead, \*\*\*\*\* will be shown.</span></span> 
  
<span data-ttu-id="604fb-149">「[電話会議の PIN をリセットする](reset-the-audio-conferencing-pin-in-teams.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="604fb-149">See [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin-in-teams.md).</span></span>
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="604fb-150">電話会議の情報が記載されたメールをユーザーに送信する</span><span class="sxs-lookup"><span data-stu-id="604fb-150">Send an email with Audio Conferencing information to a user</span></span>

<span data-ttu-id="604fb-151">![チーム ・ ロゴ ・ 30x30.png](media/teams-logo-30x30.png) **、マイクロソフトのチームとビジネス管理センターの Skype を使用します。**</span><span class="sxs-lookup"><span data-stu-id="604fb-151">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="604fb-152">左側のナビゲーションでは、**ユーザー**] をクリックしてで使用可能なユーザーの一覧からユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="604fb-152">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="604fb-153">[**電話会議**] の下で、[**電話会議情報をメールで送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="604fb-153">Under **Audio Conferencing**, click **Send conference info in email**.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="604fb-154">この操作を行っても、電話会議の PIN はユーザーに送信されません。</span><span class="sxs-lookup"><span data-stu-id="604fb-154">When you do this, the audio conferencing PIN isn't sent to the user.</span></span> 

<span data-ttu-id="604fb-155">「[電話会議の情報が記載されたメールをユーザーに送信する](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="604fb-155">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).</span></span>
  
## <a name="set-the-phone-numbers-included-on-invites"></a><span data-ttu-id="604fb-156">出席依頼に含まれている電話番号を設定する</span><span class="sxs-lookup"><span data-stu-id="604fb-156">Set the phone numbers included on invites</span></span>

<span data-ttu-id="604fb-157">![チーム ・ ロゴ ・ 30x30.png](media/teams-logo-30x30.png) **、マイクロソフトのチームとビジネス管理センターの Skype を使用します。**</span><span class="sxs-lookup"><span data-stu-id="604fb-157">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="604fb-158">左側のナビゲーションでは、**ユーザー**] をクリックしてで使用可能なユーザーの一覧からユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="604fb-158">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="604fb-159">**オーディオ会議**の横にある [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="604fb-159">Next to **Audio Conferencing**, click **Edit**.</span></span>
 
3. <span data-ttu-id="604fb-160">**オーディオ会議**のウィンドウで**電話番号**を設定でき、許可された場合、**フリー ダイヤルの番号**です。</span><span class="sxs-lookup"><span data-stu-id="604fb-160">In the **Audio Conferencing** pane, you can set the **Toll number** and, if allowed, the **Toll-free number**.</span></span>

4. <span data-ttu-id="604fb-161">The default dial-in conferencing phone number of a user is the number that is shown on the meeting invite when they schedule a meeting.</span><span class="sxs-lookup"><span data-stu-id="604fb-161">Click **Save**.</span></span>
    
<span data-ttu-id="604fb-162">「[出席依頼に含まれている会議の開催者のために電話会議の電話番号を設定する](set-the-phone-numbers-included-on-invites-in-teams.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="604fb-162">See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites-in-teams.md).</span></span>
  
  
## <a name="choose-audio-conferencing-bridge-settings"></a><span data-ttu-id="604fb-163">オーディオ会議ブリッジの設定を選択します。</span><span class="sxs-lookup"><span data-stu-id="604fb-163">Choose audio conferencing bridge settings</span></span>

<span data-ttu-id="604fb-164">\*\*\*\* Setting dial-in conferencing bridge settings</span><span class="sxs-lookup"><span data-stu-id="604fb-164">**Set the meeting experience when callers join a meeting**</span></span>

<span data-ttu-id="604fb-165">![チーム ・ ロゴ ・ 30x30.png](media/teams-logo-30x30.png) **、マイクロソフトのチームとビジネス管理センターの Skype を使用します。**</span><span class="sxs-lookup"><span data-stu-id="604fb-165">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="604fb-166">左側のナビゲーションで、[**会議**]  >  [**会議ブリッジ**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="604fb-166">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="604fb-167">**会議ブリッジ**のページの上部には、**ブリッジの設定**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="604fb-167">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="604fb-168">[**ブリッジ設定**] ウィンドウで、[**会議の開始と終了の通知**] を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="604fb-168">In the **Bridge settings** pane, enable or disable **Meeting entry and exit notifications**.</span></span>

    <span data-ttu-id="604fb-169">これは既定で有効になります。</span><span class="sxs-lookup"><span data-stu-id="604fb-169">This is enabled by default.</span></span> <span data-ttu-id="604fb-170">このオプションを無効にした場合データを入力したり、会議を離れるときに既定では、会議に参加しているユーザーが通知されません。</span><span class="sxs-lookup"><span data-stu-id="604fb-170">If you disable this option, users who have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span></span>

4. <span data-ttu-id="604fb-171">**開始/終了のお知らせの種類**、[**トーン**] または [**名前または電話番号**を選択します。</span><span class="sxs-lookup"><span data-stu-id="604fb-171">Under **Entry/exit announcement type**, choose either **Tones** or **Names or phone numbers**.</span></span> 

    <span data-ttu-id="604fb-172">**名前や電話番号**を選択する場合を有効にするまたは、**ミーティングに参加する前に自分の名前を記録するための呼び出し元の確認**を無効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="604fb-172">If you choose **Names or phone numbers**, you can also choose to enable or disable **Ask callers to record their name before joining the meeting**.</span></span> 

5. <span data-ttu-id="604fb-173">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="604fb-173">Click **Save**.</span></span>

    
<span data-ttu-id="604fb-174">Go to the Office 365 admin centerSkype for Business.[](change-the-settings-for-an-audio-conferencing-bridge.md)</span><span class="sxs-lookup"><span data-stu-id="604fb-174">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>
  
 <span data-ttu-id="604fb-175">**In the Skype for Business admin center, in the left navigation go to dial-in conferencingMicrosoft bridge settings.**</span><span class="sxs-lookup"><span data-stu-id="604fb-175">**Set the PIN length for meetings**</span></span>

1. <span data-ttu-id="604fb-176">左側のナビゲーションで、[**会議**]  >  [**会議ブリッジ**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="604fb-176">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="604fb-177">**会議ブリッジ**のページの上部には、**ブリッジの設定**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="604fb-177">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="604fb-178">**ブリッジの設定**ウィンドウで、 **PIN の長さ**] ボックスの一覧で、[暗証番号 (pin) に使用桁の番号を入力し、し、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="604fb-178">In the **Bridge settings** pane, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>

    <span data-ttu-id="604fb-p110">The PIN can only be from 4 to 12 digits.</span><span class="sxs-lookup"><span data-stu-id="604fb-p110">The PIN must be between 4 and 12 digits. The default is 5.</span></span>

    
<span data-ttu-id="604fb-181">職場または学校のアカウントを使用して、Office 365 にサインインします。[](change-the-settings-for-an-audio-conferencing-bridge.md)</span><span class="sxs-lookup"><span data-stu-id="604fb-181">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>
  
 <span data-ttu-id="604fb-182">**Sign in to Office 365 with your work or school account.**</span><span class="sxs-lookup"><span data-stu-id="604fb-182">**Enable or disable email from being sent to audio users**</span></span>

1. <span data-ttu-id="604fb-183">左側のナビゲーションで、[**会議**]  >  [**会議ブリッジ**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="604fb-183">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="604fb-184">**会議ブリッジ**のページの上部には、**ブリッジの設定**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="604fb-184">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="604fb-185">**ブリッジの設定**ウィンドウを有効にするか **、オーディオ会議の設定を変更する場合、ユーザーに e メールを自動的に送信**を無効にします。</span><span class="sxs-lookup"><span data-stu-id="604fb-185">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their audio conferencing settings change**.</span></span>

4. <span data-ttu-id="604fb-186">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="604fb-186">Click **Save**.</span></span> 
 
    <span data-ttu-id="604fb-187">ユーザーのオーディオ会議のプロパティに移動し、**電子メールで会議の情報を送信**] をクリックしてユーザーに、電話会議の設定を使用する電子メールを送信することも。</span><span class="sxs-lookup"><span data-stu-id="604fb-187">You can also send email to the user with the audio conferencing settings, by going to the user's audio conferencing properties and clicking **Send conference info in email**.</span></span>
    
    <span data-ttu-id="604fb-188">この操作を行うと、会議 ID と電話会議の番号のみが含まれるメールが送信されますが、そのメールに PIN は含まれません。</span><span class="sxs-lookup"><span data-stu-id="604fb-188">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span></span>

<span data-ttu-id="604fb-189">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span><span class="sxs-lookup"><span data-stu-id="604fb-189">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).</span></span>
    
## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a><span data-ttu-id="604fb-190">参照してくださいし、オーディオ会議ブリッジに (既定値) をプライマリとセカンダリ (代替) の言語を設定します。</span><span class="sxs-lookup"><span data-stu-id="604fb-190">See and set the primary (default) and secondary (alternate) languages on an audio conferencing bridge</span></span>

<span data-ttu-id="604fb-191">![チーム ・ ロゴ ・ 30x30.png](media/teams-logo-30x30.png) **、マイクロソフトのチームとビジネス管理センターの Skype を使用します。**</span><span class="sxs-lookup"><span data-stu-id="604fb-191">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="604fb-192">左側のナビゲーションで、[**会議**]  >  [**会議ブリッジ**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="604fb-192">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="604fb-193">リストから電話番号を選択し、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="604fb-193">Select a phone number from the list and click **Edit**.</span></span>

3. <span data-ttu-id="604fb-194">[**既定の言語**および **(省略可能) 別の言語**の言語を選択してください。</span><span class="sxs-lookup"><span data-stu-id="604fb-194">Choose the languages you want under **Default language** and **Alternate languages (optional)**.</span></span>

4. <span data-ttu-id="604fb-195">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="604fb-195">Click **Save**.</span></span>


<span data-ttu-id="604fb-196">You can also set the primary and secondary languages that are supported when you select Microsoft as the dial-in conferencing provider. The order that you select in the drop-downs will be the order of the languages that will be presented to the callers.[](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="604fb-196">See [Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span></span>
  
## <a name="see-audio-conferencing-dial-in-numbers"></a><span data-ttu-id="604fb-197">You can also set the primary and secondary languages that are supported when you select Microsoft as the dial-in conferencing provider.</span><span class="sxs-lookup"><span data-stu-id="604fb-197">See audio conferencing dial-in numbers</span></span>

<span data-ttu-id="604fb-198">![チーム ・ ロゴ ・ 30x30.png](media/teams-logo-30x30.png) **、マイクロソフトのチームとビジネス管理センターの Skype を使用します。**</span><span class="sxs-lookup"><span data-stu-id="604fb-198">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="604fb-199">左側のナビゲーションで、[**会議**]  >  [**会議ブリッジ**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="604fb-199">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="604fb-200">リストから電話番号を選択し、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="604fb-200">Select a phone number from the list and click **Edit**.</span></span> <span data-ttu-id="604fb-201">Go to the Office 365 admin centerSkype for Business.</span><span class="sxs-lookup"><span data-stu-id="604fb-201">Here you can:</span></span>
    
   - <span data-ttu-id="604fb-202">電話会議で使うために Office 365 によって設定された電話番号を表示する。</span><span class="sxs-lookup"><span data-stu-id="604fb-202">View the phone numbers that are set by Office 365 to be used for Audio Conferencing.</span></span> 
    
   - <span data-ttu-id="604fb-203">場所、およびオーディオ会議自動アテンダントによって使用される主言語を表示します。</span><span class="sxs-lookup"><span data-stu-id="604fb-203">View the location, and the primary language, that will be used by the Audio Conferencing auto attendant.</span></span>

  
<span data-ttu-id="604fb-204">You can select the dial-in conferencing default phone number that will be given to users when they are enabled for dial-in conferencing.[](see-a-list-of-audio-conferencing-numbers-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="604fb-204">See [See a list of Audio Conferencing numbers](see-a-list-of-audio-conferencing-numbers-in-teams.md).</span></span>
  

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="604fb-205">Windows PowerShell の詳細情報</span><span class="sxs-lookup"><span data-stu-id="604fb-205">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="604fb-p112">Windows PowerShell は、ユーザーと、ユーザーに許可されていることと許可されていないことを管理するためにあるということです。Windows PowerShell があれば、一元管理を使用して Office 365 を管理し、複数のタスクを抱えているときに、日常の仕事を簡素化することができます。Windows PowerShell を開始するには、これらのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="604fb-p112">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="604fb-209">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="604fb-209">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="604fb-210">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="604fb-210">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="604fb-211">Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="604fb-211">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
    
## <a name="related-topics"></a><span data-ttu-id="604fb-212">関連トピック</span><span class="sxs-lookup"><span data-stu-id="604fb-212">Related topics</span></span>

<span data-ttu-id="604fb-213">See also</span><span class="sxs-lookup"><span data-stu-id="604fb-213">[Manage the Audio Conferencing settings for a user](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)</span></span>


