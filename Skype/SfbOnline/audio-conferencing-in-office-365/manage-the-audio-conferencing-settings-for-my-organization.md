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
description: 'See steps to assign a dial-in conferencing license and conference ID to a user, set up a third party conferencing provider, and many other dial-in conferencing settings. '
ms.openlocfilehash: db355e71ff90a43c46900ad2b95b9e8593a9094d
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization"></a><span data-ttu-id="685d2-103">組織の電話会議の設定を管理する</span><span class="sxs-lookup"><span data-stu-id="685d2-103">Manage the Audio Conferencing settings for my organization</span></span>

<span data-ttu-id="685d2-104">[] 1 つの場所で Skype for Business と Microsoft Teams のすべての電話会議設定を確認することが、より簡単になります。</span><span class="sxs-lookup"><span data-stu-id="685d2-104">It might be easier for you to see all of the audio conferencing settings for Skype for Business and Microsoft Teams in one place.</span></span> 
  
## <a name="assign-an-audio-conferencing-license"></a><span data-ttu-id="685d2-105">電話会議のライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="685d2-105">Assign an Audio Conferencing license</span></span>

> [!NOTE]
> <span data-ttu-id="685d2-p101">You can't assign licenses using the **Skype for Business admin center**, you must use the Office 365 admin center.</span><span class="sxs-lookup"><span data-stu-id="685d2-p101">You can't assign licenses using the **Skype for Business admin center**. You must use the Office 365 admin center. See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span> 
  
 <span data-ttu-id="685d2-109">最大 20 人までのライセンスを同時に割り当てている場合は、[ **ビューの選択**] ボックスを使用していずれかのオプションを選択するか、独自のビューを作成することができます。次に [ 編集]、[ 次へ] を 2 回クリックし、ライセンスを選択して、[ 送信] をクリックします。また、Windows Powershell を使用してライセンスを複数のユーザーに割り当てることもできます。操作手順と PowerShell のサンプル スクリプトについては、「Skype for Business と Microsoft Teams のライセンスを割り当てる」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="685d2-109">**To assign a license for a user**</span></span>
  
