---
title: 組織の電話会議の設定を管理する
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: bc9bd328-c5b2-44e5-af15-e02bf00e1c81
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
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
description: 'ユーザーおよびその他のダイヤルイン会議の設定にダイヤルイン会議のライセンスおよび会議 ID を割り当てる手順を参照してください。 '
ms.openlocfilehash: 26d80b71344227aeaec7089e2bb9f9a9dfe32ad2
ms.sourcegitcommit: 527c7dd4c5edc70503ba31e7c689a71d7356b17e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2018
ms.locfileid: "19703670"
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization"></a><span data-ttu-id="998a0-103">組織の電話会議の設定を管理する</span><span class="sxs-lookup"><span data-stu-id="998a0-103">Manage the Audio Conferencing settings for my organization</span></span>

<span data-ttu-id="998a0-104">[] 1 つの場所で Skype for Business と Microsoft Teams のすべての電話会議設定を確認することが、より簡単になります。</span><span class="sxs-lookup"><span data-stu-id="998a0-104">It might be easier for you to see all of the audio conferencing settings for Skype for Business and Microsoft Teams in one place.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="assign-an-audio-conferencing-license"></a><span data-ttu-id="998a0-105">電話会議のライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="998a0-105">Assign an Audio Conferencing license</span></span>

> [!NOTE]
> <span data-ttu-id="998a0-p101">You can't assign licenses using the **Skype for Business admin center**, you must use the Office 365 admin center.</span><span class="sxs-lookup"><span data-stu-id="998a0-p101">You can't assign licenses using the **Skype for Business admin center**. You must use the Office 365 admin center. See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span> 
  
 <span data-ttu-id="998a0-109">最大 20 人までのライセンスを同時に割り当てている場合は、[ ビューの選択] ボックスを使用していずれかのオプションを選択するか、独自のビューを作成することができます。次に [ 編集]、[ 次へ] を 2 回クリックし、ライセンスを選択して、[ 送信] をクリックします。また、Windows Powershell を使用してライセンスを複数のユーザーに割り当てることもできます。操作手順と PowerShell のサンプル スクリプトについては、「Skype for Business と Microsoft Teams のライセンスを割り当てる」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="998a0-109">**To assign a license for a user**</span></span>
  
