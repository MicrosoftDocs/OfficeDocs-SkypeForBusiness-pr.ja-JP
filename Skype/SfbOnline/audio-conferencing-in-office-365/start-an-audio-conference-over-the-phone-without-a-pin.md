---
title: "PIN なし、電話で音声、会議を開始します。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
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
description: "有効にする、または会議に参加する Skype for Business 管理センターからまたは PowerShell スクリプトを使用してから、匿名の呼び出しを無効にする方法について説明します。 "
ms.openlocfilehash: 57e1e209180cb5811556cdd29a5d45a77302eb22
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin"></a><span data-ttu-id="02451-103">PIN なし、電話で音声、会議を開始します。</span><span class="sxs-lookup"><span data-stu-id="02451-103">Start an Audio Conference over the phone without a PIN</span></span>

<span data-ttu-id="02451-104">Skype for Business または Microsoft チーム会議の開催者が会議を開始していないために、音楽を聴く、会議のロビー内で保持する会議にダイヤルインするユーザーに不満がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="02451-104">It might be frustrating for users who dial in to a meeting to be held in the meeting's lobby listening to music because the Skype for Business or Microsoft Teams meeting organizer hasn't started the meeting.</span></span> 
  
<span data-ttu-id="02451-p101">会議の開催者通話、会議に既定では、会議を開始する PIN が必要です。誰でも会議にダイヤルインできますをいない会議を開始するピンのように求められますようにをそれを設定できます。有効にするか、1 人のユーザーには、この設定を無効にするのには、Skype for Business 管理センターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="02451-p101">If a meeting organizer calls in to the meeting, by default, a PIN is required to start a meeting. You can set it up so that anyone can dial in to a meeting and not be prompted for a PIN to start the meeting. You can use the Skype for Business admin center to enable or disable this setting for a single user.</span></span>
  
