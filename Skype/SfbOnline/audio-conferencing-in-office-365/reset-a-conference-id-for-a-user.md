---
title: ユーザーの会議 ID をリセットする
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
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
description: "Learn the steps to reset a user's meeting conference ID, and get links to meeting update and migration tools. "
ms.openlocfilehash: 077b35169b3829262c38c9ebc44451aba8bd110d
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2018
---
# <a name="reset-a-conference-id-for-a-user"></a><span data-ttu-id="aadcb-103">ユーザーの会議 ID をリセットする</span><span class="sxs-lookup"><span data-stu-id="aadcb-103">Reset a conference ID for a user</span></span>

<span data-ttu-id="aadcb-104">組織は、会議 Id を動的に有効になっていない、静的な会議 ID はプロバイダーと Microsoft を使用してオーディオ会議のため、Skype のビジネスまたはマイクロソフトのチームのユーザーが有効になっているときに自動的に作成します。</span><span class="sxs-lookup"><span data-stu-id="aadcb-104">When your organizations hasn't been enabled for dynamic conference IDs, a static conference ID is automatically created when a Skype for Business or Microsoft Teams user is enabled for Audio Conferencing using Microsoft as the provider.</span></span> <span data-ttu-id="aadcb-105">この会議 ID では、会議出席依頼と会議へのコールを呼び出し元で使用できるダイヤルインの電話番号の下に含まれています。</span><span class="sxs-lookup"><span data-stu-id="aadcb-105">This conference ID is included at the bottom of meeting invitations along with the dial-in phone numbers that can be used by callers to call in to a meeting.</span></span> <span data-ttu-id="aadcb-106">ユーザーは、電話番号をダイヤルするとき、会議のための自動応答は、会議に出席することができますので、この会議 ID を入力するのには呼び出し元を求められます。</span><span class="sxs-lookup"><span data-stu-id="aadcb-106">When the user dials the phone number, the auto attendant for the meeting will ask the caller to enter this conference ID so they can attend the meeting.</span></span>
  
> [!NOTE]
> <span data-ttu-id="aadcb-107">会議プロバイダーがマイクロソフトの場合は、ユーザーの会議 Id が既定で動的なだけに設定されます。</span><span class="sxs-lookup"><span data-stu-id="aadcb-107">If your conferencing provider is Microsoft, your users' conference IDs are set to Dynamic Only by default.</span></span> <span data-ttu-id="aadcb-108">残念ながら、ビジネス管理センターまたは Windows Powershell を使用して Skype でそれを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="aadcb-108">Unfortunately, you won't be able to change it in the Skype for Business Admin Center or using Windows Powershell.</span></span> <span data-ttu-id="aadcb-109">マイクロソフト サポートに連絡する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aadcb-109">You will have to contact Microsoft support.</span></span> 
  
<span data-ttu-id="aadcb-110">Skype for Business 管理センターおよび Windows PowerShell を使用すると、ユーザーの会議 ID を表示、変更、リセットすることができます。</span><span class="sxs-lookup"><span data-stu-id="aadcb-110">Static IDs are used when people in your organization don't want to remember a random number; they can select a certain number or use one that's easy to remember.</span></span> <span data-ttu-id="aadcb-111">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="aadcb-111">When dynamic conference IDs are used, each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="aadcb-112">場合に割り当てる静的な会議 Id を[ここ](using-audio-conferencing-dynamic-ids-in-your-organization.md)にではなく動的です。</span><span class="sxs-lookup"><span data-stu-id="aadcb-112">If you want to assign dynamic rather than static conference IDs, [go here](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span></span>
  
<span data-ttu-id="aadcb-113">会議 Id はのみ自動的に設定だけ Skype 音声会議を有効にするビジネスおよびマイクロソフトのチームのユーザーの Microsoft を使用して、オーディオ会議プロバイダーとしてです。</span><span class="sxs-lookup"><span data-stu-id="aadcb-113">Conference IDs are only automatically set only for Skype for Business and Microsoft Teams users enabled for Audio Conferencing using Microsoft as their audio conferencing provider.</span></span> <span data-ttu-id="aadcb-114">サード ・ パーティ製の音声会議プロバイダー (ACP) を使用してユーザーのための会議 ID をリセットする場合は、[プロパティ] ページで、ユーザーの会議 ID を手動で入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aadcb-114">If you need to reset a conference ID for a user who is using a third-party audio conferencing provider (ACP), you will need to manually enter a conference ID on the properties page for the user.</span></span>
  
## <a name="resetting-the-conference-id-for-a-user"></a><span data-ttu-id="aadcb-115">ユーザーの会議 ID をリセットします。</span><span class="sxs-lookup"><span data-stu-id="aadcb-115">Resetting the conference ID for a user</span></span>

<span data-ttu-id="aadcb-116">**ビジネス管理センターは、マイクロソフトのチームと Skype を使用してください。**</span><span class="sxs-lookup"><span data-stu-id="aadcb-116">**Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="aadcb-117">左側のナビゲーションでは、**ユーザー**] をクリックしてで使用可能なユーザーの一覧からユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="aadcb-117">In the left navigation, click **Users**, and then select the user from teh list of available users.</span></span>

