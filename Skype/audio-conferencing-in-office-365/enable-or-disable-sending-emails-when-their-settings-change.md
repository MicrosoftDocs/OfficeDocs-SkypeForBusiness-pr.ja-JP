---
title: "有効にするかの設定を変更すると、送信メールを無効にします。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
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
description: "有効にするか、暗証番号 (pin) の変更など、既定の会議の設定番号を変更するときに、ユーザーに e メールを送信することから、Skype を無効にする方法を説明します。 "
ms.openlocfilehash: 4efabf42f7253d89b37282103a3046cf7b2b0d26
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/15/2017
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change"></a><span data-ttu-id="94197-103">有効にするか、オーディオ会議の設定を変更すると、送信メールを無効にします。</span><span class="sxs-lookup"><span data-stu-id="94197-103">Enable or disable sending emails when Audio Conferencing settings change</span></span>

<span data-ttu-id="94197-104">ユーザーは、電話会議が有効になっているときに自動的に電子メールで通知されます。</span><span class="sxs-lookup"><span data-stu-id="94197-104">Users are automatically notified by email when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="94197-105">ただし、Skype のビジネスおよびマイクロソフトのチームのユーザーに送信される電子メールの数を削減したい場合があります。</span><span class="sxs-lookup"><span data-stu-id="94197-105">There may be times, however, when you want to reduce the number of emails that are sent to Skype for Business and Microsoft Teams user.</span></span> <span data-ttu-id="94197-106">このような場合は、電子メールの送信を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="94197-106">In such cases, you can disable sending email.</span></span>
  
<span data-ttu-id="94197-107">オーディオ会議の電子メールをユーザーが有効になっているか、オーディオ会議は、会議 ID と既定の会議の電話番号の変更と、PIN をリセットすると無効にすると、電子メールを含む、ユーザーに送信されません送信メールを無効にした場合.</span><span class="sxs-lookup"><span data-stu-id="94197-107">If you disable sending emails, Audio Conferencing emails won't be sent to your users, including emails for when users are enabled or disabled for audio conferencing, when their PIN is reset, and when the conference ID and the default conferencing phone number changes.</span></span>
  
<span data-ttu-id="94197-108">電話会議が有効になっているときに、ユーザーに送信されるメールの例を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="94197-108">Here is an example of the email that is sent to users when they are enabled for Audio Conferencing:</span></span>
  
