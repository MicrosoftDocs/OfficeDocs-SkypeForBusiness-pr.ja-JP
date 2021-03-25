---
title: Skype for Business Online でユーザーに割り当てられた会議 ID を表示、変更、リセットする
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
ms.openlocfilehash: 79c83999fdf9a9736dfe1ee425337edf938d3375
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51110013"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-skype-for-business-online"></a><span data-ttu-id="22870-103">Skype of businessオンラインのユーザーに割り当てられている会議 ID を表示させリセットしてください。</span><span class="sxs-lookup"><span data-stu-id="22870-103">View and reset a conference ID assigned to a user in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="22870-104">Microsoft Teams でのユーザー会議 ID の詳細については [、「Microsoft Teams](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams)でユーザーに割り当てられた会議 ID を表示およびリセットする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="22870-104">For information about user conference IDs in Microsoft Teams, see [View and reset a conference ID assigned to a user in Microsoft Teams](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams).</span></span>

<span data-ttu-id="22870-105">会議 ID は、Microsoft 365 または Office 365 で電話会議用にセットアップされ、Microsoft を電話会議プロバイダーとして使用すると、自動的に Skype for Business ユーザーに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="22870-105">A conferencing ID is automatically assigned to a Skype for Business user when they are set up for Audio Conferencing in Microsoft 365 or Office 365 and use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="22870-106">割り当てられた会議 ID は、会議のスケジュール時に会議出席招待で送信されます。</span><span class="sxs-lookup"><span data-stu-id="22870-106">The conference ID assigned is sent in the meeting invite when the meeting is scheduled.</span></span> <span data-ttu-id="22870-107">ユーザーがスケジュール設定した各会議には、一意の会議通話 ID が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="22870-107">Each meeting that a user schedules will get assigned a unique conference ID.</span></span>

<span data-ttu-id="22870-108">会議 ID は自動的に作成され、ユーザーに割り当てられますが、ユーザーがこれを使いたくないときに特定の番号に設定したい場合や、ユーザーが会議 ID を思い出したり紛失したりできない場合があります。</span><span class="sxs-lookup"><span data-stu-id="22870-108">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="22870-109">Skype for **Business** 管理センターを使用して、Windows PowerShell ID の表示、変更、リセットを行えます。</span><span class="sxs-lookup"><span data-stu-id="22870-109">You can use the **Skype for Business admin center** and Windows PowerShell to view, change, and reset their conference ID.</span></span>

<span data-ttu-id="22870-110">ユーザーに会議 ID と既定の電話会議の電話番号が含む電子メールが送信されるか、または会議 ID をリセットすると、PINではない 会議 ID を含む別の電子メールが送信されます。</span><span class="sxs-lookup"><span data-stu-id="22870-110">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN.</span></span> <span data-ttu-id="22870-111">会議の開催者のPINをリセットするの詳細については、 [ここ](reset-a-conference-id-for-a-user.md)をクリックします。</span><span class="sxs-lookup"><span data-stu-id="22870-111">For more information about resetting a conference organizer's PIN, [go here](reset-a-conference-id-for-a-user.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="view-and-reset-conference-ids"></a><span data-ttu-id="22870-112">会議 Idの表示と リセット</span><span class="sxs-lookup"><span data-stu-id="22870-112">View and reset conference IDs</span></span>

### <a name="to-view-the-conference-id"></a><span data-ttu-id="22870-113">会議 ID を表示するには</span><span class="sxs-lookup"><span data-stu-id="22870-113">To view the conference ID</span></span>

<span data-ttu-id="22870-114">![Skype for Business のロゴを表示したアイコン](../images/sfb-logo-30x30.png) **Skype for Business 管理センターの使用**</span><span class="sxs-lookup"><span data-stu-id="22870-114">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

<span data-ttu-id="22870-115">会議 ID を表示し、ユーザーに送信することができます。</span><span class="sxs-lookup"><span data-stu-id="22870-115">You can view their conference ID and send it to users.</span></span>

