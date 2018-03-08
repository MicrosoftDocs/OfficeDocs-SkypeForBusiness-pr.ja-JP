---
title: "ダイヤルイン情報を持つユーザーにメールを送信します。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 7440d3e2-1b49-4258-bd2c-79e9072f8c8d
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
description: "ユーザーを電話会議の情報を含む電子メールを送信します。"
ms.openlocfilehash: 7ca0a4f00f3a81cd865d65336a8be5702e620639
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="send-an-email-to-a-user-with-their-audio-conferencing-information"></a><span data-ttu-id="c92e8-103">この情報は、電話会議情報を持つユーザーにメールを送信します。</span><span class="sxs-lookup"><span data-stu-id="c92e8-103">Send an email to a user with their Audio Conferencing information</span></span>

<span data-ttu-id="c92e8-p101">あります Skype for Business または Microsoft チームのユーザーに、電話会議の情報を送信する必要があります。**Skype for Business 管理センター**を使用して、特定のユーザーのプロパティの下の [**会議情報を電子メールで送信する**] をクリックして、これを行うことができます。電子メールを送信する際にそれが含まれて、電話会議の情報がすべてなど。</span><span class="sxs-lookup"><span data-stu-id="c92e8-p101">Sometimes Skype for Business or Microsoft Teams users may need you to send them their Audio Conferencing information. You can do this by using the **Skype for Business admin center** and clicking **Send conference info via email** under the properties for a user. When you send this email, it will contain all of the audio conferencing information, including:</span></span>
  
- <span data-ttu-id="c92e8-107">ユーザーの会議電話またはダイヤルイン電話番号です。</span><span class="sxs-lookup"><span data-stu-id="c92e8-107">The conference phone or dial-in phone number for the user.</span></span>
    
- <span data-ttu-id="c92e8-108">ユーザーの会議 ID</span><span class="sxs-lookup"><span data-stu-id="c92e8-108">The user's conference ID.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c92e8-p102">静的な Id は、組織内のユーザーをランダムな番号を保存したくない場合に使用します。特定の番号を選択したり、覚えやすいものを使用することができます。動的会議 Id を使用する場合各会議ユーザーのスケジュールが取得割り当て会議の一意の id。場合は、割り当てる静的会議 Id、[ここ](using-audio-conferencing-dynamic-ids-in-your-organization.md)ではなく動的します。</span><span class="sxs-lookup"><span data-stu-id="c92e8-p102">Static IDs are used when people in your organization don't want to remember a random number; they can select a certain number or use one that's easy to remember. When dynamic conference IDs are used, each meeting that a user schedules will get assigned a unique conference ID. If you want to assign dynamic rather than static conference IDs, [go here](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span></span> 
  
<span data-ttu-id="c92e8-112">送信されたメールの例を示します。</span><span class="sxs-lookup"><span data-stu-id="c92e8-112">Here is an example of the email that is sent:</span></span>
  
![ダイヤルイン会議メール](../images/audio-conferencing-info.png)
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="c92e8-114">ユーザーに電話会議の情報を含む電子メールを送信します。</span><span class="sxs-lookup"><span data-stu-id="c92e8-114">Send an email with audio conferencing information to a user</span></span>

