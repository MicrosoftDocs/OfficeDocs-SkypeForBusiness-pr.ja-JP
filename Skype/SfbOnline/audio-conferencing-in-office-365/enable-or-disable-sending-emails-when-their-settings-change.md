---
title: Skype for Business Online で電話会議の設定が変更されたときにメールの送信を有効または無効にする
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
description: 'Pin が変更された場合や、既定の電話会議番号が変更された場合に、Skype が電子メールをユーザーに送信するのを有効または無効にする方法について説明します。 '
ms.openlocfilehash: bfdbe1c6c9380b12086ce667c588d8b974438ee5
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41707222"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-skype-for-business-online"></a><span data-ttu-id="6fd42-103">Skype for Business Online で電話会議の設定が変更されたときにメールの送信を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="6fd42-103">Enable or disable sending emails when Audio Conferencing settings change in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="6fd42-104">Microsoft Teams でメールの送信を有効または無効にする場合は、「 [Microsoft teams で電話会議の設定が変更されたときにメールの送信を有効または無効](/MicrosoftTeams/enable-or-disable-sending-emails-when-their-settings-change-in-teams)にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6fd42-104">If you want to enable or disable sending emails in Microsoft Teams, see [Enable or disable sending emails when Audio Conferencing settings change in Microsoft Teams](/MicrosoftTeams/enable-or-disable-sending-emails-when-their-settings-change-in-teams).</span></span>

<span data-ttu-id="6fd42-105">電話会議が有効になっていると、ユーザーにメールで自動的に通知されます。</span><span class="sxs-lookup"><span data-stu-id="6fd42-105">Users are automatically notified by email when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="6fd42-106">ただし、Skype for Business ユーザーに送信されるメールの数を少なくする必要がある場合もあります。</span><span class="sxs-lookup"><span data-stu-id="6fd42-106">There may be times, however, when you want to reduce the number of emails that are sent to Skype for Business users.</span></span> <span data-ttu-id="6fd42-107">その場合は、メールの送信を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="6fd42-107">In such cases, you can disable sending email.</span></span>
  
<span data-ttu-id="6fd42-108">メールの送信を無効にした場合、電話会議のメールはユーザーに送信されません。電話会議でユーザーが有効または無効になっているとき、電話会議の PIN がリセットされたとき、会議 ID と既定の会議の電話番号が変更されたときのメールが含まれます。.</span><span class="sxs-lookup"><span data-stu-id="6fd42-108">If you disable sending emails, Audio Conferencing emails won't be sent to your users, including emails for when users are enabled or disabled for audio conferencing, when their PIN is reset, and when the conference ID and the default conferencing phone number changes.</span></span>
  
<span data-ttu-id="6fd42-109">次に示すのは、電話会議が有効になっているユーザーに送信されるメールの例です。</span><span class="sxs-lookup"><span data-stu-id="6fd42-109">Here is an example of the email that is sent to users when they are enabled for Audio Conferencing:</span></span>
  
