---
title: "有効にするか、設定を変更するときに、送信メールを無効にします。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
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
description: "有効にするまたは数の変更が pin の変更など、既定の会議の設定は、ユーザーにメールを送信するから Skype を無効にする方法について説明します。 "
ms.openlocfilehash: 3fd5d7c5f12b3e5a88a217eae9a0a86ab0ea9720
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change"></a><span data-ttu-id="d2de9-103">有効にするか、音声会議の設定を変更するときに、送信メールを無効にします。</span><span class="sxs-lookup"><span data-stu-id="d2de9-103">Enable or disable sending emails when Audio Conferencing settings change</span></span>

<span data-ttu-id="d2de9-p101">ユーザーは、音声会議が有効なときに自動的に電子メールで通知されます。ただし、ビジネスや Microsoft チームのユーザーの Skype に送信されたメールの数を減らすしたい場合があります。このような場合は、電子メールの送信を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="d2de9-p101">Users are automatically notified by email when they are enabled for Audio Conferencing. There may be times, however, when you want to reduce the number of emails that are sent to Skype for Business and Microsoft Teams user. In such cases, you can disable sending email.</span></span>
  
<span data-ttu-id="d2de9-107">ユーザーが有効になっているか、会議 ID と既定の会議の電話番号と PIN をリセットすると、電話会議を無効になっているときに、電子メールを含む、ユーザーに電話会議のメールに送られません送信メールを無効にした場合.</span><span class="sxs-lookup"><span data-stu-id="d2de9-107">If you disable sending emails, Audio Conferencing emails won't be sent to your users, including emails for when users are enabled or disabled for audio conferencing, when their PIN is reset, and when the conference ID and the default conferencing phone number changes.</span></span>
  
<span data-ttu-id="d2de9-108">音声会議が有効なときに、ユーザーに送信されるメールの例を示します。</span><span class="sxs-lookup"><span data-stu-id="d2de9-108">Here is an example of the email that is sent to users when they are enabled for Audio Conferencing:</span></span>
  
