---
title: ユーザーの会議 ID を表示、変更、リセットする
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
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-apr2020
description: Microsoft Teams のユーザーに会議 ID を割り当てる方法と、会議 ID パラメーターの設定方法について説明します。
ms.openlocfilehash: b57a419266ceca09a73fc4bf75bb12153e41ea91
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117210"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-microsoft-teams"></a><span data-ttu-id="92ef0-103">Microsoft Teams でユーザーに割り当てられた会議 ID を表示およびリセットする</span><span class="sxs-lookup"><span data-stu-id="92ef0-103">View and reset a conference ID assigned to a user in Microsoft Teams</span></span>

<span data-ttu-id="92ef0-104">Microsoft 365 または Office 365 で電話会議用にセットアップされ、Microsoft を電話会議プロバイダーとして使用すると、Microsoft Teams ユーザーに会議 ID が自動的に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="92ef0-104">A conferencing ID is automatically assigned to a Microsoft Teams user when they are set up for Audio Conferencing in Microsoft 365 or Office 365 and use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="92ef0-105">割り当てられた会議 ID は、会議のスケジュール時に会議出席招待で送信されます。</span><span class="sxs-lookup"><span data-stu-id="92ef0-105">The conference ID assigned is sent in the meeting invite when the meeting is scheduled.</span></span> <span data-ttu-id="92ef0-106">ユーザーがスケジュール設定した各会議には、一意の会議通話 ID が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="92ef0-106">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> 
  
<span data-ttu-id="92ef0-107">会議 ID は自動的に作成され、ユーザーに割り当てられますが、ユーザーがこれを使いたくないときに特定の番号に設定したい場合や、ユーザーが会議 ID を思い出したり紛失したりできない場合があります。</span><span class="sxs-lookup"><span data-stu-id="92ef0-107">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="92ef0-108">Microsoft Teams 管理センターまたは管理者は、Windows PowerShell ID の表示、変更、リセットを行えます。</span><span class="sxs-lookup"><span data-stu-id="92ef0-108">You can use Microsoft Teams admin center or Windows PowerShell to view, change, and reset their conference ID.</span></span>
  
<span data-ttu-id="92ef0-109">ユーザーに会議 ID と既定の電話会議の電話番号が含む電子メールが送信されるか、または会議 ID をリセットすると、PINではない 会議 ID を含む別の電子メールが送信されます。</span><span class="sxs-lookup"><span data-stu-id="92ef0-109">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN.</span></span> <span data-ttu-id="92ef0-110">会議 [開催者の PIN をリセットする](reset-a-conference-id-for-a-user-in-teams.md) 方法の詳細については、「Microsoft Teams でユーザーの会議 ID をリセットする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="92ef0-110">See [Reset a conference ID for a user in Microsoft Teams](reset-a-conference-id-for-a-user-in-teams.md) for more information about how to reset a conference organizer's PIN.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="view-and-reset-conference-ids"></a><span data-ttu-id="92ef0-111">会議 Idの表示と リセット</span><span class="sxs-lookup"><span data-stu-id="92ef0-111">View and reset conference IDs</span></span>

### <a name="to-view-the-conference-id"></a><span data-ttu-id="92ef0-112">会議 ID を表示するには</span><span class="sxs-lookup"><span data-stu-id="92ef0-112">To view the conference ID</span></span>

