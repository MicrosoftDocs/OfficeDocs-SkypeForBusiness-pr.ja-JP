---
title: "ユーザーの会議 ID をリセットする"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
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
description: 'Learn the steps to reset a user''s meeting conference ID, and get links to meeting update and migration tools. '
ms.openlocfilehash: 2f2cbd6efa61e05defb17ef05f86fd9a228987ac
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/15/2017
---
# <a name="reset-a-conference-id-for-a-user"></a><span data-ttu-id="aa90f-103">ユーザーの会議 ID をリセットする</span><span class="sxs-lookup"><span data-stu-id="aa90f-103">Reset a conference ID for a user</span></span>

<span data-ttu-id="aa90f-104">組織は、会議 Id を動的に有効になっていない、静的な会議 ID はプロバイダーと Microsoft を使用してオーディオ会議のため、Skype のビジネスまたはマイクロソフトのチームのユーザーが有効になっているときに自動的に作成します。</span><span class="sxs-lookup"><span data-stu-id="aa90f-104">When your organizations hasn't been enabled for dynamic conference IDs, a static conference ID is automatically created when a Skype for Business or Microsoft Teams user is enabled for Audio Conferencing using Microsoft as the provider.</span></span> <span data-ttu-id="aa90f-105">この会議 ID では、会議出席依頼と会議へのコールを呼び出し元で使用できるダイヤルインの電話番号の下に含まれています。</span><span class="sxs-lookup"><span data-stu-id="aa90f-105">This conference ID is included at the bottom of meeting invitations along with the dial-in phone numbers that can be used by callers to call in to a meeting.</span></span> <span data-ttu-id="aa90f-106">ユーザーは、電話番号をダイヤルするとき、会議のための自動応答は、会議に出席することができますので、この会議 ID を入力するのには呼び出し元を求められます。</span><span class="sxs-lookup"><span data-stu-id="aa90f-106">When the user dials the phone number, the auto attendant for the meeting will ask the caller to enter this conference ID so they can attend the meeting.</span></span>
  
> [!NOTE]
> <span data-ttu-id="aa90f-107">会議プロバイダーがマイクロソフトの場合は、ユーザーの会議 Id が既定で動的なだけに設定されます。</span><span class="sxs-lookup"><span data-stu-id="aa90f-107">If your conferencing provider is Microsoft, your users' conference IDs are set to Dynamic Only by default.</span></span> <span data-ttu-id="aa90f-108">残念ながら、ビジネス管理センターまたは Windows Powershell を使用して Skype でそれを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="aa90f-108">Unfortunately, you won't be able to change it in the Skype for Business Admin Center or using Windows Powershell.</span></span> <span data-ttu-id="aa90f-109">マイクロソフト サポートに連絡する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aa90f-109">You will have to contact Microsoft support.</span></span> 
  
