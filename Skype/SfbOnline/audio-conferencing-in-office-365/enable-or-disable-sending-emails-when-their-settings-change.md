---
title: 有効にするか、オンライン ビジネスの Skype で電話会議の設定を変更すると送信メールを無効にします。
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: '有効にするか、暗証番号 (pin) の変更など、既定の会議の設定番号を変更するときに、ユーザーに e メールを送信することから、Skype を無効にする方法を説明します。 '
ms.openlocfilehash: fc6a248974dba22c18cce00246b3b9312f294229
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23883979"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-skype-for-business-online"></a><span data-ttu-id="b3b22-103">有効にするか、オンライン ビジネスの Skype で電話会議の設定を変更すると送信メールを無効にします。</span><span class="sxs-lookup"><span data-stu-id="b3b22-103">Enable or disable sending emails when Audio Conferencing settings change in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="b3b22-104">有効にするか、マイクロソフトのチームでの送信メールを無効にする場合は、[有効にするかマイクロソフトのチームでのオーディオ会議設定を変更すると、送信メールを無効にする](/MicrosoftTeams/enable-or-disable-sending-emails-when-their-settings-change-in-teams)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3b22-104">If you want to enable or disable sending emails in Microsoft Teams, see [Enable or disable sending emails when Audio Conferencing settings change in Microsoft Teams](/MicrosoftTeams/enable-or-disable-sending-emails-when-their-settings-change-in-teams).</span></span>

<span data-ttu-id="b3b22-105">ユーザーは、電話会議が有効になっているときに自動的に電子メールで通知されます。</span><span class="sxs-lookup"><span data-stu-id="b3b22-105">Users are automatically notified by email when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="b3b22-106">場合があります、ただし、Skype をビジネス ユーザーに送信される電子メールの数を減らしたいとします。</span><span class="sxs-lookup"><span data-stu-id="b3b22-106">There may be times, however, when you want to reduce the number of emails that are sent to Skype for Business users.</span></span> <span data-ttu-id="b3b22-107">このような場合は、電子メールの送信を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="b3b22-107">In such cases, you can disable sending email.</span></span>
  
<span data-ttu-id="b3b22-108">オーディオ会議の電子メールをユーザーが有効になっているか、オーディオ会議は、会議 ID と既定の会議の電話番号の変更と、PIN をリセットすると無効にすると、電子メールを含む、ユーザーに送信されません送信メールを無効にした場合.</span><span class="sxs-lookup"><span data-stu-id="b3b22-108">If you disable sending emails, Audio Conferencing emails won't be sent to your users, including emails for when users are enabled or disabled for audio conferencing, when their PIN is reset, and when the conference ID and the default conferencing phone number changes.</span></span>
  
<span data-ttu-id="b3b22-109">電話会議が有効になっているときに、ユーザーに送信されるメールの例を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="b3b22-109">Here is an example of the email that is sent to users when they are enabled for Audio Conferencing:</span></span>
  
