---
title: Microsoft Teams でユーザーに割り当てられている会議 ID を表示、変更、リセットする
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 77d36233-2aab-4802-ba9c-e9a8885ea643
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: '会議 ID を Microsoft Teams のユーザーに割り当てる方法と、会議 ID のパラメーターの値がどうなるかについて説明します。 '
ms.openlocfilehash: 317216f84044eb404541a98d24c69b2f7fb61bc4
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2018
ms.locfileid: "25017086"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-microsoft-teams"></a><span data-ttu-id="4376a-103">Microsoft Teams でユーザーに割り当てられた会議 ID を表示、リセットする</span><span class="sxs-lookup"><span data-stu-id="4376a-103">View and reset a conference ID assigned to a user in Microsoft Teams</span></span>

<span data-ttu-id="4376a-104">会議 ID が自動的に割り当てられているマイクロソフトのチームのユーザーに Office 365 での音声会議用に設定し、Microsoft を使用して、オーディオ会議プロバイダーとして。</span><span class="sxs-lookup"><span data-stu-id="4376a-104">A conferencing ID is automatically assigned to a Microsoft Teams user when they are set up for Audio Conferencing in Office 365 and use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="4376a-105">会議 ID が割り当てられているは、会議がスケジュールされているとき、会議出席依頼で送信されます。</span><span class="sxs-lookup"><span data-stu-id="4376a-105">The conference ID assigned is sent in the meeting invite when the meeting is scheduled.</span></span> <span data-ttu-id="4376a-106">ユーザーをスケジュールする会議ごとに固有の会議 ID が割り当てられますを取得</span><span class="sxs-lookup"><span data-stu-id="4376a-106">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> 
  
<span data-ttu-id="4376a-107">会議 ID が自動的に作成され、ユーザーに割り当てられているが場合がありますこの 1 つを使用するユーザーが望まないし、特定の数に設定するとき、またはユーザーが覚えられないか、会議 ID が失われている場合</span><span class="sxs-lookup"><span data-stu-id="4376a-107">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="4376a-108">マイクロソフトのチーム管理センターまたは Windows PowerShell を使用するには表示、変更、および、会議 ID をリセットするには</span><span class="sxs-lookup"><span data-stu-id="4376a-108">You can use Microsoft Teams admin center or Windows PowerShell to view, change, and reset their conference ID.</span></span>
  
<span data-ttu-id="4376a-109">ユーザーに会議 ID と既定の電話会議の電話番号が含む電子メールが送信されるか、または会議 ID をリセットすると、PINではない 会議 ID を含む別の電子メールが送信されます。</span><span class="sxs-lookup"><span data-stu-id="4376a-109">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN.</span></span> <span data-ttu-id="4376a-110">会議の開催者のPINをリセットするの詳細については、 [ここ](reset-a-conference-id-for-a-user-in-teams.md)をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4376a-110">For more information about resetting a conference organizer's PIN, [go here](reset-a-conference-id-for-a-user-in-teams.md).</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="view-and-reset-conference-ids"></a><span data-ttu-id="4376a-111">会議 Idの表示と リセット</span><span class="sxs-lookup"><span data-stu-id="4376a-111">View and reset conference IDs</span></span>

### <a name="to-view-the-conference-id"></a><span data-ttu-id="4376a-112">会議 ID を表示するには</span><span class="sxs-lookup"><span data-stu-id="4376a-112">To view the conference ID</span></span>

<span data-ttu-id="4376a-113">![teams-logo-30x30.png](media/teams-logo-30x30.png) \*\*Microsoft Teams と Skype for Business 管理センターを使用する: \*\*</span><span class="sxs-lookup"><span data-stu-id="4376a-113">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="4376a-114">左側のナビゲーションで、[**ユーザー**] をクリックしてから、空いているユーザーのリストからユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="4376a-114">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="4376a-115">ページの上部で、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4376a-115">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="4376a-116">[**電話会議**] の下で、[\*\*会議 ID \*\*] を確認します。</span><span class="sxs-lookup"><span data-stu-id="4376a-116">Under **Audio Conferencing**, look under **Conference ID**.</span></span>

    > [!TIP]
    > <span data-ttu-id="4376a-117">[**電話会議情報をメールで送信**] リンクをクリックすると、会議 ID や電話会議の電話番号を含んでいるメールで、会議に必要なすべての情報をユーザーに送信することができます。</span><span class="sxs-lookup"><span data-stu-id="4376a-117">You can send all of the conferencing information to the user in an email that includes the conference ID and audio phone numbers by clicking the **Send conference info in email** link.</span></span>
  
