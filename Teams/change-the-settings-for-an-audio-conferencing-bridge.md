---
title: 電話会議ブリッジの設定を変更する
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 783fad3f-b77c-422b-b91f-7c8b0af324fb
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- ms.teamsadmincenter.audioconferencing.bridgesettings
- seo-marvel-mar2020
description: 入退出通知、名前または電話番号の再生、トーン、発信者に名前の録音を促すメッセージなど、電話会議ブリッジの設定を変更します。
ms.openlocfilehash: 7609ac7639012eb29d6d6cab4b482c1502d27c51
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102644"
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a><span data-ttu-id="ff231-103">電話会議ブリッジの設定を変更する</span><span class="sxs-lookup"><span data-stu-id="ff231-103">Change the settings for an Audio Conferencing bridge</span></span>

<span data-ttu-id="ff231-104">Microsoft 365 または Office 365 で電話会議をセットアップすると、電話会議ブリッジと呼ばれるものからユーザーの電話番号を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="ff231-104">When you are setting up Audio Conferencing in Microsoft 365 or Office 365, you will receive phone numbers for your users from what is called an audio conferencing bridge.</span></span> <span data-ttu-id="ff231-105">電話会議ブリッジには 1 つまたは複数の電話番号を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="ff231-105">A conferencing bridge can contain one or more phone numbers.</span></span> <span data-ttu-id="ff231-106">この電話番号は、発信者が会議にダイヤルインするときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="ff231-106">These phone numbers are used when callers dial in to a meeting.</span></span> <span data-ttu-id="ff231-107">電話番号は、Skype for Business または Microsoft Teams の会議出席依頼の下部にあります。</span><span class="sxs-lookup"><span data-stu-id="ff231-107">The phone number is included at the bottom of the Skype for Business or Microsoft Teams meeting invite.</span></span>
  
