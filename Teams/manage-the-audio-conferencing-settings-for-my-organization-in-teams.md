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
ms.openlocfilehash: 96a8995b995340642c6b58be9d5062eacd3cd29c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101093"
---
# <a name="manage-the-audio-conferencing-settings-for-your-organization-in-microsoft-teams"></a><span data-ttu-id="80c52-103">Microsoft Teams で組織の電話会議の設定を管理する</span><span class="sxs-lookup"><span data-stu-id="80c52-103">Manage the Audio Conferencing settings for your organization in Microsoft Teams</span></span>

<span data-ttu-id="80c52-104">1 つの場所で Microsoft Teams のすべての電話会議設定を確認することが、より簡単になります。</span><span class="sxs-lookup"><span data-stu-id="80c52-104">It might be easier for you to see all of the audio conferencing settings for Microsoft Teams in one place.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="assign-an-audio-conferencing-license"></a><span data-ttu-id="80c52-105">電話会議のライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="80c52-105">Assign an Audio Conferencing license</span></span>

> [!NOTE]
> <span data-ttu-id="80c52-106">Teams を使用してライセンスを割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="80c52-106">You can't assign licenses using Teams.</span></span> <span data-ttu-id="80c52-107">Microsoft 365 管理センターを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="80c52-107">You must use the Microsoft 365 admin center.</span></span> <span data-ttu-id="80c52-108">「Microsoft [Teams アドオン ライセンスを割り当てる」を参照してください](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="80c52-108">See [Assign Microsoft Teams add-on licenses](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span> 
  
 <span data-ttu-id="80c52-109">**ユーザーにライセンスを割り当てる**</span><span class="sxs-lookup"><span data-stu-id="80c52-109">**To assign a license for a user**</span></span>
  