1. <span data-ttu-id="22870-116">仕事用または学校用のアカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="22870-116">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="22870-117">Skype for Business の管理> **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="22870-117">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="22870-118">**Skype of business管理センター** の> **オーディオ会議** > **ユーザー** で会議IDを必要とするユーザー を選択します。</span><span class="sxs-lookup"><span data-stu-id="22870-118">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, select the user who needs the conference ID.</span></span>

4. <span data-ttu-id="22870-119">アクション ページで、**会議 ID** を確認します。</span><span class="sxs-lookup"><span data-stu-id="22870-119">In the Action page, look under **Conference ID**.</span></span>

    > [!TIP]
    > <span data-ttu-id="22870-120">[ユーザー] ページでユーザーを選択した後、[電話会議情報をメールで送信] リンクをクリックすると、会議ID と音声電話番号を含むメールで、すべての会議情報をユーザーに送信できます。</span><span class="sxs-lookup"><span data-stu-id="22870-120">You can send all of the conferencing information to the user in an email that includes the conference ID and audio phone numbers by clicking the **Send conference info via email** link after you select the user on the **Users** page.</span></span>

<span data-ttu-id="22870-121">**Windows PowerShell を使用する**</span><span class="sxs-lookup"><span data-stu-id="22870-121">**Using Windows PowerShell**</span></span>

<span data-ttu-id="22870-122">ユーザーの会議 ID を表示するのにWindows PowerShell を使用できます。</span><span class="sxs-lookup"><span data-stu-id="22870-122">You can use Windows PowerShell to view the conference ID for a user.</span></span> <span data-ttu-id="22870-123">これを行うには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="22870-123">To do so, run:</span></span>

  ```powershell
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"
  ```

<span data-ttu-id="22870-124">コマンドレット [の詳細については、Get-CsOnlineDialInConferencingUser](/powershell/module/skype/Get-CsOnlineDialInConferencingUser) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="22870-124">See [Get-CsOnlineDialInConferencingUser](/powershell/module/skype/Get-CsOnlineDialInConferencingUser) to learn more about the cmdlet.</span></span>


### <a name="to-reset-the-conference-id"></a><span data-ttu-id="22870-125">会議 ID をリセットするには</span><span class="sxs-lookup"><span data-stu-id="22870-125">To reset the conference ID</span></span>

<span data-ttu-id="22870-126">例えば忘れてしまったなどの場合のために、ユーザーの会議 ID をリセットできます。</span><span class="sxs-lookup"><span data-stu-id="22870-126">You can reset a conference ID for a user if, for example, they forget it.</span></span>

<span data-ttu-id="22870-127">![Skype for Business のロゴを表示したアイコン](../images/sfb-logo-30x30.png) **Skype for Business 管理センターの使用**</span><span class="sxs-lookup"><span data-stu-id="22870-127">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="22870-128">仕事用または学校用のアカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="22870-128">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="22870-129">Skype for Business の管理センター> **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="22870-129">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="22870-130">Skype **for Business 管理センター** の電話会議ユーザーの [電話会議 ID] の [操作] ウィンドウで、[リセット] >    >  をクリック **します**。 </span><span class="sxs-lookup"><span data-stu-id="22870-130">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, in the Action pane under **Conference ID**, click **Reset**.</span></span>

4. <span data-ttu-id="22870-131">[会議 **ID のリセット] ウィンドウで、[** はい] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="22870-131">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="22870-132">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="22870-132">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span>

<span data-ttu-id="22870-133">**Windows PowerShell を使用する**</span><span class="sxs-lookup"><span data-stu-id="22870-133">**Using Windows PowerShell**</span></span>