2. <span data-ttu-id="aadcb-118">ページの上部で、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aadcb-118">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="aadcb-119">**会議ブリッジ**の横にあるメニューをクリックし、ドロップダウン リストに**会議 id をリセット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aadcb-119">Click the menu next to **Conference Bridges**, and then click **Reset conference id** in the drop-down list.</span></span>

2. <span data-ttu-id="aadcb-120">**会議 id のリセット**] ウィンドウで、 **[ok]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aadcb-120">In the **Reset conference id** window, click **Ok**.</span></span> <span data-ttu-id="aadcb-121">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="aadcb-121">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span> <span data-ttu-id="aadcb-122">既定では、ユーザーに電子メールが送信されますが、これを無効にできます。</span><span class="sxs-lookup"><span data-stu-id="aadcb-122">By default, emails are sent to users, but this can be turned off.</span></span>   

<span data-ttu-id="aadcb-123">****職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="aadcb-123">**Using the Skype for Business admin center**</span></span>
    
1. <span data-ttu-id="aadcb-124">**ビジネス管理センターの Skype**では、[**電話会議**] をクリックします > **ユーザー**ユーザーを選択し、し、[操作] ウィンドウの [**会議 ID** ] の [**リセット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aadcb-124">In the **Skype for Business admin center**, click **Audio conferencing** > **Users**, select a user, and then in the Action pane under **Conference ID** click **Reset**.</span></span>
    
2. <span data-ttu-id="aadcb-125">A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled.</span><span class="sxs-lookup"><span data-stu-id="aadcb-125">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="aadcb-126">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="aadcb-126">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span> <span data-ttu-id="aadcb-127">既定では、ユーザーに電子メールが送信されますが、これを無効にできます。</span><span class="sxs-lookup"><span data-stu-id="aadcb-127">By default, emails are sent to users, but this can be turned off.</span></span>
    
> [!NOTE]
> <span data-ttu-id="aadcb-p107">会議 ID をリセットすると、新しい会議 ID を記載したメールがユーザーに送信されます。このメールはプライマリ メール アドレスに送信されます。ほとんどの場合は、Office 365 のメールボックスに送信されます。新しい会議 ID、既定のダイヤルイン電話番号、Skype for Business Meeting Update Tool を使って既存の会議を更新する方法がメールに記載されています。</span><span class="sxs-lookup"><span data-stu-id="aadcb-p107">After you reset the conference ID, an email with the new conference ID will be sent to the user. This email will be sent to the primary email address, in many cases, their Office 365 mailbox. The email contains the new conference ID, default dial-in phone number(s) and instructions to use the Skype for Business Meeting Update Tool to update existing meetings.</span></span> 
  
## <a name="what-else-should-i-know"></a><span data-ttu-id="aadcb-131">他に必要な情報はありますか?</span><span class="sxs-lookup"><span data-stu-id="aadcb-131">What else should I know?</span></span>

- <span data-ttu-id="aadcb-132">操作ウィンドウでのユーザーの [**電子メール経由での会議の情報を送信**] をクリックして、会議 ID とダイヤルインの電話番号を含む電子メールでユーザーにすべての会議の情報を送信できます。</span><span class="sxs-lookup"><span data-stu-id="aadcb-132">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking **Send conference info via email** for the user in the Action pane.</span></span> <span data-ttu-id="aadcb-133">PIN は送信されません。</span><span class="sxs-lookup"><span data-stu-id="aadcb-133">It doesn't send the PIN.</span></span>
    
- <span data-ttu-id="aadcb-134">会議 ID が 7 桁の数字を含めるし、ビジネス管理センターまたは Windows PowerShell を使用して、Skype では、その長さを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="aadcb-134">A conference ID will contain 7 digits, and you can't change its length in the Skype for Business admin center or by using Windows PowerShell.</span></span>
    
- <span data-ttu-id="aadcb-135">会議 ID をリセットすると、新しい会議 ID が [ **電話会議 ID**] に一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="aadcb-135">After it has been reset, you can see the new conference ID listed under **Conference ID**.</span></span>
    
- <span data-ttu-id="aadcb-136">[**ユーザー** ] ページで、ユーザーを選択すると、**オーディオ会議**の下にある操作ウィンドウの下部にあるユーザーが電話会議の会議 ID を表示できます。</span><span class="sxs-lookup"><span data-stu-id="aadcb-136">The conference ID for a user for audio conferencing can be viewed at the bottom of the Action pane under **Audio conferencing** when you select the user on the **Users** page.</span></span>
    
- <span data-ttu-id="aadcb-137">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span><span class="sxs-lookup"><span data-stu-id="aadcb-137">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="aadcb-138">The users can use Skype for Business Meeting Migration Tool to update their existing meetings.</span><span class="sxs-lookup"><span data-stu-id="aadcb-138">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="aadcb-139">ユーザーは、ビジネス会議ツールの Skype を使用して、既存の会議を更新します。</span><span class="sxs-lookup"><span data-stu-id="aadcb-139">The users can use Skype for Business Meeting Tool to update their existing meetings.</span></span> <span data-ttu-id="aadcb-140">ダウンロード、インストール、および、Skype をビジネス会議の更新ツールを実行する方法を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aadcb-140">To see how to download, install, and run the Skype for Business Meeting Update Tool, see:</span></span>
    
  - [<span data-ttu-id="aadcb-141">Skype for Business Meeting Update Tool と Lync Meeting Update Tool</span><span class="sxs-lookup"><span data-stu-id="aadcb-141">Meeting Update Tool for Skype for Business and Lync</span></span>](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)
    
  - [<span data-ttu-id="aadcb-142">Skype for Business Online、会議移行ツール (64 ビット)</span><span class="sxs-lookup"><span data-stu-id="aadcb-142">Skype for Business Online, Meeting Migration Tool (64-bit)</span></span>](https://go.microsoft.com/fwlink/?LinkID=626047)
    
  - [<span data-ttu-id="aadcb-143">Skype for Business Online、会議移行ツール (32 ビット)</span><span class="sxs-lookup"><span data-stu-id="aadcb-143">Skype for Business Online, Meeting Migration Tool (32-bit)</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=54079)
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="aadcb-144">Windows PowerShell で管理する方法</span><span class="sxs-lookup"><span data-stu-id="aadcb-144">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="aadcb-p110">Windows PowerShell で行うのは、ユーザーを管理し、ユーザーに何を許可して何を禁止するかを管理することです。Windows PowerShell を利用すると、Office 365 と Skype for Business Online の管理を 1 か所で行うことができるので、複数のタスクを担当する管理者の日常業務を単純化できます。Windows PowerShell の使用を開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="aadcb-p110">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="aadcb-148">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="aadcb-148">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="aadcb-149">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="aadcb-149">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="aadcb-p111">Windows PowerShell には、ただ Office 365 管理センターを使用するだけではなく、速度、単純さ、生産性において多くの利点があります。次のトピックでこれらの利点について説明します。</span><span class="sxs-lookup"><span data-stu-id="aadcb-p111">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="aadcb-152">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="aadcb-152">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="aadcb-153">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="aadcb-153">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="aadcb-154">クイック リファレンス: Windows PowerShell を使用した一般的な Lync Online の管理タスクの実行</span><span class="sxs-lookup"><span data-stu-id="aadcb-154">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="aadcb-155">See also</span><span class="sxs-lookup"><span data-stu-id="aadcb-155">Related topics</span></span>

[<span data-ttu-id="aadcb-156">ユーザーの電話会議の PIN をリセットする</span><span class="sxs-lookup"><span data-stu-id="aadcb-156">Reset the Audio Conferencing PIN for a user</span></span>](reset-the-audio-conferencing-pin-for-a-user.md)
