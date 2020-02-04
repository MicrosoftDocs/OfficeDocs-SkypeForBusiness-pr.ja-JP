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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: Skype for Business Online で電話会議情報を記載した電子メールをユーザーに送信します。
ms.openlocfilehash: 78ce937bd9aa3bcdab8c860ce261c419af7cc768
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41680404"
---
# <a name="send-an-email-to-a-user-with-their-audio-conferencing-information-in-skype-for-business-online"></a><span data-ttu-id="c5cd6-103">Skype for Business Online の電話会議情報を使って、ユーザーにメールを送信する</span><span class="sxs-lookup"><span data-stu-id="c5cd6-103">Send an email to a user with their Audio Conferencing information in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="c5cd6-104">Microsoft Teams でユーザーに電話会議情報を送信する方法については、「[電話会議の情報が記載されたメールをユーザーに送信する](/MicrosoftTeams/send-an-email-to-a-user-with-their-dial-in-information-in-teams)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c5cd6-104">For information about sending Audio Conferencing information to users in Microsoft Teams, see [Send an email to a user with their Audio Conferencing information in Microsoft Teasms](/MicrosoftTeams/send-an-email-to-a-user-with-their-dial-in-information-in-teams).</span></span>

<span data-ttu-id="c5cd6-105">Skype for Business ユーザーに電話会議情報を送付しなくてはならない場合があります。</span><span class="sxs-lookup"><span data-stu-id="c5cd6-105">Sometimes Skype for Business users may need you to send them their Audio Conferencing information.</span></span> <span data-ttu-id="c5cd6-106">これを行うには、 **Skype For business 管理センター**を使用し、ユーザーのプロパティの下にある [**会議情報をメールで送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c5cd6-106">You can do this by using the **Skype for Business admin center** and clicking **Send conference info via email** under the properties for a user.</span></span> <span data-ttu-id="c5cd6-107">このメールを送信すると、次のようなすべての電話会議情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="c5cd6-107">When you send this email, it will contain all of the audio conferencing information, including:</span></span>
  
- <span data-ttu-id="c5cd6-108">ユーザー用の会議の電話番号またはダイヤルイン電話番号。</span><span class="sxs-lookup"><span data-stu-id="c5cd6-108">The conference phone or dial-in phone number for the user.</span></span>
    
- <span data-ttu-id="c5cd6-109">ユーザーの会議 ID。</span><span class="sxs-lookup"><span data-stu-id="c5cd6-109">The user's conference ID.</span></span>
    
   
<span data-ttu-id="c5cd6-110">送信されるメールの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c5cd6-110">Here is an example of the email that is sent:</span></span>
  
![ダイヤルイン会議のメール](../images/audio-conferencing-info.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="c5cd6-112">電話会議の情報が含まれるメールをユーザーに送信する</span><span class="sxs-lookup"><span data-stu-id="c5cd6-112">Send an email with audio conferencing information to a user</span></span>

1. <span data-ttu-id="c5cd6-113">左側のナビゲーションで、[**ユーザー**] をクリックしてから、空いているユーザーのリストからユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="c5cd6-113">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="c5cd6-114">ページの上部にある [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c5cd6-114">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="c5cd6-115">[**電話会議**] の [**電話会議情報をメールで送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c5cd6-115">Under **Audio Conferencing**, click **Send conference info in email**.</span></span>

1. <span data-ttu-id="c5cd6-116">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="c5cd6-116">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="c5cd6-117">**Skype For business**> 管理センターに移動し、左側のナビゲーションで [**電話会議**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c5cd6-117">Go to the admin center > **Skype for Business**, and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="c5cd6-118">[**ユーザー**] をクリックし、ユーザーを選びます。</span><span class="sxs-lookup"><span data-stu-id="c5cd6-118">Click **Users**, and then select the user.</span></span>
    
4. <span data-ttu-id="c5cd6-119">操作ウィンドウで、[ **電話会議情報をメールで送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c5cd6-119">In the Action pane, click **Send conference info via email**.</span></span>
    
> [!TIP]
> <span data-ttu-id="c5cd6-120">電話会議の設定を使用してユーザーにメールを送信することもできます。そのためには、ユーザーのプロパティを編集してから、[**電話\*\*\*\*会議** > ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c5cd6-120">You can also send email to the user with the audio conferencing settings by editing the user's properties and then clicking **Audio conferencing** > **Send conference info via email**.</span></span> 

## <a name="what-else-should-you-know-about-this-email"></a><span data-ttu-id="c5cd6-121">このようなメールについて知っておくべきその他のこと</span><span class="sxs-lookup"><span data-stu-id="c5cd6-121">What else should you know about this email?</span></span>

- <span data-ttu-id="c5cd6-122">電話会議を有効にした後、組織内のユーザーに送信されるメールが複数あります。</span><span class="sxs-lookup"><span data-stu-id="c5cd6-122">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="c5cd6-123">**電話会議** のライセンスがユーザーに割り当てられた場合。</span><span class="sxs-lookup"><span data-stu-id="c5cd6-123">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="c5cd6-124">ユーザーの電話会議の PIN を手動でリセットした場合。</span><span class="sxs-lookup"><span data-stu-id="c5cd6-124">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="c5cd6-125">ユーザーの会議 ID を手動でリセットした場合。</span><span class="sxs-lookup"><span data-stu-id="c5cd6-125">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="c5cd6-126">**電話会議** のライセンスがユーザーから削除された場合。</span><span class="sxs-lookup"><span data-stu-id="c5cd6-126">When an **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="c5cd6-127">ユーザーの電話会議プロバイダーが Microsoft から別のプロバイダーまたは **[なし**] に変更された場合。</span><span class="sxs-lookup"><span data-stu-id="c5cd6-127">When the audio conferencing provider for a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="c5cd6-128">ユーザーの電話会議プロバイダーが Microsoft に変更された場合。</span><span class="sxs-lookup"><span data-stu-id="c5cd6-128">When the audio conferencing provider for a user is changed to Microsoft.</span></span>
    
- <span data-ttu-id="c5cd6-129">既定では、メールの送信者は Office 365 から送信されますが、メールアドレスと表示名を変更するには、Windows PowerShell と[-](https://go.microsoft.com/fwlink/?LinkId=708983)コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="c5cd6-129">By default, the sender of the emails will be from Office 365, but you can change the email address and display name by using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=708983) cmdlet.</span></span> <span data-ttu-id="c5cd6-130">ユーザーにメールを送信するメールアドレスを変更するには、次のことを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="c5cd6-130">To make changes to the email address that is sending the email to users, you must:</span></span>
    
  - <span data-ttu-id="c5cd6-131">SendEmailFromAddress パラメーターにメールアドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="c5cd6-131">Enter the email address in the SendEmailFromAddress parameter.</span></span>
    
  - <span data-ttu-id="c5cd6-132">メール アドレス情報を変更したい場合は、カスタムのメール アドレスから送信されるメールが、組織の受信メール ポリシーで許可されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c5cd6-132">Set the SendEmailOverride parameter to True.</span></span>
    
  - <span data-ttu-id="c5cd6-133">SendEmailFromDisplayName パラメーターにメールの表示名を入力します。</span><span class="sxs-lookup"><span data-stu-id="c5cd6-133">Enter the email display name in the SendEmailFromDisplayName parameter.</span></span>
    
     `Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"`
    
    > [!NOTE]
    > <span data-ttu-id="c5cd6-134">メール アドレス情報を変更する場合、設定した独自のメール アドレスから送信されるメールが、組織の受信メール ポリシーで許可されることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c5cd6-134">If you want to change the email address information, you need to make sure that the inbound email policies of your organization allow emails that come from the custom email address that is set.</span></span> 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="c5cd6-135">Windows PowerShell での管理方法について</span><span class="sxs-lookup"><span data-stu-id="c5cd6-135">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="c5cd6-136">時間を節約したり、自動化したりするには、[Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) コマンドレットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="c5cd6-136">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) cmdlet.</span></span>
    
    <span data-ttu-id="c5cd6-137">電話会議の情報を使用してユーザーにメールを送信するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="c5cd6-137">To send an email to the user with their audio conferencing information, run the following:</span></span>
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com  -SendEmail
  ```

- <span data-ttu-id="c5cd6-p103">Windows PowerShell の場合、Skype for Business Online はユーザーの管理と、ユーザーが許可されている操作や許可されていない操作の管理に使います。Windows PowerShell により、単一の管理ポイントを使って Office 365 を管理でき、複数の作業を実行する必要があるときに日常業務を合理化できます。Windows PowerShell を使い始めるには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c5cd6-p103">When it comes to Windows PowerShell, Skype for Business Online is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="c5cd6-141">Office 365 PowerShell を使用する必要がある理由</span><span class="sxs-lookup"><span data-stu-id="c5cd6-141">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="c5cd6-142">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="c5cd6-142">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="c5cd6-143">Windows PowerShell には、Microsoft 365 管理センターを使用する場合にのみ、速度、シンプルさ、生産性を向上させるための多くの利点があります。たとえば、複数のユーザーに対して同時に設定を変更する場合です。</span><span class="sxs-lookup"><span data-stu-id="c5cd6-143">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="c5cd6-144">次のトピックで、これらの利点を説明します。</span><span class="sxs-lookup"><span data-stu-id="c5cd6-144">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="c5cd6-145">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="c5cd6-145">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [<span data-ttu-id="c5cd6-146">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="c5cd6-146">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="c5cd6-147">Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行</span><span class="sxs-lookup"><span data-stu-id="c5cd6-147">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="c5cd6-p105">Skype for Business Online 用の Windows PowerShell モジュールがあれば、Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成できます。このモジュールは、64 ビット版のコンピューターでのみサポートされており、「[Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688)」の Microsoft ダウンロード センターからダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="c5cd6-p105">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="c5cd6-150">関連項目</span><span class="sxs-lookup"><span data-stu-id="c5cd6-150">Related topics</span></span>

[<span data-ttu-id="c5cd6-151">Office 365 での電話会議を試用または購入する</span><span class="sxs-lookup"><span data-stu-id="c5cd6-151">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
