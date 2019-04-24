---
title: Microsoft Teams で電話会議用の PIN の長さを設定する
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
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: パラメーターの長さと、PIN の要件を説明し、マイクロソフトのチームでの会議の長さを設定する方法を参照してください。
ms.openlocfilehash: f18abb0601a624ca3b33304e45aaa1aacf0ee838
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32204833"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-microsoft-teams"></a><span data-ttu-id="edaef-103">Microsoft Teams で電話会議用の PIN の長さを設定する</span><span class="sxs-lookup"><span data-stu-id="edaef-103">Set the PIN length for Audio Conferencing meetings in Microsoft Teams</span></span>

<span data-ttu-id="edaef-104">Microsoft Teams の電話会議をセットアップしている場合、電話会議ブリッジを取得します。</span><span class="sxs-lookup"><span data-stu-id="edaef-104">When you are setting up audio conferencing for Microsoft Teams, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="edaef-105">電話会議ブリッジには、1 つまたは複数の電話番号を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="edaef-105">A conferencing bridge can contain one or more phone numbers.</span></span> <span data-ttu-id="edaef-106">設定する電話番号は、Microsoft Teams アプリの会議の招待状に含まれます。</span><span class="sxs-lookup"><span data-stu-id="edaef-106">The phone number you set will be included on the meeting invites for the Microsoft Teams app.</span></span>
  
<span data-ttu-id="edaef-107">電話会議ブリッジは、電話機を使用して会議にダイヤルインしているユーザーの通話に応答します。</span><span class="sxs-lookup"><span data-stu-id="edaef-107">The audio conferencing bridge answers a call for people who are dialing in to a meeting using a phone.</span></span> <span data-ttu-id="edaef-108">発信者に自動応答の音声案内で応答し、それから設定に応じて、通知メッセージを再生し、発信者に自分の名前を記録するように求めます。</span><span class="sxs-lookup"><span data-stu-id="edaef-108">It answers the caller with voice prompts from an auto attendant and then, depending on your settings, can play notifications and ask callers to record their name.</span></span> <span data-ttu-id="edaef-109">**Microsoft のブリッジの設定**により、会議の通知の設定や会議参加のエクスペリエンスを変更したり、会議の開催者によって使用される PIN の長さを設定したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="edaef-109">**Microsoft bridge settings** allow you to change the settings for meeting notifications and the meeting join experience, and set the length of the PINs that are used by meeting organizers.</span></span> <span data-ttu-id="edaef-110">会議の開催者は、Microsoft Teams アプリを使用して会議に参加することができない場合に、PIN を使用して会議を開始します。</span><span class="sxs-lookup"><span data-stu-id="edaef-110">Meeting organizers use PINs to start meetings if they can't join the meeting using the Microsoft Teams app.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a><span data-ttu-id="edaef-111">PIN の長さを設定する</span><span class="sxs-lookup"><span data-stu-id="edaef-111">Setting the PIN length</span></span>

