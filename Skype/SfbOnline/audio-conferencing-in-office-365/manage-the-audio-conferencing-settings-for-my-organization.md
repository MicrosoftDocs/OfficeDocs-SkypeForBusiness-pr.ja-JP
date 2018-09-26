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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'ユーザーおよびその他のダイヤルイン会議の設定にダイヤルイン会議のライセンスおよび会議 ID を割り当てる手順についてはオンライン ビジネスの Skype を参照してください。 '
ms.openlocfilehash: 7e420ef2c434807bf9e78cc1c61f808db745f3bc
ms.sourcegitcommit: 090ff859083ace43c08d483f4023009e8b6e79e4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/26/2018
ms.locfileid: "25018926"
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization-in-skype-for-business-online"></a><span data-ttu-id="78bc2-103">Skype for Business Online で組織の電話会議の設定を管理する</span><span class="sxs-lookup"><span data-stu-id="78bc2-103">Manage the Audio Conferencing settings for my organization in Skype for Business Online</span></span>

> [!NOTE]
> <span data-ttu-id="78bc2-104">Teams でこれらの設定を管理する場合は、[Microsoft Teams で組織の電話会議の設定を管理する](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-my-organization-in-teams) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="78bc2-104">If you want to manage these settings in Teams, see [Manage the Audio Conferencing settings for my organization in Microsoft Teams](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-my-organization-in-teams).</span></span>

<span data-ttu-id="78bc2-105">簡単に、すべて 1 か所でビジネス用の Skype のオーディオ会議設定の表示がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="78bc2-105">It might be easier for you to see all of the audio conferencing settings for Skype for Business in one place.</span></span>


## <a name="assign-an-audio-conferencing-license"></a><span data-ttu-id="78bc2-106">電話会議のライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="78bc2-106">Assign an Audio Conferencing license</span></span>

> [!NOTE]
> <span data-ttu-id="78bc2-107">To assign a license for a user\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="78bc2-107">You can't assign licenses using the **Skype for Business admin center**.</span></span> <span data-ttu-id="78bc2-108">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="78bc2-108">You must use the Office 365 admin center.</span></span> <span data-ttu-id="78bc2-109">ユーザーに会議 ID を割り当てる</span><span class="sxs-lookup"><span data-stu-id="78bc2-109">See [Assign Skype for Business licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>

 <span data-ttu-id="78bc2-110">最大 20 人までのライセンスを同時に割り当てている場合は、[ ビューの選択] ボックスを使用していずれかのオプションを選択するか、独自のビューを作成することができます。次に [ 編集]、[ 次へ] を 2 回クリックし、ライセンスを選択して、[ 送信] をクリックします。また、Windows Powershell を使用してライセンスを複数のユーザーに割り当てることもできます。操作手順と PowerShell のサンプル スクリプトについては、「Skype for Business と Microsoft Teams のライセンスを割り当てる」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="78bc2-110">**To assign a license for a user**</span></span>

