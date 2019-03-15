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
description: '呼び出し元のメッセージを表示し、ビジネスまたはマイクロソフトのチームのアプリケーションの Skype を使用していないことと、名前と会議の開催者のピンを収集するために使用する会議用ブリッジの設定を変更する必要があります手順を取得します。 '
ms.openlocfilehash: 2f3f08254409086ee99b3c5f60d243f893fff4e6
ms.sourcegitcommit: bc2b227b4ac0a9521993f808a1361b4f9bc7faad
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "30633234"
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a><span data-ttu-id="12773-103">電話会議ブリッジの設定を変更する</span><span class="sxs-lookup"><span data-stu-id="12773-103">Change the settings for an Audio Conferencing bridge</span></span>

<span data-ttu-id="12773-104">Office 365 に電話会議を設定する場合、オーディオ会議ブリッジと呼ばれますから、ユーザーの電話番号が表示されます。</span><span class="sxs-lookup"><span data-stu-id="12773-104">When you are setting up Audio Conferencing in Office 365, you will receive phone numbers for your users from what is called an audio conferencing bridge.</span></span> <span data-ttu-id="12773-105">会議用ブリッジは、1 つまたは複数の電話番号を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="12773-105">A conferencing bridge can contain one or more phone numbers.</span></span> <span data-ttu-id="12773-106">これらの電話番号は、呼び出し元が、会議にダイヤルインするときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="12773-106">These phone numbers are used when callers dial in to a meeting.</span></span> <span data-ttu-id="12773-107">電話番号では、ビジネスまたはマイクロソフトのチームの会議出席依頼の Skype の下部に含まれています。</span><span class="sxs-lookup"><span data-stu-id="12773-107">The phone number is included at the bottom of the Skype for Business or Microsoft Teams meeting invite.</span></span>
  
<span data-ttu-id="12773-108">会議用ブリッジが呼び出しに応答し、会議自動アテンダント、およびその後、設定によってを使用して音声メッセージを呼び出し元を確認できます通知を再生、自分の名前を記録するための呼び出し元を確認、暗証番号 (pin) の設定を制御します。</span><span class="sxs-lookup"><span data-stu-id="12773-108">The conferencing bridge answers a call and prompts the caller with voice prompts using a meeting auto attendant, and then, depending on your settings, it can play notifications, ask callers to record their name, and control the PIN settings.</span></span> <span data-ttu-id="12773-109">ピンはされたミーティングの開催者に許可するように、会議を開始するが使用していない、Skype アプリのビジネスまたはマイクロソフトのチームにします。</span><span class="sxs-lookup"><span data-stu-id="12773-109">PINs are given to meeting organizers to allow them to start a meeting when they are aren't using a Skype for Business or Microsoft Teams app.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="12773-110">PIN がだけが必要なとき、Skype アプリケーション ユーザーのビジネスまたはマイクロソフトのチームの会議の開催者が会議を既に開始していません。</span><span class="sxs-lookup"><span data-stu-id="12773-110">A PIN is only required for the meeting organizer when a Skype for Business or Microsoft Teams app user hasn't already started the meeting.</span></span> <span data-ttu-id="12773-111">場合はすべてのユーザーがダイヤルイン会議、暗証番号 (pin) は会議の開催者、会議を開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="12773-111">If everyone is dialing in to the meeting, the PIN is required for the meeting organizer to start the meeting.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="teams-logo-30x30pngmediateams-logo-30x30png-using-the-microsoft-teams-admin-center"></a>![チーム ・ ロゴ ・ 30x30.png](media/teams-logo-30x30.png) <span data-ttu-id="12773-113">マイクロソフトのチーム管理センターを使用してください。</span><span class="sxs-lookup"><span data-stu-id="12773-113">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="12773-114">左側のナビゲーションでは、**会議**に移動 > **会議ブリッジ**です。</span><span class="sxs-lookup"><span data-stu-id="12773-114">In the left navigation, go to **Meetings** > **Conference bridges**.</span></span> 