![オーディオ会議の電子メール](../images/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a><span data-ttu-id="b3b22-111">メール ユーザーに送信するのでしょうか。</span><span class="sxs-lookup"><span data-stu-id="b3b22-111">When are emails being sent to your users?</span></span>

- <span data-ttu-id="b3b22-112">送信される、組織内のユーザーを有効にした後には、オーディオ会議のいくつかの電子メールがあります。</span><span class="sxs-lookup"><span data-stu-id="b3b22-112">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="b3b22-113">**電話会議** のライセンスがユーザーに割り当てられた場合。</span><span class="sxs-lookup"><span data-stu-id="b3b22-113">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="b3b22-114">リセットすると手動で電話会議のユーザーの暗証番号 (pin) です。</span><span class="sxs-lookup"><span data-stu-id="b3b22-114">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="b3b22-115">ユーザーの会議 ID を手動でリセットした場合。</span><span class="sxs-lookup"><span data-stu-id="b3b22-115">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="b3b22-116">**電話会議**のライセンスは、それらから削除されます。</span><span class="sxs-lookup"><span data-stu-id="b3b22-116">When the **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="b3b22-117">オーディオ会議プロバイダーのユーザーの変更されたとき Microsoft から別のプロバイダーまたは **[なし]** にします。</span><span class="sxs-lookup"><span data-stu-id="b3b22-117">When the audio conferencing provider of a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="b3b22-118">マイクロソフトにユーザーの電話会議プロバイダーが変更されたとき。</span><span class="sxs-lookup"><span data-stu-id="b3b22-118">When the audio conferencing provider of a user is changed to Microsoft.</span></span>


## <a name="enable-or-disable-email-from-being-sent-to-users"></a><span data-ttu-id="b3b22-119">有効にするか、ユーザーに送信される電子メールを無効にします。</span><span class="sxs-lookup"><span data-stu-id="b3b22-119">Enable or disable email from being sent to users</span></span>

<span data-ttu-id="b3b22-120">You can use the Skype for Business admin center or Windows PowerShell to enable or disable email from being sent to users.</span><span class="sxs-lookup"><span data-stu-id="b3b22-120">You can use the Skype for Business admin center or Windows PowerShell to enable or disable email sent to users.</span></span>

 
<span data-ttu-id="b3b22-121">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Skype for Business の管理センターを使用する**</span><span class="sxs-lookup"><span data-stu-id="b3b22-121">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
    
1. <span data-ttu-id="b3b22-122">**Skype**ビジネス管理センターは、左側のナビゲーションでは、[**電話会議**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b3b22-122">In the **Skype for Business admin center**, in the left navigation, click **Audio conferencing**.</span></span>
    
2. <span data-ttu-id="b3b22-123">電話会議の設定を使用してユーザーにメールを送信することもできます。これには、ユーザーの電話会議プロパティに移動して、[ **電話会議情報をメールで送信**] をクリックします。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="b3b22-123">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>
    
3. <span data-ttu-id="b3b22-124">電話会議の設定を使用してユーザーにメールを送信することもできます。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="b3b22-124">Click **Save**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="b3b22-125">送信することも電子メール ユーザーに電話会議の設定を使用して**オーディオ会議**に > の**ユーザー**ユーザーを選択し、**電子メールを使用して会議情報を送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b3b22-125">You can also send email to a user with the audio conferencing settings by going to **Audio conferencing** > **Users**, selecting the user, and clicking **Send conference info via email**.</span></span>  <span data-ttu-id="b3b22-126">これを行うには、会議 ID と電話会議の番号がない、暗証番号 (pin) のみを含む電子メールが送信されます。</span><span class="sxs-lookup"><span data-stu-id="b3b22-126">If you do this, an email will be sent that only includes conference ID and conference phone number, but not the PIN.</span></span>  <span data-ttu-id="b3b22-127">詳細については[、オーディオ会議の情報を持つユーザーに電子メールを送信する](send-an-email-to-a-user-with-their-dial-in-information.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3b22-127">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md) for more information.</span></span>
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

<span data-ttu-id="b3b22-128">**The conference ID and default dial-in conferencing phone number is included on the meeting invite but not the PIN.**</span><span class="sxs-lookup"><span data-stu-id="b3b22-128">**Using Windows PowerShell**</span></span>
  
- <span data-ttu-id="b3b22-129">送信メールを無効にするのには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="b3b22-129">Run the following to disable sending emails:</span></span> 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

    <span data-ttu-id="b3b22-130">このコマンドレットのヘルプを表示するには、[一連の CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3b22-130">For help with this cmdlet, see [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757).</span></span>
    
## <a name="what-else-should-you-know"></a><span data-ttu-id="b3b22-131">その他の情報</span><span class="sxs-lookup"><span data-stu-id="b3b22-131">What else should you know?</span></span>

- <span data-ttu-id="b3b22-132">自動メールを無効にすると、ビジネス管理センターは、Skype を使用して会議の ID と電話番号と電子メールを送信するを手動でトリガーできます。</span><span class="sxs-lookup"><span data-stu-id="b3b22-132">When automatic emails are disabled, you can still manually trigger sending an email with the conference ID and phone number using the Skype for Business admin center.</span></span> <span data-ttu-id="b3b22-133">ただし、これを行うには、PIN に含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="b3b22-133">However, if you do this, the PIN won't be included.</span></span> <span data-ttu-id="b3b22-134">オーディオ会議の暗証番号 (pin) をリセットするし、電子メールの送信が無効になっている、別の方法でユーザーに送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b3b22-134">If you want to reset the audio conferencing PIN and sending emails is disabled, you will need to send it to the user in another way.</span></span>
    
- <span data-ttu-id="b3b22-135">ユーザーに電子メールを送信を無効にできます、Skype のビジネス管理センターまたは Windows PowerShell の使用します。</span><span class="sxs-lookup"><span data-stu-id="b3b22-135">Sending email to your users can be disabled using the Skype for Business admin center or the Windows PowerShell.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="b3b22-136">Go to the Office 365 admin centerSkype for Business.</span><span class="sxs-lookup"><span data-stu-id="b3b22-136">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="b3b22-137">これらのコマンドレットを使用するには時間を保存するか、これを自動化します。</span><span class="sxs-lookup"><span data-stu-id="b3b22-137">You can use these cmdlets to save time or automate this.</span></span>
    
  - [<span data-ttu-id="b3b22-138">Get CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="b3b22-138">Get-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715760)
    
  - [<span data-ttu-id="b3b22-139">削除 CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="b3b22-139">Remove-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715759)
    
  - [<span data-ttu-id="b3b22-140">Get CsOnlineDialinConferencingTenantConfiguration</span><span class="sxs-lookup"><span data-stu-id="b3b22-140">Get-CsOnlineDialinConferencingTenantConfiguration</span></span>](https://go.microsoft.com/fwlink/?LinkId=715758)
    
  - [<span data-ttu-id="b3b22-141">Get CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="b3b22-141">Get-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715760)
    
-  <span data-ttu-id="b3b22-p104">Windows PowerShell は、ユーザーと、ユーザーに許可されていることと許可されていないことを管理するためにあるということです。Windows PowerShell があれば、一元管理を使用して Office 365 を管理し、複数のタスクを抱えているときに、日常の仕事を簡素化することができます。Windows PowerShell を開始するには、これらのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3b22-p104">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="b3b22-145">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="b3b22-145">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="b3b22-146">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="b3b22-146">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="b3b22-p105">多くのユーザーの設定を同時に変更するときなどは、Office 365 管理センターのみを使用するよりも、Windows PowerShell の方に、速度、わかりやすさ、生産性の点で多くのメリットがあります。 次のトピックで、これらの利点を説明します。</span><span class="sxs-lookup"><span data-stu-id="b3b22-p105">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="b3b22-149">Windows PowerShell と Lync Online の概要</span><span class="sxs-lookup"><span data-stu-id="b3b22-149">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="b3b22-150">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="b3b22-150">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="b3b22-151">クイック リファレンス: Windows PowerShell を使用した一般的な Lync Online の管理タスクの実行</span><span class="sxs-lookup"><span data-stu-id="b3b22-151">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="b3b22-p106">Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行[](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="b3b22-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="b3b22-154">このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「Skype for Business Online 用 Windows PowerShell モジュール」からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="b3b22-154">Related topics</span></span>

[<span data-ttu-id="b3b22-155">オーディオ会議設定を変更するときにユーザーに送信される電子メール</span><span class="sxs-lookup"><span data-stu-id="b3b22-155">Emails sent to users when their Audio Conferencing settings change</span></span>](emails-sent-to-users-when-their-settings-change.md)

[<span data-ttu-id="b3b22-156">ユーザーに電話会議情報が含まれたメールを送信する</span><span class="sxs-lookup"><span data-stu-id="b3b22-156">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information.md)


