---
title: Skype for Business Online で電話会議の設定が変更された場合にメールの送信を有効または無効にする
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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'PIN の変更や既定の会議Skypeなどの設定が変更された場合に、ユーザーにメールを送信する機能を有効または無効にする方法について説明します。 '
ms.openlocfilehash: f6596e3e5c52dd82f4f61ad176ae4d656a5f146c
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237323"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-skype-for-business-online"></a><span data-ttu-id="5d816-103">Skype for Business Online で電話会議の設定が変更された場合にメールの送信を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="5d816-103">Enable or disable sending emails when Audio Conferencing settings change in Skype for Business Online</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> <span data-ttu-id="5d816-104">Microsoft Teams でメールの送信を有効または無効にする場合は、「Microsoft Teams で電話会議の設定が変更された場合にメールの送信を有効または無効にする」[をMicrosoft Teams。](/MicrosoftTeams/enable-or-disable-sending-emails-when-their-settings-change-in-teams)</span><span class="sxs-lookup"><span data-stu-id="5d816-104">If you want to enable or disable sending emails in Microsoft Teams, see [Enable or disable sending emails when Audio Conferencing settings change in Microsoft Teams](/MicrosoftTeams/enable-or-disable-sending-emails-when-their-settings-change-in-teams).</span></span>

<span data-ttu-id="5d816-105">電話会議が有効になると、ユーザーに電子メールで自動的に通知されます。</span><span class="sxs-lookup"><span data-stu-id="5d816-105">Users are automatically notified by email when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="5d816-106">ただし、ユーザーに送信されるメールの数を減らしたい場合Skype for Businessがあります。</span><span class="sxs-lookup"><span data-stu-id="5d816-106">There may be times, however, when you want to reduce the number of emails that are sent to Skype for Business users.</span></span> <span data-ttu-id="5d816-107">このような場合は、メールの送信を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="5d816-107">In such cases, you can disable sending email.</span></span>
  
<span data-ttu-id="5d816-108">メールの送信を無効にした場合、電話会議メールはユーザーに送信されません。たとえば、ユーザーが電話会議に対して有効または無効になっているとき、PIN がリセットされた場合、電話会議 ID と既定の会議電話番号が変更された場合のメールも含めて送信されません。</span><span class="sxs-lookup"><span data-stu-id="5d816-108">If you disable sending emails, Audio Conferencing emails won't be sent to your users, including emails for when users are enabled or disabled for audio conferencing, when their PIN is reset, and when the conference ID and the default conferencing phone number changes.</span></span>
  
<span data-ttu-id="5d816-109">電話会議が有効になっているユーザーに送信されるメールの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="5d816-109">Here is an example of the email that is sent to users when they are enabled for Audio Conferencing:</span></span>
  