<span data-ttu-id="ff231-108">電話会議ブリッジは着信に応答し、会議の自動応答を使用して音声案内で発信者を案内し、それから設定に応じて、通知メッセージを再生し、発信者に自分の名前を記録することと、PIN の設定を管理することを求めます。</span><span class="sxs-lookup"><span data-stu-id="ff231-108">The conferencing bridge answers a call and prompts the caller with voice prompts using a meeting auto attendant, and then, depending on your settings, it can play notifications, ask callers to record their name, and control the PIN settings.</span></span> <span data-ttu-id="ff231-109">PIN は 会議の開催者に付与され、Skype for Business または Microsoft Teams のアプリを使用していないときに会議を開始できます。</span><span class="sxs-lookup"><span data-stu-id="ff231-109">PINs are given to meeting organizers to allow them to start a meeting when they are aren't using a Skype for Business or Microsoft Teams app.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="ff231-110">PIN が必要になるのは、Skype for Business または Microsoft Teams のアプリのユーザーがまだ会議を開始していないときの、会議の開催者のみです。</span><span class="sxs-lookup"><span data-stu-id="ff231-110">A PIN is only required for the meeting organizer when a Skype for Business or Microsoft Teams app user hasn't already started the meeting.</span></span> <span data-ttu-id="ff231-111">全員が会議にダイヤルインすると、会議の開催者が会議を開始するために PIN が必要になります。</span><span class="sxs-lookup"><span data-stu-id="ff231-111">If everyone is dialing in to the meeting, the PIN is required for the meeting organizer to start the meeting.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![Microsoft Teams のロゴが表示されたアイコン](media/teams-logo-30x30.png) <span data-ttu-id="ff231-113">Microsoft Teams 管理センターの使用</span><span class="sxs-lookup"><span data-stu-id="ff231-113">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="ff231-114">左側のナビゲーションで、[**会議**]  >  [**会議ブリッジ**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="ff231-114">In the left navigation, go to **Meetings** > **Conference bridges**.</span></span> 

2. <span data-ttu-id="ff231-115">[**会議ブリッジ**] ページの最上部で、[**ブリッジの設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ff231-115">At the top of the **Conference bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="ff231-116">[**ブリッジ設定**] ウィンドウで、</span><span class="sxs-lookup"><span data-stu-id="ff231-116">In the **Bridge settings** pane, select:</span></span> 
   - <span data-ttu-id="ff231-117">[**会議の開始と終了の通知**] を選択します。この選択を外すと、既に参加済みのユーザーは、誰かが入ってきたり退出したりしたときに通知を受け取りません。</span><span class="sxs-lookup"><span data-stu-id="ff231-117">**Meeting entry and exit notifications** If you turn this off, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
     <span data-ttu-id="ff231-118">[**会議の開始と終了通知**] を有効にすると、以下のオプションを選択できます。</span><span class="sxs-lookup"><span data-stu-id="ff231-118">When you turn on **Meeting entry and exit notifications**, you can select these options:</span></span>
    
   - <span data-ttu-id="ff231-119">[**名前または電話番号**] ユーザーが会議にダイヤルインすると、ユーザーの参加時に参加者の電話番号が再生されます。</span><span class="sxs-lookup"><span data-stu-id="ff231-119">**Names or phone numbers** When users dial in to a meeting, their phone number will be played when they join it.</span></span>
    
   - <span data-ttu-id="ff231-120">[**トーン**] ユーザーが会議にダイヤルインすると、ユーザーの参加時にオーディオ トーンが再生されます。</span><span class="sxs-lookup"><span data-stu-id="ff231-120">**Tones** When users dial in to a meeting, an audio tone will be played when they join it.</span></span>
      
   - <span data-ttu-id="ff231-121">[**発信者に会議に参加する前に自分の名前を記録するように要求する**] これをオフにすると、発信者は会議に参加する前に名前を録音するように求められません。</span><span class="sxs-lookup"><span data-stu-id="ff231-121">**Ask callers to record their name before joining the meeting** If you turn this off, callers won't be asked to record their name before they join a meeting.</span></span>

4. <span data-ttu-id="ff231-122">電話会議の PIN の長さを設定するには、[**PIN の長さ**] リストの PIN に希望の桁数を選択します。</span><span class="sxs-lookup"><span data-stu-id="ff231-122">To set the PIN length for meetings, select the number of digits you want for the PIN in the **PIN length** list.</span></span>

5. <span data-ttu-id="ff231-123">ユーザーに電子メールを送信するかどうか指定するには、[**電話会議設定を変更した場合ユーザーに自動的に電子メールを送信する**] を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="ff231-123">To specify whether to send email to your users, enable or disable **Automatically send emails to users if their audio conferencing configuration changes**.</span></span>
    <span data-ttu-id="ff231-124">詳細については、「[Microsoft Teams で電話会議の設定を変更したときにユーザーに送信されるメール](emails-sent-to-users-when-their-settings-change-in-teams.md)」または「[Skype for Business Online で設定を変更したときにユーザーに送信されるメール](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ff231-124">See [Emails automatically sent to users when their Audio Conferencing settings change in Microsoft Teams](emails-sent-to-users-when-their-settings-change-in-teams.md) or [Emails sent to users when their settings change in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) for more information.</span></span>
 
6. <span data-ttu-id="ff231-125">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ff231-125">Click **Save**.</span></span> 

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="ff231-126">Windows PowerShell での管理方法について</span><span class="sxs-lookup"><span data-stu-id="ff231-126">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="ff231-127">時間を節約したり、このプロセスを自動化したりするには、[Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingBridge) コマンドレットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="ff231-127">To save time or automate this process, you can use the [Set-CsDialinConferencingBridge](/powershell/module/skype/Set-CsOnlineDialInConferencingBridge) cmdlet.</span></span>
    
- <span data-ttu-id="ff231-128">Windows PowerShellは、ユーザーの管理と、ユーザーに許可する操作と許可しない操作の管理に使います。</span><span class="sxs-lookup"><span data-stu-id="ff231-128">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="ff231-129">Windows PowerShell では、単一の管理ポイントを使用して Microsoft 365 または Office 365 を管理できます。複数のタスクを実行する必要がある場合に毎日の作業を簡略化できます。</span><span class="sxs-lookup"><span data-stu-id="ff231-129">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="ff231-130">Windows PowerShell の使用を開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ff231-130">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="ff231-131">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="ff231-131">Why you need to use Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="ff231-132">[Microsoft 365 または Office 365 を管理するための最適Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="ff231-132">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
- <span data-ttu-id="ff231-133">Windows PowerShellは、多くのユーザーに対して一度に設定変更を行う場合など、Microsoft 365 管理センターのみを使用する場合と同様に、速度、シンプルさ、生産性に多くの利点があります。</span><span class="sxs-lookup"><span data-stu-id="ff231-133">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="ff231-134">次のトピックで、これらの利点を説明します。</span><span class="sxs-lookup"><span data-stu-id="ff231-134">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="ff231-135">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="ff231-135">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  - [<span data-ttu-id="ff231-136">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="ff231-136">Using Windows PowerShell to manage Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  - [<span data-ttu-id="ff231-137">Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行</span><span class="sxs-lookup"><span data-stu-id="ff231-137">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
    > [!NOTE]
    > <span data-ttu-id="ff231-p107">Skype for Business Online 用の Windows PowerShell モジュールがあれば、Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成できます。このモジュールは、64 ビット版のコンピューターでのみサポートされており、「[Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688)」の Microsoft ダウンロード センターからダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="ff231-p107">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="ff231-140">関連トピック</span><span class="sxs-lookup"><span data-stu-id="ff231-140">Related topics</span></span>

[<span data-ttu-id="ff231-141">Microsoft Teams の電話会議を設定する</span><span class="sxs-lookup"><span data-stu-id="ff231-141">Set up Audio Conferencing for Microsoft Teams</span></span>](set-up-audio-conferencing-in-teams.md)

[<span data-ttu-id="ff231-142">Skype for Business Online 用電話会議を設定する</span><span class="sxs-lookup"><span data-stu-id="ff231-142">Set up Audio Conferencing for Skype for Business Online</span></span>](/skypeforbusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)