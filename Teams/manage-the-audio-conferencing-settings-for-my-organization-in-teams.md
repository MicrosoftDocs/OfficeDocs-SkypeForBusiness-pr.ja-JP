---
title: 電話会議の設定を管理する
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: bc9bd328-c5b2-44e5-af15-e02bf00e1c81
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
- m365initiative-meetings
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 'ダイヤルイン電話会議ライセンスと会議 ID をユーザーおよびその他の多くのダイヤルイン電話会議の設定に割り当てるための Microsoft Teams での手順を確認します。 '
ms.openlocfilehash: f2d056ffd2c3b40b8e39f6d4727859b45e675ebf
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031803"
---
# <a name="manage-the-audio-conferencing-settings-for-your-organization-in-microsoft-teams"></a><span data-ttu-id="90835-103">Microsoft Teams で組織の電話会議の設定を管理する</span><span class="sxs-lookup"><span data-stu-id="90835-103">Manage the Audio Conferencing settings for your organization in Microsoft Teams</span></span>

<span data-ttu-id="90835-104">1 つの場所で Microsoft Teams のすべての電話会議設定を確認することが、より簡単になります。</span><span class="sxs-lookup"><span data-stu-id="90835-104">It might be easier for you to see all of the audio conferencing settings for Microsoft Teams in one place.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="assign-an-audio-conferencing-license"></a><span data-ttu-id="90835-105">電話会議のライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="90835-105">Assign an Audio Conferencing license</span></span>

> [!NOTE]
> <span data-ttu-id="90835-106">Teams を使用してライセンスを割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="90835-106">You can't assign licenses using Teams.</span></span> <span data-ttu-id="90835-107">Microsoft 365 管理センターを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="90835-107">You must use the Microsoft 365 admin center.</span></span> <span data-ttu-id="90835-108">「 [Microsoft Teams のアドオンライセンスを割り当てる](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="90835-108">See [Assign Microsoft Teams add-on licenses](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing).</span></span> 
  
 <span data-ttu-id="90835-109">**ユーザーにライセンスを割り当てる**</span><span class="sxs-lookup"><span data-stu-id="90835-109">**To assign a license for a user**</span></span>
  
