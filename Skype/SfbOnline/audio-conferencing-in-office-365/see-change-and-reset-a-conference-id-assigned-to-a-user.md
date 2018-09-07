---
title: Skype for Business Online でユーザーに割り当てられた会議 ID を参照、変更、リセットする
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
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Skype of business オンライン のユーザーに会議 ID を割り当てる方法と、会議ID パラメーターのあるべき姿について学びます。 '
ms.openlocfilehash: d47e188220f66e320289384c4fbe421328d8eca3
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23850187"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-skype-for-business-online"></a><span data-ttu-id="981bd-103">Skype of businessオンラインのユーザーに割り当てられている会議 ID を表示させリセットしてください。</span><span class="sxs-lookup"><span data-stu-id="981bd-103">View and reset a conference ID assigned to a user in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="981bd-104">マイクロソフト チーム内でのユーザー会議 Id の詳細については、 [マイクロソフト チーム 内のユーザーに割り当てられている会議 IDの表示とリセット](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="981bd-104">For information about user conference IDs in Microsoft Teams, see [View and reset a conference ID assigned to a user in Microsoft Teasms](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams).</span></span>

<span data-ttu-id="981bd-105">会議 ID は、Office 365 での音声会議用に設定し、Microsoft をオーディオ会議プロバイダーとしてを使用する場合に、Skype of business の ユーザーに自動的に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="981bd-105">A conferencing ID is automatically assigned to a Skype for Business user when they are set up for Audio Conferencing in Office 365 and use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="981bd-106">割り当てられている会議 ID は、会議がスケジュールされている場合、会議出席依頼で送信されます。</span><span class="sxs-lookup"><span data-stu-id="981bd-106">The conference ID assigned can be either static or dynamic and is sent in the meeting invite when the meeting is scheduled.</span></span> <span data-ttu-id="981bd-107">ユーザーが計画する会議ごとに、固有の会議 ID が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="981bd-107">When dynamic conference IDs are used, each meeting that a user schedules will get assigned a unique conference ID.</span></span>

<span data-ttu-id="981bd-108">会議 ID は自動的に作成されてユーザーに割り当てられますが、ユーザーがこの ID を使用したくない場合や、特定の番号に設定したい場合、またはユーザーが会議 ID を覚えていなかったり、失くしてしまう場合もあります。</span><span class="sxs-lookup"><span data-stu-id="981bd-108">Although a static conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="981bd-109">\*\* Skype for Business 管理センター \*\*と Windows PowerShell を使用して、ユーザーの会議 ID を閲覧、変更、リセットすることができます。</span><span class="sxs-lookup"><span data-stu-id="981bd-109">You can use the Skype for Business admin center and Windows PowerShell to view, change, and reset their conference ID.</span></span>

<span data-ttu-id="981bd-110">ユーザーに会議 ID と既定の電話会議の電話番号が含む電子メールが送信されるか、または会議 ID をリセットすると、PINではない 会議 ID を含む別の電子メールが送信されます。</span><span class="sxs-lookup"><span data-stu-id="981bd-110">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN.</span></span> <span data-ttu-id="981bd-111">会議の開催者のPINをリセットするの詳細については、 [ここ](reset-a-conference-id-for-a-user.md)をクリックします。</span><span class="sxs-lookup"><span data-stu-id="981bd-111">For more information about resetting a conference organizer's PIN, [go here](reset-a-conference-id-for-a-user.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="view-and-reset-conference-ids"></a><span data-ttu-id="981bd-112">会議 Idの表示と リセット</span><span class="sxs-lookup"><span data-stu-id="981bd-112">View and reset conference IDs</span></span>

### <a name="to-view-the-conference-id"></a><span data-ttu-id="981bd-113">会議 ID を表示するには</span><span class="sxs-lookup"><span data-stu-id="981bd-113">To reset the meeting conference ID</span></span>

<span data-ttu-id="981bd-114">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Skype for Business 管理センターを使用する**</span><span class="sxs-lookup"><span data-stu-id="981bd-114">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

<span data-ttu-id="981bd-115">会議 ID を表示し、ユーザーに送信することができます。</span><span class="sxs-lookup"><span data-stu-id="981bd-115">You can view their conference ID and send it to users.</span></span>

1. <span data-ttu-id="981bd-116">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="981bd-116">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="981bd-117">\*\*Office 365 管理センター \*\* > **Skype for Business** に移動します。</span><span class="sxs-lookup"><span data-stu-id="981bd-117">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="981bd-118">**Skype of business管理センター**の> **オーディオ会議** > **ユーザー**で会議IDを必要とするユーザー を選択します。</span><span class="sxs-lookup"><span data-stu-id="981bd-118">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, select the user who needs the conference ID.</span></span>

4. <span data-ttu-id="981bd-119">アクション ページで、**会議 ID** を確認します。</span><span class="sxs-lookup"><span data-stu-id="981bd-119">In the Action page, look under **Conference ID**.</span></span>

    > [!TIP]
    > <span data-ttu-id="981bd-120">**ユーザー** ページで、ユーザーを選択した後に **電子メールを使用して会議情報を送信する**をクリックして、会議 ID とオーディオの電話番号を含む電子メールでユーザーにすべての会議の情報を送信できます。</span><span class="sxs-lookup"><span data-stu-id="981bd-120">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking the **Send conference info via email**. It doesn't send the PIN.</span></span>

<span data-ttu-id="981bd-121">**Windows PowerShell の使用**</span><span class="sxs-lookup"><span data-stu-id="981bd-121">**Using Windows PowerShell**</span></span>

<span data-ttu-id="981bd-122">ユーザーの会議 ID を表示するのにWindows PowerShell を使用できます。</span><span class="sxs-lookup"><span data-stu-id="981bd-122">You can use Windows PowerShell to view the conference ID for a user.</span></span> <span data-ttu-id="981bd-123">これを行うには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="981bd-123">To do so:</span></span>

  ```
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"
  ```

    See [Get-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 ) to learn more about the cmdlet.


### <a name="to-reset-the-conference-id"></a><span data-ttu-id="981bd-124">会議 ID をリセットするには</span><span class="sxs-lookup"><span data-stu-id="981bd-124">To reset the meeting conference ID</span></span>

<span data-ttu-id="981bd-125">例えば忘れてしまったなどの場合のために、ユーザーの会議 ID をリセットできます。</span><span class="sxs-lookup"><span data-stu-id="981bd-125">You can reset a conference ID for a user if, for example, they forget it.</span></span>

<span data-ttu-id="981bd-126">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Skype for Business 管理センターを使用する**</span><span class="sxs-lookup"><span data-stu-id="981bd-126">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="981bd-127">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="981bd-127">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="981bd-128">\*\*Office 365 管理センター \*\* > **Skype for Business** に移動します。</span><span class="sxs-lookup"><span data-stu-id="981bd-128">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="981bd-129">**Skype for Business 管理センター**の> **電話会議** > **ユーザー**、操作ウィンドウの下の **会議 ID** で**リセット**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="981bd-129">In the **Skype for Business admin center**> **Dial-in conferencing**, in the Action page under **Conference ID** click **Reset**.</span></span>

4. <span data-ttu-id="981bd-130">**会議 ID をリセットしますか?** ウインドウで、 **はい** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="981bd-130">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="981bd-131">会議 ID が自動的に生成されて、ユーザーに新しい会議 ID を含む電子メールが送信されます。</span><span class="sxs-lookup"><span data-stu-id="981bd-131">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span>

<span data-ttu-id="981bd-132">**Windows PowerShell の使用**</span><span class="sxs-lookup"><span data-stu-id="981bd-132">**Using Windows PowerShell**</span></span>

<span data-ttu-id="981bd-133">ユーザーの会議 ID をリセットするには、Windows PowerShell を使用します。</span><span class="sxs-lookup"><span data-stu-id="981bd-133">You can reset the conference ID for a user by using the Windows PowerShell.</span></span> <span data-ttu-id="981bd-134">これを行う場合は、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="981bd-134">To do this, run:</span></span>

  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ResetConferenceID 8271964
  ```

## <a name="what-else-should-you-know"></a><span data-ttu-id="981bd-135">その他の情報は必要ですか？</span><span class="sxs-lookup"><span data-stu-id="981bd-135">What else should you know?</span></span>

   > [!IMPORTANT]
   >  <span data-ttu-id="981bd-136">新しい会議 ID が作成された後、あるいはリセット後は、呼び出し元は古い会議 ID を使用できません。</span><span class="sxs-lookup"><span data-stu-id="981bd-136">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="981bd-137">新しい会議 ID が招待状に追加されたことを確認するには、既存の会議招待を再スケジュールするのにユーザーに通知する必要があります。</span><span class="sxs-lookup"><span data-stu-id="981bd-137">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="981bd-138">ユーザーは、Skype for Business 会議移行ツールを使用して、既存の会議を更新できます。</span><span class="sxs-lookup"><span data-stu-id="981bd-138">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="981bd-139">ツールをどのようにダウンロードし、インストールして実行するかについては、[Skype for Business と Lync 用の会議更新ツール](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4),、[Skype for Business Online、会議移行ツール (64 ビット) ](https://go.microsoft.com/fwlink/?LinkID=626047)および [Skype for Business Online、会議移行ツール (32 ビット)](https://www.microsoft.com/en-us/download/details.aspx?id=54079) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="981bd-139">To see how to download, install, and run the Skype for Business Meeting Update Tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](https://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span></span>

- <span data-ttu-id="981bd-140">コマンドレットの詳細については、[Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="981bd-140">See [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) to learn more about the cmdlet.</span></span>

- <span data-ttu-id="981bd-141">会議 ID は、オーディオ会議ブリッジに設定された桁の長さを満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="981bd-141">The conference ID must meet the length in digits set on the audio conferencing bridge.</span></span> <span data-ttu-id="981bd-142">会議 Id には、アルファベットまたは特殊文字を使うことはできません。数値のみが使用できます。</span><span class="sxs-lookup"><span data-stu-id="981bd-142">You can't use alphabetic or special characters in conference IDs; only numbers can be used.</span></span>

- <span data-ttu-id="981bd-143">オーディオ会議のすべてのユーザーの会議 ID は、既定では、7 桁になります。桁数を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="981bd-143">The conference ID for all of your audio conferencing users will be 7 digits by default, and the number of digits can't be changed.</span></span>


## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="981bd-144">Windows PowerShell を管理する方法を知る必要がありますか？</span><span class="sxs-lookup"><span data-stu-id="981bd-144">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="981bd-p109">Windows PowerShell で行うのは、ユーザーを管理し、ユーザーに何を許可して何を禁止するかを管理することです。Windows PowerShell を利用すると、Office 365 と Skype for Business Online の管理を 1 か所で行うことができるので、複数のタスクを担当する管理者の日常業務を単純化できます。Windows PowerShell の使用を開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="981bd-p109">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="981bd-148">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="981bd-148">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [<span data-ttu-id="981bd-149">Office 365 PowerShell をお使いいただく理由</span><span class="sxs-lookup"><span data-stu-id="981bd-149">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

- <span data-ttu-id="981bd-p110">Windows PowerShell には、ただ Office 365 管理センターを使用するだけではなく、速度、単純さ、生産性において多くの利点があります。次のトピックでこれらの利点について説明します。</span><span class="sxs-lookup"><span data-stu-id="981bd-p110">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="981bd-152">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="981bd-152">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [<span data-ttu-id="981bd-153">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="981bd-153">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [<span data-ttu-id="981bd-154">クイック リファレンス: Windows PowerShell を使用した一般的な Lync Online の管理タスクの実行</span><span class="sxs-lookup"><span data-stu-id="981bd-154">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="981bd-155">関連トピック</span><span class="sxs-lookup"><span data-stu-id="981bd-155">Related topics</span></span>

[<span data-ttu-id="981bd-156">Office 365 での電話会議を使用または購入する</span><span class="sxs-lookup"><span data-stu-id="981bd-156">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

