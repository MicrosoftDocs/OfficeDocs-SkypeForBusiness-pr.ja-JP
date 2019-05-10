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
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: ms.teamsadmincenter.audioconferencing.bridgesettings
ms.custom:
- Audio Conferencing
description: 'Skype for Business または Microsoft Teams アプリを使用していない場合に、発信者にメッセージを表示し、会議開催者の名前やピンを集めるために使用される会議ブリッジの設定を変更する際に必要な手順を説明します。 '
ms.openlocfilehash: 2f3f08254409086ee99b3c5f60d243f893fff4e6
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32198561"
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a><span data-ttu-id="561d4-103">電話会議ブリッジの設定を変更する</span><span class="sxs-lookup"><span data-stu-id="561d4-103">Change the settings for an Audio Conferencing bridge</span></span>

<span data-ttu-id="561d4-104">Office 365 で電話会議を設定している場合、電話会議ブリッジと呼ばれるものからユーザーの電話番号を受信します。</span><span class="sxs-lookup"><span data-stu-id="561d4-104">When you are setting up Audio Conferencing in Office 365, you will receive phone numbers for your users from what is called an audio conferencing bridge.</span></span> <span data-ttu-id="561d4-105">電話会議ブリッジには 1 つまたは複数の電話番号を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="561d4-105">A conferencing bridge can contain one or more phone numbers that people will use to call in to a Microsoft Teams meeting.</span></span> <span data-ttu-id="561d4-106">この電話番号は、発信者が会議にダイヤルインするときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="561d4-106">These phone numbers are used when callers dial in to a meeting.</span></span> <span data-ttu-id="561d4-107">電話番号は、Skype for Business または Microsoft Teams の会議出席依頼の下部にあります。</span><span class="sxs-lookup"><span data-stu-id="561d4-107">The phone number is included at the bottom of the Skype for Business or Microsoft Teams meeting invite.</span></span>
  