1. <span data-ttu-id="685d2-110">最大 20 人までのライセンスを同時に割り当てている場合は、[ ビューの選択] ボックスを使用していずれかのオプションを選択するか、独自のビューを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="685d2-110">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="685d2-111">次に [ **編集**]、[ **次へ**] を 2 回クリックし、ライセンスを選択して、[  > ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="685d2-111">In the left navigation of the **Office 365 admin center**, go to **Users** > **Active users**, and then select the user or users from the list of available users.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="685d2-p102">また、Windows Powershell を使用してライセンスを複数のユーザーに割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="685d2-p102">If you are assigning licenses to up to 20 users at the same time, you can use the **Select a view** drop-down then choose one of the options or create your own view. Then click **Edit**, **Next** twice then select the license and click **Submit**. You can also assign licenses to multiple users by using Windows Powershell. For instructions and sample PowerShell scripts, see [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span> 
  
3. <span data-ttu-id="685d2-116">ライセンスの詳細については、「**Skype for Business と Microsoft Teams のアドオン ライセンス**」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="685d2-116">In the Action pane under **Product licenses**, click **Edit**.</span></span> 
    
4. <span data-ttu-id="685d2-p103">ライセンスを割り当てると、電話会議プロバイダーのリストに Microsoft が表示されなくなることがあります。この場合は、Office 365 管理センターからログアウトするか、CTRL キーを押しながら F5 キーを押してブラウザーのウィンドウを更新します。</span><span class="sxs-lookup"><span data-stu-id="685d2-p103">On the **Product Licenses** page, turn on **Audio Conferencing** and then click **Save**. For more on licensing, see [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
    
> [!NOTE]
> <span data-ttu-id="685d2-p104">ユーザーに会議 ID を割り当てる</span><span class="sxs-lookup"><span data-stu-id="685d2-p104">After you assign the license, Microsoft might not appear initially in the list as an audio conferencing provider. If this happens, either log out of the Office 365 admin center or press CTRL+F5 to refresh the browser window.</span></span> 
  
## <a name="assign-a-conference-id-for-a-user"></a><span data-ttu-id="685d2-121">割り当てられた 会議 ID は、静的または動的 ID で、会議がスケジュール設定されると会議出席依頼で送信されます。</span><span class="sxs-lookup"><span data-stu-id="685d2-121">Assign a conference ID for a user</span></span>

<span data-ttu-id="685d2-122">A conference ID is automatically assigned to a user when they are set up for dial-in conferencing using Microsoft as the dial-in conferencing provider.</span><span class="sxs-lookup"><span data-stu-id="685d2-122">A conference ID is automatically assigned to a user when they are set up for audio conferencing using Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="685d2-123">会議がスケジュールされているとき、会議出席依頼に会議 ID が送信されます。</span><span class="sxs-lookup"><span data-stu-id="685d2-123">The conference ID is sent in the meeting invite when the meeting is scheduled.</span></span> <span data-ttu-id="685d2-124">ユーザーをスケジュールする会議ごとに固有の会議 ID が割り当てられますを取得</span><span class="sxs-lookup"><span data-stu-id="685d2-124">Each meeting that a user schedules will get assigned a unique conference ID.</span></span>
  
<span data-ttu-id="685d2-125">Skype for Business 管理センターにおいて、または Windows PowerShell を使用して、この情報を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="685d2-125">The Skype for Business admin center can't be used to assign a conference ID to a user, but you can use the Windows PowerShell cmdlet to do this.</span></span>
  
<span data-ttu-id="685d2-126">A conference ID must contain 7 digits and you can't change it in the Skype for Business admin center or using Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="685d2-126">To set the conference ID for a user, run:</span></span>
  
```
Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ConferenceId 8271964 
```

> [!IMPORTANT]
> <span data-ttu-id="685d2-127">See Set-CsOnlineDialInConferencingUser to learn more about the cmdlet.</span><span class="sxs-lookup"><span data-stu-id="685d2-127">A conference ID must contain 7 digits, and you can't change it in the Skype for Business admin center or by using Windows PowerShell.</span></span> 
  
<span data-ttu-id="685d2-128">After a new conference ID is created, the old conference ID can't be used by callers. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. The users can use Skype for Business Meeting Migration Tool to update their existing meetings. To see how to download, install and run the Lync Meeting Update Tool, see:> Meeting Update Tool for Skype for Business and LyncSkype for Business Online, Meeting Migration Tool (64-bit)Skype for Business Online, Meeting Migration Tool (32-bit)</span><span class="sxs-lookup"><span data-stu-id="685d2-128">See [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) to learn more about the cmdlet.</span></span>
  
> [!IMPORTANT]
>  <span data-ttu-id="685d2-p106">After a new conference ID is created, the old conference ID can't be used by callers.</span><span class="sxs-lookup"><span data-stu-id="685d2-p106">After a new conference ID is created, the old conference ID can't be used by callers. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. The users can use the Skype for Business Meeting Migration Tool to update their existing meetings. To see how to download, install, and run the Skype for Business Meeting Update Tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](http://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span></span>
  
<span data-ttu-id="685d2-133">[](see-change-and-reset-a-conference-id-assigned-to-a-user.md)職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="685d2-133">See [See, change, and reset a conference ID assigned to a user](see-change-and-reset-a-conference-id-assigned-to-a-user.md).</span></span>
  
## <a name="change-the-audio-conferencing-provider-from-microsoft-to-a-third-party-provider"></a><span data-ttu-id="685d2-134">Sign in to Office 365 with your work or school account.</span><span class="sxs-lookup"><span data-stu-id="685d2-134">Change the audio conferencing provider from Microsoft to a third-party provider</span></span>

<span data-ttu-id="685d2-135">![デバイスのロゴ-30x30.png](../images/sfb-logo-30x30.png) **ビジネス管理センターの Skype を使用します。**</span><span class="sxs-lookup"><span data-stu-id="685d2-135">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="685d2-136">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="685d2-136">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="685d2-137">In the Skype for Business admin center, in the left navigation go to Dial-in conferencingDial-in users and then and select the user you want to change the dial-in conferencing provider for.</span><span class="sxs-lookup"><span data-stu-id="685d2-137">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="685d2-138">In the Action pane, click **Edit**.</span><span class="sxs-lookup"><span data-stu-id="685d2-138">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, and then and select the user you want to change the audio conferencing provider for.</span></span>
    
4. <span data-ttu-id="685d2-139">In the Skype for Business admin center, in the left navigation go to Dial-in conferencing > Provider name drop-down, and then select the dial-in conferencing provider for the user.</span><span class="sxs-lookup"><span data-stu-id="685d2-139">In the Action pane, click **Edit**.</span></span> 
    
5. <span data-ttu-id="685d2-140">[ **保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="685d2-140">On the **Properties** page, under **Provider name**, choose the audio conferencing provider for the user.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="685d2-141">「 **ユーザーのダイヤルイン会議プロバイダーを変更する**」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="685d2-141">You can only select Microsoft as the audio conferencing provider or **None** if you have selected multiple users.</span></span>
  
6. <span data-ttu-id="685d2-142">電話会議ユーザーへのメール送信を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="685d2-142">Click **Save**.</span></span> 
    
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a><span data-ttu-id="685d2-143">Skype for Business 管理センターまたは Windows PowerShell を使用すると、ユーザーへのメール送信を有効または無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="685d2-143">Enable or disable emails sent to audio conferencing users</span></span>

<span data-ttu-id="685d2-144">![チーム ・ ロゴ ・ 30x30.png](../images/teams-logo-30x30.png) **、マイクロソフトのチームとビジネス管理センターの Skype を使用します。**</span><span class="sxs-lookup"><span data-stu-id="685d2-144">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="685d2-145">左側のナビゲーションでは、**会議**に移動 > **会議ブリッジ**です。</span><span class="sxs-lookup"><span data-stu-id="685d2-145">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="685d2-146">**会議ブリッジ**のページの上部には、**ブリッジの設定**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="685d2-146">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="685d2-147">**ブリッジの設定**ウィンドウで、有効または、**ユーザーのダイヤルインの設定を変更する場合に e メールを自動的に送信**を無効にします。</span><span class="sxs-lookup"><span data-stu-id="685d2-147">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="685d2-148">[ **保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="685d2-148">Click **Save**.</span></span>

<span data-ttu-id="685d2-149">![デバイスのロゴ-30x30.png](../images/sfb-logo-30x30.png) **ビジネス管理センターの Skype を使用します。**</span><span class="sxs-lookup"><span data-stu-id="685d2-149">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
  
1. <span data-ttu-id="685d2-150">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="685d2-150">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="685d2-151">On the **Microsoft bridge settings** page, check or uncheck the  > .</span><span class="sxs-lookup"><span data-stu-id="685d2-151">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="685d2-152">電話会議の設定を使用してユーザーにメールを送信することもできます。これには、ユーザーの電話会議プロパティに移動して、[ **電話会議情報をメールで送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="685d2-152">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>
    
4. <span data-ttu-id="685d2-153">ユーザーの電話会議プロパティに移動し、[ **電話会議情報をメールで送信**] をクリックすると、電話会議の設定が含まれるメールをユーザーに送信することもできます。会議 ID と電話会議用の既定の電話番号は会議出席依頼に記載されていますが、PIN は記載されていません。</span><span class="sxs-lookup"><span data-stu-id="685d2-153">Click **Save**.</span></span>
    
    <span data-ttu-id="685d2-p107">ユーザーの電話会議プロパティに移動し、[ **電話会議情報をメールで送信**] をクリックすると、電話会議の設定が含まれるメールをユーザーに送信することもできます。</span><span class="sxs-lookup"><span data-stu-id="685d2-p107">You can also send emails to the user with the audio conferencing settings by going to the user's audio conferencing properties and clicking **Send conference info via email**. The conference ID and default audio conferencing phone number is included on the meeting invite but not the PIN.</span></span>
    
    <span data-ttu-id="685d2-156">You can also send emails to the user with the dial-in conferencing settings, by going to the user's properties > Dial-in conferencingSend conference info via email.</span><span class="sxs-lookup"><span data-stu-id="685d2-156">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>
    
 <span data-ttu-id="685d2-157">The conference ID and default dial-in conferencing phone number is included on the meeting invite but not the PIN.</span><span class="sxs-lookup"><span data-stu-id="685d2-157">**Using Windows PowerShell**</span></span>
  
- <span data-ttu-id="685d2-158">Windows PowerShell を使用する</span><span class="sxs-lookup"><span data-stu-id="685d2-158">You can also use the Windows PowerShell and run:</span></span> 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $true|$false
  ```

    <span data-ttu-id="685d2-159">[](https://go.microsoft.com/fwlink/?LinkId=627285)Windows PowerShell を使用して、次を実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="685d2-159">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) to manage other settings for your organization, including email.</span></span>
    
## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a><span data-ttu-id="685d2-160">You can also use the Windows PowerShell and run:</span><span class="sxs-lookup"><span data-stu-id="685d2-160">Change the sender's contact information in email messages sent to users</span></span>

<span data-ttu-id="685d2-p108">ユーザーに送信されるメール メッセージの、差出人の連絡先情報を変更する</span><span class="sxs-lookup"><span data-stu-id="685d2-p108">You can make changes to the email that is automatically sent to your users, including the actual email address and the display name of the sender's contact information. By default, the sender of the emails is Office 365, but you can change the email address and display name using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet. To make changes to the email address that is sending the email to the users, you must:</span></span>
  
- <span data-ttu-id="685d2-164">Enter the email display name in the  _SendEmailFromDisplayName_ parameter.</span><span class="sxs-lookup"><span data-stu-id="685d2-164">Enter the email address in the _SendEmailFromAddress_ parameter.</span></span>
    
- <span data-ttu-id="685d2-165">メールの差出人のメール アドレスやメールの表示名など、ユーザーに送信したメールの内容を変更するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="685d2-165">Enter the email display name in the  _SendEmailFromDisplayName_ parameter.</span></span>
    
- <span data-ttu-id="685d2-166">メール アドレス情報を変更したい場合は、カスタムのメール アドレスから送信されるメールが、組織の受信メール ポリシーで許可されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="685d2-166">Set the _SendEmailOverride_ parameter to _True_.</span></span>
    
<span data-ttu-id="685d2-167">If you want to change the email address information, you need to make sure that the inbound email policies of your organization allow emails that come from the custom email address.</span><span class="sxs-lookup"><span data-stu-id="685d2-167">You can make changes to the email sent to users, such as the email address that the email is sent from or the display name for the email by running:</span></span>
  
```
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

<span data-ttu-id="685d2-168">「ダイヤルイン会議の設定が変更されたユーザーにメールを自動的に送信する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="685d2-168">If you want to change the email address information, you need to make sure that the inbound email policies of your organization allow emails that come from the custom email address.</span></span>
  
<span data-ttu-id="685d2-169">会議 ID をリセットする</span><span class="sxs-lookup"><span data-stu-id="685d2-169">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet to manage other settings for your organization, including email.</span></span>
  
<span data-ttu-id="685d2-170">[](emails-sent-to-users-when-their-settings-change.md)職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="685d2-170">See [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md).</span></span>
  
## <a name="reset-the-meeting-conference-id"></a><span data-ttu-id="685d2-171">Sign in to Office 365 with your work or school account.</span><span class="sxs-lookup"><span data-stu-id="685d2-171">Reset the meeting conference ID</span></span>

<span data-ttu-id="685d2-172">![チーム ・ ロゴ ・ 30x30.png](../images/teams-logo-30x30.png) **、マイクロソフトのチームとビジネス管理センターの Skype を使用します。**</span><span class="sxs-lookup"><span data-stu-id="685d2-172">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="685d2-173">左側のナビゲーションでは、**ユーザー**] をクリックしてで使用可能なユーザーの一覧からユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="685d2-173">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="685d2-174">ページの上部で、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="685d2-174">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="685d2-175">[**オーディオ会議**、**会議 ID のリセット**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="685d2-175">Under **Audio Conferencing**, click **Reset conference ID**.</span></span>  

4. <span data-ttu-id="685d2-176">**会議 ID をリセットしますか?** ] ウィンドウで、[**リセット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="685d2-176">In the **Reset conference ID?** window, click **Reset**.</span></span> <span data-ttu-id="685d2-177">It's enabled by default.</span><span class="sxs-lookup"><span data-stu-id="685d2-177">A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled.</span></span> <span data-ttu-id="685d2-178">After a new conference ID is created, the old conference ID can't be used by callers. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. The users can use Skype for Business Meeting Migration Tool to update their existing meetings. To see how to download, install and run the Lync Meeting Update Tool, see:> Meeting Update Tool for Skype for Business and LyncSkype for Business Online, Meeting Migration Tool (64-bit)Skype for Business Online, Meeting Migration Tool (32-bit)</span><span class="sxs-lookup"><span data-stu-id="685d2-178">It's enabled by default.</span></span>

<span data-ttu-id="685d2-179">![デバイスのロゴ-30x30.png](../images/sfb-logo-30x30.png) **ビジネス管理センターの Skype を使用します。**</span><span class="sxs-lookup"><span data-stu-id="685d2-179">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>  

1. <span data-ttu-id="685d2-180">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="685d2-180">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="685d2-181">In the Skype for Business admin centerDial-in conferencing, in the Action page under Conference ID click Reset.</span><span class="sxs-lookup"><span data-stu-id="685d2-181">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="685d2-182">In the ** Reset conference ID?** window, click **Yes**. A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled. It's enabled by default.</span><span class="sxs-lookup"><span data-stu-id="685d2-182">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and in the Action pane under **Conference ID**, click **Reset**.</span></span>
    
4. <span data-ttu-id="685d2-p110">In the ** Reset conference ID?** window, click **Yes**.</span><span class="sxs-lookup"><span data-stu-id="685d2-p110">In the **Reset conference ID?** window, click **Yes**. A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled. It's enabled by default.</span></span>
    
    > [!IMPORTANT]
    >  <span data-ttu-id="685d2-p111">After a new conference ID is created, the old conference ID can't be used by callers.</span><span class="sxs-lookup"><span data-stu-id="685d2-p111">After a new conference ID is created, the old conference ID can't be used by callers. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. The users can use the Skype for Business Meeting Migration Tool to update their existing meetings. To see how to download, install, and run the Skype for Business Meeting Update Tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](http://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span></span>
  
<span data-ttu-id="685d2-190">[](reset-a-conference-id-for-a-user.md)Reset a conference organizer's PIN</span><span class="sxs-lookup"><span data-stu-id="685d2-190">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).</span></span>
  
## <a name="reset-a-conference-organizers-pin"></a><span data-ttu-id="685d2-191">静的会議 ID は自動的に作成されユーザーに割り当てられますが、ユーザーがそれを使いたくないため特定の番号に設定しようと考える場合や、ユーザーが会議 ID を覚えられない、または紛失してしまう場合があります。Skype for Business 管理センターおよび Windows PowerShell を使用すると、ユーザーの会議 ID を表示、変更、リセットすることができます。</span><span class="sxs-lookup"><span data-stu-id="685d2-191">Reset a conference organizer's PIN</span></span>

<span data-ttu-id="685d2-192">ユーザーをスケジュールする会議ごとに固有の会議 ID が割り当てられますを取得</span><span class="sxs-lookup"><span data-stu-id="685d2-192">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="685d2-193">会議 ID が自動的に作成され、ユーザーに割り当てられているがあります、ユーザーは、この 1 つを使用する場合は、特定の数に設定するとユーザーが覚えられないか、会議 ID が失われています。</span><span class="sxs-lookup"><span data-stu-id="685d2-193">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="685d2-194">ユーザーが電話会議で有効になるか、PIN がリセットされた場合、ユーザーは自分の PIN が含まれるメールを受信します。ただし、メールの自動送信を無効にしても、PIN リセットのメールは送信されません。管理者は、ユーザーに PIN を手動で送信する必要があります。PIN をリセットした後、PIN が表示されるのは 1 回だけです。リセットの直後に 1 回表示された後は、ユーザーのプロパティには PIN に代わって "\*\*\*\*\*" が表示されます。</span><span class="sxs-lookup"><span data-stu-id="685d2-194">You can use the Skype for Business admin center and Windows PowerShell to view, change, and reset their conference ID.</span></span>

<span data-ttu-id="685d2-195">![チーム ・ ロゴ ・ 30x30.png](../images/teams-logo-30x30.png) **、マイクロソフトのチームとビジネス管理センターの Skype を使用します。**</span><span class="sxs-lookup"><span data-stu-id="685d2-195">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="685d2-196">左側のナビゲーションでは、**ユーザー**] をクリックしてで使用可能なユーザーの一覧からユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="685d2-196">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="685d2-197">ページの上部で、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="685d2-197">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="685d2-198">**オーディオ会議**では、[ **PIN のリセット**] をクリックし、[**リセット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="685d2-198">Under **Audio Conferencing**, click **Reset PIN**, and then click **Reset**.</span></span> 
  
<span data-ttu-id="685d2-199">![デバイスのロゴ-30x30.png](../images/sfb-logo-30x30.png) **ビジネス管理センターの Skype を使用します。**</span><span class="sxs-lookup"><span data-stu-id="685d2-199">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span> 

1. <span data-ttu-id="685d2-200">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="685d2-200">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="685d2-201">Sign in to Office 365 with your work or school account.</span><span class="sxs-lookup"><span data-stu-id="685d2-201">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="685d2-202">管理者は、ユーザーに PIN を手動で送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="685d2-202">Click **Users**, and then select the user that you want to reset the PIN for.</span></span>
    
4. <span data-ttu-id="685d2-203">PIN をリセットした後、PIN が表示されるのは 1 回だけです。</span><span class="sxs-lookup"><span data-stu-id="685d2-203">In the Action pane, under **PIN**, click **Reset**.</span></span>
    
<span data-ttu-id="685d2-p113">リセットの直後に 1 回表示された後は、ユーザーのプロパティには PIN に代わって "\*\*\*\*\*" が表示されます。</span><span class="sxs-lookup"><span data-stu-id="685d2-p113">Users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset. But if you have disabled automatically sending emails, a PIN reset email won't be sent and you will have to manually send the PIN to the user. The PIN will only be shown once after it has been reset. After it's displayed just after being reset, the PIN won't be shown anymore on the user properties; instead, \*\*\*\*\* will be shown.</span></span> 
  
<span data-ttu-id="685d2-208">[オーディオ会議の PIN のリセット](reset-the-audio-conferencing-pin.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="685d2-208">See [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin.md).</span></span>
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="685d2-209">電話会議の情報が記載されたメールをユーザーに送信する</span><span class="sxs-lookup"><span data-stu-id="685d2-209">Send an email with Audio Conferencing information to a user</span></span>

<span data-ttu-id="685d2-210">![チーム ・ ロゴ ・ 30x30.png](../images/teams-logo-30x30.png) **、マイクロソフトのチームとビジネス管理センターの Skype を使用します。**</span><span class="sxs-lookup"><span data-stu-id="685d2-210">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="685d2-211">左側のナビゲーションでは、**ユーザー**] をクリックしてで使用可能なユーザーの一覧からユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="685d2-211">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="685d2-212">ページの上部で、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="685d2-212">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="685d2-213">[**オーディオ会議****電子メールで会議の情報を送信**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="685d2-213">Under **Audio Conferencing**, click **Send conference info in email**.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="685d2-214">この操作を行っても、電話会議の PIN はユーザーに送信されません。</span><span class="sxs-lookup"><span data-stu-id="685d2-214">When you do this, the audio conferencing PIN isn't sent to the user.</span></span> 

<span data-ttu-id="685d2-215">![デバイスのロゴ-30x30.png](../images/sfb-logo-30x30.png) **ビジネス管理センターの Skype を使用します。**</span><span class="sxs-lookup"><span data-stu-id="685d2-215">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>  

1. <span data-ttu-id="685d2-216">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="685d2-216">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="685d2-217">Sign in to Office 365 with your work or school account.</span><span class="sxs-lookup"><span data-stu-id="685d2-217">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="685d2-218">Go to the Office 365 admin centerSkype for Business and in the left navigation click Dial-in conferencing</span><span class="sxs-lookup"><span data-stu-id="685d2-218">Click **Users**, and then select the user that you want to reset the PIN for.</span></span>
    
4. <span data-ttu-id="685d2-219">操作ウィンドウで、[ **電話会議情報をメールで送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="685d2-219">In the Action pane, click **Send conference info via email**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="685d2-220">この操作を行っても、電話会議の PIN はユーザーに送信されません。</span><span class="sxs-lookup"><span data-stu-id="685d2-220">When you do this, the audio conferencing PIN isn't sent to the user.</span></span> 
  
<span data-ttu-id="685d2-221">When you do this, the dial-in conferencing PIN isn't sent to the user.</span><span class="sxs-lookup"><span data-stu-id="685d2-221">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>
  
## <a name="setting-the-default-audio-conferencing-phone-number-for-meeting-organizers"></a><span data-ttu-id="685d2-222">会議開催者に対して電話会議用の既定の電話番号を設定する</span><span class="sxs-lookup"><span data-stu-id="685d2-222">Setting the default audio conferencing phone number for meeting organizers</span></span>

 <span data-ttu-id="685d2-223">**** Setting the default dial-in conferencing phone number for meeting organizers</span><span class="sxs-lookup"><span data-stu-id="685d2-223">**To set the default audio conferencing phone number for meeting organizers when you are enabling a user for Audio Conferencing**</span></span>
  
1. <span data-ttu-id="685d2-224">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="685d2-224">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="685d2-225">Sign in to Office 365 with your work or school account.</span><span class="sxs-lookup"><span data-stu-id="685d2-225">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="685d2-p114">Go to the **Office 365 admin center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="685d2-p114">In the left navigation, go to **Audio conferencing** > **Users**. Select the user that you want to enable for Audio Conferencing.</span></span>
    
4. <span data-ttu-id="685d2-228">Select the user that you want to enable for dial-in conferencing.</span><span class="sxs-lookup"><span data-stu-id="685d2-228">In the Action pane, in the user's properties, click **Edit**.</span></span>
    
5. <span data-ttu-id="685d2-229">In the Action pane, in the user's properties click **Edit**.</span><span class="sxs-lookup"><span data-stu-id="685d2-229">On the **Properties** page, under **Provider name**, use the drop-down list to select the audio conferencing provider.</span></span>
    
  - <span data-ttu-id="685d2-230">電話会議プロバイダーに Microsoft を選ぶ場合は、電話会議の既定の電話番号を一覧から選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="685d2-230">If you select Microsoft as the audio conferencing provider, you can choose the default audio conferencing phone number from the list.</span></span>  
    
  - <span data-ttu-id="685d2-p115">電話会議プロバイダーにサードパーティーの ACP を選ぶ場合は、有料の電話番号 (または必要に応じてフリーダイヤルの電話番号) を手動で入力する必要があります。これらの電話番号は、既定の電話番号に設定されます。</span><span class="sxs-lookup"><span data-stu-id="685d2-p115">If you select a third-party ACP as the audio conferencing provider, you will need to manually enter the Toll and if required, the Toll-free phone number. These phone numbers will be the default phone number.</span></span>
    
    <span data-ttu-id="685d2-233">ユーザーの電話会議用の既定の電話番号は、ユーザーが会議をスケジュールしたときに会議出席依頼に表示される番号です。</span><span class="sxs-lookup"><span data-stu-id="685d2-233">The default audio conferencing phone number of a user is the number that is shown on the meeting invite when they schedule a meeting.</span></span>
    
6. <span data-ttu-id="685d2-234">The default dial-in conferencing phone number of a user is the number that is shown on the meeting invite when they schedule a meeting.</span><span class="sxs-lookup"><span data-stu-id="685d2-234">Click **Save**.</span></span> 
    
<span data-ttu-id="685d2-235">「[出席依頼に含まれている会議の開催者のために電話会議の電話番号を設定する](set-the-phone-numbers-included-on-invites.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="685d2-235">See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites.md).</span></span>
  
 <span data-ttu-id="685d2-236">**電話会議のユーザーを有効にした後に、会議開催者に対して電話会議用の既定の電話番号を設定するには**</span><span class="sxs-lookup"><span data-stu-id="685d2-236">**To set the default audio conferencing phone number for meeting organizers after you have enabled a user for audio conferencing**</span></span>
  
1. <span data-ttu-id="685d2-237">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="685d2-237">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="685d2-238">Sign in to Office 365 with your work or school account.</span><span class="sxs-lookup"><span data-stu-id="685d2-238">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="685d2-239">Go to the **Office 365 admin center****** > .</span><span class="sxs-lookup"><span data-stu-id="685d2-239">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, select the user you want, and in the Action page, click **Edit**.</span></span>
    
4. <span data-ttu-id="685d2-240">In the Skype for Business admin center, in the left navigation go to Dial-in conferencingDial-in users, select the user you want and in the Action page, click Edit.</span><span class="sxs-lookup"><span data-stu-id="685d2-240">On the **Properties** page, under **Provider name**, use the drop-down list to select the audio conferencing provider.</span></span>
    
  - <span data-ttu-id="685d2-241">ユーザーが電話会議プロバイダーとして Microsoft を使用する場合は、電話会議の既定の電話番号を一覧から選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="685d2-241">If the user uses Microsoft as the audio conferencing provider, you can choose the default audio conferencing phone number from the list.</span></span>  
    
  - <span data-ttu-id="685d2-242">電話会議プロバイダーにサードパーティーの ACP を使う場合は、有料の電話番号 (または必要に応じてフリーダイヤルの電話番号) を手動で入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="685d2-242">If the user uses a third-party ACP as the audio conferencing provider, you will need to manually enter the Toll and if required, the Toll-free phone number.</span></span>
    
    <span data-ttu-id="685d2-243">ユーザーの電話会議用の既定の電話番号は、ユーザーが会議をスケジュールしたときに会議出席依頼に表示される番号です。</span><span class="sxs-lookup"><span data-stu-id="685d2-243">The default audio conferencing phone number of a user is the number that is shown on the meeting invite when they schedule a meeting.</span></span>
    
5. <span data-ttu-id="685d2-244">The default dial-in conferencing phone number of a user is the number that is shown on the meeting invite when they schedule a meeting.</span><span class="sxs-lookup"><span data-stu-id="685d2-244">Click **Save**.</span></span> 
    
<span data-ttu-id="685d2-245">「[出席依頼に含まれている会議の開催者のために電話会議の電話番号を設定する](set-the-phone-numbers-included-on-invites.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="685d2-245">See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites.md).</span></span>
  
## <a name="choosing-audio-conferencing-bridge-settings"></a><span data-ttu-id="685d2-246">オーディオ会議ブリッジの設定を選択します。</span><span class="sxs-lookup"><span data-stu-id="685d2-246">Choosing audio conferencing bridge settings</span></span>

<span data-ttu-id="685d2-247">**** Setting dial-in conferencing bridge settings</span><span class="sxs-lookup"><span data-stu-id="685d2-247">**Set the meeting experience when callers join a meeting**</span></span>

 <span data-ttu-id="685d2-248">![チーム ・ ロゴ ・ 30x30.png](../images/teams-logo-30x30.png) **、マイクロソフトのチームとビジネス管理センターの Skype を使用します。**</span><span class="sxs-lookup"><span data-stu-id="685d2-248">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="685d2-249">左側のナビゲーションでは、**会議**に移動 > **会議ブリッジ**です。</span><span class="sxs-lookup"><span data-stu-id="685d2-249">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="685d2-250">**会議ブリッジ**のページの上部には、**ブリッジの設定**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="685d2-250">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="685d2-251">**ブリッジの設定**ウィンドウを有効にするまたは**ミーティングのエントリと終了の通知**を無効にします。</span><span class="sxs-lookup"><span data-stu-id="685d2-251">In the **Bridge settings** pane, enable or disable **Meeting entry and exit notifications**.</span></span>

    <span data-ttu-id="685d2-252">これは既定で有効になります。</span><span class="sxs-lookup"><span data-stu-id="685d2-252">This is enabled by default.</span></span> <span data-ttu-id="685d2-253">このオプションを無効にした場合データを入力したり、会議を離れるときに既定では、会議に参加しているユーザーが通知されません。</span><span class="sxs-lookup"><span data-stu-id="685d2-253">If you disable this option, users who have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span></span>

4. <span data-ttu-id="685d2-254">**開始/終了のお知らせの種類**、[**トーン**] または [**名前または電話番号**を選択します。</span><span class="sxs-lookup"><span data-stu-id="685d2-254">Under **Entry/exit announcement type**, choose either **Tones** or **Names or phone numbers**.</span></span> 

    <span data-ttu-id="685d2-255">**名前や電話番号**を選択する場合を有効にするまたは、**ミーティングに参加する前に自分の名前を記録するための呼び出し元の確認**を無効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="685d2-255">If you choose **Names or phone numbers**, you can also choose to enable or disable **Ask callers to record their name before joining the meeting**.</span></span> 

1. <span data-ttu-id="685d2-256">[ **保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="685d2-256">Click **Save**.</span></span>

<span data-ttu-id="685d2-257">![デバイスのロゴ-30x30.png](../images/sfb-logo-30x30.png) **ビジネス管理センターの Skype を使用します。**</span><span class="sxs-lookup"><span data-stu-id="685d2-257">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span> 
  
1. <span data-ttu-id="685d2-258">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="685d2-258">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="685d2-259">Sign in to Office 365 with your work or school account.</span><span class="sxs-lookup"><span data-stu-id="685d2-259">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="685d2-260">Go to the **Office 365 admin center****** > .</span><span class="sxs-lookup"><span data-stu-id="685d2-260">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="685d2-261">In the Skype for Business admin center, in the left navigation go to dial-in conferencingMicrosoft bridge settings.</span><span class="sxs-lookup"><span data-stu-id="685d2-261">Under **Meeting join experience**, select the following actions:</span></span>
    
  - <span data-ttu-id="685d2-p117">**Enable meeting entry and exit notifications to be turned on** This is selected by default. However if you uncheck it, users that have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span><span class="sxs-lookup"><span data-stu-id="685d2-p117">**Enable meeting entry and exit notifications to be turned on** This is selected by default. If you clear this check box, users who have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span></span>
    
    <span data-ttu-id="685d2-264">変更したら [ **保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="685d2-264">This can be set on a meeting-by-meeting basis when a user joins a meeting using a Skype for Business or Microsoft Teams app and they modify the **Announce when people enter or leave** setting in the Skype Meeting or Microsoft Teams **Options** menu of the meeting.</span></span>
    
  - <span data-ttu-id="685d2-p118">「**電話会議ブリッジの設定を変更する**」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="685d2-p118">**Ask callers to record their name before joining the meeting** This is selected by default. If you clear this check box, callers won't be asked to record their name before they join a meeting.</span></span>
    
5. <span data-ttu-id="685d2-267">Sign in to Office 365 with your work or school account.</span><span class="sxs-lookup"><span data-stu-id="685d2-267">After you make your changes, click **Save**.</span></span>
    
<span data-ttu-id="685d2-268">Go to the Office 365 admin centerSkype for Business.</span><span class="sxs-lookup"><span data-stu-id="685d2-268">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>
  
 <span data-ttu-id="685d2-269">In the Skype for Business admin center, in the left navigation go to dial-in conferencingMicrosoft bridge settings.</span><span class="sxs-lookup"><span data-stu-id="685d2-269">**Set the PIN length for meetings**</span></span>

 <span data-ttu-id="685d2-270">![チーム ・ ロゴ ・ 30x30.png](../images/teams-logo-30x30.png) **、マイクロソフトのチームとビジネス管理センターの Skype を使用します。**</span><span class="sxs-lookup"><span data-stu-id="685d2-270">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="685d2-271">左側のナビゲーションでは、**会議**に移動 > **会議ブリッジ**です。</span><span class="sxs-lookup"><span data-stu-id="685d2-271">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="685d2-272">**会議ブリッジ**のページの上部には、**ブリッジの設定**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="685d2-272">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="685d2-273">**ブリッジの設定**ウィンドウで、 **PIN の長さ**] ボックスの一覧で、[暗証番号 (pin) に使用桁の番号を入力し、し、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="685d2-273">In the **Bridge settings** pane, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>

    <span data-ttu-id="685d2-p119">The PIN can only be from 4 to 12 digits.</span><span class="sxs-lookup"><span data-stu-id="685d2-p119">The PIN must be between 4 and 12 digits. The default is 5.</span></span>

<span data-ttu-id="685d2-276">![デバイスのロゴ-30x30.png](../images/sfb-logo-30x30.png) **ビジネス管理センターの Skype を使用します。**</span><span class="sxs-lookup"><span data-stu-id="685d2-276">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span> 
  
1. <span data-ttu-id="685d2-277">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="685d2-277">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="685d2-278">Sign in to Office 365 with your work or school account.</span><span class="sxs-lookup"><span data-stu-id="685d2-278">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="685d2-279">既定値は 5 です。</span><span class="sxs-lookup"><span data-stu-id="685d2-279">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="685d2-280">The PIN can only be from 4 to 12 digits. The default is 5.</span><span class="sxs-lookup"><span data-stu-id="685d2-280">Under **Security**, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>
    
    <span data-ttu-id="685d2-p120">The PIN can only be from 4 to 12 digits.</span><span class="sxs-lookup"><span data-stu-id="685d2-p120">The PIN must be between 4 and 12 digits. The default is 5.</span></span>
    
<span data-ttu-id="685d2-283">[](change-the-settings-for-an-audio-conferencing-bridge.md)職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="685d2-283">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>
  
 <span data-ttu-id="685d2-284">Sign in to Office 365 with your work or school account.</span><span class="sxs-lookup"><span data-stu-id="685d2-284">**Enable or disable email from being sent to audio users**</span></span>

 <span data-ttu-id="685d2-285">![チーム ・ ロゴ ・ 30x30.png](../images/teams-logo-30x30.png) **、マイクロソフトのチームとビジネス管理センターの Skype を使用します。**</span><span class="sxs-lookup"><span data-stu-id="685d2-285">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="685d2-286">左側のナビゲーションでは、**会議**に移動 > **会議ブリッジ**です。</span><span class="sxs-lookup"><span data-stu-id="685d2-286">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="685d2-287">**会議ブリッジ**のページの上部には、**ブリッジの設定**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="685d2-287">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="685d2-288">**ブリッジの設定**ウィンドウを有効にするか**、オーディオ会議の設定を変更する場合、ユーザーに e メールを自動的に送信**を無効にします。</span><span class="sxs-lookup"><span data-stu-id="685d2-288">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their audio conferencing settings change**.</span></span>

4. <span data-ttu-id="685d2-289">[ **保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="685d2-289">Click **Save**.</span></span> 
 
    <span data-ttu-id="685d2-290">ユーザーのオーディオ会議のプロパティに移動し、**電子メールで会議の情報を送信**] をクリックしてユーザーに、電話会議の設定を使用する電子メールを送信することも。</span><span class="sxs-lookup"><span data-stu-id="685d2-290">You can also send email to the user with the audio conferencing settings, by going to the user's audio conferencing properties and clicking **Send conference info in email**.</span></span>
    
    <span data-ttu-id="685d2-291">この操作を行うと、会議 ID と電話会議の番号のみが含まれるメールが送信されますが、そのメールに PIN は含まれません。</span><span class="sxs-lookup"><span data-stu-id="685d2-291">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span></span>

<span data-ttu-id="685d2-292">![デバイスのロゴ-30x30.png](../images/sfb-logo-30x30.png) **ビジネス管理センターの Skype を使用します。**</span><span class="sxs-lookup"><span data-stu-id="685d2-292">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span> 
  
1. <span data-ttu-id="685d2-293">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="685d2-293">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="685d2-294">On the **Microsoft bridge settings** page, check or uncheck the  > .</span><span class="sxs-lookup"><span data-stu-id="685d2-294">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="685d2-295">電話会議の設定を使用してユーザーにメールを送信することもできます。これには、ユーザーの電話会議プロパティに移動して、[ **電話会議情報をメールで送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="685d2-295">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>
    
4. <span data-ttu-id="685d2-296">電話会議の設定を使用してユーザーにメールを送信することもできます。</span><span class="sxs-lookup"><span data-stu-id="685d2-296">Click **Save**.</span></span>
    
    <span data-ttu-id="685d2-297">これには、ユーザーの電話会議プロパティに移動して、[ **電話会議情報をメールで送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="685d2-297">You can also send email to the user with the audio conferencing settings, by going to the user's audio conferencing properties and clicking **Send conference info via email**.</span></span>
    
    <span data-ttu-id="685d2-298">この操作を行うと、会議 ID と電話会議の番号のみが含まれるメールが送信されますが、そのメールに PIN は含まれません。</span><span class="sxs-lookup"><span data-stu-id="685d2-298">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span></span>
    
    <span data-ttu-id="685d2-299">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span><span class="sxs-lookup"><span data-stu-id="685d2-299">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>
    
## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a><span data-ttu-id="685d2-300">参照してくださいし、オーディオ会議ブリッジに (既定値) をプライマリとセカンダリ (代替) の言語を設定します。</span><span class="sxs-lookup"><span data-stu-id="685d2-300">See and set the primary (default) and secondary (alternate) languages on an audio conferencing bridge</span></span>

 <span data-ttu-id="685d2-301">![チーム ・ ロゴ ・ 30x30.png](../images/teams-logo-30x30.png) **、マイクロソフトのチームとビジネス管理センターの Skype を使用します。**</span><span class="sxs-lookup"><span data-stu-id="685d2-301">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="685d2-302">左側のナビゲーションでは、**会議**に移動 > **会議ブリッジ**です。</span><span class="sxs-lookup"><span data-stu-id="685d2-302">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="685d2-303">リストから電話番号を選択し、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="685d2-303">Select a phone number from the list and click **Edit**.</span></span>

3. <span data-ttu-id="685d2-304">[**既定の言語**および **(省略可能) 別の言語**の言語を選択してください。</span><span class="sxs-lookup"><span data-stu-id="685d2-304">Choose the languages you want under **Default language** and **Alternate languages (optional)**.</span></span>

<span data-ttu-id="685d2-305">![デバイスのロゴ-30x30.png](../images/sfb-logo-30x30.png) **ビジネス管理センターの Skype を使用します。**</span><span class="sxs-lookup"><span data-stu-id="685d2-305">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span> 

1. <span data-ttu-id="685d2-306">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="685d2-306">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="685d2-307">Sign in to Office 365 with your work or school account.</span><span class="sxs-lookup"><span data-stu-id="685d2-307">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="685d2-308">Go to the **Office 365 admin center********Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="685d2-308">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and then click **Microsoft bridge**.</span></span>
    
4. <span data-ttu-id="685d2-309">リストから電話番号を選択し、操作ウィンドウで [ **言語を設定**] をクリックしてから、[ **言語を設定**] ページで [ **第 1 言語**] リストをクリックして、サポートされている言語の完全なリストを表示します。</span><span class="sxs-lookup"><span data-stu-id="685d2-309">Select a phone number from the list, click **Set languages** in the Action pane, and then on the **Set languages** page, click the use the **Primary language** list to view the complete list of supported languages.</span></span>
    
    <span data-ttu-id="685d2-p121">Microsoft を電話会議プロバイダーとして選ぶときに、サポートされる第 1 言語と第 2 言語を設定することもできます。発信者に対する言語の表示順は、リストで言語を選んだ順序になります。</span><span class="sxs-lookup"><span data-stu-id="685d2-p121">You can also set the primary and secondary languages that are supported when you select Microsoft as the audio conferencing provider. The order that you select in the lists is the same order in which languages will be presented to callers.</span></span>
    
<span data-ttu-id="685d2-312">You can also set the primary and secondary languages that are supported when you select Microsoft as the dial-in conferencing provider. The order that you select in the drop-downs will be the order of the languages that will be presented to the callers.</span><span class="sxs-lookup"><span data-stu-id="685d2-312">See [Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing.md).</span></span>
  
## <a name="sfb-logo-30x30pngimagessfb-logo-30x30png--see-audio-conferencing-dial-in-numbers"></a>![デバイス ・ ロゴ ・ 30x30.png](../images/sfb-logo-30x30.png)  <span data-ttu-id="685d2-314">You can also set the primary and secondary languages that are supported when you select Microsoft as the dial-in conferencing provider.</span><span class="sxs-lookup"><span data-stu-id="685d2-314">See audio conferencing dial-in numbers</span></span>

1. <span data-ttu-id="685d2-315">The order that you select in the drop-downs will be the order of the languages that will be presented to the callers.</span><span class="sxs-lookup"><span data-stu-id="685d2-315">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="685d2-316">「電話会議のダイヤルイン番号」をご覧ください</span><span class="sxs-lookup"><span data-stu-id="685d2-316">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="685d2-p122">**** 職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="685d2-p122">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge**. Here you can:</span></span>
    
  - <span data-ttu-id="685d2-319">電話会議で使うために Office 365 によって設定された電話番号を表示する。</span><span class="sxs-lookup"><span data-stu-id="685d2-319">View the phone numbers that are set by Office 365 to be used for Audio Conferencing.</span></span> 
    
  - <span data-ttu-id="685d2-320">場所を表示したり、電話会議の自動応答で使用する第 1 言語と第 2 言語を表示したりする。</span><span class="sxs-lookup"><span data-stu-id="685d2-320">View the location, and the primary and secondary languages, that will be used by the Audio Conferencing auto attendant.</span></span>
    
  - <span data-ttu-id="685d2-p123">ユーザーが電話会議で有効になっているときに、ユーザーに渡される既定の電話番号を選択します。ただし、電話会議ブリッジの既定の電話番号が変わっても、既存のユーザーの既定の電話番号は変わりません。</span><span class="sxs-lookup"><span data-stu-id="685d2-p123">Select the default phone number that will be given to users when they are enabled for Audio Conferencing. However, if the default phone number of the audio conferencing bridge changes, the default phone number for existing users won't change.</span></span>
    
<span data-ttu-id="685d2-323">You can select the dial-in conferencing default phone number that will be given to users when they are enabled for dial-in conferencing. However, if the default phone number of the dial-in conferencing bridge changes, the default phone number for existing users won't change.</span><span class="sxs-lookup"><span data-stu-id="685d2-323">You can go to **Audio conferencing** > **Users** and select the user's properties to change the default number for a user by choosing a new number from the list of numbers that are available in your organization.</span></span>
  
<span data-ttu-id="685d2-324">You can select the dial-in conferencing default phone number that will be given to users when they are enabled for dial-in conferencing.</span><span class="sxs-lookup"><span data-stu-id="685d2-324">See [See a list of Audio Conferencing numbers](see-a-list-of-audio-conferencing-numbers.md).</span></span>
  
## <a name="sfb-logo-30x30pngimagessfb-logo-30x30png-see-a-list-of-users-that-are-enabled"></a>![デバイス ・ ロゴ ・ 30x30.png](../images/sfb-logo-30x30.png) <span data-ttu-id="685d2-326">However, if the default phone number of the dial-in conferencing bridge changes, the default phone number for existing users won't change.</span><span class="sxs-lookup"><span data-stu-id="685d2-326">See a list of users that are enabled</span></span>

1. <span data-ttu-id="685d2-327">You can go to Dial-in conferencingDial-in users and select the user's properties to change the default number for a user by choosing a new number from the list of numbers that are available in your organization.</span><span class="sxs-lookup"><span data-stu-id="685d2-327">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="685d2-328">有効になっているユーザーのリストを表示する</span><span class="sxs-lookup"><span data-stu-id="685d2-328">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="685d2-329">**** 職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="685d2-329">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**> and then **Users**.</span></span>
    
<span data-ttu-id="685d2-330">Sign in to Office 365 with your work or school account.</span><span class="sxs-lookup"><span data-stu-id="685d2-330">See [See a list of users that are enabled for Audio Conferencing](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).</span></span>
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="685d2-331">Go to the Office 365 admin centerSkype for Business.</span><span class="sxs-lookup"><span data-stu-id="685d2-331">Want to know how to manage with Windows PowerShell?</span></span>

<span data-ttu-id="685d2-p124">In the Skype for Business admin center, in the left navigation go to Dial-in conferencing> and then Dial-in users.</span><span class="sxs-lookup"><span data-stu-id="685d2-p124">There are several settings that you can manage at the organization level using Windows PowerShell. This makes it easy to apply settings to all of your users.</span></span> 
    
<span data-ttu-id="685d2-334">[](https://go.microsoft.com/fwlink/?LinkId=627324)Windows PowerShell を使用して組織レベルで管理できる複数の設定があります。</span><span class="sxs-lookup"><span data-stu-id="685d2-334">To get more help on each cmdlet, see [Skype for Business Online cmdlets](https://go.microsoft.com/fwlink/?LinkId=627324).</span></span>

<span data-ttu-id="685d2-335">このため、簡単にこれらの設定をすべてのユーザーに適用できます。</span><span class="sxs-lookup"><span data-stu-id="685d2-335">Here are the organization-level settings:</span></span> 
> 
- <span data-ttu-id="685d2-336">組織レベルの設定を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="685d2-336">**Setting entry/exit notifications** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableEntryExitNotifications $true|$false 
  ```

- <span data-ttu-id="685d2-337">There are several settings that you can manage settings at the organization level using Windows PowerShell. This makes it easy to make these settings and have them apply to all of your users. Here are the organization level settings:</span><span class="sxs-lookup"><span data-stu-id="685d2-337">**Setting name recording** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableNameRecording $true|false
  ```

- <span data-ttu-id="685d2-338">There are several settings that you can manage settings at the organization level using Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="685d2-338">**Setting the PIN length** The default is 5.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -PinLength 7
  ```

- <span data-ttu-id="685d2-339">This makes it easy to make these settings and have them apply to all of your users.</span><span class="sxs-lookup"><span data-stu-id="685d2-339">**Setting only dial-in meetings from a phone** The default _$false_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true|$false
  ```

- <span data-ttu-id="685d2-340">Here are the organization level settings:</span><span class="sxs-lookup"><span data-stu-id="685d2-340">**Setting whether to send email to users** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

- <span data-ttu-id="685d2-341">Windows PowerShell の場合、ユーザーの管理と、ユーザーに許可する操作や許可しない操作の管理に使います。Windows PowerShell により、単一の管理ポイントを使って Office 365 を管理でき、複数の作業を実行する必要があるときに日常業務を合理化できます。Windows PowerShell を使い始めるには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="685d2-341">**Setting whether to send email from a different account** The default is  _$false_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromOverride $true|$false
  ```

- <span data-ttu-id="685d2-342">Windows PowerShell の場合、ユーザーの管理と、ユーザーに許可する操作や許可しない操作の管理に使います。</span><span class="sxs-lookup"><span data-stu-id="685d2-342">**Setting the From address on email that is sent to users** The default is _$null_.</span></span> 
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromAddress
  ```

- <span data-ttu-id="685d2-343">Windows PowerShell により、単一の管理ポイントを使って Office 365 を管理でき、複数の作業を実行する必要があるときに日常業務を合理化できます。</span><span class="sxs-lookup"><span data-stu-id="685d2-343">**Setting the display name for the email that is sent to users** The default is  _$null_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromDisplayName
  ```

 ## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="685d2-344">Windows PowerShell を使い始めるには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="685d2-344">Want to know more about Windows PowerShell</span></span>   
- <span data-ttu-id="685d2-p125">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span><span class="sxs-lookup"><span data-stu-id="685d2-p125">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="685d2-348">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="685d2-348">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="685d2-349">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="685d2-349">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="685d2-p126">多くのユーザーの設定を同時に変更するときなどは、Office 365 管理センターのみを使用するよりも、Windows PowerShell の方に、速度、わかりやすさ、生産性の点で多くのメリットがあります。</span><span class="sxs-lookup"><span data-stu-id="685d2-p126">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time. Learn about these advantages in the following topics:</span></span> 
    
  - <span data-ttu-id="685d2-352">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time.</span><span class="sxs-lookup"><span data-stu-id="685d2-352">[An introduction to Windows PowerShell and Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)</span></span>
    
  - [<span data-ttu-id="685d2-353">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="685d2-353">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="685d2-354">Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行</span><span class="sxs-lookup"><span data-stu-id="685d2-354">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    <span data-ttu-id="685d2-p127">[Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="685d2-p127">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="685d2-357">このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「Skype for Business Online 用 Windows PowerShell モジュール」からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="685d2-357">Related topics</span></span>

<span data-ttu-id="685d2-358">See also</span><span class="sxs-lookup"><span data-stu-id="685d2-358">[Manage the Audio Conferencing settings for a user](manage-the-audio-conferencing-settings-for-a-user.md)</span></span>


