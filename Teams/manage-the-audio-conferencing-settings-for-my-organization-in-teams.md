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
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'ダイヤルイン電話会議ライセンスと会議 ID をユーザーおよびその他の多くのダイヤルイン電話会議の設定に割り当てるための Microsoft Teams での手順を確認します。 '
ms.openlocfilehash: 201da13370852b6506fe7aa32f695d973bcc637a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32202766"
---
# <a name="manage-the-audio-conferencing-settings-for-your-organization-in-microsoft-teams"></a><span data-ttu-id="4bade-103">Microsoft Teams で組織の電話会議の設定を管理する</span><span class="sxs-lookup"><span data-stu-id="4bade-103">Manage the Audio Conferencing settings for your organization in Microsoft Teams</span></span>

<span data-ttu-id="4bade-104">1 つの場所で Microsoft Teams のすべての電話会議設定を確認することが、より簡単になります。</span><span class="sxs-lookup"><span data-stu-id="4bade-104">It might be easier for you to see all of the audio conferencing settings for Microsoft Teams in one place.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="assign-an-audio-conferencing-license"></a><span data-ttu-id="4bade-105">電話会議のライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="4bade-105">Assign an Audio Conferencing license</span></span>

> [!NOTE]
> <span data-ttu-id="4bade-106">Teams を使用してライセンスを割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="4bade-106">You can't assign licenses using Teams.</span></span> <span data-ttu-id="4bade-107">Office 365 管理センターを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4bade-107">You must use the Office 365 admin center.</span></span> <span data-ttu-id="4bade-108">[Skype for Business と Microsoft Teams のライセンスを割り当てる](assign-teams-licenses.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4bade-108">See [Assign Skype for Business and Microsoft Teams licenses](assign-teams-licenses.md).</span></span> 
  
 <span data-ttu-id="4bade-109">**ユーザーにライセンスを割り当てる**</span><span class="sxs-lookup"><span data-stu-id="4bade-109">**To assign a license for a user**</span></span>
  
