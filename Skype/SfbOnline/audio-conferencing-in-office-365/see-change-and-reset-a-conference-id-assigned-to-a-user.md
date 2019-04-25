---
title: 参照してください、変更、およびオンライン ビジネスの Skype のユーザーに割り当てられている会議 ID をリセットします。
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 77d36233-2aab-4802-ba9c-e9a8885ea643
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
description: 'Skype of business オンライン のユーザーに会議 ID を割り当てる方法と、会議ID パラメーターのあるべき姿について学びます。 '
ms.openlocfilehash: eb7d42fa88c54b917e89eb97ce9f52bd03af4935
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32229333"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-skype-for-business-online"></a><span data-ttu-id="184e2-103">Skype of businessオンラインのユーザーに割り当てられている会議 ID を表示させリセットしてください。</span><span class="sxs-lookup"><span data-stu-id="184e2-103">View and reset a conference ID assigned to a user in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="184e2-104">マイクロソフト チーム内でのユーザー会議 Id の詳細については、 [マイクロソフト チーム 内のユーザーに割り当てられている会議 IDの表示とリセット](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="184e2-104">For information about user conference IDs in Microsoft Teams, see [View and reset a conference ID assigned to a user in Microsoft Teasms](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams).</span></span>

<span data-ttu-id="184e2-p101">A conferencing ID is automatically assigned to a Skype for Business user when they are set up for Audio Conferencing in Office 365 and use Microsoft as the audio conferencing provider. The conference ID assigned is sent in the meeting invite when the meeting is scheduled. Each meeting that a user schedules will get assigned a unique conference ID.</span><span class="sxs-lookup"><span data-stu-id="184e2-p101">A conferencing ID is automatically assigned to a Skype for Business user when they are set up for Audio Conferencing in Office 365 and use Microsoft as the audio conferencing provider. The conference ID assigned is sent in the meeting invite when the meeting is scheduled. Each meeting that a user schedules will get assigned a unique conference ID.</span></span>

<span data-ttu-id="184e2-p102">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID. You can use the **Skype for Business admin center** and Windows PowerShell to view, change, and reset their conference ID.</span><span class="sxs-lookup"><span data-stu-id="184e2-p102">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID. You can use the **Skype for Business admin center** and Windows PowerShell to view, change, and reset their conference ID.</span></span>

<span data-ttu-id="184e2-p103">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN. For more information about resetting a conference organizer's PIN, [go here](reset-a-conference-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="184e2-p103">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN. For more information about resetting a conference organizer's PIN, [go here](reset-a-conference-id-for-a-user.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="view-and-reset-conference-ids"></a><span data-ttu-id="184e2-112">会議 Idの表示と リセット</span><span class="sxs-lookup"><span data-stu-id="184e2-112">View and reset conference IDs</span></span>

### <a name="to-view-the-conference-id"></a><span data-ttu-id="184e2-113">会議 ID を表示するのには</span><span class="sxs-lookup"><span data-stu-id="184e2-113">To view the conference ID</span></span>

<span data-ttu-id="184e2-114">![デバイスのロゴ-30x30.png](../images/sfb-logo-30x30.png) **ビジネス管理センターの Skype を使用します。**</span><span class="sxs-lookup"><span data-stu-id="184e2-114">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

<span data-ttu-id="184e2-115">会議 ID を表示し、ユーザーに送信することができます。</span><span class="sxs-lookup"><span data-stu-id="184e2-115">You can view their conference ID and send it to users.</span></span>

1. <span data-ttu-id="184e2-116">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="184e2-116">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="184e2-117">Go to the **Office 365 admin center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="184e2-117">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="184e2-118">**Skype of business管理センター**の> **オーディオ会議** > **ユーザー**で会議IDを必要とするユーザー を選択します。</span><span class="sxs-lookup"><span data-stu-id="184e2-118">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, select the user who needs the conference ID.</span></span>

4. <span data-ttu-id="184e2-119">アクション ページで、**会議 ID** を確認します。</span><span class="sxs-lookup"><span data-stu-id="184e2-119">In the Action page, look under **Conference ID**.</span></span>

    > [!TIP]
    > <span data-ttu-id="184e2-120">[**ユーザー** ] ページで、ユーザーを選択した後に**電子メールを使用して会議情報を送信する**リンクをクリックして、会議 ID とオーディオの電話番号を含む電子メールでユーザーにすべての会議の情報を送信できます。</span><span class="sxs-lookup"><span data-stu-id="184e2-120">You can send all of the conferencing information to the user in an email that includes the conference ID and audio phone numbers by clicking the **Send conference info via email** link after you select the user on the **Users** page.</span></span>

<span data-ttu-id="184e2-121">**The conference ID and default dial-in conferencing phone number is included on the meeting invite but not the PIN.**</span><span class="sxs-lookup"><span data-stu-id="184e2-121">**Using Windows PowerShell**</span></span>

<span data-ttu-id="184e2-p104">You can use Windows PowerShell to view the conference ID for a user. To do so, run:</span><span class="sxs-lookup"><span data-stu-id="184e2-p104">You can use Windows PowerShell to view the conference ID for a user. To do so, run:</span></span>

  ```
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"
  ```

    See [Get-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 ) to learn more about the cmdlet.


### <a name="to-reset-the-conference-id"></a><span data-ttu-id="184e2-124">会議 ID をリセットするのには</span><span class="sxs-lookup"><span data-stu-id="184e2-124">To reset the conference ID</span></span>

<span data-ttu-id="184e2-125">例えば忘れてしまったなどの場合のために、ユーザーの会議 ID をリセットできます。</span><span class="sxs-lookup"><span data-stu-id="184e2-125">You can reset a conference ID for a user if, for example, they forget it.</span></span>

<span data-ttu-id="184e2-126">![デバイスのロゴ-30x30.png](../images/sfb-logo-30x30.png) **ビジネス管理センターの Skype を使用します。**</span><span class="sxs-lookup"><span data-stu-id="184e2-126">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="184e2-127">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="184e2-127">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="184e2-128">Go to the **Office 365 admin center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="184e2-128">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="184e2-129">**ビジネス管理センターの Skype**の> **電話会議** > **ユーザー**、操作ウィンドウの [**会議 ID**に**リセット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="184e2-129">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, in the Action pane under **Conference ID**, click **Reset**.</span></span>

4. <span data-ttu-id="184e2-p105">In the **Reset conference ID?** window, click **Yes**. A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="184e2-p105">In the **Reset conference ID?** window, click **Yes**. A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span>

<span data-ttu-id="184e2-132">**The conference ID and default dial-in conferencing phone number is included on the meeting invite but not the PIN.**</span><span class="sxs-lookup"><span data-stu-id="184e2-132">**Using Windows PowerShell**</span></span>

<span data-ttu-id="184e2-p106">You can reset the conference ID for a user by using the Windows PowerShell. To do this, run:</span><span class="sxs-lookup"><span data-stu-id="184e2-p106">You can reset the conference ID for a user by using the Windows PowerShell. To do this, run:</span></span>

  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble" -ResetConferenceID
  ```

## <a name="what-else-should-you-know"></a><span data-ttu-id="184e2-135">その他の情報</span><span class="sxs-lookup"><span data-stu-id="184e2-135">What else should you know?</span></span>

   > [!IMPORTANT]
   >  <span data-ttu-id="184e2-p107">After a new conference ID is created or one is reset, the old conference ID can't be used by callers. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. The users can use the Skype for Business Meeting Migration Tool to update their existing meetings. To see how to download, install, and run the tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](https://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span><span class="sxs-lookup"><span data-stu-id="184e2-p107">After a new conference ID is created or one is reset, the old conference ID can't be used by callers. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. The users can use the Skype for Business Meeting Migration Tool to update their existing meetings. To see how to download, install, and run the tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](https://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span></span>

- <span data-ttu-id="184e2-140">コマンドレットの詳細については、[設定 CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 )を参照してください。</span><span class="sxs-lookup"><span data-stu-id="184e2-140">See [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) to learn more about the cmdlet.</span></span>

- <span data-ttu-id="184e2-p108">The conference ID must meet the length in digits set on the audio conferencing bridge. You can't use alphabetic or special characters in conference IDs; only numbers can be used.</span><span class="sxs-lookup"><span data-stu-id="184e2-p108">The conference ID must meet the length in digits set on the audio conferencing bridge. You can't use alphabetic or special characters in conference IDs; only numbers can be used.</span></span>

- <span data-ttu-id="184e2-143">オーディオ会議のすべてのユーザーの会議 ID は、既定では、7 桁になります。桁数を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="184e2-143">The conference ID for all of your audio conferencing users will be 7 digits by default, and the number of digits can't be changed.</span></span>


## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="184e2-144">Windows PowerShell での管理方法について</span><span class="sxs-lookup"><span data-stu-id="184e2-144">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="184e2-p109">Windows PowerShell で行うのは、ユーザーを管理し、ユーザーに何を許可して何を禁止するかを管理することです。Windows PowerShell を利用すると、Office 365 と Skype for Business Online の管理を 1 か所で行うことができるので、複数のタスクを担当する管理者の日常業務を単純化できます。Windows PowerShell の使用を開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="184e2-p109">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="184e2-148">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="184e2-148">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [<span data-ttu-id="184e2-149">Office 365 PowerShell を使用する必要がある理由</span><span class="sxs-lookup"><span data-stu-id="184e2-149">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

- <span data-ttu-id="184e2-p110">Windows PowerShell には、ただ Office 365 管理センターを使用するだけではなく、速度、単純さ、生産性において多くの利点があります。次のトピックでこれらの利点について説明します。</span><span class="sxs-lookup"><span data-stu-id="184e2-p110">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="184e2-152">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="184e2-152">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [<span data-ttu-id="184e2-153">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="184e2-153">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [<span data-ttu-id="184e2-154">クイック リファレンス: Windows PowerShell を使用した一般的な Lync Online の管理タスクの実行</span><span class="sxs-lookup"><span data-stu-id="184e2-154">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="184e2-155">関連項目</span><span class="sxs-lookup"><span data-stu-id="184e2-155">Related topics</span></span>

[<span data-ttu-id="184e2-156">Office 365 での電話会議を試用または購入する</span><span class="sxs-lookup"><span data-stu-id="184e2-156">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