2. <span data-ttu-id="12773-115">**会議ブリッジ**のページの上部には、**ブリッジの設定**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="12773-115">At the top of the **Conference bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="12773-116">**ブリッジの設定**ウィンドウで、次のコマンドを選択します。</span><span class="sxs-lookup"><span data-stu-id="12773-116">In the **Bridge settings** pane, select:</span></span> 
   - <span data-ttu-id="12773-117">**ミーティングのエントリと終了の通知**場合はこのオプションをオフにすると、データを入力したり、会議を離れると、会議に参加しているユーザーが通知はありません。</span><span class="sxs-lookup"><span data-stu-id="12773-117">**Meeting entry and exit notifications** If you turn this off, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
     <span data-ttu-id="12773-118">**会議の開始と終了の通知**を有効にするときは、これらのオプションを選択できます。</span><span class="sxs-lookup"><span data-stu-id="12773-118">When you turn on **Meeting entry and exit notifications**, you can select these options:</span></span>
    
   - <span data-ttu-id="12773-119">**名前や電話番号**ユーザーが会議にダイヤルインするときは、それに参加するときに、電話番号が再生されます。</span><span class="sxs-lookup"><span data-stu-id="12773-119">**Names or phone numbers** When users dial in to a meeting, their phone number will be played when they join it.</span></span>
    
   - <span data-ttu-id="12773-120">**トーン**ユーザーが会議にダイヤルインするときは、それに参加するときに、オーディオの音が再生されます。</span><span class="sxs-lookup"><span data-stu-id="12773-120">**Tones** When users dial in to a meeting, an audio tone will be played when they join it.</span></span>
      
   - <span data-ttu-id="12773-121">**ミーティングに参加する前に自分の名前を記録する呼び出し元を確認**このオプションをオフにすると場合、は、会議に参加する前に自分の名前を記録するための呼び出し元を求められますされません。</span><span class="sxs-lookup"><span data-stu-id="12773-121">**Ask callers to record their name before joining the meeting** If you turn this off, callers won't be asked to record their name before they join a meeting.</span></span>

4. <span data-ttu-id="12773-122">会議の暗証番号 (pin) の長さを設定するには、**暗証番号 (pin) の長さ**] ボックスの一覧に PIN の桁数を選択します。</span><span class="sxs-lookup"><span data-stu-id="12773-122">To set the PIN length for meetings, select the number of digits you want for the PIN in the **PIN length** list.</span></span>