1. <span data-ttu-id="4bade-110">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="4bade-110">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="4bade-111">次に [ **編集**]、[ **次へ**] を 2 回クリックし、ライセンスを選択して、[  > ] をクリックします。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="4bade-111">In the left navigation of the **Office 365 admin center**, go to **Users** > **Active users**, and then select the user or users from the list of available users.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4bade-112">操作手順と PowerShell のサンプル スクリプトについては、「**Skype for Business と Microsoft Teams のライセンスを割り当てる**」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4bade-112">If you are assigning licenses to up to 20 users at the same time, you can use the **Select a view** drop-down then choose one of the options or create your own view.</span></span> <span data-ttu-id="4bade-113">次に [**編集**]、[**次へ**] を 2 回クリックしてからライセンスを選択し、[**送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4bade-113">Then click **Edit**, **Next** twice then select the license and click **Submit**.</span></span>  
  
3. <span data-ttu-id="4bade-114">操作ウィンドウの [**製品ライセンス**] で [ **編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4bade-114">In the Action pane under **Product licenses**, click **Edit**.</span></span> 
    
4. <span data-ttu-id="4bade-p103">[**製品ライセンス**] ページで、[**電話会議**] を有効にし、[**保存**] をクリックします。ライセンスの詳細については、「[Microsoft Teams アドオン ライセンス](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4bade-p103">On the **Product Licenses** page, turn on **Audio Conferencing** and then click **Save**. For more on licensing, see [Skype for Business and Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
    
> [!NOTE]
> <span data-ttu-id="4bade-p104">ライセンスを割り当てた後に、Microsoft では、電話会議プロバイダーとしてリストに最初に表示されない場合があります。この状況が生じた場合は、Office 365 管理センターからログアウトするか、CTRL+F5 を同時に押すかして、ブラウザー ウィンドウを更新します。</span><span class="sxs-lookup"><span data-stu-id="4bade-p104">After you assign the license, Microsoft might not appear initially in the list as an audio conferencing provider. If this happens, either log out of the Office 365 admin center or press CTRL+F5 to refresh the browser window.</span></span> 
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a><span data-ttu-id="4bade-119">電話会議ユーザーに送信されたメールを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="4bade-119">Enable or disable emails sent to audio conferencing users</span></span>

<span data-ttu-id="4bade-120">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Microsoft Teams 管理センターの使用**</span><span class="sxs-lookup"><span data-stu-id="4bade-120">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="4bade-121">左側のナビゲーションで、[**会議**]  >  [**会議ブリッジ**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="4bade-121">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="4bade-122">[**会議ブリッジ**] ページの最上部で、[**ブリッジの設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4bade-122">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="4bade-123">[**ブリッジの設定**] ペインで、[**ダイヤルイン設定が変わると、ユーザーに自動的に電子メールが送信されます**] を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="4bade-123">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="4bade-124">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4bade-124">Click **Save**.</span></span>

    
<span data-ttu-id="4bade-125">**Windows PowerShell を使用する**</span><span class="sxs-lookup"><span data-stu-id="4bade-125">**Using Windows PowerShell**</span></span>
  
<span data-ttu-id="4bade-126">詳細については、[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4bade-126">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="reset-the-meeting-conference-id"></a><span data-ttu-id="4bade-127">会議通話 ID をリセットする</span><span class="sxs-lookup"><span data-stu-id="4bade-127">Reset the meeting conference ID</span></span>

<span data-ttu-id="4bade-128">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Microsoft Teams 管理センターの使用**</span><span class="sxs-lookup"><span data-stu-id="4bade-128">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="4bade-129">左側のナビゲーションで、[**ユーザー**] をクリックしてから、空いているユーザーのリストからユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="4bade-129">In the left navigation of the **Office 365 admin center, go to UsersActive users**, and then select the user or users from the list of available users.</span></span>

2. <span data-ttu-id="4bade-130">[**電話会議**] で [**会議通話 ID のリセット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4bade-130">Under **Audio Conferencing**, click **Reset conference ID**.</span></span>  

3. <span data-ttu-id="4bade-131">[**会議通話 ID のリセット**] ウィンドウで、[**リセット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4bade-131">In the **Reset conference ID?** window, click **Reset**.</span></span> <span data-ttu-id="4bade-132">ユーザーに電子メールを送信することが有効になっている場合、会議通話 ID は自動的に作成され、新しい会議通話 ID が記載された電子メールがユーザーに送信されます。</span><span class="sxs-lookup"><span data-stu-id="4bade-132">In the Reset conference ID? window, click Yes. A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled. It's enabled by default.</span></span> <span data-ttu-id="4bade-133">これは既定では有効になっています。</span><span class="sxs-lookup"><span data-stu-id="4bade-133">It's enabled by default.</span></span>

<span data-ttu-id="4bade-134">「[ユーザーの会議通話 ID をリセットする](reset-a-conference-id-for-a-user-in-teams.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4bade-134">[Reset a conference ID for a user](reset-a-conference-id-for-a-user-in-teams.md)</span></span>
  
## <a name="reset-a-conference-organizers-pin"></a><span data-ttu-id="4bade-135">会議通話の開催者の PIN をリセットする</span><span class="sxs-lookup"><span data-stu-id="4bade-135">Reset a conference organizer's PIN</span></span>

<span data-ttu-id="4bade-136">ユーザーがスケジュール設定した各会議には、一意の会議通話 ID が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="4bade-136">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="4bade-137">会議通話 ID は自動的に作成されユーザーに割り当てられますが、ユーザーは使わないため特定の番号に設定しようと考える場合や、ユーザーが会議通話 ID を覚えられない、または紛失してしまう場合があります。</span><span class="sxs-lookup"><span data-stu-id="4bade-137">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or your users can't remember or have lost their conference ID.</span></span> 

<span data-ttu-id="4bade-138">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Microsoft Teams 管理センターの使用**</span><span class="sxs-lookup"><span data-stu-id="4bade-138">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="4bade-139">左側のナビゲーションで、[**ユーザー**] をクリックしてから、空いているユーザーのリストからユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="4bade-139">In the left navigation of the **Office 365 admin center, go to UsersActive users**, and then select the user or users from the list of available users.</span></span>

2. <span data-ttu-id="4bade-140">[**電話会議**] で、[**PIN のリセット**] をクリックしてから [**リセット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4bade-140">Under **Audio Conferencing**, click **Reset PIN**, and then click **Reset**.</span></span> 
  
<span data-ttu-id="4bade-p107">ユーザーは、電話会議の PIN が有効になっているか、PIN が再設定されている場合、自分の PIN を使ってメールを受け取れます。しかし、自動で送信するメールが無効になっている場合、 PIN リセットのメールは送信されませんので、手動でユーザーに前述の PIN を送信する必要があります。 PIN が再設定されるとその PIN は一度だけ表示されます。再設定された直後に表示された後、その PIN はユーザーのプロパティ上に表示されることはなく、その代わりに \*\*\*\*\* と表示されます。</span><span class="sxs-lookup"><span data-stu-id="4bade-p107">Users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset. But if you have disabled automatically sending emails, a PIN reset email won't be sent and you will have to manually send the PIN to the user. The PIN will only be shown once after it has been reset. After it's displayed just after being reset, the PIN won't be shown anymore on the user properties; instead, \*\*\*\*\* will be shown.</span></span> 
  
<span data-ttu-id="4bade-145">「[電話会議の PIN をリセットする](reset-the-audio-conferencing-pin-in-teams.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4bade-145">[Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin-in-teams.md)</span></span>
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="4bade-146">電話会議の情報が記載された電子メールをユーザーに送信する</span><span class="sxs-lookup"><span data-stu-id="4bade-146">Send an email to a user with their Audio Conferencing information</span></span>

<span data-ttu-id="4bade-147">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Microsoft Teams 管理センターの使用**</span><span class="sxs-lookup"><span data-stu-id="4bade-147">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="4bade-148">左側のナビゲーションで、[**ユーザー**] をクリックしてから、空いているユーザーのリストからユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="4bade-148">In the left navigation of the **Office 365 admin center, go to UsersActive users**, and then select the user or users from the list of available users.</span></span>

2. <span data-ttu-id="4bade-149">[**電話会議**] の下で、[**電話会議情報をメールで送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4bade-149">Under **Audio Conferencing**, click **Send conference info in email**.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="4bade-150">この操作を行っても、電話会議の PIN はユーザーに送信されません。</span><span class="sxs-lookup"><span data-stu-id="4bade-150">When you do this, the audio conferencing PIN isn't sent to the user.</span></span> 

<span data-ttu-id="4bade-151">「[電話会議の情報が記載された電子メールをユーザーに送信する](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4bade-151">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).</span></span>
  
## <a name="set-the-phone-numbers-included-on-invites"></a><span data-ttu-id="4bade-152">招待状に含まれている電話番号を設定する</span><span class="sxs-lookup"><span data-stu-id="4bade-152">Set the phone numbers included on invites</span></span>

<span data-ttu-id="4bade-153">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Microsoft Teams 管理センターの使用**</span><span class="sxs-lookup"><span data-stu-id="4bade-153">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="4bade-154">左側のナビゲーションで、[**ユーザー**] をクリックしてから、空いているユーザーのリストからユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="4bade-154">In the left navigation of the **Office 365 admin center, go to UsersActive users**, and then select the user or users from the list of available users.</span></span>

2. <span data-ttu-id="4bade-155">[**電話会議**] の横の [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4bade-155">Next to **Audio Conferencing**, click **Edit**.</span></span>
 
3. <span data-ttu-id="4bade-156">[**電話会議**] ウィンドウで、[**有料電話番号**] と、可能な場合は [**フリーダイヤル番号**] を設定できます。</span><span class="sxs-lookup"><span data-stu-id="4bade-156">In the Action pane, you can set the Toll number and, if allowed, the Toll-free number.</span></span>

4. <span data-ttu-id="4bade-157">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4bade-157">Click **Save**.</span></span>
    
<span data-ttu-id="4bade-158">「[招待状に含まれている電話番号を設定する](set-the-phone-numbers-included-on-invites-in-teams.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4bade-158">[Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites-in-teams.md)</span></span>
  
  
## <a name="choose-audio-conferencing-bridge-settings"></a><span data-ttu-id="4bade-159">電話会議ブリッジの設定を選択する</span><span class="sxs-lookup"><span data-stu-id="4bade-159">Choose audio conferencing bridge settings</span></span>

<span data-ttu-id="4bade-160">**発信者が会議に参加するときの会議エクスペリエンスを設定する**</span><span class="sxs-lookup"><span data-stu-id="4bade-160">**Set the meeting experience when callers join a meeting**</span></span>

<span data-ttu-id="4bade-161">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Microsoft Teams 管理センターの使用**</span><span class="sxs-lookup"><span data-stu-id="4bade-161">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="4bade-162">左側のナビゲーションで、[**会議**]  >  [**会議ブリッジ**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="4bade-162">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="4bade-163">[**会議ブリッジ**] ページの最上部で、[**ブリッジの設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4bade-163">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span> 

3. <span data-ttu-id="4bade-164">[**ブリッジの設定**] ウィンドウで、[**会議の開始と終了の通知**] を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="4bade-164">In the **Bridge settings** pane, enable or disable **Meeting entry and exit notifications**.</span></span>

    <span data-ttu-id="4bade-165">これは既定では有効になっています。</span><span class="sxs-lookup"><span data-stu-id="4bade-165">CDR is enabled by default.</span></span> <span data-ttu-id="4bade-166">このオプションを無効にすると、既定ですでに会議に参加済みのユーザーは、誰かが入ってきたり退出したりしたときに通知を受け取りません。</span><span class="sxs-lookup"><span data-stu-id="4bade-166">If you clear it, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>

4. <span data-ttu-id="4bade-167">[**開始/終了のお知らせの種類**] で、[**トーン**] または [**名前または電話番号**] のどちらかを選びます。</span><span class="sxs-lookup"><span data-stu-id="4bade-167">Under **Entry/exit announcement type**, choose either **Tones** or **Names or phone numbers**.</span></span> 

    <span data-ttu-id="4bade-168">[**名前または電話番号**] を選ぶと、[**発信者に会議に参加する前に自分の名前を記録するように要求する**] を有効または無効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="4bade-168">If you chose **Names or phone numbers**, enable or disable **Ask callers to record their name before joining the meeting**.</span></span> 

5. <span data-ttu-id="4bade-169">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4bade-169">Click **Save**.</span></span>

    
<span data-ttu-id="4bade-170">[電話会議ブリッジの設定を変更する](change-the-settings-for-an-audio-conferencing-bridge.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4bade-170">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>
  
 <span data-ttu-id="4bade-171">**会議の PIN の長さを設定する**</span><span class="sxs-lookup"><span data-stu-id="4bade-171">**Set the PIN length for meetings**</span></span>

1. <span data-ttu-id="4bade-172">左側のナビゲーションで、[**会議**]  >  [**会議ブリッジ**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="4bade-172">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="4bade-173">[**会議ブリッジ**] ページの最上部で、[**ブリッジの設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4bade-173">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span> 

3. <span data-ttu-id="4bade-174">[**ブリッジの設定**] ウィンドウで、[**PIN の長さ**] リストに PIN の桁数を入力し、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4bade-174">Under **Security**, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>

    <span data-ttu-id="4bade-p109">PIN は 4 桁から 12 桁の間の値にする必要があります。既定値は 5 桁です。</span><span class="sxs-lookup"><span data-stu-id="4bade-p109">The PIN must be between 4 and 12 digits. The default is 5.</span></span>

    
<span data-ttu-id="4bade-177">職場または学校のアカウントを使用して、Office 365 にサインインします。[](change-the-settings-for-an-audio-conferencing-bridge.md)</span><span class="sxs-lookup"><span data-stu-id="4bade-177">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>
  
 <span data-ttu-id="4bade-178">**電話会議 ユーザーに送信されているメールを有効または無効にする**</span><span class="sxs-lookup"><span data-stu-id="4bade-178">**Enable or disable email from being sent to audio users**</span></span>

1. <span data-ttu-id="4bade-179">左側のナビゲーションで、[**会議**]  >  [**会議ブリッジ**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="4bade-179">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="4bade-180">[**会議ブリッジ**] ページの最上部で、[**ブリッジの設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4bade-180">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span> 

3. <span data-ttu-id="4bade-181">[**ブリッジの設定**] ペインで、[**電話会議設定を変更した場合ユーザーに自動的に電子メールを送信する**] を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="4bade-181">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their audio conferencing settings change**.</span></span>

4. <span data-ttu-id="4bade-182">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4bade-182">Click **Save**.</span></span> 
 
    <span data-ttu-id="4bade-183">電話会議設定をメールでユーザーに送ることもできます。その場合は、ユーザーの電話会議プロパティに移動して、[**電話会議情報を電子メールで送信する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4bade-183">You can also send email to the user with the audio conferencing settings, by going to the user's audio conferencing properties and clicking **Send conference info via email**.</span></span>
    
    <span data-ttu-id="4bade-184">この操作を行うと、会議 ID と電話会議の番号のみが含まれるメールが送信されますが、そのメールに PIN は含まれません。</span><span class="sxs-lookup"><span data-stu-id="4bade-184">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span></span>

<span data-ttu-id="4bade-185">「[電話会議の情報が記載された電子メールをユーザーに送信する](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4bade-185">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).</span></span>
    
## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a><span data-ttu-id="4bade-186">電話会議ブリッジの第 1 (既定) 言語と第 2 (代替) 言語を表示、設定する</span><span class="sxs-lookup"><span data-stu-id="4bade-186">See and set the primary (default) and secondary (alternate) languages on an audio conferencing bridge</span></span>

<span data-ttu-id="4bade-187">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Microsoft Teams 管理センターの使用**</span><span class="sxs-lookup"><span data-stu-id="4bade-187">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="4bade-188">左側のナビゲーションで、[**会議**]  >  [**会議ブリッジ**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="4bade-188">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="4bade-189">リストから電話番号を選択し、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4bade-189">Select a number from the list of phone numbers and click **Assign**.</span></span>

3. <span data-ttu-id="4bade-190">[**既定の言語**] と [**代替言語 (オプション)**] で必要な言語を選びます。</span><span class="sxs-lookup"><span data-stu-id="4bade-190">Choose the languages you want under **Default language** and **Alternate languages (optional)**.</span></span>

4. <span data-ttu-id="4bade-191">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4bade-191">Click **Save**.</span></span>


<span data-ttu-id="4bade-192">[電話会議の自動案内の言語を設定する](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4bade-192">See [Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span></span>
  
## <a name="see-audio-conferencing-dial-in-numbers"></a><span data-ttu-id="4bade-193">電話会議のダイヤルイン番号を確認する</span><span class="sxs-lookup"><span data-stu-id="4bade-193">See audio conferencing dial-in numbers</span></span>

<span data-ttu-id="4bade-194">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Microsoft Teams 管理センターの使用**</span><span class="sxs-lookup"><span data-stu-id="4bade-194">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="4bade-195">左側のナビゲーションで、[**会議**]  >  [**会議ブリッジ**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="4bade-195">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="4bade-196">リストから電話番号を選択し、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4bade-196">Select a number from the list of phone numbers and click **Assign**.</span></span> <span data-ttu-id="4bade-197">ここでは、</span><span class="sxs-lookup"><span data-stu-id="4bade-197">Here you can:</span></span>
    
   - <span data-ttu-id="4bade-198">電話会議で使うために Office 365 によって設定された電話番号を表示する。</span><span class="sxs-lookup"><span data-stu-id="4bade-198">View the phone numbers that are set by Office 365 to be used for Audio Conferencing.</span></span> 
    
   - <span data-ttu-id="4bade-199">場所や、電話会議の自動応答で使用する第 1 言語を表示できます。</span><span class="sxs-lookup"><span data-stu-id="4bade-199">View the location, and the primary and secondary languages, that will be used by the Audio Conferencing auto attendant.</span></span>

  
<span data-ttu-id="4bade-200">「[電話会議の電話番号のリストを表示する](see-a-list-of-audio-conferencing-numbers-in-teams.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4bade-200">See [See a list of Audio Conferencing numbers](see-a-list-of-audio-conferencing-numbers-in-teams.md).</span></span>
  

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="4bade-201">Windows PowerShell の詳細情報</span><span class="sxs-lookup"><span data-stu-id="4bade-201">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="4bade-p111">Windows PowerShell で行うのは、ユーザーを管理し、ユーザーに何を許可して何を禁止するかを管理することです。Windows PowerShell を利用すると、Office 365 の管理を 1 か所で行うことができるので、複数のタスクを担当する管理者の日常業務を単純化できます。Windows PowerShell の使用を開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4bade-p111">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="4bade-205">Office 365 PowerShell を使用する必要がある理由</span><span class="sxs-lookup"><span data-stu-id="4bade-205">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="4bade-206">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="4bade-206">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="4bade-207">Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4bade-207">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
    
## <a name="related-topics"></a><span data-ttu-id="4bade-208">関連トピック</span><span class="sxs-lookup"><span data-stu-id="4bade-208">Related topics</span></span>

[<span data-ttu-id="4bade-209">ユーザーの電話会議の設定を管理する</span><span class="sxs-lookup"><span data-stu-id="4bade-209">Manage the Audio Conferencing settings for a user</span></span>](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)