![会議のオーディオのメール](../images/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a><span data-ttu-id="d2de9-110">ときは、メールに送信されるユーザーですか。</span><span class="sxs-lookup"><span data-stu-id="d2de9-110">When are emails being sent to your users?</span></span>

- <span data-ttu-id="d2de9-111">複数のメールに送信された、組織のユーザーが有効な後に電話会議があります。</span><span class="sxs-lookup"><span data-stu-id="d2de9-111">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="d2de9-112">**電話会議**のライセンスが割り当てられているとします。</span><span class="sxs-lookup"><span data-stu-id="d2de9-112">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="d2de9-113">手動でをリセットすると、ユーザーの電話会議暗証番号 (pin)。</span><span class="sxs-lookup"><span data-stu-id="d2de9-113">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="d2de9-114">ユーザーの会議 ID を手動でリセットする場合</span><span class="sxs-lookup"><span data-stu-id="d2de9-114">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="d2de9-115">**電話会議**ライセンスは、それらから削除されます。</span><span class="sxs-lookup"><span data-stu-id="d2de9-115">When the **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="d2de9-116">ユーザーの電話会議プロバイダーが変更された場合 Microsoft から別のプロバイダー [**なし]**にします。</span><span class="sxs-lookup"><span data-stu-id="d2de9-116">When the audio conferencing provider of a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="d2de9-117">ユーザーの電話会議プロバイダーが Microsoft に変更された場合。</span><span class="sxs-lookup"><span data-stu-id="d2de9-117">When the audio conferencing provider of a user is changed to Microsoft.</span></span>
    
## <a name="enable-or-disable-email-from-being-sent-to-users"></a><span data-ttu-id="d2de9-118">有効にする、またはユーザーに送信されるメールを無効にします。</span><span class="sxs-lookup"><span data-stu-id="d2de9-118">Enable or disable email from being sent to users</span></span>

<span data-ttu-id="d2de9-119">有効にする、またはユーザーに送信されたメールを無効にするのには、Skype for Business 管理センター」または「Windows PowerShell を使用できます。</span><span class="sxs-lookup"><span data-stu-id="d2de9-119">You can use the Skype for Business admin center or Windows PowerShell to enable or disable email sent to users.</span></span>
  
 <span data-ttu-id="d2de9-120">**Business 管理センターの Skype を使用します。**</span><span class="sxs-lookup"><span data-stu-id="d2de9-120">**Using the Skype for Business admin center**</span></span>
  
1. <span data-ttu-id="d2de9-121">職場または学校のアカウントで Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="d2de9-121">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="d2de9-122">**Office 365 管理センター**に移動 > **Skype for Business**の場合は、左のナビゲーションで [**電話会議**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d2de9-122">Go to the **Office 365 admin center** > **Skype for Business**, and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="d2de9-123">**Microsoft ブリッジの設定**] ページでオンまたはオフの**場合は、電話会議の設定を変更するユーザーにメールを自動的に送信**します。</span><span class="sxs-lookup"><span data-stu-id="d2de9-123">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>
    
4. <span data-ttu-id="d2de9-124">{[**保存**] をクリックします。}</span><span class="sxs-lookup"><span data-stu-id="d2de9-124">Click **Save**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="d2de9-p102">送信することもメールをユーザーに電話会議の設定で**電話会議**に移動して > **ユーザー**をユーザーを選択して、**会議情報を電子メールで送信する**] をクリックします。 これを行うをのみが含まれていますが、会議 ID、会議の電話番号、PIN ではないメールが送信されます。 詳細については[、電話会議の情報を持つユーザーにメールを送信する](send-an-email-to-a-user-with-their-dial-in-information.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d2de9-p102">You can also send email to a user with the audio conferencing settings by going to **Audio conferencing** > **Users**, selecting the user, and clicking **Send conference info via email**.  If you do this, an email will be sent that only includes conference ID and conference phone number, but not the PIN.  See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md) for more information.</span></span>
  
 <span data-ttu-id="d2de9-128">**Windows PowerShell を使用します。**</span><span class="sxs-lookup"><span data-stu-id="d2de9-128">**Using Windows PowerShell**</span></span>
  
- <span data-ttu-id="d2de9-129">送信メールを無効にするのには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="d2de9-129">Run the following to disable sending emails:</span></span> 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

    <span data-ttu-id="d2de9-130">このコマンドレット ヘルプは、[セット CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d2de9-130">For help with this cmdlet, see [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757).</span></span>
    
## <a name="what-else-should-you-know"></a><span data-ttu-id="d2de9-131">他かする必要がありますか。</span><span class="sxs-lookup"><span data-stu-id="d2de9-131">What else should you know?</span></span>

- <span data-ttu-id="d2de9-p103">自動メールが無効にするの Skype for Business 管理センターを使った会議 ID と電話番号、メールを送信を手動でトリガーできます。ただし、これを行うには、PIN に含めることはできません。電話会議の PIN をリセットするメールの送信が無効になっている場合は、別の方法でユーザーに送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d2de9-p103">When automatic emails are disabled, you can still manually trigger sending an email with the conference ID and phone number using the Skype for Business admin center. However, if you do this, the PIN won't be included. If you want to reset the audio conferencing PIN and sending emails is disabled, you will need to send it to the user in another way.</span></span>
    
- <span data-ttu-id="d2de9-135">既定ではのメールの送信者が、Office 365 から表示されますが、メール アドレスを変更し、Windows PowerShell を使用して、名前を表示およびも[セット CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757)コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="d2de9-135">By default, the sender of the emails will be from Office 365, but you can change the email address and display name using Windows PowerShell and also use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757) cmdlet.</span></span>
    
    > [!NOTE]
    >  <span data-ttu-id="d2de9-136">メール アドレスの情報を変更する場合は、環境の受信メール ポリシーがアドレスから指定したユーザー設定のメールを許可するかどうかを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d2de9-136">If you want to change the email address information, you need to make sure that the inbound email policies of your environment allow emails that come from the custom specified from address.</span></span>
  
  - <span data-ttu-id="d2de9-137">_SendEmailFromAddress_パラメーターには、メール アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="d2de9-137">Enter the email address in the  _SendEmailFromAddress_ parameter.</span></span>
    
  - <span data-ttu-id="d2de9-138">_SendEmailFromDisplayName_パラメーターには、メールの表示名を入力します。</span><span class="sxs-lookup"><span data-stu-id="d2de9-138">Enter the email display name in the  _SendEmailFromDisplayName_ parameter.</span></span>
    
  - <span data-ttu-id="d2de9-139">_SendEmailOverride_パラメーターを_True_に設定します。</span><span class="sxs-lookup"><span data-stu-id="d2de9-139">Set the  _SendEmailOverride_ parameter to _True_.</span></span>
    
  -  `Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"`
    
- <span data-ttu-id="d2de9-140">ユーザーにメールを送信することができます無効にする、Skype を Business 管理センターの Windows PowerShell を使用します。</span><span class="sxs-lookup"><span data-stu-id="d2de9-140">Sending email to your users can be disabled using the Skype for Business admin center or the Windows PowerShell.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="d2de9-141">Windows PowerShell で管理する方法を知りたいとしていますか。</span><span class="sxs-lookup"><span data-stu-id="d2de9-141">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="d2de9-142">これらのコマンドレットを使用して時間を節約したり、自動化したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="d2de9-142">You can use these cmdlets to save time or automate this.</span></span>
    
  - [<span data-ttu-id="d2de9-143">Get CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="d2de9-143">Get-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715760)
    
  - [<span data-ttu-id="d2de9-144">削除 CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="d2de9-144">Remove-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715759)
    
  - [<span data-ttu-id="d2de9-145">Get CsOnlineDialinConferencingTenantConfiguration</span><span class="sxs-lookup"><span data-stu-id="d2de9-145">Get-CsOnlineDialinConferencingTenantConfiguration</span></span>](https://go.microsoft.com/fwlink/?LinkId=715758)
    
  - [<span data-ttu-id="d2de9-146">Get CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="d2de9-146">Get-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715760)
    
-  <span data-ttu-id="d2de9-p104">Windows PowerShell がユーザーを管理するユーザーを許可または使用できません。Windows PowerShell で複数のタスクを実行するがある場合、日常業務を簡素化する管理の 1 つのポイントを使用して Office 365 を管理できます。Windows PowerShell で開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d2de9-p104">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="d2de9-150">Office 365 PowerShell を使用する必要がある理由</span><span class="sxs-lookup"><span data-stu-id="d2de9-150">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="d2de9-151">Windows PowerShell で Office 365 を管理する最善の方法</span><span class="sxs-lookup"><span data-stu-id="d2de9-151">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="d2de9-p105">Windows PowerShell では多くの利点速度、わかりやすいように、および生産性でのみ実行しようとする設定の変更、多くのユーザーに一度になど、Office 365 管理センターを使用します。次のトピックでこれらの利点について学習します。</span><span class="sxs-lookup"><span data-stu-id="d2de9-p105">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="d2de9-154">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="d2de9-154">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="d2de9-155">Windows PowerShell を使用して、Skype for Business Online の管理するには</span><span class="sxs-lookup"><span data-stu-id="d2de9-155">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="d2de9-156">Windows PowerShell を使用して、共通の Skype for Business Online の管理タスクを実行するには</span><span class="sxs-lookup"><span data-stu-id="d2de9-156">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="d2de9-p106">Skype for Business Online 用の Windows PowerShell モジュールを使用すると、Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成することができます。このモジュールでは、64 ビット コンピューター以外では、Microsoft ダウンロード センターからダウンロードできます[Skype for Business Online 用の Windows PowerShell モジュール](https://go.microsoft.com/fwlink/?LinkId=294688)。</span><span class="sxs-lookup"><span data-stu-id="d2de9-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="d2de9-159">関連トピック</span><span class="sxs-lookup"><span data-stu-id="d2de9-159">Related topics</span></span>

[<span data-ttu-id="d2de9-160">その電話会議の設定を変更するときに、ユーザーに送信されるメール</span><span class="sxs-lookup"><span data-stu-id="d2de9-160">Emails sent to users when their Audio Conferencing settings change</span></span>](emails-sent-to-users-when-their-settings-change.md)

[<span data-ttu-id="d2de9-161">この情報は、電話会議情報を持つユーザーにメールを送信します。</span><span class="sxs-lookup"><span data-stu-id="d2de9-161">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information.md)

[<span data-ttu-id="d2de9-162">Skype for Business とチームの Microsoft の音声会議をセットアップする設定します。</span><span class="sxs-lookup"><span data-stu-id="d2de9-162">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](set-up-audio-conferencing.md)

