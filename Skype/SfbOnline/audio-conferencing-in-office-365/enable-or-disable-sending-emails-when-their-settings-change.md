---
title: Enable or disable sending emails when their settings change
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'Learn how to enable or disable Skype from sending emails to users when settings such as pin changes or the default conferencing number changes. '
ms.openlocfilehash: 4138ed08ef05cc1947131dab22d5470e52eda6c5
ms.sourcegitcommit: dea27df69d948b7b9cc017b7023c4013cee8e4d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2018
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change"></a><span data-ttu-id="ed19c-103">Enable or disable sending emails when Audio Conferencing settings change</span><span class="sxs-lookup"><span data-stu-id="ed19c-103">Enable or disable sending emails when Audio Conferencing settings change</span></span>

<span data-ttu-id="ed19c-104">Users are automatically notified by email when they are enabled for Audio Conferencing.</span><span class="sxs-lookup"><span data-stu-id="ed19c-104">Users are automatically notified by email when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="ed19c-105">There may be times, however, when you want to reduce the number of emails that are sent to Skype for Business and Microsoft Teams user.</span><span class="sxs-lookup"><span data-stu-id="ed19c-105">There may be times, however, when you want to reduce the number of emails that are sent to Skype for Business and Microsoft Teams user.</span></span> <span data-ttu-id="ed19c-106">In such cases, you can disable sending email.</span><span class="sxs-lookup"><span data-stu-id="ed19c-106">In such cases, you can disable sending email.</span></span>
  
<span data-ttu-id="ed19c-107">If you disable sending emails, Audio Conferencing emails won't be sent to your users, including emails for when users are enabled or disabled for audio conferencing, when their PIN is reset, and when the conference ID and the default conferencing phone number changes.</span><span class="sxs-lookup"><span data-stu-id="ed19c-107">If you disable sending emails, Audio Conferencing emails won't be sent to your users, including emails for when users are enabled or disabled for audio conferencing, when their PIN is reset, and when the conference ID and the default conferencing phone number changes.</span></span>
  
<span data-ttu-id="ed19c-108">Here is an example of the email that is sent to users when they are enabled for Audio Conferencing:</span><span class="sxs-lookup"><span data-stu-id="ed19c-108">Here is an example of the email that is sent to users when they are enabled for Audio Conferencing:</span></span>
  