1. <span data-ttu-id="c92e8-115">職場または学校のアカウントで Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="c92e8-115">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="c92e8-116">**Office 365 管理センター**に移動 > **Skype for Business**の場合は、左のナビゲーションで [**電話会議**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c92e8-116">Go to the **Office 365 admin center** > **Skype for Business**, and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="c92e8-117">**ユーザー**] をクリックし、[ユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="c92e8-117">Click **Users**, and then select the user.</span></span>
    
4. <span data-ttu-id="c92e8-118">操作ウィンドウで、**会議情報を電子メールで送信する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c92e8-118">In the Action pane, click **Send conference info via email**.</span></span>
    
> [!TIP]
> <span data-ttu-id="c92e8-119">メールを送信できるユーザーに電話会議の設定を含む、ユーザーのプロパティを編集して、**電話会議**をクリックして、 > **会議情報を電子メールで送信します**。</span><span class="sxs-lookup"><span data-stu-id="c92e8-119">You can also send email to the user with the audio conferencing settings by editing the user's properties and then clicking **Audio conferencing** > **Send conference info via email**.</span></span> 
  
## <a name="what-else-should-you-know-about-this-email"></a><span data-ttu-id="c92e8-120">このメールについて他を把握してする必要がありますか。</span><span class="sxs-lookup"><span data-stu-id="c92e8-120">What else should you know about this email?</span></span>

- <span data-ttu-id="c92e8-121">複数のメールに送信された、組織のユーザーが有効な後に電話会議があります。</span><span class="sxs-lookup"><span data-stu-id="c92e8-121">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="c92e8-122">**電話会議**のライセンスが割り当てられているとします。</span><span class="sxs-lookup"><span data-stu-id="c92e8-122">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="c92e8-123">手動でをリセットすると、ユーザーの電話会議暗証番号 (pin)。</span><span class="sxs-lookup"><span data-stu-id="c92e8-123">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="c92e8-124">ユーザーの会議 ID を手動でリセットする場合</span><span class="sxs-lookup"><span data-stu-id="c92e8-124">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="c92e8-125">**電話会議**のライセンスは、それらから削除されます。</span><span class="sxs-lookup"><span data-stu-id="c92e8-125">When an **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="c92e8-126">ユーザーの電話会議プロバイダーが変更された場合 Microsoft から別のプロバイダー [**なし]**にします。</span><span class="sxs-lookup"><span data-stu-id="c92e8-126">When the audio conferencing provider for a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="c92e8-127">ユーザーの電話会議プロバイダーが Microsoft に変更された場合。</span><span class="sxs-lookup"><span data-stu-id="c92e8-127">When the audio conferencing provider for a user is changed to Microsoft.</span></span>
    
- <span data-ttu-id="c92e8-p103">既定では、Office 365 からのメールの送信者になりますが、メール アドレスを変更し、Windows PowerShell と[セット CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=708983)コマンドレットを使用して名前を表示することができます。ユーザーにメールを送信するメール アドレスを変更するには、次の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="c92e8-p103">By default, the sender of the emails will be from Office 365, but you can change the email address and display name by using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=708983) cmdlet. To make changes to the email address that is sending the email to users, you must:</span></span>
    
  - <span data-ttu-id="c92e8-130">SendEmailFromAddress パラメーターには、メール アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="c92e8-130">Enter the email address in the SendEmailFromAddress parameter.</span></span>
    
  - <span data-ttu-id="c92e8-131">SendEmailOverride パラメーターが True に設定します。</span><span class="sxs-lookup"><span data-stu-id="c92e8-131">Set the SendEmailOverride parameter to True.</span></span>
    
  - <span data-ttu-id="c92e8-132">SendEmailFromDisplayName パラメーターには、メールの表示名を入力します。</span><span class="sxs-lookup"><span data-stu-id="c92e8-132">Enter the email display name in the SendEmailFromDisplayName parameter.</span></span>
    
     `Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"`
    
    > [!NOTE]
    > <span data-ttu-id="c92e8-133">メール アドレスの情報を変更する場合は、組織のメールの受信ポリシーが設定されているユーザー設定のメール アドレスからメールを許可するかどうかを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c92e8-133">If you want to change the email address information, you need to make sure that the inbound email policies of your organization allow emails that come from the custom email address that is set.</span></span> 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="c92e8-134">Windows PowerShell で管理する方法を知りたいとしていますか。</span><span class="sxs-lookup"><span data-stu-id="c92e8-134">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="c92e8-135">時間を節約し、自動化したりには、[セット CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 )コマンドレットを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="c92e8-135">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) cmdlet.</span></span>
    
    <span data-ttu-id="c92e8-136">電話会議の情報をユーザーにメールを送信するのには次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c92e8-136">To send an email to the user with their audio conferencing information, run the following:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com  -SendEmail
  ```

-  <span data-ttu-id="c92e8-p104">Windows PowerShell する際に、Skype for Business Online はすべてを管理するユーザーとユーザーの許可または使用できません。Windows PowerShell で複数のタスクを実行するがある場合、日常業務を簡素化する管理の 1 つのポイントを使用して Office 365 を管理できます。Windows PowerShell で開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c92e8-p104">When it comes to Windows PowerShell, Skype for Business Online is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="c92e8-140">Office 365 PowerShell を使用する必要がある理由</span><span class="sxs-lookup"><span data-stu-id="c92e8-140">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="c92e8-141">Windows PowerShell で Office 365 を管理する最善の方法</span><span class="sxs-lookup"><span data-stu-id="c92e8-141">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="c92e8-p105">Windows PowerShell では多くの利点速度、わかりやすいように、および生産性でのみ実行しようとする設定の変更、多くのユーザーに一度になど、Office 365 管理センターを使用します。次のトピックでこれらの利点について学習します。</span><span class="sxs-lookup"><span data-stu-id="c92e8-p105">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="c92e8-144">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="c92e8-144">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [<span data-ttu-id="c92e8-145">Windows PowerShell を使用して、Skype for Business Online の管理するには</span><span class="sxs-lookup"><span data-stu-id="c92e8-145">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="c92e8-146">Windows PowerShell を使用して、共通の Skype for Business Online の管理タスクを実行するには</span><span class="sxs-lookup"><span data-stu-id="c92e8-146">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="c92e8-p106">Skype for Business Online 用の Windows PowerShell モジュールを使用すると、Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成することができます。このモジュールでは、64 ビット コンピューター以外では、Microsoft ダウンロード センターからダウンロードできます[Skype for Business Online 用の Windows PowerShell モジュール](https://go.microsoft.com/fwlink/?LinkId=294688)。</span><span class="sxs-lookup"><span data-stu-id="c92e8-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="c92e8-149">関連トピック</span><span class="sxs-lookup"><span data-stu-id="c92e8-149">Related topics</span></span>

[<span data-ttu-id="c92e8-150">Skype for Business とチームの Microsoft の音声会議をセットアップする設定します。</span><span class="sxs-lookup"><span data-stu-id="c92e8-150">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](set-up-audio-conferencing.md)
