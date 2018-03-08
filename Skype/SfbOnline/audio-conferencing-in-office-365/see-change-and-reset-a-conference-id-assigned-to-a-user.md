---
title: "表示、変更、およびユーザーに割り当てられている電話会議 ID をリセットします。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 77d36233-2aab-4802-ba9c-e9a8885ea643
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
description: "Skype for Business のユーザーに会議 ID を割り当てる方法と、どのような会議 ID パラメーターをする必要があります。 "
ms.openlocfilehash: f98257892c219e2777c52aefb3b2fd89bfb53710
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="see-change-and-reset-a-conference-id-assigned-to-a-user"></a><span data-ttu-id="028c7-103">表示、変更、およびユーザーに割り当てられている電話会議 ID をリセットします。</span><span class="sxs-lookup"><span data-stu-id="028c7-103">See, change, and reset a conference ID assigned to a user</span></span>

<span data-ttu-id="028c7-p101">Skype for Business または Microsoft チームのユーザーには、会議 ID が、Office 365 での電話会議用に設定し、電話会議プロバイダーとして Microsoft を使用して自動的に割り当てられています。割り当てられている電話会議 ID 静的または動的でき、会議がスケジュールされている場合は、会議の出席依頼の送信します。</span><span class="sxs-lookup"><span data-stu-id="028c7-p101">A conferencing ID is automatically assigned to a Skype for Business or Microsoft Teams user when they are set up for Audio Conferencing in Office 365 and use Microsoft as the audio conferencing provider. The conference ID assigned can be either static or dynamic and is sent in the meeting invite when the meeting is scheduled.</span></span>
  
