---
title: Skype for Business Online で電話会議情報を記載した電子メールをユーザーに送信する
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 7440d3e2-1b49-4258-bd2c-79e9072f8c8d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: Skype for Business Online で電話会議情報を記載した電子メールをユーザーに送信します。
ms.openlocfilehash: 7b32608eae4fa5bb0d7f5b1eafbf49825ee937ad
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23849977"
---
# <a name="send-an-email-to-a-user-with-their-audio-conferencing-information-in-skype-for-business-online"></a><span data-ttu-id="1de94-103">Skype for Business Online で電話会議情報を記載した電子メールをユーザーに送信する</span><span class="sxs-lookup"><span data-stu-id="1de94-103">Send an email to a user with their Audio Conferencing information</span></span>

> [!Note]
> <span data-ttu-id="1de94-104">Microsoft Teams でユーザーに電話会議情報を送信する方法については、「[電話会議の情報が記載されたメールをユーザーに送信する](/MicrosoftTeams/send-an-email-to-a-user-with-their-dial-in-information-in-teams)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1de94-104">For information about sending Audio Conferencing information to users in Microsoft Teams, see [Send an email to a user with their Audio Conferencing information in Microsoft Teasms](/MicrosoftTeams/send-an-email-to-a-user-with-their-dial-in-information-in-teams).</span></span>

<span data-ttu-id="1de94-105">Skype for Business ユーザーに電話会議情報を送付しなくてはならない場合があります。</span><span class="sxs-lookup"><span data-stu-id="1de94-105">Sometimes Skype for Business users may need you to send them their Audio Conferencing information.</span></span> <span data-ttu-id="1de94-106">そのような場合は、**Skype for Business 管理センター**で、ユーザーのプロパティの **[電話会議情報をメールで送信]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1de94-106">You can do this by using the Skype for Business admin center and clicking **Send conference info via email** under the dial-in properties for a user.</span></span> <span data-ttu-id="1de94-107">送信する電子メールには、次のような電話会議情報がすべて含まれています。</span><span class="sxs-lookup"><span data-stu-id="1de94-107">When you send this email, it will contain all of the dial-in information including:</span></span>
  
- <span data-ttu-id="1de94-108">ユーザー用の会議の電話番号またはダイヤルイン電話番号。</span><span class="sxs-lookup"><span data-stu-id="1de94-108">The conference phone or dial-in phone number for the user.</span></span>
    
- <span data-ttu-id="1de94-109">ユーザーの会議 ID。</span><span class="sxs-lookup"><span data-stu-id="1de94-109">The user's conference ID.</span></span>
    
   
<span data-ttu-id="1de94-110">以下は送信される電子メールの例です。</span><span class="sxs-lookup"><span data-stu-id="1de94-110">Here is an example of the email that is sent to users that are enabled for dial-in conferencing:</span></span>
  
