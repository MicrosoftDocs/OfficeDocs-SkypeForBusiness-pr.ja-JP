---
title: 有効にするかの設定を変更すると、送信メールを無効にします。
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
description: '有効にするか、暗証番号 (pin) の変更など、既定の会議の設定番号を変更するときに、ユーザーに e メールを送信することから、Skype を無効にする方法を説明します。 '
ms.openlocfilehash: e2a57a63cbc7b633e0240b7ec94f2d548a2dbe31
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/03/2018
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change"></a><span data-ttu-id="e2946-103">有効にするか、オーディオ会議の設定を変更すると、送信メールを無効にします。</span><span class="sxs-lookup"><span data-stu-id="e2946-103">Enable or disable sending emails when Audio Conferencing settings change</span></span>

<span data-ttu-id="e2946-104">ユーザーは、電話会議が有効になっているときに自動的に電子メールで通知されます。</span><span class="sxs-lookup"><span data-stu-id="e2946-104">Users are automatically notified by email when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="e2946-105">ただし、Skype のビジネスおよびマイクロソフトのチームのユーザーに送信される電子メールの数を削減したい場合があります。</span><span class="sxs-lookup"><span data-stu-id="e2946-105">There may be times, however, when you want to reduce the number of emails that are sent to Skype for Business and Microsoft Teams user.</span></span> <span data-ttu-id="e2946-106">このような場合は、電子メールの送信を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="e2946-106">In such cases, you can disable sending email.</span></span>
  
<span data-ttu-id="e2946-107">オーディオ会議の電子メールをユーザーが有効になっているか、オーディオ会議は、会議 ID と既定の会議の電話番号の変更と、PIN をリセットすると無効にすると、電子メールを含む、ユーザーに送信されません送信メールを無効にした場合.</span><span class="sxs-lookup"><span data-stu-id="e2946-107">If you disable sending emails, Audio Conferencing emails won't be sent to your users, including emails for when users are enabled or disabled for audio conferencing, when their PIN is reset, and when the conference ID and the default conferencing phone number changes.</span></span>
  
<span data-ttu-id="e2946-108">電話会議が有効になっているときに、ユーザーに送信されるメールの例を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="e2946-108">Here is an example of the email that is sent to users when they are enabled for Audio Conferencing:</span></span>
  
