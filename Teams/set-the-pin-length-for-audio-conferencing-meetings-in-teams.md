---
title: マイクロソフトのチームでミーティングの電話会議の暗証番号 (pin) の長さを設定します。
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: b86d31c6-1543-478f-b8c6-4b71e708403a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: パラメーターの長さと、PIN の要件を説明し、マイクロソフトのチームでの会議の長さを設定する方法を参照してください。
ms.openlocfilehash: 3c4b0d40e78cda844a443c4ca1d4fc7927dfeed3
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23867084"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-microsoft-teams"></a><span data-ttu-id="d9725-103">マイクロソフトのチームでミーティングの電話会議の暗証番号 (pin) の長さを設定します。</span><span class="sxs-lookup"><span data-stu-id="d9725-103">Set the PIN length for Audio Conferencing meetings in Microsoft Teams</span></span>

<span data-ttu-id="d9725-104">マイクロソフト チームの電話会議を設定するときに、オーディオ会議ブリッジが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d9725-104">When you are setting up audio conferencing for Microsoft Teams, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="d9725-105">会議用ブリッジは、1 つまたは複数の電話番号を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="d9725-105">A conferencing bridge can contain one or more phone numbers.</span></span> <span data-ttu-id="d9725-106">チームの Microsoft アプリケーションの会議の招待に設定した電話番号が含まれます。</span><span class="sxs-lookup"><span data-stu-id="d9725-106">The phone number you set will be included on the meeting invites for the Microsoft Teams app.</span></span>
  
<span data-ttu-id="d9725-107">オーディオ会議ブリッジ、電話を使用して会議にダイヤルインしている人のための呼び出しに応答します。</span><span class="sxs-lookup"><span data-stu-id="d9725-107">The audio conferencing bridge answers a call for people who are dialing in to a meeting using a phone.</span></span> <span data-ttu-id="d9725-108">自動応答から、設定によっては、音声メッセージを呼び出し元に応答、通知を再生でき、自分の名前を記録するための呼び出し元に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="d9725-108">It answers the caller with voice prompts from an auto attendant and then, depending on your settings, can play notifications and ask callers to record their name.</span></span> <span data-ttu-id="d9725-109">**マイクロソフト ブリッジの設定**では、会議の通知の設定を変更することができ、会議の参加、会議の開催者によって使用されているピンの長さを設定します。</span><span class="sxs-lookup"><span data-stu-id="d9725-109">**Microsoft bridge settings** allow you to change the settings for meeting notifications and the meeting join experience, and set the length of the PINs that are used by meeting organizers.</span></span> <span data-ttu-id="d9725-110">ミーティングの開催者は、マイクロソフト チームのアプリケーションを使用してミーティングに参加することはできない場合は、会議を開始するためのピンを使用します。</span><span class="sxs-lookup"><span data-stu-id="d9725-110">Meeting organizers use PINs to start meetings if they can't join the meeting using the Microsoft Teams app.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a><span data-ttu-id="d9725-111">暗証番号 (pin) の長さを設定</span><span class="sxs-lookup"><span data-stu-id="d9725-111">Setting the PIN length</span></span>

1. <span data-ttu-id="d9725-112">左側のナビゲーションでは、**会議**に移動 > **会議ブリッジ**です。</span><span class="sxs-lookup"><span data-stu-id="d9725-112">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="d9725-113">**会議ブリッジ**のページの上部には、**ブリッジの設定**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d9725-113">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span> 

