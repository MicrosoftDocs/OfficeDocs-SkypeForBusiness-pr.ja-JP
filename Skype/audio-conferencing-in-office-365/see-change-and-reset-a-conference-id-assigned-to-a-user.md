---
title: "参照してください、変更、およびユーザーに割り当てられている会議 ID をリセットします。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 77d36233-2aab-4802-ba9c-e9a8885ea643
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
description: "については、ビジネスの Skype のユーザーに会議 ID を割り当てる方法と、どのような会議 ID のパラメーターにする必要があります。 "
ms.openlocfilehash: 46edf684a835984524ce988da532b6b9a14931da
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/15/2017
---
# <a name="see-change-and-reset-a-conference-id-assigned-to-a-user"></a><span data-ttu-id="99b8e-103">参照してください、変更、およびユーザーに割り当てられている会議 ID をリセットします。</span><span class="sxs-lookup"><span data-stu-id="99b8e-103">See, change, and reset a conference ID assigned to a user</span></span>

<span data-ttu-id="99b8e-104">会議 ID が、Skype のビジネスまたはマイクロソフトのチームのユーザーに割り当てられたは、Office 365 での音声会議用に設定し、Microsoft を使用して、オーディオ会議プロバイダーとして自動的にします。</span><span class="sxs-lookup"><span data-stu-id="99b8e-104">A conferencing ID is automatically assigned to a Skype for Business or Microsoft Teams user when they are set up for Audio Conferencing in Office 365 and use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="99b8e-105">会議 ID が割り当てられている静的または動的のどちらかにすることができ、会議がスケジュールされているときに会議出席依頼の送信します。</span><span class="sxs-lookup"><span data-stu-id="99b8e-105">The conference ID assigned can be either static or dynamic and is sent in the meeting invite when the meeting is scheduled.</span></span>
  