![ダイヤルイン会議の電子メール](../images/audio-conferencing-info.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="1de94-112">電話会議の情報が記載された電子メールをユーザーに送信する</span><span class="sxs-lookup"><span data-stu-id="1de94-112">Send an email with Audio Conferencing information to a user</span></span>

1. <span data-ttu-id="1de94-113">左側のナビゲーションで、**[ユーザー]** をクリックして、出席可能なユーザーの一覧からユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="1de94-113">In the left navigation of the **Office 365 admin center, go to UsersActive users**, and then select the user or users from the list of available users.</span></span>

2. <span data-ttu-id="1de94-114">ページの上部で、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1de94-114">At the top of the page, choose **Users**.</span></span>

3. <span data-ttu-id="1de94-115">[**電話会議**] の [**電話会議情報をメールで送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1de94-115">Under **Audio Conferencing**, click **Send conference info in email**.</span></span>

1. <span data-ttu-id="1de94-116">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="1de94-116">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="1de94-117"> *\*[Office 365 管理センター]**  > *\*[Skype for Business]** と選び、左側のナビゲーションで [*\*電話会議*\*] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1de94-117">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="1de94-118">[**ユーザー**] をクリックし、ユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="1de94-118">Click on **Dial-in users** and then select the user.</span></span>
    
4. <span data-ttu-id="1de94-119">操作ウィンドウで、[**電話会議情報をメールで送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1de94-119">In the Action pane, click **Send conference info via email**.</span></span>
    
> [!TIP]
> <span data-ttu-id="1de94-120">ユーザーのプロパティを編集し、[**電話会議**]  >  「**電話会議情報をメールで送信**」とクリックして、電話会議の設定が記載された電子メールをユーザーに送信することもできます。</span><span class="sxs-lookup"><span data-stu-id="1de94-120">You can also send email to the user with the audio conferencing settings, by going to the user's audio conferencing properties and clicking Send conference info via email.</span></span> 

## <a name="what-else-should-you-know-about-this-email"></a><span data-ttu-id="1de94-121">電子メールについてのその他の必須情報</span><span class="sxs-lookup"><span data-stu-id="1de94-121">What else should you know about this email?</span></span>

- <span data-ttu-id="1de94-122">組織のユーザーが電話会議を使用できるようになると、以下のような場合に電子メールが送信されます。</span><span class="sxs-lookup"><span data-stu-id="1de94-122">There are several emails that are sent to users in your organization after they are enabled for dial-in conferencing:</span></span>
    
  - <span data-ttu-id="1de94-123">**電話会議** のライセンスがユーザーに割り当てられた場合。</span><span class="sxs-lookup"><span data-stu-id="1de94-123">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="1de94-124">ユーザーの電話会議の PIN を手動でリセットした場合。</span><span class="sxs-lookup"><span data-stu-id="1de94-124">When you manually reset the user's dial-in conferencing PIN.</span></span>
    
  - <span data-ttu-id="1de94-125">ユーザーの会議 ID を手動でリセットした場合。</span><span class="sxs-lookup"><span data-stu-id="1de94-125">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="1de94-126">**電話会議** のライセンスがユーザーから削除された場合。</span><span class="sxs-lookup"><span data-stu-id="1de94-126">When an **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="1de94-127">ユーザーの電話会議プロバイダが Microsoft から別のプロバイダ、または [**なし**] に変更された場合。</span><span class="sxs-lookup"><span data-stu-id="1de94-127">When the dial-in conferencing provider for a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="1de94-128">ユーザーの電話会議プロバイダが Microsoft に変更された場合。</span><span class="sxs-lookup"><span data-stu-id="1de94-128">When the dial-in conferencing provider for a user is changed to Microsoft.</span></span>
    
- <span data-ttu-id="1de94-129">既定では、メールの差出人は Office 365 ですが、Windows PowerShell と [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=708983) コマンドレットを使って、メール アドレスと表示名を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="1de94-129">By default, the sender of the emails will be from Office 365 but you can change the email address and display name using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=708983) cmdlet.</span></span> <span data-ttu-id="1de94-130">ユーザーへの電子メールの送信元となるメール アドレスに変更を加えるには、以下を実行しなくてはなりません。</span><span class="sxs-lookup"><span data-stu-id="1de94-130">To make changes to the email address that is sending the email to the users, you must:</span></span>
    
  - <span data-ttu-id="1de94-131">SendEmailFromAddress パラメータにメール アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="1de94-131">Enter the email address in the SendEmailFromAddress parameter.</span></span>
    
  - <span data-ttu-id="1de94-132">SendEmailOverride パラメータを True に設定します。</span><span class="sxs-lookup"><span data-stu-id="1de94-132">Set the SendEmailOverride parameter to True.</span></span>
    
  - <span data-ttu-id="1de94-133">SendEmailFromDisplayName パラメーターにメールの表示名を入力する</span><span class="sxs-lookup"><span data-stu-id="1de94-133">Enter the email display name in the  SendEmailFromDisplayName parameter.</span></span>
    
     `Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"`
    
    > [!NOTE]
    > <span data-ttu-id="1de94-134">メール アドレス情報を変更する場合、設定した独自のメール アドレスから送信されるメールが、組織の受信メール ポリシーで許可されることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1de94-134">If you want to change the email address information, you need to make sure that the inbound email policies of your organization allow emails that come from the custom email address that is set.</span></span> 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="1de94-135">Windows PowerShell で管理する方法</span><span class="sxs-lookup"><span data-stu-id="1de94-135">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="1de94-136">時間を節約したり、自動化したりするには、[Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) コマンドレットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="1de94-136">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) cmdlet.</span></span>
    
    <span data-ttu-id="1de94-137">ユーザーに電話会議情報が記載されたメールを送信するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="1de94-137">To send an email to the user with their dial-in conferencing information, run the following:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com  -SendEmail
  ```

-  <span data-ttu-id="1de94-p103">Windows PowerShell の場合、Skype for Business Online はユーザーの管理と、ユーザーが許可されている操作や許可されていない操作の管理に使います。Windows PowerShell により、単一の管理ポイントを使って Office 365 を管理でき、複数の作業を実行する必要があるときに日常業務を合理化できます。Windows PowerShell を使い始めるには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1de94-p103">When it comes to Windows PowerShell, Skype for Business Online is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="1de94-141">Windows PowerShell で Office 365 を管理する</span><span class="sxs-lookup"><span data-stu-id="1de94-141">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="1de94-142">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="1de94-142">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="1de94-p104">多くのユーザーの設定を同時に変更するときなどは、Office 365 管理センターのみを使用するよりも、Windows PowerShell の方に、速度、わかりやすさ、生産性の点で多くのメリットがあります。 次のトピックで、これらの利点を説明します。</span><span class="sxs-lookup"><span data-stu-id="1de94-p104">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="1de94-145">Windows PowerShell と Lync Online の概要</span><span class="sxs-lookup"><span data-stu-id="1de94-145">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [<span data-ttu-id="1de94-146">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="1de94-146">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="1de94-147">クイック リファレンス: Windows PowerShell を使用した一般的な Lync Online の管理タスクの実行</span><span class="sxs-lookup"><span data-stu-id="1de94-147">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="1de94-p105">Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行[](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="1de94-p105">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="1de94-150">関連トピック</span><span class="sxs-lookup"><span data-stu-id="1de94-150">Related topics</span></span>

[<span data-ttu-id="1de94-151">Office 365 での電話会議を使用または購入する</span><span class="sxs-lookup"><span data-stu-id="1de94-151">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
