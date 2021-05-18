---
title: Skype for Business Online で組織の電話会議の設定を管理する
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: bc9bd328-c5b2-44e5-af15-e02bf00e1c81
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: '「Skype for Businessオンラインの手順」を参照して、ダイヤルイン会議ライセンスと会議 ID をユーザーに割り当て、その他の多くのダイヤルイン会議設定を割り当てる必要があります。 '
ms.openlocfilehash: 3a0f6d37612c345c8561fbd2a64b4c90fdb27957
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237249"
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization-in-skype-for-business-online"></a><span data-ttu-id="9706d-103">Skype for Business Online で組織の電話会議の設定を管理する</span><span class="sxs-lookup"><span data-stu-id="9706d-103">Manage the Audio Conferencing settings for my organization in Skype for Business Online</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!NOTE]
> <span data-ttu-id="9706d-104">Teams でこれらの設定を管理する場合は、[Microsoft Teams で組織の電話会議の設定を管理する](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-my-organization-in-teams) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9706d-104">If you want to manage these settings in Teams, see [Manage the Audio Conferencing settings for my organization in Microsoft Teams](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-my-organization-in-teams).</span></span>

<span data-ttu-id="9706d-105">すべての電話会議の設定を 1 か所でSkype for Business表示する方が簡単な場合があります。</span><span class="sxs-lookup"><span data-stu-id="9706d-105">It might be easier for you to see all of the audio conferencing settings for Skype for Business in one place.</span></span>


## <a name="assign-an-audio-conferencing-license"></a><span data-ttu-id="9706d-106">電話会議のライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="9706d-106">Assign an Audio Conferencing license</span></span>

> [!NOTE]
> <span data-ttu-id="9706d-107">To assign a license for a user</span><span class="sxs-lookup"><span data-stu-id="9706d-107">You can't assign licenses using the **Skype for Business admin center**.</span></span> <span data-ttu-id="9706d-108">管理センターで Microsoft 365する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9706d-108">You must use the Microsoft 365 admin center.</span></span> <span data-ttu-id="9706d-109">「ライセンスを[割りSkype for Businessする」を参照してください](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="9706d-109">See [Assign Skype for Business licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>

 <span data-ttu-id="9706d-110">**ユーザーにライセンスを割り当てる**</span><span class="sxs-lookup"><span data-stu-id="9706d-110">**To assign a license for a user**</span></span>

