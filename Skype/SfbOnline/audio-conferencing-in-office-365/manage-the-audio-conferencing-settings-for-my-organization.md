---
title: "組織用の電話会議の設定を管理します。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: bc9bd328-c5b2-44e5-af15-e02bf00e1c81
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "ダイヤルイン会議ライセンスと会議 ID をサードパーティ会議プロバイダー、およびその他のダイヤルイン会議設定を設定する、ユーザーに割り当てる手順を参照してください。 "
ms.openlocfilehash: 6fb10654c5845fb5524264219e642cd0a250e860
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization"></a><span data-ttu-id="7ec2b-103">組織用の電話会議の設定を管理します。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-103">Manage the Audio Conferencing settings for my organization</span></span>

<span data-ttu-id="7ec2b-104">簡単にすべての skype for Business と Microsoft チームを 1 か所で電話会議設定を確認する場合があります。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-104">It might be easier for you to see all of the audio conferencing settings for Skype for Business and Microsoft Teams in one place.</span></span> 
  
## <a name="assign-an-audio-conferencing-license"></a><span data-ttu-id="7ec2b-105">音声会議ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="7ec2b-105">Assign an Audio Conferencing license</span></span>

> [!NOTE]
> <span data-ttu-id="7ec2b-p101">**Skype for Business 管理センター**を使用してライセンスを割り当てることはできません。Office 365 管理センターを使用する必要があります。[ビジネスや Microsoft チームのライセンスを割り当てる Skype](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-p101">You can't assign licenses using the **Skype for Business admin center**. You must use the Office 365 admin center. See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span> 
  
 <span data-ttu-id="7ec2b-109">**ユーザーのライセンスを割り当てる**</span><span class="sxs-lookup"><span data-stu-id="7ec2b-109">**To assign a license for a user**</span></span>
  
1. <span data-ttu-id="7ec2b-110">職場または学校のアカウントで Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-110">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="7ec2b-111">**Office 365 管理センター**の左のナビゲーションでの [**ユーザー**] に移動 > **アクティブなユーザー**の場合は、し利用可能なユーザーの一覧からユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-111">In the left navigation of the **Office 365 admin center**, go to **Users** > **Active users**, and then select the user or users from the list of available users.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7ec2b-p102">場合は、同時に最大 20 人のユーザーにライセンスを割り当てる、**ビューの選択**ドロップダウン リストを使用して、オプションのいずれかを選択し、独自のビューを作成したりできます。**編集**、**次回**2 回] をクリックし、ライセンスを選択し、[**送信**] をクリックします。Windows Powershell を使用して複数のユーザーにライセンスを割り当てることもできます。手順とサンプル PowerShell スクリプト、[ビジネスや Microsoft チームのライセンスを割り当てる Skype](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-p102">If you are assigning licenses to up to 20 users at the same time, you can use the **Select a view** drop-down then choose one of the options or create your own view. Then click **Edit**, **Next** twice then select the license and click **Submit**. You can also assign licenses to multiple users by using Windows Powershell. For instructions and sample PowerShell scripts, see [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span> 
  
3. <span data-ttu-id="7ec2b-116">操作ウィンドウの [**製品のライセンス**] で、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-116">In the Action pane under **Product licenses**, click **Edit**.</span></span> 
    
4. <span data-ttu-id="7ec2b-p103">[**製品のライセンス**] ページで**電話会議**を有効にして、[**保存**] をクリックします。ライセンスの詳細は、 [Skype for Business や Microsoft チーム アドオンのライセンス](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-p103">On the **Product Licenses** page, turn on **Audio Conferencing** and then click **Save**. For more on licensing, see [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
    
> [!NOTE]
> <span data-ttu-id="7ec2b-p104">ライセンスを割り当てたら、Microsoft 可能性がありますしない最初にリストに表示、電話会議プロバイダーとしてします。このような場合、Office 365 管理センターからログアウトしするか、ctrl キーを押しながら f5 キーを押してブラウザー ウィンドウを更新します。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-p104">After you assign the license, Microsoft might not appear initially in the list as an audio conferencing provider. If this happens, either log out of the Office 365 admin center or press CTRL+F5 to refresh the browser window.</span></span> 
  
## <a name="assign-a-conference-id-for-a-user"></a><span data-ttu-id="7ec2b-121">ユーザーの会議 ID を割り当てる</span><span class="sxs-lookup"><span data-stu-id="7ec2b-121">Assign a conference ID for a user</span></span>

<span data-ttu-id="7ec2b-p105">会議 ID が自動的に割り当てられているをユーザーに電話会議プロバイダーとして Microsoft を使って電話会議設定している場合。割り当てられている電話会議 ID 静的または動的でき、会議がスケジュールされている場合は、会議の出席依頼の送信します。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-p105">A conference ID is automatically assigned to a user when they are set up for audio conferencing using Microsoft as the audio conferencing provider. The conference ID assigned can be either static or dynamic and is sent in the meeting invite when the meeting is scheduled.</span></span> 
  
<span data-ttu-id="7ec2b-p106">静的な Id は、組織内のユーザーをランダムな番号を保存したくない場合に使用します。特定の番号を選択したり、覚えやすいものを選択することができます。動的会議 Id を使用する場合各会議ユーザーのスケジュールが取得割り当て会議の一意の id。割り当てたい動的静的会議 Id ではなく場合、は、[組織内の電話会議を使用して動的な Id](using-audio-conferencing-dynamic-ids-in-your-organization.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-p106">Static IDs are used when people in your organization don't want to remember a random number; they can select a certain number or choose one that's easy to remember. When dynamic conference IDs are used, each meeting that a user schedules will get assigned a unique conference ID. If you want to assign dynamic rather than static conference IDs, see [Using Audio Conferencing dynamic IDs in your organization](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span></span>
  
<span data-ttu-id="7ec2b-127">Skype for Business 管理センターは、会議 ID をユーザーに割り当てるには使用できませんが、これを行う Windows PowerShell コマンドレットを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-127">The Skype for Business admin center can't be used to assign a conference ID to a user, but you can use the Windows PowerShell cmdlet to do this.</span></span>
  
<span data-ttu-id="7ec2b-128">ユーザーの会議 ID を設定するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-128">To set the conference ID for a user, run:</span></span>
  
```
Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ConferenceId 8271964 
```

> [!IMPORTANT]
> <span data-ttu-id="7ec2b-129">会議 ID が 7 つの数字を含める必要があり、Skype for Business 管理センター、または Windows PowerShell を使用してで変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-129">A conference ID must contain 7 digits, and you can't change it in the Skype for Business admin center or by using Windows PowerShell.</span></span> 
  
<span data-ttu-id="7ec2b-130">コマンドレットの詳細については、[セット CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 )を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-130">See [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) to learn more about the cmdlet.</span></span>
  
> [!IMPORTANT]
>  <span data-ttu-id="7ec2b-p107">新しい会議 ID を作成したら、発信者に応答して古い会議 ID を使用できません。既存ように招待状に ID が追加された新しい会議出席依頼を会議のスケジュールを変更するユーザーに通知する必要があります。ユーザーは、Skype for Business 会議の移行ツールを使用して、既存の会議を更新することができます。ダウンロード、インストール、および Business Meeting Update Tool の Skype を実行する方法を参照してください: [skype for Business と Lync Meeting Update Tool](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)、 [Skype for Business Online、会議の移行ツール (64 ビット)](http://go.microsoft.com/fwlink/?LinkID=626047)、および[Skype for Business Online では、会議移行ツール (32 ビット)](https://www.microsoft.com/en-us/download/details.aspx?id=54079)します。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-p107">After a new conference ID is created, the old conference ID can't be used by callers. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. The users can use the Skype for Business Meeting Migration Tool to update their existing meetings. To see how to download, install, and run the Skype for Business Meeting Update Tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](http://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span></span>
  
<span data-ttu-id="7ec2b-135">[表示、変更、およびユーザーに割り当てられている電話会議 ID をリセットする](see-change-and-reset-a-conference-id-assigned-to-a-user.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-135">See [See, change, and reset a conference ID assigned to a user](see-change-and-reset-a-conference-id-assigned-to-a-user.md).</span></span>
  
## <a name="change-the-audio-conferencing-provider-from-microsoft-to-a-third-party-provider"></a><span data-ttu-id="7ec2b-136">Microsoft からサードパーティ プロバイダーに電話会議プロバイダーを変更します。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-136">Change the audio conferencing provider from Microsoft to a third-party provider</span></span>

1. <span data-ttu-id="7ec2b-137">職場または学校のアカウントで Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-137">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="7ec2b-138">**Office 365 管理センター**に移動 > **Skype for Business**します。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-138">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="7ec2b-139">**Skype for Business 管理センター**、左のナビゲーションで**電話会議**に移動 > **ユーザー**の場合は、電話会議プロバイダーを変更するユーザーを選択し、します。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-139">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, and then and select the user you want to change the audio conferencing provider for.</span></span>
    
4. <span data-ttu-id="7ec2b-140">操作ウィンドウで、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-140">In the Action pane, click **Edit**.</span></span> 
    
5. <span data-ttu-id="7ec2b-141">[**プロパティ**] ページで、[**プロバイダー名**] で、ユーザーの電話会議プロバイダーを選択します。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-141">On the **Properties** page, under **Provider name**, choose the audio conferencing provider for the user.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7ec2b-142">複数のユーザーを選択した場合は、電話会議プロバイダー、[**なし]**として使用して Microsoft を選ぶだけことができます。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-142">You can only select Microsoft as the audio conferencing provider or **None** if you have selected multiple users.</span></span>
  
6. <span data-ttu-id="7ec2b-143">{[**保存**] をクリックします。}</span><span class="sxs-lookup"><span data-stu-id="7ec2b-143">Click **Save**.</span></span> 
    
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a><span data-ttu-id="7ec2b-144">有効にする、または電話会議のユーザーに送信されるメールを無効にします。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-144">Enable or disable emails sent to audio conferencing users</span></span>

<span data-ttu-id="7ec2b-145">有効にする、またはユーザーに送信されたメールを無効にするのには、Skype for Business 管理センター」または「Windows PowerShell を使用できます。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-145">You can use the Skype for Business admin center or Windows PowerShell to enable or disable email sent to users.</span></span>
  
 <span data-ttu-id="7ec2b-146">**Business 管理センターの Skype を使用します。**</span><span class="sxs-lookup"><span data-stu-id="7ec2b-146">**Using the Skype for Business admin center**</span></span>
  
1. <span data-ttu-id="7ec2b-147">職場または学校のアカウントで Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-147">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="7ec2b-148">**Office 365 管理センター**に移動 > **Skype for Business**し、左のナビゲーションで [**電話会議**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-148">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="7ec2b-149">**Microsoft ブリッジの設定**] ページでオンまたはオフの**場合は、電話会議の設定を変更するユーザーにメールを自動的に送信**します。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-149">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>
    
4. <span data-ttu-id="7ec2b-150">{[**保存**] をクリックします。}</span><span class="sxs-lookup"><span data-stu-id="7ec2b-150">Click **Save**.</span></span>
    
    <span data-ttu-id="7ec2b-p108">ユーザーの電話会議のプロパティをクリックして**会議情報を電子メールで送信する**ユーザーに電話会議の設定を含むメールを送信することもできます。会議の出席依頼がない、暗証番号 (pin) では、会議 ID と既定の電話会議の電話番号が含まれます。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-p108">You can also send emails to the user with the audio conferencing settings by going to the user's audio conferencing properties and clicking **Send conference info via email**. The conference ID and default audio conferencing phone number is included on the meeting invite but not the PIN.</span></span>
    
    <span data-ttu-id="7ec2b-153">[この情報は、電話会議情報を持つユーザーに電子メールを送信](send-an-email-to-a-user-with-their-dial-in-information.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-153">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>
    
 <span data-ttu-id="7ec2b-154">**Windows PowerShell を使用します。**</span><span class="sxs-lookup"><span data-stu-id="7ec2b-154">**Using Windows PowerShell**</span></span>
  
- <span data-ttu-id="7ec2b-155">Windows PowerShell を使用してもおよび実行できます。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-155">You can also use the Windows PowerShell and run:</span></span> 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $true|$false
  ```

    <span data-ttu-id="7ec2b-156">メールを含む、組織の他の設定を管理するのには、[セット CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285)を使用できます。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-156">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) to manage other settings for your organization, including email.</span></span>
    
## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a><span data-ttu-id="7ec2b-157">ユーザーに送信されたメール メッセージの送信者の連絡先の情報を変更します。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-157">Change the sender's contact information in email messages sent to users</span></span>

<span data-ttu-id="7ec2b-p109">実際のメール アドレスと、その送信者の連絡先情報の表示名を含む、ユーザーに自動的に送信されるメールに変更を加えたことができます。既定では、メールの送信者には、「Office 365 がメール アドレスを変更して名前を表示する Windows PowerShell と[セット CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285)コマンドレットを使用します。ユーザーにメールを送信するメール アドレスを変更するには、次の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-p109">You can make changes to the email that is automatically sent to your users, including the actual email address and the display name of the sender's contact information. By default, the sender of the emails is Office 365, but you can change the email address and display name using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet. To make changes to the email address that is sending the email to the users, you must:</span></span>
  
- <span data-ttu-id="7ec2b-161">_SendEmailFromAddress_パラメーターには、メール アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-161">Enter the email address in the _SendEmailFromAddress_ parameter.</span></span>
    
- <span data-ttu-id="7ec2b-162">_SendEmailFromDisplayName_パラメーターには、メールの表示名を入力します。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-162">Enter the email display name in the  _SendEmailFromDisplayName_ parameter.</span></span>
    
- <span data-ttu-id="7ec2b-163">_SendEmailOverride_パラメーターを_True_に設定します。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-163">Set the _SendEmailOverride_ parameter to _True_.</span></span>
    
<span data-ttu-id="7ec2b-164">メールが送信されたメール アドレスなどを実行して、メールの表示名のユーザーに送信されたメールに変更を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-164">You can make changes to the email sent to users, such as the email address that the email is sent from or the display name for the email by running:</span></span>
  
```
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

<span data-ttu-id="7ec2b-165">メール アドレスの情報を変更する場合は、組織のメールの受信ポリシーが、ユーザー設定のメール アドレスからメールを許可するかどうかを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-165">If you want to change the email address information, you need to make sure that the inbound email policies of your organization allow emails that come from the custom email address.</span></span>
  
<span data-ttu-id="7ec2b-166">メールを含む、組織の他の設定を管理するのには、[セット CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285)コマンドレットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-166">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet to manage other settings for your organization, including email.</span></span>
  
<span data-ttu-id="7ec2b-167">[ユーザーの電話会議の設定を変更するときに自動的に送信されるメール](emails-sent-to-users-when-their-settings-change.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-167">See [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md).</span></span>
  
## <a name="reset-the-meeting-conference-id"></a><span data-ttu-id="7ec2b-168">会議を再設定する会議 ID</span><span class="sxs-lookup"><span data-stu-id="7ec2b-168">Reset the meeting conference ID</span></span>

1. <span data-ttu-id="7ec2b-169">職場または学校のアカウントで Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-169">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="7ec2b-170">**Office 365 管理センター**に移動 > **Skype for Business**します。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-170">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="7ec2b-171">**Skype for Business 管理センター**、左のナビゲーションで [**電話会議**] に移動し、操作ウィンドウの [**電話会議 ID**で、[**リセット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-171">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and in the Action pane under **Conference ID**, click **Reset**.</span></span>
    
4. <span data-ttu-id="7ec2b-p110">**会議 ID をリセットですか?**ウィンドウで、[**はい**] をクリックします。会議 ID が自動的に作成し、ユーザーに電子メールの送信が有効になっているかどうかは、新しい会議 ID を持つユーザーに電子メールを送信します。既定で有効です。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-p110">In the **Reset conference ID?** window, click **Yes**. A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled. It's enabled by default.</span></span>
    
    > [!IMPORTANT]
    >  <span data-ttu-id="7ec2b-p111">新しい会議 ID を作成したら、発信者に応答して古い会議 ID を使用できません。既存ように招待状に ID が追加された新しい会議出席依頼を会議のスケジュールを変更するユーザーに通知する必要があります。ユーザーは、Skype for Business 会議の移行ツールを使用して、既存の会議を更新することができます。ダウンロード、インストール、および Business Meeting Update Tool の Skype を実行する方法を参照してください: [skype for Business と Lync Meeting Update Tool] ((https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)、 [Skype for Business Online では、会議の移行ツール (64 ビット)](http://go.microsoft.com/fwlink/?LinkID=626047)、 [Skype for Business Online、会議の移行ツール (32 ビット)](https://www.microsoft.com/en-us/download/details.aspx?id=54079)とします。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-p111">After a new conference ID is created, the old conference ID can't be used by callers. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. The users can use the Skype for Business Meeting Migration Tool to update their existing meetings. To see how to download, install, and run the Skype for Business Meeting Update Tool, see: [Meeting Update Tool for Skype for Business and Lync]((https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](http://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span></span>
  
<span data-ttu-id="7ec2b-179">[ユーザーの会議 ID をリセットする](reset-a-conference-id-for-a-user.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-179">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).</span></span>
  
## <a name="reset-a-conference-organizers-pin"></a><span data-ttu-id="7ec2b-180">会議の開催者の PIN をリセットします。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-180">Reset a conference organizer's PIN</span></span>

<span data-ttu-id="7ec2b-p112">静的な Id は、組織内のユーザーをランダムな番号を保存したくない場合に使用します。特定の番号を選択したり、覚えやすいものを使用することができます。動的会議 Id を使用する場合各会議ユーザーのスケジュールが取得割り当て会議の一意の id。場合は、割り当てる静的会議 Id、[組織内の電話会議を使用して動的な Id](using-audio-conferencing-dynamic-ids-in-your-organization.md)ではなく動的します。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-p112">Static IDs are used when people in your organization don't want to remember a random number; they can select a certain number or use one that's easy to remember. When dynamic conference IDs are used, each meeting that a user schedules will get assigned a unique conference ID. If you want to assign dynamic rather than static conference IDs, [Using Audio Conferencing dynamic IDs in your organization](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span></span>
  
<span data-ttu-id="7ec2b-p113">静的会議 ID が自動的に作成され、ユーザーに割り当てられているがありますとユーザーが使用して、特定の数を設定するまたはユーザーに、会議 ID が喪失したか、思い出せないSkype for Business 管理センターと Windows PowerShell を使用するには、表示、変更、および、会議 ID をリセットするには</span><span class="sxs-lookup"><span data-stu-id="7ec2b-p113">Although a static conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or your users can't remember or have lost their conference ID. You can use the Skype for Business admin center and Windows PowerShell to view, change, and reset their conference ID.</span></span>
  
1. <span data-ttu-id="7ec2b-186">職場または学校のアカウントで Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-186">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="7ec2b-187">**Office 365 管理センター**に移動 > **Skype for Business**し、左のナビゲーションで [**電話会議**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-187">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="7ec2b-188">**ユーザー**] をクリックし、[の PIN をリセットするユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-188">Click **Users**, and then select the user that you want to reset the PIN for.</span></span>
    
4. <span data-ttu-id="7ec2b-189">操作ウィンドウで、**暗証番号 (pin)**、[**リセット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-189">In the Action pane, under **PIN**, click **Reset**.</span></span>
    
<span data-ttu-id="7ec2b-p114">電話会議の PIN をリセットするときの有効なしているとき、ユーザーは自分の PIN とメールを受信します。自動的に無効にした場合、メールを送信する PIN のリセット メールに送られませんし、手動で PIN をユーザーに送信する必要があります。PIN がのみ後に表示される 1 回が再設定します。ユーザーのプロパティにリセットした後が表示されたら、PIN をなった表示されません。代わりに、。 が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-p114">Users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset. But if you have disabled automatically sending emails, a PIN reset email won't be sent and you will have to manually send the PIN to the user. The PIN will only be shown once after it has been reset. After it's displayed just after being reset, the PIN won't be shown anymore on the user properties; instead, \*\*\*\*\* will be shown.</span></span> 
  
<span data-ttu-id="7ec2b-194">[ユーザーの音声会議の PIN のリセット](reset-the-audio-conferencing-pin-for-a-user.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-194">See [Reset the Audio Conferencing PIN for a user](reset-the-audio-conferencing-pin-for-a-user.md).</span></span>
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="7ec2b-195">ユーザーに電話会議の情報を含む電子メールを送信します。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-195">Send an email with Audio Conferencing information to a user</span></span>

1. <span data-ttu-id="7ec2b-196">職場または学校のアカウントで Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-196">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="7ec2b-197">**Office 365 管理センター**に移動 > **Skype for Business**し、左のナビゲーションで [**電話会議**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-197">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="7ec2b-198">**ユーザー**] をクリックし、[の PIN をリセットするユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-198">Click **Users**, and then select the user that you want to reset the PIN for.</span></span>
    
4. <span data-ttu-id="7ec2b-199">操作ウィンドウで、**会議情報を電子メールで送信する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-199">In the Action pane, click **Send conference info via email**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7ec2b-200">これを行うときに電話会議の PIN いない、[ユーザーに送信します。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-200">When you do this, the audio conferencing PIN isn't sent to the user.</span></span> 
  
<span data-ttu-id="7ec2b-201">[この情報は、電話会議情報を持つユーザーに電子メールを送信](send-an-email-to-a-user-with-their-dial-in-information.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-201">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>
  
## <a name="setting-the-default-audio-conferencing-phone-number-for-meeting-organizers"></a><span data-ttu-id="7ec2b-202">会議の開催者の既定の電話会議の電話番号を設定します。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-202">Setting the default audio conferencing phone number for meeting organizers</span></span>

 <span data-ttu-id="7ec2b-203">**電話会議のユーザーを有効にする場合に会議の開催者の既定の電話会議の電話番号を設定するには**</span><span class="sxs-lookup"><span data-stu-id="7ec2b-203">**To set the default audio conferencing phone number for meeting organizers when you are enabling a user for Audio Conferencing**</span></span>
  
1. <span data-ttu-id="7ec2b-204">職場または学校のアカウントで Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-204">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="7ec2b-205">**Office 365 管理センター**に移動 > **Skype for Business**します。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-205">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="7ec2b-p115">左のナビゲーションで**電話会議**に移動 > **ユーザー**。電話会議を有効にユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-p115">In the left navigation, go to **Audio conferencing** > **Users**. Select the user that you want to enable for Audio Conferencing.</span></span>
    
4. <span data-ttu-id="7ec2b-208">ユーザーのプロパティ] で、操作ウィンドウで [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-208">In the Action pane, in the user's properties, click **Edit**.</span></span>
    
5. <span data-ttu-id="7ec2b-209">[**プロパティ**] ページで、[**プロバイダー名**] でドロップダウン リストを使用して、電話会議プロバイダーを選択します。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-209">On the **Properties** page, under **Provider name**, use the drop-down list to select the audio conferencing provider.</span></span>
    
  - <span data-ttu-id="7ec2b-210">電話会議プロバイダーとして Microsoft を選択すると、一覧から既定の電話会議の電話番号を選択します。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-210">If you select Microsoft as the audio conferencing provider, you can choose the default audio conferencing phone number from the list.</span></span>  
    
  - <span data-ttu-id="7ec2b-p116">電話会議プロバイダーとしてサードパーティ ACP を選ぶ場合有料を手動で入力する必要があり、必要に応じて、フリー ダイヤル電話番号です。これらの電話番号を既定の電話番号となります。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-p116">If you select a third-party ACP as the audio conferencing provider, you will need to manually enter the Toll and if required, the Toll-free phone number. These phone numbers will be the default phone number.</span></span>
    
    <span data-ttu-id="7ec2b-213">ユーザーの既定の電話会議の電話番号は、会議をスケジュールする場合は、会議の出席依頼に表示される数です。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-213">The default audio conferencing phone number of a user is the number that is shown on the meeting invite when they schedule a meeting.</span></span>
    
6. <span data-ttu-id="7ec2b-214">{[**保存**] をクリックします。}</span><span class="sxs-lookup"><span data-stu-id="7ec2b-214">Click **Save**.</span></span> 
    
<span data-ttu-id="7ec2b-215">[携帯電話への招待に含まれる数値の設定](set-the-phone-numbers-included-on-invites.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-215">See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites.md).</span></span>
  
 <span data-ttu-id="7ec2b-216">**電話会議のユーザーを有効にした後に会議の開催者の既定の電話会議の電話番号を設定するには**</span><span class="sxs-lookup"><span data-stu-id="7ec2b-216">**To set the default audio conferencing phone number for meeting organizers after you have enabled a user for audio conferencing**</span></span>
  
1. <span data-ttu-id="7ec2b-217">職場または学校のアカウントで Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-217">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="7ec2b-218">**Office 365 管理センター**に移動 > **Skype for Business**します。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-218">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="7ec2b-219">**Skype for Business 管理センター**、左のナビゲーションで**電話会議**に移動 > **ユーザー**の場合は、必要なユーザーを選択し、[アクション] ページで、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-219">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, select the user you want, and in the Action page, click **Edit**.</span></span>
    
4. <span data-ttu-id="7ec2b-220">[**プロパティ**] ページで、[**プロバイダー名**] でドロップダウン リストを使用して、電話会議プロバイダーを選択します。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-220">On the **Properties** page, under **Provider name**, use the drop-down list to select the audio conferencing provider.</span></span>
    
  - <span data-ttu-id="7ec2b-221">ユーザーは、電話会議プロバイダーとして Microsoft を使用している場合は、一覧から既定の電話会議の電話番号を選択できます。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-221">If the user uses Microsoft as the audio conferencing provider, you can choose the default audio conferencing phone number from the list.</span></span>  
    
  - <span data-ttu-id="7ec2b-222">ユーザーは、電話会議プロバイダーとしてのサードパーティ ACP を使用している場合は、有料に手動で入力する必要があり、フリー ダイヤル電話番号を必要に応じてします。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-222">If the user uses a third-party ACP as the audio conferencing provider, you will need to manually enter the Toll and if required, the Toll-free phone number.</span></span>
    
    <span data-ttu-id="7ec2b-223">ユーザーの既定の電話会議の電話番号は、会議をスケジュールする場合は、会議の出席依頼に表示される数です。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-223">The default audio conferencing phone number of a user is the number that is shown on the meeting invite when they schedule a meeting.</span></span>
    
5. <span data-ttu-id="7ec2b-224">{[**保存**] をクリックします。}</span><span class="sxs-lookup"><span data-stu-id="7ec2b-224">Click **Save**.</span></span> 
    
<span data-ttu-id="7ec2b-225">[携帯電話への招待に含まれる数値の設定](set-the-phone-numbers-included-on-invites.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-225">See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites.md).</span></span>
  
## <a name="setting-audio-conferencing-bridge-settings"></a><span data-ttu-id="7ec2b-226">電話会議ブリッジの設定</span><span class="sxs-lookup"><span data-stu-id="7ec2b-226">Setting audio conferencing bridge settings</span></span>

 <span data-ttu-id="7ec2b-227">**発信者が会議に参加するときに、会議のエクスペリエンスを設定します。**</span><span class="sxs-lookup"><span data-stu-id="7ec2b-227">**Set the meeting experience when callers join a meeting**</span></span>
  
1. <span data-ttu-id="7ec2b-228">職場または学校のアカウントで Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-228">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="7ec2b-229">**Office 365 管理センター**に移動 > **Skype for Business**します。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-229">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="7ec2b-230">**Skype for Business 管理センター**、左のナビゲーションで**電話会議**に移動 > **Microsoft ブリッジの設定**します。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-230">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="7ec2b-231">[**会議参加エクスペリエンス**には、次の操作を選択します。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-231">Under **Meeting join experience**, select the following actions:</span></span>
    
  - <span data-ttu-id="7ec2b-p117">**会議のエントリを有効にして終了通知を有効にするには**これが既定で選択されます。このチェック ボックスをオフにする場合は、既定では、会議に参加しているユーザーは入力したり、会議のままに通知されません。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-p117">**Enable meeting entry and exit notifications to be turned on** This is selected by default. If you clear this check box, users who have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span></span>
    
    <span data-ttu-id="7ec2b-234">ユーザーが Skype を for Business または Microsoft チームのアプリを使って会議に参加し、[Skype 会議または Microsoft チーム**のオプション**] メニューの [**入ユーザー退室を通知**の設定を変更するときに会議ごとの単位で設定できます、会議します。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-234">This can be set on a meeting-by-meeting basis when a user joins a meeting using a Skype for Business or Microsoft Teams app and they modify the **Announce when people enter or leave** setting in the Skype Meeting or Microsoft Teams **Options** menu of the meeting.</span></span>
    
  - <span data-ttu-id="7ec2b-p118">**質問の発信者**これが既定で選択されます。このチェック ボックスをオフにする場合、発信者が、会議に参加する前に、相手の名前を記録するように依頼されません。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-p118">**Ask callers to record their name before joining the meeting** This is selected by default. If you clear this check box, callers won't be asked to record their name before they join a meeting.</span></span>
    
5. <span data-ttu-id="7ec2b-237">変更が終了したら、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-237">After you make your changes, click **Save**.</span></span>
    
<span data-ttu-id="7ec2b-238">[電話会議ブリッジの設定を変更する](change-the-settings-for-an-audio-conferencing-bridge.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-238">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>
  
 <span data-ttu-id="7ec2b-239">**会議の PIN の長さを設定します。**</span><span class="sxs-lookup"><span data-stu-id="7ec2b-239">**Set the PIN length for meetings**</span></span>
  
1. <span data-ttu-id="7ec2b-240">職場または学校のアカウントで Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-240">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="7ec2b-241">**Office 365 管理センター**に移動 > **Skype for Business**します。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-241">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="7ec2b-242">**Skype for Business 管理センター**、左のナビゲーションで**電話会議**に移動 > **Microsoft ブリッジの設定**します。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-242">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="7ec2b-243">[**セキュリティ**] の**PIN の長さ**] ボックスの一覧で、[PIN の桁数を入力し、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-243">Under **Security**, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>
    
    <span data-ttu-id="7ec2b-p119">4、12 桁の数字の間、暗証番号 (pin) があります。既定では 5 です。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-p119">The PIN must be between 4 and 12 digits. The default is 5.</span></span>
    
<span data-ttu-id="7ec2b-246">[電話会議ブリッジの設定を変更する](change-the-settings-for-an-audio-conferencing-bridge.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-246">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>
  
 <span data-ttu-id="7ec2b-247">**有効にするまたはオーディオのユーザーに送信されるメールを無効にします。**</span><span class="sxs-lookup"><span data-stu-id="7ec2b-247">**Enable or disable email from being sent to audio users**</span></span>
  
1. <span data-ttu-id="7ec2b-248">職場または学校のアカウントで Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-248">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="7ec2b-249">**Office 365 管理センター**に移動 > **Skype for Business**し、左のナビゲーションで [**電話会議**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-249">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="7ec2b-250">**Microsoft ブリッジの設定**] ページでオンまたはオフの**場合は、電話会議の設定を変更するユーザーにメールを自動的に送信**します。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-250">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>
    
4. <span data-ttu-id="7ec2b-251">{[**保存**] をクリックします。}</span><span class="sxs-lookup"><span data-stu-id="7ec2b-251">Click **Save**.</span></span>
    
    <span data-ttu-id="7ec2b-252">ユーザーの電話会議のプロパティをクリックして**会議情報を電子メールで送信する**ユーザーに電話会議の設定] でメールを送信することもできます。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-252">You can also send email to the user with the audio conferencing settings, by going to the user's audio conferencing properties and clicking **Send conference info via email**.</span></span>
    
    <span data-ttu-id="7ec2b-253">これを行う場合は、メールが送信されますが、会議 ID と、会議の電話番号を含むのみ、PIN を含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-253">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span></span>
    
    <span data-ttu-id="7ec2b-254">[この情報は、電話会議情報を持つユーザーに電子メールを送信](send-an-email-to-a-user-with-their-dial-in-information.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-254">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>
    
## <a name="see-and-set-the-primary-and-secondary-languages-on-an-audio-conferencing-bridge"></a><span data-ttu-id="7ec2b-255">表示し、電話会議ブリッジにプライマリおよびセカンダリ言語の設定</span><span class="sxs-lookup"><span data-stu-id="7ec2b-255">See and set the primary and secondary languages on an audio conferencing bridge</span></span>

1. <span data-ttu-id="7ec2b-256">職場または学校のアカウントで Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-256">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="7ec2b-257">**Office 365 管理センター**に移動 > **Skype for Business**します。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-257">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="7ec2b-258">**Skype for Business 管理センター**] で、左のナビゲーションでは、**音声会議**に移動し、[ **Microsoft bridge**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-258">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and then click **Microsoft bridge**.</span></span>
    
4. <span data-ttu-id="7ec2b-259">一覧から電話番号を選択、操作ウィンドウ] の [**言語の設定**] をクリックし、[**言語の設定**] ページで、使用、**主言語**] をクリックし、サポートされている言語のリストを表示します。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-259">Select a phone number from the list, click **Set languages** in the Action pane, and then on the **Set languages** page, click the use the **Primary language** list to view the complete list of supported languages.</span></span>
    
    <span data-ttu-id="7ec2b-p120">電話会議プロバイダーとして Microsoft を選ぶときにサポートされているプライマリおよびセカンダリ言語を設定することもできます。リストで選択した順序は、同じ順序の発信者に応答する言語が表示されますです。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-p120">You can also set the primary and secondary languages that are supported when you select Microsoft as the audio conferencing provider. The order that you select in the lists is the same order in which languages will be presented to callers.</span></span>
    
<span data-ttu-id="7ec2b-262">[電話会議の自動応答の言語を設定する](set-auto-attendant-languages-for-audio-conferencing.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-262">See [Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing.md).</span></span>
  
## <a name="see-audio-conferencing-dial-in-numbers"></a><span data-ttu-id="7ec2b-263">電話会議にダイヤルイン番号が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-263">See audio conferencing dial-in numbers</span></span>

1. <span data-ttu-id="7ec2b-264">職場または学校のアカウントで Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-264">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="7ec2b-265">**Office 365 管理センター**に移動 > **Skype for Business**します。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-265">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="7ec2b-p121">**Skype for Business 管理センター**、左のナビゲーションで**電話会議**に移動 > **Microsoft ブリッジ**します。ここで次のようなことができます。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-p121">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge**. Here you can:</span></span>
    
  - <span data-ttu-id="7ec2b-268">電話会議のために、Office 365 によって設定されている電話番号を表示します。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-268">View the phone numbers that are set by Office 365 to be used for Audio Conferencing.</span></span> 
    
  - <span data-ttu-id="7ec2b-269">場所、および音声会議の自動応答で使用されるプライマリおよびセカンダリ言語を表示します。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-269">View the location, and the primary and secondary languages, that will be used by the Audio Conferencing auto attendant.</span></span>
    
  - <span data-ttu-id="7ec2b-p122">音声会議が有効なときに、ユーザーに指定される既定の電話番号を選択します。電話会議ブリッジの既定の電話番号を変更する場合は、既存ユーザーに対して既定の電話番号は変更されません。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-p122">Select the default phone number that will be given to users when they are enabled for Audio Conferencing. However, if the default phone number of the audio conferencing bridge changes, the default phone number for existing users won't change.</span></span>
    
<span data-ttu-id="7ec2b-272">**電話会議**に移動できる > **ユーザー**と既定値を変更するのには、ユーザーのプロパティは、組織で使用できる番号の一覧から新しい番号を選択し、ユーザーの番号を選択します。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-272">You can go to **Audio conferencing** > **Users** and select the user's properties to change the default number for a user by choosing a new number from the list of numbers that are available in your organization.</span></span>
  
<span data-ttu-id="7ec2b-273">[電話会議の数値のリストを表示する](see-a-list-of-audio-conferencing-numbers.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-273">See [See a list of Audio Conferencing numbers](see-a-list-of-audio-conferencing-numbers.md).</span></span>
  
## <a name="see-a-list-of-users-that-are-enabled"></a><span data-ttu-id="7ec2b-274">有効になっているユーザーの一覧を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-274">See a list of users that are enabled</span></span>

1. <span data-ttu-id="7ec2b-275">職場または学校のアカウントで Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-275">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="7ec2b-276">**Office 365 管理センター**に移動 > **Skype for Business**します。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-276">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="7ec2b-277">**Skype for Business 管理センター**、左のナビゲーションで**電話会議**に移動 >、[**ユーザー**。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-277">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**> and then **Users**.</span></span>
    
<span data-ttu-id="7ec2b-278">[電話会議を有効になっているユーザーのリストを表示する](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-278">See [See a list of users that are enabled for Audio Conferencing](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).</span></span>
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="7ec2b-279">Windows PowerShell で管理する方法を知りたいとしていますか。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-279">Want to know how to manage with Windows PowerShell?</span></span>

<span data-ttu-id="7ec2b-p123">Windows PowerShell を使用して組織レベルで管理できるいくつかの設定があります。これにより、簡単にすべてのユーザーに設定を適用します。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-p123">There are several settings that you can manage at the organization level using Windows PowerShell. This makes it easy to apply settings to all of your users.</span></span> 
    
<span data-ttu-id="7ec2b-282">各コマンドレットのヘルプを表示する、 [Skype for Business Online のコマンドレット](https://go.microsoft.com/fwlink/?LinkId=627324)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-282">To get more help on each cmdlet, see [Skype for Business Online cmdlets](https://go.microsoft.com/fwlink/?LinkId=627324).</span></span>

<span data-ttu-id="7ec2b-283">組織レベルの設定を紹介します。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-283">Here are the organization-level settings:</span></span> 
> 
- <span data-ttu-id="7ec2b-284">**開始/終了通知を設定します。**既定では_$true です_。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-284">**Setting entry/exit notifications** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableEntryExitNotifications $true|$false 
  ```

- <span data-ttu-id="7ec2b-285">**レコーディングの名前を設定します。**既定では_$true です_。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-285">**Setting name recording** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableNameRecording $true|false
  ```

- <span data-ttu-id="7ec2b-286">**PIN の長さを設定します。**既定では 5 です。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-286">**Setting the PIN length** The default is 5.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -PinLength 7
  ```

- <span data-ttu-id="7ec2b-287">**のみのダイヤルイン会議電話からを設定します。**既定の_$false_します。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-287">**Setting only dial-in meetings from a phone** The default _$false_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true|$false
  ```

- <span data-ttu-id="7ec2b-288">**ユーザーにメールを送信するかどうかを設定します。**既定では_$true です_。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-288">**Setting whether to send email to users** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

- <span data-ttu-id="7ec2b-289">**別のアカウントからメールを送信するかどうかを設定します。**既定では_$false です_。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-289">**Setting whether to send email from a different account** The default is  _$false_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromOverride $true|$false
  ```

- <span data-ttu-id="7ec2b-290">**ユーザーに送信されるメールの差出人アドレスを設定します。**既定では_$null です_。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-290">**Setting the From address on email that is sent to users** The default is _$null_.</span></span> 
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromAddress
  ```

- <span data-ttu-id="7ec2b-291">**ユーザーに送信されるメールの表示名を設定します。**既定では_$null です_。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-291">**Setting the display name for the email that is sent to users** The default is  _$null_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromDisplayName
  ```

 ## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="7ec2b-292">Windows PowerShell の詳細を知りたいです。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-292">Want to know more about Windows PowerShell</span></span>   
- <span data-ttu-id="7ec2b-p124">Windows PowerShell がユーザーを管理するユーザーを許可または使用できません。Windows PowerShell で複数のタスクを実行するがある場合、日常業務を簡素化する管理の 1 つのポイントを使用して Office 365 を管理できます。Windows PowerShell で開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-p124">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="7ec2b-296">Office 365 PowerShell を使用する必要がある理由</span><span class="sxs-lookup"><span data-stu-id="7ec2b-296">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="7ec2b-297">Windows PowerShell で Office 365 を管理する最善の方法</span><span class="sxs-lookup"><span data-stu-id="7ec2b-297">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="7ec2b-p125">Windows PowerShell では多くの利点速度、わかりやすいように、および生産性でのみ実行しようとする設定の変更、多くのユーザーに一度になど、Office 365 管理センターを使用します。次のトピックでこれらの利点について学習します。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-p125">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time. Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="7ec2b-300">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="7ec2b-300">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="7ec2b-301">Windows PowerShell を使用して、Skype for Business Online の管理するには</span><span class="sxs-lookup"><span data-stu-id="7ec2b-301">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="7ec2b-302">Windows PowerShell を使用して、共通の Skype for Business Online の管理タスクを実行するには</span><span class="sxs-lookup"><span data-stu-id="7ec2b-302">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    <span data-ttu-id="7ec2b-p126">Skype for Business Online 用の Windows PowerShell モジュールを使用すると、Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成することができます。このモジュールでは、64 ビット コンピューター以外では、Microsoft ダウンロード センターからダウンロードできます[Skype for Business Online 用の Windows PowerShell モジュール](https://go.microsoft.com/fwlink/?LinkId=294688)。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-p126">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="7ec2b-305">関連トピック</span><span class="sxs-lookup"><span data-stu-id="7ec2b-305">Related topics</span></span>

[<span data-ttu-id="7ec2b-306">ユーザーの電話会議の設定を管理します。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-306">Manage the Audio Conferencing settings for a user</span></span>](manage-the-audio-conferencing-settings-for-a-user.md)

[<span data-ttu-id="7ec2b-307">Skype for Business とチームの Microsoft の音声会議をセットアップする設定します。</span><span class="sxs-lookup"><span data-stu-id="7ec2b-307">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](set-up-audio-conferencing.md)