1. <span data-ttu-id="78bc2-111">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="78bc2-111">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="78bc2-112">次に [ **編集**]、[ **次へ**] を 2 回クリックし、ライセンスを選択して、[  > ] をクリックします。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="78bc2-112">In the left navigation of the **Office 365 admin center**, go to **Users** > **Active users**, and then select the user or users from the list of available users.</span></span>

    > [!NOTE]
    > <span data-ttu-id="78bc2-113">操作手順と PowerShell のサンプル スクリプトについては、「**Skype for Business と Microsoft Teams のライセンスを割り当てる**」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="78bc2-113">If you are assigning licenses to up to 20 users at the same time, you can use the **Select a view** drop-down then choose one of the options or create your own view.</span></span> <span data-ttu-id="78bc2-114">操作ウィンドウの [ **製品ライセンス**] で [ **編集**] をクリックします。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="78bc2-114">Then click **Edit**, **Next** twice then select the license and click **Submit**.</span></span> <span data-ttu-id="78bc2-115">[ 製品ライセンス] ページで [ 電話会議] をオンにして、[ 保存] をクリックします。ライセンスの詳細については、「Skype for Business と Microsoft Teams のアドオン ライセンス」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="78bc2-115">You can also assign licenses to multiple users by using Windows Powershell.</span></span> <span data-ttu-id="78bc2-116">手順とサンプルの PowerShell スクリプトでは、[ビジネス ライセンスの割り当ての Skype](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="78bc2-116">For instructions and sample PowerShell scripts, see [Assign Skype for Business licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>

3. <span data-ttu-id="78bc2-117">ライセンスの詳細については、「**Skype for Business と Microsoft Teams のアドオン ライセンス**」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="78bc2-117">In the Action pane under **Product licenses**, click **Edit**.</span></span>

4. <span data-ttu-id="78bc2-118">ライセンスを割り当てると、電話会議プロバイダーのリストに Microsoft が表示されなくなることがあります。</span><span class="sxs-lookup"><span data-stu-id="78bc2-118">On the **Product Licenses** page, turn on **Audio Conferencing** and then click **Save**.</span></span> <span data-ttu-id="78bc2-119">ライセンスの詳細は、[アドオン ライセンスのビジネス用の Skype](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="78bc2-119">For more on licensing, see [Skype for Business add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>

> [!NOTE]
> <span data-ttu-id="78bc2-p104">ユーザーに会議 ID を割り当てる</span><span class="sxs-lookup"><span data-stu-id="78bc2-p104">After you assign the license, Microsoft might not appear initially in the list as an audio conferencing provider. If this happens, either log out of the Office 365 admin center or press CTRL+F5 to refresh the browser window.</span></span>

## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a><span data-ttu-id="78bc2-122">Skype for Business 管理センターまたは Windows PowerShell を使用すると、ユーザーへのメール送信を有効または無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="78bc2-122">Enable or disable emails sent to audio conferencing users</span></span>

<span data-ttu-id="78bc2-123">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Skype for Business の管理センターを使用する**</span><span class="sxs-lookup"><span data-stu-id="78bc2-123">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="78bc2-124">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="78bc2-124">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="78bc2-125">On the **Microsoft bridge settings** page, check or uncheck the  > .\*\*\*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="78bc2-125">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>

3. <span data-ttu-id="78bc2-126">電話会議の設定を使用してユーザーにメールを送信することもできます。これには、ユーザーの電話会議プロパティに移動して、[ **電話会議情報をメールで送信**] をクリックします。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="78bc2-126">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>

4. <span data-ttu-id="78bc2-127">ユーザーの電話会議プロパティに移動し、[ **電話会議情報をメールで送信**] をクリックすると、電話会議の設定が含まれるメールをユーザーに送信することもできます。会議 ID と電話会議用の既定の電話番号は会議出席依頼に記載されていますが、PIN は記載されていません。</span><span class="sxs-lookup"><span data-stu-id="78bc2-127">Click **Save**.</span></span>

    <span data-ttu-id="78bc2-p105">ユーザーの電話会議プロパティに移動し、[ **電話会議情報をメールで送信**] をクリックすると、電話会議の設定が含まれるメールをユーザーに送信することもできます。</span><span class="sxs-lookup"><span data-stu-id="78bc2-p105">You can also send emails to the user with the audio conferencing settings by going to the user's audio conferencing properties and clicking **Send conference info via email**. The conference ID and default audio conferencing phone number is included on the meeting invite but not the PIN.</span></span>

    <span data-ttu-id="78bc2-130">[電話会議の情報が記載されたメールをユーザーに送信する](send-an-email-to-a-user-with-their-dial-in-information.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="78bc2-130">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

<span data-ttu-id="78bc2-131">**The conference ID and default dial-in conferencing phone number is included on the meeting invite but not the PIN.**</span><span class="sxs-lookup"><span data-stu-id="78bc2-131">**Using Windows PowerShell**</span></span>

- <span data-ttu-id="78bc2-132">Windows PowerShell を使用する</span><span class="sxs-lookup"><span data-stu-id="78bc2-132">You can also use the Windows PowerShell and run:</span></span>

  ```
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

    <span data-ttu-id="78bc2-133">Windows PowerShell を使用して、次を実行することもできます。[](https://go.microsoft.com/fwlink/?LinkId=627285)</span><span class="sxs-lookup"><span data-stu-id="78bc2-133">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) to manage other settings for your organization, including email.</span></span>

## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a><span data-ttu-id="78bc2-134">You can also use the Windows PowerShell and run:</span><span class="sxs-lookup"><span data-stu-id="78bc2-134">Change the sender's contact information in email messages sent to users</span></span>

<span data-ttu-id="78bc2-p106">ユーザーに送信されるメール メッセージの、差出人の連絡先情報を変更する[](https://go.microsoft.com/fwlink/?LinkId=627285)</span><span class="sxs-lookup"><span data-stu-id="78bc2-p106">You can make changes to the email that is automatically sent to your users, including the actual email address and the display name of the sender's contact information. By default, the sender of the emails is Office 365, but you can change the email address and display name using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet. To make changes to the email address that is sending the email to the users, you must:</span></span>

- <span data-ttu-id="78bc2-138">Enter the email display name in the  _SendEmailFromDisplayName_ parameter.</span><span class="sxs-lookup"><span data-stu-id="78bc2-138">Enter the email address in the _SendEmailFromAddress_ parameter.</span></span>

- <span data-ttu-id="78bc2-139">メールの差出人のメール アドレスやメールの表示名など、ユーザーに送信したメールの内容を変更するには、次のコマンドを実行します。__</span><span class="sxs-lookup"><span data-stu-id="78bc2-139">Enter the email display name in the  _SendEmailFromDisplayName_ parameter.</span></span>

- <span data-ttu-id="78bc2-140">メール アドレス情報を変更したい場合は、カスタムのメール アドレスから送信されるメールが、組織の受信メール ポリシーで許可されていることを確認する必要があります。____</span><span class="sxs-lookup"><span data-stu-id="78bc2-140">Set the _SendEmailOverride_ parameter to _True_.</span></span>

<span data-ttu-id="78bc2-141">If you want to change the email address information, you need to make sure that the inbound email policies of your organization allow emails that come from the custom email address.</span><span class="sxs-lookup"><span data-stu-id="78bc2-141">You can make changes to the email sent to users, such as the email address that the email is sent from or the display name for the email by running:</span></span>

```
Set-CsOnlineDialInConferencingTenantSettings -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

<span data-ttu-id="78bc2-142">「ダイヤルイン会議の設定が変更されたユーザーにメールを自動的に送信する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="78bc2-142">If you want to change the email address information, you need to make sure that the inbound email policies of your organization allow emails that come from the custom email address.</span></span>

<span data-ttu-id="78bc2-143">会議 ID をリセットする[](https://go.microsoft.com/fwlink/?LinkId=627285)</span><span class="sxs-lookup"><span data-stu-id="78bc2-143">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet to manage other settings for your organization, including email.</span></span>

<span data-ttu-id="78bc2-144">職場または学校のアカウントを使用して、Office 365 にサインインします。[](emails-sent-to-users-when-their-settings-change.md)</span><span class="sxs-lookup"><span data-stu-id="78bc2-144">See [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md).</span></span>

## <a name="reset-the-meeting-conference-id"></a><span data-ttu-id="78bc2-145">Sign in to Office 365 with your work or school account.</span><span class="sxs-lookup"><span data-stu-id="78bc2-145">Reset the meeting conference ID</span></span>

1. <span data-ttu-id="78bc2-146">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="78bc2-146">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="78bc2-147">In the Skype for Business admin centerDial-in conferencing, in the Action page under Conference ID click Reset.\*\*\*\* > \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="78bc2-147">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="78bc2-148">In the \*\* Reset conference ID?\*\* window, click **Yes**. A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled. It's enabled by default.\*\*\*\*\*\*\*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="78bc2-148">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and in the Action pane under **Conference ID**, click **Reset**.</span></span>

4. <span data-ttu-id="78bc2-p107">In the \*\* Reset conference ID?\*\* window, click **Yes**.\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="78bc2-p107">In the **Reset conference ID?** window, click **Yes**. A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled. It's enabled by default.</span></span>

    > [!IMPORTANT]
    >  <span data-ttu-id="78bc2-p108">After a new conference ID is created, the old conference ID can't be used by callers.[](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)[](https://go.microsoft.com/fwlink/?LinkID=626047)[](https://www.microsoft.com/en-us/download/details.aspx?id=54079)</span><span class="sxs-lookup"><span data-stu-id="78bc2-p108">After a new conference ID is created, the old conference ID can't be used by callers. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. The users can use the Skype for Business Meeting Migration Tool to update their existing meetings. To see how to download, install, and run the Skype for Business Meeting Update Tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](https://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span></span>

<span data-ttu-id="78bc2-156">[](reset-a-conference-id-for-a-user.md)Reset a conference organizer's PIN</span><span class="sxs-lookup"><span data-stu-id="78bc2-156">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).</span></span>

## <a name="reset-a-conference-organizers-pin"></a><span data-ttu-id="78bc2-157">静的会議 ID は自動的に作成されユーザーに割り当てられますが、ユーザーがそれを使いたくないため特定の番号に設定しようと考える場合や、ユーザーが会議 ID を覚えられない、または紛失してしまう場合があります。Skype for Business 管理センターおよび Windows PowerShell を使用すると、ユーザーの会議 ID を表示、変更、リセットすることができます。</span><span class="sxs-lookup"><span data-stu-id="78bc2-157">Reset a conference organizer's PIN</span></span>

<span data-ttu-id="78bc2-158">ユーザーをスケジュールする会議ごとに固有の会議 ID が割り当てられますを取得</span><span class="sxs-lookup"><span data-stu-id="78bc2-158">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="78bc2-159">会議 ID が自動的に作成され、ユーザーに割り当てられているがあります、ユーザーは、この 1 つを使用する場合は、特定の数に設定するとユーザーが覚えられないか、会議 ID が失われています。</span><span class="sxs-lookup"><span data-stu-id="78bc2-159">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="78bc2-160">ユーザーが電話会議で有効になるか、PIN がリセットされた場合、ユーザーは自分の PIN が含まれるメールを受信します。ただし、メールの自動送信を無効にしても、PIN リセットのメールは送信されません。管理者は、ユーザーに PIN を手動で送信する必要があります。PIN をリセットした後、PIN が表示されるのは 1 回だけです。リセットの直後に 1 回表示された後は、ユーザーのプロパティには PIN に代わって "\*\*\*\*\*" が表示されます。</span><span class="sxs-lookup"><span data-stu-id="78bc2-160">You can use the Skype for Business admin center and Windows PowerShell to view, change, and reset their conference ID.</span></span>


1. <span data-ttu-id="78bc2-161">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="78bc2-161">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="78bc2-162">Sign in to Office 365 with your work or school account.\*\*\*\* > \*\*\*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="78bc2-162">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>

3. <span data-ttu-id="78bc2-163">管理者は、ユーザーに PIN を手動で送信する必要があります。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="78bc2-163">Click **Users**, and then select the user that you want to reset the PIN for.</span></span>

4. <span data-ttu-id="78bc2-164">PIN をリセットした後、PIN が表示されるのは 1 回だけです。\*\*\*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="78bc2-164">In the Action pane, under **PIN**, click **Reset**.</span></span>

<span data-ttu-id="78bc2-p110">リセットの直後に 1 回表示された後は、ユーザーのプロパティには PIN に代わって "\*\*\*\*\*" が表示されます。</span><span class="sxs-lookup"><span data-stu-id="78bc2-p110">Users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset. But if you have disabled automatically sending emails, a PIN reset email won't be sent and you will have to manually send the PIN to the user. The PIN will only be shown once after it has been reset. After it's displayed just after being reset, the PIN won't be shown anymore on the user properties; instead, \*\*\*\*\* will be shown.</span></span>

<span data-ttu-id="78bc2-169">[オーディオ会議の PIN のリセット](reset-the-audio-conferencing-pin.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="78bc2-169">See [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin.md).</span></span>

## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="78bc2-170">電話会議の情報が記載されたメールをユーザーに送信する</span><span class="sxs-lookup"><span data-stu-id="78bc2-170">Send an email with Audio Conferencing information to a user</span></span>

1. <span data-ttu-id="78bc2-171">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="78bc2-171">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="78bc2-172">Sign in to Office 365 with your work or school account.\*\*\*\* > \*\*\*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="78bc2-172">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>

3. <span data-ttu-id="78bc2-173">Go to the Office 365 admin centerSkype for Business and in the left navigation click Dial-in conferencing\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="78bc2-173">Click **Users**, and then select the user that you want to reset the PIN for.</span></span>

4. <span data-ttu-id="78bc2-174">操作ウィンドウで、[ **電話会議情報をメールで送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="78bc2-174">In the Action pane, click **Send conference info via email**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="78bc2-175">この操作を行っても、電話会議の PIN はユーザーに送信されません。</span><span class="sxs-lookup"><span data-stu-id="78bc2-175">When you do this, the audio conferencing PIN isn't sent to the user.</span></span>

<span data-ttu-id="78bc2-176">When you do this, the dial-in conferencing PIN isn't sent to the user.</span><span class="sxs-lookup"><span data-stu-id="78bc2-176">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>

## <a name="setting-the-phone-numbers-included-on-invites"></a><span data-ttu-id="78bc2-177">携帯電話への招待に含まれている番号を設定します。</span><span class="sxs-lookup"><span data-stu-id="78bc2-177">Setting the phone numbers included on invites</span></span>

1. <span data-ttu-id="78bc2-178">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="78bc2-178">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="78bc2-179">Sign in to Office 365 with your work or school account.\*\*\*\* > \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="78bc2-179">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="78bc2-p111">Go to the **Office 365 admin center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="78bc2-p111">In the left navigation, go to **Audio conferencing** > **Users**. Select the user that you want to enable for Audio Conferencing.</span></span>

4. <span data-ttu-id="78bc2-182">[操作] ウィンドウで、[**有料番号**] を、また許可されている場合は [**無料番号**] も設定することができます。</span><span class="sxs-lookup"><span data-stu-id="78bc2-182">In the Action pane, you can set the **Toll number** and, if allowed, the **Toll-free number**.</span></span>

5. <span data-ttu-id="78bc2-183">The default dial-in conferencing phone number of a user is the number that is shown on the meeting invite when they schedule a meeting.</span><span class="sxs-lookup"><span data-stu-id="78bc2-183">Click **Save**.</span></span>

<span data-ttu-id="78bc2-184">「[出席依頼に含まれている会議の開催者のために電話会議の電話番号を設定する](set-the-phone-numbers-included-on-invites.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="78bc2-184">See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites.md).</span></span>


## <a name="choosing-audio-conferencing-bridge-settings"></a><span data-ttu-id="78bc2-185">オーディオ会議ブリッジの設定を選択します。</span><span class="sxs-lookup"><span data-stu-id="78bc2-185">Choosing audio conferencing bridge settings</span></span>

<span data-ttu-id="78bc2-186">\*\*\*\* Setting dial-in conferencing bridge settings</span><span class="sxs-lookup"><span data-stu-id="78bc2-186">**Set the meeting experience when callers join a meeting**</span></span>


1. <span data-ttu-id="78bc2-187">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="78bc2-187">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="78bc2-188">Sign in to Office 365 with your work or school account.\*\*\*\* > \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="78bc2-188">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="78bc2-189">Go to the \*\*Office 365 admin center\*\*\*\*\*\* > .\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="78bc2-189">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>

4. <span data-ttu-id="78bc2-190">In the Skype for Business admin center, in the left navigation go to dial-in conferencingMicrosoft bridge settings.\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="78bc2-190">Under **Meeting join experience**, select the following actions:</span></span>

  - <span data-ttu-id="78bc2-p112">**Enable meeting entry and exit notifications to be turned on** This is selected by default. However if you uncheck it, users that have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span><span class="sxs-lookup"><span data-stu-id="78bc2-p112">**Enable meeting entry and exit notifications to be turned on** This is selected by default. If you clear this check box, users who have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span></span>

    <span data-ttu-id="78bc2-193">ユーザーがビジネス アプリケーションに、Skype を使用して会議に参加し、Skype ミーティングの**オプション**] メニューの [会議の**アナウンスの人を入力するかのままにするとき**の設定を変更するときに会議ごとの単位で設定できます。</span><span class="sxs-lookup"><span data-stu-id="78bc2-193">This can be set on a meeting-by-meeting basis when a user joins a meeting using a Skype for Business app and they modify the **Announce when people enter or leave** setting in the Skype Meeting **Options** menu of the meeting.</span></span>

  - <span data-ttu-id="78bc2-p113">「**電話会議ブリッジの設定を変更する**」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="78bc2-p113">**Ask callers to record their name before joining the meeting** This is selected by default. If you clear this check box, callers won't be asked to record their name before they join a meeting.</span></span>

5. <span data-ttu-id="78bc2-196">Sign in to Office 365 with your work or school account.\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="78bc2-196">After you make your changes, click **Save**.</span></span>
    
<span data-ttu-id="78bc2-197">Go to the Office 365 admin centerSkype for Business.[](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge)</span><span class="sxs-lookup"><span data-stu-id="78bc2-197">See [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span></span>
  
 <span data-ttu-id="78bc2-198">**In the Skype for Business admin center, in the left navigation go to dial-in conferencingMicrosoft bridge settings.**</span><span class="sxs-lookup"><span data-stu-id="78bc2-198">**Set the PIN length for meetings**</span></span>

1. <span data-ttu-id="78bc2-199">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="78bc2-199">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="78bc2-200">Sign in to Office 365 with your work or school account.\*\*\*\* > \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="78bc2-200">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="78bc2-201">既定値は 5 です。\*\*\*\*\*\*\*\* > \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="78bc2-201">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>

4. <span data-ttu-id="78bc2-202">The PIN can only be from 4 to 12 digits. The default is 5.\*\*\*\*\*\*\*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="78bc2-202">Under **Security**, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>

    <span data-ttu-id="78bc2-p114">The PIN can only be from 4 to 12 digits.</span><span class="sxs-lookup"><span data-stu-id="78bc2-p114">The PIN must be between 4 and 12 digits. The default is 5.</span></span>
    
<span data-ttu-id="78bc2-205">職場または学校のアカウントを使用して、Office 365 にサインインします。[](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge)</span><span class="sxs-lookup"><span data-stu-id="78bc2-205">See [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span></span>
  
 <span data-ttu-id="78bc2-206">**Sign in to Office 365 with your work or school account.**</span><span class="sxs-lookup"><span data-stu-id="78bc2-206">**Enable or disable email from being sent to audio users**</span></span>

1. <span data-ttu-id="78bc2-207">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="78bc2-207">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="78bc2-208">On the **Microsoft bridge settings** page, check or uncheck the  > .\*\*\*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="78bc2-208">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>

3. <span data-ttu-id="78bc2-209">電話会議の設定を使用してユーザーにメールを送信することもできます。これには、ユーザーの電話会議プロパティに移動して、[ **電話会議情報をメールで送信**] をクリックします。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="78bc2-209">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>

4. <span data-ttu-id="78bc2-210">電話会議の設定を使用してユーザーにメールを送信することもできます。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="78bc2-210">Click **Save**.</span></span>

    <span data-ttu-id="78bc2-211">これには、ユーザーの電話会議プロパティに移動して、[ **電話会議情報をメールで送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="78bc2-211">You can also send email to the user with the audio conferencing settings, by going to the user's audio conferencing properties and clicking **Send conference info via email**.</span></span>

    <span data-ttu-id="78bc2-212">この操作を行うと、会議 ID と電話会議の番号のみが含まれるメールが送信されますが、そのメールに PIN は含まれません。</span><span class="sxs-lookup"><span data-stu-id="78bc2-212">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span></span>

    <span data-ttu-id="78bc2-213">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span><span class="sxs-lookup"><span data-stu-id="78bc2-213">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>

## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a><span data-ttu-id="78bc2-214">参照してくださいし、オーディオ会議ブリッジに (既定値) をプライマリとセカンダリ (代替) の言語を設定します。</span><span class="sxs-lookup"><span data-stu-id="78bc2-214">See and set the primary (default) and secondary (alternate) languages on an audio conferencing bridge</span></span>


1. <span data-ttu-id="78bc2-215">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="78bc2-215">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="78bc2-216">Sign in to Office 365 with your work or school account.\*\*\*\* > \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="78bc2-216">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="78bc2-217">Go to the **Office 365 admin center\*\*\*\*\*\*\*\*Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="78bc2-217">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and then click **Microsoft bridge**.</span></span>

4. <span data-ttu-id="78bc2-218">リストから電話番号を選択し、操作ウィンドウで [ **言語を設定**] をクリックしてから、[ **言語を設定**] ページで [ **第 1 言語**] リストをクリックして、サポートされている言語の完全なリストを表示します。</span><span class="sxs-lookup"><span data-stu-id="78bc2-218">Select a phone number from the list, click **Set languages** in the Action pane, and then on the **Set languages** page, click the use the **Primary language** list to view the complete list of supported languages.</span></span>

    <span data-ttu-id="78bc2-p115">Microsoft を電話会議プロバイダーとして選ぶときに、サポートされる第 1 言語と第 2 言語を設定することもできます。発信者に対する言語の表示順は、リストで言語を選んだ順序になります。</span><span class="sxs-lookup"><span data-stu-id="78bc2-p115">You can also set the primary and secondary languages that are supported when you select Microsoft as the audio conferencing provider. The order that you select in the lists is the same order in which languages will be presented to callers.</span></span>

<span data-ttu-id="78bc2-221">You can also set the primary and secondary languages that are supported when you select Microsoft as the dial-in conferencing provider. The order that you select in the drop-downs will be the order of the languages that will be presented to the callers.[](set-auto-attendant-languages-for-audio-conferencing.md)</span><span class="sxs-lookup"><span data-stu-id="78bc2-221">See [Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing.md).</span></span>

## <a name="see-audio-conferencing-dial-in-numbers"></a><span data-ttu-id="78bc2-222">You can also set the primary and secondary languages that are supported when you select Microsoft as the dial-in conferencing provider.</span><span class="sxs-lookup"><span data-stu-id="78bc2-222">See audio conferencing dial-in numbers</span></span>

1. <span data-ttu-id="78bc2-223">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="78bc2-223">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="78bc2-224">「電話会議のダイヤルイン番号」をご覧ください\*\*\*\* > \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="78bc2-224">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="78bc2-p116">職場または学校のアカウントを使用して、Office 365 にサインインします。\*\*\*\*\*\*\*\* > \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="78bc2-p116">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge**. Here you can:</span></span>

  - <span data-ttu-id="78bc2-227">電話会議で使うために Office 365 によって設定された電話番号を表示する。</span><span class="sxs-lookup"><span data-stu-id="78bc2-227">View the phone numbers that are set by Office 365 to be used for Audio Conferencing.</span></span>

  - <span data-ttu-id="78bc2-228">場所を表示したり、電話会議の自動応答で使用する第 1 言語と第 2 言語を表示したりする。</span><span class="sxs-lookup"><span data-stu-id="78bc2-228">View the location, and the primary and secondary languages, that will be used by the Audio Conferencing auto attendant.</span></span>

  - <span data-ttu-id="78bc2-p117">ユーザーが電話会議で有効になっているときに、ユーザーに渡される既定の電話番号を選択します。ただし、電話会議ブリッジの既定の電話番号が変わっても、既存のユーザーの既定の電話番号は変わりません。</span><span class="sxs-lookup"><span data-stu-id="78bc2-p117">Select the default phone number that will be given to users when they are enabled for Audio Conferencing. However, if the default phone number of the audio conferencing bridge changes, the default phone number for existing users won't change.</span></span>

<span data-ttu-id="78bc2-231">You can select the dial-in conferencing default phone number that will be given to users when they are enabled for dial-in conferencing. However, if the default phone number of the dial-in conferencing bridge changes, the default phone number for existing users won't change.\*\*\*\* > \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="78bc2-231">You can go to **Audio conferencing** > **Users** and select the user's properties to change the default number for a user by choosing a new number from the list of numbers that are available in your organization.</span></span>

<span data-ttu-id="78bc2-232">You can select the dial-in conferencing default phone number that will be given to users when they are enabled for dial-in conferencing.[](see-a-list-of-audio-conferencing-numbers.md)</span><span class="sxs-lookup"><span data-stu-id="78bc2-232">See [See a list of Audio Conferencing numbers](see-a-list-of-audio-conferencing-numbers.md).</span></span>

## <a name="see-a-list-of-users-that-are-enabled"></a><span data-ttu-id="78bc2-233">However, if the default phone number of the dial-in conferencing bridge changes, the default phone number for existing users won't change.</span><span class="sxs-lookup"><span data-stu-id="78bc2-233">See a list of users that are enabled</span></span>

1. <span data-ttu-id="78bc2-234">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="78bc2-234">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="78bc2-235">有効になっているユーザーのリストを表示する\*\*\*\* > \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="78bc2-235">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="78bc2-236">職場または学校のアカウントを使用して、Office 365 にサインインします。\*\*\*\*\*\*\*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="78bc2-236">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**> and then **Users**.</span></span>

<span data-ttu-id="78bc2-237">Sign in to Office 365 with your work or school account.[](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md)</span><span class="sxs-lookup"><span data-stu-id="78bc2-237">See [See a list of users that are enabled for Audio Conferencing](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).</span></span>

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="78bc2-238">Go to the Office 365 admin centerSkype for Business.</span><span class="sxs-lookup"><span data-stu-id="78bc2-238">Want to know how to manage with Windows PowerShell?</span></span>

<span data-ttu-id="78bc2-p118">In the Skype for Business admin center, in the left navigation go to Dial-in conferencing> and then Dial-in users.</span><span class="sxs-lookup"><span data-stu-id="78bc2-p118">There are several settings that you can manage at the organization level using Windows PowerShell. This makes it easy to apply settings to all of your users.</span></span>

<span data-ttu-id="78bc2-241">Windows PowerShell を使用して組織レベルで管理できる複数の設定があります。[](https://go.microsoft.com/fwlink/?LinkId=627324)</span><span class="sxs-lookup"><span data-stu-id="78bc2-241">To get more help on each cmdlet, see [Skype for Business Online cmdlets](https://go.microsoft.com/fwlink/?LinkId=627324).</span></span>

<span data-ttu-id="78bc2-242">このため、簡単にこれらの設定をすべてのユーザーに適用できます。</span><span class="sxs-lookup"><span data-stu-id="78bc2-242">Here are the organization-level settings:</span></span>

- <span data-ttu-id="78bc2-243">**組織レベルの設定を以下に示します。**__</span><span class="sxs-lookup"><span data-stu-id="78bc2-243">**Setting entry/exit notifications** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableEntryExitNotifications $true|$false
  ```

- <span data-ttu-id="78bc2-244">**There are several settings that you can manage settings at the organization level using Windows PowerShell. This makes it easy to make these settings and have them apply to all of your users. Here are the organization level settings:**__</span><span class="sxs-lookup"><span data-stu-id="78bc2-244">**Setting name recording** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableNameRecording $true|false
  ```

- <span data-ttu-id="78bc2-245">**There are several settings that you can manage settings at the organization level using Windows PowerShell.**</span><span class="sxs-lookup"><span data-stu-id="78bc2-245">**Setting the PIN length** The default is 5.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -PinLength 7
  ```

- <span data-ttu-id="78bc2-246">**This makes it easy to make these settings and have them apply to all of your users.**__</span><span class="sxs-lookup"><span data-stu-id="78bc2-246">**Setting only dial-in meetings from a phone** The default _$false_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true|$false
  ```

- <span data-ttu-id="78bc2-247">**Here are the organization level settings:**__</span><span class="sxs-lookup"><span data-stu-id="78bc2-247">**Setting whether to send email to users** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

- <span data-ttu-id="78bc2-248">**Windows PowerShell の場合、ユーザーの管理と、ユーザーに許可する操作や許可しない操作の管理に使います。Windows PowerShell により、単一の管理ポイントを使って Office 365 を管理でき、複数の作業を実行する必要があるときに日常業務を合理化できます。Windows PowerShell を使い始めるには、次のトピックを参照してください。**__</span><span class="sxs-lookup"><span data-stu-id="78bc2-248">**Setting whether to send email from a different account** The default is  _$false_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromOverride $true|$false
  ```

- <span data-ttu-id="78bc2-249">**Windows PowerShell の場合、ユーザーの管理と、ユーザーに許可する操作や許可しない操作の管理に使います。**__</span><span class="sxs-lookup"><span data-stu-id="78bc2-249">**Setting the From address on email that is sent to users** The default is _$null_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromAddress
  ```

- <span data-ttu-id="78bc2-250">**Windows PowerShell により、単一の管理ポイントを使って Office 365 を管理でき、複数の作業を実行する必要があるときに日常業務を合理化できます。**__</span><span class="sxs-lookup"><span data-stu-id="78bc2-250">**Setting the display name for the email that is sent to users** The default is  _$null_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromDisplayName
  ```

 ## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="78bc2-251">Windows PowerShell を使い始めるには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="78bc2-251">Want to know more about Windows PowerShell</span></span>
- <span data-ttu-id="78bc2-p119">Windows PowerShell は、ユーザーと、ユーザーに許可されていることと許可されていないことを管理するためにあるということです。Windows PowerShell があれば、一元管理を使用して Office 365 を管理し、複数のタスクを抱えているときに、日常の仕事を簡素化することができます。Windows PowerShell を開始するには、これらのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="78bc2-p119">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="78bc2-255">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="78bc2-255">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

  - [<span data-ttu-id="78bc2-256">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="78bc2-256">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

- <span data-ttu-id="78bc2-p120">多くのユーザーの設定を同時に変更するときなどは、Office 365 管理センターのみを使用するよりも、Windows PowerShell の方に、速度、わかりやすさ、生産性の点で多くのメリットがあります。</span><span class="sxs-lookup"><span data-stu-id="78bc2-p120">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time. Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="78bc2-259">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time.</span><span class="sxs-lookup"><span data-stu-id="78bc2-259">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [<span data-ttu-id="78bc2-260">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="78bc2-260">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [<span data-ttu-id="78bc2-261">Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行</span><span class="sxs-lookup"><span data-stu-id="78bc2-261">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

    <span data-ttu-id="78bc2-p121">Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行[](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="78bc2-p121">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>

## <a name="related-topics"></a><span data-ttu-id="78bc2-264">このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「Skype for Business Online 用 Windows PowerShell モジュール」からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="78bc2-264">Related topics</span></span>

<span data-ttu-id="78bc2-265">See also</span><span class="sxs-lookup"><span data-stu-id="78bc2-265">[Manage the Audio Conferencing settings for a user](manage-the-audio-conferencing-settings-for-a-user.md)</span></span>