1. <span data-ttu-id="9706d-111">仕事用または学校用のアカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="9706d-111">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="9706d-112">管理センターの左側のナビゲーションで、[ユーザーのアクティブなユーザー] に移動し、使用可能なユーザーの一覧からユーザー  >  またはユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="9706d-112">In the left navigation of the admin center, go to **Users** > **Active users**, and then select the user or users from the list of available users.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9706d-113">操作手順と PowerShell のサンプル スクリプトについては、「**Skype for Business と Microsoft Teams のライセンスを割り当てる**」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9706d-113">If you are assigning licenses to up to 20 users at the same time, you can use the **Select a view** drop-down then choose one of the options or create your own view.</span></span> <span data-ttu-id="9706d-114">操作ウィンドウの [ **製品ライセンス**] で [ **編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9706d-114">Then click **Edit**, **Next** twice then select the license and click **Submit**.</span></span> <span data-ttu-id="9706d-115">PowerShell で複数のユーザーにライセンスを割り当Windowsできます。</span><span class="sxs-lookup"><span data-stu-id="9706d-115">You can also assign licenses to multiple users by using Windows Powershell.</span></span> <span data-ttu-id="9706d-116">PowerShell スクリプトの手順とサンプルについては、ライセンスの割り当て[に関するSkype for Business参照してください](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="9706d-116">For instructions and sample PowerShell scripts, see [Assign Skype for Business licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>

3. <span data-ttu-id="9706d-117">[操作] ウィンドウの [**製品ライセンス**] で [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9706d-117">In the Action pane under **Product licenses**, click **Edit**.</span></span>

4. <span data-ttu-id="9706d-118">[製品ライセンス **] ページで** 、[電話会議] **をオンにし** 、[保存] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="9706d-118">On the **Product Licenses** page, turn on **Audio Conferencing** and then click **Save**.</span></span> <span data-ttu-id="9706d-119">ライセンスの詳細については[、「Skype for Business」を参照してください](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="9706d-119">For more on licensing, see [Skype for Business add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>

> [!NOTE]
> <span data-ttu-id="9706d-120">ライセンスを割り当てると、最初に Microsoft が電話会議プロバイダーとしてリストに表示されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="9706d-120">After you assign the license, Microsoft might not appear initially in the list as an audio conferencing provider.</span></span> <span data-ttu-id="9706d-121">この場合は、管理センターからログアウトするか、Ctrl キーを押しながら F5 キーを押してブラウザー ウィンドウを更新します。</span><span class="sxs-lookup"><span data-stu-id="9706d-121">If this happens, either log out of the admin center or press CTRL+F5 to refresh the browser window.</span></span>

## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a><span data-ttu-id="9706d-122">電話会議ユーザーに送信されたメールを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="9706d-122">Enable or disable emails sent to audio conferencing users</span></span>

<span data-ttu-id="9706d-123">![Skype for Business のロゴを表示したアイコン](../images/sfb-logo-30x30.png) **Skype for Business 管理センターの使用**</span><span class="sxs-lookup"><span data-stu-id="9706d-123">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="9706d-124">仕事用または学校用のアカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="9706d-124">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="9706d-125">管理センターに移動し **> Skype for Business** のナビゲーションで、[電話会議]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="9706d-125">Go to the admin center > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>

3. <span data-ttu-id="9706d-126">電話会議の設定を使用してユーザーにメールを送信することもできます。これには、ユーザーの電話会議プロパティに移動して、[ **電話会議情報をメールで送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9706d-126">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>

4. <span data-ttu-id="9706d-127">ユーザーの電話会議プロパティに移動し、[ **電話会議情報をメールで送信**] をクリックすると、電話会議の設定が含まれるメールをユーザーに送信することもできます。会議 ID と電話会議用の既定の電話番号は会議出席依頼に記載されていますが、PIN は記載されていません。</span><span class="sxs-lookup"><span data-stu-id="9706d-127">Click **Save**.</span></span>

    <span data-ttu-id="9706d-p105">ユーザーの電話会議プロパティに移動し、[ **電話会議情報をメールで送信**] をクリックすると、電話会議の設定が含まれるメールをユーザーに送信することもできます。</span><span class="sxs-lookup"><span data-stu-id="9706d-p105">You can also send emails to the user with the audio conferencing settings by going to the user's audio conferencing properties and clicking **Send conference info via email**. The conference ID and default audio conferencing phone number is included on the meeting invite but not the PIN.</span></span>

    <span data-ttu-id="9706d-130">[電話会議の情報が記載されたメールをユーザーに送信する](send-an-email-to-a-user-with-their-dial-in-information.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9706d-130">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

<span data-ttu-id="9706d-131">**The conference ID and default dial-in conferencing phone number is included on the meeting invite but not the PIN.**</span><span class="sxs-lookup"><span data-stu-id="9706d-131">**Using Windows PowerShell**</span></span>

- <span data-ttu-id="9706d-132">Windows PowerShell を使用する</span><span class="sxs-lookup"><span data-stu-id="9706d-132">You can also use the Windows PowerShell and run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

    <span data-ttu-id="9706d-133">Windows PowerShell を使用して、次を実行することもできます。[](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="9706d-133">You can use the [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) to manage other settings for your organization, including email.</span></span>

## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a><span data-ttu-id="9706d-134">You can also use the Windows PowerShell and run:</span><span class="sxs-lookup"><span data-stu-id="9706d-134">Change the sender's contact information in email messages sent to users</span></span>

<span data-ttu-id="9706d-135">実際のメール アドレスや送信者の連絡先情報の表示名など、ユーザーに自動的に送信されるメールを変更できます。</span><span class="sxs-lookup"><span data-stu-id="9706d-135">You can make changes to the email that is automatically sent to your users, including the actual email address and the display name of the sender's contact information.</span></span> <span data-ttu-id="9706d-136">既定では、メールの送信者は Microsoft 365 または Office 365 ですが、Windows PowerShell コマンドレットと[Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps)コマンドレットを使用して、メール アドレスと表示名を変更できます。</span><span class="sxs-lookup"><span data-stu-id="9706d-136">By default, the sender of the emails is Microsoft 365 or Office 365, but you can change the email address and display name using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="9706d-137">ユーザーにメールを送信するメール アドレスを変更するには、次の条件を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9706d-137">To make changes to the email address that is sending the email to the users, you must:</span></span>

- <span data-ttu-id="9706d-138">Enter the email display name in the  _SendEmailFromDisplayName_ parameter.</span><span class="sxs-lookup"><span data-stu-id="9706d-138">Enter the email address in the _SendEmailFromAddress_ parameter.</span></span>

- <span data-ttu-id="9706d-139">メールの差出人のメール アドレスやメールの表示名など、ユーザーに送信したメールの内容を変更するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9706d-139">Enter the email display name in the  _SendEmailFromDisplayName_ parameter.</span></span>

- <span data-ttu-id="9706d-140">メール アドレス情報を変更したい場合は、カスタムのメール アドレスから送信されるメールが、組織の受信メール ポリシーで許可されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9706d-140">Set the _SendEmailOverride_ parameter to _True_.</span></span>

<span data-ttu-id="9706d-141">If you want to change the email address information, you need to make sure that the inbound email policies of your organization allow emails that come from the custom email address.</span><span class="sxs-lookup"><span data-stu-id="9706d-141">You can make changes to the email sent to users, such as the email address that the email is sent from or the display name for the email by running:</span></span>

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

<span data-ttu-id="9706d-142">「ダイヤルイン会議の設定が変更されたユーザーにメールを自動的に送信する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9706d-142">If you want to change the email address information, you need to make sure that the inbound email policies of your organization allow emails that come from the custom email address.</span></span>

<span data-ttu-id="9706d-143">会議 ID をリセットする[](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="9706d-143">You can use the [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet to manage other settings for your organization, including email.</span></span>

<span data-ttu-id="9706d-144">職場または学校のアカウントを使用して、Office 365 にサインインします。[](emails-sent-to-users-when-their-settings-change.md)</span><span class="sxs-lookup"><span data-stu-id="9706d-144">See [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md).</span></span>

## <a name="reset-the-meeting-conference-id"></a><span data-ttu-id="9706d-145">Sign in to Office 365 with your work or school account.</span><span class="sxs-lookup"><span data-stu-id="9706d-145">Reset the meeting conference ID</span></span>

1. <span data-ttu-id="9706d-146">仕事用または学校用のアカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="9706d-146">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="9706d-147">[管理センター] に移動 **> Skype for Business。**</span><span class="sxs-lookup"><span data-stu-id="9706d-147">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="9706d-148">In the \*\* Reset conference ID?\*\* window, click **Yes**. A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled. It's enabled by default.</span><span class="sxs-lookup"><span data-stu-id="9706d-148">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and in the Action pane under **Conference ID**, click **Reset**.</span></span>

4. <span data-ttu-id="9706d-p107">In the \*\* Reset conference ID?\*\* window, click **Yes**.</span><span class="sxs-lookup"><span data-stu-id="9706d-p107">In the **Reset conference ID?** window, click **Yes**. A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled. It's enabled by default.</span></span>

    > [!IMPORTANT]
    >  <span data-ttu-id="9706d-p108">After a new conference ID is created, the old conference ID can't be used by callers.[](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)[](https://go.microsoft.com/fwlink/?LinkID=626047)[](https://www.microsoft.com/download/details.aspx?id=54079)</span><span class="sxs-lookup"><span data-stu-id="9706d-p108">After a new conference ID is created, the old conference ID can't be used by callers. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. The users can use the Skype for Business Meeting Migration Tool to update their existing meetings. To see how to download, install, and run the Skype for Business Meeting Update Tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](https://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/download/details.aspx?id=54079).</span></span>

<span data-ttu-id="9706d-156">「[ユーザーの会議通話 ID をリセットする](reset-a-conference-id-for-a-user.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9706d-156">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).</span></span>

## <a name="reset-a-conference-organizers-pin"></a><span data-ttu-id="9706d-157">会議通話の開催者の PIN をリセットする</span><span class="sxs-lookup"><span data-stu-id="9706d-157">Reset a conference organizer's PIN</span></span>

<span data-ttu-id="9706d-158">ユーザーがスケジュール設定した各会議には、一意の会議通話 ID が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="9706d-158">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="9706d-159">会議通話 ID は自動的に作成されユーザーに割り当てられますが、ユーザーは使わないため特定の番号に設定しようと考える場合や、ユーザーが会議通話 ID を覚えられない、または紛失してしまう場合があります。</span><span class="sxs-lookup"><span data-stu-id="9706d-159">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="9706d-160">管理者センターと Skype for Businessを使用してWindows PowerShell ID の表示、変更、リセットを行えます。</span><span class="sxs-lookup"><span data-stu-id="9706d-160">You can use the Skype for Business admin center and Windows PowerShell to view, change, and reset their conference ID.</span></span>


1. <span data-ttu-id="9706d-161">仕事用または学校用のアカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="9706d-161">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="9706d-162">管理センターに移動し **> Skype for Business** のナビゲーションで、[電話会議]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="9706d-162">Go to the admin center > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>

3. <span data-ttu-id="9706d-163">管理者は、ユーザーに PIN を手動で送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9706d-163">Click **Users**, and then select the user that you want to reset the PIN for.</span></span>

4. <span data-ttu-id="9706d-164">PIN をリセットした後、PIN が表示されるのは 1 回だけです。</span><span class="sxs-lookup"><span data-stu-id="9706d-164">In the Action pane, under **PIN**, click **Reset**.</span></span>

<span data-ttu-id="9706d-p110">リセットの直後に 1 回表示された後は、ユーザーのプロパティには PIN に代わって "\*\*\*\*\*" が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9706d-p110">Users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset. But if you have disabled automatically sending emails, a PIN reset email won't be sent and you will have to manually send the PIN to the user. The PIN will only be shown once after it has been reset. After it's displayed just after being reset, the PIN won't be shown anymore on the user properties; instead, \*\*\*\*\* will be shown.</span></span>

<span data-ttu-id="9706d-169">「[電話会議の PIN をリセットする](reset-the-audio-conferencing-pin.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9706d-169">See [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin.md).</span></span>

## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="9706d-170">電話会議の情報が記載された電子メールをユーザーに送信する</span><span class="sxs-lookup"><span data-stu-id="9706d-170">Send an email with Audio Conferencing information to a user</span></span>

1. <span data-ttu-id="9706d-171">仕事用または学校用のアカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="9706d-171">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="9706d-172">管理センターに移動し **> Skype for Business** のナビゲーションで、[電話会議]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="9706d-172">Go to the admin center > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>

3. <span data-ttu-id="9706d-173">Go to the Office 365 admin centerSkype for Business and in the left navigation click Dial-in conferencing</span><span class="sxs-lookup"><span data-stu-id="9706d-173">Click **Users**, and then select the user that you want to reset the PIN for.</span></span>

4. <span data-ttu-id="9706d-174">操作ウィンドウで、[ **電話会議情報をメールで送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9706d-174">In the Action pane, click **Send conference info via email**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9706d-175">この操作を行っても、電話会議の PIN はユーザーに送信されません。</span><span class="sxs-lookup"><span data-stu-id="9706d-175">When you do this, the audio conferencing PIN isn't sent to the user.</span></span>

<span data-ttu-id="9706d-176">「[電話会議の情報が記載された電子メールをユーザーに送信する](send-an-email-to-a-user-with-their-dial-in-information.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9706d-176">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>

## <a name="setting-the-phone-numbers-included-on-invites"></a><span data-ttu-id="9706d-177">招待に含まれる電話番号を設定する</span><span class="sxs-lookup"><span data-stu-id="9706d-177">Setting the phone numbers included on invites</span></span>

1. <span data-ttu-id="9706d-178">仕事用または学校用のアカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="9706d-178">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="9706d-179">[管理センター] に移動 **> Skype for Business。**</span><span class="sxs-lookup"><span data-stu-id="9706d-179">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="9706d-180">左側のナビゲーションで、[電話会議ユーザー **] に移動**  >  **します**。</span><span class="sxs-lookup"><span data-stu-id="9706d-180">In the left navigation, go to **Audio conferencing** > **Users**.</span></span> <span data-ttu-id="9706d-181">電話会議で有効にするユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="9706d-181">Select the user that you want to enable for Audio Conferencing.</span></span>

4. <span data-ttu-id="9706d-182">[操作] ウィンドウで、[**有料番号**] を、また許可されている場合は [**無料番号**] も設定することができます。</span><span class="sxs-lookup"><span data-stu-id="9706d-182">In the Action pane, you can set the **Toll number** and, if allowed, the **Toll-free number**.</span></span>

5. <span data-ttu-id="9706d-183">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9706d-183">Click **Save**.</span></span>

<span data-ttu-id="9706d-184">「[招待状に含まれている電話番号を設定する](set-the-phone-numbers-included-on-invites.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9706d-184">See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites.md).</span></span>


## <a name="choosing-audio-conferencing-bridge-settings"></a><span data-ttu-id="9706d-185">電話会議ブリッジの設定の選択</span><span class="sxs-lookup"><span data-stu-id="9706d-185">Choosing audio conferencing bridge settings</span></span>

<span data-ttu-id="9706d-186">**発信者が会議に参加するときの会議エクスペリエンスを設定する**</span><span class="sxs-lookup"><span data-stu-id="9706d-186">**Set the meeting experience when callers join a meeting**</span></span>


1. <span data-ttu-id="9706d-187">仕事用または学校用のアカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="9706d-187">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="9706d-188">[管理センター] に移動 **> Skype for Business。**</span><span class="sxs-lookup"><span data-stu-id="9706d-188">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="9706d-189">Go to the **Office 365 admin center** > .</span><span class="sxs-lookup"><span data-stu-id="9706d-189">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>

4. <span data-ttu-id="9706d-190">In the Skype for Business admin center, in the left navigation go to dial-in conferencingMicrosoft bridge settings.</span><span class="sxs-lookup"><span data-stu-id="9706d-190">Under **Meeting join experience**, select the following actions:</span></span>

   - <span data-ttu-id="9706d-p112">**Enable meeting entry and exit notifications to be turned on** This is selected by default. However if you uncheck it, users that have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span><span class="sxs-lookup"><span data-stu-id="9706d-p112">**Enable meeting entry and exit notifications to be turned on** This is selected by default. If you clear this check box, users who have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span></span>

     <span data-ttu-id="9706d-193">これは、ユーザーが Skype for Business アプリを使用して会議に参加し、ユーザーが会議の [Skype 会議オプション] メニューの[入退出時に発表する] 設定を変更するときに、会議単位で設定できます。</span><span class="sxs-lookup"><span data-stu-id="9706d-193">This can be set on a meeting-by-meeting basis when a user joins a meeting using a Skype for Business app and they modify the **Announce when people enter or leave** setting in the Skype Meeting **Options** menu of the meeting.</span></span>

   - <span data-ttu-id="9706d-p113">「**電話会議ブリッジの設定を変更する**」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9706d-p113">**Ask callers to record their name before joining the meeting** This is selected by default. If you clear this check box, callers won't be asked to record their name before they join a meeting.</span></span>

5. <span data-ttu-id="9706d-196">Sign in to Office 365 with your work or school account.</span><span class="sxs-lookup"><span data-stu-id="9706d-196">After you make your changes, click **Save**.</span></span>
    
<span data-ttu-id="9706d-197">Go to the Office 365 admin centerSkype for Business.[](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge)</span><span class="sxs-lookup"><span data-stu-id="9706d-197">See [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span></span>
  
 <span data-ttu-id="9706d-198">**会議の PIN の長さを設定する**</span><span class="sxs-lookup"><span data-stu-id="9706d-198">**Set the PIN length for meetings**</span></span>

1. <span data-ttu-id="9706d-199">仕事用または学校用のアカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="9706d-199">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="9706d-200">[管理センター] に移動 **> Skype for Business。**</span><span class="sxs-lookup"><span data-stu-id="9706d-200">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="9706d-201">既定値は 5 です。 > </span><span class="sxs-lookup"><span data-stu-id="9706d-201">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>

4. <span data-ttu-id="9706d-202">The PIN can only be from 4 to 12 digits. The default is 5.</span><span class="sxs-lookup"><span data-stu-id="9706d-202">Under **Security**, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>

    <span data-ttu-id="9706d-p114">The PIN can only be from 4 to 12 digits.</span><span class="sxs-lookup"><span data-stu-id="9706d-p114">The PIN must be between 4 and 12 digits. The default is 5.</span></span>
    
<span data-ttu-id="9706d-205">職場または学校のアカウントを使用して、Office 365 にサインインします。[](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge)</span><span class="sxs-lookup"><span data-stu-id="9706d-205">See [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span></span>
  
 <span data-ttu-id="9706d-206">**電話会議 ユーザーに送信されているメールを有効または無効にする**</span><span class="sxs-lookup"><span data-stu-id="9706d-206">**Enable or disable email from being sent to audio users**</span></span>

1. <span data-ttu-id="9706d-207">仕事用または学校用のアカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="9706d-207">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="9706d-208">管理センターに移動し **> Skype for Business** のナビゲーションで、[電話会議]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="9706d-208">Go to the admin center > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>

3. <span data-ttu-id="9706d-209">電話会議の設定を使用してユーザーにメールを送信することもできます。これには、ユーザーの電話会議プロパティに移動して、[ **電話会議情報をメールで送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9706d-209">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>

4. <span data-ttu-id="9706d-210">電話会議の設定を使用してユーザーにメールを送信することもできます。</span><span class="sxs-lookup"><span data-stu-id="9706d-210">Click **Save**.</span></span>

    <span data-ttu-id="9706d-211">これには、ユーザーの電話会議プロパティに移動して、[ **電話会議情報をメールで送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9706d-211">You can also send email to the user with the audio conferencing settings, by going to the user's audio conferencing properties and clicking **Send conference info via email**.</span></span>

    <span data-ttu-id="9706d-212">この操作を行うと、会議 ID と電話会議の番号のみが含まれるメールが送信されますが、そのメールに PIN は含まれません。</span><span class="sxs-lookup"><span data-stu-id="9706d-212">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span></span>

    <span data-ttu-id="9706d-213">「[電話会議の情報が記載された電子メールをユーザーに送信する](send-an-email-to-a-user-with-their-dial-in-information.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9706d-213">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>

## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a><span data-ttu-id="9706d-214">電話会議ブリッジの第 1 (既定) 言語と第 2 (代替) 言語を表示、設定する</span><span class="sxs-lookup"><span data-stu-id="9706d-214">See and set the primary (default) and secondary (alternate) languages on an audio conferencing bridge</span></span>


1. <span data-ttu-id="9706d-215">仕事用または学校用のアカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="9706d-215">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="9706d-216">[管理センター] に移動 **> Skype for Business。**</span><span class="sxs-lookup"><span data-stu-id="9706d-216">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="9706d-217">Go to the **Office 365 admin center\*\*\*\*Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="9706d-217">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and then click **Microsoft bridge**.</span></span>

4. <span data-ttu-id="9706d-218">リストから電話番号を選択し、操作ウィンドウで [ **言語を設定**] をクリックしてから、[ **言語を設定**] ページで [ **第 1 言語**] リストをクリックして、サポートされている言語の完全なリストを表示します。</span><span class="sxs-lookup"><span data-stu-id="9706d-218">Select a phone number from the list, click **Set languages** in the Action pane, and then on the **Set languages** page, click the use the **Primary language** list to view the complete list of supported languages.</span></span>

    <span data-ttu-id="9706d-p115">Microsoft を電話会議プロバイダーとして選ぶときに、サポートされる第 1 言語と第 2 言語を設定することもできます。発信者に対する言語の表示順は、リストで言語を選んだ順序になります。</span><span class="sxs-lookup"><span data-stu-id="9706d-p115">You can also set the primary and secondary languages that are supported when you select Microsoft as the audio conferencing provider. The order that you select in the lists is the same order in which languages will be presented to callers.</span></span>

<span data-ttu-id="9706d-221">You can also set the primary and secondary languages that are supported when you select Microsoft as the dial-in conferencing provider. The order that you select in the drop-downs will be the order of the languages that will be presented to the callers.[](set-auto-attendant-languages-for-audio-conferencing.md)</span><span class="sxs-lookup"><span data-stu-id="9706d-221">See [Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing.md).</span></span>

## <a name="see-audio-conferencing-dial-in-numbers"></a><span data-ttu-id="9706d-222">電話会議のダイヤルイン番号を確認する</span><span class="sxs-lookup"><span data-stu-id="9706d-222">See audio conferencing dial-in numbers</span></span>

1. <span data-ttu-id="9706d-223">仕事用または学校用のアカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="9706d-223">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="9706d-224">[管理センター] に移動 **> Skype for Business。**</span><span class="sxs-lookup"><span data-stu-id="9706d-224">Go to the admin center > **Skype for Business**.</span></span>
 
3. <span data-ttu-id="9706d-p116">職場または学校のアカウントを使用して、Office 365 にサインインします。 > </span><span class="sxs-lookup"><span data-stu-id="9706d-p116">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge**. Here you can:</span></span>

   - <span data-ttu-id="9706d-227">電話会議に使用する電話番号またはMicrosoft 365またはOffice 365電話番号を表示します。</span><span class="sxs-lookup"><span data-stu-id="9706d-227">View the phone numbers that are set by Microsoft 365 or Office 365 to be used for Audio Conferencing.</span></span>

   - <span data-ttu-id="9706d-228">場所を表示したり、電話会議の自動応答で使用する第 1 言語と第 2 言語を表示したりする。</span><span class="sxs-lookup"><span data-stu-id="9706d-228">View the location, and the primary and secondary languages, that will be used by the Audio Conferencing auto attendant.</span></span>

   - <span data-ttu-id="9706d-p117">ユーザーが電話会議で有効になっているときに、ユーザーに渡される既定の電話番号を選択します。ただし、電話会議ブリッジの既定の電話番号が変わっても、既存のユーザーの既定の電話番号は変わりません。</span><span class="sxs-lookup"><span data-stu-id="9706d-p117">Select the default phone number that will be given to users when they are enabled for Audio Conferencing. However, if the default phone number of the audio conferencing bridge changes, the default phone number for existing users won't change.</span></span>

<span data-ttu-id="9706d-231">You can select the dial-in conferencing default phone number that will be given to users when they are enabled for dial-in conferencing. However, if the default phone number of the dial-in conferencing bridge changes, the default phone number for existing users won't change. > </span><span class="sxs-lookup"><span data-stu-id="9706d-231">You can go to **Audio conferencing** > **Users** and select the user's properties to change the default number for a user by choosing a new number from the list of numbers that are available in your organization.</span></span>

<span data-ttu-id="9706d-232">You can select the dial-in conferencing default phone number that will be given to users when they are enabled for dial-in conferencing.[](see-a-list-of-audio-conferencing-numbers.md)</span><span class="sxs-lookup"><span data-stu-id="9706d-232">See [See a list of Audio Conferencing numbers](see-a-list-of-audio-conferencing-numbers.md).</span></span>

## <a name="see-a-list-of-users-that-are-enabled"></a><span data-ttu-id="9706d-233">However, if the default phone number of the dial-in conferencing bridge changes, the default phone number for existing users won't change.</span><span class="sxs-lookup"><span data-stu-id="9706d-233">See a list of users that are enabled</span></span>

1. <span data-ttu-id="9706d-234">仕事用または学校用のアカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="9706d-234">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="9706d-235">[管理センター] に移動 **> Skype for Business。**</span><span class="sxs-lookup"><span data-stu-id="9706d-235">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="9706d-236">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="9706d-236">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**> and then **Users**.</span></span>

<span data-ttu-id="9706d-237">Sign in to Office 365 with your work or school account.[](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md)</span><span class="sxs-lookup"><span data-stu-id="9706d-237">See [See a list of users that are enabled for Audio Conferencing](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).</span></span>

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="9706d-238">Go to the Office 365 admin centerSkype for Business.</span><span class="sxs-lookup"><span data-stu-id="9706d-238">Want to know how to manage with Windows PowerShell?</span></span>

<span data-ttu-id="9706d-p118">In the Skype for Business admin center, in the left navigation go to Dial-in conferencing> and then Dial-in users.</span><span class="sxs-lookup"><span data-stu-id="9706d-p118">There are several settings that you can manage at the organization level using Windows PowerShell. This makes it easy to apply settings to all of your users.</span></span>

<span data-ttu-id="9706d-241">Windows PowerShell を使用して組織レベルで管理できる複数の設定があります。[](/previous-versions//mt228132(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="9706d-241">To get more help on each cmdlet, see [Skype for Business Online cmdlets](/previous-versions//mt228132(v=technet.10)).</span></span>

<span data-ttu-id="9706d-242">このため、簡単にこれらの設定をすべてのユーザーに適用できます。</span><span class="sxs-lookup"><span data-stu-id="9706d-242">Here are the organization-level settings:</span></span>

- <span data-ttu-id="9706d-243">**組織レベルの設定を以下に示します。**</span><span class="sxs-lookup"><span data-stu-id="9706d-243">**Setting entry/exit notifications** The default is _$true_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -EnableEntryExitNotifications $true|$false
  ```

- <span data-ttu-id="9706d-244">**There are several settings that you can manage settings at the organization level using Windows PowerShell. This makes it easy to make these settings and have them apply to all of your users. Here are the organization level settings:**</span><span class="sxs-lookup"><span data-stu-id="9706d-244">**Setting name recording** The default is _$true_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -EnableNameRecording $true|false
  ```

- <span data-ttu-id="9706d-245">**There are several settings that you can manage settings at the organization level using Windows PowerShell.**</span><span class="sxs-lookup"><span data-stu-id="9706d-245">**Setting the PIN length** The default is 5.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -PinLength 7
  ```

- <span data-ttu-id="9706d-246">**This makes it easy to make these settings and have them apply to all of your users.**</span><span class="sxs-lookup"><span data-stu-id="9706d-246">**Setting only dial-in meetings from a phone** The default _$false_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true|$false
  ```

- <span data-ttu-id="9706d-247">**Here are the organization level settings:**</span><span class="sxs-lookup"><span data-stu-id="9706d-247">**Setting whether to send email to users** The default is _$true_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

- <span data-ttu-id="9706d-248">**Windows PowerShell の場合、ユーザーの管理と、ユーザーに許可する操作や許可しない操作の管理に使います。Windows PowerShell により、単一の管理ポイントを使って Office 365 を管理でき、複数の作業を実行する必要があるときに日常業務を合理化できます。Windows PowerShell を使い始めるには、次のトピックを参照してください。**</span><span class="sxs-lookup"><span data-stu-id="9706d-248">**Setting whether to send email from a different account** The default is  _$false_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromOverride $true|$false
  ```

- <span data-ttu-id="9706d-249">**Windows PowerShell の場合、ユーザーの管理と、ユーザーに許可する操作や許可しない操作の管理に使います。**</span><span class="sxs-lookup"><span data-stu-id="9706d-249">**Setting the From address on email that is sent to users** The default is _$null_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromAddress
  ```

- <span data-ttu-id="9706d-250">**Windows PowerShell により、単一の管理ポイントを使って Office 365 を管理でき、複数の作業を実行する必要があるときに日常業務を合理化できます。**</span><span class="sxs-lookup"><span data-stu-id="9706d-250">**Setting the display name for the email that is sent to users** The default is  _$null_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromDisplayName
  ```

  ## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="9706d-251">Windows PowerShell を使い始めるには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9706d-251">Want to know more about Windows PowerShell</span></span>
- <span data-ttu-id="9706d-252">Windows PowerShellは、ユーザーの管理と、ユーザーが許可または許可されていない操作についてすべて行います。</span><span class="sxs-lookup"><span data-stu-id="9706d-252">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="9706d-253">このWindows PowerShell、1 つの管理Microsoft 365またはOffice 365を管理し、複数のタスクを実行する場合に毎日の作業を簡略化できます。</span><span class="sxs-lookup"><span data-stu-id="9706d-253">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="9706d-254">Windows PowerShell の使用を開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9706d-254">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="9706d-255">PowerShell で使用する必要があるMicrosoft 365またはOffice 365理由</span><span class="sxs-lookup"><span data-stu-id="9706d-255">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

  - <span data-ttu-id="9706d-256">[アプリを使用してMicrosoft 365またはOffice 365を管理Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="9706d-256">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>

- <span data-ttu-id="9706d-257">Windows PowerShell、多くのユーザーに対して一度に設定を変更する場合など、管理センターを使用する場合に限り、速度、シンプルさ、生産性に多くの利点があります。</span><span class="sxs-lookup"><span data-stu-id="9706d-257">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="9706d-258">次のトピックで、これらの利点を説明します。</span><span class="sxs-lookup"><span data-stu-id="9706d-258">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="9706d-259">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="9706d-259">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [<span data-ttu-id="9706d-260">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="9706d-260">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [<span data-ttu-id="9706d-261">Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行</span><span class="sxs-lookup"><span data-stu-id="9706d-261">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

    <span data-ttu-id="9706d-p121">Skype for Business Online 用の Windows PowerShell モジュールがあれば、Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成できます。このモジュールは、64 ビット版のコンピューターでのみサポートされており、「[Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688)」の Microsoft ダウンロード センターからダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="9706d-p121">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>

## <a name="related-topics"></a><span data-ttu-id="9706d-264">関連トピック</span><span class="sxs-lookup"><span data-stu-id="9706d-264">Related topics</span></span>

[<span data-ttu-id="9706d-265">ユーザーの電話会議の設定を管理する</span><span class="sxs-lookup"><span data-stu-id="9706d-265">Manage the Audio Conferencing settings for a user</span></span>](manage-the-audio-conferencing-settings-for-a-user.md)