<span data-ttu-id="02451-p102">PIN は、他のユーザーには、Skype for Business または Microsoft チームのアプリから、会議が開始した場合に会議の開催者の必要ありません。PIN は、会議の開催者、電話で自分の会議に参加するときに必要です。会議の PIN は、**電話会議**のライセンスが割り当てられている電話会議が有効なときに、オーディオのユーザーに送信されます。[この情報は、電話会議情報を持つユーザーに電子メールを送信](send-an-email-to-a-user-with-their-dial-in-information.md)し、[ユーザーの電話会議の設定を変更するときに自動的に送信されるメール](emails-sent-to-users-when-their-settings-change.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02451-p102">A PIN isn't required for the meeting organizer if someone has started the meeting from a Skype for Business or Microsoft Teams app. A PIN is only required when a meeting organizer joins their meeting over a phone. The PIN for meetings is sent to the audio user when they are assigned the **Audio Conferencing** license and are enabled for Audio Conferencing. See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md) and [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md).</span></span>
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a><span data-ttu-id="02451-112">有効にする、またはから会議に参加する匿名の発信者に応答を無効にします。</span><span class="sxs-lookup"><span data-stu-id="02451-112">Enable or disable anonymous callers from joining a meeting</span></span>

1. <span data-ttu-id="02451-113">職場または学校のアカウントで Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="02451-113">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="02451-114">**Office 365 管理センター**に移動 > **Skype for Business**します。</span><span class="sxs-lookup"><span data-stu-id="02451-114">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="02451-115">**Skype for Business 管理センター**、左のナビゲーションで**電話会議**に移動 > **ユーザー**。</span><span class="sxs-lookup"><span data-stu-id="02451-115">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**.</span></span> 
    
4. <span data-ttu-id="02451-116">一覧で、ユーザーを選択し、操作ウィンドウで [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="02451-116">In the list, select the user and in the Action pane click **Edit**.</span></span> 
    
5. <span data-ttu-id="02451-117">[**会議のオプション**] で、ユーザーのプロパティ ページを選択または**許可認証されていない会議内の最初のユーザーに発信者に応答をオフにします。かどうかは、[はロビーで待機認証済みユーザーに参加するまで**します。</span><span class="sxs-lookup"><span data-stu-id="02451-117">On the user's properties page, under **Meeting options**, select or clear **Allow unauthenticated callers to be the first people in a meeting. If not, then they will wait in the lobby until an authenticated user joins**.</span></span>
    
6. <span data-ttu-id="02451-118">{[**保存**] をクリックします。}</span><span class="sxs-lookup"><span data-stu-id="02451-118">Click **Save**.</span></span> 
    
 <span data-ttu-id="02451-119">**有効にするまたは、すべての Windows Powershell を使用して、ユーザーの会議に匿名の発信者に応答を無効にするには**</span><span class="sxs-lookup"><span data-stu-id="02451-119">**To enable or disable anonymous callers to all of your user's meetings using Windows Powershell**</span></span>
  
- <span data-ttu-id="02451-120">次を実行します。</span><span class="sxs-lookup"><span data-stu-id="02451-120">Run the following:</span></span> 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AllowPSTNOnlyMeetingsByDefault $true | $false
  ```

## <a name="what-else-should-you-know"></a><span data-ttu-id="02451-121">他かする必要がありますか。</span><span class="sxs-lookup"><span data-stu-id="02451-121">What else should you know?</span></span>

- <span data-ttu-id="02451-122">PIN をリセットする場合は、[ユーザーの音声会議の PIN のリセット](reset-the-audio-conferencing-pin-for-a-user.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02451-122">If you want to reset the PIN, see [Reset the Audio Conferencing PIN for a user](reset-the-audio-conferencing-pin-for-a-user.md).</span></span>
    
- <span data-ttu-id="02451-123">匿名アクセス、または会議を開始する暗証番号 (pin) を必要としない] がオンの場合</span><span class="sxs-lookup"><span data-stu-id="02451-123">If anonymous access, or not requiring a PIN to start a meeting, is enabled:</span></span>
    
  - <span data-ttu-id="02451-124">会議を開始していない場合 (は誰で、会議にまだ): 場合は、開催者の発信者が求められるPIN は、のように求められます彼場合は、彼には、[はい] と表示されるとミーティングを開始し、ユーザーが会議に参加する、暗証番号 (pin) を入力しています。</span><span class="sxs-lookup"><span data-stu-id="02451-124">If the meeting hasn't started (there's no one in the meeting yet): A caller will be prompted if he's the organizer; if he says yes, he'll be prompted for his PIN, and after he inputs the PIN, the meeting will start and the user will join the meeting.</span></span>
    
  - <span data-ttu-id="02451-125">会議を既に開始している場合 (他のユーザーが既に、会議中): 開催者は、彼ことがないように求められます PIN の場合、発信者が求められるはありません。会議がすでに開始されたら、および発信者に参加します。</span><span class="sxs-lookup"><span data-stu-id="02451-125">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if he's the organizer and he'll never be prompted for the PIN; the meeting is already started, and the caller will join it.</span></span>
    
- <span data-ttu-id="02451-126">匿名アクセス、または会議を開始する暗証番号 (pin) を必要としないが無効の場合</span><span class="sxs-lookup"><span data-stu-id="02451-126">If anonymous access, or not requiring a PIN to start a meeting, is disabled:</span></span>
    
  - <span data-ttu-id="02451-p103">会議を開始していない場合 (は誰で、会議にまだ): は、開催者と彼女ことがないように求められます PIN の場合、発信者が求められるはありません。開催者の設定はオフ] に設定されているため、ミーティングを開始し、匿名の発信者が会議への参加します。</span><span class="sxs-lookup"><span data-stu-id="02451-p103">If the meeting hasn't started (there's no one in the meeting yet): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN. Because the setting of the organizer is set to off, the meeting will start and the anonymous callers will join the meeting.</span></span>
    
  - <span data-ttu-id="02451-129">会議を既に開始している場合 (他のユーザーが既に、会議中): は、開催者と彼女ことがないように求められます、PIN の場合、発信者が求められるはありません。 会議がすでに開始されたら、および発信者に参加します。</span><span class="sxs-lookup"><span data-stu-id="02451-129">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN,;the meeting is already started, and the caller will join it.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="02451-130">Windows PowerShell で管理する方法を知りたいとしていますか。</span><span class="sxs-lookup"><span data-stu-id="02451-130">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="02451-131">時間を節約し、1 つ以上のユーザーの自動化したりには、[セット CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 )コマンドレットを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="02451-131">To save time or automate this for more than one user, you can use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) cmdlet.</span></span>
    
-  <span data-ttu-id="02451-p104">Windows PowerShell する際に、Skype for Business Online はすべてを管理するユーザーとユーザーの許可または使用できません。Windows PowerShell で複数のタスクを実行するがある場合、日常業務を簡素化する管理の 1 つのポイントを使用して Office 365 を管理できます。Windows PowerShell で開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="02451-p104">When it comes to Windows PowerShell, Skype for Business Online is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="02451-135">Office 365 PowerShell を使用する必要がある理由</span><span class="sxs-lookup"><span data-stu-id="02451-135">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="02451-136">Windows PowerShell で Office 365 を管理する最善の方法</span><span class="sxs-lookup"><span data-stu-id="02451-136">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="02451-p105">Windows PowerShell では多くの利点速度、わかりやすいように、および生産性でのみ実行しようとする設定の変更、多くのユーザーに一度になど、Office 365 管理センターを使用します。次のトピックでこれらの利点について学習します。</span><span class="sxs-lookup"><span data-stu-id="02451-p105">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time. Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="02451-139">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="02451-139">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [<span data-ttu-id="02451-140">Windows PowerShell を使用して、Skype for Business Online の管理するには</span><span class="sxs-lookup"><span data-stu-id="02451-140">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="02451-141">Windows PowerShell を使用して、共通の Skype for Business Online の管理タスクを実行するには</span><span class="sxs-lookup"><span data-stu-id="02451-141">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="02451-p106">Skype for Business Online 用の Windows PowerShell モジュールを使用すると、Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成することができます。このモジュールでは、64 ビット コンピューター以外では、Microsoft ダウンロード センターからダウンロードできます[Skype for Business Online 用の Windows PowerShell モジュール](https://go.microsoft.com/fwlink/?LinkId=294688)。</span><span class="sxs-lookup"><span data-stu-id="02451-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="02451-144">関連トピック</span><span class="sxs-lookup"><span data-stu-id="02451-144">Related topics</span></span>

[<span data-ttu-id="02451-145">Skype for Business とチームの Microsoft の音声会議をセットアップする設定します。</span><span class="sxs-lookup"><span data-stu-id="02451-145">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](set-up-audio-conferencing.md)