<span data-ttu-id="92ef0-113">![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**</span><span class="sxs-lookup"><span data-stu-id="92ef0-113">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="92ef0-114">左側のナビゲーションで、[**ユーザー**] をクリックしてから、空いているユーザーのリストからユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="92ef0-114">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="92ef0-115">ページの上部にある [編集] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="92ef0-115">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="92ef0-116">[ **電話会議] で、[** 電話会議 **ID] の下を確認します**。</span><span class="sxs-lookup"><span data-stu-id="92ef0-116">Under **Audio Conferencing**, look under **Conference ID**.</span></span>

    > [!TIP]
    > <span data-ttu-id="92ef0-117">[電話会議情報をメールで送信] リンクをクリックすると、会議 ID と音声電話番号を含むすべての会議情報をメールでユーザー **に送信** できます。</span><span class="sxs-lookup"><span data-stu-id="92ef0-117">You can send all of the conferencing information to the user in an email that includes the conference ID and audio phone numbers by clicking the **Send conference info in email** link.</span></span>
  
<span data-ttu-id="92ef0-118">**Windows PowerShell を使用する**</span><span class="sxs-lookup"><span data-stu-id="92ef0-118">**Using Windows PowerShell**</span></span>

<span data-ttu-id="92ef0-119">詳細については、[Microsoft Teams PowerShell のリファレンス](/powershell/module/teams/?view=teams-ps)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="92ef0-119">See the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
### <a name="to-reset-the-conference-id"></a><span data-ttu-id="92ef0-120">会議 ID をリセットするには</span><span class="sxs-lookup"><span data-stu-id="92ef0-120">To reset the conference ID</span></span>

<span data-ttu-id="92ef0-121">例えば忘れてしまったなどの場合のために、ユーザーの会議 ID をリセットできます。</span><span class="sxs-lookup"><span data-stu-id="92ef0-121">You can reset a conference ID for a user if, for example, they forget it.</span></span>
  
<span data-ttu-id="92ef0-122">![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**</span><span class="sxs-lookup"><span data-stu-id="92ef0-122">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="92ef0-123">左側のナビゲーションで、[**ユーザー**] をクリックしてから、空いているユーザーのリストからユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="92ef0-123">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="92ef0-124">ページの上部にある [編集] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="92ef0-124">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="92ef0-125">[**電話会議**] で [**会議通話 ID のリセット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="92ef0-125">Under **Audio Conferencing**, click **Reset conference ID**.</span></span>

4. <span data-ttu-id="92ef0-126">[会議 ID **のリセット] ウィンドウで** 、[リセット] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="92ef0-126">In the **Reset conference ID** window, click **Reset**.</span></span> <span data-ttu-id="92ef0-127">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="92ef0-127">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span>
  
<span data-ttu-id="92ef0-128">**Windows PowerShell を使用する**</span><span class="sxs-lookup"><span data-stu-id="92ef0-128">**Using Windows PowerShell**</span></span>

<span data-ttu-id="92ef0-129">詳細については、[Microsoft Teams PowerShell のリファレンス](/powershell/module/teams/?view=teams-ps)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="92ef0-129">See the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>


## <a name="what-else-should-you-know"></a><span data-ttu-id="92ef0-130">その他の情報</span><span class="sxs-lookup"><span data-stu-id="92ef0-130">What else should you know?</span></span>

   > [!IMPORTANT]
   >  <span data-ttu-id="92ef0-131">新しい会議 ID が作成またはリセットされると、古い会議 ID を発信者が使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="92ef0-131">After a new conference ID is created or one is reset, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="92ef0-132">既存の会議の出席依頼のスケジュールを変更して、新しい会議 ID を出席依頼に追加するように、ユーザーに通知してください。</span><span class="sxs-lookup"><span data-stu-id="92ef0-132">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> 
  
    
- <span data-ttu-id="92ef0-133">会議 ID は、オーディオ会議ブリッジに設定された桁の長さを満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="92ef0-133">The conference ID must meet the length in digits set on the audio conferencing bridge.</span></span> <span data-ttu-id="92ef0-134">会議 Id には、アルファベットまたは特殊文字を使うことはできません。数値のみが使用できます。</span><span class="sxs-lookup"><span data-stu-id="92ef0-134">You can't use alphabetic or special characters in conference IDs; only numbers can be used.</span></span>
   
    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="92ef0-135">Windows PowerShell の詳細情報</span><span class="sxs-lookup"><span data-stu-id="92ef0-135">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="92ef0-136">Windows PowerShellは、ユーザーの管理と、ユーザーに許可する操作と許可しない操作の管理に使います。</span><span class="sxs-lookup"><span data-stu-id="92ef0-136">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="92ef0-137">Windows PowerShell では、単一の管理ポイントを使用して Microsoft 365 または Office 365 を管理できます。複数のタスクを実行する必要がある場合に毎日の作業を簡略化できます。</span><span class="sxs-lookup"><span data-stu-id="92ef0-137">With Windows PowerShell, you can manage Microsoft 365 or Office 365 by using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="92ef0-138">Windows PowerShell の使用を開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="92ef0-138">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="92ef0-139">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="92ef0-139">Why you need to use Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="92ef0-140">[Microsoft 365 または Office 365 を管理するための最適Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="92ef0-140">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
<span data-ttu-id="92ef0-141">Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](/powershell/module/teams/?view=teams-ps)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="92ef0-141">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="92ef0-142">関連トピック</span><span class="sxs-lookup"><span data-stu-id="92ef0-142">Related topics</span></span>

[<span data-ttu-id="92ef0-143">Microsoft 365 または Office 365 で電話会議を試用または購入する</span><span class="sxs-lookup"><span data-stu-id="92ef0-143">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)