<span data-ttu-id="22870-134">ユーザーの会議 ID をリセットするには、Windows PowerShell を使用します。</span><span class="sxs-lookup"><span data-stu-id="22870-134">You can reset the conference ID for a user by using the Windows PowerShell.</span></span> <span data-ttu-id="22870-135">これを行う場合は、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="22870-135">To do this, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble" -ResetConferenceID
  ```

## <a name="what-else-should-you-know"></a><span data-ttu-id="22870-136">その他の情報</span><span class="sxs-lookup"><span data-stu-id="22870-136">What else should you know?</span></span>

   > [!IMPORTANT]
   >  <span data-ttu-id="22870-137">新しい会議 ID が作成またはリセットされると、古い会議 ID を発信者が使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="22870-137">After a new conference ID is created or one is reset, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="22870-138">既存の会議の出席依頼のスケジュールを変更して、新しい会議 ID を出席依頼に追加するように、ユーザーに通知してください。</span><span class="sxs-lookup"><span data-stu-id="22870-138">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="22870-139">ユーザーは Skype for Business 会議移行ツールを使用して、既存の会議を更新できます。</span><span class="sxs-lookup"><span data-stu-id="22870-139">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="22870-140">このツールをダウンロード、インストール、実行する方法については [、「Skype for Business](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)および Lync の会議更新ツール、Skype for Business Online、会議移行ツール [(64](https://go.microsoft.com/fwlink/?LinkID=626047)ビット)、Skype for Business Online、会議移行ツール  [(32 ビット)」](https://www.microsoft.com/download/details.aspx?id=54079)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="22870-140">To see how to download, install, and run the tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](https://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/download/details.aspx?id=54079).</span></span>

- <span data-ttu-id="22870-141">コマンドレット [の詳細については、「Set-CsOnlineDialInConferencingUser」](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="22870-141">See [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) to learn more about the cmdlet.</span></span>

- <span data-ttu-id="22870-142">会議 ID は、オーディオ会議ブリッジに設定された桁の長さを満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="22870-142">The conference ID must meet the length in digits set on the audio conferencing bridge.</span></span> <span data-ttu-id="22870-143">会議 Id には、アルファベットまたは特殊文字を使うことはできません。数値のみが使用できます。</span><span class="sxs-lookup"><span data-stu-id="22870-143">You can't use alphabetic or special characters in conference IDs; only numbers can be used.</span></span>

- <span data-ttu-id="22870-144">すべての電話会議ユーザーの会議 ID は既定で 9 桁の数字で、数字の数は変更できません。</span><span class="sxs-lookup"><span data-stu-id="22870-144">The conference ID for all of your audio conferencing users will be 9 digits by default, and the number of digits can't be changed.</span></span>


## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="22870-145">Windows PowerShell での管理方法について</span><span class="sxs-lookup"><span data-stu-id="22870-145">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="22870-146">Windows PowerShell で行うのは、ユーザーを管理し、ユーザーに何を許可して何を禁止するかを管理することです。</span><span class="sxs-lookup"><span data-stu-id="22870-146">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="22870-147">Windows PowerShell を使用すると、単一の管理ポイントを使用して Microsoft 365 または Office 365 と Skype for Business Online を管理できます。複数のタスクを実行する必要がある場合に毎日の作業を簡略化できます。</span><span class="sxs-lookup"><span data-stu-id="22870-147">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="22870-148">Windows PowerShell の使用を開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="22870-148">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="22870-149">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="22870-149">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [<span data-ttu-id="22870-150">Microsoft 365 または Office 365 PowerShell を使用する必要がある理由</span><span class="sxs-lookup"><span data-stu-id="22870-150">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- <span data-ttu-id="22870-151">Windows PowerShellは、多くのユーザーに対して同時に設定変更を行う場合など、Microsoft 365 管理センターを使用する場合に限って、速度、シンプルさ、生産性の点で多くの利点があります。</span><span class="sxs-lookup"><span data-stu-id="22870-151">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="22870-152">次のトピックでこれらの利点について説明します。</span><span class="sxs-lookup"><span data-stu-id="22870-152">Learn about these advantages in the following topics:</span></span>

  - <span data-ttu-id="22870-153">[Microsoft 365 または Office 365 を管理するための最適Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="22870-153">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>

  - [<span data-ttu-id="22870-154">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="22870-154">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [<span data-ttu-id="22870-155">Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行</span><span class="sxs-lookup"><span data-stu-id="22870-155">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

## <a name="related-topics"></a><span data-ttu-id="22870-156">関連項目</span><span class="sxs-lookup"><span data-stu-id="22870-156">Related topics</span></span>

[<span data-ttu-id="22870-157">Microsoft 365 または Office 365 で電話会議を試用または購入する</span><span class="sxs-lookup"><span data-stu-id="22870-157">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)