![Audio Conferencing email](../images/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a><span data-ttu-id="ed19c-110">When are emails being sent to your users?</span><span class="sxs-lookup"><span data-stu-id="ed19c-110">When are emails being sent to your users?</span></span>

- <span data-ttu-id="ed19c-111">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span><span class="sxs-lookup"><span data-stu-id="ed19c-111">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="ed19c-112">When an **Audio Conferencing** license is assigned to them.</span><span class="sxs-lookup"><span data-stu-id="ed19c-112">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="ed19c-113">When you manually reset the user's audio conferencing PIN.</span><span class="sxs-lookup"><span data-stu-id="ed19c-113">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="ed19c-114">ユーザーの会議 ID を手動でリセットした場合。</span><span class="sxs-lookup"><span data-stu-id="ed19c-114">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="ed19c-115">When the **Audio Conferencing** license is removed from them.</span><span class="sxs-lookup"><span data-stu-id="ed19c-115">When the **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="ed19c-116">When the audio conferencing provider of a user is changed from Microsoft to another provider or **None**.</span><span class="sxs-lookup"><span data-stu-id="ed19c-116">When the audio conferencing provider of a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="ed19c-117">When the audio conferencing provider of a user is changed to Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ed19c-117">When the audio conferencing provider of a user is changed to Microsoft.</span></span>
    
## <a name="enable-or-disable-email-from-being-sent-to-users"></a><span data-ttu-id="ed19c-118">Enable or disable email from being sent to users</span><span class="sxs-lookup"><span data-stu-id="ed19c-118">Enable or disable email from being sent to users</span></span>

<span data-ttu-id="ed19c-119">You can use Microsoft Teams, the Skype for Business admin center, or Windows PowerShell to enable or disable email sent to users.</span><span class="sxs-lookup"><span data-stu-id="ed19c-119">You can use Microsoft Teams, the Skype for Business admin center, or Windows PowerShell to enable or disable email sent to users.</span></span>

<span data-ttu-id="ed19c-120">**Using the Microsoft Teams and Skype for Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="ed19c-120">**Using the Microsoft Teams and Skype for Business Admin Center**</span></span>
1. <span data-ttu-id="ed19c-121">In the left navigation, go to **Meetings** > **Conference Bridges**.</span><span class="sxs-lookup"><span data-stu-id="ed19c-121">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="ed19c-122">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span><span class="sxs-lookup"><span data-stu-id="ed19c-122">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span> 

3. <span data-ttu-id="ed19c-123">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span><span class="sxs-lookup"><span data-stu-id="ed19c-123">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="ed19c-124">[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ed19c-124">Click **Apply**.</span></span>
  
<span data-ttu-id="ed19c-125">****職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="ed19c-125">**Using the Skype for Business admin center**</span></span>
    
1. <span data-ttu-id="ed19c-126">In the **Skype for Business admin center**, in the left navigation, click **Audio conferencing**.</span><span class="sxs-lookup"><span data-stu-id="ed19c-126">In the **Skype for Business admin center**, in the left navigation, click **Audio conferencing**.</span></span>
    
2. <span data-ttu-id="ed19c-127">電話会議の設定を使用してユーザーにメールを送信することもできます。これには、ユーザーの電話会議プロパティに移動して、[ **電話会議情報をメールで送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ed19c-127">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>
    
3. <span data-ttu-id="ed19c-128">電話会議の設定を使用してユーザーにメールを送信することもできます。</span><span class="sxs-lookup"><span data-stu-id="ed19c-128">Click **Save**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="ed19c-129">You can also send email to a user with the audio conferencing settings by going to **Audio conferencing** > **Users**, selecting the user, and clicking **Send conference info via email**.</span><span class="sxs-lookup"><span data-stu-id="ed19c-129">You can also send email to a user with the audio conferencing settings by going to **Audio conferencing** > **Users**, selecting the user, and clicking **Send conference info via email**.</span></span>  <span data-ttu-id="ed19c-130">If you do this, an email will be sent that only includes conference ID and conference phone number, but not the PIN.</span><span class="sxs-lookup"><span data-stu-id="ed19c-130">If you do this, an email will be sent that only includes conference ID and conference phone number, but not the PIN.</span></span>  <span data-ttu-id="ed19c-131">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md) for more information.</span><span class="sxs-lookup"><span data-stu-id="ed19c-131">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md) for more information.</span></span>
  
<span data-ttu-id="ed19c-132">The conference ID and default dial-in conferencing phone number is included on the meeting invite but not the PIN.</span><span class="sxs-lookup"><span data-stu-id="ed19c-132">**Using Windows PowerShell**</span></span>
  
- <span data-ttu-id="ed19c-133">Run the following to disable sending emails:</span><span class="sxs-lookup"><span data-stu-id="ed19c-133">Run the following to disable sending emails:</span></span> 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

    <span data-ttu-id="ed19c-134">For help with this cmdlet, see [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757).</span><span class="sxs-lookup"><span data-stu-id="ed19c-134">For help with this cmdlet, see [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757).</span></span>
    
## <a name="what-else-should-you-know"></a><span data-ttu-id="ed19c-135">その他の情報</span><span class="sxs-lookup"><span data-stu-id="ed19c-135">What else should you know?</span></span>

- <span data-ttu-id="ed19c-136">When automatic emails are disabled, you can still manually trigger sending an email with the conference ID and phone number using the Skype for Business admin center.</span><span class="sxs-lookup"><span data-stu-id="ed19c-136">When automatic emails are disabled, you can still manually trigger sending an email with the conference ID and phone number using the Skype for Business admin center.</span></span> <span data-ttu-id="ed19c-137">However, if you do this, the PIN won't be included.</span><span class="sxs-lookup"><span data-stu-id="ed19c-137">However, if you do this, the PIN won't be included.</span></span> <span data-ttu-id="ed19c-138">If you want to reset the audio conferencing PIN and sending emails is disabled, you will need to send it to the user in another way.</span><span class="sxs-lookup"><span data-stu-id="ed19c-138">If you want to reset the audio conferencing PIN and sending emails is disabled, you will need to send it to the user in another way.</span></span>
    
- <span data-ttu-id="ed19c-139">Sending email to your users can be disabled using the Skype for Business admin center or the Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ed19c-139">Sending email to your users can be disabled using the Skype for Business admin center or the Windows PowerShell.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="ed19c-140">Go to the Office 365 admin centerSkype for Business.</span><span class="sxs-lookup"><span data-stu-id="ed19c-140">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="ed19c-141">You can use these cmdlets to save time or automate this.</span><span class="sxs-lookup"><span data-stu-id="ed19c-141">You can use these cmdlets to save time or automate this.</span></span>
    
  - [<span data-ttu-id="ed19c-142">Get-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="ed19c-142">Get-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715760)
    
  - [<span data-ttu-id="ed19c-143">Remove-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="ed19c-143">Remove-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715759)
    
  - [<span data-ttu-id="ed19c-144">Get-CsOnlineDialinConferencingTenantConfiguration</span><span class="sxs-lookup"><span data-stu-id="ed19c-144">Get-CsOnlineDialinConferencingTenantConfiguration</span></span>](https://go.microsoft.com/fwlink/?LinkId=715758)
    
  - [<span data-ttu-id="ed19c-145">Get-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="ed19c-145">Get-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715760)
    
-  <span data-ttu-id="ed19c-p104">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span><span class="sxs-lookup"><span data-stu-id="ed19c-p104">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="ed19c-149">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="ed19c-149">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="ed19c-150">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="ed19c-150">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="ed19c-p105">多くのユーザーの設定を同時に変更するときなどは、Office 365 管理センターのみを使用するよりも、Windows PowerShell の方に、速度、わかりやすさ、生産性の点で多くのメリットがあります。 次のトピックで、これらの利点を説明します。</span><span class="sxs-lookup"><span data-stu-id="ed19c-p105">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="ed19c-153">Windows PowerShell と Lync Online の概要</span><span class="sxs-lookup"><span data-stu-id="ed19c-153">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="ed19c-154">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="ed19c-154">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="ed19c-155">Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行</span><span class="sxs-lookup"><span data-stu-id="ed19c-155">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="ed19c-p106">[Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="ed19c-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="ed19c-158">このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「Skype for Business Online 用 Windows PowerShell モジュール」からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="ed19c-158">Related topics</span></span>

[<span data-ttu-id="ed19c-159">Emails sent to users when their Audio Conferencing settings change</span><span class="sxs-lookup"><span data-stu-id="ed19c-159">Emails sent to users when their Audio Conferencing settings change</span></span>](emails-sent-to-users-when-their-settings-change.md)

[<span data-ttu-id="ed19c-160">ユーザーに電話会議情報が含まれたメールを送信する</span><span class="sxs-lookup"><span data-stu-id="ed19c-160">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information.md)