<span data-ttu-id="aa90f-110">静的の Id は、組織内のユーザーはランダムな番号を覚えておく必要があるときに使用します。特定の番号を選択したり、覚えやすいものを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="aa90f-110">Static IDs are used when people in your organization don't want to remember a random number; they can select a certain number or use one that's easy to remember.</span></span> <span data-ttu-id="aa90f-111">動的会議 Id を使用する場合各会議ユーザのスケジュールは割り当てられます会議の一意の id。</span><span class="sxs-lookup"><span data-stu-id="aa90f-111">When dynamic conference IDs are used, each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="aa90f-112">場合に割り当てる静的な会議 Id を[ここ](using-audio-conferencing-dynamic-ids-in-your-organization.md)にではなく動的です。</span><span class="sxs-lookup"><span data-stu-id="aa90f-112">If you want to assign dynamic rather than static conference IDs, [go here](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span></span>
  
<span data-ttu-id="aa90f-113">会議 Id はのみ自動的に設定だけ Skype 音声会議を有効にするビジネスおよびマイクロソフトのチームのユーザーの Microsoft を使用して、オーディオ会議プロバイダーとしてです。</span><span class="sxs-lookup"><span data-stu-id="aa90f-113">Conference IDs are only automatically set only for Skype for Business and Microsoft Teams users enabled for Audio Conferencing using Microsoft as their audio conferencing provider.</span></span> <span data-ttu-id="aa90f-114">サード ・ パーティ製の音声会議プロバイダー (ACP) を使用してユーザーのための会議 ID をリセットする場合は、[プロパティ] ページで、ユーザーの会議 ID を手動で入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aa90f-114">If you need to reset a conference ID for a user who is using a third-party audio conferencing provider (ACP), you will need to manually enter a conference ID on the properties page for the user.</span></span>
  
## <a name="resetting-the-conference-id-for-a-user"></a><span data-ttu-id="aa90f-115">ユーザーの会議 ID をリセットします。</span><span class="sxs-lookup"><span data-stu-id="aa90f-115">Resetting the conference ID for a user</span></span>

1. <span data-ttu-id="aa90f-116">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="aa90f-116">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="aa90f-117">**Office 365 管理センター**を参照して > **ビジネス用の Skype**です。</span><span class="sxs-lookup"><span data-stu-id="aa90f-117">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="aa90f-118">**ビジネス管理センターの Skype**では、[**電話会議**] をクリックします > **ユーザー**ユーザーを選択し、し、[操作] ウィンドウの [**会議 ID** ] の [**リセット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aa90f-118">In the **Skype for Business admin center**, click **Audio conferencing** > **Users**, select a user, and then in the Action pane under **Conference ID** click **Reset**.</span></span>
    
4. <span data-ttu-id="aa90f-119">**会議 ID をリセットしますか?** ] ウィンドウで、[**はい**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aa90f-119">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="aa90f-120">会議 ID が自動的に作成し、新しい会議 ID を持つユーザーに送信する電子メール</span><span class="sxs-lookup"><span data-stu-id="aa90f-120">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span> <span data-ttu-id="aa90f-121">既定では、ユーザーに電子メールが送信されますが、これを無効にできます。</span><span class="sxs-lookup"><span data-stu-id="aa90f-121">By default, emails are sent to users, but this can be turned off.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="aa90f-p106">会議 ID をリセットすると、新しい会議 ID を記載したメールがユーザーに送信されます。このメールはプライマリ メール アドレスに送信されます。ほとんどの場合は、Office 365 のメールボックスに送信されます。新しい会議 ID、既定のダイヤルイン電話番号、Skype for Business Meeting Update Tool を使って既存の会議を更新する方法がメールに記載されています。</span><span class="sxs-lookup"><span data-stu-id="aa90f-p106">After you reset the conference ID, an email with the new conference ID will be sent to the user. This email will be sent to the primary email address, in many cases, their Office 365 mailbox. The email contains the new conference ID, default dial-in phone number(s) and instructions to use the Skype for Business Meeting Update Tool to update existing meetings.</span></span> 
  
## <a name="what-else-should-i-know"></a><span data-ttu-id="aa90f-125">他に必要な情報はありますか?</span><span class="sxs-lookup"><span data-stu-id="aa90f-125">What else should I know?</span></span>

- <span data-ttu-id="aa90f-126">操作ウィンドウでのユーザーの [**電子メール経由での会議の情報を送信**] をクリックして、会議 ID とダイヤルインの電話番号を含む電子メールでユーザーにすべての会議の情報を送信できます。</span><span class="sxs-lookup"><span data-stu-id="aa90f-126">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking **Send conference info via email** for the user in the Action pane.</span></span> <span data-ttu-id="aa90f-127">暗証番号 (pin) を送信しないことです。</span><span class="sxs-lookup"><span data-stu-id="aa90f-127">It doesn't send the PIN.</span></span>
    
- <span data-ttu-id="aa90f-128">会議 ID が 7 桁の数字を含めるし、ビジネス管理センターまたは Windows PowerShell を使用して、Skype では、その長さを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="aa90f-128">A conference ID will contain 7 digits, and you can't change its length in the Skype for Business admin center or by using Windows PowerShell.</span></span>
    
- <span data-ttu-id="aa90f-129">会議 ID をリセットすると、新しい会議 ID が [ **電話会議 ID**] に一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="aa90f-129">After it has been reset, you can see the new conference ID listed under **Conference ID**.</span></span>
    
- <span data-ttu-id="aa90f-130">[**ユーザー** ] ページで、ユーザーを選択すると、**オーディオ会議**の下にある操作ウィンドウの下部にあるユーザーが電話会議の会議 ID を表示できます。</span><span class="sxs-lookup"><span data-stu-id="aa90f-130">The conference ID for a user for audio conferencing can be viewed at the bottom of the Action pane under **Audio conferencing** when you select the user on the **Users** page.</span></span>
    
- <span data-ttu-id="aa90f-131">新しい会議 ID が作成されると、呼び出し元が古い会議 ID を使用できません。</span><span class="sxs-lookup"><span data-stu-id="aa90f-131">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="aa90f-132">ミーティングの招待新しい会議 ID が、招待状に追加されることを確認するのには、既存のスケジュールを変更するのにはユーザーに通知する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aa90f-132">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="aa90f-133">ユーザーは、ビジネス会議ツールの Skype を使用して、既存の会議を更新します。</span><span class="sxs-lookup"><span data-stu-id="aa90f-133">The users can use Skype for Business Meeting Tool to update their existing meetings.</span></span> <span data-ttu-id="aa90f-134">ダウンロード、インストール、および、Skype をビジネス会議の更新ツールを実行する方法を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aa90f-134">To see how to download, install, and run the Skype for Business Meeting Update Tool, see:</span></span>
    
  - [<span data-ttu-id="aa90f-135">Skype for Business Meeting Update Tool と Lync Meeting Update Tool</span><span class="sxs-lookup"><span data-stu-id="aa90f-135">Meeting Update Tool for Skype for Business and Lync</span></span>](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)
    
  - [<span data-ttu-id="aa90f-136">Skype for Business Online、会議移行ツール (64 ビット)</span><span class="sxs-lookup"><span data-stu-id="aa90f-136">Skype for Business Online, Meeting Migration Tool (64-bit)</span></span>](https://go.microsoft.com/fwlink/?LinkID=626047)
    
  - [<span data-ttu-id="aa90f-137">Skype for Business Online、会議移行ツール (32 ビット)</span><span class="sxs-lookup"><span data-stu-id="aa90f-137">Skype for Business Online, Meeting Migration Tool (32-bit)</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=54079)
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="aa90f-138">Windows PowerShell で管理する方法</span><span class="sxs-lookup"><span data-stu-id="aa90f-138">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="aa90f-p109">Windows PowerShell で行うのは、ユーザーを管理し、ユーザーに何を許可して何を禁止するかを管理することです。Windows PowerShell を利用すると、Office 365 と Skype for Business Online の管理を 1 か所で行うことができるので、複数のタスクを担当する管理者の日常業務を単純化できます。Windows PowerShell の使用を開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="aa90f-p109">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="aa90f-142">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="aa90f-142">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="aa90f-143">Office 365 の PowerShell を使用する必要がある理由</span><span class="sxs-lookup"><span data-stu-id="aa90f-143">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="aa90f-p110">Windows PowerShell には、ただ Office 365 管理センターを使用するだけではなく、速度、単純さ、生産性において多くの利点があります。次のトピックでこれらの利点について説明します。</span><span class="sxs-lookup"><span data-stu-id="aa90f-p110">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="aa90f-146">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="aa90f-146">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="aa90f-147">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="aa90f-147">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="aa90f-148">Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行</span><span class="sxs-lookup"><span data-stu-id="aa90f-148">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="aa90f-149">関連トピック</span><span class="sxs-lookup"><span data-stu-id="aa90f-149">Related topics</span></span>

[<span data-ttu-id="aa90f-150">ユーザーのオーディオ会議の PIN をリセットします。</span><span class="sxs-lookup"><span data-stu-id="aa90f-150">Reset the Audio Conferencing PIN for a user</span></span>](reset-the-audio-conferencing-pin-for-a-user.md)
