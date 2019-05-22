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
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: PIN の長さと要件のパラメーターについて説明し、「Microsoft Teams で会議の長さを設定する方法」を参照してください。
ms.openlocfilehash: 938e8096cf39c482a2de9f143174e6c261c652d8
ms.sourcegitcommit: 30995da65ff6a9b33534c3818833cf0ae1952ab9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/22/2019
ms.locfileid: "34344219"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-microsoft-teams"></a><span data-ttu-id="d296e-103">Microsoft Teams で電話会議用の PIN の長さを設定する</span><span class="sxs-lookup"><span data-stu-id="d296e-103">Set the PIN length for Audio Conferencing meetings in Microsoft Teams</span></span>

<span data-ttu-id="d296e-104">Microsoft Teams の電話会議をセットアップする場合は、電話会議ブリッジを取得します。</span><span class="sxs-lookup"><span data-stu-id="d296e-104">When you are setting up audio conferencing for Microsoft Teams, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="d296e-105">電話会議ブリッジには 1 つまたは複数の電話番号を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="d296e-105">A conferencing bridge can contain one or more phone numbers.</span></span> <span data-ttu-id="d296e-106">設定した電話番号は、Microsoft Teams アプリの会議出席依頼に含まれます。</span><span class="sxs-lookup"><span data-stu-id="d296e-106">The phone number you set will be included on the meeting invites for the Microsoft Teams app.</span></span>
  
<span data-ttu-id="d296e-107">電話会議ブリッジは、電話を使って会議にダイヤルインしているユーザーに対して、通話に応答します。</span><span class="sxs-lookup"><span data-stu-id="d296e-107">The audio conferencing bridge answers a call for people who are dialing in to a meeting using a phone.</span></span> <span data-ttu-id="d296e-108">自動応答からの音声プロンプトで、発信者に応答し、設定に応じて、通知を再生し、発信者に名前を記録するように依頼することができます。</span><span class="sxs-lookup"><span data-stu-id="d296e-108">It answers the caller with voice prompts from an auto attendant and then, depending on your settings, can play notifications and ask callers to record their name.</span></span> <span data-ttu-id="d296e-109">**Microsoft bridge の設定**を使用すると、会議の通知と会議の参加エクスペリエンスの設定を変更したり、会議の開催者によって使用される pin の長さを設定したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="d296e-109">**Microsoft bridge settings** allow you to change the settings for meeting notifications and the meeting join experience, and set the length of the PINs that are used by meeting organizers.</span></span> <span data-ttu-id="d296e-110">会議の開催者が Microsoft Teams アプリを使って会議に参加できない場合は、Pin を使って会議を開始します。</span><span class="sxs-lookup"><span data-stu-id="d296e-110">Meeting organizers use PINs to start meetings if they can't join the meeting using the Microsoft Teams app.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a><span data-ttu-id="d296e-111">PIN の長さを設定する</span><span class="sxs-lookup"><span data-stu-id="d296e-111">Setting the PIN length</span></span>

<span data-ttu-id="d296e-112">![Microsoft teams](media/teams-logo-30x30.png) **管理センターを使用し**た microsoft teams ロゴを示すアイコン</span><span class="sxs-lookup"><span data-stu-id="d296e-112">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="d296e-113">左側のナビゲーションで、[**会議**]  >  [**会議ブリッジ**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="d296e-113">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="d296e-114">[**会議ブリッジ**] ページの最上部で、[**ブリッジの設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d296e-114">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span> 

3. <span data-ttu-id="d296e-115">[**ブリッジの設定**] ウィンドウの [ **pin の長さ**] で、pin に必要な数字の数を選びます。</span><span class="sxs-lookup"><span data-stu-id="d296e-115">In the **Bridge settings** pane, under **PIN length**, select the number of digits you want for the PIN.</span></span>

4. <span data-ttu-id="d296e-116">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d296e-116">Click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="d296e-117">PIN が会議 ID とは異なります。</span><span class="sxs-lookup"><span data-stu-id="d296e-117">A PIN is different from a conference ID.</span></span> <span data-ttu-id="d296e-118">会議 Id は、発信者が会議に参加するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="d296e-118">Conference IDs are used by callers when they join the meeting.</span></span> <span data-ttu-id="d296e-119">会議を識別するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="d296e-119">They are used to identify the meeting.</span></span> <span data-ttu-id="d296e-120">PIN は、会議の開催者として発信者を認証するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="d296e-120">The PIN is used to authenticate a caller as the meeting organizer.</span></span> 

## <a name="want-to-know-more-about-pin-settings"></a><span data-ttu-id="d296e-121">PIN の設定について詳しく知りたいですか?</span><span class="sxs-lookup"><span data-stu-id="d296e-121">Want to know more about PIN settings?</span></span>

- <span data-ttu-id="d296e-122">Pin は 4 ~ 12 桁にすることができます。既定値は5です。</span><span class="sxs-lookup"><span data-stu-id="d296e-122">PINs can be from 4 to 12 digits; the default is 5.</span></span> <span data-ttu-id="d296e-123">数値はピンの作成時にのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="d296e-123">Numbers are only used when creating PINs.</span></span> <span data-ttu-id="d296e-124">文字と特殊文字は使用されません。</span><span class="sxs-lookup"><span data-stu-id="d296e-124">Letters and special characters aren't used.</span></span>
    
- <span data-ttu-id="d296e-125">PIN は、Microsoft Teams ユーザーが会議を開始していない場合に、会議の開催者にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="d296e-125">A PIN is only required for the meeting organizer when a Microsoft Teams user hasn't already started the meeting.</span></span> <span data-ttu-id="d296e-126">すべてのユーザーが会議にダイヤルインしている場合、会議の開催者が会議を開始するには、PIN が必要です。</span><span class="sxs-lookup"><span data-stu-id="d296e-126">If everyone is dialing in to the meeting, then the PIN is required for the meeting organizer to start the meeting.</span></span>
    
- <span data-ttu-id="d296e-127">PIN のセキュリティ設定は、Microsoft bridge に関連付けられているすべての電話番号に適用されます。</span><span class="sxs-lookup"><span data-stu-id="d296e-127">PIN security settings are applied to all of the phone numbers that are associated with a Microsoft bridge.</span></span> <span data-ttu-id="d296e-128">これらは、特定のブリッジに関連付けられている電話番号を使用するすべての会議に適用されます。</span><span class="sxs-lookup"><span data-stu-id="d296e-128">They will be applied to all meetings that use the phone numbers associated with a given bridge.</span></span> 
    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="d296e-129">Windows PowerShell の詳細情報</span><span class="sxs-lookup"><span data-stu-id="d296e-129">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="d296e-p107">Windows PowerShell で行うのは、ユーザーを管理し、ユーザーに何を許可して何を禁止するかを管理することです。Windows PowerShell を利用すると、Office 365 の管理を 1 か所で行うことができるので、複数のタスクを担当する管理者の日常業務を単純化できます。Windows PowerShell の使用を開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d296e-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="d296e-133">Office 365 PowerShell を使用する必要がある理由</span><span class="sxs-lookup"><span data-stu-id="d296e-133">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="d296e-134">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="d296e-134">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="d296e-135">Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d296e-135">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
## <a name="related-topics"></a><span data-ttu-id="d296e-136">関連トピック</span><span class="sxs-lookup"><span data-stu-id="d296e-136">Related topics</span></span>

[<span data-ttu-id="d296e-137">Office 365 での電話会議を試用または購入する</span><span class="sxs-lookup"><span data-stu-id="d296e-137">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
