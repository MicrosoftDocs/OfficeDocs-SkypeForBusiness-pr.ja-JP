---
title: 電話 PIN なしで、オーディオ会議の開始します。
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Learn how to enable or disable anonymous callers from joining a meeting from the Skype for Business admin center or using a PowerShell script. '
ms.openlocfilehash: 4deb415e9fd7154d72b7d598bcc5dfb8eabed6ed
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin"></a><span data-ttu-id="cb74b-103">電話 PIN なしで、オーディオ会議の開始します。</span><span class="sxs-lookup"><span data-stu-id="cb74b-103">Start an Audio Conference over the phone without a PIN</span></span>

<span data-ttu-id="cb74b-104">[] 会議にダイヤルインしたのに、Skype for Business または Microsoft Teams 会議の開催者が会議を開始していないために、保留音の音楽を聞きながら会議のロビーで待たされるのは、ユーザーにとって不快な場合があります。</span><span class="sxs-lookup"><span data-stu-id="cb74b-104">It might be frustrating for users who dial in to a meeting to be held in the meeting's lobby listening to music because the Skype for Business or Microsoft Teams meeting organizer hasn't started the meeting.</span></span> 
  
<span data-ttu-id="cb74b-105">会議の開催者を呼び出す場合、会議出席依頼には、既定では、会議を開始するのには、暗証番号 (pin) が必要です。</span><span class="sxs-lookup"><span data-stu-id="cb74b-105">If a meeting organizer calls in to the meeting, by default, a PIN is required to start a meeting.</span></span> <span data-ttu-id="cb74b-106">できますを設定することをだれでも会議にダイヤルイン会議を開始するのには暗証番号 (pin) には求められません。</span><span class="sxs-lookup"><span data-stu-id="cb74b-106">You can set it up so that anyone can dial in to a meeting and not be prompted for a PIN to start the meeting.</span></span> <span data-ttu-id="cb74b-107">Skype for Business 管理センターを使用すると、この設定を 1 人のユーザーに対して有効または無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="cb74b-107">You can use the Skype for Business admin center to enable or disable this setting for a single user.</span></span>
  
<span data-ttu-id="cb74b-108">あるユーザーが Skype for Business または Microsoft Teams アプリから会議を開始した場合、会議の開催者に PIN が要求されることはありません。</span><span class="sxs-lookup"><span data-stu-id="cb74b-108">A PIN isn't required for the meeting organizer if someone has started the meeting from a Skype for Business or Microsoft Teams app.</span></span> <span data-ttu-id="cb74b-109">PIN が必要であるのは、会議の開催者が電話で自分の会議に参加する場合のみです。</span><span class="sxs-lookup"><span data-stu-id="cb74b-109">A PIN is only required when a meeting organizer joins their meeting over a phone.</span></span> <span data-ttu-id="cb74b-110">会議の暗証番号 (pin) は、**オーディオ会議**のライセンスが割り当てられている音声会議が有効になっていると、オーディオのユーザーに送信されます。</span><span class="sxs-lookup"><span data-stu-id="cb74b-110">The PIN for meetings is sent to the audio user when they are assigned the **Audio Conferencing** license and are enabled for Audio Conferencing.</span></span> <span data-ttu-id="cb74b-111">[オーディオ会議の情報を持つユーザーに電子メールを送信](send-an-email-to-a-user-with-their-dial-in-information.md)し、[ユーザーが電話会議の設定を変更するときに自動的に送信される電子メール](emails-sent-to-users-when-their-settings-change.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb74b-111">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md) and [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md).</span></span>
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a><span data-ttu-id="cb74b-112">匿名の発信者の会議への参加を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="cb74b-112">Enable or disable anonymous callers from joining a meeting</span></span>

<span data-ttu-id="cb74b-113">![チーム ・ ロゴ ・ 30x30.png](../images/teams-logo-30x30.png) **、マイクロソフトのチームとビジネス管理センターの Skype を使用します。**</span><span class="sxs-lookup"><span data-stu-id="cb74b-113">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="cb74b-114">左側のナビゲーションでは、**ユーザー**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb74b-114">In the left navigation, click **Users**.</span></span> 

