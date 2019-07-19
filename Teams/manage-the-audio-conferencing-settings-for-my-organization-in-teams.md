---
title: Microsoft Teams で組織の電話会議の設定を管理する
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
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'ダイヤルイン電話会議ライセンスと会議 ID をユーザーおよびその他の多くのダイヤルイン電話会議の設定に割り当てるための Microsoft Teams での手順を確認します。 '
ms.openlocfilehash: d5b3b616d8e3a42f5084d8de424c3fd557271b1d
ms.sourcegitcommit: 4c041e8a7c39bd6517605ed7fc9aab18cf466596
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/18/2019
ms.locfileid: "35793197"
---
# <a name="manage-the-audio-conferencing-settings-for-your-organization-in-microsoft-teams"></a><span data-ttu-id="9e320-103">Microsoft Teams で組織の電話会議の設定を管理する</span><span class="sxs-lookup"><span data-stu-id="9e320-103">Manage the Audio Conferencing settings for your organization in Microsoft Teams</span></span>

<span data-ttu-id="9e320-104">1 つの場所で Microsoft Teams のすべての電話会議設定を確認することが、より簡単になります。</span><span class="sxs-lookup"><span data-stu-id="9e320-104">It might be easier for you to see all of the audio conferencing settings for Microsoft Teams in one place.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="assign-an-audio-conferencing-license"></a><span data-ttu-id="9e320-105">電話会議のライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="9e320-105">Assign an Audio Conferencing license</span></span>

> [!NOTE]
> <span data-ttu-id="9e320-106">Teams を使用してライセンスを割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="9e320-106">You can't assign licenses using Teams.</span></span> <span data-ttu-id="9e320-107">Microsoft 365 管理センターを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e320-107">You must use the Microsoft 365 admin center.</span></span> <span data-ttu-id="9e320-108">[Skype for Business と Microsoft Teams のライセンスを割り当てる](assign-teams-licenses.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e320-108">See [Assign Skype for Business and Microsoft Teams licenses](assign-teams-licenses.md).</span></span> 
  
 <span data-ttu-id="9e320-109">**ユーザーにライセンスを割り当てる**</span><span class="sxs-lookup"><span data-stu-id="9e320-109">**To assign a license for a user**</span></span>
  
