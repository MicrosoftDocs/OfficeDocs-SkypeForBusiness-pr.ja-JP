---
title: 電話会議の PIN の長さを設定する
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: b86d31c6-1543-478f-b8c6-4b71e708403a
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: PIN の長さと要件のパラメーターについて説明し、会議の期間を設定する方法Microsoft Teams。
ms.openlocfilehash: 68dc1f3ea5508dc88bc168a5f3fbed837bbee04f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117165"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-microsoft-teams"></a><span data-ttu-id="c821c-103">Microsoft Teams で電話会議用の PIN の長さを設定する</span><span class="sxs-lookup"><span data-stu-id="c821c-103">Set the PIN length for Audio Conferencing meetings in Microsoft Teams</span></span>

<span data-ttu-id="c821c-104">会議用に電話会議を設定Microsoft Teams、電話会議ブリッジが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c821c-104">When you are setting up audio conferencing for Microsoft Teams, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="c821c-105">電話会議ブリッジには 1 つまたは複数の電話番号を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="c821c-105">A conferencing bridge can contain one or more phone numbers.</span></span> <span data-ttu-id="c821c-106">設定した電話番号は、新しいアプリの会議出席Microsoft Teamsされます。</span><span class="sxs-lookup"><span data-stu-id="c821c-106">The phone number you set will be included on the meeting invites for the Microsoft Teams app.</span></span>
  
<span data-ttu-id="c821c-107">電話会議ブリッジは、電話を使用して会議にダイヤルインしようとしているユーザーの呼び出しに応答します。</span><span class="sxs-lookup"><span data-stu-id="c821c-107">The audio conferencing bridge answers a call for people who are dialing in to a meeting using a phone.</span></span> <span data-ttu-id="c821c-108">自動応答からの音声プロンプトで呼び出し元に応答し、設定に応じて通知を再生し、発信者に自分の名前を記録するよう要求できます。</span><span class="sxs-lookup"><span data-stu-id="c821c-108">It answers the caller with voice prompts from an auto attendant and then, depending on your settings, can play notifications and ask callers to record their name.</span></span> <span data-ttu-id="c821c-109">**Microsoft Bridge の設定** を使用すると、会議通知と会議参加エクスペリエンスの設定を変更し、会議開催者が使用する PIN の長さを設定できます。</span><span class="sxs-lookup"><span data-stu-id="c821c-109">**Microsoft bridge settings** allow you to change the settings for meeting notifications and the meeting join experience, and set the length of the PINs that are used by meeting organizers.</span></span> <span data-ttu-id="c821c-110">会議の開催者は、新しいアプリを使用して会議に参加できない場合、PIN を使用してMicrosoft Teamsします。</span><span class="sxs-lookup"><span data-stu-id="c821c-110">Meeting organizers use PINs to start meetings if they can't join the meeting using the Microsoft Teams app.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a><span data-ttu-id="c821c-111">PIN の長さの設定</span><span class="sxs-lookup"><span data-stu-id="c821c-111">Setting the PIN length</span></span>