<span data-ttu-id="4376a-118">**Windows PowerShell を使用する**</span><span class="sxs-lookup"><span data-stu-id="4376a-118">**Using Windows PowerShell**</span></span>

<span data-ttu-id="4376a-119">詳細については、[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4376a-119">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
### <a name="to-reset-the-conference-id"></a><span data-ttu-id="4376a-120">会議 ID をリセットするには</span><span class="sxs-lookup"><span data-stu-id="4376a-120">To reset the conference ID</span></span>

<span data-ttu-id="4376a-121">ユーザーの会議 ID を、ユーザーが忘れてしまった場合などに、リセットすることができます。</span><span class="sxs-lookup"><span data-stu-id="4376a-121">You can reset a conference ID for a user if, for example, they forget it.</span></span>
  
<span data-ttu-id="4376a-122">![teams-logo-30x30.png](media/teams-logo-30x30.png) \*\*Microsoft Teams と Skype for Business 管理センターを使用する: \*\*</span><span class="sxs-lookup"><span data-stu-id="4376a-122">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="4376a-123">左側のナビゲーションで、[**ユーザー**] をクリックしてから、空いているユーザーのリストからユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="4376a-123">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="4376a-124">ページの上部で、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4376a-124">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="4376a-125">[**電話会議**] の下で、[**会議 ID のリセット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4376a-125">Under **Audio Conferencing**, click **Reset conference ID**.</span></span>

4. <span data-ttu-id="4376a-126">**会議 ID のリセット**] ウィンドウで、[**リセット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4376a-126">In the **Reset conference ID** window, click **Reset**.</span></span> <span data-ttu-id="4376a-127">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="4376a-127">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span>
  
<span data-ttu-id="4376a-128">**Windows PowerShell を使用する**</span><span class="sxs-lookup"><span data-stu-id="4376a-128">**Using Windows PowerShell**</span></span>

<span data-ttu-id="4376a-129">詳細については、[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4376a-129">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>


## <a name="what-else-should-you-know"></a><span data-ttu-id="4376a-130">その他の情報</span><span class="sxs-lookup"><span data-stu-id="4376a-130">What else should you know?</span></span>

   > [!IMPORTANT]
   >  <span data-ttu-id="4376a-131">新しい会議 ID が作成されるか、1 つは、リセット後、は、呼び出し元が古い会議 ID を使用できません。</span><span class="sxs-lookup"><span data-stu-id="4376a-131">After a new conference ID is created or one is reset, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="4376a-132">The users can use Skype for Business Meeting Migration Tool to update their existing meetings.</span><span class="sxs-lookup"><span data-stu-id="4376a-132">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> 
  
    
- <span data-ttu-id="4376a-133">会議 ID は、オーディオ会議ブリッジに設定された桁の長さを満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="4376a-133">The conference ID must meet the length in digits set on the audio conferencing bridge.</span></span> <span data-ttu-id="4376a-134">会議 Id には、アルファベットまたは特殊文字を使うことはできません。数値のみが使用できます。</span><span class="sxs-lookup"><span data-stu-id="4376a-134">You can't use alphabetic or special characters in conference IDs; only numbers can be used.</span></span>
    
- <span data-ttu-id="4376a-135">オーディオ会議のすべてのユーザーの会議 ID は、既定では、7 桁になります。桁数を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="4376a-135">The conference ID for all of your audio conferencing users will be 7 digits by default, and the number of digits can't be changed.</span></span>
    
    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="4376a-136">Windows PowerShell の詳細情報</span><span class="sxs-lookup"><span data-stu-id="4376a-136">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="4376a-p107">Windows PowerShell は、ユーザーと、ユーザーに許可されていることと許可されていないことを管理するためにあるということです。Windows PowerShell があれば、一元管理を使用して Office 365 を管理し、複数のタスクを抱えているときに、日常の仕事を簡素化することができます。Windows PowerShell を開始するには、これらのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4376a-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="4376a-140">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="4376a-140">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="4376a-141">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="4376a-141">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="4376a-142">Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4376a-142">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="4376a-143">関連トピック</span><span class="sxs-lookup"><span data-stu-id="4376a-143">Related topics</span></span>

[<span data-ttu-id="4376a-144">Office 365 での電話会議を使用または購入する</span><span class="sxs-lookup"><span data-stu-id="4376a-144">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)