![オーディオ会議の電子メール](../images/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a><span data-ttu-id="94197-110">メール ユーザーに送信するのでしょうか。</span><span class="sxs-lookup"><span data-stu-id="94197-110">When are emails being sent to your users?</span></span>

- <span data-ttu-id="94197-111">送信される、組織内のユーザーを有効にした後には、オーディオ会議のいくつかの電子メールがあります。</span><span class="sxs-lookup"><span data-stu-id="94197-111">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="94197-112">ときに、**オーディオ会議**のライセンスが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="94197-112">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="94197-113">リセットすると手動で電話会議のユーザーの暗証番号 (pin) です。</span><span class="sxs-lookup"><span data-stu-id="94197-113">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="94197-114">ユーザーの会議 ID を手動でリセットした場合。</span><span class="sxs-lookup"><span data-stu-id="94197-114">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="94197-115">**電話会議**のライセンスは、それらから削除されます。</span><span class="sxs-lookup"><span data-stu-id="94197-115">When the **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="94197-116">オーディオ会議プロバイダーのユーザーの変更されたとき Microsoft から別のプロバイダーまたは**[なし]**にします。</span><span class="sxs-lookup"><span data-stu-id="94197-116">When the audio conferencing provider of a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="94197-117">マイクロソフトにユーザーの電話会議プロバイダーが変更されたとき。</span><span class="sxs-lookup"><span data-stu-id="94197-117">When the audio conferencing provider of a user is changed to Microsoft.</span></span>
    
## <a name="enable-or-disable-email-from-being-sent-to-users"></a><span data-ttu-id="94197-118">有効にするか、ユーザーに送信される電子メールを無効にします。</span><span class="sxs-lookup"><span data-stu-id="94197-118">Enable or disable email from being sent to users</span></span>

<span data-ttu-id="94197-119">有効にするか、ユーザーに送信される電子メールを無効にするのには、ビジネス管理センターの Skype または Windows PowerShell を使用できます。</span><span class="sxs-lookup"><span data-stu-id="94197-119">You can use the Skype for Business admin center or Windows PowerShell to enable or disable email sent to users.</span></span>
  
 <span data-ttu-id="94197-120">**ビジネス管理センターに、Skype を使用します。**</span><span class="sxs-lookup"><span data-stu-id="94197-120">**Using the Skype for Business admin center**</span></span>
  
1. <span data-ttu-id="94197-121">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="94197-121">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="94197-122">**Office 365 管理センター**を参照して > **ビジネス用の Skype**では、左側のナビゲーションで [**電話会議**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94197-122">Go to the **Office 365 admin center** > **Skype for Business**, and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="94197-123">**Microsoft ブリッジの設定**] ページをオンまたはオフの**オーディオ会議の設定を変更する場合、ユーザーに e メールを自動的に送信**する。</span><span class="sxs-lookup"><span data-stu-id="94197-123">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>
    
4. <span data-ttu-id="94197-124">[ **保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94197-124">Click **Save**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="94197-125">送信することも電子メール ユーザーに電話会議の設定を使用して**オーディオ会議**に > の**ユーザー**ユーザーを選択し、**電子メールを使用して会議情報を送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94197-125">You can also send email to a user with the audio conferencing settings by going to **Audio conferencing** > **Users**, selecting the user, and clicking **Send conference info via email**.</span></span>  <span data-ttu-id="94197-126">これを行うには、会議 ID と電話会議の番号がない、暗証番号 (pin) のみを含む電子メールが送信されます。</span><span class="sxs-lookup"><span data-stu-id="94197-126">If you do this, an email will be sent that only includes conference ID and conference phone number, but not the PIN.</span></span>  <span data-ttu-id="94197-127">詳細については[、オーディオ会議の情報を持つユーザーに電子メールを送信する](send-an-email-to-a-user-with-their-dial-in-information.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="94197-127">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md) for more information.</span></span>
  
 <span data-ttu-id="94197-128">**Windows PowerShell を使用します。**</span><span class="sxs-lookup"><span data-stu-id="94197-128">**Using Windows PowerShell**</span></span>
  
- <span data-ttu-id="94197-129">送信メールを無効にするのには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="94197-129">Run the following to disable sending emails:</span></span> 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

    <span data-ttu-id="94197-130">このコマンドレットのヘルプを表示するには、[一連の CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="94197-130">For help with this cmdlet, see [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757).</span></span>
    
## <a name="what-else-should-you-know"></a><span data-ttu-id="94197-131">その他の情報</span><span class="sxs-lookup"><span data-stu-id="94197-131">What else should you know?</span></span>

- <span data-ttu-id="94197-132">自動メールを無効にすると、ビジネス管理センターは、Skype を使用して会議の ID と電話番号と電子メールを送信するを手動でトリガーできます。</span><span class="sxs-lookup"><span data-stu-id="94197-132">When automatic emails are disabled, you can still manually trigger sending an email with the conference ID and phone number using the Skype for Business admin center.</span></span> <span data-ttu-id="94197-133">ただし、これを行うには、PIN に含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="94197-133">However, if you do this, the PIN won't be included.</span></span> <span data-ttu-id="94197-134">オーディオ会議の暗証番号 (pin) をリセットするし、電子メールの送信が無効になっている、別の方法でユーザーに送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="94197-134">If you want to reset the audio conferencing PIN and sending emails is disabled, you will need to send it to the user in another way.</span></span>
    
- <span data-ttu-id="94197-135">既定では、電子メールの送信者は、Office 365 からなりますが、電子メール アドレスを変更し、Windows PowerShell を使用して名前を表示して[セット CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757)コマンドレットを使用しても。</span><span class="sxs-lookup"><span data-stu-id="94197-135">By default, the sender of the emails will be from Office 365, but you can change the email address and display name using Windows PowerShell and also use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757) cmdlet.</span></span>
    
    > [!NOTE]
    >  <span data-ttu-id="94197-136">電子メール アドレス情報を変更する場合は、環境内の受信電子メール ポリシーが、アドレスから指定されたユーザーから送信される電子メールを許可するかどうかを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="94197-136">If you want to change the email address information, you need to make sure that the inbound email policies of your environment allow emails that come from the custom specified from address.</span></span>
  
  - <span data-ttu-id="94197-137">_SendEmailFromAddress_ パラメーターにメール アドレスを入力する</span><span class="sxs-lookup"><span data-stu-id="94197-137">Enter the email address in the  _SendEmailFromAddress_ parameter.</span></span>
    
  - <span data-ttu-id="94197-138">_SendEmailFromDisplayName_ パラメーターにメールの表示名を入力する</span><span class="sxs-lookup"><span data-stu-id="94197-138">Enter the email display name in the  _SendEmailFromDisplayName_ parameter.</span></span>
    
  - <span data-ttu-id="94197-139">_SendEmailOverride_パラメーターを_True_に設定します。</span><span class="sxs-lookup"><span data-stu-id="94197-139">Set the  _SendEmailOverride_ parameter to _True_.</span></span>
    
  -  `Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"`
    
- <span data-ttu-id="94197-140">ユーザーに電子メールを送信を無効にできます、Skype のビジネス管理センターまたは Windows PowerShell の使用します。</span><span class="sxs-lookup"><span data-stu-id="94197-140">Sending email to your users can be disabled using the Skype for Business admin center or the Windows PowerShell.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="94197-141">Windows PowerShell で管理する方法</span><span class="sxs-lookup"><span data-stu-id="94197-141">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="94197-142">これらのコマンドレットを使用するには時間を保存するか、これを自動化します。</span><span class="sxs-lookup"><span data-stu-id="94197-142">You can use these cmdlets to save time or automate this.</span></span>
    
  - [<span data-ttu-id="94197-143">Get CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="94197-143">Get-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715760)
    
  - [<span data-ttu-id="94197-144">削除 CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="94197-144">Remove-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715759)
    
  - [<span data-ttu-id="94197-145">Get CsOnlineDialinConferencingTenantConfiguration</span><span class="sxs-lookup"><span data-stu-id="94197-145">Get-CsOnlineDialinConferencingTenantConfiguration</span></span>](https://go.microsoft.com/fwlink/?LinkId=715758)
    
  - [<span data-ttu-id="94197-146">Get CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="94197-146">Get-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715760)
    
-  <span data-ttu-id="94197-147">Windows PowerShell は、ユーザーを管理するユーザーを許可または許可されません。</span><span class="sxs-lookup"><span data-stu-id="94197-147">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="94197-148">Windows PowerShell を実行する複数のタスクがある場合、日常的な作業を簡素化する管理の単一ポイントを使用して Office 365 を管理できます。</span><span class="sxs-lookup"><span data-stu-id="94197-148">With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="94197-149">Windows PowerShell を使い始めるには、以下のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="94197-149">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="94197-150">Office 365 の PowerShell を使用する必要がある理由</span><span class="sxs-lookup"><span data-stu-id="94197-150">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="94197-151">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="94197-151">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="94197-152">Windows PowerShell には、実行しようとする設定の変更多くのユーザーを一度に 1 つなど、Office 365 管理センターを使用するだけでスピード、シンプルさと生産性に多くの利点があります。</span><span class="sxs-lookup"><span data-stu-id="94197-152">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="94197-153">次のトピックで、これらの利点について学習します。</span><span class="sxs-lookup"><span data-stu-id="94197-153">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="94197-154">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="94197-154">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="94197-155">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="94197-155">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="94197-156">Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行</span><span class="sxs-lookup"><span data-stu-id="94197-156">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="94197-p106">Skype for Business Online 用 Windows PowerShell モジュールでは、リモート Windows PowerShell セッションを作成して Skype for Business Online に接続できます。このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「[Skype for Business Online 用 Windows PowerShell モジュール](https://go.microsoft.com/fwlink/?LinkId=294688)」からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="94197-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="94197-159">関連トピック</span><span class="sxs-lookup"><span data-stu-id="94197-159">Related topics</span></span>

[<span data-ttu-id="94197-160">オーディオ会議設定を変更するときにユーザーに送信される電子メール</span><span class="sxs-lookup"><span data-stu-id="94197-160">Emails sent to users when their Audio Conferencing settings change</span></span>](emails-sent-to-users-when-their-settings-change.md)

[<span data-ttu-id="94197-161">オーディオ会議の情報を持つユーザーに電子メールを送信します。</span><span class="sxs-lookup"><span data-stu-id="94197-161">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information.md)

[<span data-ttu-id="94197-162">Skype for Business および Microsoft Teams の電話会議のセットアップ</span><span class="sxs-lookup"><span data-stu-id="94197-162">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](set-up-audio-conferencing.md)