1. <span data-ttu-id="80c52-110">職場または学校のアカウントを使用して、Microsoft 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="80c52-110">Sign in to Microsoft 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="80c52-111">**Microsoft 365** 管理センターの左側のナビゲーションで、[アクティブなユーザー] に移動し、使用可能なユーザーの一覧からユーザーを  >  選択します。</span><span class="sxs-lookup"><span data-stu-id="80c52-111">In the left navigation of the **Microsoft 365 admin center**, go to **Users** > **Active users**, and then select the user or users from the list of available users.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="80c52-112">操作手順と PowerShell のサンプル スクリプトについては、「**Skype for Business と Microsoft Teams のライセンスを割り当てる**」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="80c52-112">If you are assigning licenses to up to 20 users at the same time, you can use the **Select a view** drop-down then choose one of the options or create your own view.</span></span> <span data-ttu-id="80c52-113">次に [**編集**]、[**次へ**] を 2 回クリックしてからライセンスを選択し、[**送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="80c52-113">Then click **Edit**, **Next** twice then select the license and click **Submit**.</span></span>  
  
3. <span data-ttu-id="80c52-114">操作ウィンドウの [**製品ライセンス**] で [ **編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="80c52-114">In the Action pane under **Product licenses**, click **Edit**.</span></span> 
    
4. <span data-ttu-id="80c52-p103">[**製品ライセンス**] ページで、[**電話会議**] を有効にし、[**保存**] をクリックします。ライセンスの詳細については、「[Microsoft Teams アドオン ライセンス](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="80c52-p103">On the **Product Licenses** page, turn on **Audio Conferencing** and then click **Save**. For more on licensing, see [Microsoft Teams add-on licensing](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="80c52-117">ライセンスを割り当てると、Microsoft が電話会議プロバイダーとして最初にリストに表示されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="80c52-117">After you assign the license, Microsoft might not appear initially in the list as an audio conferencing provider.</span></span> <span data-ttu-id="80c52-118">この場合は、管理センターからログアウトするか、Ctrl キーを押しながら F5 キーを押してブラウザー ウィンドウを更新します。</span><span class="sxs-lookup"><span data-stu-id="80c52-118">If this happens, either log out of the admin center or press CTRL+F5 to refresh the browser window.</span></span> 
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a><span data-ttu-id="80c52-119">電話会議ユーザーに送信されたメールを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="80c52-119">Enable or disable emails sent to audio conferencing users</span></span>

<span data-ttu-id="80c52-120">![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**</span><span class="sxs-lookup"><span data-stu-id="80c52-120">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="80c52-121">左側のナビゲーションで、[**会議**]  >  [**会議ブリッジ**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="80c52-121">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="80c52-122">[**会議ブリッジ**] ページの最上部で、[**ブリッジの設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="80c52-122">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="80c52-123">[**ブリッジの設定**] ペインで、[**ダイヤルイン設定が変わると、ユーザーに自動的に電子メールが送信されます**] を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="80c52-123">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="80c52-124">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="80c52-124">Click **Save**.</span></span>

    
<span data-ttu-id="80c52-125">**Windows PowerShell を使用する**</span><span class="sxs-lookup"><span data-stu-id="80c52-125">**Using Windows PowerShell**</span></span>
  
<span data-ttu-id="80c52-126">詳細については、[Microsoft Teams PowerShell のリファレンス](/powershell/module/teams/?view=teams-ps)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="80c52-126">See the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="reset-the-meeting-conference-id"></a><span data-ttu-id="80c52-127">会議通話 ID をリセットする</span><span class="sxs-lookup"><span data-stu-id="80c52-127">Reset the meeting conference ID</span></span>

<span data-ttu-id="80c52-128">![Microsoft Teams 管理センターを使用する ](media/teams-logo-30x30.png) **Teams ロゴを示すアイコン**</span><span class="sxs-lookup"><span data-stu-id="80c52-128">![An icon showing the Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="80c52-129">左側のナビゲーションで、[**ユーザー**] をクリックしてから、空いているユーザーのリストからユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="80c52-129">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="80c52-130">[**電話会議**] で [**会議通話 ID のリセット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="80c52-130">Under **Audio Conferencing**, click **Reset conference ID**.</span></span>  

3. <span data-ttu-id="80c52-131">[**会議通話 ID のリセット**] ウィンドウで、[**リセット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="80c52-131">In the **Reset conference ID?** window, click **Reset**.</span></span> <span data-ttu-id="80c52-132">ユーザーに電子メールを送信することが有効になっている場合、会議通話 ID は自動的に作成され、新しい会議通話 ID が記載された電子メールがユーザーに送信されます。</span><span class="sxs-lookup"><span data-stu-id="80c52-132">A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled.</span></span> <span data-ttu-id="80c52-133">これは既定では有効になっています。</span><span class="sxs-lookup"><span data-stu-id="80c52-133">It's enabled by default.</span></span>

<span data-ttu-id="80c52-134">「[ユーザーの会議通話 ID をリセットする](reset-a-conference-id-for-a-user-in-teams.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="80c52-134">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user-in-teams.md).</span></span>
  
## <a name="reset-a-conference-organizers-pin"></a><span data-ttu-id="80c52-135">会議通話の開催者の PIN をリセットする</span><span class="sxs-lookup"><span data-stu-id="80c52-135">Reset a conference organizer's PIN</span></span>

<span data-ttu-id="80c52-136">ユーザーがスケジュール設定した各会議には、一意の会議通話 ID が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="80c52-136">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="80c52-137">会議通話 ID は自動的に作成されユーザーに割り当てられますが、ユーザーは使わないため特定の番号に設定しようと考える場合や、ユーザーが会議通話 ID を覚えられない、または紛失してしまう場合があります。</span><span class="sxs-lookup"><span data-stu-id="80c52-137">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or your users can't remember or have lost their conference ID.</span></span> 

<span data-ttu-id="80c52-138">![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**</span><span class="sxs-lookup"><span data-stu-id="80c52-138">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="80c52-139">左側のナビゲーションで、[**ユーザー**] をクリックしてから、空いているユーザーのリストからユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="80c52-139">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="80c52-140">[**電話会議**] で、[**PIN のリセット**] をクリックしてから [**リセット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="80c52-140">Under **Audio Conferencing**, click **Reset PIN**, and then click **Reset**.</span></span> 
  
<span data-ttu-id="80c52-p107">ユーザーは、電話会議の PIN が有効になっているか、PIN が再設定されている場合、自分の PIN を使ってメールを受け取れます。しかし、自動で送信するメールが無効になっている場合、 PIN リセットのメールは送信されませんので、手動でユーザーに前述の PIN を送信する必要があります。 PIN が再設定されるとその PIN は一度だけ表示されます。再設定された直後に表示された後、その PIN はユーザーのプロパティ上に表示されることはなく、その代わりに \*\*\*\*\* と表示されます。</span><span class="sxs-lookup"><span data-stu-id="80c52-p107">Users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset. But if you have disabled automatically sending emails, a PIN reset email won't be sent and you will have to manually send the PIN to the user. The PIN will only be shown once after it has been reset. After it's displayed just after being reset, the PIN won't be shown anymore on the user properties; instead, \*\*\*\*\* will be shown.</span></span> 
  
<span data-ttu-id="80c52-145">「[電話会議の PIN をリセットする](reset-the-audio-conferencing-pin-in-teams.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="80c52-145">See [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin-in-teams.md).</span></span>
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="80c52-146">電話会議の情報が記載された電子メールをユーザーに送信する</span><span class="sxs-lookup"><span data-stu-id="80c52-146">Send an email with Audio Conferencing information to a user</span></span>

<span data-ttu-id="80c52-147">![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**</span><span class="sxs-lookup"><span data-stu-id="80c52-147">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="80c52-148">左側のナビゲーションで、[**ユーザー**] をクリックしてから、空いているユーザーのリストからユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="80c52-148">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="80c52-149">[**電話会議**] の下で、[**電話会議情報をメールで送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="80c52-149">Under **Audio Conferencing**, click **Send conference info in email**.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="80c52-150">この操作を行っても、電話会議の PIN はユーザーに送信されません。</span><span class="sxs-lookup"><span data-stu-id="80c52-150">When you do this, the audio conferencing PIN isn't sent to the user.</span></span> 

<span data-ttu-id="80c52-151">「[電話会議の情報が記載された電子メールをユーザーに送信する](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="80c52-151">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).</span></span>
  
## <a name="set-the-phone-numbers-included-on-invites"></a><span data-ttu-id="80c52-152">招待状に含まれている電話番号を設定する</span><span class="sxs-lookup"><span data-stu-id="80c52-152">Set the phone numbers included on invites</span></span>

<span data-ttu-id="80c52-153">![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**</span><span class="sxs-lookup"><span data-stu-id="80c52-153">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="80c52-154">左側のナビゲーションで、[**ユーザー**] をクリックしてから、空いているユーザーのリストからユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="80c52-154">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="80c52-155">[**電話会議**] の横の [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="80c52-155">Next to **Audio Conferencing**, click **Edit**.</span></span>
 
3. <span data-ttu-id="80c52-156">[**電話会議**] ウィンドウで、[**有料電話番号**] と、可能な場合は [**フリーダイヤル番号**] を設定できます。</span><span class="sxs-lookup"><span data-stu-id="80c52-156">In the **Audio Conferencing** pane, you can set the **Toll number** and, if allowed, the **Toll-free number**.</span></span>

4. <span data-ttu-id="80c52-157">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="80c52-157">Click **Save**.</span></span>
    
<span data-ttu-id="80c52-158">「[招待状に含まれている電話番号を設定する](set-the-phone-numbers-included-on-invites-in-teams.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="80c52-158">See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites-in-teams.md).</span></span>
  
  
## <a name="choose-audio-conferencing-bridge-settings"></a><span data-ttu-id="80c52-159">電話会議ブリッジの設定を選択する</span><span class="sxs-lookup"><span data-stu-id="80c52-159">Choose audio conferencing bridge settings</span></span>

<span data-ttu-id="80c52-160">**発信者が会議に参加するときの会議エクスペリエンスを設定する**</span><span class="sxs-lookup"><span data-stu-id="80c52-160">**Set the meeting experience when callers join a meeting**</span></span>

<span data-ttu-id="80c52-161">![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**</span><span class="sxs-lookup"><span data-stu-id="80c52-161">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="80c52-162">左側のナビゲーションで、[**会議**]  >  [**会議ブリッジ**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="80c52-162">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="80c52-163">[**会議ブリッジ**] ページの最上部で、[**ブリッジの設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="80c52-163">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="80c52-164">[**ブリッジの設定**] ウィンドウで、[**会議の開始と終了の通知**] を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="80c52-164">In the **Bridge settings** pane, enable or disable **Meeting entry and exit notifications**.</span></span>

    <span data-ttu-id="80c52-165">これは既定では有効になっています。</span><span class="sxs-lookup"><span data-stu-id="80c52-165">This is enabled by default.</span></span> <span data-ttu-id="80c52-166">このオプションを無効にすると、既定ですでに会議に参加済みのユーザーは、誰かが入ってきたり退出したりしたときに通知を受け取りません。</span><span class="sxs-lookup"><span data-stu-id="80c52-166">If you disable this option, users who have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span></span>

4. <span data-ttu-id="80c52-167">[**開始/終了のお知らせの種類**] で、[**トーン**] または [**名前または電話番号**] のどちらかを選びます。</span><span class="sxs-lookup"><span data-stu-id="80c52-167">Under **Entry/exit announcement type**, choose either **Tones** or **Names or phone numbers**.</span></span> 

    <span data-ttu-id="80c52-168">[**名前または電話番号**] を選ぶと、[**発信者に会議に参加する前に自分の名前を記録するように要求する**] を有効または無効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="80c52-168">If you choose **Names or phone numbers**, you can also choose to enable or disable **Ask callers to record their name before joining the meeting**.</span></span> 
    > [!NOTE]
    > <span data-ttu-id="80c52-169">既定では、外部参加者はダイヤルイン参加者の電話番号を表示されません。</span><span class="sxs-lookup"><span data-stu-id="80c52-169">By default, external participants can't see the phone numbers of dialed-in participants.</span></span> <span data-ttu-id="80c52-170">これらの電話番号のプライバシーを維持したい場合は、**開始/終了のお知らせの種類** の **トーン** を選びます (これにより、数字が Teams によって読み上げられません)。</span><span class="sxs-lookup"><span data-stu-id="80c52-170">If you want to maintain the privacy of these phone numbers, select **Tones** for **Entry/exit announcement type** (this prevents the numbers from being read out by Teams).</span></span>


5. <span data-ttu-id="80c52-171">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="80c52-171">Click **Save**.</span></span>

    
<span data-ttu-id="80c52-172">[電話会議ブリッジの設定を変更する](change-the-settings-for-an-audio-conferencing-bridge.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="80c52-172">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>
  
 <span data-ttu-id="80c52-173">**会議の PIN の長さを設定する**</span><span class="sxs-lookup"><span data-stu-id="80c52-173">**Set the PIN length for meetings**</span></span>

1. <span data-ttu-id="80c52-174">左側のナビゲーションで、[**会議**]  >  [**会議ブリッジ**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="80c52-174">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="80c52-175">[**会議ブリッジ**] ページの最上部で、[**ブリッジの設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="80c52-175">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="80c52-176">[**ブリッジの設定**] ウィンドウで、[**PIN の長さ**] リストに PIN の桁数を入力し、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="80c52-176">In the **Bridge settings** pane, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>

    <span data-ttu-id="80c52-p110">PIN は 4 桁から 12 桁の間の値にする必要があります。既定値は 5 桁です。</span><span class="sxs-lookup"><span data-stu-id="80c52-p110">The PIN must be between 4 and 12 digits. The default is 5.</span></span>

    
<span data-ttu-id="80c52-179">職場または学校のアカウントを使用して、Office 365 にサインインします。[](change-the-settings-for-an-audio-conferencing-bridge.md)</span><span class="sxs-lookup"><span data-stu-id="80c52-179">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>
  
 <span data-ttu-id="80c52-180">**電話会議 ユーザーに送信されているメールを有効または無効にする**</span><span class="sxs-lookup"><span data-stu-id="80c52-180">**Enable or disable email from being sent to audio users**</span></span>

1. <span data-ttu-id="80c52-181">左側のナビゲーションで、[**会議**]  >  [**会議ブリッジ**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="80c52-181">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="80c52-182">[**会議ブリッジ**] ページの最上部で、[**ブリッジの設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="80c52-182">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="80c52-183">[**ブリッジの設定**] ペインで、[**電話会議設定を変更した場合ユーザーに自動的に電子メールを送信する**] を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="80c52-183">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their audio conferencing settings change**.</span></span>

4. <span data-ttu-id="80c52-184">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="80c52-184">Click **Save**.</span></span> 
 
    <span data-ttu-id="80c52-185">電話会議設定をメールでユーザーに送ることもできます。その場合は、ユーザーの電話会議プロパティに移動して、[**電話会議情報を電子メールで送信する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="80c52-185">You can also send email to the user with the audio conferencing settings, by going to the user's audio conferencing properties and clicking **Send conference info in email**.</span></span>
    
    <span data-ttu-id="80c52-186">この操作を行うと、会議 ID と電話会議の番号のみが含まれるメールが送信されますが、そのメールに PIN は含まれません。</span><span class="sxs-lookup"><span data-stu-id="80c52-186">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span></span>

<span data-ttu-id="80c52-187">「[電話会議の情報が記載された電子メールをユーザーに送信する](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="80c52-187">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).</span></span>
    
## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a><span data-ttu-id="80c52-188">電話会議ブリッジの第 1 (既定) 言語と第 2 (代替) 言語を表示、設定する</span><span class="sxs-lookup"><span data-stu-id="80c52-188">See and set the primary (default) and secondary (alternate) languages on an audio conferencing bridge</span></span>

<span data-ttu-id="80c52-189">![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**</span><span class="sxs-lookup"><span data-stu-id="80c52-189">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="80c52-190">左側のナビゲーションで、[**会議**]  >  [**会議ブリッジ**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="80c52-190">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="80c52-191">リストから電話番号を選択し、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="80c52-191">Select a phone number from the list and click **Edit**.</span></span>

3. <span data-ttu-id="80c52-192">[**既定の言語**] と [**代替言語 (オプション)**] で必要な言語を選びます。</span><span class="sxs-lookup"><span data-stu-id="80c52-192">Choose the languages you want under **Default language** and **Alternate languages (optional)**.</span></span>

4. <span data-ttu-id="80c52-193">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="80c52-193">Click **Save**.</span></span>


<span data-ttu-id="80c52-194">[電話会議の自動案内の言語を設定する](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="80c52-194">See [Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span></span>
  
## <a name="see-audio-conferencing-dial-in-numbers"></a><span data-ttu-id="80c52-195">電話会議のダイヤルイン番号を確認する</span><span class="sxs-lookup"><span data-stu-id="80c52-195">See audio conferencing dial-in numbers</span></span>

<span data-ttu-id="80c52-196">![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**</span><span class="sxs-lookup"><span data-stu-id="80c52-196">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="80c52-197">左側のナビゲーションで、[**会議**]  >  [**会議ブリッジ**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="80c52-197">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="80c52-198">リストから電話番号を選択し、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="80c52-198">Select a phone number from the list and click **Edit**.</span></span> <span data-ttu-id="80c52-199">ここでは、</span><span class="sxs-lookup"><span data-stu-id="80c52-199">Here you can:</span></span>
    
   - <span data-ttu-id="80c52-200">電話会議に使用する電話番号を表示します。</span><span class="sxs-lookup"><span data-stu-id="80c52-200">View the phone numbers that are to be used for Audio Conferencing.</span></span> 
    
   - <span data-ttu-id="80c52-201">場所や、電話会議の自動応答で使用する第 1 言語を表示できます。</span><span class="sxs-lookup"><span data-stu-id="80c52-201">View the location, and the primary language, that will be used by the Audio Conferencing auto attendant.</span></span>

  
<span data-ttu-id="80c52-202">「[電話会議の電話番号のリストを表示する](see-a-list-of-audio-conferencing-numbers-in-teams.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="80c52-202">See [See a list of Audio Conferencing numbers](see-a-list-of-audio-conferencing-numbers-in-teams.md).</span></span>
  

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="80c52-203">Windows PowerShell の詳細情報</span><span class="sxs-lookup"><span data-stu-id="80c52-203">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="80c52-204">Windows PowerShellは、ユーザーの管理と、ユーザーに許可する操作と許可しない操作の管理に使います。</span><span class="sxs-lookup"><span data-stu-id="80c52-204">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="80c52-205">Windows PowerShell を使用すると、単一の管理ポイントを使用して Microsoft 365 または Office 365 を管理し、複数のタスクを実行する必要があるときに日常業務を簡略化できます。</span><span class="sxs-lookup"><span data-stu-id="80c52-205">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="80c52-206">Windows PowerShell の使用を開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="80c52-206">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="80c52-207">Microsoft 365 または Office 365 PowerShell を使用する必要がある理由</span><span class="sxs-lookup"><span data-stu-id="80c52-207">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="80c52-208">[Microsoft 365 または Office 365 を他のユーザーとWindows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="80c52-208">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
<span data-ttu-id="80c52-209">Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](/powershell/module/teams/?view=teams-ps)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="80c52-209">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
    
## <a name="related-topics"></a><span data-ttu-id="80c52-210">関連トピック</span><span class="sxs-lookup"><span data-stu-id="80c52-210">Related topics</span></span>

[<span data-ttu-id="80c52-211">ユーザーの電話会議の設定を管理する</span><span class="sxs-lookup"><span data-stu-id="80c52-211">Manage the Audio Conferencing settings for a user</span></span>](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)