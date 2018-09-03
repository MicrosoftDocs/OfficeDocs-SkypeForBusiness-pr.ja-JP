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
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'ダイヤルイン会議ライセンスと会議 ID を、ユーザーとその他多くのダイヤルイン会議設定に割り当てるには、Skype for Business Online の手順をご覧ください。 '
ms.openlocfilehash: 7f4387e7d818730de3b2b0336453a3f6ec9b39e7
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2018
ms.locfileid: "23780493"
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization-in-skype-for-business-online"></a><span data-ttu-id="9c2a1-103">Skype for Business Online で組織の電話会議の設定を管理する</span><span class="sxs-lookup"><span data-stu-id="9c2a1-103">Manage the Audio Conferencing settings for my organization in Skype for Business Online</span></span>

> [!NOTE]
> <span data-ttu-id="9c2a1-104">Teams でこれらの設定を管理する場合は、[Microsoft Teams で組織の電話会議の設定を管理する](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-my-organization-in-teams) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9c2a1-104">If you want to manage these settings in Teams, see [Manage the Audio Conferencing settings for my organization in Microsoft Teams](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-my-organization-in-teams).</span></span>

<span data-ttu-id="9c2a1-105">1 つの場所で Skype for Business の電話会議のすべての設定を参照する方がより簡単な場合があります。</span><span class="sxs-lookup"><span data-stu-id="9c2a1-105">It might be easier for you to see all of the audio conferencing settings for Skype for Business and Microsoft Teams in one place.</span></span>


## <a name="assign-an-audio-conferencing-license"></a><span data-ttu-id="9c2a1-106">電話会議のライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="9c2a1-106">Assign an Audio Conferencing license</span></span>

> [!NOTE]
> <span data-ttu-id="9c2a1-107">To assign a license for a user****</span><span class="sxs-lookup"><span data-stu-id="9c2a1-107">You can't assign licenses using the **Skype for Business admin center**.</span></span> <span data-ttu-id="9c2a1-108">Office 365 管理センターを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9c2a1-108">You must use the Office 365 admin center.</span></span> <span data-ttu-id="9c2a1-109">「[Skype for Business のライセンスを割り当てる](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)」 をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9c2a1-109">See [Assign Skype for Business licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>

 <span data-ttu-id="9c2a1-110">**ユーザーへライセンスを割り当てるには**</span><span class="sxs-lookup"><span data-stu-id="9c2a1-110">**To assign a license for a user**</span></span>