1. <span data-ttu-id="9e320-110">職場または学校のアカウントを使用して、Microsoft 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="9e320-110">Sign in to Microsoft 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="9e320-111">**Microsoft 365 管理センター**の左のナビゲーションで、[**ユーザー** > の**アクティブな**ユーザー] に移動し、利用可能なユーザーのリストからユーザー (複数可) を選びます。</span><span class="sxs-lookup"><span data-stu-id="9e320-111">In the left navigation of the **Microsoft 365 admin center**, go to **Users** > **Active users**, and then select the user or users from the list of available users.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9e320-112">操作手順と PowerShell のサンプル スクリプトについては、「**Skype for Business と Microsoft Teams のライセンスを割り当てる**」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9e320-112">If you are assigning licenses to up to 20 users at the same time, you can use the **Select a view** drop-down then choose one of the options or create your own view.</span></span> <span data-ttu-id="9e320-113">次に [**編集**]、[**次へ**] を 2 回クリックしてからライセンスを選択し、[**送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9e320-113">Then click **Edit**, **Next** twice then select the license and click **Submit**.</span></span>  
  
3. <span data-ttu-id="9e320-114">操作ウィンドウの [**製品ライセンス**] で [ **編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9e320-114">In the Action pane under **Product licenses**, click **Edit**.</span></span> 
    
4. <span data-ttu-id="9e320-p103">[**製品ライセンス**] ページで、[**電話会議**] を有効にし、[**保存**] をクリックします。ライセンスの詳細については、「[Microsoft Teams アドオン ライセンス](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e320-p103">On the **Product Licenses** page, turn on **Audio Conferencing** and then click **Save**. For more on licensing, see [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
    
> [!NOTE]
> <span data-ttu-id="9e320-117">ライセンスを割り当てた後は、リストの最初の電話会議プロバイダーとして Microsoft が表示されない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9e320-117">After you assign the license, Microsoft might not appear initially in the list as an audio conferencing provider.</span></span> <span data-ttu-id="9e320-118">この問題が発生した場合は、管理センターからログアウトするか、CTRL キーを押しながら F5 キーを押してブラウザーウィンドウを更新してください。</span><span class="sxs-lookup"><span data-stu-id="9e320-118">If this happens, either log out of the admin center or press CTRL+F5 to refresh the browser window.</span></span> 
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a><span data-ttu-id="9e320-119">電話会議ユーザーに送信されたメールを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="9e320-119">Enable or disable emails sent to audio conferencing users</span></span>

<span data-ttu-id="9e320-120">![Microsoft teams](media/teams-logo-30x30.png) **管理センターを使用し**た microsoft teams ロゴを示すアイコン</span><span class="sxs-lookup"><span data-stu-id="9e320-120">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="9e320-121">左側のナビゲーションで、[**会議**]  >  [**会議ブリッジ**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="9e320-121">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="9e320-122">[**会議ブリッジ**] ページの最上部で、[**ブリッジの設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9e320-122">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="9e320-123">[**ブリッジの設定**] ペインで、[**ダイヤルイン設定が変わると、ユーザーに自動的に電子メールが送信されます**] を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="9e320-123">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="9e320-124">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9e320-124">Click **Save**.</span></span>

    
<span data-ttu-id="9e320-125">**Windows PowerShell を使用する**</span><span class="sxs-lookup"><span data-stu-id="9e320-125">**Using Windows PowerShell**</span></span>
  
<span data-ttu-id="9e320-126">詳細については、[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9e320-126">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="reset-the-meeting-conference-id"></a><span data-ttu-id="9e320-127">会議通話 ID をリセットする</span><span class="sxs-lookup"><span data-stu-id="9e320-127">Reset the meeting conference ID</span></span>

<span data-ttu-id="9e320-128">![](media/teams-logo-30x30.png) **Microsoft teams 管理センターを使用し**た Teams のロゴを示すアイコン</span><span class="sxs-lookup"><span data-stu-id="9e320-128">![An icon showing the Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="9e320-129">左側のナビゲーションで、[**ユーザー**] をクリックしてから、空いているユーザーのリストからユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="9e320-129">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="9e320-130">[**電話会議**] で [**会議通話 ID のリセット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9e320-130">Under **Audio Conferencing**, click **Reset conference ID**.</span></span>  

3. <span data-ttu-id="9e320-131">[**会議通話 ID のリセット**] ウィンドウで、[**リセット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9e320-131">In the **Reset conference ID?** window, click **Reset**.</span></span> <span data-ttu-id="9e320-132">ユーザーに電子メールを送信することが有効になっている場合、会議通話 ID は自動的に作成され、新しい会議通話 ID が記載された電子メールがユーザーに送信されます。</span><span class="sxs-lookup"><span data-stu-id="9e320-132">A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled.</span></span> <span data-ttu-id="9e320-133">これは既定では有効になっています。</span><span class="sxs-lookup"><span data-stu-id="9e320-133">It's enabled by default.</span></span>

<span data-ttu-id="9e320-134">「[ユーザーの会議通話 ID をリセットする](reset-a-conference-id-for-a-user-in-teams.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e320-134">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user-in-teams.md).</span></span>
  
## <a name="reset-a-conference-organizers-pin"></a><span data-ttu-id="9e320-135">会議通話の開催者の PIN をリセットする</span><span class="sxs-lookup"><span data-stu-id="9e320-135">Reset a conference organizer's PIN</span></span>

<span data-ttu-id="9e320-136">ユーザーがスケジュール設定した各会議には、一意の会議通話 ID が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="9e320-136">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="9e320-137">会議通話 ID は自動的に作成されユーザーに割り当てられますが、ユーザーは使わないため特定の番号に設定しようと考える場合や、ユーザーが会議通話 ID を覚えられない、または紛失してしまう場合があります。</span><span class="sxs-lookup"><span data-stu-id="9e320-137">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or your users can't remember or have lost their conference ID.</span></span> 

<span data-ttu-id="9e320-138">![Microsoft teams](media/teams-logo-30x30.png) **管理センターを使用し**た microsoft teams ロゴを示すアイコン</span><span class="sxs-lookup"><span data-stu-id="9e320-138">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="9e320-139">左側のナビゲーションで、[**ユーザー**] をクリックしてから、空いているユーザーのリストからユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="9e320-139">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="9e320-140">[**電話会議**] で、[**PIN のリセット**] をクリックしてから [**リセット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9e320-140">Under **Audio Conferencing**, click **Reset PIN**, and then click **Reset**.</span></span> 
  
<span data-ttu-id="9e320-p107">ユーザーは、電話会議の PIN が有効になっているか、PIN が再設定されている場合、自分の PIN を使ってメールを受け取れます。しかし、自動で送信するメールが無効になっている場合、 PIN リセットのメールは送信されませんので、手動でユーザーに前述の PIN を送信する必要があります。 PIN が再設定されるとその PIN は一度だけ表示されます。再設定された直後に表示された後、その PIN はユーザーのプロパティ上に表示されることはなく、その代わりに \*\*\*\*\* と表示されます。</span><span class="sxs-lookup"><span data-stu-id="9e320-p107">Users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset. But if you have disabled automatically sending emails, a PIN reset email won't be sent and you will have to manually send the PIN to the user. The PIN will only be shown once after it has been reset. After it's displayed just after being reset, the PIN won't be shown anymore on the user properties; instead, \*\*\*\*\* will be shown.</span></span> 
  
<span data-ttu-id="9e320-145">「[電話会議の PIN をリセットする](reset-the-audio-conferencing-pin-in-teams.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e320-145">See [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin-in-teams.md).</span></span>
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="9e320-146">電話会議の情報が記載された電子メールをユーザーに送信する</span><span class="sxs-lookup"><span data-stu-id="9e320-146">Send an email with Audio Conferencing information to a user</span></span>

<span data-ttu-id="9e320-147">![Microsoft teams](media/teams-logo-30x30.png) **管理センターを使用し**た microsoft teams ロゴを示すアイコン</span><span class="sxs-lookup"><span data-stu-id="9e320-147">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="9e320-148">左側のナビゲーションで、[**ユーザー**] をクリックしてから、空いているユーザーのリストからユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="9e320-148">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="9e320-149">[**電話会議**] の下で、[**電話会議情報をメールで送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9e320-149">Under **Audio Conferencing**, click **Send conference info in email**.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="9e320-150">この操作を行っても、電話会議の PIN はユーザーに送信されません。</span><span class="sxs-lookup"><span data-stu-id="9e320-150">When you do this, the audio conferencing PIN isn't sent to the user.</span></span> 

<span data-ttu-id="9e320-151">「[電話会議の情報が記載された電子メールをユーザーに送信する](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e320-151">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).</span></span>
  
## <a name="set-the-phone-numbers-included-on-invites"></a><span data-ttu-id="9e320-152">招待状に含まれている電話番号を設定する</span><span class="sxs-lookup"><span data-stu-id="9e320-152">Set the phone numbers included on invites</span></span>

<span data-ttu-id="9e320-153">![Microsoft teams](media/teams-logo-30x30.png) **管理センターを使用し**た microsoft teams ロゴを示すアイコン</span><span class="sxs-lookup"><span data-stu-id="9e320-153">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="9e320-154">左側のナビゲーションで、[**ユーザー**] をクリックしてから、空いているユーザーのリストからユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="9e320-154">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="9e320-155">[**電話会議**] の横の [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9e320-155">Next to **Audio Conferencing**, click **Edit**.</span></span>
 
3. <span data-ttu-id="9e320-156">[**電話会議**] ウィンドウで、[**有料電話番号**] と、可能な場合は [**フリーダイヤル番号**] を設定できます。</span><span class="sxs-lookup"><span data-stu-id="9e320-156">In the **Audio Conferencing** pane, you can set the **Toll number** and, if allowed, the **Toll-free number**.</span></span>

4. <span data-ttu-id="9e320-157">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9e320-157">Click **Save**.</span></span>
    
<span data-ttu-id="9e320-158">「[招待状に含まれている電話番号を設定する](set-the-phone-numbers-included-on-invites-in-teams.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e320-158">See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites-in-teams.md).</span></span>
  
  
## <a name="choose-audio-conferencing-bridge-settings"></a><span data-ttu-id="9e320-159">電話会議ブリッジの設定を選択する</span><span class="sxs-lookup"><span data-stu-id="9e320-159">Choose audio conferencing bridge settings</span></span>

<span data-ttu-id="9e320-160">**発信者が会議に参加するときの会議エクスペリエンスを設定する**</span><span class="sxs-lookup"><span data-stu-id="9e320-160">**Set the meeting experience when callers join a meeting**</span></span>

<span data-ttu-id="9e320-161">![Microsoft teams](media/teams-logo-30x30.png) **管理センターを使用し**た microsoft teams ロゴを示すアイコン</span><span class="sxs-lookup"><span data-stu-id="9e320-161">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="9e320-162">左側のナビゲーションで、[**会議**]  >  [**会議ブリッジ**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="9e320-162">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="9e320-163">[**会議ブリッジ**] ページの最上部で、[**ブリッジの設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9e320-163">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="9e320-164">[**ブリッジの設定**] ウィンドウで、[**会議の開始と終了の通知**] を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="9e320-164">In the **Bridge settings** pane, enable or disable **Meeting entry and exit notifications**.</span></span>

    <span data-ttu-id="9e320-165">これは既定では有効になっています。</span><span class="sxs-lookup"><span data-stu-id="9e320-165">This is enabled by default.</span></span> <span data-ttu-id="9e320-166">このオプションを無効にすると、既定ですでに会議に参加済みのユーザーは、誰かが入ってきたり退出したりしたときに通知を受け取りません。</span><span class="sxs-lookup"><span data-stu-id="9e320-166">If you disable this option, users who have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span></span>

4. <span data-ttu-id="9e320-167">[**開始/終了のお知らせの種類**] で、[**トーン**] または [**名前または電話番号**] のどちらかを選びます。</span><span class="sxs-lookup"><span data-stu-id="9e320-167">Under **Entry/exit announcement type**, choose either **Tones** or **Names or phone numbers**.</span></span> 

    <span data-ttu-id="9e320-168">[**名前または電話番号**] を選ぶと、[**発信者に会議に参加する前に自分の名前を記録するように要求する**] を有効または無効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="9e320-168">If you choose **Names or phone numbers**, you can also choose to enable or disable **Ask callers to record their name before joining the meeting**.</span></span> 

5. <span data-ttu-id="9e320-169">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9e320-169">Click **Save**.</span></span>

    
<span data-ttu-id="9e320-170">[電話会議ブリッジの設定を変更する](change-the-settings-for-an-audio-conferencing-bridge.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e320-170">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>
  
 <span data-ttu-id="9e320-171">**会議の PIN の長さを設定する**</span><span class="sxs-lookup"><span data-stu-id="9e320-171">**Set the PIN length for meetings**</span></span>

1. <span data-ttu-id="9e320-172">左側のナビゲーションで、[**会議**]  >  [**会議ブリッジ**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="9e320-172">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="9e320-173">[**会議ブリッジ**] ページの最上部で、[**ブリッジの設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9e320-173">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="9e320-174">[**ブリッジの設定**] ウィンドウで、[**PIN の長さ**] リストに PIN の桁数を入力し、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9e320-174">In the **Bridge settings** pane, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>

    <span data-ttu-id="9e320-p109">PIN は 4 桁から 12 桁の間の値にする必要があります。既定値は 5 桁です。</span><span class="sxs-lookup"><span data-stu-id="9e320-p109">The PIN must be between 4 and 12 digits. The default is 5.</span></span>

    
<span data-ttu-id="9e320-177">職場または学校のアカウントを使用して、Office 365 にサインインします。[](change-the-settings-for-an-audio-conferencing-bridge.md)</span><span class="sxs-lookup"><span data-stu-id="9e320-177">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>
  
 <span data-ttu-id="9e320-178">**電話会議 ユーザーに送信されているメールを有効または無効にする**</span><span class="sxs-lookup"><span data-stu-id="9e320-178">**Enable or disable email from being sent to audio users**</span></span>

1. <span data-ttu-id="9e320-179">左側のナビゲーションで、[**会議**]  >  [**会議ブリッジ**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="9e320-179">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="9e320-180">[**会議ブリッジ**] ページの最上部で、[**ブリッジの設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9e320-180">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="9e320-181">[**ブリッジの設定**] ペインで、[**電話会議設定を変更した場合ユーザーに自動的に電子メールを送信する**] を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="9e320-181">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their audio conferencing settings change**.</span></span>

4. <span data-ttu-id="9e320-182">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9e320-182">Click **Save**.</span></span> 
 
    <span data-ttu-id="9e320-183">電話会議設定をメールでユーザーに送ることもできます。その場合は、ユーザーの電話会議プロパティに移動して、[**電話会議情報を電子メールで送信する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9e320-183">You can also send email to the user with the audio conferencing settings, by going to the user's audio conferencing properties and clicking **Send conference info in email**.</span></span>
    
    <span data-ttu-id="9e320-184">この操作を行うと、会議 ID と電話会議の番号のみが含まれるメールが送信されますが、そのメールに PIN は含まれません。</span><span class="sxs-lookup"><span data-stu-id="9e320-184">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span></span>

<span data-ttu-id="9e320-185">「[電話会議の情報が記載された電子メールをユーザーに送信する](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e320-185">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).</span></span>
    
## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a><span data-ttu-id="9e320-186">電話会議ブリッジの第 1 (既定) 言語と第 2 (代替) 言語を表示、設定する</span><span class="sxs-lookup"><span data-stu-id="9e320-186">See and set the primary (default) and secondary (alternate) languages on an audio conferencing bridge</span></span>

<span data-ttu-id="9e320-187">![Microsoft teams](media/teams-logo-30x30.png) **管理センターを使用し**た microsoft teams ロゴを示すアイコン</span><span class="sxs-lookup"><span data-stu-id="9e320-187">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="9e320-188">左側のナビゲーションで、[**会議**]  >  [**会議ブリッジ**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="9e320-188">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="9e320-189">リストから電話番号を選択し、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9e320-189">Select a phone number from the list and click **Edit**.</span></span>

3. <span data-ttu-id="9e320-190">[**既定の言語**] と [**代替言語 (オプション)**] で必要な言語を選びます。</span><span class="sxs-lookup"><span data-stu-id="9e320-190">Choose the languages you want under **Default language** and **Alternate languages (optional)**.</span></span>

4. <span data-ttu-id="9e320-191">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9e320-191">Click **Save**.</span></span>


<span data-ttu-id="9e320-192">[電話会議の自動案内の言語を設定する](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e320-192">See [Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span></span>
  
## <a name="see-audio-conferencing-dial-in-numbers"></a><span data-ttu-id="9e320-193">電話会議のダイヤルイン番号を確認する</span><span class="sxs-lookup"><span data-stu-id="9e320-193">See audio conferencing dial-in numbers</span></span>

<span data-ttu-id="9e320-194">![Microsoft teams](media/teams-logo-30x30.png) **管理センターを使用し**た microsoft teams ロゴを示すアイコン</span><span class="sxs-lookup"><span data-stu-id="9e320-194">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="9e320-195">左側のナビゲーションで、[**会議**]  >  [**会議ブリッジ**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="9e320-195">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="9e320-196">リストから電話番号を選択し、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9e320-196">Select a phone number from the list and click **Edit**.</span></span> <span data-ttu-id="9e320-197">ここでは、</span><span class="sxs-lookup"><span data-stu-id="9e320-197">Here you can:</span></span>
    
   - <span data-ttu-id="9e320-198">電話会議で使うために Office 365 によって設定された電話番号を表示する。</span><span class="sxs-lookup"><span data-stu-id="9e320-198">View the phone numbers that are set by Office 365 to be used for Audio Conferencing.</span></span> 
    
   - <span data-ttu-id="9e320-199">場所や、電話会議の自動応答で使用する第 1 言語を表示できます。</span><span class="sxs-lookup"><span data-stu-id="9e320-199">View the location, and the primary language, that will be used by the Audio Conferencing auto attendant.</span></span>

  
<span data-ttu-id="9e320-200">「[電話会議の電話番号のリストを表示する](see-a-list-of-audio-conferencing-numbers-in-teams.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e320-200">See [See a list of Audio Conferencing numbers](see-a-list-of-audio-conferencing-numbers-in-teams.md).</span></span>
  

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="9e320-201">Windows PowerShell の詳細情報</span><span class="sxs-lookup"><span data-stu-id="9e320-201">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="9e320-p111">Windows PowerShell で行うのは、ユーザーを管理し、ユーザーに何を許可して何を禁止するかを管理することです。Windows PowerShell を利用すると、Office 365 の管理を 1 か所で行うことができるので、複数のタスクを担当する管理者の日常業務を単純化できます。Windows PowerShell の使用を開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e320-p111">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="9e320-205">Office 365 PowerShell を使用する必要がある理由</span><span class="sxs-lookup"><span data-stu-id="9e320-205">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="9e320-206">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="9e320-206">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="9e320-207">Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9e320-207">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
    
## <a name="related-topics"></a><span data-ttu-id="9e320-208">関連トピック</span><span class="sxs-lookup"><span data-stu-id="9e320-208">Related topics</span></span>

[<span data-ttu-id="9e320-209">ユーザーの電話会議の設定を管理する</span><span class="sxs-lookup"><span data-stu-id="9e320-209">Manage the Audio Conferencing settings for a user</span></span>](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)