![電話会議のメール](../images/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a><span data-ttu-id="6fd42-111">ユーザーにメールが送信されるのはいつですか?</span><span class="sxs-lookup"><span data-stu-id="6fd42-111">When are emails being sent to your users?</span></span>

- <span data-ttu-id="6fd42-112">電話会議を有効にした後、組織内のユーザーに送信されるメールが複数あります。</span><span class="sxs-lookup"><span data-stu-id="6fd42-112">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="6fd42-113">**電話会議** のライセンスがユーザーに割り当てられた場合。</span><span class="sxs-lookup"><span data-stu-id="6fd42-113">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="6fd42-114">ユーザーの電話会議の PIN を手動でリセットした場合。</span><span class="sxs-lookup"><span data-stu-id="6fd42-114">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="6fd42-115">ユーザーの会議 ID を手動でリセットした場合。</span><span class="sxs-lookup"><span data-stu-id="6fd42-115">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="6fd42-116">**電話会議**ライセンスが削除されたとき。</span><span class="sxs-lookup"><span data-stu-id="6fd42-116">When the **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="6fd42-117">ユーザーの電話会議プロバイダーが Microsoft から別のプロバイダーまたは **[なし**] に変更された場合。</span><span class="sxs-lookup"><span data-stu-id="6fd42-117">When the audio conferencing provider of a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="6fd42-118">ユーザーの電話会議プロバイダーが Microsoft に変更された場合。</span><span class="sxs-lookup"><span data-stu-id="6fd42-118">When the audio conferencing provider of a user is changed to Microsoft.</span></span>


## <a name="enable-or-disable-email-from-being-sent-to-users"></a><span data-ttu-id="6fd42-119">ユーザーへのメール送信を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="6fd42-119">Enable or disable email from being sent to users</span></span>

<span data-ttu-id="6fd42-120">Skype for Business 管理センターまたは Windows PowerShell を使用して、ユーザーに送信されたメールを有効または無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="6fd42-120">You can use the Skype for Business admin center or Windows PowerShell to enable or disable email sent to users.</span></span>

 
<span data-ttu-id="6fd42-121">![Skype for Business のロゴを表示したアイコン](../images/sfb-logo-30x30.png) **Skype for Business 管理センターの使用**</span><span class="sxs-lookup"><span data-stu-id="6fd42-121">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
    
1. <span data-ttu-id="6fd42-122">**Skype For business 管理センター**の左側のナビゲーションで、[**電話会議**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6fd42-122">In the **Skype for Business admin center**, in the left navigation, click **Audio conferencing**.</span></span>
    
2. <span data-ttu-id="6fd42-123">電話会議の設定を使用してユーザーにメールを送信することもできます。これには、ユーザーの電話会議プロパティに移動して、[ **電話会議情報をメールで送信**] をクリックします。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="6fd42-123">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>
    
3. <span data-ttu-id="6fd42-124">電話会議の設定を使用してユーザーにメールを送信することもできます。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="6fd42-124">Click **Save**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="6fd42-125">電話会議の設定を使用してユーザーにメールを送信することもできます。電話**会議** > の**ユーザー**に移動し、ユーザーを選んで、[**電話会議情報をメールで送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6fd42-125">You can also send email to a user with the audio conferencing settings by going to **Audio conferencing** > **Users**, selecting the user, and clicking **Send conference info via email**.</span></span>  <span data-ttu-id="6fd42-126">この操作を行うと、会議 ID と電話会議の番号のみを含むメールが送信され、PIN は送信されません。</span><span class="sxs-lookup"><span data-stu-id="6fd42-126">If you do this, an email will be sent that only includes conference ID and conference phone number, but not the PIN.</span></span>  <span data-ttu-id="6fd42-127">詳細については、「[電話会議の情報をユーザーに電子メールで送信する](send-an-email-to-a-user-with-their-dial-in-information.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6fd42-127">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md) for more information.</span></span>
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

<span data-ttu-id="6fd42-128">**Windows PowerShell を使用する**</span><span class="sxs-lookup"><span data-stu-id="6fd42-128">**Using Windows PowerShell**</span></span>
  
- <span data-ttu-id="6fd42-129">メールの送信を無効にするには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="6fd42-129">Run the following to disable sending emails:</span></span> 
    
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

    <span data-ttu-id="6fd42-130">このコマンドレットについては、「 [Set--](https://go.microsoft.com/fwlink/?LinkId=715757)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6fd42-130">For help with this cmdlet, see [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757).</span></span>
    
## <a name="what-else-should-you-know"></a><span data-ttu-id="6fd42-131">その他の情報</span><span class="sxs-lookup"><span data-stu-id="6fd42-131">What else should you know?</span></span>

- <span data-ttu-id="6fd42-132">自動メールを無効にしても、Skype for Business 管理センターを使って、会議 ID と電話番号を使ってメールを手動で送信することができます。</span><span class="sxs-lookup"><span data-stu-id="6fd42-132">When automatic emails are disabled, you can still manually trigger sending an email with the conference ID and phone number using the Skype for Business admin center.</span></span> <span data-ttu-id="6fd42-133">ただし、この場合、PIN は含まれません。</span><span class="sxs-lookup"><span data-stu-id="6fd42-133">However, if you do this, the PIN won't be included.</span></span> <span data-ttu-id="6fd42-134">電話会議の PIN をリセットして、メールの送信を無効にする場合は、別の方法でユーザーに送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6fd42-134">If you want to reset the audio conferencing PIN and sending emails is disabled, you will need to send it to the user in another way.</span></span>
    
- <span data-ttu-id="6fd42-135">Skype for Business 管理センターまたは Windows PowerShell を使用して、ユーザーへのメールの送信を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="6fd42-135">Sending email to your users can be disabled using the Skype for Business admin center or the Windows PowerShell.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="6fd42-136">Windows PowerShell での管理方法について</span><span class="sxs-lookup"><span data-stu-id="6fd42-136">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="6fd42-137">これらのコマンドレットを使用して、時間を節約したり、自動化したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="6fd42-137">You can use these cmdlets to save time or automate this.</span></span>
    
  - [<span data-ttu-id="6fd42-138">Get--</span><span class="sxs-lookup"><span data-stu-id="6fd42-138">Get-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715760)
    
  - [<span data-ttu-id="6fd42-139">Remove--</span><span class="sxs-lookup"><span data-stu-id="6fd42-139">Remove-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715759)
    
  - [<span data-ttu-id="6fd42-140">Get-CsOnlineDialinConferencingTenantConfiguration</span><span class="sxs-lookup"><span data-stu-id="6fd42-140">Get-CsOnlineDialinConferencingTenantConfiguration</span></span>](https://go.microsoft.com/fwlink/?LinkId=715758)
    
  - [<span data-ttu-id="6fd42-141">Get--</span><span class="sxs-lookup"><span data-stu-id="6fd42-141">Get-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715760)
    
- <span data-ttu-id="6fd42-p104">Windows PowerShell で行うのは、ユーザーを管理し、ユーザーに何を許可して何を禁止するかを管理することです。Windows PowerShell を利用すると、Office 365 の管理を 1 か所で行うことができるので、複数のタスクを担当する管理者の日常業務を単純化できます。Windows PowerShell の使用を開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6fd42-p104">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="6fd42-145">Office 365 PowerShell を使用する必要がある理由</span><span class="sxs-lookup"><span data-stu-id="6fd42-145">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="6fd42-146">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="6fd42-146">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="6fd42-147">Windows PowerShell には、Microsoft 365 管理センターを使用する場合にのみ、速度、シンプルさ、生産性を向上させるための多くの利点があります。たとえば、複数のユーザーに対して同時に設定を変更する場合です。</span><span class="sxs-lookup"><span data-stu-id="6fd42-147">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="6fd42-148">次のトピックで、これらの利点を説明します。</span><span class="sxs-lookup"><span data-stu-id="6fd42-148">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="6fd42-149">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="6fd42-149">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="6fd42-150">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="6fd42-150">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="6fd42-151">Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行</span><span class="sxs-lookup"><span data-stu-id="6fd42-151">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="6fd42-p106">Skype for Business Online 用の Windows PowerShell モジュールがあれば、Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成できます。このモジュールは、64 ビット版のコンピューターでのみサポートされており、「[Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688)」の Microsoft ダウンロード センターからダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="6fd42-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="6fd42-154">関連トピック</span><span class="sxs-lookup"><span data-stu-id="6fd42-154">Related topics</span></span>

[<span data-ttu-id="6fd42-155">電話会議の設定が変更されたときにユーザーに送信されるメール</span><span class="sxs-lookup"><span data-stu-id="6fd42-155">Emails sent to users when their Audio Conferencing settings change</span></span>](emails-sent-to-users-when-their-settings-change.md)

[<span data-ttu-id="6fd42-156">電話会議の情報が記載されたメールをユーザーに送信する</span><span class="sxs-lookup"><span data-stu-id="6fd42-156">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information.md)