5. <span data-ttu-id="12773-123">ユーザーに電子メールを送信するかどうかを指定するには、有効または **、オーディオ会議の構成が変更された場合、ユーザーに e メールを自動的に送信**を無効にします。</span><span class="sxs-lookup"><span data-stu-id="12773-123">To specify whether to send email to your users, enable or disable **Automatically send emails to users if their audio conferencing configuration changes**.</span></span>
    <span data-ttu-id="12773-124">詳細については、[マイクロソフトのチームで、オーディオ会議の設定を変更する場合にユーザーに自動的に電子メールの送信](emails-sent-to-users-when-their-settings-change-in-teams.md)または[Skype のオンライン ビジネスでの設定を変更するときにユーザーに送信された電子メール](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="12773-124">See [Emails automatically sent to users when their Audio Conferencing settings change in Microsoft Teams](emails-sent-to-users-when-their-settings-change-in-teams.md) or [Emails sent to users when their settings change in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) for more information.</span></span>
 
6. <span data-ttu-id="12773-125">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="12773-125">Click **Save**.</span></span> 


## <a name="sfb-logo-30x30pngmediasfb-logo-30x30png--using-the-skype-for-business-admin-center"></a>![sfb-logo-30x30.png](media/sfb-logo-30x30.png)  <span data-ttu-id="12773-127">Skype for Business 管理センターを使用する</span><span class="sxs-lookup"><span data-stu-id="12773-127">Using the Skype for Business admin center</span></span>

 <span data-ttu-id="12773-128">**呼び出し元がミーティングに参加するときに会議の経験を設定します。**</span><span class="sxs-lookup"><span data-stu-id="12773-128">**Set up the meeting experience when callers join a meeting**</span></span>
    
1. <span data-ttu-id="12773-129">**ビジネス管理センターの Skype**では、左側のナビゲーションで移動**電話会議**に > **Microsoft ブリッジ設定**します。</span><span class="sxs-lookup"><span data-stu-id="12773-129">In the **Skype for Business admin center**, in the left navigation go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="12773-130">**Microsoft ブリッジの設定**ページで、[**会議参加の経験**をするには、次のコマンドを選択します。</span><span class="sxs-lookup"><span data-stu-id="12773-130">On the **Microsoft bridge settings** page, under **Meeting join experience**, select:</span></span>
    
   - <span data-ttu-id="12773-131">**会議エントリを有効にして終了の通知をオンにする**これがデフォルトで選択されます。</span><span class="sxs-lookup"><span data-stu-id="12773-131">**Enable meeting entry and exit notifications to be turned on** This is selected by default.</span></span> <span data-ttu-id="12773-132">チェック ボックスをオフにするとデータを入力したり、会議を離れると、会議に参加しているユーザーが通知はありません。</span><span class="sxs-lookup"><span data-stu-id="12773-132">If you clear the check box, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
   - <span data-ttu-id="12773-133">**会議エントリを有効にして終了の通知をオンにする**を選択すると、**開始/終了のお知らせの種類**] ボックスの一覧からこれらのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="12773-133">When you select **Enable meeting entry and exit notifications to be turned on**, you can select these options from the **Entry/exit announcement type** list:</span></span>
    
   - <span data-ttu-id="12773-134">**名前や電話番号**ユーザーが会議にダイヤルインするときは、それに参加するときに、電話番号が再生されます。</span><span class="sxs-lookup"><span data-stu-id="12773-134">**Names or phone numbers** When users dial in to a meeting, their phone number will be played when they join it.</span></span>
    
   - <span data-ttu-id="12773-135">**トーン**ユーザーが会議にダイヤルインするときは、それに参加するときに、オーディオの音が再生されます。</span><span class="sxs-lookup"><span data-stu-id="12773-135">**Tones** When users dial in to a meeting, an audio tone will be played when they join it.</span></span>
  
   - <span data-ttu-id="12773-136">**ミーティングに参加する前に自分の名前を記録する呼び出し元を確認**これがデフォルトで選択されます。</span><span class="sxs-lookup"><span data-stu-id="12773-136">**Ask callers to record their name before joining the meeting** This is selected by default.</span></span> <span data-ttu-id="12773-137">チェック ボックスをオフにした場合は、会議に参加する前に自分の名前を記録する呼び出し元を求められますされません。</span><span class="sxs-lookup"><span data-stu-id="12773-137">If you clear the check box, callers won't be asked to record their name before they join a meeting.</span></span>
    
3. <span data-ttu-id="12773-138">Sign in to Office 365 with your work or school account.\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="12773-138">After you make your changes, click **Save**.</span></span>
    
<span data-ttu-id="12773-139">**In the Skype for Business admin center, in the left navigation go to dial-in conferencingMicrosoft bridge settings.**</span><span class="sxs-lookup"><span data-stu-id="12773-139">**Set the PIN length for meetings**</span></span>
  
1. <span data-ttu-id="12773-140">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="12773-140">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="12773-141">Sign in to Office 365 with your work or school account.\*\*\*\* > \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="12773-141">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="12773-142">既定値は 5 です。\*\*\*\*\*\*\*\* > \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="12773-142">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="12773-143">**Microsoft ブリッジの設定**] ページの [**セキュリティ**] の下に**暗証番号 (pin) の長さ**] ボックスの一覧で、[暗証番号 (pin) に使用桁の番号を入力し、し、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="12773-143">On the **Microsoft bridge settings** page, under **Security**, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="12773-144">暗証番号 (pin) は、4 桁から 12 桁の間である必要があります。</span><span class="sxs-lookup"><span data-stu-id="12773-144">The PIN must be between 4 and 12 digits.</span></span> 
  
<span data-ttu-id="12773-145">**ユーザーに電子メールを送信するかどうかを選択します。**</span><span class="sxs-lookup"><span data-stu-id="12773-145">**Select whether to send email to your users**</span></span>
  
1. <span data-ttu-id="12773-146">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="12773-146">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="12773-147">Sign in to Office 365 with your work or school account.\*\*\*\* > \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="12773-147">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="12773-148">既定値は 5 です。\*\*\*\*\*\*\*\* > \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="12773-148">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="12773-149">**Microsoft ブリッジの設定**] ページで、選択や**ダイヤルイン情報を変更した場合、ユーザーに e メールを自動的に送信**を、し、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="12773-149">On the **Microsoft bridge settings** page, select or clear **Automatically send emails to users if their dial-in information changes**, and then click **Save**.</span></span>
    
    <span data-ttu-id="12773-150">詳細については、[マイクロソフトのチームで、オーディオ会議の設定を変更する場合にユーザーに自動的に電子メールの送信](emails-sent-to-users-when-their-settings-change-in-teams.md)または[Skype のオンライン ビジネスでの設定を変更するときにユーザーに送信された電子メール](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="12773-150">See [Emails automatically sent to users when their Audio Conferencing settings change in Microsoft Teams](emails-sent-to-users-when-their-settings-change-in-teams.md) or [Emails sent to users when their settings change in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) for more information.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="12773-151">Go to the Office 365 admin centerSkype for Business.</span><span class="sxs-lookup"><span data-stu-id="12773-151">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="12773-152">時間を節約またはこのプロセスを自動化するには、[セット CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686)コマンドレットを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="12773-152">To save time or automate this process, you can use the [Set-CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686) cmdlet.</span></span>
    
- <span data-ttu-id="12773-p107">Windows PowerShell は、ユーザーと、ユーザーに許可されていることと許可されていないことを管理するためにあるということです。Windows PowerShell があれば、一元管理を使用して Office 365 を管理し、複数のタスクを抱えているときに、日常の仕事を簡素化することができます。Windows PowerShell を開始するには、これらのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="12773-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="12773-156">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="12773-156">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="12773-157">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="12773-157">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="12773-p108">多くのユーザーの設定を同時に変更するときなどは、Office 365 管理センターのみを使用するよりも、Windows PowerShell の方に、速度、わかりやすさ、生産性の点で多くのメリットがあります。 次のトピックで、これらの利点を説明します。</span><span class="sxs-lookup"><span data-stu-id="12773-p108">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="12773-160">Windows PowerShell と Lync Online の概要</span><span class="sxs-lookup"><span data-stu-id="12773-160">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="12773-161">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="12773-161">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="12773-162">Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行</span><span class="sxs-lookup"><span data-stu-id="12773-162">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="12773-p109">Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行[](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="12773-p109">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="12773-165">このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「Skype for Business Online 用 Windows PowerShell モジュール」からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="12773-165">Related topics</span></span>

[<span data-ttu-id="12773-166">マイクロソフト チームの電話会議を設定します</span><span class="sxs-lookup"><span data-stu-id="12773-166">Set up Audio Conferencing for Microsoft Teams</span></span>](set-up-audio-conferencing-in-teams.md)

[<span data-ttu-id="12773-167">オンライン ビジネスの Skype の電話会議を設定します。</span><span class="sxs-lookup"><span data-stu-id="12773-167">Set up Audio Conferencing for Skype for Business Online</span></span>](/skypeforbusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)
