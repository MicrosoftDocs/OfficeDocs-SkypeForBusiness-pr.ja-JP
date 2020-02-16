---
title: Skype for Business Online のユーザーに割り当てられている会議 ID を表示、変更、リセットする
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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Skype of business オンライン のユーザーに会議 ID を割り当てる方法と、会議ID パラメーターのあるべき姿について学びます。 '
ms.openlocfilehash: 8bec76e25df092beb18725467c3041de3c1d7745
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42010990"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-skype-for-business-online"></a><span data-ttu-id="2eabb-103">Skype of businessオンラインのユーザーに割り当てられている会議 ID を表示させリセットしてください。</span><span class="sxs-lookup"><span data-stu-id="2eabb-103">View and reset a conference ID assigned to a user in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="2eabb-104">Microsoft Teams のユーザー会議 id の詳細については、「 [Microsoft teams でユーザーに割り当てられている会議 ID を表示およびリセット](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2eabb-104">For information about user conference IDs in Microsoft Teams, see [View and reset a conference ID assigned to a user in Microsoft Teams](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams).</span></span>

<span data-ttu-id="2eabb-105">会議 ID は、Office 365 での音声会議用に設定し、Microsoft をオーディオ会議プロバイダーとしてを使用する場合に、Skype of business の ユーザーに自動的に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="2eabb-105">A conferencing ID is automatically assigned to a Skype for Business user when they are set up for Audio Conferencing in Office 365 and use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="2eabb-106">会議がスケジュールされると、割り当てられた会議 ID が会議の出席依頼に送信されます。</span><span class="sxs-lookup"><span data-stu-id="2eabb-106">The conference ID assigned is sent in the meeting invite when the meeting is scheduled.</span></span> <span data-ttu-id="2eabb-107">ユーザーがスケジュール設定した各会議には、一意の会議通話 ID が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="2eabb-107">Each meeting that a user schedules will get assigned a unique conference ID.</span></span>

<span data-ttu-id="2eabb-108">会議 ID は自動的に作成され、ユーザーに割り当てられますが、ユーザーがこの機能を使用したくない場合や、特定の番号に設定したい場合、またはユーザーが自分の会議 ID を忘れてしまったり、紛失したりする場合もあります。</span><span class="sxs-lookup"><span data-stu-id="2eabb-108">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="2eabb-109">**Skype For business 管理センター**と Windows PowerShell を使用して、会議 ID を表示、変更、リセットすることができます。</span><span class="sxs-lookup"><span data-stu-id="2eabb-109">You can use the **Skype for Business admin center** and Windows PowerShell to view, change, and reset their conference ID.</span></span>

<span data-ttu-id="2eabb-110">ユーザーに会議 ID と既定の電話会議の電話番号が含む電子メールが送信されるか、または会議 ID をリセットすると、PINではない 会議 ID を含む別の電子メールが送信されます。</span><span class="sxs-lookup"><span data-stu-id="2eabb-110">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN.</span></span> <span data-ttu-id="2eabb-111">会議の開催者のPINをリセットするの詳細については、 [ここ](reset-a-conference-id-for-a-user.md)をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2eabb-111">For more information about resetting a conference organizer's PIN, [go here](reset-a-conference-id-for-a-user.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="view-and-reset-conference-ids"></a><span data-ttu-id="2eabb-112">会議 Idの表示と リセット</span><span class="sxs-lookup"><span data-stu-id="2eabb-112">View and reset conference IDs</span></span>

### <a name="to-view-the-conference-id"></a><span data-ttu-id="2eabb-113">会議 ID を表示するには</span><span class="sxs-lookup"><span data-stu-id="2eabb-113">To view the conference ID</span></span>

<span data-ttu-id="2eabb-114">![Skype for Business のロゴを表示したアイコン](../images/sfb-logo-30x30.png) **Skype for Business 管理センターの使用**</span><span class="sxs-lookup"><span data-stu-id="2eabb-114">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

<span data-ttu-id="2eabb-115">会議 ID を表示し、ユーザーに送信することができます。</span><span class="sxs-lookup"><span data-stu-id="2eabb-115">You can view their conference ID and send it to users.</span></span>

1. <span data-ttu-id="2eabb-116">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="2eabb-116">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="2eabb-117">**Skype For business**> 管理センターに移動します。</span><span class="sxs-lookup"><span data-stu-id="2eabb-117">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="2eabb-118">**Skype of business管理センター**の> **オーディオ会議** > **ユーザー**で会議IDを必要とするユーザー を選択します。</span><span class="sxs-lookup"><span data-stu-id="2eabb-118">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, select the user who needs the conference ID.</span></span>

4. <span data-ttu-id="2eabb-119">アクション ページで、**会議 ID** を確認します。</span><span class="sxs-lookup"><span data-stu-id="2eabb-119">In the Action page, look under **Conference ID**.</span></span>

    > [!TIP]
    > <span data-ttu-id="2eabb-120">[**ユーザー** ] ページでユーザーを選択した後、[電話会議**情報をメールで送信**] リンクをクリックすると、会議 ID と電話番号を含むメールのユーザーにすべての会議情報を送信できます。</span><span class="sxs-lookup"><span data-stu-id="2eabb-120">You can send all of the conferencing information to the user in an email that includes the conference ID and audio phone numbers by clicking the **Send conference info via email** link after you select the user on the **Users** page.</span></span>

<span data-ttu-id="2eabb-121">**Windows PowerShell を使用する**</span><span class="sxs-lookup"><span data-stu-id="2eabb-121">**Using Windows PowerShell**</span></span>

<span data-ttu-id="2eabb-122">ユーザーの会議 ID を表示するのにWindows PowerShell を使用できます。</span><span class="sxs-lookup"><span data-stu-id="2eabb-122">You can use Windows PowerShell to view the conference ID for a user.</span></span> <span data-ttu-id="2eabb-123">そのためには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="2eabb-123">To do so, run:</span></span>

  ```powershell
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"
  ```

<span data-ttu-id="2eabb-124">コマンドレットの詳細については、 [get-csonlinedialinconferencinguser](https://go.microsoft.com/fwlink/?LinkId=617693 )を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2eabb-124">See [Get-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 ) to learn more about the cmdlet.</span></span>


### <a name="to-reset-the-conference-id"></a><span data-ttu-id="2eabb-125">会議 ID をリセットするには</span><span class="sxs-lookup"><span data-stu-id="2eabb-125">To reset the conference ID</span></span>

<span data-ttu-id="2eabb-126">例えば忘れてしまったなどの場合のために、ユーザーの会議 ID をリセットできます。</span><span class="sxs-lookup"><span data-stu-id="2eabb-126">You can reset a conference ID for a user if, for example, they forget it.</span></span>

<span data-ttu-id="2eabb-127">![Skype for Business のロゴを表示したアイコン](../images/sfb-logo-30x30.png) **Skype for Business 管理センターの使用**</span><span class="sxs-lookup"><span data-stu-id="2eabb-127">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="2eabb-128">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="2eabb-128">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="2eabb-129">**Skype For business**> 管理センターに移動します。</span><span class="sxs-lookup"><span data-stu-id="2eabb-129">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="2eabb-130">**Skype for business 管理センター**> **電話会議** > **ユーザー**で、操作ウィンドウの [**会議 ID**] で [**リセット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2eabb-130">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, in the Action pane under **Conference ID**, click **Reset**.</span></span>

4. <span data-ttu-id="2eabb-131">[**会議 ID をリセットしますか?** ] ウィンドウで、[**はい**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2eabb-131">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="2eabb-132">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="2eabb-132">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span>

<span data-ttu-id="2eabb-133">**Windows PowerShell を使用する**</span><span class="sxs-lookup"><span data-stu-id="2eabb-133">**Using Windows PowerShell**</span></span>

<span data-ttu-id="2eabb-134">ユーザーの会議 ID をリセットするには、Windows PowerShell を使用します。</span><span class="sxs-lookup"><span data-stu-id="2eabb-134">You can reset the conference ID for a user by using the Windows PowerShell.</span></span> <span data-ttu-id="2eabb-135">これを行う場合は、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="2eabb-135">To do this, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble" -ResetConferenceID
  ```

## <a name="what-else-should-you-know"></a><span data-ttu-id="2eabb-136">その他の情報</span><span class="sxs-lookup"><span data-stu-id="2eabb-136">What else should you know?</span></span>

   > [!IMPORTANT]
   >  <span data-ttu-id="2eabb-137">新しい会議 ID を作成するか、またはリセットした後は、古い会議 ID を発信者が使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="2eabb-137">After a new conference ID is created or one is reset, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="2eabb-138">既存の会議の出席依頼のスケジュールを変更して、新しい会議 ID を出席依頼に追加するように、ユーザーに通知してください。</span><span class="sxs-lookup"><span data-stu-id="2eabb-138">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="2eabb-139">ユーザーは Skype for Business 会議移行ツールを使用して、既存の会議を更新することができます。</span><span class="sxs-lookup"><span data-stu-id="2eabb-139">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="2eabb-140">このツールのダウンロード、インストール、実行の方法については、「 [skype For business および Lync の会議更新ツール](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)」、「 [Skype for Business Online、会議移行ツール (64 ビット)](https://go.microsoft.com/fwlink/?LinkID=626047)」、「 [Skype For Business online、会議移行ツール (32 ビット)](https://www.microsoft.com/download/details.aspx?id=54079)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2eabb-140">To see how to download, install, and run the tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](https://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/download/details.aspx?id=54079).</span></span>

- <span data-ttu-id="2eabb-141">コマンドレットの詳細については、「 [Set-get-csonlinedialinconferencinguser](https://go.microsoft.com/fwlink/?LinkId=617688 ) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2eabb-141">See [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) to learn more about the cmdlet.</span></span>

- <span data-ttu-id="2eabb-142">会議 ID は、オーディオ会議ブリッジに設定された桁の長さを満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="2eabb-142">The conference ID must meet the length in digits set on the audio conferencing bridge.</span></span> <span data-ttu-id="2eabb-143">会議 Id には、アルファベットまたは特殊文字を使うことはできません。数値のみが使用できます。</span><span class="sxs-lookup"><span data-stu-id="2eabb-143">You can't use alphabetic or special characters in conference IDs; only numbers can be used.</span></span>

- <span data-ttu-id="2eabb-144">オーディオ会議のすべてのユーザーの会議 ID は、既定では、7 桁になります。桁数を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="2eabb-144">The conference ID for all of your audio conferencing users will be 7 digits by default, and the number of digits can't be changed.</span></span>


## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="2eabb-145">Windows PowerShell での管理方法について</span><span class="sxs-lookup"><span data-stu-id="2eabb-145">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="2eabb-p109">Windows PowerShell で行うのは、ユーザーを管理し、ユーザーに何を許可して何を禁止するかを管理することです。Windows PowerShell を利用すると、Office 365 と Skype for Business Online の管理を 1 か所で行うことができるので、複数のタスクを担当する管理者の日常業務を単純化できます。Windows PowerShell の使用を開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2eabb-p109">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="2eabb-149">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="2eabb-149">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [<span data-ttu-id="2eabb-150">Office 365 PowerShell を使用する必要がある理由</span><span class="sxs-lookup"><span data-stu-id="2eabb-150">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

- <span data-ttu-id="2eabb-151">Windows PowerShell には、多くのユーザーについて同時に設定を変更する場合など、Microsoft 365 管理センターを使用する場合にのみ、速度、シンプルさ、生産性を高めることができます。</span><span class="sxs-lookup"><span data-stu-id="2eabb-151">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="2eabb-152">次のトピックでこれらの利点について説明します。</span><span class="sxs-lookup"><span data-stu-id="2eabb-152">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="2eabb-153">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="2eabb-153">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [<span data-ttu-id="2eabb-154">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="2eabb-154">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [<span data-ttu-id="2eabb-155">Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行</span><span class="sxs-lookup"><span data-stu-id="2eabb-155">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="2eabb-156">関連項目</span><span class="sxs-lookup"><span data-stu-id="2eabb-156">Related topics</span></span>

[<span data-ttu-id="2eabb-157">Office 365 での電話会議を試用または購入する</span><span class="sxs-lookup"><span data-stu-id="2eabb-157">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