![電話会議の電子メール](../images/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a><span data-ttu-id="5d816-111">メールがユーザーに送信されるのは、いつですか?</span><span class="sxs-lookup"><span data-stu-id="5d816-111">When are emails being sent to your users?</span></span>

- <span data-ttu-id="5d816-112">電話会議を有効にした後、組織内のユーザーに送信されるメールは複数あります。</span><span class="sxs-lookup"><span data-stu-id="5d816-112">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="5d816-113">**電話会議** のライセンスがユーザーに割り当てられた場合。</span><span class="sxs-lookup"><span data-stu-id="5d816-113">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="5d816-114">ユーザーの電話会議 PIN を手動でリセットする場合。</span><span class="sxs-lookup"><span data-stu-id="5d816-114">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="5d816-115">ユーザーの会議 ID を手動でリセットした場合。</span><span class="sxs-lookup"><span data-stu-id="5d816-115">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="5d816-116">電話会議 **ライセンスが** 削除された場合。</span><span class="sxs-lookup"><span data-stu-id="5d816-116">When the **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="5d816-117">ユーザーの電話会議プロバイダーが Microsoft から別のプロバイダーまたはなし に変更 **された場合**。</span><span class="sxs-lookup"><span data-stu-id="5d816-117">When the audio conferencing provider of a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="5d816-118">ユーザーの電話会議プロバイダーが Microsoft に変更された場合。</span><span class="sxs-lookup"><span data-stu-id="5d816-118">When the audio conferencing provider of a user is changed to Microsoft.</span></span>


## <a name="enable-or-disable-email-from-being-sent-to-users"></a><span data-ttu-id="5d816-119">メールがユーザーに送信されるのを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="5d816-119">Enable or disable email from being sent to users</span></span>

<span data-ttu-id="5d816-120">管理者センターまたは Skype for Businessを使用してWindows PowerShellに送信されたメールを有効または無効にできます。</span><span class="sxs-lookup"><span data-stu-id="5d816-120">You can use the Skype for Business admin center or Windows PowerShell to enable or disable email sent to users.</span></span>

 
<span data-ttu-id="5d816-121">![Skype for Business のロゴを表示したアイコン](../images/sfb-logo-30x30.png) **Skype for Business 管理センターの使用**</span><span class="sxs-lookup"><span data-stu-id="5d816-121">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
    
1. <span data-ttu-id="5d816-122">[Skype for Business **センター] の左側** のナビゲーションで、[電話会議]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="5d816-122">In the **Skype for Business admin center**, in the left navigation, click **Audio conferencing**.</span></span>
    
2. <span data-ttu-id="5d816-123">電話会議の設定を使用してユーザーにメールを送信することもできます。これには、ユーザーの電話会議プロパティに移動して、[ **電話会議情報をメールで送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5d816-123">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>
    
3. <span data-ttu-id="5d816-124">電話会議の設定を使用してユーザーにメールを送信することもできます。</span><span class="sxs-lookup"><span data-stu-id="5d816-124">Click **Save**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="5d816-125">[電話会議ユーザー] に移動し、ユーザーを選択し、[電子メールで電話会議情報を送信] をクリックして、電話会議の設定を使用してユーザーにメール  >  **を送信することもできます**。</span><span class="sxs-lookup"><span data-stu-id="5d816-125">You can also send email to a user with the audio conferencing settings by going to **Audio conferencing** > **Users**, selecting the user, and clicking **Send conference info via email**.</span></span>  <span data-ttu-id="5d816-126">この操作を行う場合、PIN ではなく、会議 ID と電話会議の電話番号のみを含むメールが送信されます。</span><span class="sxs-lookup"><span data-stu-id="5d816-126">If you do this, an email will be sent that only includes conference ID and conference phone number, but not the PIN.</span></span>  <span data-ttu-id="5d816-127">詳細 [については、「電話会議情報を使用してユーザーに電子メールを送信する」](send-an-email-to-a-user-with-their-dial-in-information.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d816-127">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md) for more information.</span></span>
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

<span data-ttu-id="5d816-128">**Windows PowerShell を使用する**</span><span class="sxs-lookup"><span data-stu-id="5d816-128">**Using Windows PowerShell**</span></span>
  
- <span data-ttu-id="5d816-129">次のコマンドを実行して、メールの送信を無効にします。</span><span class="sxs-lookup"><span data-stu-id="5d816-129">Run the following to disable sending emails:</span></span> 
    
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

    <span data-ttu-id="5d816-130">このコマンドレットのヘルプについては [、「Set-CsOnlineDialInConferencingTenantSettings」を参照してください](/powershell/module/skype/Set-CsOnlineDialInConferencingTenantSettings)。</span><span class="sxs-lookup"><span data-stu-id="5d816-130">For help with this cmdlet, see [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Set-CsOnlineDialInConferencingTenantSettings).</span></span>
    
## <a name="what-else-should-you-know"></a><span data-ttu-id="5d816-131">その他の情報</span><span class="sxs-lookup"><span data-stu-id="5d816-131">What else should you know?</span></span>

- <span data-ttu-id="5d816-132">自動メールを無効にした場合でも、管理者センターの管理センターで会議 ID と電話番号を含む電子メールの送信Skype for Businessトリガーできます。</span><span class="sxs-lookup"><span data-stu-id="5d816-132">When automatic emails are disabled, you can still manually trigger sending an email with the conference ID and phone number using the Skype for Business admin center.</span></span> <span data-ttu-id="5d816-133">ただし、この操作を行った場合、PIN は含まれません。</span><span class="sxs-lookup"><span data-stu-id="5d816-133">However, if you do this, the PIN won't be included.</span></span> <span data-ttu-id="5d816-134">電話会議 PIN をリセットし、メールの送信が無効になっている場合は、別の方法でユーザーに送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d816-134">If you want to reset the audio conferencing PIN and sending emails is disabled, you will need to send it to the user in another way.</span></span>
    
- <span data-ttu-id="5d816-135">ユーザーにメールを送信するには、管理者センターまたは管理者Skype for Businessを使用Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="5d816-135">Sending email to your users can be disabled using the Skype for Business admin center or the Windows PowerShell.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="5d816-136">Windows PowerShell での管理方法について</span><span class="sxs-lookup"><span data-stu-id="5d816-136">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="5d816-137">これらのコマンドレットを使用すると、時間を節約したり、自動化することができます。</span><span class="sxs-lookup"><span data-stu-id="5d816-137">You can use these cmdlets to save time or automate this.</span></span>
    
  - [<span data-ttu-id="5d816-138">Get-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="5d816-138">Get-CsOnlineDialInConferencingTenantSettings</span></span>](/powershell/module/skype/Get-CsOnlineDialInConferencingTenantSettings)
    
  - [<span data-ttu-id="5d816-139">Remove-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="5d816-139">Remove-CsOnlineDialInConferencingTenantSettings</span></span>](/powershell/module/skype/Remove-CsOnlineDialInConferencingTenantSettings)
    
  - [<span data-ttu-id="5d816-140">Get-CsOnlineDialinConferencingTenantConfiguration</span><span class="sxs-lookup"><span data-stu-id="5d816-140">Get-CsOnlineDialinConferencingTenantConfiguration</span></span>](/powershell/module/skype/Get-CsOnlineDialinConferencingTenantConfiguration)
    
  - [<span data-ttu-id="5d816-141">Get-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="5d816-141">Get-CsOnlineDialInConferencingTenantSettings</span></span>](/powershell/module/skype/Get-CsOnlineDialInConferencingTenantSettings)
    
- <span data-ttu-id="5d816-142">Windows PowerShellは、ユーザーの管理と、ユーザーが許可または許可されていない操作についてすべて行います。</span><span class="sxs-lookup"><span data-stu-id="5d816-142">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="5d816-143">このWindows PowerShell、1 つの管理Microsoft 365またはOffice 365を管理し、複数のタスクを実行する場合に毎日の作業を簡略化できます。</span><span class="sxs-lookup"><span data-stu-id="5d816-143">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="5d816-144">Windows PowerShell の使用を開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d816-144">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="5d816-145">PowerShell で使用する必要があるMicrosoft 365またはOffice 365理由</span><span class="sxs-lookup"><span data-stu-id="5d816-145">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="5d816-146">[アプリを使用してMicrosoft 365またはOffice 365を管理Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="5d816-146">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
- <span data-ttu-id="5d816-147">Windows PowerShell多くのユーザーに対して一度に設定を変更する場合など、Microsoft 365 管理センターのみを使用する場合に、速度、シンプルさ、生産性に多くの利点があります。</span><span class="sxs-lookup"><span data-stu-id="5d816-147">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="5d816-148">次のトピックで、これらの利点を説明します。</span><span class="sxs-lookup"><span data-stu-id="5d816-148">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="5d816-149">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="5d816-149">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="5d816-150">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="5d816-150">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="5d816-151">Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行</span><span class="sxs-lookup"><span data-stu-id="5d816-151">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > <span data-ttu-id="5d816-p106">Skype for Business Online 用の Windows PowerShell モジュールがあれば、Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成できます。このモジュールは、64 ビット版のコンピューターでのみサポートされており、「[Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688)」の Microsoft ダウンロード センターからダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="5d816-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="5d816-154">関連項目</span><span class="sxs-lookup"><span data-stu-id="5d816-154">Related topics</span></span>

[<span data-ttu-id="5d816-155">電話会議の設定が変更された場合にユーザーに送信されるメール</span><span class="sxs-lookup"><span data-stu-id="5d816-155">Emails sent to users when their Audio Conferencing settings change</span></span>](emails-sent-to-users-when-their-settings-change.md)

[<span data-ttu-id="5d816-156">電話会議の情報が記載されたメールをユーザーに送信する</span><span class="sxs-lookup"><span data-stu-id="5d816-156">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information.md)