1. <span data-ttu-id="90835-110">職場または学校のアカウントを使用して、Microsoft 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="90835-110">Sign in to Microsoft 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="90835-111">**Microsoft 365 管理センター** の左のナビゲーションで、[ユーザーの **Users**  >  **アクティブな** ユーザー] に移動し、利用可能なユーザーのリストからユーザー (複数可) を選びます。</span><span class="sxs-lookup"><span data-stu-id="90835-111">In the left navigation of the **Microsoft 365 admin center** , go to **Users** > **Active users** , and then select the user or users from the list of available users.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="90835-112">操作手順と PowerShell のサンプル スクリプトについては、「 **Skype for Business と Microsoft Teams のライセンスを割り当てる** 」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="90835-112">If you are assigning licenses to up to 20 users at the same time, you can use the **Select a view** drop-down then choose one of the options or create your own view.</span></span> <span data-ttu-id="90835-113">次に [ **編集** ]、[ **次へ** ] を 2 回クリックしてからライセンスを選択し、[ **送信** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="90835-113">Then click **Edit** , **Next** twice then select the license and click **Submit**.</span></span>  
  
3. <span data-ttu-id="90835-114">操作ウィンドウの [ **製品ライセンス** ] で [ **編集** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="90835-114">In the Action pane under **Product licenses** , click **Edit**.</span></span> 
    
4. <span data-ttu-id="90835-p103">[ **製品ライセンス** ] ページで、[ **電話会議** ] を有効にし、[ **保存** ] をクリックします。ライセンスの詳細については、「 [Microsoft Teams アドオン ライセンス](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="90835-p103">On the **Product Licenses** page, turn on **Audio Conferencing** and then click **Save**. For more on licensing, see [Microsoft Teams add-on licensing](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing).</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="90835-p104">ライセンスを割り当てた後は、リストの最初の電話会議プロバイダーとして Microsoft が表示されない可能性があります。この問題が発生した場合は、管理センターからログアウトするか、CTRL キーを押しながら F5 キーを押してブラウザーウィンドウを更新してください。</span><span class="sxs-lookup"><span data-stu-id="90835-p104">After you assign the license, Microsoft might not appear initially in the list as an audio conferencing provider. If this happens, either log out of the admin center or press CTRL+F5 to refresh the browser window.</span></span> 
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a><span data-ttu-id="90835-119">電話会議ユーザーに送信されたメールを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="90835-119">Enable or disable emails sent to audio conferencing users</span></span>

<span data-ttu-id="90835-120">![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**</span><span class="sxs-lookup"><span data-stu-id="90835-120">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="90835-121">左側のナビゲーションで、[ **会議** ]  >  [ **会議ブリッジ** ] に移動します。</span><span class="sxs-lookup"><span data-stu-id="90835-121">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="90835-122">[ **会議ブリッジ** ] ページの最上部で、[ **ブリッジの設定** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="90835-122">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="90835-123">[ **ブリッジの設定** ] ペインで、[ **ダイヤルイン設定が変わると、ユーザーに自動的に電子メールが送信されます** ] を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="90835-123">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="90835-124">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="90835-124">Click **Save**.</span></span>

    
<span data-ttu-id="90835-125">**Windows PowerShell を使用する**</span><span class="sxs-lookup"><span data-stu-id="90835-125">**Using Windows PowerShell**</span></span>
  
<span data-ttu-id="90835-126">詳細については、[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="90835-126">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="reset-the-meeting-conference-id"></a><span data-ttu-id="90835-127">会議通話 ID をリセットする</span><span class="sxs-lookup"><span data-stu-id="90835-127">Reset the meeting conference ID</span></span>

<span data-ttu-id="90835-128">![](media/teams-logo-30x30.png) **Microsoft teams 管理センターを使用し** た Teams のロゴを示すアイコン</span><span class="sxs-lookup"><span data-stu-id="90835-128">![An icon showing the Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="90835-129">左側のナビゲーションで、[ **ユーザー** ] をクリックしてから、空いているユーザーのリストからユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="90835-129">In the left navigation, click **Users** , and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="90835-130">[ **電話会議** ] で [ **会議通話 ID のリセット** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="90835-130">Under **Audio Conferencing** , click **Reset conference ID**.</span></span>  

3. <span data-ttu-id="90835-131">[ **会議通話 ID のリセット** ] ウィンドウで、[ **リセット** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="90835-131">In the **Reset conference ID?** window, click **Reset**.</span></span> <span data-ttu-id="90835-132">ユーザーに電子メールを送信することが有効になっている場合、会議通話 ID は自動的に作成され、新しい会議通話 ID が記載された電子メールがユーザーに送信されます。</span><span class="sxs-lookup"><span data-stu-id="90835-132">A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled.</span></span> <span data-ttu-id="90835-133">これは既定では有効になっています。</span><span class="sxs-lookup"><span data-stu-id="90835-133">It's enabled by default.</span></span>

<span data-ttu-id="90835-134">「[ユーザーの会議通話 ID をリセットする](reset-a-conference-id-for-a-user-in-teams.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="90835-134">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user-in-teams.md).</span></span>
  
## <a name="reset-a-conference-organizers-pin"></a><span data-ttu-id="90835-135">会議通話の開催者の PIN をリセットする</span><span class="sxs-lookup"><span data-stu-id="90835-135">Reset a conference organizer's PIN</span></span>

<span data-ttu-id="90835-136">ユーザーがスケジュール設定した各会議には、一意の会議通話 ID が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="90835-136">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="90835-137">会議通話 ID は自動的に作成されユーザーに割り当てられますが、ユーザーは使わないため特定の番号に設定しようと考える場合や、ユーザーが会議通話 ID を覚えられない、または紛失してしまう場合があります。</span><span class="sxs-lookup"><span data-stu-id="90835-137">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or your users can't remember or have lost their conference ID.</span></span> 

<span data-ttu-id="90835-138">![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**</span><span class="sxs-lookup"><span data-stu-id="90835-138">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="90835-139">左側のナビゲーションで、[ **ユーザー** ] をクリックしてから、空いているユーザーのリストからユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="90835-139">In the left navigation, click **Users** , and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="90835-140">[ **電話会議** ] で、[ **PIN のリセット** ] をクリックしてから [ **リセット** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="90835-140">Under **Audio Conferencing** , click **Reset PIN** , and then click **Reset**.</span></span> 
  
<span data-ttu-id="90835-p107">ユーザーは、電話会議の PIN が有効になっているか、PIN が再設定されている場合、自分の PIN を使ってメールを受け取れます。しかし、自動で送信するメールが無効になっている場合、 PIN リセットのメールは送信されませんので、手動でユーザーに前述の PIN を送信する必要があります。 PIN が再設定されるとその PIN は一度だけ表示されます。再設定された直後に表示された後、その PIN はユーザーのプロパティ上に表示されることはなく、その代わりに \*\*\*\*\* と表示されます。</span><span class="sxs-lookup"><span data-stu-id="90835-p107">Users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset. But if you have disabled automatically sending emails, a PIN reset email won't be sent and you will have to manually send the PIN to the user. The PIN will only be shown once after it has been reset. After it's displayed just after being reset, the PIN won't be shown anymore on the user properties; instead, \*\*\*\*\* will be shown.</span></span> 
  
<span data-ttu-id="90835-145">「[電話会議の PIN をリセットする](reset-the-audio-conferencing-pin-in-teams.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="90835-145">See [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin-in-teams.md).</span></span>
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="90835-146">電話会議の情報が記載された電子メールをユーザーに送信する</span><span class="sxs-lookup"><span data-stu-id="90835-146">Send an email with Audio Conferencing information to a user</span></span>

<span data-ttu-id="90835-147">![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**</span><span class="sxs-lookup"><span data-stu-id="90835-147">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="90835-148">左側のナビゲーションで、[ **ユーザー** ] をクリックしてから、空いているユーザーのリストからユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="90835-148">In the left navigation, click **Users** , and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="90835-149">[ **電話会議** ] の下で、[ **電話会議情報をメールで送信** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="90835-149">Under **Audio Conferencing** , click **Send conference info in email**.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="90835-150">この操作を行っても、電話会議の PIN はユーザーに送信されません。</span><span class="sxs-lookup"><span data-stu-id="90835-150">When you do this, the audio conferencing PIN isn't sent to the user.</span></span> 

<span data-ttu-id="90835-151">「[電話会議の情報が記載された電子メールをユーザーに送信する](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="90835-151">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).</span></span>
  
## <a name="set-the-phone-numbers-included-on-invites"></a><span data-ttu-id="90835-152">招待状に含まれている電話番号を設定する</span><span class="sxs-lookup"><span data-stu-id="90835-152">Set the phone numbers included on invites</span></span>

<span data-ttu-id="90835-153">![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**</span><span class="sxs-lookup"><span data-stu-id="90835-153">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="90835-154">左側のナビゲーションで、[ **ユーザー** ] をクリックしてから、空いているユーザーのリストからユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="90835-154">In the left navigation, click **Users** , and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="90835-155">[ **電話会議** ] の横の [ **編集** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="90835-155">Next to **Audio Conferencing** , click **Edit**.</span></span>
 
3. <span data-ttu-id="90835-156">[ **電話会議** ] ウィンドウで、[ **有料電話番号** ] と、可能な場合は [ **フリーダイヤル番号** ] を設定できます。</span><span class="sxs-lookup"><span data-stu-id="90835-156">In the **Audio Conferencing** pane, you can set the **Toll number** and, if allowed, the **Toll-free number**.</span></span>

4. <span data-ttu-id="90835-157">[ **保存** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="90835-157">Click **Save**.</span></span>
    
<span data-ttu-id="90835-158">「[招待状に含まれている電話番号を設定する](set-the-phone-numbers-included-on-invites-in-teams.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="90835-158">See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites-in-teams.md).</span></span>
  
  
## <a name="choose-audio-conferencing-bridge-settings"></a><span data-ttu-id="90835-159">電話会議ブリッジの設定を選択する</span><span class="sxs-lookup"><span data-stu-id="90835-159">Choose audio conferencing bridge settings</span></span>

<span data-ttu-id="90835-160">**発信者が会議に参加するときの会議エクスペリエンスを設定する**</span><span class="sxs-lookup"><span data-stu-id="90835-160">**Set the meeting experience when callers join a meeting**</span></span>

<span data-ttu-id="90835-161">![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**</span><span class="sxs-lookup"><span data-stu-id="90835-161">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="90835-162">左側のナビゲーションで、[ **会議** ]  >  [ **会議ブリッジ** ] に移動します。</span><span class="sxs-lookup"><span data-stu-id="90835-162">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="90835-163">[ **会議ブリッジ** ] ページの最上部で、[ **ブリッジの設定** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="90835-163">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="90835-164">[ **ブリッジの設定** ] ウィンドウで、[ **会議の開始と終了の通知** ] を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="90835-164">In the **Bridge settings** pane, enable or disable **Meeting entry and exit notifications**.</span></span>

    <span data-ttu-id="90835-165">これは既定では有効になっています。</span><span class="sxs-lookup"><span data-stu-id="90835-165">This is enabled by default.</span></span> <span data-ttu-id="90835-166">このオプションを無効にすると、既定ですでに会議に参加済みのユーザーは、誰かが入ってきたり退出したりしたときに通知を受け取りません。</span><span class="sxs-lookup"><span data-stu-id="90835-166">If you disable this option, users who have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span></span>

4. <span data-ttu-id="90835-167">[ **開始/終了のお知らせの種類** ] で、[ **トーン** ] または [ **名前または電話番号** ] のどちらかを選びます。</span><span class="sxs-lookup"><span data-stu-id="90835-167">Under **Entry/exit announcement type** , choose either **Tones** or **Names or phone numbers**.</span></span> 

    <span data-ttu-id="90835-168">[ **名前または電話番号** ] を選ぶと、[ **発信者に会議に参加する前に自分の名前を記録するように要求する** ] を有効または無効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="90835-168">If you choose **Names or phone numbers** , you can also choose to enable or disable **Ask callers to record their name before joining the meeting**.</span></span> 
    > [!NOTE]
    > <span data-ttu-id="90835-169">既定では、外部参加者はダイヤルイン参加者の電話番号を表示することはできません。</span><span class="sxs-lookup"><span data-stu-id="90835-169">By default, external participants can't see the phone numbers of dialed-in participants.</span></span> <span data-ttu-id="90835-170">これらの電話番号のプライバシーを維持したい場合は、 **開始/終了のお知らせの種類** の **トーン** を選びます (これにより、数字が Teams によって読み上げられません)。</span><span class="sxs-lookup"><span data-stu-id="90835-170">If you want to maintain the privacy of these phone numbers, select **Tones** for **Entry/exit announcement type** (this prevents the numbers from being read out by Teams).</span></span>


5. <span data-ttu-id="90835-171">[ **保存** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="90835-171">Click **Save**.</span></span>

    
<span data-ttu-id="90835-172">[電話会議ブリッジの設定を変更する](change-the-settings-for-an-audio-conferencing-bridge.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="90835-172">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>
  
 <span data-ttu-id="90835-173">**会議の PIN の長さを設定する**</span><span class="sxs-lookup"><span data-stu-id="90835-173">**Set the PIN length for meetings**</span></span>

1. <span data-ttu-id="90835-174">左側のナビゲーションで、[ **会議** ]  >  [ **会議ブリッジ** ] に移動します。</span><span class="sxs-lookup"><span data-stu-id="90835-174">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="90835-175">[ **会議ブリッジ** ] ページの最上部で、[ **ブリッジの設定** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="90835-175">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="90835-176">[ **ブリッジの設定** ] ウィンドウで、[ **PIN の長さ** ] リストに PIN の桁数を入力し、[ **保存** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="90835-176">In the **Bridge settings** pane, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>

    <span data-ttu-id="90835-p110">PIN は 4 桁から 12 桁の間の値にする必要があります。既定値は 5 桁です。</span><span class="sxs-lookup"><span data-stu-id="90835-p110">The PIN must be between 4 and 12 digits. The default is 5.</span></span>

    
<span data-ttu-id="90835-179">職場または学校のアカウントを使用して、Office 365 にサインインします。[](change-the-settings-for-an-audio-conferencing-bridge.md)</span><span class="sxs-lookup"><span data-stu-id="90835-179">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>
  
 <span data-ttu-id="90835-180">**電話会議 ユーザーに送信されているメールを有効または無効にする**</span><span class="sxs-lookup"><span data-stu-id="90835-180">**Enable or disable email from being sent to audio users**</span></span>

1. <span data-ttu-id="90835-181">左側のナビゲーションで、[ **会議** ]  >  [ **会議ブリッジ** ] に移動します。</span><span class="sxs-lookup"><span data-stu-id="90835-181">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="90835-182">[ **会議ブリッジ** ] ページの最上部で、[ **ブリッジの設定** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="90835-182">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="90835-183">[ **ブリッジの設定** ] ペインで、[ **電話会議設定を変更した場合ユーザーに自動的に電子メールを送信する** ] を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="90835-183">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their audio conferencing settings change**.</span></span>

4. <span data-ttu-id="90835-184">[ **保存** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="90835-184">Click **Save**.</span></span> 
 
    <span data-ttu-id="90835-185">電話会議設定をメールでユーザーに送ることもできます。その場合は、ユーザーの電話会議プロパティに移動して、[ **電話会議情報を電子メールで送信する** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="90835-185">You can also send email to the user with the audio conferencing settings, by going to the user's audio conferencing properties and clicking **Send conference info in email**.</span></span>
    
    <span data-ttu-id="90835-186">この操作を行うと、会議 ID と電話会議の番号のみが含まれるメールが送信されますが、そのメールに PIN は含まれません。</span><span class="sxs-lookup"><span data-stu-id="90835-186">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span></span>

<span data-ttu-id="90835-187">「[電話会議の情報が記載された電子メールをユーザーに送信する](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="90835-187">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).</span></span>
    
## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a><span data-ttu-id="90835-188">電話会議ブリッジの第 1 (既定) 言語と第 2 (代替) 言語を表示、設定する</span><span class="sxs-lookup"><span data-stu-id="90835-188">See and set the primary (default) and secondary (alternate) languages on an audio conferencing bridge</span></span>

<span data-ttu-id="90835-189">![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**</span><span class="sxs-lookup"><span data-stu-id="90835-189">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="90835-190">左側のナビゲーションで、[ **会議** ]  >  [ **会議ブリッジ** ] に移動します。</span><span class="sxs-lookup"><span data-stu-id="90835-190">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="90835-191">リストから電話番号を選択し、[ **編集** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="90835-191">Select a phone number from the list and click **Edit**.</span></span>

3. <span data-ttu-id="90835-192">[ **既定の言語** ] と [ **代替言語 (オプション)** ] で必要な言語を選びます。</span><span class="sxs-lookup"><span data-stu-id="90835-192">Choose the languages you want under **Default language** and **Alternate languages (optional)**.</span></span>

4. <span data-ttu-id="90835-193">[ **保存** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="90835-193">Click **Save**.</span></span>


<span data-ttu-id="90835-194">[電話会議の自動案内の言語を設定する](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="90835-194">See [Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span></span>
  
## <a name="see-audio-conferencing-dial-in-numbers"></a><span data-ttu-id="90835-195">電話会議のダイヤルイン番号を確認する</span><span class="sxs-lookup"><span data-stu-id="90835-195">See audio conferencing dial-in numbers</span></span>

<span data-ttu-id="90835-196">![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**</span><span class="sxs-lookup"><span data-stu-id="90835-196">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="90835-197">左側のナビゲーションで、[ **会議** ]  >  [ **会議ブリッジ** ] に移動します。</span><span class="sxs-lookup"><span data-stu-id="90835-197">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="90835-198">リストから電話番号を選択し、[ **編集** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="90835-198">Select a phone number from the list and click **Edit**.</span></span> <span data-ttu-id="90835-199">ここでは、</span><span class="sxs-lookup"><span data-stu-id="90835-199">Here you can:</span></span>
    
   - <span data-ttu-id="90835-200">電話会議に使用する電話番号を表示します。</span><span class="sxs-lookup"><span data-stu-id="90835-200">View the phone numbers that are to be used for Audio Conferencing.</span></span> 
    
   - <span data-ttu-id="90835-201">場所や、電話会議の自動応答で使用する第 1 言語を表示できます。</span><span class="sxs-lookup"><span data-stu-id="90835-201">View the location, and the primary language, that will be used by the Audio Conferencing auto attendant.</span></span>

  
<span data-ttu-id="90835-202">「[電話会議の電話番号のリストを表示する](see-a-list-of-audio-conferencing-numbers-in-teams.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="90835-202">See [See a list of Audio Conferencing numbers](see-a-list-of-audio-conferencing-numbers-in-teams.md).</span></span>
  

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="90835-203">Windows PowerShell の詳細情報</span><span class="sxs-lookup"><span data-stu-id="90835-203">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="90835-204">Windows PowerShell では、ユーザーの管理と、許可または許可されていないユーザーの操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="90835-204">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="90835-205">Windows PowerShell を使用すると、複数のタスクがある場合に、1つの管理ポイントを使用して Microsoft 365 または Office 365 を管理し、日常業務を簡素化することができます。</span><span class="sxs-lookup"><span data-stu-id="90835-205">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="90835-206">Windows PowerShell の使用を開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="90835-206">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="90835-207">Microsoft 365 または Office 365 PowerShell を使用する必要がある理由</span><span class="sxs-lookup"><span data-stu-id="90835-207">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="90835-208">Windows PowerShell を使用して Microsoft 365 または Office 365 を管理するのに最適な方法</span><span class="sxs-lookup"><span data-stu-id="90835-208">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="90835-209">Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="90835-209">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
    
## <a name="related-topics"></a><span data-ttu-id="90835-210">関連トピック</span><span class="sxs-lookup"><span data-stu-id="90835-210">Related topics</span></span>

[<span data-ttu-id="90835-211">ユーザーの電話会議の設定を管理する</span><span class="sxs-lookup"><span data-stu-id="90835-211">Manage the Audio Conferencing settings for a user</span></span>](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)