2. <span data-ttu-id="cb74b-115">の一覧でユーザーを選択し、ページの上部にある**編集**を] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb74b-115">Select a user in the list, and then click **Edit** at the top of the page.</span></span> 

3. <span data-ttu-id="cb74b-116">**会議ブリッジ**の横にあるメニューをクリックし、し、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb74b-116">Click the menu next to **Conference Bridges**, and then click **Edit**.</span></span>

4. <span data-ttu-id="cb74b-117">**会議ブリッジのプロバイダー**のウィンドウでを有効にするまたは**許可が認証されていない呼び出し元は会議の最初のユーザーを無効にします。かどうか、ロビーで待機、認証されたユーザーが参加するまで**。</span><span class="sxs-lookup"><span data-stu-id="cb74b-117">In the **Conference bridge provider** pane, enable or disable **Allow unauthenticated callers to be the first people in a meeting. If not, then they will wait in the lobby until an authenticated user joins**.</span></span>
    
4. <span data-ttu-id="cb74b-118">[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb74b-118">Click **Apply**.</span></span> 

<span data-ttu-id="cb74b-119">![デバイスのロゴ-30x30.png](../images/sfb-logo-30x30.png) **ビジネス管理センターの Skype を使用します。**</span><span class="sxs-lookup"><span data-stu-id="cb74b-119">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
    
1. <span data-ttu-id="cb74b-120">**電話会議**には、**ビジネス管理センターの Skype**、左側のナビゲーションでの > **のユーザー**です。</span><span class="sxs-lookup"><span data-stu-id="cb74b-120">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**.</span></span> 
    
2. <span data-ttu-id="cb74b-121">の一覧でユーザーを選択し、[操作] ウィンドウの [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb74b-121">In the list, select the user and in the Action pane click **Edit**.</span></span> 
    
3. <span data-ttu-id="cb74b-122">ユーザーのプロパティ] ページで [**ミーティングのオプション**] でオンまたはオフ**許可が認証されていない呼び出し元は、会議の最初の人に。かどうか、ロビーで待機、認証されたユーザーが参加するまで**。</span><span class="sxs-lookup"><span data-stu-id="cb74b-122">On the user's properties page, under **Meeting options**, select or clear **Allow unauthenticated callers to be the first people in a meeting. If not, then they will wait in the lobby until an authenticated user joins**.</span></span>
    
4. <span data-ttu-id="cb74b-123">[ **保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb74b-123">Click **Save**.</span></span> 

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
    
 <span data-ttu-id="cb74b-124">**Windows Powershell を使用します。**</span><span class="sxs-lookup"><span data-stu-id="cb74b-124">**Using Windows Powershell**</span></span>
  
- <span data-ttu-id="cb74b-125">次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="cb74b-125">Run the following:</span></span> 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AllowPSTNOnlyMeetingsByDefault $true | $false
  ```

## <a name="what-else-should-you-know"></a><span data-ttu-id="cb74b-126">その他の情報</span><span class="sxs-lookup"><span data-stu-id="cb74b-126">What else should you know?</span></span>

- <span data-ttu-id="cb74b-127">PIN をリセットする場合は、[オーディオ会議の PIN のリセット](reset-the-audio-conferencing-pin.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb74b-127">If you want to reset the PIN, see [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin.md).</span></span>
    
- <span data-ttu-id="cb74b-128">匿名アクセス、または、会議を開始するのには暗証番号 (pin) を必要としない] がオンの場合</span><span class="sxs-lookup"><span data-stu-id="cb74b-128">If anonymous access, or not requiring a PIN to start a meeting, is enabled:</span></span>
    
  - <span data-ttu-id="cb74b-129">会議が開始されていない場合 (は誰もまだ会議で): 彼は、開催者の場合、呼び出し元が求められます、PIN のよう求められますその場合、[はい] と PIN を入力した後、ミーティングを開始し、ユーザーがミーティングに参加します。</span><span class="sxs-lookup"><span data-stu-id="cb74b-129">If the meeting hasn't started (there's no one in the meeting yet): A caller will be prompted if he's the organizer; if he says yes, he'll be prompted for his PIN, and after he inputs the PIN, the meeting will start and the user will join the meeting.</span></span>
    
  - <span data-ttu-id="cb74b-130">会議が既に開始されている場合 (他のユーザーが既に会議): 開催者は、彼とはしないよう求められます暗証番号 (pin) の場合、呼び出し元は要求されません。会議は既に開始されていると、呼び出し元に参加します。</span><span class="sxs-lookup"><span data-stu-id="cb74b-130">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if he's the organizer and he'll never be prompted for the PIN; the meeting is already started, and the caller will join it.</span></span>
    
- <span data-ttu-id="cb74b-131">匿名アクセス、または、会議を開始するのには暗証番号 (pin) を必要としないが無効の場合</span><span class="sxs-lookup"><span data-stu-id="cb74b-131">If anonymous access, or not requiring a PIN to start a meeting, is disabled:</span></span>
    
  - <span data-ttu-id="cb74b-132">会議が開始されていない場合 (は誰もまだ会議で): 開催者は、彼女と彼女がするメッセージは表示されません、暗証番号 (pin) の場合、呼び出し元は要求されません。</span><span class="sxs-lookup"><span data-stu-id="cb74b-132">If the meeting hasn't started (there's no one in the meeting yet): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN.</span></span> <span data-ttu-id="cb74b-133">開催者の設定がオフになっているため、会議が始まり、匿名の発信者が会議に参加します。</span><span class="sxs-lookup"><span data-stu-id="cb74b-133">Because the setting of the organizer is set to off, the meeting will start and the anonymous callers will join the meeting.</span></span>
    
  - <span data-ttu-id="cb74b-134">会議が既に開始されている場合 (他のユーザーが既に会議): 場合は、開催者は、彼女と暗証番号 (pin) の彼女を求められますことはありませんが、呼び出し元は要求されません; 会議は既に開始されていると、呼び出し元に参加します。</span><span class="sxs-lookup"><span data-stu-id="cb74b-134">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN,;the meeting is already started, and the caller will join it.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="cb74b-135">Windows PowerShell で管理する方法</span><span class="sxs-lookup"><span data-stu-id="cb74b-135">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="cb74b-136">時間を節約したり、複数のユーザーに対してこの動作を自動化したりするには、[Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) コマンドレットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="cb74b-136">To save time or automate this for more than one user, you can use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) cmdlet.</span></span>
    
-  <span data-ttu-id="cb74b-p104">Windows PowerShell の場合、Skype for Business Online はユーザーの管理と、ユーザーが許可されている操作や許可されていない操作の管理に使います。Windows PowerShell により、単一の管理ポイントを使って Office 365 を管理でき、複数の作業を実行する必要があるときに日常業務を合理化できます。Windows PowerShell を使い始めるには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb74b-p104">When it comes to Windows PowerShell, Skype for Business Online is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="cb74b-140">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="cb74b-140">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="cb74b-141">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="cb74b-141">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="cb74b-p105">多くのユーザーの設定を同時に変更するときなどは、Office 365 管理センターのみを使用するよりも、Windows PowerShell の方に、速度、わかりやすさ、生産性の点で多くのメリットがあります。</span><span class="sxs-lookup"><span data-stu-id="cb74b-p105">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time. Learn about these advantages in the following topics:</span></span> 
    
  - <span data-ttu-id="cb74b-144">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time.</span><span class="sxs-lookup"><span data-stu-id="cb74b-144">[An introduction to Windows PowerShell and Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)</span></span>
    
    [<span data-ttu-id="cb74b-145">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="cb74b-145">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="cb74b-146">Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行</span><span class="sxs-lookup"><span data-stu-id="cb74b-146">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="cb74b-p106">[Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="cb74b-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="cb74b-149">このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「Skype for Business Online 用 Windows PowerShell モジュール」からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="cb74b-149">Related topics</span></span>

[<span data-ttu-id="cb74b-150">Office 365 での電話会議を使用または購入する</span><span class="sxs-lookup"><span data-stu-id="cb74b-150">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