<span data-ttu-id="c821c-112">![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**</span><span class="sxs-lookup"><span data-stu-id="c821c-112">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="c821c-113">左側のナビゲーションで、[**会議**]  >  [**会議ブリッジ**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="c821c-113">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="c821c-114">[**会議ブリッジ**] ページの最上部で、[**ブリッジの設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c821c-114">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span> 

3. <span data-ttu-id="c821c-115">[ブリッジ **設定] ウィンドウ** の [PIN の長さ] **で、PIN** に使用する桁数を選択します。</span><span class="sxs-lookup"><span data-stu-id="c821c-115">In the **Bridge settings** pane, under **PIN length**, select the number of digits you want for the PIN.</span></span>

4. <span data-ttu-id="c821c-116">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c821c-116">Click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="c821c-117">PIN は会議 ID とは異なります。</span><span class="sxs-lookup"><span data-stu-id="c821c-117">A PIN is different from a conference ID.</span></span> <span data-ttu-id="c821c-118">会議 ID は、発信者が会議に参加するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="c821c-118">Conference IDs are used by callers when they join the meeting.</span></span> <span data-ttu-id="c821c-119">会議を識別するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="c821c-119">They are used to identify the meeting.</span></span> <span data-ttu-id="c821c-120">PIN は、発信者を会議開催者として認証するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="c821c-120">The PIN is used to authenticate a caller as the meeting organizer.</span></span> 

## <a name="want-to-know-more-about-pin-settings"></a><span data-ttu-id="c821c-121">PIN 設定の詳細については、次のページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c821c-121">Want to know more about PIN settings?</span></span>

- <span data-ttu-id="c821c-122">PIN は 4 ~ 12 桁です。既定値は 5 です。</span><span class="sxs-lookup"><span data-stu-id="c821c-122">PINs can be from 4 to 12 digits; the default is 5.</span></span> <span data-ttu-id="c821c-123">数値は、PIN を作成するときにのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="c821c-123">Numbers are only used when creating PINs.</span></span> <span data-ttu-id="c821c-124">文字と特殊文字は使用されません。</span><span class="sxs-lookup"><span data-stu-id="c821c-124">Letters and special characters aren't used.</span></span>
    
- <span data-ttu-id="c821c-125">PIN は、ユーザーが会議を開始していないMicrosoft Teams開催者にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="c821c-125">A PIN is only required for the meeting organizer when a Microsoft Teams user hasn't already started the meeting.</span></span> <span data-ttu-id="c821c-126">全員が会議にダイヤルインしている場合、会議の開催者が会議を開始するには PIN が必要です。</span><span class="sxs-lookup"><span data-stu-id="c821c-126">If everyone is dialing in to the meeting, then the PIN is required for the meeting organizer to start the meeting.</span></span>
    
- <span data-ttu-id="c821c-127">PIN のセキュリティ設定は、Microsoft ブリッジに関連付けられているすべての電話番号に適用されます。</span><span class="sxs-lookup"><span data-stu-id="c821c-127">PIN security settings are applied to all of the phone numbers that are associated with a Microsoft bridge.</span></span> <span data-ttu-id="c821c-128">特定のブリッジに関連付けられている電話番号を使用する会議に適用されます。</span><span class="sxs-lookup"><span data-stu-id="c821c-128">They will be applied to all meetings that use the phone numbers associated with a given bridge.</span></span> 
    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="c821c-129">Windows PowerShell の詳細情報</span><span class="sxs-lookup"><span data-stu-id="c821c-129">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="c821c-130">Windows PowerShellは、ユーザーの管理と、ユーザーが許可または許可されていない操作についてすべて行います。</span><span class="sxs-lookup"><span data-stu-id="c821c-130">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="c821c-131">このWindows PowerShell、1 つの管理Microsoft 365または Office 365 を管理し、複数のタスクを実行する場合に毎日の作業を簡略化できます。</span><span class="sxs-lookup"><span data-stu-id="c821c-131">With Windows PowerShell, you can manage Microsoft 365 or Office 365 by using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="c821c-132">Windows PowerShell の使用を開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c821c-132">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="c821c-133">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="c821c-133">Why you need to use Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="c821c-134">[アプリを使用してMicrosoft 365またはOffice 365を管理Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="c821c-134">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
<span data-ttu-id="c821c-135">Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](/powershell/module/teams/?view=teams-ps)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c821c-135">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
## <a name="related-topics"></a><span data-ttu-id="c821c-136">関連トピック</span><span class="sxs-lookup"><span data-stu-id="c821c-136">Related topics</span></span>

[<span data-ttu-id="c821c-137">電話会議を試用または購入するには、Microsoft 365またはOffice 365</span><span class="sxs-lookup"><span data-stu-id="c821c-137">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)