1. <span data-ttu-id="9c2a1-111">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="9c2a1-111">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="9c2a1-112">次に [ **編集**]、[ **次へ**] を 2 回クリックし、ライセンスを選択して、[  > ] をクリックします。****</span><span class="sxs-lookup"><span data-stu-id="9c2a1-112">In the left navigation of the **Office 365 admin center**, go to **Users** > **Active users**, and then select the user or users from the list of available users.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9c2a1-113">操作手順と PowerShell のサンプル スクリプトについては、「**Skype for Business と Microsoft Teams のライセンスを割り当てる**」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9c2a1-113">If you are assigning licenses to up to 20 users at the same time, you can use the **Select a view** drop-down then choose one of the options or create your own view.</span></span> <span data-ttu-id="9c2a1-114">操作ウィンドウの [ **製品ライセンス**] で [ **編集**] をクリックします。****</span><span class="sxs-lookup"><span data-stu-id="9c2a1-114">Then click **Edit**, **Next** twice then select the license and click **Submit**.</span></span> <span data-ttu-id="9c2a1-115">Windows PowerShell を使用して複数のユーザーにライセンスを割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="9c2a1-115">You can also assign licenses to multiple users by using Windows Powershell.</span></span> <span data-ttu-id="9c2a1-116">手順とサンプルの PowerShell スクリプトについては、「[Skype for Business のライセンスを割り当てる](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9c2a1-116">For instructions and sample PowerShell scripts, see [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>

3. <span data-ttu-id="9c2a1-117">[**製品のライセンス**] の下にある [操作] ウィンドウで、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9c2a1-117">In the Action pane under **Product licenses**, click **Edit**.</span></span>

4. <span data-ttu-id="9c2a1-118">[**製品のライセンス**] ページで、[**電話会議**] をオンにして [**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9c2a1-118">On the **Product Licenses** page, turn on **Audio Conferencing** and then click **Save**.</span></span> <span data-ttu-id="9c2a1-119">ライセンスについての詳細は、「[Skype for Business のアドイン ライセンス](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)「 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9c2a1-119">For more on licensing, see [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>

> [!NOTE]
> <span data-ttu-id="9c2a1-p104">ユーザーに会議 ID を割り当てる</span><span class="sxs-lookup"><span data-stu-id="9c2a1-p104">After you assign the license, Microsoft might not appear initially in the list as an audio conferencing provider. If this happens, either log out of the Office 365 admin center or press CTRL+F5 to refresh the browser window.</span></span>

## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a><span data-ttu-id="9c2a1-122">電話会議ユーザーに送信されたメールを有効化または無効化する</span><span class="sxs-lookup"><span data-stu-id="9c2a1-122">Enable or disable emails sent to audio conferencing users</span></span>

<span data-ttu-id="9c2a1-123">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Skype for Business 管理センターを使用する**</span><span class="sxs-lookup"><span data-stu-id="9c2a1-123">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="9c2a1-124">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="9c2a1-124">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="9c2a1-125">On the **Microsoft bridge settings** page, check or uncheck the  > .********</span><span class="sxs-lookup"><span data-stu-id="9c2a1-125">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>

3. <span data-ttu-id="9c2a1-126">電話会議の設定を使用してユーザーにメールを送信することもできます。これには、ユーザーの電話会議プロパティに移動して、[ **電話会議情報をメールで送信**] をクリックします。****</span><span class="sxs-lookup"><span data-stu-id="9c2a1-126">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>

4. <span data-ttu-id="9c2a1-127">ユーザーの電話会議プロパティに移動し、[ **電話会議情報をメールで送信**] をクリックすると、電話会議の設定が含まれるメールをユーザーに送信することもできます。会議 ID と電話会議用の既定の電話番号は会議出席依頼に記載されていますが、PIN は記載されていません。</span><span class="sxs-lookup"><span data-stu-id="9c2a1-127">Click **Save**.</span></span>

    <span data-ttu-id="9c2a1-p105">ユーザーの電話会議プロパティに移動し、[ **電話会議情報をメールで送信**] をクリックすると、電話会議の設定が含まれるメールをユーザーに送信することもできます。</span><span class="sxs-lookup"><span data-stu-id="9c2a1-p105">You can also send emails to the user with the audio conferencing settings by going to the user's audio conferencing properties and clicking **Send conference info via email**. The conference ID and default audio conferencing phone number is included on the meeting invite but not the PIN.</span></span>

    <span data-ttu-id="9c2a1-130">[電話会議の情報が記載されたメールをユーザーに送信する](send-an-email-to-a-user-with-their-dial-in-information.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9c2a1-130">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

<span data-ttu-id="9c2a1-131">**The conference ID and default dial-in conferencing phone number is included on the meeting invite but not the PIN.**</span><span class="sxs-lookup"><span data-stu-id="9c2a1-131">**Using Windows PowerShell**</span></span>

- <span data-ttu-id="9c2a1-132">Windows PowerShell を使用する</span><span class="sxs-lookup"><span data-stu-id="9c2a1-132">You can also use the Windows PowerShell and run:</span></span>

  ```
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

    <span data-ttu-id="9c2a1-133">Windows PowerShell を使用して、次を実行することもできます。[](https://go.microsoft.com/fwlink/?LinkId=627285)</span><span class="sxs-lookup"><span data-stu-id="9c2a1-133">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) to manage other settings for your organization, including email.</span></span>

## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a><span data-ttu-id="9c2a1-134">You can also use the Windows PowerShell and run:</span><span class="sxs-lookup"><span data-stu-id="9c2a1-134">Change the sender's contact information in email messages sent to users</span></span>

<span data-ttu-id="9c2a1-p106">ユーザーに送信されるメール メッセージの、差出人の連絡先情報を変更する[](https://go.microsoft.com/fwlink/?LinkId=627285)</span><span class="sxs-lookup"><span data-stu-id="9c2a1-p106">You can make changes to the email that is automatically sent to your users, including the actual email address and the display name of the sender's contact information. By default, the sender of the emails is Office 365, but you can change the email address and display name using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet. To make changes to the email address that is sending the email to the users, you must:</span></span>

- <span data-ttu-id="9c2a1-138">Enter the email display name in the  _SendEmailFromDisplayName_ parameter.</span><span class="sxs-lookup"><span data-stu-id="9c2a1-138">Enter the email address in the _SendEmailFromAddress_ parameter.</span></span>

- <span data-ttu-id="9c2a1-139">メールの差出人のメール アドレスやメールの表示名など、ユーザーに送信したメールの内容を変更するには、次のコマンドを実行します。__</span><span class="sxs-lookup"><span data-stu-id="9c2a1-139">Enter the email display name in the  _SendEmailFromDisplayName_ parameter.</span></span>

- <span data-ttu-id="9c2a1-140">メール アドレス情報を変更したい場合は、カスタムのメール アドレスから送信されるメールが、組織の受信メール ポリシーで許可されていることを確認する必要があります。____</span><span class="sxs-lookup"><span data-stu-id="9c2a1-140">Set the _SendEmailOverride_ parameter to _True_.</span></span>

<span data-ttu-id="9c2a1-141">If you want to change the email address information, you need to make sure that the inbound email policies of your organization allow emails that come from the custom email address.</span><span class="sxs-lookup"><span data-stu-id="9c2a1-141">You can make changes to the email sent to users, such as the email address that the email is sent from or the display name for the email by running:</span></span>

```
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

<span data-ttu-id="9c2a1-142">「ダイヤルイン会議の設定が変更されたユーザーにメールを自動的に送信する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9c2a1-142">If you want to change the email address information, you need to make sure that the inbound email policies of your organization allow emails that come from the custom email address.</span></span>

<span data-ttu-id="9c2a1-143">会議 ID をリセットする[](https://go.microsoft.com/fwlink/?LinkId=627285)</span><span class="sxs-lookup"><span data-stu-id="9c2a1-143">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet to manage other settings for your organization, including email.</span></span>

<span data-ttu-id="9c2a1-144">職場または学校のアカウントを使用して、Office 365 にサインインします。[](emails-sent-to-users-when-their-settings-change.md)</span><span class="sxs-lookup"><span data-stu-id="9c2a1-144">See [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md).</span></span>

## <a name="reset-the-meeting-conference-id"></a><span data-ttu-id="9c2a1-145">Sign in to Office 365 with your work or school account.</span><span class="sxs-lookup"><span data-stu-id="9c2a1-145">Reset the meeting conference ID</span></span>

1. <span data-ttu-id="9c2a1-146">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="9c2a1-146">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="9c2a1-147">In the Skype for Business admin centerDial-in conferencing, in the Action page under Conference ID click Reset.**** > ****</span><span class="sxs-lookup"><span data-stu-id="9c2a1-147">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="9c2a1-148">In the ** Reset conference ID?** window, click **Yes**. A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled. It's enabled by default.************</span><span class="sxs-lookup"><span data-stu-id="9c2a1-148">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and in the Action pane under **Conference ID**, click **Reset**.</span></span>

4. <span data-ttu-id="9c2a1-p107">In the ** Reset conference ID?** window, click **Yes**.****</span><span class="sxs-lookup"><span data-stu-id="9c2a1-p107">In the **Reset conference ID?** window, click **Yes**. A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled. It's enabled by default.</span></span>

    > [!IMPORTANT]
    >  <span data-ttu-id="9c2a1-p108">After a new conference ID is created, the old conference ID can't be used by callers.[](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)[](https://go.microsoft.com/fwlink/?LinkID=626047)[](https://www.microsoft.com/en-us/download/details.aspx?id=54079)</span><span class="sxs-lookup"><span data-stu-id="9c2a1-p108">After a new conference ID is created, the old conference ID can't be used by callers. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. The users can use the Skype for Business Meeting Migration Tool to update their existing meetings. To see how to download, install, and run the Skype for Business Meeting Update Tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](https://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span></span>

<span data-ttu-id="9c2a1-156">「[ユーザーの会議 ID をリセットする](reset-a-conference-id-for-a-user.md)」 をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9c2a1-156">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).</span></span>

## <a name="reset-a-conference-organizers-pin"></a><span data-ttu-id="9c2a1-157">会議主催者の PIN をリセットする</span><span class="sxs-lookup"><span data-stu-id="9c2a1-157">Reset a conference organizer's PIN</span></span>

<span data-ttu-id="9c2a1-158">ユーザーが計画する会議ごとに、固有の会議 ID が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="9c2a1-158">When dynamic conference IDs are used, each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="9c2a1-159">会議 ID は自動的に作成されてユーザーに割り当てられますが、ユーザーがこの ID を使用したくない場合や、特定の番号に設定したい場合、またはユーザーが会議 ID を思い出せなかったり失くしてしまう場合もあることでしょう。</span><span class="sxs-lookup"><span data-stu-id="9c2a1-159">Although a static conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="9c2a1-160">Skype for Business 管理センターと Windows PowerShell を使用して、ユーザーの会議 ID を閲覧、変更、リセットすることができます。</span><span class="sxs-lookup"><span data-stu-id="9c2a1-160">You can use the Skype for Business admin center and Windows PowerShell to view, change, and reset their conference ID.</span></span>


1. <span data-ttu-id="9c2a1-161">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="9c2a1-161">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="9c2a1-162">Sign in to Office 365 with your work or school account.**** > ********</span><span class="sxs-lookup"><span data-stu-id="9c2a1-162">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>

3. <span data-ttu-id="9c2a1-163">管理者は、ユーザーに PIN を手動で送信する必要があります。****</span><span class="sxs-lookup"><span data-stu-id="9c2a1-163">Click **Users**, and then select the user that you want to reset the PIN for.</span></span>

4. <span data-ttu-id="9c2a1-164">PIN をリセットした後、PIN が表示されるのは 1 回だけです。********</span><span class="sxs-lookup"><span data-stu-id="9c2a1-164">In the Action pane, under **PIN**, click **Reset**.</span></span>

<span data-ttu-id="9c2a1-p110">リセットの直後に 1 回表示された後は、ユーザーのプロパティには PIN に代わって "\*\*\*\*\*" が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9c2a1-p110">Users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset. But if you have disabled automatically sending emails, a PIN reset email won't be sent and you will have to manually send the PIN to the user. The PIN will only be shown once after it has been reset. After it's displayed just after being reset, the PIN won't be shown anymore on the user properties; instead, \*\*\*\*\* will be shown.</span></span>

<span data-ttu-id="9c2a1-169">「[電話会議の PIN をリセットする](reset-the-audio-conferencing-pin.md)」 をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9c2a1-169">See [Reset the Audio Conferencing PIN for a user](reset-the-audio-conferencing-pin.md).</span></span>

## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="9c2a1-170">電話会議の情報が記載されたメールをユーザーに送信する</span><span class="sxs-lookup"><span data-stu-id="9c2a1-170">Send an email with Audio Conferencing information to a user</span></span>

1. <span data-ttu-id="9c2a1-171">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="9c2a1-171">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="9c2a1-172">Sign in to Office 365 with your work or school account.**** > ********</span><span class="sxs-lookup"><span data-stu-id="9c2a1-172">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>

3. <span data-ttu-id="9c2a1-173">Go to the Office 365 admin centerSkype for Business and in the left navigation click Dial-in conferencing****</span><span class="sxs-lookup"><span data-stu-id="9c2a1-173">Click **Users**, and then select the user that you want to reset the PIN for.</span></span>

4. <span data-ttu-id="9c2a1-174">操作ウィンドウで、[ **電話会議情報をメールで送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9c2a1-174">In the Action pane, click **Send conference info via email**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9c2a1-175">この操作を行っても、電話会議の PIN はユーザーに送信されません。</span><span class="sxs-lookup"><span data-stu-id="9c2a1-175">When you do this, the audio conferencing PIN isn't sent to the user.</span></span>

<span data-ttu-id="9c2a1-176">「[電話会議の情報が記載されたメールをユーザーに送信する](send-an-email-to-a-user-with-their-dial-in-information.md) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9c2a1-176">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>

## <a name="setting-the-phone-numbers-included-on-invites"></a><span data-ttu-id="9c2a1-177">会議招集に含まれる電話番号を設定する</span><span class="sxs-lookup"><span data-stu-id="9c2a1-177">Set the phone numbers included on invites</span></span>

1. <span data-ttu-id="9c2a1-178">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="9c2a1-178">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="9c2a1-179">Sign in to Office 365 with your work or school account.**** > ****</span><span class="sxs-lookup"><span data-stu-id="9c2a1-179">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="9c2a1-p111">左側のナビゲーションで、[**電話会議**]  >  [**ユーザー**] の順に開きます。電話会議用に有効化したいユーザーを選択してください。</span><span class="sxs-lookup"><span data-stu-id="9c2a1-p111">In the left navigation, go to **Audio conferencing** > **Users**. Select the user that you want to enable for Audio Conferencing.</span></span>

4. <span data-ttu-id="9c2a1-182">[操作] ウィンドウで、[**有料番号**] を、また許可されている場合は [**無料番号**] も設定することができます。</span><span class="sxs-lookup"><span data-stu-id="9c2a1-182">In the Action pane, you can set the **Toll number** and, if allowed, the **Toll-free number**.</span></span>

5. <span data-ttu-id="9c2a1-183">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9c2a1-183">Click **Save**.</span></span>

<span data-ttu-id="9c2a1-184">「[会議招集に含まれる電話番号を設定する](set-the-phone-numbers-included-on-invites.md)」 をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9c2a1-184">See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites.md).</span></span>


## <a name="choosing-audio-conferencing-bridge-settings"></a><span data-ttu-id="9c2a1-185">電話会議ブリッジの設定を選択する</span><span class="sxs-lookup"><span data-stu-id="9c2a1-185">Setting audio conferencing bridge settings</span></span>

<span data-ttu-id="9c2a1-186">**呼び出しをしたユーザーが会議に参加する場合の会議のエクスペリエンスを設定する**</span><span class="sxs-lookup"><span data-stu-id="9c2a1-186">**Set the meeting experience when callers join a meeting**</span></span>


1. <span data-ttu-id="9c2a1-187">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="9c2a1-187">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="9c2a1-188">Sign in to Office 365 with your work or school account.**** > ****</span><span class="sxs-lookup"><span data-stu-id="9c2a1-188">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="9c2a1-189">Go to the **Office 365 admin center****** > .****</span><span class="sxs-lookup"><span data-stu-id="9c2a1-189">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>

4. <span data-ttu-id="9c2a1-190">In the Skype for Business admin center, in the left navigation go to dial-in conferencingMicrosoft bridge settings.****</span><span class="sxs-lookup"><span data-stu-id="9c2a1-190">Under **Meeting join experience**, select the following actions:</span></span>

  - <span data-ttu-id="9c2a1-p112">**Enable meeting entry and exit notifications to be turned on** This is selected by default. However if you uncheck it, users that have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span><span class="sxs-lookup"><span data-stu-id="9c2a1-p112">**Enable meeting entry and exit notifications to be turned on** This is selected by default. If you clear this check box, users who have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span></span>

    <span data-ttu-id="9c2a1-193">これは、ユーザーが Skype for Business アプリを使用して会議に参加し、会議の Skype 会議 **オプション** メニューで **ユーザーが参加または退席した時に通知する** を変更した場合に、会議ごとに設定することができます。</span><span class="sxs-lookup"><span data-stu-id="9c2a1-193">This can be set on a meeting-by-meeting basis when a user joins a meeting using a Skype for Business client and they modify the **Announce when people enter or leave** setting in the Skype Meeting Options menu of the meeting.</span></span>

  - <span data-ttu-id="9c2a1-p113">「**電話会議ブリッジの設定を変更する**」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9c2a1-p113">**Ask callers to record their name before joining the meeting** This is selected by default. If you clear this check box, callers won't be asked to record their name before they join a meeting.</span></span>

5. <span data-ttu-id="9c2a1-196">Sign in to Office 365 with your work or school account.****</span><span class="sxs-lookup"><span data-stu-id="9c2a1-196">After you make your changes, click **Save**.</span></span>
    
<span data-ttu-id="9c2a1-197">Go to the Office 365 admin centerSkype for Business.[](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge)</span><span class="sxs-lookup"><span data-stu-id="9c2a1-197">See [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span></span>
  
 <span data-ttu-id="9c2a1-198">**In the Skype for Business admin center, in the left navigation go to dial-in conferencingMicrosoft bridge settings.**</span><span class="sxs-lookup"><span data-stu-id="9c2a1-198">**Set the PIN length for meetings**</span></span>

1. <span data-ttu-id="9c2a1-199">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="9c2a1-199">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="9c2a1-200">Sign in to Office 365 with your work or school account.**** > ****</span><span class="sxs-lookup"><span data-stu-id="9c2a1-200">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="9c2a1-201">既定値は 5 です。******** > ****</span><span class="sxs-lookup"><span data-stu-id="9c2a1-201">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>

4. <span data-ttu-id="9c2a1-202">The PIN can only be from 4 to 12 digits. The default is 5.************</span><span class="sxs-lookup"><span data-stu-id="9c2a1-202">Under **Security**, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>

    <span data-ttu-id="9c2a1-p114">The PIN can only be from 4 to 12 digits.</span><span class="sxs-lookup"><span data-stu-id="9c2a1-p114">The PIN must be between 4 and 12 digits. The default is 5.</span></span>
    
<span data-ttu-id="9c2a1-205">職場または学校のアカウントを使用して、Office 365 にサインインします。[](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge)</span><span class="sxs-lookup"><span data-stu-id="9c2a1-205">See [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span></span>
  
 <span data-ttu-id="9c2a1-206">**Sign in to Office 365 with your work or school account.**</span><span class="sxs-lookup"><span data-stu-id="9c2a1-206">**Enable or disable email from being sent to audio users**</span></span>

1. <span data-ttu-id="9c2a1-207">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="9c2a1-207">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="9c2a1-208">On the **Microsoft bridge settings** page, check or uncheck the  > .********</span><span class="sxs-lookup"><span data-stu-id="9c2a1-208">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>

3. <span data-ttu-id="9c2a1-209">電話会議の設定を使用してユーザーにメールを送信することもできます。これには、ユーザーの電話会議プロパティに移動して、[ **電話会議情報をメールで送信**] をクリックします。****</span><span class="sxs-lookup"><span data-stu-id="9c2a1-209">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>

4. <span data-ttu-id="9c2a1-210">電話会議の設定を使用してユーザーにメールを送信することもできます。****</span><span class="sxs-lookup"><span data-stu-id="9c2a1-210">Click **Save**.</span></span>

    <span data-ttu-id="9c2a1-211">これには、ユーザーの電話会議プロパティに移動して、[ **電話会議情報をメールで送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9c2a1-211">You can also send email to the user with the audio conferencing settings, by going to the user's audio conferencing properties and clicking **Send conference info via email**.</span></span>

    <span data-ttu-id="9c2a1-212">この操作を行うと、会議 ID と電話会議の番号のみが含まれるメールが送信されますが、そのメールに PIN は含まれません。</span><span class="sxs-lookup"><span data-stu-id="9c2a1-212">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span></span>

    <span data-ttu-id="9c2a1-213">「[電話会議の情報が記載されたメールをユーザーに送信する](send-an-email-to-a-user-with-their-dial-in-information.md) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9c2a1-213">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>

## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a><span data-ttu-id="9c2a1-214">電話会議ブリッジでプライマリ (既定) とセカンダリ (代替) の言語を参照して設定する</span><span class="sxs-lookup"><span data-stu-id="9c2a1-214">See and set the primary and secondary languages on an audio conferencing bridge</span></span>


1. <span data-ttu-id="9c2a1-215">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="9c2a1-215">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="9c2a1-216">Sign in to Office 365 with your work or school account.**** > ****</span><span class="sxs-lookup"><span data-stu-id="9c2a1-216">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="9c2a1-217">Go to the **Office 365 admin center********Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="9c2a1-217">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and then click **Microsoft bridge**.</span></span>

4. <span data-ttu-id="9c2a1-218">リストから電話番号を選択し、操作ウィンドウで [ **言語を設定**] をクリックしてから、[ **言語を設定**] ページで [ **第 1 言語**] リストをクリックして、サポートされている言語の完全なリストを表示します。</span><span class="sxs-lookup"><span data-stu-id="9c2a1-218">Select a phone number from the list, click **Set languages** in the Action pane, and then on the **Set languages** page, click the use the **Primary language** list to view the complete list of supported languages.</span></span>

    <span data-ttu-id="9c2a1-p115">Microsoft を電話会議プロバイダーとして選ぶときに、サポートされる第 1 言語と第 2 言語を設定することもできます。発信者に対する言語の表示順は、リストで言語を選んだ順序になります。</span><span class="sxs-lookup"><span data-stu-id="9c2a1-p115">You can also set the primary and secondary languages that are supported when you select Microsoft as the audio conferencing provider. The order that you select in the lists is the same order in which languages will be presented to callers.</span></span>

<span data-ttu-id="9c2a1-221">You can also set the primary and secondary languages that are supported when you select Microsoft as the dial-in conferencing provider. The order that you select in the drop-downs will be the order of the languages that will be presented to the callers.[](set-auto-attendant-languages-for-audio-conferencing.md)</span><span class="sxs-lookup"><span data-stu-id="9c2a1-221">See [Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing.md).</span></span>

## <a name="see-audio-conferencing-dial-in-numbers"></a><span data-ttu-id="9c2a1-222">You can also set the primary and secondary languages that are supported when you select Microsoft as the dial-in conferencing provider.</span><span class="sxs-lookup"><span data-stu-id="9c2a1-222">See audio conferencing dial-in numbers</span></span>

1. <span data-ttu-id="9c2a1-223">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="9c2a1-223">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="9c2a1-224">「電話会議のダイヤルイン番号」をご覧ください**** > ****</span><span class="sxs-lookup"><span data-stu-id="9c2a1-224">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="9c2a1-p116">職場または学校のアカウントを使用して、Office 365 にサインインします。******** > ****</span><span class="sxs-lookup"><span data-stu-id="9c2a1-p116">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge**. Here you can:</span></span>

  - <span data-ttu-id="9c2a1-227">電話会議で使うために Office 365 によって設定された電話番号を表示する。</span><span class="sxs-lookup"><span data-stu-id="9c2a1-227">View the phone numbers that are set by Office 365 to be used for Audio Conferencing.</span></span>

  - <span data-ttu-id="9c2a1-228">場所を表示したり、電話会議の自動応答で使用する第 1 言語と第 2 言語を表示したりする。</span><span class="sxs-lookup"><span data-stu-id="9c2a1-228">View the location, and the primary and secondary languages, that will be used by the Audio Conferencing auto attendant.</span></span>

  - <span data-ttu-id="9c2a1-p117">ユーザーが電話会議で有効になっているときに、ユーザーに渡される既定の電話番号を選択します。ただし、電話会議ブリッジの既定の電話番号が変わっても、既存のユーザーの既定の電話番号は変わりません。</span><span class="sxs-lookup"><span data-stu-id="9c2a1-p117">Select the default phone number that will be given to users when they are enabled for Audio Conferencing. However, if the default phone number of the audio conferencing bridge changes, the default phone number for existing users won't change.</span></span>

<span data-ttu-id="9c2a1-231">You can select the dial-in conferencing default phone number that will be given to users when they are enabled for dial-in conferencing. However, if the default phone number of the dial-in conferencing bridge changes, the default phone number for existing users won't change.**** > ****</span><span class="sxs-lookup"><span data-stu-id="9c2a1-231">You can go to **Audio conferencing** > **Users** and select the user's properties to change the default number for a user by choosing a new number from the list of numbers that are available in your organization.</span></span>

<span data-ttu-id="9c2a1-232">You can select the dial-in conferencing default phone number that will be given to users when they are enabled for dial-in conferencing.[](see-a-list-of-audio-conferencing-numbers.md)</span><span class="sxs-lookup"><span data-stu-id="9c2a1-232">See [See a list of Audio Conferencing numbers](see-a-list-of-audio-conferencing-numbers.md).</span></span>

## <a name="see-a-list-of-users-that-are-enabled"></a><span data-ttu-id="9c2a1-233">However, if the default phone number of the dial-in conferencing bridge changes, the default phone number for existing users won't change.</span><span class="sxs-lookup"><span data-stu-id="9c2a1-233">See a list of users that are enabled</span></span>

1. <span data-ttu-id="9c2a1-234">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="9c2a1-234">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="9c2a1-235">有効になっているユーザーのリストを表示する**** > ****</span><span class="sxs-lookup"><span data-stu-id="9c2a1-235">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="9c2a1-236">職場または学校のアカウントを使用して、Office 365 にサインインします。************</span><span class="sxs-lookup"><span data-stu-id="9c2a1-236">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**> and then **Users**.</span></span>

<span data-ttu-id="9c2a1-237">Sign in to Office 365 with your work or school account.[](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md)</span><span class="sxs-lookup"><span data-stu-id="9c2a1-237">See [See a list of users that are enabled for Audio Conferencing](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).</span></span>

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="9c2a1-238">Go to the Office 365 admin centerSkype for Business.</span><span class="sxs-lookup"><span data-stu-id="9c2a1-238">Want to know how to manage with Windows PowerShell?</span></span>

<span data-ttu-id="9c2a1-p118">In the Skype for Business admin center, in the left navigation go to Dial-in conferencing> and then Dial-in users.</span><span class="sxs-lookup"><span data-stu-id="9c2a1-p118">There are several settings that you can manage at the organization level using Windows PowerShell. This makes it easy to apply settings to all of your users.</span></span>

<span data-ttu-id="9c2a1-241">Windows PowerShell を使用して組織レベルで管理できる複数の設定があります。[](https://go.microsoft.com/fwlink/?LinkId=627324)</span><span class="sxs-lookup"><span data-stu-id="9c2a1-241">To get more help on each cmdlet, see [Skype for Business Online cmdlets](https://go.microsoft.com/fwlink/?LinkId=627324).</span></span>

<span data-ttu-id="9c2a1-242">このため、簡単にこれらの設定をすべてのユーザーに適用できます。</span><span class="sxs-lookup"><span data-stu-id="9c2a1-242">Here are the organization-level settings:</span></span>

- <span data-ttu-id="9c2a1-243">**組織レベルの設定を以下に示します。**__</span><span class="sxs-lookup"><span data-stu-id="9c2a1-243">**Setting entry/exit notifications** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableEntryExitNotifications $true|$false
  ```

- <span data-ttu-id="9c2a1-244">**There are several settings that you can manage settings at the organization level using Windows PowerShell. This makes it easy to make these settings and have them apply to all of your users. Here are the organization level settings:**__</span><span class="sxs-lookup"><span data-stu-id="9c2a1-244">**Setting name recording** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableNameRecording $true|false
  ```

- <span data-ttu-id="9c2a1-245">**There are several settings that you can manage settings at the organization level using Windows PowerShell.**</span><span class="sxs-lookup"><span data-stu-id="9c2a1-245">**Setting the PIN length** The default is 5.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -PinLength 7
  ```

- <span data-ttu-id="9c2a1-246">**This makes it easy to make these settings and have them apply to all of your users.**__</span><span class="sxs-lookup"><span data-stu-id="9c2a1-246">**Setting only dial-in meetings from a phone** The default _$false_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true|$false
  ```

- <span data-ttu-id="9c2a1-247">**Here are the organization level settings:**__</span><span class="sxs-lookup"><span data-stu-id="9c2a1-247">**Setting whether to send email to users** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

- <span data-ttu-id="9c2a1-248">**Windows PowerShell の場合、ユーザーの管理と、ユーザーに許可する操作や許可しない操作の管理に使います。Windows PowerShell により、単一の管理ポイントを使って Office 365 を管理でき、複数の作業を実行する必要があるときに日常業務を合理化できます。Windows PowerShell を使い始めるには、次のトピックを参照してください。**__</span><span class="sxs-lookup"><span data-stu-id="9c2a1-248">**Setting whether to send email from a different account** The default is  _$false_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromOverride $true|$false
  ```

- <span data-ttu-id="9c2a1-249">**Windows PowerShell の場合、ユーザーの管理と、ユーザーに許可する操作や許可しない操作の管理に使います。**__</span><span class="sxs-lookup"><span data-stu-id="9c2a1-249">**Setting the From address on email that is sent to users** The default is _$null_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromAddress
  ```

- <span data-ttu-id="9c2a1-250">**Windows PowerShell により、単一の管理ポイントを使って Office 365 を管理でき、複数の作業を実行する必要があるときに日常業務を合理化できます。**__</span><span class="sxs-lookup"><span data-stu-id="9c2a1-250">**Setting the display name for the email that is sent to users** The default is  _$null_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromDisplayName
  ```

 ## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="9c2a1-251">Windows PowerShell を使い始めるには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9c2a1-251">Want to know more about Windows PowerShell</span></span>
- <span data-ttu-id="9c2a1-p119">Windows PowerShell は、ユーザーと、ユーザーに許可されていることと許可されていないことを管理するためにあるということです。Windows PowerShell があれば、一元管理を使用して Office 365 を管理し、複数のタスクを抱えているときに、日常の仕事を簡素化することができます。Windows PowerShell を開始するには、これらのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9c2a1-p119">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="9c2a1-255">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="9c2a1-255">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

  - [<span data-ttu-id="9c2a1-256">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="9c2a1-256">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

- <span data-ttu-id="9c2a1-p120">多くのユーザーの設定を同時に変更するときなどは、Office 365 管理センターのみを使用するよりも、Windows PowerShell の方に、速度、わかりやすさ、生産性の点で多くのメリットがあります。</span><span class="sxs-lookup"><span data-stu-id="9c2a1-p120">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time. Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="9c2a1-259">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time.</span><span class="sxs-lookup"><span data-stu-id="9c2a1-259">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [<span data-ttu-id="9c2a1-260">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="9c2a1-260">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [<span data-ttu-id="9c2a1-261">Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行</span><span class="sxs-lookup"><span data-stu-id="9c2a1-261">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

    <span data-ttu-id="9c2a1-p121">Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行[](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="9c2a1-p121">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>

## <a name="related-topics"></a><span data-ttu-id="9c2a1-264">このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「Skype for Business Online 用 Windows PowerShell モジュール」からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="9c2a1-264">Related topics</span></span>

[<span data-ttu-id="9c2a1-265">ユーザーの電話会議の設定を管理する</span><span class="sxs-lookup"><span data-stu-id="9c2a1-265">Manage the Audio Conferencing settings for a user</span></span>](manage-the-audio-conferencing-settings-for-a-user.md)