![オーディオ会議の電子メール](../images/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a><span data-ttu-id="e2946-110">メール ユーザーに送信するのでしょうか。</span><span class="sxs-lookup"><span data-stu-id="e2946-110">When are emails being sent to your users?</span></span>

- <span data-ttu-id="e2946-111">送信される、組織内のユーザーを有効にした後には、オーディオ会議のいくつかの電子メールがあります。</span><span class="sxs-lookup"><span data-stu-id="e2946-111">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="e2946-112">ときに、**オーディオ会議**のライセンスが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="e2946-112">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="e2946-113">リセットすると手動で電話会議のユーザーの暗証番号 (pin) です。</span><span class="sxs-lookup"><span data-stu-id="e2946-113">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="e2946-114">ユーザーの会議 ID を手動でリセットした場合。</span><span class="sxs-lookup"><span data-stu-id="e2946-114">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="e2946-115">**電話会議**のライセンスは、それらから削除されます。</span><span class="sxs-lookup"><span data-stu-id="e2946-115">When the **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="e2946-116">オーディオ会議プロバイダーのユーザーの変更されたとき Microsoft から別のプロバイダーまたは**[なし]**にします。</span><span class="sxs-lookup"><span data-stu-id="e2946-116">When the audio conferencing provider of a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="e2946-117">マイクロソフトにユーザーの電話会議プロバイダーが変更されたとき。</span><span class="sxs-lookup"><span data-stu-id="e2946-117">When the audio conferencing provider of a user is changed to Microsoft.</span></span>
    
## <a name="enable-or-disable-email-from-being-sent-to-users"></a><span data-ttu-id="e2946-118">有効にするか、ユーザーに送信される電子メールを無効にします。</span><span class="sxs-lookup"><span data-stu-id="e2946-118">Enable or disable email from being sent to users</span></span>

<span data-ttu-id="e2946-119">You can use the Skype for Business admin center or Windows PowerShell to enable or disable email from being sent to users.</span><span class="sxs-lookup"><span data-stu-id="e2946-119">You can use the Skype for Business admin center or Windows PowerShell to enable or disable email sent to users.</span></span>
  
 <span data-ttu-id="e2946-120">****職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="e2946-120">**Using the Skype for Business admin center**</span></span>
  
1. <span data-ttu-id="e2946-121">Sign in to Office 365 with your work or school account.</span><span class="sxs-lookup"><span data-stu-id="e2946-121">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="e2946-122">**Office 365 管理センター**を参照して > **ビジネス用の Skype**では、左側のナビゲーションで [**電話会議**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e2946-122">Go to the **Office 365 admin center** > **Skype for Business**, and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="e2946-123">電話会議の設定を使用してユーザーにメールを送信することもできます。これには、ユーザーの電話会議プロパティに移動して、[ **電話会議情報をメールで送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e2946-123">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>
    
4. <span data-ttu-id="e2946-124">電話会議の設定を使用してユーザーにメールを送信することもできます。</span><span class="sxs-lookup"><span data-stu-id="e2946-124">Click **Save**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="e2946-125">送信することも電子メール ユーザーに電話会議の設定を使用して**オーディオ会議**に > の**ユーザー**ユーザーを選択し、**電子メールを使用して会議情報を送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e2946-125">You can also send email to a user with the audio conferencing settings by going to **Audio conferencing** > **Users**, selecting the user, and clicking **Send conference info via email**.</span></span>  <span data-ttu-id="e2946-126">これを行うには、会議 ID と電話会議の番号がない、暗証番号 (pin) のみを含む電子メールが送信されます。</span><span class="sxs-lookup"><span data-stu-id="e2946-126">If you do this, an email will be sent that only includes conference ID and conference phone number, but not the PIN.</span></span>  <span data-ttu-id="e2946-127">詳細については[、オーディオ会議の情報を持つユーザーに電子メールを送信する](send-an-email-to-a-user-with-their-dial-in-information.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2946-127">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md) for more information.</span></span>
  
 <span data-ttu-id="e2946-128">The conference ID and default dial-in conferencing phone number is included on the meeting invite but not the PIN.</span><span class="sxs-lookup"><span data-stu-id="e2946-128">**Using Windows PowerShell**</span></span>
  
- <span data-ttu-id="e2946-129">送信メールを無効にするのには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="e2946-129">Run the following to disable sending emails:</span></span> 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

    <span data-ttu-id="e2946-130">このコマンドレットのヘルプを表示するには、[一連の CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2946-130">For help with this cmdlet, see [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757).</span></span>
    
## <a name="what-else-should-you-know"></a><span data-ttu-id="e2946-131">その他の情報</span><span class="sxs-lookup"><span data-stu-id="e2946-131">What else should you know?</span></span>

- <span data-ttu-id="e2946-132">自動メールを無効にすると、ビジネス管理センターは、Skype を使用して会議の ID と電話番号と電子メールを送信するを手動でトリガーできます。</span><span class="sxs-lookup"><span data-stu-id="e2946-132">When automatic emails are disabled, you can still manually trigger sending an email with the conference ID and phone number using the Skype for Business admin center.</span></span> <span data-ttu-id="e2946-133">ただし、これを行うには、PIN に含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="e2946-133">However, if you do this, the PIN won't be included.</span></span> <span data-ttu-id="e2946-134">オーディオ会議の暗証番号 (pin) をリセットするし、電子メールの送信が無効になっている、別の方法でユーザーに送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2946-134">If you want to reset the audio conferencing PIN and sending emails is disabled, you will need to send it to the user in another way.</span></span>
    
- <span data-ttu-id="e2946-135">既定では、電子メールの送信者は、Office 365 からなりますが、電子メール アドレスを変更し、Windows PowerShell を使用して名前を表示して[セット CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757)コマンドレットを使用しても。</span><span class="sxs-lookup"><span data-stu-id="e2946-135">By default, the sender of the emails will be from Office 365, but you can change the email address and display name using Windows PowerShell and also use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757) cmdlet.</span></span>
    
    > [!NOTE]
    >  <span data-ttu-id="e2946-136">電子メール アドレス情報を変更する場合は、環境内の受信電子メール ポリシーが、アドレスから指定されたユーザーから送信される電子メールを許可するかどうかを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2946-136">If you want to change the email address information, you need to make sure that the inbound email policies of your environment allow emails that come from the custom specified from address.</span></span>
  
  - <span data-ttu-id="e2946-137">_SendEmailFromAddress_ パラメーターにメール アドレスを入力する</span><span class="sxs-lookup"><span data-stu-id="e2946-137">Enter the email address in the  _SendEmailFromAddress_ parameter.</span></span>
    
  - <span data-ttu-id="e2946-138">_SendEmailFromDisplayName_ パラメーターにメールの表示名を入力する</span><span class="sxs-lookup"><span data-stu-id="e2946-138">Enter the email display name in the  _SendEmailFromDisplayName_ parameter.</span></span>
    
  - <span data-ttu-id="e2946-139">_SendEmailOverride_パラメーターを_True_に設定します。</span><span class="sxs-lookup"><span data-stu-id="e2946-139">Set the  _SendEmailOverride_ parameter to _True_.</span></span>
    
  -  `Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"`
    
- <span data-ttu-id="e2946-140">ユーザーに電子メールを送信を無効にできます、Skype のビジネス管理センターまたは Windows PowerShell の使用します。</span><span class="sxs-lookup"><span data-stu-id="e2946-140">Sending email to your users can be disabled using the Skype for Business admin center or the Windows PowerShell.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="e2946-141">Go to the Office 365 admin centerSkype for Business.</span><span class="sxs-lookup"><span data-stu-id="e2946-141">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="e2946-142">これらのコマンドレットを使用するには時間を保存するか、これを自動化します。</span><span class="sxs-lookup"><span data-stu-id="e2946-142">You can use these cmdlets to save time or automate this.</span></span>
    
  - [<span data-ttu-id="e2946-143">Get CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="e2946-143">Get-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715760)
    
  - [<span data-ttu-id="e2946-144">削除 CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="e2946-144">Remove-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715759)
    
  - [<span data-ttu-id="e2946-145">Get CsOnlineDialinConferencingTenantConfiguration</span><span class="sxs-lookup"><span data-stu-id="e2946-145">Get-CsOnlineDialinConferencingTenantConfiguration</span></span>](https://go.microsoft.com/fwlink/?LinkId=715758)
    
  - [<span data-ttu-id="e2946-146">Get CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="e2946-146">Get-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715760)
    
-  <span data-ttu-id="e2946-p104">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span><span class="sxs-lookup"><span data-stu-id="e2946-p104">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="e2946-150">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="e2946-150">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="e2946-151">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="e2946-151">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="e2946-p105">多くのユーザーの設定を同時に変更するときなどは、Office 365 管理センターのみを使用するよりも、Windows PowerShell の方に、速度、わかりやすさ、生産性の点で多くのメリットがあります。 次のトピックで、これらの利点を説明します。</span><span class="sxs-lookup"><span data-stu-id="e2946-p105">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="e2946-154">Windows PowerShell と Lync Online の概要</span><span class="sxs-lookup"><span data-stu-id="e2946-154">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="e2946-155">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="e2946-155">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="e2946-156">Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行</span><span class="sxs-lookup"><span data-stu-id="e2946-156">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="e2946-p106">[Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="e2946-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="e2946-159">このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「Skype for Business Online 用 Windows PowerShell モジュール」からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="e2946-159">Related topics</span></span>

[<span data-ttu-id="e2946-160">オーディオ会議設定を変更するときにユーザーに送信される電子メール</span><span class="sxs-lookup"><span data-stu-id="e2946-160">Emails sent to users when their Audio Conferencing settings change</span></span>](emails-sent-to-users-when-their-settings-change.md)

[<span data-ttu-id="e2946-161">ユーザーに電話会議情報が含まれたメールを送信する</span><span class="sxs-lookup"><span data-stu-id="e2946-161">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information.md)


