---
title: "組織内でのオーディオ会議設定を管理します。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: bc9bd328-c5b2-44e5-af15-e02bf00e1c81
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "サード パーティ製会議プロバイダー、およびその他のダイヤルイン会議の設定を設定、ユーザーにダイヤルイン会議のライセンスおよび会議 ID を割り当てる手順を参照してください。 "
ms.openlocfilehash: 6bca89f60c5ee4e9b840d2094500077cfa972902
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/15/2017
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization"></a><span data-ttu-id="0798a-103">組織内でのオーディオ会議設定を管理します。</span><span class="sxs-lookup"><span data-stu-id="0798a-103">Manage the Audio Conferencing settings for my organization</span></span>

<span data-ttu-id="0798a-104">容易にするすべてのビジネスおよびマイクロソフトのチームで 1 つの場所に Skype の電話会議の設定を表示する場合があります。</span><span class="sxs-lookup"><span data-stu-id="0798a-104">It might be easier for you to see all of the audio conferencing settings for Skype for Business and Microsoft Teams in one place.</span></span> 
  
## <a name="assign-an-audio-conferencing-license"></a><span data-ttu-id="0798a-105">オーディオ会議のライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="0798a-105">Assign an Audio Conferencing license</span></span>

> [!NOTE]
> <span data-ttu-id="0798a-106">**ビジネス管理センターの Skype**を使用してライセンスを割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="0798a-106">You can't assign licenses using the **Skype for Business admin center**.</span></span> <span data-ttu-id="0798a-107">Office 365 管理センターを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0798a-107">You must use the Office 365 admin center.</span></span> <span data-ttu-id="0798a-108">[ビジネスおよびマイクロソフトのチームのライセンスを Skype を割り当てる](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0798a-108">See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span> 
  
 <span data-ttu-id="0798a-109">**ユーザーのライセンスを割り当てるには**</span><span class="sxs-lookup"><span data-stu-id="0798a-109">**To assign a license for a user**</span></span>
  