1. <span data-ttu-id="998a0-110">最大 20 人までのライセンスを同時に割り当てている場合は、[ ビューの選択] ボックスを使用していずれかのオプションを選択するか、独自のビューを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="998a0-110">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="998a0-111">次に [ **編集**]、[ **次へ**] を 2 回クリックし、ライセンスを選択して、[  > ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="998a0-111">In the left navigation of the **Office 365 admin center**, go to **Users** > **Active users**, and then select the user or users from the list of available users.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="998a0-p102">また、Windows Powershell を使用してライセンスを複数のユーザーに割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="998a0-p102">If you are assigning licenses to up to 20 users at the same time, you can use the **Select a view** drop-down then choose one of the options or create your own view. Then click **Edit**, **Next** twice then select the license and click **Submit**. You can also assign licenses to multiple users by using Windows Powershell. For instructions and sample PowerShell scripts, see [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span> 
  
3. <span data-ttu-id="998a0-116">ライセンスの詳細については、「**Skype for Business と Microsoft Teams のアドオン ライセンス**」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="998a0-116">In the Action pane under **Product licenses**, click **Edit**.</span></span> 
    
4. <span data-ttu-id="998a0-p103">ライセンスを割り当てると、電話会議プロバイダーのリストに Microsoft が表示されなくなることがあります。この場合は、Office 365 管理センターからログアウトするか、CTRL キーを押しながら F5 キーを押してブラウザーのウィンドウを更新します。</span><span class="sxs-lookup"><span data-stu-id="998a0-p103">On the **Product Licenses** page, turn on **Audio Conferencing** and then click **Save**. For more on licensing, see [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
    
> [!NOTE]
> <span data-ttu-id="998a0-p104">ユーザーに会議 ID を割り当てる</span><span class="sxs-lookup"><span data-stu-id="998a0-p104">After you assign the license, Microsoft might not appear initially in the list as an audio conferencing provider. If this happens, either log out of the Office 365 admin center or press CTRL+F5 to refresh the browser window.</span></span> 
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a><span data-ttu-id="998a0-121">Skype for Business 管理センターまたは Windows PowerShell を使用すると、ユーザーへのメール送信を有効または無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="998a0-121">Enable or disable emails sent to audio conferencing users</span></span>

<span data-ttu-id="998a0-122">![チーム ・ ロゴ ・ 30x30.png](../images/teams-logo-30x30.png) **、マイクロソフトのチームとビジネス管理センターの Skype を使用します。**</span><span class="sxs-lookup"><span data-stu-id="998a0-122">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="998a0-123">左側のナビゲーションでは、**会議**に移動 > **会議ブリッジ**です。</span><span class="sxs-lookup"><span data-stu-id="998a0-123">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="998a0-124">**会議ブリッジ**のページの上部には、**ブリッジの設定**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="998a0-124">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="998a0-125">**ブリッジの設定**ウィンドウで、有効または、**ユーザーのダイヤルインの設定を変更する場合に e メールを自動的に送信**を無効にします。</span><span class="sxs-lookup"><span data-stu-id="998a0-125">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="998a0-126">[ **保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="998a0-126">Click **Save**.</span></span>

<span data-ttu-id="998a0-127">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Skype for Business の管理センターを使用する**</span><span class="sxs-lookup"><span data-stu-id="998a0-127">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
  
1. <span data-ttu-id="998a0-128">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="998a0-128">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="998a0-129">On the **Microsoft bridge settings** page, check or uncheck the  > .</span><span class="sxs-lookup"><span data-stu-id="998a0-129">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="998a0-130">電話会議の設定を使用してユーザーにメールを送信することもできます。これには、ユーザーの電話会議プロパティに移動して、[ **電話会議情報をメールで送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="998a0-130">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>
    
4. <span data-ttu-id="998a0-131">ユーザーの電話会議プロパティに移動し、[ **電話会議情報をメールで送信**] をクリックすると、電話会議の設定が含まれるメールをユーザーに送信することもできます。会議 ID と電話会議用の既定の電話番号は会議出席依頼に記載されていますが、PIN は記載されていません。</span><span class="sxs-lookup"><span data-stu-id="998a0-131">Click **Save**.</span></span>
    
    <span data-ttu-id="998a0-p105">ユーザーの電話会議プロパティに移動し、[ **電話会議情報をメールで送信**] をクリックすると、電話会議の設定が含まれるメールをユーザーに送信することもできます。</span><span class="sxs-lookup"><span data-stu-id="998a0-p105">You can also send emails to the user with the audio conferencing settings by going to the user's audio conferencing properties and clicking **Send conference info via email**. The conference ID and default audio conferencing phone number is included on the meeting invite but not the PIN.</span></span>
    
    <span data-ttu-id="998a0-134">You can also send emails to the user with the dial-in conferencing settings, by going to the user's properties > Dial-in conferencingSend conference info via email.</span><span class="sxs-lookup"><span data-stu-id="998a0-134">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>
    
 <span data-ttu-id="998a0-135">The conference ID and default dial-in conferencing phone number is included on the meeting invite but not the PIN.</span><span class="sxs-lookup"><span data-stu-id="998a0-135">**Using Windows PowerShell**</span></span>
  
- <span data-ttu-id="998a0-136">Windows PowerShell を使用する</span><span class="sxs-lookup"><span data-stu-id="998a0-136">You can also use the Windows PowerShell and run:</span></span> 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $true|$false
  ```

    <span data-ttu-id="998a0-137">[](https://go.microsoft.com/fwlink/?LinkId=627285)Windows PowerShell を使用して、次を実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="998a0-137">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) to manage other settings for your organization, including email.</span></span>
    
## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a><span data-ttu-id="998a0-138">You can also use the Windows PowerShell and run:</span><span class="sxs-lookup"><span data-stu-id="998a0-138">Change the sender's contact information in email messages sent to users</span></span>

<span data-ttu-id="998a0-p106">ユーザーに送信されるメール メッセージの、差出人の連絡先情報を変更する</span><span class="sxs-lookup"><span data-stu-id="998a0-p106">You can make changes to the email that is automatically sent to your users, including the actual email address and the display name of the sender's contact information. By default, the sender of the emails is Office 365, but you can change the email address and display name using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet. To make changes to the email address that is sending the email to the users, you must:</span></span>
  
- <span data-ttu-id="998a0-142">Enter the email display name in the  _SendEmailFromDisplayName_ parameter.</span><span class="sxs-lookup"><span data-stu-id="998a0-142">Enter the email address in the _SendEmailFromAddress_ parameter.</span></span>
    
- <span data-ttu-id="998a0-143">メールの差出人のメール アドレスやメールの表示名など、ユーザーに送信したメールの内容を変更するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="998a0-143">Enter the email display name in the  _SendEmailFromDisplayName_ parameter.</span></span>
    
- <span data-ttu-id="998a0-144">メール アドレス情報を変更したい場合は、カスタムのメール アドレスから送信されるメールが、組織の受信メール ポリシーで許可されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="998a0-144">Set the _SendEmailOverride_ parameter to _True_.</span></span>
    
<span data-ttu-id="998a0-145">If you want to change the email address information, you need to make sure that the inbound email policies of your organization allow emails that come from the custom email address.</span><span class="sxs-lookup"><span data-stu-id="998a0-145">You can make changes to the email sent to users, such as the email address that the email is sent from or the display name for the email by running:</span></span>
  
```
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

<span data-ttu-id="998a0-146">「ダイヤルイン会議の設定が変更されたユーザーにメールを自動的に送信する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="998a0-146">If you want to change the email address information, you need to make sure that the inbound email policies of your organization allow emails that come from the custom email address.</span></span>
  
<span data-ttu-id="998a0-147">会議 ID をリセットする</span><span class="sxs-lookup"><span data-stu-id="998a0-147">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet to manage other settings for your organization, including email.</span></span>
  
<span data-ttu-id="998a0-148">[](emails-sent-to-users-when-their-settings-change.md)職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="998a0-148">See [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md).</span></span>
  
## <a name="reset-the-meeting-conference-id"></a><span data-ttu-id="998a0-149">Sign in to Office 365 with your work or school account.</span><span class="sxs-lookup"><span data-stu-id="998a0-149">Reset the meeting conference ID</span></span>

<span data-ttu-id="998a0-150">![チーム ・ ロゴ ・ 30x30.png](../images/teams-logo-30x30.png) **、マイクロソフトのチームとビジネス管理センターの Skype を使用します。**</span><span class="sxs-lookup"><span data-stu-id="998a0-150">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="998a0-151">左側のナビゲーションでは、**ユーザー**] をクリックしてで使用可能なユーザーの一覧からユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="998a0-151">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="998a0-152">ページの上部で、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="998a0-152">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="998a0-153">[**オーディオ会議**、**会議 ID のリセット**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="998a0-153">Under **Audio Conferencing**, click **Reset conference ID**.</span></span>  

4. <span data-ttu-id="998a0-154">**会議 ID をリセットしますか?** ] ウィンドウで、[**リセット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="998a0-154">In the **Reset conference ID?** window, click **Reset**.</span></span> <span data-ttu-id="998a0-155">It's enabled by default.</span><span class="sxs-lookup"><span data-stu-id="998a0-155">A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled.</span></span> <span data-ttu-id="998a0-156">After a new conference ID is created, the old conference ID can't be used by callers. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. The users can use Skype for Business Meeting Migration Tool to update their existing meetings. To see how to download, install and run the Lync Meeting Update Tool, see:> Meeting Update Tool for Skype for Business and LyncSkype for Business Online, Meeting Migration Tool (64-bit)Skype for Business Online, Meeting Migration Tool (32-bit)</span><span class="sxs-lookup"><span data-stu-id="998a0-156">It's enabled by default.</span></span>

<span data-ttu-id="998a0-157">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Skype for Business の管理センターを使用する**</span><span class="sxs-lookup"><span data-stu-id="998a0-157">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>  

1. <span data-ttu-id="998a0-158">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="998a0-158">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="998a0-159">In the Skype for Business admin centerDial-in conferencing, in the Action page under Conference ID click Reset.</span><span class="sxs-lookup"><span data-stu-id="998a0-159">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="998a0-160">In the ** Reset conference ID?** window, click **Yes**. A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled. It's enabled by default.</span><span class="sxs-lookup"><span data-stu-id="998a0-160">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and in the Action pane under **Conference ID**, click **Reset**.</span></span>
    
4. <span data-ttu-id="998a0-p108">In the ** Reset conference ID?** window, click **Yes**.</span><span class="sxs-lookup"><span data-stu-id="998a0-p108">In the **Reset conference ID?** window, click **Yes**. A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled. It's enabled by default.</span></span>
    
    > [!IMPORTANT]
    >  <span data-ttu-id="998a0-p109">After a new conference ID is created, the old conference ID can't be used by callers.</span><span class="sxs-lookup"><span data-stu-id="998a0-p109">After a new conference ID is created, the old conference ID can't be used by callers. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. The users can use the Skype for Business Meeting Migration Tool to update their existing meetings. To see how to download, install, and run the Skype for Business Meeting Update Tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](http://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span></span>
  
<span data-ttu-id="998a0-168">[](reset-a-conference-id-for-a-user.md)Reset a conference organizer's PIN</span><span class="sxs-lookup"><span data-stu-id="998a0-168">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).</span></span>
  
## <a name="reset-a-conference-organizers-pin"></a><span data-ttu-id="998a0-169">静的会議 ID は自動的に作成されユーザーに割り当てられますが、ユーザーがそれを使いたくないため特定の番号に設定しようと考える場合や、ユーザーが会議 ID を覚えられない、または紛失してしまう場合があります。Skype for Business 管理センターおよび Windows PowerShell を使用すると、ユーザーの会議 ID を表示、変更、リセットすることができます。</span><span class="sxs-lookup"><span data-stu-id="998a0-169">Reset a conference organizer's PIN</span></span>

<span data-ttu-id="998a0-170">ユーザーをスケジュールする会議ごとに固有の会議 ID が割り当てられますを取得</span><span class="sxs-lookup"><span data-stu-id="998a0-170">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="998a0-171">会議 ID が自動的に作成され、ユーザーに割り当てられているがあります、ユーザーは、この 1 つを使用する場合は、特定の数に設定するとユーザーが覚えられないか、会議 ID が失われています。</span><span class="sxs-lookup"><span data-stu-id="998a0-171">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="998a0-172">ユーザーが電話会議で有効になるか、PIN がリセットされた場合、ユーザーは自分の PIN が含まれるメールを受信します。ただし、メールの自動送信を無効にしても、PIN リセットのメールは送信されません。管理者は、ユーザーに PIN を手動で送信する必要があります。PIN をリセットした後、PIN が表示されるのは 1 回だけです。リセットの直後に 1 回表示された後は、ユーザーのプロパティには PIN に代わって "\*\*\*\*\*" が表示されます。</span><span class="sxs-lookup"><span data-stu-id="998a0-172">You can use the Skype for Business admin center and Windows PowerShell to view, change, and reset their conference ID.</span></span>

<span data-ttu-id="998a0-173">![チーム ・ ロゴ ・ 30x30.png](../images/teams-logo-30x30.png) **、マイクロソフトのチームとビジネス管理センターの Skype を使用します。**</span><span class="sxs-lookup"><span data-stu-id="998a0-173">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="998a0-174">左側のナビゲーションでは、**ユーザー**] をクリックしてで使用可能なユーザーの一覧からユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="998a0-174">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="998a0-175">ページの上部で、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="998a0-175">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="998a0-176">**オーディオ会議**では、[ **PIN のリセット**] をクリックし、[**リセット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="998a0-176">Under **Audio Conferencing**, click **Reset PIN**, and then click **Reset**.</span></span> 
  
<span data-ttu-id="998a0-177">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Skype for Business の管理センターを使用する**</span><span class="sxs-lookup"><span data-stu-id="998a0-177">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span> 

1. <span data-ttu-id="998a0-178">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="998a0-178">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="998a0-179">Sign in to Office 365 with your work or school account.</span><span class="sxs-lookup"><span data-stu-id="998a0-179">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="998a0-180">管理者は、ユーザーに PIN を手動で送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="998a0-180">Click **Users**, and then select the user that you want to reset the PIN for.</span></span>
    
4. <span data-ttu-id="998a0-181">PIN をリセットした後、PIN が表示されるのは 1 回だけです。</span><span class="sxs-lookup"><span data-stu-id="998a0-181">In the Action pane, under **PIN**, click **Reset**.</span></span>
    
<span data-ttu-id="998a0-p111">リセットの直後に 1 回表示された後は、ユーザーのプロパティには PIN に代わって "\*\*\*\*\*" が表示されます。</span><span class="sxs-lookup"><span data-stu-id="998a0-p111">Users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset. But if you have disabled automatically sending emails, a PIN reset email won't be sent and you will have to manually send the PIN to the user. The PIN will only be shown once after it has been reset. After it's displayed just after being reset, the PIN won't be shown anymore on the user properties; instead, \*\*\*\*\* will be shown.</span></span> 
  
<span data-ttu-id="998a0-186">[オーディオ会議の PIN のリセット](reset-the-audio-conferencing-pin.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="998a0-186">See [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin.md).</span></span>
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="998a0-187">電話会議の情報が記載されたメールをユーザーに送信する</span><span class="sxs-lookup"><span data-stu-id="998a0-187">Send an email with Audio Conferencing information to a user</span></span>

<span data-ttu-id="998a0-188">![チーム ・ ロゴ ・ 30x30.png](../images/teams-logo-30x30.png) **、マイクロソフトのチームとビジネス管理センターの Skype を使用します。**</span><span class="sxs-lookup"><span data-stu-id="998a0-188">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="998a0-189">左側のナビゲーションでは、**ユーザー**] をクリックしてで使用可能なユーザーの一覧からユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="998a0-189">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="998a0-190">ページの上部で、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="998a0-190">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="998a0-191">[**オーディオ会議****電子メールで会議の情報を送信**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="998a0-191">Under **Audio Conferencing**, click **Send conference info in email**.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="998a0-192">この操作を行っても、電話会議の PIN はユーザーに送信されません。</span><span class="sxs-lookup"><span data-stu-id="998a0-192">When you do this, the audio conferencing PIN isn't sent to the user.</span></span> 

<span data-ttu-id="998a0-193">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Skype for Business の管理センターを使用する**</span><span class="sxs-lookup"><span data-stu-id="998a0-193">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>  

1. <span data-ttu-id="998a0-194">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="998a0-194">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="998a0-195">Sign in to Office 365 with your work or school account.</span><span class="sxs-lookup"><span data-stu-id="998a0-195">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="998a0-196">Go to the Office 365 admin centerSkype for Business and in the left navigation click Dial-in conferencing</span><span class="sxs-lookup"><span data-stu-id="998a0-196">Click **Users**, and then select the user that you want to reset the PIN for.</span></span>
    
4. <span data-ttu-id="998a0-197">操作ウィンドウで、[ **電話会議情報をメールで送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="998a0-197">In the Action pane, click **Send conference info via email**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="998a0-198">この操作を行っても、電話会議の PIN はユーザーに送信されません。</span><span class="sxs-lookup"><span data-stu-id="998a0-198">When you do this, the audio conferencing PIN isn't sent to the user.</span></span> 
  
<span data-ttu-id="998a0-199">When you do this, the dial-in conferencing PIN isn't sent to the user.</span><span class="sxs-lookup"><span data-stu-id="998a0-199">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>
  
## <a name="setting-the-phone-numbers-included-on-invites"></a><span data-ttu-id="998a0-200">携帯電話への招待に含まれている番号を設定します。</span><span class="sxs-lookup"><span data-stu-id="998a0-200">Setting the phone numbers included on invites</span></span>

<span data-ttu-id="998a0-201">![チーム ・ ロゴ ・ 30x30.png](../images/teams-logo-30x30.png) **、マイクロソフトのチームとビジネス管理センターの Skype を使用します。**</span><span class="sxs-lookup"><span data-stu-id="998a0-201">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="998a0-202">左側のナビゲーションでは、**ユーザー**] をクリックしてで使用可能なユーザーの一覧からユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="998a0-202">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="998a0-203">**オーディオ会議**の横にある [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="998a0-203">Next to **Audio Conferencing**, click **Edit**.</span></span>
 
3. <span data-ttu-id="998a0-204">**オーディオ会議**のウィンドウで**電話番号**を設定でき、許可された場合、**フリー ダイヤルの番号**です。</span><span class="sxs-lookup"><span data-stu-id="998a0-204">In the **Audio Conferencing** pane, you can set the **Toll number** and, if allowed, the **Toll-free number**.</span></span>

4. <span data-ttu-id="998a0-205">[ **保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="998a0-205">Click **Save**.</span></span>

<span data-ttu-id="998a0-206">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Skype for Business の管理センターを使用する**</span><span class="sxs-lookup"><span data-stu-id="998a0-206">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>  
  
1. <span data-ttu-id="998a0-207">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="998a0-207">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="998a0-208">Sign in to Office 365 with your work or school account.</span><span class="sxs-lookup"><span data-stu-id="998a0-208">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="998a0-p112">Go to the **Office 365 admin center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="998a0-p112">In the left navigation, go to **Audio conferencing** > **Users**. Select the user that you want to enable for Audio Conferencing.</span></span>
    
4. <span data-ttu-id="998a0-211">[操作] ウィンドウで、**有料電話番号**を設定することができ、許可された場合、**フリー ダイヤルの番号**です。</span><span class="sxs-lookup"><span data-stu-id="998a0-211">In the Action pane, you can set the **Toll number** and, if allowed, the **Toll-free number**.</span></span>

5. <span data-ttu-id="998a0-212">The default dial-in conferencing phone number of a user is the number that is shown on the meeting invite when they schedule a meeting.</span><span class="sxs-lookup"><span data-stu-id="998a0-212">Click **Save**.</span></span>
    
<span data-ttu-id="998a0-213">「[出席依頼に含まれている会議の開催者のために電話会議の電話番号を設定する](set-the-phone-numbers-included-on-invites.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="998a0-213">See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites.md).</span></span>
  
  
## <a name="choosing-audio-conferencing-bridge-settings"></a><span data-ttu-id="998a0-214">オーディオ会議ブリッジの設定を選択します。</span><span class="sxs-lookup"><span data-stu-id="998a0-214">Choosing audio conferencing bridge settings</span></span>

<span data-ttu-id="998a0-215">**** Setting dial-in conferencing bridge settings</span><span class="sxs-lookup"><span data-stu-id="998a0-215">**Set the meeting experience when callers join a meeting**</span></span>

 <span data-ttu-id="998a0-216">![チーム ・ ロゴ ・ 30x30.png](../images/teams-logo-30x30.png) **、マイクロソフトのチームとビジネス管理センターの Skype を使用します。**</span><span class="sxs-lookup"><span data-stu-id="998a0-216">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="998a0-217">左側のナビゲーションでは、**会議**に移動 > **会議ブリッジ**です。</span><span class="sxs-lookup"><span data-stu-id="998a0-217">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="998a0-218">**会議ブリッジ**のページの上部には、**ブリッジの設定**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="998a0-218">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="998a0-219">**ブリッジの設定**ウィンドウを有効にするまたは**ミーティングのエントリと終了の通知**を無効にします。</span><span class="sxs-lookup"><span data-stu-id="998a0-219">In the **Bridge settings** pane, enable or disable **Meeting entry and exit notifications**.</span></span>

    <span data-ttu-id="998a0-220">これは既定で有効になります。</span><span class="sxs-lookup"><span data-stu-id="998a0-220">This is enabled by default.</span></span> <span data-ttu-id="998a0-221">このオプションを無効にした場合データを入力したり、会議を離れるときに既定では、会議に参加しているユーザーが通知されません。</span><span class="sxs-lookup"><span data-stu-id="998a0-221">If you disable this option, users who have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span></span>

4. <span data-ttu-id="998a0-222">**開始/終了のお知らせの種類**、[**トーン**] または [**名前または電話番号**を選択します。</span><span class="sxs-lookup"><span data-stu-id="998a0-222">Under **Entry/exit announcement type**, choose either **Tones** or **Names or phone numbers**.</span></span> 

    <span data-ttu-id="998a0-223">**名前や電話番号**を選択する場合を有効にするまたは、**ミーティングに参加する前に自分の名前を記録するための呼び出し元の確認**を無効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="998a0-223">If you choose **Names or phone numbers**, you can also choose to enable or disable **Ask callers to record their name before joining the meeting**.</span></span> 

1. <span data-ttu-id="998a0-224">[ **保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="998a0-224">Click **Save**.</span></span>

<span data-ttu-id="998a0-225">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Skype for Business の管理センターを使用する**</span><span class="sxs-lookup"><span data-stu-id="998a0-225">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span> 
  
1. <span data-ttu-id="998a0-226">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="998a0-226">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="998a0-227">Sign in to Office 365 with your work or school account.</span><span class="sxs-lookup"><span data-stu-id="998a0-227">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="998a0-228">Go to the **Office 365 admin center****** > .</span><span class="sxs-lookup"><span data-stu-id="998a0-228">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="998a0-229">In the Skype for Business admin center, in the left navigation go to dial-in conferencingMicrosoft bridge settings.</span><span class="sxs-lookup"><span data-stu-id="998a0-229">Under **Meeting join experience**, select the following actions:</span></span>
    
  - <span data-ttu-id="998a0-p114">**Enable meeting entry and exit notifications to be turned on** This is selected by default. However if you uncheck it, users that have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span><span class="sxs-lookup"><span data-stu-id="998a0-p114">**Enable meeting entry and exit notifications to be turned on** This is selected by default. If you clear this check box, users who have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span></span>
    
    <span data-ttu-id="998a0-232">変更したら [ **保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="998a0-232">This can be set on a meeting-by-meeting basis when a user joins a meeting using a Skype for Business or Microsoft Teams app and they modify the **Announce when people enter or leave** setting in the Skype Meeting or Microsoft Teams **Options** menu of the meeting.</span></span>
    
  - <span data-ttu-id="998a0-p115">「**電話会議ブリッジの設定を変更する**」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="998a0-p115">**Ask callers to record their name before joining the meeting** This is selected by default. If you clear this check box, callers won't be asked to record their name before they join a meeting.</span></span>
    
5. <span data-ttu-id="998a0-235">Sign in to Office 365 with your work or school account.</span><span class="sxs-lookup"><span data-stu-id="998a0-235">After you make your changes, click **Save**.</span></span>
    
<span data-ttu-id="998a0-236">Go to the Office 365 admin centerSkype for Business.</span><span class="sxs-lookup"><span data-stu-id="998a0-236">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>
  
 <span data-ttu-id="998a0-237">In the Skype for Business admin center, in the left navigation go to dial-in conferencingMicrosoft bridge settings.</span><span class="sxs-lookup"><span data-stu-id="998a0-237">**Set the PIN length for meetings**</span></span>

 <span data-ttu-id="998a0-238">![チーム ・ ロゴ ・ 30x30.png](../images/teams-logo-30x30.png) **、マイクロソフトのチームとビジネス管理センターの Skype を使用します。**</span><span class="sxs-lookup"><span data-stu-id="998a0-238">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="998a0-239">左側のナビゲーションでは、**会議**に移動 > **会議ブリッジ**です。</span><span class="sxs-lookup"><span data-stu-id="998a0-239">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="998a0-240">**会議ブリッジ**のページの上部には、**ブリッジの設定**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="998a0-240">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="998a0-241">**ブリッジの設定**ウィンドウで、 **PIN の長さ**] ボックスの一覧で、[暗証番号 (pin) に使用桁の番号を入力し、し、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="998a0-241">In the **Bridge settings** pane, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>

    <span data-ttu-id="998a0-p116">The PIN can only be from 4 to 12 digits.</span><span class="sxs-lookup"><span data-stu-id="998a0-p116">The PIN must be between 4 and 12 digits. The default is 5.</span></span>

<span data-ttu-id="998a0-244">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Skype for Business の管理センターを使用する**</span><span class="sxs-lookup"><span data-stu-id="998a0-244">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span> 
  
1. <span data-ttu-id="998a0-245">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="998a0-245">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="998a0-246">Sign in to Office 365 with your work or school account.</span><span class="sxs-lookup"><span data-stu-id="998a0-246">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="998a0-247">既定値は 5 です。</span><span class="sxs-lookup"><span data-stu-id="998a0-247">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="998a0-248">The PIN can only be from 4 to 12 digits. The default is 5.</span><span class="sxs-lookup"><span data-stu-id="998a0-248">Under **Security**, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>
    
    <span data-ttu-id="998a0-p117">The PIN can only be from 4 to 12 digits.</span><span class="sxs-lookup"><span data-stu-id="998a0-p117">The PIN must be between 4 and 12 digits. The default is 5.</span></span>
    
<span data-ttu-id="998a0-251">[](change-the-settings-for-an-audio-conferencing-bridge.md)職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="998a0-251">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>
  
 <span data-ttu-id="998a0-252">Sign in to Office 365 with your work or school account.</span><span class="sxs-lookup"><span data-stu-id="998a0-252">**Enable or disable email from being sent to audio users**</span></span>

 <span data-ttu-id="998a0-253">![チーム ・ ロゴ ・ 30x30.png](../images/teams-logo-30x30.png) **、マイクロソフトのチームとビジネス管理センターの Skype を使用します。**</span><span class="sxs-lookup"><span data-stu-id="998a0-253">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="998a0-254">左側のナビゲーションでは、**会議**に移動 > **会議ブリッジ**です。</span><span class="sxs-lookup"><span data-stu-id="998a0-254">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="998a0-255">**会議ブリッジ**のページの上部には、**ブリッジの設定**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="998a0-255">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="998a0-256">**ブリッジの設定**ウィンドウを有効にするか **、オーディオ会議の設定を変更する場合、ユーザーに e メールを自動的に送信**を無効にします。</span><span class="sxs-lookup"><span data-stu-id="998a0-256">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their audio conferencing settings change**.</span></span>

4. <span data-ttu-id="998a0-257">[ **保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="998a0-257">Click **Save**.</span></span> 
 
    <span data-ttu-id="998a0-258">ユーザーのオーディオ会議のプロパティに移動し、**電子メールで会議の情報を送信**] をクリックしてユーザーに、電話会議の設定を使用する電子メールを送信することも。</span><span class="sxs-lookup"><span data-stu-id="998a0-258">You can also send email to the user with the audio conferencing settings, by going to the user's audio conferencing properties and clicking **Send conference info in email**.</span></span>
    
    <span data-ttu-id="998a0-259">この操作を行うと、会議 ID と電話会議の番号のみが含まれるメールが送信されますが、そのメールに PIN は含まれません。</span><span class="sxs-lookup"><span data-stu-id="998a0-259">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span></span>

<span data-ttu-id="998a0-260">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Skype for Business の管理センターを使用する**</span><span class="sxs-lookup"><span data-stu-id="998a0-260">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span> 
  
1. <span data-ttu-id="998a0-261">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="998a0-261">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="998a0-262">On the **Microsoft bridge settings** page, check or uncheck the  > .</span><span class="sxs-lookup"><span data-stu-id="998a0-262">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="998a0-263">電話会議の設定を使用してユーザーにメールを送信することもできます。これには、ユーザーの電話会議プロパティに移動して、[ **電話会議情報をメールで送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="998a0-263">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>
    
4. <span data-ttu-id="998a0-264">電話会議の設定を使用してユーザーにメールを送信することもできます。</span><span class="sxs-lookup"><span data-stu-id="998a0-264">Click **Save**.</span></span>
    
    <span data-ttu-id="998a0-265">これには、ユーザーの電話会議プロパティに移動して、[ **電話会議情報をメールで送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="998a0-265">You can also send email to the user with the audio conferencing settings, by going to the user's audio conferencing properties and clicking **Send conference info via email**.</span></span>
    
    <span data-ttu-id="998a0-266">この操作を行うと、会議 ID と電話会議の番号のみが含まれるメールが送信されますが、そのメールに PIN は含まれません。</span><span class="sxs-lookup"><span data-stu-id="998a0-266">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span></span>
    
    <span data-ttu-id="998a0-267">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span><span class="sxs-lookup"><span data-stu-id="998a0-267">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>
    
## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a><span data-ttu-id="998a0-268">参照してくださいし、オーディオ会議ブリッジに (既定値) をプライマリとセカンダリ (代替) の言語を設定します。</span><span class="sxs-lookup"><span data-stu-id="998a0-268">See and set the primary (default) and secondary (alternate) languages on an audio conferencing bridge</span></span>

 <span data-ttu-id="998a0-269">![チーム ・ ロゴ ・ 30x30.png](../images/teams-logo-30x30.png) **、マイクロソフトのチームとビジネス管理センターの Skype を使用します。**</span><span class="sxs-lookup"><span data-stu-id="998a0-269">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="998a0-270">左側のナビゲーションでは、**会議**に移動 > **会議ブリッジ**です。</span><span class="sxs-lookup"><span data-stu-id="998a0-270">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="998a0-271">リストから電話番号を選択し、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="998a0-271">Select a phone number from the list and click **Edit**.</span></span>

3. <span data-ttu-id="998a0-272">[**既定の言語**および **(省略可能) 別の言語**の言語を選択してください。</span><span class="sxs-lookup"><span data-stu-id="998a0-272">Choose the languages you want under **Default language** and **Alternate languages (optional)**.</span></span>

<span data-ttu-id="998a0-273">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Skype for Business の管理センターを使用する**</span><span class="sxs-lookup"><span data-stu-id="998a0-273">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span> 

1. <span data-ttu-id="998a0-274">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="998a0-274">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="998a0-275">Sign in to Office 365 with your work or school account.</span><span class="sxs-lookup"><span data-stu-id="998a0-275">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="998a0-276">Go to the **Office 365 admin center********Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="998a0-276">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and then click **Microsoft bridge**.</span></span>
    
4. <span data-ttu-id="998a0-277">リストから電話番号を選択し、操作ウィンドウで [ **言語を設定**] をクリックしてから、[ **言語を設定**] ページで [ **第 1 言語**] リストをクリックして、サポートされている言語の完全なリストを表示します。</span><span class="sxs-lookup"><span data-stu-id="998a0-277">Select a phone number from the list, click **Set languages** in the Action pane, and then on the **Set languages** page, click the use the **Primary language** list to view the complete list of supported languages.</span></span>
    
    <span data-ttu-id="998a0-p118">Microsoft を電話会議プロバイダーとして選ぶときに、サポートされる第 1 言語と第 2 言語を設定することもできます。発信者に対する言語の表示順は、リストで言語を選んだ順序になります。</span><span class="sxs-lookup"><span data-stu-id="998a0-p118">You can also set the primary and secondary languages that are supported when you select Microsoft as the audio conferencing provider. The order that you select in the lists is the same order in which languages will be presented to callers.</span></span>
    
<span data-ttu-id="998a0-280">You can also set the primary and secondary languages that are supported when you select Microsoft as the dial-in conferencing provider. The order that you select in the drop-downs will be the order of the languages that will be presented to the callers.</span><span class="sxs-lookup"><span data-stu-id="998a0-280">See [Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing.md).</span></span>
  
## <a name="see-audio-conferencing-dial-in-numbers"></a><span data-ttu-id="998a0-281">You can also set the primary and secondary languages that are supported when you select Microsoft as the dial-in conferencing provider.</span><span class="sxs-lookup"><span data-stu-id="998a0-281">See audio conferencing dial-in numbers</span></span>

<span data-ttu-id="998a0-282">![チーム ・ ロゴ ・ 30x30.png](../images/teams-logo-30x30.png) **、マイクロソフトのチームとビジネス管理センターの Skype を使用します。**</span><span class="sxs-lookup"><span data-stu-id="998a0-282">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="998a0-283">左側のナビゲーションでは、**会議**に移動 > **会議ブリッジ**です。</span><span class="sxs-lookup"><span data-stu-id="998a0-283">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="998a0-284">リストから電話番号を選択し、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="998a0-284">Select a phone number from the list and click **Edit**.</span></span> <span data-ttu-id="998a0-285">Go to the Office 365 admin centerSkype for Business.</span><span class="sxs-lookup"><span data-stu-id="998a0-285">Here you can:</span></span>
    
  - <span data-ttu-id="998a0-286">電話会議で使うために Office 365 によって設定された電話番号を表示する。</span><span class="sxs-lookup"><span data-stu-id="998a0-286">View the phone numbers that are set by Office 365 to be used for Audio Conferencing.</span></span> 
    
  - <span data-ttu-id="998a0-287">場所、およびオーディオ会議自動アテンダントによって使用される主言語を表示します。</span><span class="sxs-lookup"><span data-stu-id="998a0-287">View the location, and the primary language, that will be used by the Audio Conferencing auto attendant.</span></span>


<span data-ttu-id="998a0-288">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Skype for Business の管理センターを使用する**</span><span class="sxs-lookup"><span data-stu-id="998a0-288">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>  

1. <span data-ttu-id="998a0-289">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="998a0-289">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="998a0-290">「電話会議のダイヤルイン番号」をご覧ください</span><span class="sxs-lookup"><span data-stu-id="998a0-290">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="998a0-p120">**** 職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="998a0-p120">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge**. Here you can:</span></span>
    
  - <span data-ttu-id="998a0-293">電話会議で使うために Office 365 によって設定された電話番号を表示する。</span><span class="sxs-lookup"><span data-stu-id="998a0-293">View the phone numbers that are set by Office 365 to be used for Audio Conferencing.</span></span> 
    
  - <span data-ttu-id="998a0-294">場所を表示したり、電話会議の自動応答で使用する第 1 言語と第 2 言語を表示したりする。</span><span class="sxs-lookup"><span data-stu-id="998a0-294">View the location, and the primary and secondary languages, that will be used by the Audio Conferencing auto attendant.</span></span>
    
  - <span data-ttu-id="998a0-p121">ユーザーが電話会議で有効になっているときに、ユーザーに渡される既定の電話番号を選択します。ただし、電話会議ブリッジの既定の電話番号が変わっても、既存のユーザーの既定の電話番号は変わりません。</span><span class="sxs-lookup"><span data-stu-id="998a0-p121">Select the default phone number that will be given to users when they are enabled for Audio Conferencing. However, if the default phone number of the audio conferencing bridge changes, the default phone number for existing users won't change.</span></span>
    
<span data-ttu-id="998a0-297">You can select the dial-in conferencing default phone number that will be given to users when they are enabled for dial-in conferencing. However, if the default phone number of the dial-in conferencing bridge changes, the default phone number for existing users won't change.</span><span class="sxs-lookup"><span data-stu-id="998a0-297">You can go to **Audio conferencing** > **Users** and select the user's properties to change the default number for a user by choosing a new number from the list of numbers that are available in your organization.</span></span>
  
<span data-ttu-id="998a0-298">You can select the dial-in conferencing default phone number that will be given to users when they are enabled for dial-in conferencing.</span><span class="sxs-lookup"><span data-stu-id="998a0-298">See [See a list of Audio Conferencing numbers](see-a-list-of-audio-conferencing-numbers.md).</span></span>
  
## <a name="sfb-logo-30x30pngimagessfb-logo-30x30png-see-a-list-of-users-that-are-enabled"></a>![デバイス ・ ロゴ ・ 30x30.png](../images/sfb-logo-30x30.png) <span data-ttu-id="998a0-300">However, if the default phone number of the dial-in conferencing bridge changes, the default phone number for existing users won't change.</span><span class="sxs-lookup"><span data-stu-id="998a0-300">See a list of users that are enabled</span></span>

1. <span data-ttu-id="998a0-301">You can go to Dial-in conferencingDial-in users and select the user's properties to change the default number for a user by choosing a new number from the list of numbers that are available in your organization.</span><span class="sxs-lookup"><span data-stu-id="998a0-301">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="998a0-302">有効になっているユーザーのリストを表示する</span><span class="sxs-lookup"><span data-stu-id="998a0-302">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="998a0-303">**** 職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="998a0-303">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**> and then **Users**.</span></span>
    
<span data-ttu-id="998a0-304">Sign in to Office 365 with your work or school account.</span><span class="sxs-lookup"><span data-stu-id="998a0-304">See [See a list of users that are enabled for Audio Conferencing](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).</span></span>
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="998a0-305">Go to the Office 365 admin centerSkype for Business.</span><span class="sxs-lookup"><span data-stu-id="998a0-305">Want to know how to manage with Windows PowerShell?</span></span>

<span data-ttu-id="998a0-p122">In the Skype for Business admin center, in the left navigation go to Dial-in conferencing> and then Dial-in users.</span><span class="sxs-lookup"><span data-stu-id="998a0-p122">There are several settings that you can manage at the organization level using Windows PowerShell. This makes it easy to apply settings to all of your users.</span></span> 
    
<span data-ttu-id="998a0-308">[](https://go.microsoft.com/fwlink/?LinkId=627324)Windows PowerShell を使用して組織レベルで管理できる複数の設定があります。</span><span class="sxs-lookup"><span data-stu-id="998a0-308">To get more help on each cmdlet, see [Skype for Business Online cmdlets](https://go.microsoft.com/fwlink/?LinkId=627324).</span></span>

<span data-ttu-id="998a0-309">このため、簡単にこれらの設定をすべてのユーザーに適用できます。</span><span class="sxs-lookup"><span data-stu-id="998a0-309">Here are the organization-level settings:</span></span> 
 
- <span data-ttu-id="998a0-310">組織レベルの設定を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="998a0-310">**Setting entry/exit notifications** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableEntryExitNotifications $true|$false 
  ```

- <span data-ttu-id="998a0-311">There are several settings that you can manage settings at the organization level using Windows PowerShell. This makes it easy to make these settings and have them apply to all of your users. Here are the organization level settings:</span><span class="sxs-lookup"><span data-stu-id="998a0-311">**Setting name recording** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableNameRecording $true|false
  ```

- <span data-ttu-id="998a0-312">There are several settings that you can manage settings at the organization level using Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="998a0-312">**Setting the PIN length** The default is 5.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -PinLength 7
  ```

- <span data-ttu-id="998a0-313">This makes it easy to make these settings and have them apply to all of your users.</span><span class="sxs-lookup"><span data-stu-id="998a0-313">**Setting only dial-in meetings from a phone** The default _$false_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true|$false
  ```

- <span data-ttu-id="998a0-314">Here are the organization level settings:</span><span class="sxs-lookup"><span data-stu-id="998a0-314">**Setting whether to send email to users** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

- <span data-ttu-id="998a0-315">Windows PowerShell の場合、ユーザーの管理と、ユーザーに許可する操作や許可しない操作の管理に使います。Windows PowerShell により、単一の管理ポイントを使って Office 365 を管理でき、複数の作業を実行する必要があるときに日常業務を合理化できます。Windows PowerShell を使い始めるには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="998a0-315">**Setting whether to send email from a different account** The default is  _$false_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromOverride $true|$false
  ```

- <span data-ttu-id="998a0-316">Windows PowerShell の場合、ユーザーの管理と、ユーザーに許可する操作や許可しない操作の管理に使います。</span><span class="sxs-lookup"><span data-stu-id="998a0-316">**Setting the From address on email that is sent to users** The default is _$null_.</span></span> 
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromAddress
  ```

- <span data-ttu-id="998a0-317">Windows PowerShell により、単一の管理ポイントを使って Office 365 を管理でき、複数の作業を実行する必要があるときに日常業務を合理化できます。</span><span class="sxs-lookup"><span data-stu-id="998a0-317">**Setting the display name for the email that is sent to users** The default is  _$null_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromDisplayName
  ```

 ## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="998a0-318">Windows PowerShell を使い始めるには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="998a0-318">Want to know more about Windows PowerShell</span></span>   
- <span data-ttu-id="998a0-p123">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span><span class="sxs-lookup"><span data-stu-id="998a0-p123">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="998a0-322">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="998a0-322">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="998a0-323">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="998a0-323">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="998a0-p124">多くのユーザーの設定を同時に変更するときなどは、Office 365 管理センターのみを使用するよりも、Windows PowerShell の方に、速度、わかりやすさ、生産性の点で多くのメリットがあります。</span><span class="sxs-lookup"><span data-stu-id="998a0-p124">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time. Learn about these advantages in the following topics:</span></span> 
    
  - <span data-ttu-id="998a0-326">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time.</span><span class="sxs-lookup"><span data-stu-id="998a0-326">[An introduction to Windows PowerShell and Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)</span></span>
    
  - [<span data-ttu-id="998a0-327">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="998a0-327">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="998a0-328">Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行</span><span class="sxs-lookup"><span data-stu-id="998a0-328">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    <span data-ttu-id="998a0-p125">[Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="998a0-p125">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="998a0-331">このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「Skype for Business Online 用 Windows PowerShell モジュール」からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="998a0-331">Related topics</span></span>

<span data-ttu-id="998a0-332">See also</span><span class="sxs-lookup"><span data-stu-id="998a0-332">[Manage the Audio Conferencing settings for a user](manage-the-audio-conferencing-settings-for-a-user.md)</span></span>