<span data-ttu-id="99b8e-106">静的の Id は、組織内のユーザーはランダムな番号を覚えておく必要があるときに使用します。特定の番号を選択したり、覚えやすいものを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="99b8e-106">Static IDs are used when people in your organization don't want to remember a random number; they can select a certain number or use one that's easy to remember.</span></span> <span data-ttu-id="99b8e-107">動的会議 Id を使用する場合各会議ユーザのスケジュールは割り当てられます会議の一意の id。</span><span class="sxs-lookup"><span data-stu-id="99b8e-107">When dynamic conference IDs are used, each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="99b8e-108">場合に割り当てる静的な会議 Id を[ここ](using-audio-conferencing-dynamic-ids-in-your-organization.md)にではなく動的です。</span><span class="sxs-lookup"><span data-stu-id="99b8e-108">If you want to assign dynamic rather than static conference IDs, [go here](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span></span>
  
<span data-ttu-id="99b8e-109">静的な会議 ID が自動的に作成され、ユーザーに割り当てられているが場合がありますこの 1 つを使用するユーザーが望まないし、特定の数に設定するとき、またはユーザーが覚えられないか、会議 ID が失われている場合</span><span class="sxs-lookup"><span data-stu-id="99b8e-109">Although a static conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="99b8e-110">**Skype**ビジネス管理センターは、Windows PowerShell を使用するには表示、変更、および、会議 ID をリセットするには</span><span class="sxs-lookup"><span data-stu-id="99b8e-110">You can use the **Skype for Business admin center** and Windows PowerShell to view, change, and reset their conference ID.</span></span>
  
<span data-ttu-id="99b8e-111">会議 ID と既定の電話会議の電話番号をユーザーに電子メールが送信される、または会議 ID がない、暗証番号 (pin) に含まれている会議 ID をリセットする場合、別の電子メールが送信されます。</span><span class="sxs-lookup"><span data-stu-id="99b8e-111">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN.</span></span>
  
## <a name="view-and-change-conference-ids"></a><span data-ttu-id="99b8e-112">表示し、会議 Id を変更します。</span><span class="sxs-lookup"><span data-stu-id="99b8e-112">View and change conference IDs</span></span>

### <a name="to-view-the-conference-id"></a><span data-ttu-id="99b8e-113">会議 ID を表示するのには</span><span class="sxs-lookup"><span data-stu-id="99b8e-113">To view the conference ID</span></span>

<span data-ttu-id="99b8e-114">会議 ID を表示し、ユーザーに送信することができます。</span><span class="sxs-lookup"><span data-stu-id="99b8e-114">You can view their conference ID and send it to users.</span></span>
  
1. <span data-ttu-id="99b8e-115">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="99b8e-115">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="99b8e-116">**Office 365 管理センター**を参照して > **ビジネス用の Skype**です。</span><span class="sxs-lookup"><span data-stu-id="99b8e-116">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="99b8e-117">**ビジネス管理センターの Skype**の> **オーディオ会議** > **ユーザー**ユーザーが必要な会議の id を選択。</span><span class="sxs-lookup"><span data-stu-id="99b8e-117">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, select the user who needs the conference ID.</span></span>
    
4. <span data-ttu-id="99b8e-118">[アクション] ページで、[**会議 ID**] を確認します。</span><span class="sxs-lookup"><span data-stu-id="99b8e-118">In the Action page, look under **Conference ID**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="99b8e-119">[**ユーザー** ] ページで、ユーザーを選択した後に**電子メールを使用して会議情報を送信する**リンクをクリックして、会議 ID とオーディオの電話番号を含む電子メールでユーザーにすべての会議の情報を送信できます。</span><span class="sxs-lookup"><span data-stu-id="99b8e-119">You can send all of the conferencing information to the user in an email that includes the conference ID and audio phone numbers by clicking the **Send conference info via email** link after you select the user on the **Users** page.</span></span>
  
    <span data-ttu-id="99b8e-120">ユーザーの会議 ID を表示するのには、Windows PowerShell を使用できます。</span><span class="sxs-lookup"><span data-stu-id="99b8e-120">You can use Windows PowerShell to view the conference ID for a user.</span></span> <span data-ttu-id="99b8e-121">これを行うには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="99b8e-121">To do so, run:</span></span>
    
  ```
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"  
  ```

    <span data-ttu-id="99b8e-122">コマンドレットの詳細については、 [Get CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 )を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99b8e-122">See [Get-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 ) to learn more about the cmdlet.</span></span>
    
### <a name="to-assign-or-change-the-conference-id"></a><span data-ttu-id="99b8e-123">割り当て、または会議 ID を変更するには</span><span class="sxs-lookup"><span data-stu-id="99b8e-123">To assign or change the conference ID</span></span>

<span data-ttu-id="99b8e-124">ユーザーの会議 ID を変更する場合、たとえば、覚えやすいものである会議 ID を割り当てたりできます。</span><span class="sxs-lookup"><span data-stu-id="99b8e-124">You can assign or change a conference ID for a user if, for example, someone wants a conference ID that's easy to remember.</span></span>

  > [!NOTE]
  > <span data-ttu-id="99b8e-125">ビジネス管理センターの Skype は自動的に作成されている会議 ID を編集するのには使用できませんが、編集、または設定した会議 ID を変更する Windows PowerShell を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="99b8e-125">The Skype for Business admin center can't be used to edit a conference ID that has been automatically created, but you can use Windows PowerShell to edit or change a conference ID that you have set.</span></span> 
     
<span data-ttu-id="99b8e-126">編集またはユーザーの会議 ID を変更する、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="99b8e-126">To edit or change the conference ID for a user, run:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ConferenceId 8271964
  ```

  > [!TIP]
  > <span data-ttu-id="99b8e-127">会議 ID が 7 桁の数字を含める必要があり、ビジネス管理センターまたは Windows PowerShell を使用して、Skype で変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="99b8e-127">A conference ID must contain 7 digits, and you can't change it in the Skype for Business admin center or by using Windows PowerShell.</span></span> 
  
### <a name="to-reset-the-conference-id"></a><span data-ttu-id="99b8e-128">会議 ID をリセットするのには</span><span class="sxs-lookup"><span data-stu-id="99b8e-128">To reset the conference ID</span></span>

<span data-ttu-id="99b8e-129">ユーザーの会議 ID をリセットすることができる場合、忘れた場合などです。</span><span class="sxs-lookup"><span data-stu-id="99b8e-129">You can reset a conference ID for a user if, for example, if they forget it.</span></span>
  
1. <span data-ttu-id="99b8e-130">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="99b8e-130">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="99b8e-131">**Office 365 管理センター**を参照して > **ビジネス用の Skype**です。</span><span class="sxs-lookup"><span data-stu-id="99b8e-131">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="99b8e-132">**ビジネス管理センターの Skype**の> **電話会議** > **ユーザー**、操作ウィンドウの [**会議 ID**に**リセット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="99b8e-132">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, in the Action pane under **Conference ID**, click **Reset**.</span></span>
    
4. <span data-ttu-id="99b8e-133">**会議 ID をリセットしますか?** ] ウィンドウで、[**はい**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="99b8e-133">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="99b8e-134">会議 ID が自動的に作成し、新しい会議 ID を持つユーザーに送信する電子メール</span><span class="sxs-lookup"><span data-stu-id="99b8e-134">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span>
    
    <span data-ttu-id="99b8e-135">ユーザーの会議 ID をリセットするには、Windows PowerShell を使用します。</span><span class="sxs-lookup"><span data-stu-id="99b8e-135">You can reset the conference ID for a user by using the Windows PowerShell.</span></span> <span data-ttu-id="99b8e-136">これを行うには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="99b8e-136">To do this, run:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ResetLeaderPIN 8271964
  ```

## <a name="what-else-should-you-know"></a><span data-ttu-id="99b8e-137">その他の情報</span><span class="sxs-lookup"><span data-stu-id="99b8e-137">What else should you know?</span></span>

   > [!IMPORTANT]
   >  <span data-ttu-id="99b8e-138">新しい会議 ID が作成されるか、1 つは、リセット後、は、呼び出し元が古い会議 ID を使用できません。</span><span class="sxs-lookup"><span data-stu-id="99b8e-138">After a new conference ID is created or one is reset, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="99b8e-139">ミーティングの招待新しい会議 ID が、招待状に追加されることを確認するのには、既存のスケジュールを変更するのにはユーザーに通知する必要があります。</span><span class="sxs-lookup"><span data-stu-id="99b8e-139">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="99b8e-140">ユーザーは、ビジネス会議の移行ツールの Skype を使用して、既存の会議を更新します。</span><span class="sxs-lookup"><span data-stu-id="99b8e-140">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="99b8e-141">ダウンロード、インストール、およびツールを実行する方法を参照してください:[ビジネスと Lync の Skype の会議の更新ツール](http://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)、 [Skype](http://go.microsoft.com/fwlink/?LinkID=626047)、および[Skype](https://www.microsoft.com/en-us/download/details.aspx?id=54079)です。</span><span class="sxs-lookup"><span data-stu-id="99b8e-141">To see how to download, install, and run the tool, see: [Meeting Update Tool for Skype for Business and Lync](http://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](http://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span></span>
  
- <span data-ttu-id="99b8e-142">コマンドレットの詳細については、[設定 CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 )を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99b8e-142">See [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) to learn more about the cmdlet.</span></span>
    
- <span data-ttu-id="99b8e-143">会議 ID は、オーディオ会議ブリッジを設定する桁の長さを満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="99b8e-143">The conference ID must meet the length in digits set on the audio conferencing bridge.</span></span> <span data-ttu-id="99b8e-144">会議 Id のアルファベット順または特殊文字を使うことはできません。数値のみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="99b8e-144">You can't use alphabetic or special characters in conference IDs; only numbers can be used.</span></span>
    
- <span data-ttu-id="99b8e-145">オーディオ会議のユーザーのすべての会議 ID が既定では、7 桁になるし、以下の桁数を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="99b8e-145">The conference ID for all of your audio conferencing users will be 7 digits by default, and the number of digits can't be changed.</span></span>
    
- <span data-ttu-id="99b8e-146">サード ・ パーティ製のオーディオ会議プロバイダーにオーディオ会議プロバイダーとして、ユーザーがマイクロソフトから移動したりされたり、オーディオ会議プロバイダーが**[なし]**に設定されて、会議 ID が動作しなくなります。</span><span class="sxs-lookup"><span data-stu-id="99b8e-146">If the user is moved from Microsoft as the audio conferencing provider to a third-party audio conferencing provider or the audio conferencing provider is set to **None**, the conference ID will no longer work.</span></span> <span data-ttu-id="99b8e-147">[オーディオ会議プロバイダーとしてサード パーティを割り当てる](assign-a-third-party-as-the-audio-conferencing-provider.md)か、[マイクロソフトのユーザーのオーディオ会議プロバイダーの移動](moving-a-user-s-audio-conferencing-provider-to-microsoft.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99b8e-147">See [Assign a third-party as the audio conferencing provider](assign-a-third-party-as-the-audio-conferencing-provider.md) or [Moving a user's audio conferencing provider to Microsoft](moving-a-user-s-audio-conferencing-provider-to-microsoft.md).</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="99b8e-148">Windows PowerShell で管理する方法</span><span class="sxs-lookup"><span data-stu-id="99b8e-148">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="99b8e-p110">Windows PowerShell で行うのは、ユーザーを管理し、ユーザーに何を許可して何を禁止するかを管理することです。Windows PowerShell を利用すると、Office 365 と Skype for Business Online の管理を 1 か所で行うことができるので、複数のタスクを担当する管理者の日常業務を単純化できます。Windows PowerShell の使用を開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="99b8e-p110">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="99b8e-152">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="99b8e-152">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="99b8e-153">Office 365 の PowerShell を使用する必要がある理由</span><span class="sxs-lookup"><span data-stu-id="99b8e-153">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="99b8e-p111">Windows PowerShell には、ただ Office 365 管理センターを使用するだけではなく、速度、単純さ、生産性において多くの利点があります。次のトピックでこれらの利点について説明します。</span><span class="sxs-lookup"><span data-stu-id="99b8e-p111">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="99b8e-156">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="99b8e-156">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="99b8e-157">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="99b8e-157">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="99b8e-158">Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行</span><span class="sxs-lookup"><span data-stu-id="99b8e-158">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="99b8e-159">関連トピック</span><span class="sxs-lookup"><span data-stu-id="99b8e-159">Related topics</span></span>

[<span data-ttu-id="99b8e-160">Skype for Business および Microsoft Teams の電話会議のセットアップ</span><span class="sxs-lookup"><span data-stu-id="99b8e-160">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](set-up-audio-conferencing.md)
  