<span data-ttu-id="561d4-108">電話会議ブリッジは着信に応答し、会議の自動応答を使用して音声案内で発信者を案内し、それから設定に応じて、通知メッセージを再生し、発信者に自分の名前を記録することと、PIN の設定を管理することを求めます。</span><span class="sxs-lookup"><span data-stu-id="561d4-108">The conferencing bridge answers the caller with voice prompts from a conferencing auto attendant, and then, depending on your settings, can play notifications, ask callers to record their name, and set up the PIN security.</span></span> <span data-ttu-id="561d4-109">PIN は 会議の開催者に付与され、Skype for Business または Microsoft Teams のアプリを使用していないときに会議を開始できます。</span><span class="sxs-lookup"><span data-stu-id="561d4-109">PINs are given to meeting organizers to allow them to start a meeting when they are aren't using a Skype for Business or Microsoft Teams app.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="561d4-110">PIN が必要になるのは、Skype for Business または Microsoft Teams のアプリのユーザーがまだ会議を開始していないときの、会議の開催者のみです。</span><span class="sxs-lookup"><span data-stu-id="561d4-110">A PIN is only required for the meeting organizer when a Skype for Business or Microsoft Teams app user hasn't already started the meeting.</span></span> <span data-ttu-id="561d4-111">全員が会議にダイヤルインすると、会議の開催者が会議を開始するために PIN が必要になります。</span><span class="sxs-lookup"><span data-stu-id="561d4-111">If everyone is dialing in to the meeting, the PIN is required for the meeting organizer to start the meeting.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="teams-logo-30x30pngmediateams-logo-30x30png-using-the-microsoft-teams-admin-center"></a>![teams-logo-30x30.png](media/teams-logo-30x30.png) <span data-ttu-id="561d4-113">Microsoft Teams 管理センターの使用</span><span class="sxs-lookup"><span data-stu-id="561d4-113">teams-logo-30x30.pngUsing the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="561d4-114">左側のナビゲーションで、[**会議**]  >  [**会議ブリッジ**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="561d4-114">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="561d4-115">[**会議ブリッジ**] ページの最上部で、[**ブリッジの設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="561d4-115">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span> 

3. <span data-ttu-id="561d4-116">[**ブリッジ設定**] ウィンドウで、</span><span class="sxs-lookup"><span data-stu-id="561d4-116">In the **Bridge settings** pane, select:</span></span> 
   - <span data-ttu-id="561d4-117">[**会議の開始と終了の通知**] を選択します。この選択を外すと、既に参加済みのユーザーは、誰かが入ってきたり退出したりしたときに通知を受け取りません。</span><span class="sxs-lookup"><span data-stu-id="561d4-117">**Enable meeting entry and exit notifications to be turned on** This is selected by default. If you clear this check box, users who have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span></span>
    
     <span data-ttu-id="561d4-118">[**会議の開始と終了通知**] を有効にすると、以下のオプションを選択できます。</span><span class="sxs-lookup"><span data-stu-id="561d4-118">When you turn on **Meeting entry and exit notifications**, you can select these options:</span></span>
    
   - <span data-ttu-id="561d4-119">[**名前または電話番号**] ユーザーが会議にダイヤルインすると、ユーザーの参加時に参加者の電話番号が再生されます。</span><span class="sxs-lookup"><span data-stu-id="561d4-119">**Names or phone numbers** When users dial in to a meeting, their phone number will be played when they join it.</span></span>
    
   - <span data-ttu-id="561d4-120">[**トーン**] ユーザーが会議にダイヤルインすると、ユーザーの参加時にオーディオ トーンが再生されます。</span><span class="sxs-lookup"><span data-stu-id="561d4-120">**Tones** When users dial in to a meeting, an audio tone will be played when they join it.</span></span>
      
   - <span data-ttu-id="561d4-121">[**発信者に会議に参加する前に自分の名前を記録するように要求する**] これをオフにすると、発信者は会議に参加する前に名前を録音するように求められません。</span><span class="sxs-lookup"><span data-stu-id="561d4-121">**Ask callers to record their name before joining the meeting** This is selected by default. If you clear this check box, callers won't be asked to record their name before they join a meeting.</span></span>

4. <span data-ttu-id="561d4-122">電話会議の PIN の長さを設定するには、[**PIN の長さ**] リストの PIN に希望の桁数を選択します。</span><span class="sxs-lookup"><span data-stu-id="561d4-122">To set the PIN length for meetings, select the number of digits you want for the PIN in the **PIN length** list.</span></span>

5. <span data-ttu-id="561d4-123">ユーザーに電子メールを送信するかどうか指定するには、[**電話会議設定を変更した場合ユーザーに自動的に電子メールを送信する**] を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="561d4-123">To specify whether to send email to your users, enable or disable **Automatically send emails to users if their audio conferencing configuration changes**.</span></span>
    <span data-ttu-id="561d4-124">詳細については、「[Microsoft Teams で電話会議の設定を変更したときにユーザーに送信されるメール](emails-sent-to-users-when-their-settings-change-in-teams.md)」または「[Skype for Business Online で設定を変更したときにユーザーに送信されるメール](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="561d4-124">See [Emails automatically sent to users when their Audio Conferencing settings change in Microsoft Teams](emails-sent-to-users-when-their-settings-change-in-teams.md) or [Emails sent to users when their settings change in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) for more information.</span></span>
 
6. <span data-ttu-id="561d4-125">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="561d4-125">Click **Save**.</span></span> 


## <a name="sfb-logo-30x30pngmediasfb-logo-30x30png--using-the-skype-for-business-admin-center"></a>![sfb-logo-30x30.png](media/sfb-logo-30x30.png)  <span data-ttu-id="561d4-127">Skype for Business 管理センターの使用</span><span class="sxs-lookup"><span data-stu-id="561d4-127">Using the Skype for Business admin center</span></span>

 <span data-ttu-id="561d4-128">**発信者が会議に参加するときの会議エクスペリエンスを設定する**</span><span class="sxs-lookup"><span data-stu-id="561d4-128">**Set up the meeting experience when callers join a meeting**</span></span>
    
1. <span data-ttu-id="561d4-129">**Skype for Business 管理センター**の左側のナビゲーション ウィンドウで、[**電話会議**]  >  [**Microsoft ブリッジ設定**] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="561d4-129">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="561d4-130">[**Microsoft ブリッジ設定**] ページの [**会議に参加**] から次を選択します。</span><span class="sxs-lookup"><span data-stu-id="561d4-130">On the **Microsoft bridge settings** page, under **Meeting join experience**, select:</span></span>
    
   - <span data-ttu-id="561d4-131">[**会議の開始と終了の通知を有効にする**] これは既定で選択されています。</span><span class="sxs-lookup"><span data-stu-id="561d4-131">**Enable meeting entry and exit notifications to be turned on** This is selected by default.</span></span> <span data-ttu-id="561d4-132">このチェック ボックスの選択を外すと、誰かが入室したり退出したりしたときに、既に参加済みのユーザーは通知を受け取りません。</span><span class="sxs-lookup"><span data-stu-id="561d4-132">If you clear it, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
   - <span data-ttu-id="561d4-133">[**会議の開始と終了の通知を有効にする**] を選択すると、[**開始または終了のお知らせの種類**] リストから次のオプションを選択できます。</span><span class="sxs-lookup"><span data-stu-id="561d4-133">When you select **Enable meeting entry and exit notifications to be turned on**, you can select these options from the **Entry/exit announcement type** list:</span></span>
    
   - <span data-ttu-id="561d4-134">[**名前または電話番号**] ユーザーが会議にダイヤルインすると、ユーザーの参加時に参加者の電話番号が再生されます。</span><span class="sxs-lookup"><span data-stu-id="561d4-134">**Names or phone numbers** When users dial in to a meeting, their phone number will be played when they join it.</span></span>
    
   - <span data-ttu-id="561d4-135">[**トーン**] ユーザーが会議にダイヤルインすると、ユーザーの参加時にオーディオ トーンが再生されます。</span><span class="sxs-lookup"><span data-stu-id="561d4-135">**Tones** When users dial in to a meeting, an audio tone will be played when they join it.</span></span>
  
   - <span data-ttu-id="561d4-136">[**発信者に会議に参加する前に自分の名前を記録するように要求する**] これは既定で選択されています。</span><span class="sxs-lookup"><span data-stu-id="561d4-136">**Ask callers to record their name before joining the meeting** This is selected by default. If you clear this check box, callers won't be asked to record their name before they join a meeting.</span></span> <span data-ttu-id="561d4-137">チェック ボックスから選択を外すと、発信者が会議に参加する前に自分の名前を記録するよう求められることはありません。</span><span class="sxs-lookup"><span data-stu-id="561d4-137">Ask callers to record their name before joining the meeting This is selected by default. If you clear this check box, callers won't be asked to record their name before they join a meeting.</span></span>
    
3. <span data-ttu-id="561d4-138">変更を完了したら、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="561d4-138">After you make your changes, click **Save**.</span></span>
    
<span data-ttu-id="561d4-139">**In the Skype for Business admin center, in the left navigation go to dial-in conferencingMicrosoft bridge settings.**</span><span class="sxs-lookup"><span data-stu-id="561d4-139">**Set the PIN length for meetings**</span></span>
  
1. <span data-ttu-id="561d4-140">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="561d4-140">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="561d4-141">Go to the **Office 365 admin center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="561d4-141">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="561d4-142">既定値は 5 です。\*\*\*\*\*\*\*\* > \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="561d4-142">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="561d4-143">[**Microsoft ブリッジの設定**] ウィンドウの [**セキュリティ**] で、[**PIN の長さ**] リストに PIN の桁数を入力し、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="561d4-143">Under **Security**, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="561d4-144">PIN は 4 桁から 12 桁の間の値にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="561d4-144">The PIN must be between 4 and 12 digits. The default is 5.</span></span> 
  
<span data-ttu-id="561d4-145">**ユーザーにメールを送信するかどうかを選択する**</span><span class="sxs-lookup"><span data-stu-id="561d4-145">**Select whether to send email to your users**</span></span>
  
1. <span data-ttu-id="561d4-146">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="561d4-146">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="561d4-147">Go to the **Office 365 admin center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="561d4-147">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="561d4-148">既定値は 5 です。\*\*\*\*\*\*\*\* > \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="561d4-148">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="561d4-149">[**Microsoft ブリッジ設定**] ページで [**ダイヤルイン情報を変更したらユーザーに自動的に電子メールを送信する**] を選択または選択解除して [**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="561d4-149">On the **Microsoft bridge settings** page, select or clear **Automatically send emails to users if their dial-in information changes**, and then click **Save**.</span></span>
    
    <span data-ttu-id="561d4-150">詳細については、「[Microsoft Teams で電話会議の設定を変更したときにユーザーに送信されるメール](emails-sent-to-users-when-their-settings-change-in-teams.md)」または「[Skype for Business Online で設定を変更したときにユーザーに送信されるメール](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="561d4-150">See [Emails automatically sent to users when their Audio Conferencing settings change in Microsoft Teams](emails-sent-to-users-when-their-settings-change-in-teams.md) or [Emails sent to users when their settings change in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) for more information.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="561d4-151">Windows PowerShell での管理方法について</span><span class="sxs-lookup"><span data-stu-id="561d4-151">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="561d4-152">時間を節約したり、このプロセスを自動化したりするには、[Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617686) コマンドレットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="561d4-152">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617686) cmdlet.</span></span>
    
- <span data-ttu-id="561d4-p107">Windows PowerShell で行うのは、ユーザーを管理し、ユーザーに何を許可して何を禁止するかを管理することです。Windows PowerShell を利用すると、Office 365 の管理を 1 か所で行うことができるので、複数のタスクを担当する管理者の日常業務を単純化できます。Windows PowerShell の使用を開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="561d4-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="561d4-156">Office 365 PowerShell を使用する必要がある理由</span><span class="sxs-lookup"><span data-stu-id="561d4-156">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="561d4-157">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="561d4-157">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="561d4-p108">多くのユーザーの設定を同時に変更するときなどは、Office 365 管理センターのみを使用するよりも、Windows PowerShell の方に、速度、わかりやすさ、生産性の点で多くのメリットがあります。 次のトピックで、これらの利点を説明します。</span><span class="sxs-lookup"><span data-stu-id="561d4-p108">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="561d4-160">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="561d4-160">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="561d4-161">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="561d4-161">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="561d4-162">Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行</span><span class="sxs-lookup"><span data-stu-id="561d4-162">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="561d4-p109">Skype for Business Online 用の Windows PowerShell モジュールがあれば、Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成できます。このモジュールは、64 ビット版のコンピューターでのみサポートされており、「[Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688)」の Microsoft ダウンロード センターからダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="561d4-p109">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="561d4-165">関連トピック</span><span class="sxs-lookup"><span data-stu-id="561d4-165">Related topics</span></span>

[<span data-ttu-id="561d4-166">Microsoft Teams の電話会議を設定する</span><span class="sxs-lookup"><span data-stu-id="561d4-166">Set up Audio Conferencing for Microsoft Teams</span></span>](set-up-audio-conferencing-in-teams.md)

<span data-ttu-id="561d4-167">[Skype for Business Online 用電話会議を設定する](/skypeforbusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)</span><span class="sxs-lookup"><span data-stu-id="561d4-167">For details, see [Set up Audio Conferencing for Skype for Business and Microsoft Teams](/skypeforbusiness/audio-conferencing-in-office-365/set-up-audio-conferencing).</span></span>