<span data-ttu-id="edaef-112">![チーム ・ ロゴ ・ 30x30.png](media/teams-logo-30x30.png) **、マイクロソフトのチーム管理センターを使用して**</span><span class="sxs-lookup"><span data-stu-id="edaef-112">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="edaef-113">左側のナビゲーションで、[**会議**]  >  [**会議ブリッジ**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="edaef-113">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="edaef-114">[**会議ブリッジ**] ページの最上部で、[**ブリッジの設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="edaef-114">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span> 

3. <span data-ttu-id="edaef-115">**ブリッジ設定**ペインで、[**暗証番号 (pin) の長さ**PIN の桁数を選択します。</span><span class="sxs-lookup"><span data-stu-id="edaef-115">In the **Bridge settings** pane, under **PIN length**, select the number of digits you want for the PIN.</span></span>

4. <span data-ttu-id="edaef-116">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="edaef-116">Click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="edaef-117">PIN とは異なる、会議の id です。</span><span class="sxs-lookup"><span data-stu-id="edaef-117">A PIN is different from a conference ID.</span></span> <span data-ttu-id="edaef-118">会議 Id は、ミーティングに参加するときに、呼び出し元が使用されます。</span><span class="sxs-lookup"><span data-stu-id="edaef-118">Conference IDs are used by callers when they join the meeting.</span></span> <span data-ttu-id="edaef-119">ミーティングに使用されます。</span><span class="sxs-lookup"><span data-stu-id="edaef-119">They are used to identify the meeting.</span></span> <span data-ttu-id="edaef-120">暗証番号 (pin) を使用して、会議の開催者は、呼び出し元を認証します。</span><span class="sxs-lookup"><span data-stu-id="edaef-120">The PIN is used to authenticate a caller as the meeting organizer.</span></span> 

## <a name="want-to-know-more-about-pin-settings"></a><span data-ttu-id="edaef-121">暗証番号 (pin) の設定の詳細を知りたいとしていますか。</span><span class="sxs-lookup"><span data-stu-id="edaef-121">Want to know more about PIN settings?</span></span>

- <span data-ttu-id="edaef-122">ピンすることが 4 から 12 桁の数字です。デフォルトは 5 です。</span><span class="sxs-lookup"><span data-stu-id="edaef-122">PINs can be from 4 to 12 digits; the default is 5.</span></span> <span data-ttu-id="edaef-123">番号は、ピンを作成するときにのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="edaef-123">Numbers are only used when creating PINs.</span></span> <span data-ttu-id="edaef-124">文字と特殊文字は使用されません。</span><span class="sxs-lookup"><span data-stu-id="edaef-124">Letters and special characters aren't used.</span></span>
    
- <span data-ttu-id="edaef-125">のみ、暗証番号 (pin) は、マイクロソフトのチームのユーザーが会議を既に開始していないときに、会議の開催者に必要な。</span><span class="sxs-lookup"><span data-stu-id="edaef-125">A PIN is only required for the meeting organizer when a Microsoft Teams user hasn't already started the meeting.</span></span> <span data-ttu-id="edaef-126">場合はすべてのユーザーがダイヤルイン会議、PIN は、会議の開催者、会議を開始するために必要。</span><span class="sxs-lookup"><span data-stu-id="edaef-126">If everyone is dialing in to the meeting, then the PIN is required for the meeting organizer to start the meeting.</span></span>
    
- <span data-ttu-id="edaef-127">暗証番号 (pin) のセキュリティ設定は、すべての Microsoft のブリッジに関連付けられている電話番号に適用されます。</span><span class="sxs-lookup"><span data-stu-id="edaef-127">PIN security settings are applied to all of the phone numbers that are associated with a Microsoft bridge.</span></span> <span data-ttu-id="edaef-128">各ブリッジに関連付けられている電話番号を使用するすべての会議に適用されます。</span><span class="sxs-lookup"><span data-stu-id="edaef-128">They will be applied to all meetings that use the phone numbers associated with a given bridge.</span></span> 
    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="edaef-129">Windows PowerShell の詳細情報</span><span class="sxs-lookup"><span data-stu-id="edaef-129">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="edaef-p107">Windows PowerShell は、ユーザーと、ユーザーに許可されていることと許可されていないことを管理するためにあるということです。Windows PowerShell があれば、一元管理を使用して Office 365 を管理し、複数のタスクを抱えているときに、日常の仕事を簡素化することができます。Windows PowerShell を開始するには、これらのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="edaef-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="edaef-133">Office 365 PowerShell を使用する必要がある理由</span><span class="sxs-lookup"><span data-stu-id="edaef-133">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="edaef-134">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="edaef-134">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="edaef-135">Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="edaef-135">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
## <a name="related-topics"></a><span data-ttu-id="edaef-136">関連トピック</span><span class="sxs-lookup"><span data-stu-id="edaef-136">Related topics</span></span>

[<span data-ttu-id="edaef-137">Office 365 での電話会議を試用または購入する</span><span class="sxs-lookup"><span data-stu-id="edaef-137">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