3. <span data-ttu-id="d9725-114">**ブリッジ設定**ペインで、[**暗証番号 (pin) の長さ**PIN の桁数を選択します。</span><span class="sxs-lookup"><span data-stu-id="d9725-114">In the **Bridge settings** pane, under **PIN length**, select the number of digits you want for the PIN.</span></span>

4. <span data-ttu-id="d9725-115">[ **保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d9725-115">Click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="d9725-116">PIN とは異なる、会議の id です。</span><span class="sxs-lookup"><span data-stu-id="d9725-116">A PIN is different from a conference ID.</span></span> <span data-ttu-id="d9725-117">会議 Id は、ミーティングに参加するときに、呼び出し元が使用されます。</span><span class="sxs-lookup"><span data-stu-id="d9725-117">Conference IDs are used by callers when they join the meeting.</span></span> <span data-ttu-id="d9725-118">ミーティングに使用されます。</span><span class="sxs-lookup"><span data-stu-id="d9725-118">They are used to identify the meeting.</span></span> <span data-ttu-id="d9725-119">暗証番号 (pin) を使用して、会議の開催者は、呼び出し元を認証します。</span><span class="sxs-lookup"><span data-stu-id="d9725-119">The PIN is used to authenticate a caller as the meeting organizer.</span></span> 

## <a name="want-to-know-more-about-pin-settings"></a><span data-ttu-id="d9725-120">暗証番号 (pin) の設定の詳細を知りたいとしていますか。</span><span class="sxs-lookup"><span data-stu-id="d9725-120">Want to know more about PIN settings?</span></span>

- <span data-ttu-id="d9725-121">ピンすることが 4 から 12 桁の数字です。デフォルトは 5 です。</span><span class="sxs-lookup"><span data-stu-id="d9725-121">PINs can be from 4 to 12 digits; the default is 5.</span></span> <span data-ttu-id="d9725-122">番号は、ピンを作成するときにのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="d9725-122">Numbers are only used when creating PINs.</span></span> <span data-ttu-id="d9725-123">文字と特殊文字は使用されません。</span><span class="sxs-lookup"><span data-stu-id="d9725-123">Letters and special characters aren't used.</span></span>
    
- <span data-ttu-id="d9725-124">のみ、暗証番号 (pin) は、マイクロソフトのチームのユーザーが会議を既に開始していないときに、会議の開催者に必要な。</span><span class="sxs-lookup"><span data-stu-id="d9725-124">A PIN is only required for the meeting organizer when a Microsoft Teams user hasn't already started the meeting.</span></span> <span data-ttu-id="d9725-125">場合はすべてのユーザーがダイヤルイン会議、PIN は、会議の開催者、会議を開始するために必要。</span><span class="sxs-lookup"><span data-stu-id="d9725-125">If everyone is dialing in to the meeting, then the PIN is required for the meeting organizer to start the meeting.</span></span>
    
- <span data-ttu-id="d9725-126">暗証番号 (pin) のセキュリティ設定は、すべての Microsoft のブリッジに関連付けられている電話番号に適用されます。</span><span class="sxs-lookup"><span data-stu-id="d9725-126">PIN security settings are applied to all of the phone numbers that are associated with a Microsoft bridge.</span></span> <span data-ttu-id="d9725-127">各ブリッジに関連付けられている電話番号を使用するすべての会議に適用されます。</span><span class="sxs-lookup"><span data-stu-id="d9725-127">They will be applied to all meetings that use the phone numbers associated with a given bridge.</span></span> 
    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="d9725-128">Windows PowerShell の詳細情報</span><span class="sxs-lookup"><span data-stu-id="d9725-128">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="d9725-p107">Windows PowerShell は、ユーザーと、ユーザーに許可されていることと許可されていないことを管理するためにあるということです。Windows PowerShell があれば、一元管理を使用して Office 365 を管理し、複数のタスクを抱えているときに、日常の仕事を簡素化することができます。Windows PowerShell を開始するには、これらのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d9725-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="d9725-132">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="d9725-132">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="d9725-133">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="d9725-133">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="d9725-134">Windows PowerShell の詳細については、[マイクロソフト チームの PowerShell の参照](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)の詳細についてを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d9725-134">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
## <a name="related-topics"></a><span data-ttu-id="d9725-135">このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「Skype for Business Online 用 Windows PowerShell モジュール」からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="d9725-135">Related topics</span></span>

[<span data-ttu-id="d9725-136">Office 365 での電話会議を使用または購入する</span><span class="sxs-lookup"><span data-stu-id="d9725-136">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