<span data-ttu-id="028c7-p102">静的な Id は、組織内のユーザーをランダムな番号を保存したくない場合に使用します。特定の番号を選択したり、覚えやすいものを使用することができます。動的会議 Id を使用する場合各会議ユーザーのスケジュールが取得割り当て会議の一意の id。場合は、割り当てる静的会議 Id、[ここ](using-audio-conferencing-dynamic-ids-in-your-organization.md)ではなく動的します。</span><span class="sxs-lookup"><span data-stu-id="028c7-p102">Static IDs are used when people in your organization don't want to remember a random number; they can select a certain number or use one that's easy to remember. When dynamic conference IDs are used, each meeting that a user schedules will get assigned a unique conference ID. If you want to assign dynamic rather than static conference IDs, [go here](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span></span>
  
<span data-ttu-id="028c7-p103">静的会議 ID が自動的に作成され、ユーザーに割り当てられているがありますか、ユーザーが使用するし、特定の数を設定するユーザーに、会議 ID が喪失したか、思い出せない場合**Skype for Business 管理センター**と Windows PowerShell を使用するには、表示、変更、および、会議 ID をリセットするには</span><span class="sxs-lookup"><span data-stu-id="028c7-p103">Although a static conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID. You can use the **Skype for Business admin center** and Windows PowerShell to view, change, and reset their conference ID.</span></span>
  
<span data-ttu-id="028c7-111">メール、会議 ID と既定電話会議の電話番号、ユーザーに送信されます。 または場合、会議 ID をリセットする別のメールが送信されますが、会議 ID、PIN いないに含まれています。</span><span class="sxs-lookup"><span data-stu-id="028c7-111">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN.</span></span>
  
## <a name="view-and-change-conference-ids"></a><span data-ttu-id="028c7-112">表示して、会議 Id を変更します。</span><span class="sxs-lookup"><span data-stu-id="028c7-112">View and change conference IDs</span></span>

### <a name="to-view-the-conference-id"></a><span data-ttu-id="028c7-113">電話会議 ID を表示するには</span><span class="sxs-lookup"><span data-stu-id="028c7-113">To view the conference ID</span></span>

<span data-ttu-id="028c7-114">自分の会議 ID を表示し、ユーザーに送信できます。</span><span class="sxs-lookup"><span data-stu-id="028c7-114">You can view their conference ID and send it to users.</span></span>
  
1. <span data-ttu-id="028c7-115">職場または学校のアカウントで Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="028c7-115">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="028c7-116">**Office 365 管理センター**に移動 > **Skype for Business**します。</span><span class="sxs-lookup"><span data-stu-id="028c7-116">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="028c7-117">**Skype for Business 管理センター**で> **電話会議** > **ユーザー**会議の id 必要なユーザーを選択。</span><span class="sxs-lookup"><span data-stu-id="028c7-117">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, select the user who needs the conference ID.</span></span>
    
4. <span data-ttu-id="028c7-118">[アクション] ページで、[**電話会議 ID**を確認します。</span><span class="sxs-lookup"><span data-stu-id="028c7-118">In the Action page, look under **Conference ID**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="028c7-119">すべての会議情報を**ユーザー** ] ページでユーザーを選択した後に**会議情報を電子メールで送信する**リンクをクリックして、会議 ID とオーディオの電話番号を含むメール内のユーザーに送信できます。</span><span class="sxs-lookup"><span data-stu-id="028c7-119">You can send all of the conferencing information to the user in an email that includes the conference ID and audio phone numbers by clicking the **Send conference info via email** link after you select the user on the **Users** page.</span></span>
  
    <span data-ttu-id="028c7-p104">ユーザーの会議 ID を表示するのには、Windows PowerShell を使うことができます。これを行うには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="028c7-p104">You can use Windows PowerShell to view the conference ID for a user. To do so, run:</span></span>
    
  ```
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"  
  ```

    <span data-ttu-id="028c7-122">[Get-csonlinedialinconferencinguser](https://go.microsoft.com/fwlink/?LinkId=617693 )コマンドレットの詳細を参照してください。</span><span class="sxs-lookup"><span data-stu-id="028c7-122">See [Get-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 ) to learn more about the cmdlet.</span></span>
    
### <a name="to-assign-or-change-the-conference-id"></a><span data-ttu-id="028c7-123">割り当てるか、会議 ID を変更するには</span><span class="sxs-lookup"><span data-stu-id="028c7-123">To assign or change the conference ID</span></span>

<span data-ttu-id="028c7-124">割り当てる場合、たとえば、覚えやすい会議 ID を特定のユーザーの会議 ID を変更したりできます。</span><span class="sxs-lookup"><span data-stu-id="028c7-124">You can assign or change a conference ID for a user if, for example, someone wants a conference ID that's easy to remember.</span></span>

  > [!NOTE]
  > <span data-ttu-id="028c7-125">Skype for Business 管理センターを使用すると、自動的に作成されている会議 ID を編集することはできませんが、編集または変更する設定した会議 ID に Windows PowerShell を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="028c7-125">The Skype for Business admin center can't be used to edit a conference ID that has been automatically created, but you can use Windows PowerShell to edit or change a conference ID that you have set.</span></span> 
     
<span data-ttu-id="028c7-126">編集または変更するユーザーの会議 ID を実行します。</span><span class="sxs-lookup"><span data-stu-id="028c7-126">To edit or change the conference ID for a user, run:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ConferenceId 8271964
  ```

  > [!TIP]
  > <span data-ttu-id="028c7-127">会議 ID が 7 つの数字を含める必要があり、Skype for Business 管理センター、または Windows PowerShell を使用してで変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="028c7-127">A conference ID must contain 7 digits, and you can't change it in the Skype for Business admin center or by using Windows PowerShell.</span></span> 
  
### <a name="to-reset-the-conference-id"></a><span data-ttu-id="028c7-128">電話会議 ID をリセットするには</span><span class="sxs-lookup"><span data-stu-id="028c7-128">To reset the conference ID</span></span>

<span data-ttu-id="028c7-129">ユーザーの会議 ID をリセットする場合は、たとえば、忘れた場合。</span><span class="sxs-lookup"><span data-stu-id="028c7-129">You can reset a conference ID for a user if, for example, if they forget it.</span></span>
  
1. <span data-ttu-id="028c7-130">職場または学校のアカウントで Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="028c7-130">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="028c7-131">**Office 365 管理センター**に移動 > **Skype for Business**します。</span><span class="sxs-lookup"><span data-stu-id="028c7-131">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="028c7-132">**Skype for Business 管理センター**で> **電話会議** > **ユーザー**の場合は、操作ウィンドウの [**電話会議 ID**を**リセット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="028c7-132">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, in the Action pane under **Conference ID**, click **Reset**.</span></span>
    
4. <span data-ttu-id="028c7-p105">**会議 ID をリセットですか?**ウィンドウで、[**はい**] をクリックします。会議 ID が自動的に作成し、新しい会議 ID を持つユーザーに送信されたメール</span><span class="sxs-lookup"><span data-stu-id="028c7-p105">In the **Reset conference ID?** window, click **Yes**. A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span>
    
    <span data-ttu-id="028c7-p106">Windows PowerShell を使用して、ユーザーの会議 ID をリセットできます。これを行うには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="028c7-p106">You can reset the conference ID for a user by using the Windows PowerShell. To do this, run:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ResetLeaderPIN 8271964
  ```

## <a name="what-else-should-you-know"></a><span data-ttu-id="028c7-137">他かする必要がありますか。</span><span class="sxs-lookup"><span data-stu-id="028c7-137">What else should you know?</span></span>

   > [!IMPORTANT]
   >  <span data-ttu-id="028c7-p107">新しい会議 ID を作成または再設定する 1 つは、古い会議 ID 発信者では使用できません。既存ように招待状に ID が追加された新しい会議出席依頼を会議のスケジュールを変更するユーザーに通知する必要があります。ユーザーは、Skype for Business 会議の移行ツールを使用して、既存の会議を更新することができます。ダウンロード、インストール、およびツールを実行する方法を参照してください: [skype for Business と Lync Meeting Update Tool](http://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)、 [Skype for Business Online、会議の移行ツール (64 ビット)](http://go.microsoft.com/fwlink/?LinkID=626047)、および[Skype for Business Online、会議の移行ツール (32 ビット)](https://www.microsoft.com/en-us/download/details.aspx?id=54079)。</span><span class="sxs-lookup"><span data-stu-id="028c7-p107">After a new conference ID is created or one is reset, the old conference ID can't be used by callers. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. The users can use the Skype for Business Meeting Migration Tool to update their existing meetings. To see how to download, install, and run the tool, see: [Meeting Update Tool for Skype for Business and Lync](http://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](http://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span></span>
  
- <span data-ttu-id="028c7-142">コマンドレットの詳細については、[セット CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 )を参照してください。</span><span class="sxs-lookup"><span data-stu-id="028c7-142">See [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) to learn more about the cmdlet.</span></span>
    
- <span data-ttu-id="028c7-p108">電話会議 ID には、電話会議ブリッジの設定の桁の長さを満たす必要があります。会議 Id にアルファベット順または特殊文字を使うことはできません。数値のみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="028c7-p108">The conference ID must meet the length in digits set on the audio conferencing bridge. You can't use alphabetic or special characters in conference IDs; only numbers can be used.</span></span>
    
- <span data-ttu-id="028c7-145">すべての電話会議ユーザーの会議 ID 既定では、7 桁し、以下の桁数を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="028c7-145">The conference ID for all of your audio conferencing users will be 7 digits by default, and the number of digits can't be changed.</span></span>
    
- <span data-ttu-id="028c7-p109">サードパーティ電話会議プロバイダーに電話会議プロバイダーとしてユーザーを Microsoft から移動、または電話会議プロバイダーは、 **[なし]**に設定されて、会議 ID は機能しなくなります。[電話会議プロバイダーとしてサードパーティ](assign-a-third-party-as-the-audio-conferencing-provider.md)を割り当てたり、[移動するのには、Microsoft のユーザーの電話会議プロバイダー](moving-a-user-s-audio-conferencing-provider-to-microsoft.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="028c7-p109">If the user is moved from Microsoft as the audio conferencing provider to a third-party audio conferencing provider or the audio conferencing provider is set to **None**, the conference ID will no longer work. See [Assign a third-party as the audio conferencing provider](assign-a-third-party-as-the-audio-conferencing-provider.md) or [Moving a user's audio conferencing provider to Microsoft](moving-a-user-s-audio-conferencing-provider-to-microsoft.md).</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="028c7-148">Windows PowerShell で管理する方法を知りたいとしていますか。</span><span class="sxs-lookup"><span data-stu-id="028c7-148">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="028c7-p110">Windows powershell となるはすべてを管理するユーザーとユーザーの許可または使用できません。Windows PowerShell で Office 365 と Skype for Business Online の複数のタスクを実行するがある場合、日常業務を簡素化する管理の 1 つのポイントを使用して管理できます。Windows PowerShell で開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="028c7-p110">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="028c7-152">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="028c7-152">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="028c7-153">Office 365 PowerShell を使用する必要がある理由</span><span class="sxs-lookup"><span data-stu-id="028c7-153">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="028c7-p111">Windows PowerShell では多くの利点速度、わかりやすいように、および生産性でのみ実行しようとする設定の変更、多くのユーザーに一度になどの Office 365 管理センターを使用します。次のトピックでこれらの利点について学習します。</span><span class="sxs-lookup"><span data-stu-id="028c7-p111">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="028c7-156">Windows PowerShell で Office 365 を管理する最善の方法</span><span class="sxs-lookup"><span data-stu-id="028c7-156">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="028c7-157">Windows PowerShell を使用して、Skype for Business Online の管理するには</span><span class="sxs-lookup"><span data-stu-id="028c7-157">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="028c7-158">Windows PowerShell を使用して、共通の Skype for Business Online の管理タスクを実行するには</span><span class="sxs-lookup"><span data-stu-id="028c7-158">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="028c7-159">関連トピック</span><span class="sxs-lookup"><span data-stu-id="028c7-159">Related topics</span></span>

[<span data-ttu-id="028c7-160">Skype for Business とチームの Microsoft の音声会議をセットアップする設定します。</span><span class="sxs-lookup"><span data-stu-id="028c7-160">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](set-up-audio-conferencing.md)
  