1. <span data-ttu-id="0798a-110">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="0798a-110">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="0798a-111">**Office 365 管理センター**の左側のナビゲーションでは、**ユーザー**に移動 > **アクティブなユーザー**の利用可能なユーザーの一覧からユーザーまたはユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="0798a-111">In the left navigation of the **Office 365 admin center**, go to **Users** > **Active users**, and then select the user or users from the list of available users.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0798a-112">場合は同時に最大 20 個のユーザーにライセンスを割り当てる場合は、**ビューを選択して**ドロップダウン リストを使用し、オプションのいずれかを選択したり、独自のビューを作成できます。</span><span class="sxs-lookup"><span data-stu-id="0798a-112">If you are assigning licenses to up to 20 users at the same time, you can use the **Select a view** drop-down then choose one of the options or create your own view.</span></span> <span data-ttu-id="0798a-113">**編集**、**次へ**2 回クリックし、ライセンスを選択し、[**送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0798a-113">Then click **Edit**, **Next** twice then select the license and click **Submit**.</span></span> <span data-ttu-id="0798a-114">Windows Powershell を使用して複数のユーザーにライセンスを割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="0798a-114">You can also assign licenses to multiple users by using Windows Powershell.</span></span> <span data-ttu-id="0798a-115">手順とサンプルの PowerShell スクリプトでは、[ビジネスおよびマイクロソフトのチームのライセンスを Skype を割り当てる](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0798a-115">For instructions and sample PowerShell scripts, see [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span> 
  
3. <span data-ttu-id="0798a-116">操作ウィンドウの [ **製品ライセンス**] で [ **編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0798a-116">In the Action pane under **Product licenses**, click **Edit**.</span></span> 
    
4. <span data-ttu-id="0798a-117">[**製品ライセンス**] ページで、**電話会議**を有効にして、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0798a-117">On the **Product Licenses** page, turn on **Audio Conferencing** and then click **Save**.</span></span> <span data-ttu-id="0798a-118">ライセンスの詳細は、 [Skype](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0798a-118">For more on licensing, see [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
    
> [!NOTE]
> <span data-ttu-id="0798a-119">ライセンスを割り当てると、Microsoft が最初に一覧に表示されない、オーディオ会議プロバイダーとして。</span><span class="sxs-lookup"><span data-stu-id="0798a-119">After you assign the license, Microsoft might not appear initially in the list as an audio conferencing provider.</span></span> <span data-ttu-id="0798a-120">このような場合は、Office 365 の管理ページからログアウトするか、CTRL + f5 キーを押してブラウザー ウィンドウを更新します。</span><span class="sxs-lookup"><span data-stu-id="0798a-120">If this happens, either log out of the Office 365 admin center or press CTRL+F5 to refresh the browser window.</span></span> 
  
## <a name="assign-a-conference-id-for-a-user"></a><span data-ttu-id="0798a-121">ユーザーの会議 ID を割り当てる</span><span class="sxs-lookup"><span data-stu-id="0798a-121">Assign a conference ID for a user</span></span>

<span data-ttu-id="0798a-122">会議 ID が自動的に割り当てられているユーザーに電話会議のオーディオ会議プロバイダーとして Microsoft を使用する設定している場合。</span><span class="sxs-lookup"><span data-stu-id="0798a-122">A conference ID is automatically assigned to a user when they are set up for audio conferencing using Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="0798a-123">会議 ID が割り当てられている静的または動的のどちらかにすることができ、会議がスケジュールされているときに会議出席依頼の送信します。</span><span class="sxs-lookup"><span data-stu-id="0798a-123">The conference ID assigned can be either static or dynamic and is sent in the meeting invite when the meeting is scheduled.</span></span> 
  
<span data-ttu-id="0798a-124">静的の Id は、組織内のユーザーはランダムな番号を覚えておく必要があるときに使用します。特定の番号を選択したり、覚えやすいものを選択することができます。</span><span class="sxs-lookup"><span data-stu-id="0798a-124">Static IDs are used when people in your organization don't want to remember a random number; they can select a certain number or choose one that's easy to remember.</span></span> <span data-ttu-id="0798a-125">動的会議 Id を使用する場合各会議ユーザのスケジュールは割り当てられます会議の一意の id。</span><span class="sxs-lookup"><span data-stu-id="0798a-125">When dynamic conference IDs are used, each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="0798a-126">割り当てる静的な会議 Id ではなく動的をする場合は、[組織内のオーディオ会議を使用して動的な Id](using-audio-conferencing-dynamic-ids-in-your-organization.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0798a-126">If you want to assign dynamic rather than static conference IDs, see [Using Audio Conferencing dynamic IDs in your organization](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span></span>
  
<span data-ttu-id="0798a-127">ビジネス管理センターの Skype は、ユーザーに会議 ID を割り当てるには使用できませんが、Windows PowerShell コマンドレットを使用してこれを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="0798a-127">The Skype for Business admin center can't be used to assign a conference ID to a user, but you can use the Windows PowerShell cmdlet to do this.</span></span>
  
<span data-ttu-id="0798a-128">ユーザーの会議 ID を設定するのには次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0798a-128">To set the conference ID for a user, run:</span></span>
  
```
Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ConferenceId 8271964 
```

> [!IMPORTANT]
> <span data-ttu-id="0798a-129">会議 ID が 7 桁の数字を含める必要があり、ビジネス管理センターまたは Windows PowerShell を使用して、Skype で変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="0798a-129">A conference ID must contain 7 digits, and you can't change it in the Skype for Business admin center or by using Windows PowerShell.</span></span> 
  
<span data-ttu-id="0798a-130">コマンドレットの詳細については、[設定 CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 )を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0798a-130">See [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) to learn more about the cmdlet.</span></span>
  
> [!IMPORTANT]
>  <span data-ttu-id="0798a-131">新しい会議 ID が作成されると、呼び出し元が古い会議 ID を使用できません。</span><span class="sxs-lookup"><span data-stu-id="0798a-131">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="0798a-132">ミーティングの招待新しい会議 ID が、招待状に追加されることを確認するのには、既存のスケジュールを変更するのにはユーザーに通知する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0798a-132">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="0798a-133">ユーザーは、ビジネス会議の移行ツールの Skype を使用して、既存の会議を更新します。</span><span class="sxs-lookup"><span data-stu-id="0798a-133">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="0798a-134">ダウンロード、インストール、および、Skype をビジネス会議の更新ツールを実行する方法を参照してください:[ビジネスと Lync の Skype の会議の更新ツール](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)、 [Skype](http://go.microsoft.com/fwlink/?LinkID=626047)、および[のビジネス オンラインでは、Skype 会議移行ツール (32 ビット)](https://www.microsoft.com/en-us/download/details.aspx?id=54079)。</span><span class="sxs-lookup"><span data-stu-id="0798a-134">To see how to download, install, and run the Skype for Business Meeting Update Tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](http://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span></span>
  
<span data-ttu-id="0798a-135">[参照してください、変更、およびユーザーに割り当てられている会議 ID のリセット](see-change-and-reset-a-conference-id-assigned-to-a-user.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0798a-135">See [See, change, and reset a conference ID assigned to a user](see-change-and-reset-a-conference-id-assigned-to-a-user.md).</span></span>
  
## <a name="change-the-audio-conferencing-provider-from-microsoft-to-a-third-party-provider"></a><span data-ttu-id="0798a-136">マイクロソフトからサード パーティのプロバイダーに、オーディオ会議プロバイダーを変更します。</span><span class="sxs-lookup"><span data-stu-id="0798a-136">Change the audio conferencing provider from Microsoft to a third-party provider</span></span>

1. <span data-ttu-id="0798a-137">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="0798a-137">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="0798a-138">**Office 365 管理センター**を参照して > **ビジネス用の Skype**です。</span><span class="sxs-lookup"><span data-stu-id="0798a-138">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="0798a-139">**電話会議**には、**ビジネス管理センターの Skype**、左側のナビゲーションでの > **ユーザー**、オーディオ会議プロバイダーを変更するユーザーを選択し、します。</span><span class="sxs-lookup"><span data-stu-id="0798a-139">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, and then and select the user you want to change the audio conferencing provider for.</span></span>
    
4. <span data-ttu-id="0798a-140">操作ウィンドウで、[ **編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0798a-140">In the Action pane, click **Edit**.</span></span> 
    
5. <span data-ttu-id="0798a-141">[**プロパティ**] ページの [**プロバイダー名**] で、ユーザーの電話会議プロバイダーを選択します。</span><span class="sxs-lookup"><span data-stu-id="0798a-141">On the **Properties** page, under **Provider name**, choose the audio conferencing provider for the user.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0798a-142">のみ、複数のユーザーを選択した場合、Microsoft をオーディオ会議プロバイダー、または**[なし]**として選択できます。</span><span class="sxs-lookup"><span data-stu-id="0798a-142">You can only select Microsoft as the audio conferencing provider or **None** if you have selected multiple users.</span></span>
  
6. <span data-ttu-id="0798a-143">[ **保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0798a-143">Click **Save**.</span></span> 
    
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a><span data-ttu-id="0798a-144">有効にするか、オーディオ会議のユーザーに送信された電子メールを無効にします。</span><span class="sxs-lookup"><span data-stu-id="0798a-144">Enable or disable emails sent to audio conferencing users</span></span>

<span data-ttu-id="0798a-145">有効にするか、ユーザーに送信される電子メールを無効にするのには、ビジネス管理センターの Skype または Windows PowerShell を使用できます。</span><span class="sxs-lookup"><span data-stu-id="0798a-145">You can use the Skype for Business admin center or Windows PowerShell to enable or disable email sent to users.</span></span>
  
 <span data-ttu-id="0798a-146">**ビジネス管理センターに、Skype を使用します。**</span><span class="sxs-lookup"><span data-stu-id="0798a-146">**Using the Skype for Business admin center**</span></span>
  
1. <span data-ttu-id="0798a-147">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="0798a-147">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="0798a-148">**Office 365 管理センター**を参照して > **ビジネス用の Skype**の左側のナビゲーションでは、[**電話会議**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0798a-148">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="0798a-149">**Microsoft ブリッジの設定**] ページをオンまたはオフの**オーディオ会議の設定を変更する場合、ユーザーに e メールを自動的に送信**する。</span><span class="sxs-lookup"><span data-stu-id="0798a-149">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>
    
4. <span data-ttu-id="0798a-150">[ **保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0798a-150">Click **Save**.</span></span>
    
    <span data-ttu-id="0798a-151">電子メールを送信するユーザーに電話会議の設定を使用してユーザーのオーディオ会議のプロパティに移動し、**電子メールを使用して会議情報を送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0798a-151">You can also send emails to the user with the audio conferencing settings by going to the user's audio conferencing properties and clicking **Send conference info via email**.</span></span> <span data-ttu-id="0798a-152">会議 ID と既定の電話会議の電話番号は、会議出席依頼がない、暗証番号 (pin) に含まれています。</span><span class="sxs-lookup"><span data-stu-id="0798a-152">The conference ID and default audio conferencing phone number is included on the meeting invite but not the PIN.</span></span>
    
    <span data-ttu-id="0798a-153">[オーディオ会議の情報を持つユーザーに電子メールを送信する](send-an-email-to-a-user-with-their-dial-in-information.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0798a-153">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>
    
 <span data-ttu-id="0798a-154">**Windows PowerShell を使用します。**</span><span class="sxs-lookup"><span data-stu-id="0798a-154">**Using Windows PowerShell**</span></span>
  
- <span data-ttu-id="0798a-155">Windows PowerShell を使用して実行します。</span><span class="sxs-lookup"><span data-stu-id="0798a-155">You can also use the Windows PowerShell and run:</span></span> 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $true|$false
  ```

    <span data-ttu-id="0798a-156">[セット CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285)を使用すると、メールを含む、組織の他の設定を管理します。</span><span class="sxs-lookup"><span data-stu-id="0798a-156">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) to manage other settings for your organization, including email.</span></span>
    
## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a><span data-ttu-id="0798a-157">ユーザーに送信される電子メール メッセージ内の送信者の連絡先情報を変更します。</span><span class="sxs-lookup"><span data-stu-id="0798a-157">Change the sender's contact information in email messages sent to users</span></span>

<span data-ttu-id="0798a-158">実際の電子メール アドレス、送信者の連絡先情報の表示名など、ユーザーに自動的に送信される電子メールの変更を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="0798a-158">You can make changes to the email that is automatically sent to your users, including the actual email address and the display name of the sender's contact information.</span></span> <span data-ttu-id="0798a-159">既定では、電子メールの送信者には、Office 365 は、電子メール アドレスを変更し、名前を表示できます Windows PowerShell と[セット CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285)コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="0798a-159">By default, the sender of the emails is Office 365, but you can change the email address and display name using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet.</span></span> <span data-ttu-id="0798a-160">ユーザーに電子メールを送信する電子メール アドレスを変更するには、次の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="0798a-160">To make changes to the email address that is sending the email to the users, you must:</span></span>
  
- <span data-ttu-id="0798a-161">_SendEmailFromAddress_パラメーターでは、電子メール アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="0798a-161">Enter the email address in the _SendEmailFromAddress_ parameter.</span></span>
    
- <span data-ttu-id="0798a-162">_SendEmailFromDisplayName_ パラメーターにメールの表示名を入力する</span><span class="sxs-lookup"><span data-stu-id="0798a-162">Enter the email display name in the  _SendEmailFromDisplayName_ parameter.</span></span>
    
- <span data-ttu-id="0798a-163">_SendEmailOverride_パラメーターを_True_に設定します。</span><span class="sxs-lookup"><span data-stu-id="0798a-163">Set the _SendEmailOverride_ parameter to _True_.</span></span>
    
<span data-ttu-id="0798a-164">電子メールが送信される電子メール アドレス、またはを実行して、電子メールの表示名など、ユーザーに送信された電子メールに変更を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="0798a-164">You can make changes to the email sent to users, such as the email address that the email is sent from or the display name for the email by running:</span></span>
  
```
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

<span data-ttu-id="0798a-165">電子メール アドレス情報を変更する場合は、組織の受信電子メール ポリシーがカスタムの電子メール アドレスから送信されるメールを許可するかどうかを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0798a-165">If you want to change the email address information, you need to make sure that the inbound email policies of your organization allow emails that come from the custom email address.</span></span>
  
<span data-ttu-id="0798a-166">[セット CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285)コマンドレットを使用するとメールを含む、組織の他の設定を管理するのにことができます。</span><span class="sxs-lookup"><span data-stu-id="0798a-166">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet to manage other settings for your organization, including email.</span></span>
  
<span data-ttu-id="0798a-167">[ユーザーが電話会議の設定を変更するときに自動的に送信される電子メール](emails-sent-to-users-when-their-settings-change.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0798a-167">See [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md).</span></span>
  
## <a name="reset-the-meeting-conference-id"></a><span data-ttu-id="0798a-168">リセット会議会議 ID</span><span class="sxs-lookup"><span data-stu-id="0798a-168">Reset the meeting conference ID</span></span>

1. <span data-ttu-id="0798a-169">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="0798a-169">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="0798a-170">**Office 365 管理センター**を参照して > **ビジネス用の Skype**です。</span><span class="sxs-lookup"><span data-stu-id="0798a-170">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="0798a-171">**Skype**ビジネス管理センターは、左側のナビゲーションでの**オーディオ会議**、および [操作] ウィンドウの [**会議 ID**] を [**リセット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0798a-171">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and in the Action pane under **Conference ID**, click **Reset**.</span></span>
    
4. <span data-ttu-id="0798a-172">**会議 ID をリセットしますか?** ] ウィンドウで、[**はい**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0798a-172">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="0798a-173">会議 ID が自動的に作成され、ユーザーに電子メールを送信することが有効になっているかどうか、新しい会議 ID を使用してユーザーに電子メールを送信します。</span><span class="sxs-lookup"><span data-stu-id="0798a-173">A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled.</span></span> <span data-ttu-id="0798a-174">既定で有効です。</span><span class="sxs-lookup"><span data-stu-id="0798a-174">It's enabled by default.</span></span>
    
    > [!IMPORTANT]
    >  <span data-ttu-id="0798a-175">新しい会議 ID が作成されると、呼び出し元が古い会議 ID を使用できません。</span><span class="sxs-lookup"><span data-stu-id="0798a-175">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="0798a-176">ミーティングの招待新しい会議 ID が、招待状に追加されることを確認するのには、既存のスケジュールを変更するのにはユーザーに通知する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0798a-176">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="0798a-177">ユーザーは、ビジネス会議の移行ツールの Skype を使用して、既存の会議を更新します。</span><span class="sxs-lookup"><span data-stu-id="0798a-177">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="0798a-178">ダウンロード、インストール、および、Skype をビジネス会議の更新ツールを実行する方法を参照してください: [会議のビジネスおよび Lync Skype の更新ツール] ((https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)、 [、ビジネス オンラインの Skype会議の移行ツール (64 ビット)](http://go.microsoft.com/fwlink/?LinkID=626047)、 [Skype オンライン ビジネスをミーティングの移行ツール (32 ビット)](https://www.microsoft.com/en-us/download/details.aspx?id=54079)とします。</span><span class="sxs-lookup"><span data-stu-id="0798a-178">To see how to download, install, and run the Skype for Business Meeting Update Tool, see: [Meeting Update Tool for Skype for Business and Lync]((https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](http://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span></span>
  
<span data-ttu-id="0798a-179">[ユーザーの会議 ID のリセット](reset-a-conference-id-for-a-user.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0798a-179">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).</span></span>
  
## <a name="reset-a-conference-organizers-pin"></a><span data-ttu-id="0798a-180">会議開催者の PIN をリセットする</span><span class="sxs-lookup"><span data-stu-id="0798a-180">Reset a conference organizer's PIN</span></span>

<span data-ttu-id="0798a-181">静的の Id は、組織内のユーザーはランダムな番号を覚えておく必要があるときに使用します。特定の番号を選択したり、覚えやすいものを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="0798a-181">Static IDs are used when people in your organization don't want to remember a random number; they can select a certain number or use one that's easy to remember.</span></span> <span data-ttu-id="0798a-182">動的会議 Id を使用する場合各会議ユーザのスケジュールは割り当てられます会議の一意の id。</span><span class="sxs-lookup"><span data-stu-id="0798a-182">When dynamic conference IDs are used, each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="0798a-183">場合に割り当てる静的な会議 Id、[組織内のオーディオ会議を使用して動的な Id](using-audio-conferencing-dynamic-ids-in-your-organization.md)ではなく動的です。</span><span class="sxs-lookup"><span data-stu-id="0798a-183">If you want to assign dynamic rather than static conference IDs, [Using Audio Conferencing dynamic IDs in your organization](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span></span>
  
<span data-ttu-id="0798a-184">静的な会議 ID が自動的に作成され、ユーザーに割り当てられているがある場合ユーザーは、この 1 つを使用する場合は、特定の数に設定するとユーザーが覚えられないか、会議 ID が失われています。</span><span class="sxs-lookup"><span data-stu-id="0798a-184">Although a static conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="0798a-185">ビジネス管理センターの Skype と Windows PowerShell を使用するには表示、変更、および、会議 ID をリセットするには</span><span class="sxs-lookup"><span data-stu-id="0798a-185">You can use the Skype for Business admin center and Windows PowerShell to view, change, and reset their conference ID.</span></span>
  
1. <span data-ttu-id="0798a-186">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="0798a-186">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="0798a-187">**Office 365 管理センター**を参照して > **ビジネス用の Skype**の左側のナビゲーションでは、[**電話会議**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0798a-187">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="0798a-188">**ユーザー**] をクリックし、ユーザーの PIN をリセットするにします。</span><span class="sxs-lookup"><span data-stu-id="0798a-188">Click **Users**, and then select the user that you want to reset the PIN for.</span></span>
    
4. <span data-ttu-id="0798a-189">[操作] ウィンドウで、**暗証番号 (pin)**、[**リセット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0798a-189">In the Action pane, under **PIN**, click **Reset**.</span></span>
    
<span data-ttu-id="0798a-190">オーディオ会議や、PIN をリセットする場合は有効にしている場合、ユーザーは PIN をメールに表示されます。</span><span class="sxs-lookup"><span data-stu-id="0798a-190">Users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset.</span></span> <span data-ttu-id="0798a-191">自動的に無効にした場合は、電子メールを送信する PIN リセットの電子メールは送信されません、ユーザーに PIN を手動で送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0798a-191">But if you have disabled automatically sending emails, a PIN reset email won't be sent and you will have to manually send the PIN to the user.</span></span> <span data-ttu-id="0798a-192">暗証番号 (pin) のみが表示されます 1 回リセットされた後。</span><span class="sxs-lookup"><span data-stu-id="0798a-192">The PIN will only be shown once after it has been reset.</span></span> <span data-ttu-id="0798a-193">ユーザーのプロパティのリセットの直後にそれが表示されたら、PIN をもう表示されません。代わりに、。 が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0798a-193">After it's displayed just after being reset, the PIN won't be shown anymore on the user properties; instead, \*\*\*\*\* will be shown.</span></span> 
  
<span data-ttu-id="0798a-194">[ユーザーのオーディオ会議の PIN のリセット](reset-the-audio-conferencing-pin-for-a-user.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0798a-194">See [Reset the Audio Conferencing PIN for a user](reset-the-audio-conferencing-pin-for-a-user.md).</span></span>
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="0798a-195">オーディオ会議の情報を使用して電子メールをユーザーに送信します。</span><span class="sxs-lookup"><span data-stu-id="0798a-195">Send an email with Audio Conferencing information to a user</span></span>

1. <span data-ttu-id="0798a-196">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="0798a-196">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="0798a-197">**Office 365 管理センター**を参照して > **ビジネス用の Skype**の左側のナビゲーションでは、[**電話会議**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0798a-197">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="0798a-198">**ユーザー**] をクリックし、ユーザーの PIN をリセットするにします。</span><span class="sxs-lookup"><span data-stu-id="0798a-198">Click **Users**, and then select the user that you want to reset the PIN for.</span></span>
    
4. <span data-ttu-id="0798a-199">操作ウィンドウで、[ **電話会議情報をメールで送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0798a-199">In the Action pane, click **Send conference info via email**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0798a-200">これを行うには、オーディオ会議暗証番号 (pin) はありませんがユーザーに送信します。</span><span class="sxs-lookup"><span data-stu-id="0798a-200">When you do this, the audio conferencing PIN isn't sent to the user.</span></span> 
  
<span data-ttu-id="0798a-201">[オーディオ会議の情報を持つユーザーに電子メールを送信する](send-an-email-to-a-user-with-their-dial-in-information.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0798a-201">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>
  
## <a name="setting-the-default-audio-conferencing-phone-number-for-meeting-organizers"></a><span data-ttu-id="0798a-202">ミーティングの開催者の既定の電話会議の電話番号を設定します。</span><span class="sxs-lookup"><span data-stu-id="0798a-202">Setting the default audio conferencing phone number for meeting organizers</span></span>

 <span data-ttu-id="0798a-203">**オーディオ会議のユーザーを有効にすると、ミーティングの開催者の既定の電話会議の電話番号を設定するのには**</span><span class="sxs-lookup"><span data-stu-id="0798a-203">**To set the default audio conferencing phone number for meeting organizers when you are enabling a user for Audio Conferencing**</span></span>
  
1. <span data-ttu-id="0798a-204">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="0798a-204">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="0798a-205">**Office 365 管理センター**を参照して > **ビジネス用の Skype**です。</span><span class="sxs-lookup"><span data-stu-id="0798a-205">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="0798a-206">左側のナビゲーションでは、**オーディオ会議**に移動 > **のユーザー**です。</span><span class="sxs-lookup"><span data-stu-id="0798a-206">In the left navigation, go to **Audio conferencing** > **Users**.</span></span> <span data-ttu-id="0798a-207">電話会議を有効にするユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="0798a-207">Select the user that you want to enable for Audio Conferencing.</span></span>
    
4. <span data-ttu-id="0798a-208">[操作] ウィンドウの [ユーザーのプロパティ] で、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0798a-208">In the Action pane, in the user's properties, click **Edit**.</span></span>
    
5. <span data-ttu-id="0798a-209">[**プロパティ**] ページで、[**プロバイダー名**] には、オーディオ会議プロバイダーを選択するのに」ドロップ ダウン リストを使用します。</span><span class="sxs-lookup"><span data-stu-id="0798a-209">On the **Properties** page, under **Provider name**, use the drop-down list to select the audio conferencing provider.</span></span>
    
  - <span data-ttu-id="0798a-210">オーディオ会議プロバイダーとして Microsoft を選択した場合は、ボックスの一覧から既定の電話会議の電話番号を選択できます。</span><span class="sxs-lookup"><span data-stu-id="0798a-210">If you select Microsoft as the audio conferencing provider, you can choose the default audio conferencing phone number from the list.</span></span>  
    
  - <span data-ttu-id="0798a-211">オーディオ会議プロバイダーとして、サード パーティ製の ACP を選択した場合、有料の電話を手動で入力する必要が場合は、フリー ダイヤルの電話番号が必要とします。</span><span class="sxs-lookup"><span data-stu-id="0798a-211">If you select a third-party ACP as the audio conferencing provider, you will need to manually enter the Toll and if required, the Toll-free phone number.</span></span> <span data-ttu-id="0798a-212">これらの電話番号は、既定の電話番号になります。</span><span class="sxs-lookup"><span data-stu-id="0798a-212">These phone numbers will be the default phone number.</span></span>
    
    <span data-ttu-id="0798a-213">ユーザーの既定の電話会議の電話番号は、会議出席依頼に会議をスケジュールするときに表示されている番号です。</span><span class="sxs-lookup"><span data-stu-id="0798a-213">The default audio conferencing phone number of a user is the number that is shown on the meeting invite when they schedule a meeting.</span></span>
    
6. <span data-ttu-id="0798a-214">[ **保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0798a-214">Click **Save**.</span></span> 
    
<span data-ttu-id="0798a-215">[携帯電話への招待に含まれている番号の設定](set-the-phone-numbers-included-on-invites.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0798a-215">See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites.md).</span></span>
  
 <span data-ttu-id="0798a-216">**オーディオ会議のユーザーを有効にした後会議の開催者の既定の電話会議の電話番号を設定するのには**</span><span class="sxs-lookup"><span data-stu-id="0798a-216">**To set the default audio conferencing phone number for meeting organizers after you have enabled a user for audio conferencing**</span></span>
  
1. <span data-ttu-id="0798a-217">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="0798a-217">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="0798a-218">**Office 365 管理センター**を参照して > **ビジネス用の Skype**です。</span><span class="sxs-lookup"><span data-stu-id="0798a-218">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="0798a-219">**電話会議**には、**ビジネス管理センターの Skype**、左側のナビゲーションでの > **ユーザー**は、ユーザーを選択し、[アクション] ページで、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0798a-219">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, select the user you want, and in the Action page, click **Edit**.</span></span>
    
4. <span data-ttu-id="0798a-220">[**プロパティ**] ページで、[**プロバイダー名**] には、オーディオ会議プロバイダーを選択するのに」ドロップ ダウン リストを使用します。</span><span class="sxs-lookup"><span data-stu-id="0798a-220">On the **Properties** page, under **Provider name**, use the drop-down list to select the audio conferencing provider.</span></span>
    
  - <span data-ttu-id="0798a-221">ユーザーは、オーディオ会議プロバイダーとして、Microsoft を使用する場合は、ボックスの一覧から既定の電話会議の電話番号を選択できます。</span><span class="sxs-lookup"><span data-stu-id="0798a-221">If the user uses Microsoft as the audio conferencing provider, you can choose the default audio conferencing phone number from the list.</span></span>  
    
  - <span data-ttu-id="0798a-222">ユーザーは、オーディオ会議プロバイダーとしてのサード ・ パーティ製の ACP を使用する場合、有料の電話を手動で入力する必要が必要な場合、フリー ダイヤルの電話番号とします。</span><span class="sxs-lookup"><span data-stu-id="0798a-222">If the user uses a third-party ACP as the audio conferencing provider, you will need to manually enter the Toll and if required, the Toll-free phone number.</span></span>
    
    <span data-ttu-id="0798a-223">ユーザーの既定の電話会議の電話番号は、会議出席依頼に会議をスケジュールするときに表示されている番号です。</span><span class="sxs-lookup"><span data-stu-id="0798a-223">The default audio conferencing phone number of a user is the number that is shown on the meeting invite when they schedule a meeting.</span></span>
    
5. <span data-ttu-id="0798a-224">[ **保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0798a-224">Click **Save**.</span></span> 
    
<span data-ttu-id="0798a-225">[携帯電話への招待に含まれている番号の設定](set-the-phone-numbers-included-on-invites.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0798a-225">See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites.md).</span></span>
  
## <a name="setting-audio-conferencing-bridge-settings"></a><span data-ttu-id="0798a-226">オーディオ会議ブリッジの設定を設定します。</span><span class="sxs-lookup"><span data-stu-id="0798a-226">Setting audio conferencing bridge settings</span></span>

 <span data-ttu-id="0798a-227">**呼び出し元がミーティングに参加するときは、会議の経験を設定します。**</span><span class="sxs-lookup"><span data-stu-id="0798a-227">**Set the meeting experience when callers join a meeting**</span></span>
  
1. <span data-ttu-id="0798a-228">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="0798a-228">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="0798a-229">**Office 365 管理センター**を参照して > **ビジネス用の Skype**です。</span><span class="sxs-lookup"><span data-stu-id="0798a-229">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="0798a-230">**電話会議**には、**ビジネス管理センターの Skype**、左側のナビゲーションでの > **Microsoft ブリッジ設定**します。</span><span class="sxs-lookup"><span data-stu-id="0798a-230">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="0798a-231">[**会議参加の経験**をするには、次の操作を選択します。</span><span class="sxs-lookup"><span data-stu-id="0798a-231">Under **Meeting join experience**, select the following actions:</span></span>
    
  - <span data-ttu-id="0798a-232">**会議エントリを有効にして終了の通知をオンにする**これがデフォルトで選択されます。</span><span class="sxs-lookup"><span data-stu-id="0798a-232">**Enable meeting entry and exit notifications to be turned on** This is selected by default.</span></span> <span data-ttu-id="0798a-233">このチェック ボックスをオフにするとデータを入力したり、会議を離れるときに既定では、会議に参加しているユーザーが通知はありません。</span><span class="sxs-lookup"><span data-stu-id="0798a-233">If you clear this check box, users who have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span></span>
    
    <span data-ttu-id="0798a-234">ユーザーが、Skype を使用して、アプリケーションのビジネスまたはマイクロソフトのチームの会議に参加し、Skype の会議またはマイクロソフトのチーム**のオプション**メニューでの**アナウンス**設定を変更するときに会議ごとの単位で設定できます、会議。</span><span class="sxs-lookup"><span data-stu-id="0798a-234">This can be set on a meeting-by-meeting basis when a user joins a meeting using a Skype for Business or Microsoft Teams app and they modify the **Announce when people enter or leave** setting in the Skype Meeting or Microsoft Teams **Options** menu of the meeting.</span></span>
    
  - <span data-ttu-id="0798a-235">**ミーティングに参加する前に自分の名前を記録する呼び出し元を確認**これがデフォルトで選択されます。</span><span class="sxs-lookup"><span data-stu-id="0798a-235">**Ask callers to record their name before joining the meeting** This is selected by default.</span></span> <span data-ttu-id="0798a-236">このチェック ボックスをオフにすると会議に参加する前に自分の名前を記録するための呼び出し元を求められますされません。</span><span class="sxs-lookup"><span data-stu-id="0798a-236">If you clear this check box, callers won't be asked to record their name before they join a meeting.</span></span>
    
5. <span data-ttu-id="0798a-237">変更を行ったら、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0798a-237">After you make your changes, click **Save**.</span></span>
    
<span data-ttu-id="0798a-238">[オーディオ会議ブリッジの設定を変更する](change-the-settings-for-an-audio-conferencing-bridge.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0798a-238">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>
  
 <span data-ttu-id="0798a-239">**会議の暗証番号 (pin) の長さを設定します。**</span><span class="sxs-lookup"><span data-stu-id="0798a-239">**Set the PIN length for meetings**</span></span>
  
1. <span data-ttu-id="0798a-240">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="0798a-240">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="0798a-241">**Office 365 管理センター**を参照して > **ビジネス用の Skype**です。</span><span class="sxs-lookup"><span data-stu-id="0798a-241">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="0798a-242">**電話会議**には、**ビジネス管理センターの Skype**、左側のナビゲーションでの > **Microsoft ブリッジ設定**します。</span><span class="sxs-lookup"><span data-stu-id="0798a-242">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="0798a-243">[**セキュリティ**] の**暗証番号 (pin) の長さ**] ボックスの一覧で、[暗証番号 (pin) に使用桁数を入力し、し、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0798a-243">Under **Security**, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>
    
    <span data-ttu-id="0798a-244">暗証番号 (pin) は、4 桁から 12 桁の間である必要があります。</span><span class="sxs-lookup"><span data-stu-id="0798a-244">The PIN must be between 4 and 12 digits.</span></span> <span data-ttu-id="0798a-245">デフォルトは 5 です。</span><span class="sxs-lookup"><span data-stu-id="0798a-245">The default is 5.</span></span>
    
<span data-ttu-id="0798a-246">[オーディオ会議ブリッジの設定を変更する](change-the-settings-for-an-audio-conferencing-bridge.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0798a-246">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>
  
 <span data-ttu-id="0798a-247">**有効にするか、オーディオのユーザーに送信される電子メールを無効にします。**</span><span class="sxs-lookup"><span data-stu-id="0798a-247">**Enable or disable email from being sent to audio users**</span></span>
  
1. <span data-ttu-id="0798a-248">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="0798a-248">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="0798a-249">**Office 365 管理センター**を参照して > **ビジネス用の Skype**の左側のナビゲーションでは、[**電話会議**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0798a-249">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="0798a-250">**Microsoft ブリッジの設定**] ページをオンまたはオフの**オーディオ会議の設定を変更する場合、ユーザーに e メールを自動的に送信**する。</span><span class="sxs-lookup"><span data-stu-id="0798a-250">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>
    
4. <span data-ttu-id="0798a-251">[ **保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0798a-251">Click **Save**.</span></span>
    
    <span data-ttu-id="0798a-252">ユーザーのオーディオ会議のプロパティに移動し、**電子メールを使用して会議情報を送信**] をクリックしてユーザーに、電話会議の設定を使用する電子メールを送信することも。</span><span class="sxs-lookup"><span data-stu-id="0798a-252">You can also send email to the user with the audio conferencing settings, by going to the user's audio conferencing properties and clicking **Send conference info via email**.</span></span>
    
    <span data-ttu-id="0798a-253">電子メールを送信する場合はこれを行うには、会議 ID と電話会議の番号を含むのみですが、暗証番号 (pin) を含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="0798a-253">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span></span>
    
    <span data-ttu-id="0798a-254">[オーディオ会議の情報を持つユーザーに電子メールを送信する](send-an-email-to-a-user-with-their-dial-in-information.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0798a-254">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>
    
## <a name="see-and-set-the-primary-and-secondary-languages-on-an-audio-conferencing-bridge"></a><span data-ttu-id="0798a-255">参照してくださいし、オーディオ会議ブリッジにプライマリとセカンダリの言語を設定します。</span><span class="sxs-lookup"><span data-stu-id="0798a-255">See and set the primary and secondary languages on an audio conferencing bridge</span></span>

1. <span data-ttu-id="0798a-256">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="0798a-256">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="0798a-257">**Office 365 管理センター**を参照して > **ビジネス用の Skype**です。</span><span class="sxs-lookup"><span data-stu-id="0798a-257">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="0798a-258">**Skype**ビジネス管理センターは、左側のナビゲーションでは、では、**オーディオ会議**に移動し、 **Microsoft ブリッジ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0798a-258">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and then click **Microsoft bridge**.</span></span>
    
4. <span data-ttu-id="0798a-259">リストから電話番号を選択して、[操作] ウィンドウで、[**言語の設定**] をクリックし、**言語の設定**] ページで、[使用] をクリックして、サポートされている言語の完全な一覧を表示するのには、**主言語**] ボックスの一覧。</span><span class="sxs-lookup"><span data-stu-id="0798a-259">Select a phone number from the list, click **Set languages** in the Action pane, and then on the **Set languages** page, click the use the **Primary language** list to view the complete list of supported languages.</span></span>
    
    <span data-ttu-id="0798a-260">オーディオ会議プロバイダーとして Microsoft を選択した場合にサポートされているプライマリとセカンダリの言語を設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="0798a-260">You can also set the primary and secondary languages that are supported when you select Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="0798a-261">リストで選択した順序は、呼び出し元の言語が表示されます同じ順序です。</span><span class="sxs-lookup"><span data-stu-id="0798a-261">The order that you select in the lists is the same order in which languages will be presented to callers.</span></span>
    
<span data-ttu-id="0798a-262">[オーディオ会議の自動応答の言語設定](set-auto-attendant-languages-for-audio-conferencing.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0798a-262">See [Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing.md).</span></span>
  
## <a name="see-audio-conferencing-dial-in-numbers"></a><span data-ttu-id="0798a-263">電話会議にダイヤルイン番号を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0798a-263">See audio conferencing dial-in numbers</span></span>

1. <span data-ttu-id="0798a-264">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="0798a-264">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="0798a-265">**Office 365 管理センター**を参照して > **ビジネス用の Skype**です。</span><span class="sxs-lookup"><span data-stu-id="0798a-265">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="0798a-266">**電話会議**には、**ビジネス管理センターの Skype**、左側のナビゲーションでの > **マイクロソフトのブリッジ**です。</span><span class="sxs-lookup"><span data-stu-id="0798a-266">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge**.</span></span> <span data-ttu-id="0798a-267">ここでは次のようなことができます。</span><span class="sxs-lookup"><span data-stu-id="0798a-267">Here you can:</span></span>
    
  - <span data-ttu-id="0798a-268">電話会議に使用する Office 365 によって設定されている電話番号を表示します。</span><span class="sxs-lookup"><span data-stu-id="0798a-268">View the phone numbers that are set by Office 365 to be used for Audio Conferencing.</span></span> 
    
  - <span data-ttu-id="0798a-269">場所、および音声会議自動アテンダントによって使用されるプライマリとセカンダリ言語を表示します。</span><span class="sxs-lookup"><span data-stu-id="0798a-269">View the location, and the primary and secondary languages, that will be used by the Audio Conferencing auto attendant.</span></span>
    
  - <span data-ttu-id="0798a-270">電話会議が有効になっているときに、ユーザーに指定された既定の電話番号を選択します。</span><span class="sxs-lookup"><span data-stu-id="0798a-270">Select the default phone number that will be given to users when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="0798a-271">オーディオ会議ブリッジの既定の電話番号が変更された場合は、既存のユーザーの既定の電話番号は変更されません。</span><span class="sxs-lookup"><span data-stu-id="0798a-271">However, if the default phone number of the audio conferencing bridge changes, the default phone number for existing users won't change.</span></span>
    
<span data-ttu-id="0798a-272">**オーディオ会議**に移動することができます > **ユーザー**およびユーザーのプロパティを既定値を変更するのには、組織で使用可能な番号の一覧から新しい番号を選択することによってユーザーの番号を選択します。</span><span class="sxs-lookup"><span data-stu-id="0798a-272">You can go to **Audio conferencing** > **Users** and select the user's properties to change the default number for a user by choosing a new number from the list of numbers that are available in your organization.</span></span>
  
<span data-ttu-id="0798a-273">[オーディオ会議の番号の一覧を参照してください](see-a-list-of-audio-conferencing-numbers.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="0798a-273">See [See a list of Audio Conferencing numbers](see-a-list-of-audio-conferencing-numbers.md).</span></span>
  
## <a name="see-a-list-of-users-that-are-enabled"></a><span data-ttu-id="0798a-274">有効になっているユーザーの一覧を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0798a-274">See a list of users that are enabled</span></span>

1. <span data-ttu-id="0798a-275">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="0798a-275">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="0798a-276">**Office 365 管理センター**を参照して > **ビジネス用の Skype**です。</span><span class="sxs-lookup"><span data-stu-id="0798a-276">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="0798a-277">**Skype**ビジネス管理センターは、左側のナビゲーションでは、[**電話会議**に移動 > および**ユーザー**です。</span><span class="sxs-lookup"><span data-stu-id="0798a-277">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**> and then **Users**.</span></span>
    
<span data-ttu-id="0798a-278">[電話会議を有効になっているユーザーの一覧を参照してください](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="0798a-278">See [See a list of users that are enabled for Audio Conferencing](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).</span></span>
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="0798a-279">Windows PowerShell で管理する方法</span><span class="sxs-lookup"><span data-stu-id="0798a-279">Want to know how to manage with Windows PowerShell?</span></span>

<span data-ttu-id="0798a-280">Windows PowerShell を使用して組織レベルで管理することができますいくつかの設定があります。</span><span class="sxs-lookup"><span data-stu-id="0798a-280">There are several settings that you can manage at the organization level using Windows PowerShell.</span></span> <span data-ttu-id="0798a-281">これにより、簡単にすべてのユーザー設定を適用します。</span><span class="sxs-lookup"><span data-stu-id="0798a-281">This makes it easy to apply settings to all of your users.</span></span> 
    
<span data-ttu-id="0798a-282">各コマンドレットのヘルプを表示する、 [Skype](https://go.microsoft.com/fwlink/?LinkId=627324)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0798a-282">To get more help on each cmdlet, see [Skype for Business Online cmdlets](https://go.microsoft.com/fwlink/?LinkId=627324).</span></span>

<span data-ttu-id="0798a-283">組織レベルの設定を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="0798a-283">Here are the organization-level settings:</span></span> 
> 
- <span data-ttu-id="0798a-284">**開始/終了の通知を設定します。**_$True_は、既定では。</span><span class="sxs-lookup"><span data-stu-id="0798a-284">**Setting entry/exit notifications** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableEntryExitNotifications $true|$false 
  ```

- <span data-ttu-id="0798a-285">**名の記録を設定します。**_$True_は、既定では。</span><span class="sxs-lookup"><span data-stu-id="0798a-285">**Setting name recording** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableNameRecording $true|false
  ```

- <span data-ttu-id="0798a-286">**暗証番号 (pin) の長さを設定**デフォルトは 5 です。</span><span class="sxs-lookup"><span data-stu-id="0798a-286">**Setting the PIN length** The default is 5.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -PinLength 7
  ```

- <span data-ttu-id="0798a-287">**のみダイヤルイン会議電話からの設定**既定値の_$false_です。</span><span class="sxs-lookup"><span data-stu-id="0798a-287">**Setting only dial-in meetings from a phone** The default _$false_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true|$false
  ```

- <span data-ttu-id="0798a-288">**ユーザーに電子メールを送信するかどうかを設定**_$True_は、既定では。</span><span class="sxs-lookup"><span data-stu-id="0798a-288">**Setting whether to send email to users** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

- <span data-ttu-id="0798a-289">**別のアカウントから電子メールを送信するかどうかを設定**既定では_$false_です。</span><span class="sxs-lookup"><span data-stu-id="0798a-289">**Setting whether to send email from a different account** The default is  _$false_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromOverride $true|$false
  ```

- <span data-ttu-id="0798a-290">**ユーザーに送信される電子メールの差出人アドレスの設定**_$Null_を既定値には。</span><span class="sxs-lookup"><span data-stu-id="0798a-290">**Setting the From address on email that is sent to users** The default is _$null_.</span></span> 
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromAddress
  ```

- <span data-ttu-id="0798a-291">**ユーザーに送信される電子メールの表示名を設定します。**_$Null_を既定値には。</span><span class="sxs-lookup"><span data-stu-id="0798a-291">**Setting the display name for the email that is sent to users** The default is  _$null_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromDisplayName
  ```

 ## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="0798a-292">Windows PowerShell についてより詳しく知りたいです。</span><span class="sxs-lookup"><span data-stu-id="0798a-292">Want to know more about Windows PowerShell</span></span>   
- <span data-ttu-id="0798a-293">Windows PowerShell は、ユーザーを管理するユーザーを許可または許可されません。</span><span class="sxs-lookup"><span data-stu-id="0798a-293">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="0798a-294">Windows PowerShell を実行する複数のタスクがある場合、日常的な作業を簡素化する管理の単一ポイントを使用して Office 365 を管理できます。</span><span class="sxs-lookup"><span data-stu-id="0798a-294">With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="0798a-295">Windows PowerShell を使い始めるには、以下のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0798a-295">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="0798a-296">Office 365 の PowerShell を使用する必要がある理由</span><span class="sxs-lookup"><span data-stu-id="0798a-296">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="0798a-297">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="0798a-297">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="0798a-298">Windows PowerShell には、実行しようとする設定の変更多くのユーザーを一度に 1 つなど、Office 365 管理センターを使用するだけでスピード、シンプルさと生産性に多くの利点があります。</span><span class="sxs-lookup"><span data-stu-id="0798a-298">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="0798a-299">次のトピックで、これらの利点について学習します。</span><span class="sxs-lookup"><span data-stu-id="0798a-299">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="0798a-300">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="0798a-300">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="0798a-301">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="0798a-301">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="0798a-302">Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行</span><span class="sxs-lookup"><span data-stu-id="0798a-302">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    <span data-ttu-id="0798a-p126">Skype for Business Online 用 Windows PowerShell モジュールでは、リモート Windows PowerShell セッションを作成して Skype for Business Online に接続できます。このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「[Skype for Business Online 用 Windows PowerShell モジュール](https://go.microsoft.com/fwlink/?LinkId=294688)」からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="0798a-p126">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="0798a-305">関連トピック</span><span class="sxs-lookup"><span data-stu-id="0798a-305">Related topics</span></span>

[<span data-ttu-id="0798a-306">ユーザーの電話会議の設定を管理します。</span><span class="sxs-lookup"><span data-stu-id="0798a-306">Manage the Audio Conferencing settings for a user</span></span>](manage-the-audio-conferencing-settings-for-a-user.md)

[<span data-ttu-id="0798a-307">Skype for Business および Microsoft Teams の電話会議のセットアップ</span><span class="sxs-lookup"><span data-stu-id="0798a-307">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](set-up-audio-conferencing.md)

