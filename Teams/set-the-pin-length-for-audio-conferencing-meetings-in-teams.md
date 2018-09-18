---
title: Microsoft Teams で電話会議用の PIN の長さを設定する
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
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: PIN の長さと要件のパラメーターについて、および Microsoft Teams の会議での長さを設定する方法について、説明します。
ms.openlocfilehash: 0300bba9139bdf98315b8af4200dd729ff6e70a1
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882992"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-microsoft-teams"></a><span data-ttu-id="34e92-103">Microsoft Teams で電話会議用の PIN の長さを設定する</span><span class="sxs-lookup"><span data-stu-id="34e92-103">Set the PIN length for Audio Conferencing meetings</span></span>

<span data-ttu-id="34e92-104">Microsoft Teams の電話会議をセットアップしている場合、電話会議ブリッジを取得します。</span><span class="sxs-lookup"><span data-stu-id="34e92-104">When you are setting up audio conferencing for Microsoft Teams, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="34e92-105">電話会議ブリッジには、1 つまたは複数の電話番号を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="34e92-105">A conferencing bridge can contain one or more phone numbers that people will use to call in to a Microsoft Teams meeting.</span></span> <span data-ttu-id="34e92-106">設定する電話番号は、Microsoft Teams アプリの会議の招待状に含まれます。</span><span class="sxs-lookup"><span data-stu-id="34e92-106">The phone number you set will be included on the meeting invites for the Microsoft Teams app.</span></span>
  
<span data-ttu-id="34e92-107">電話会議ブリッジは、電話機を使用して会議にダイヤルインしているユーザーの通話に応答します。</span><span class="sxs-lookup"><span data-stu-id="34e92-107">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="34e92-108">発信者に自動応答の音声案内で応答し、それから設定に応じて、通知メッセージを再生し、発信者に自分の名前を記録するように求めます。</span><span class="sxs-lookup"><span data-stu-id="34e92-108">The conferencing bridge answers the caller with voice prompts from a conferencing auto attendant, and then, depending on your settings, can play notifications, ask callers to record their name, and set up the PIN security.</span></span> <span data-ttu-id="34e92-109">**Microsoft のブリッジの設定**により、会議の通知の設定や会議参加のエクスペリエンスを変更したり、会議の開催者によって使用される PIN の長さを設定したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="34e92-109">**Microsoft bridge settings** allow you to change the settings for meeting notifications and the meeting join experience, and set the length of the PINs that are used by meeting organizers.</span></span> <span data-ttu-id="34e92-110">会議の開催者は、Microsoft Teams アプリを使用して会議に参加することができない場合に、PIN を使用して会議を開始します。</span><span class="sxs-lookup"><span data-stu-id="34e92-110">Meeting organizers use PINs to start meetings if they can't join the meeting using the Microsoft Teams app.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a><span data-ttu-id="34e92-111">PIN の長さを設定する</span><span class="sxs-lookup"><span data-stu-id="34e92-111">Setting the PIN length The default is 5.</span></span>

1. <span data-ttu-id="34e92-112">左側のナビゲーションで、[**会議**]  >  [**会議ブリッジ**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="34e92-112">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="34e92-113">[**会議ブリッジ**] ページの最上部で、[**ブリッジの設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34e92-113">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span> 

3. <span data-ttu-id="34e92-114">[**ブリッジの設定**] ペインの、[ **PIN の長さ**] の下で、PIN で必要な桁数を選択します。</span><span class="sxs-lookup"><span data-stu-id="34e92-114">In the **Bridge settings** pane, under **PIN length**, select the number of digits you want for the PIN.</span></span>

4. <span data-ttu-id="34e92-115">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34e92-115">Click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="34e92-116">PIN は会議 ID とは異なります。</span><span class="sxs-lookup"><span data-stu-id="34e92-116">A PIN is different from a conference ID.</span></span> <span data-ttu-id="34e92-117">会議 ID は発信者が会議に参加するときに使用するものです。</span><span class="sxs-lookup"><span data-stu-id="34e92-117">Conference IDs are used by callers when they join the meeting.</span></span> <span data-ttu-id="34e92-118">会議を識別するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="34e92-118">They are used to identify the meeting.</span></span> <span data-ttu-id="34e92-119">PIN は、会議の開催者が発信者を認証するために使用するものです。</span><span class="sxs-lookup"><span data-stu-id="34e92-119">The PIN is used to authenticate a caller as the meeting organizer.</span></span> 

## <a name="want-to-know-more-about-pin-settings"></a><span data-ttu-id="34e92-120">PIN 設定の詳細について調べる</span><span class="sxs-lookup"><span data-stu-id="34e92-120">Want to know more about PIN settings?</span></span>

- <span data-ttu-id="34e92-121">PIN は 4 桁から 12 桁の間にすることができます。既定では 5 桁です。</span><span class="sxs-lookup"><span data-stu-id="34e92-121">PINs can be from 4 to 12 digits; the default is 5.</span></span> <span data-ttu-id="34e92-122">PIN を作成するときに、使われるのは数字のみです。</span><span class="sxs-lookup"><span data-stu-id="34e92-122">Numbers are only used when creating PINs.</span></span> <span data-ttu-id="34e92-123">英字および特殊文字は使われません。</span><span class="sxs-lookup"><span data-stu-id="34e92-123">Letters and special characters aren't used.</span></span>
    
- <span data-ttu-id="34e92-124">PIN が必要になるのは、Microsoft Teams のユーザーがまだ会議を開始していないときの、会議の開催者のみです。</span><span class="sxs-lookup"><span data-stu-id="34e92-124">A PIN is only required for the meeting organizer when a Microsoft Teams user hasn't already started the meeting.</span></span> <span data-ttu-id="34e92-125">全員が会議にダイヤルインすると、会議の開催者が会議を開始するために PIN が必要になります。</span><span class="sxs-lookup"><span data-stu-id="34e92-125">If everyone is dialing in to the meeting, then the PIN is required for the meeting organizer to start the meeting.</span></span>
    
- <span data-ttu-id="34e92-126">PIN のセキュリティ設定は、Microsoft ブリッジに関連付けられているすべての電話番号に適用されます。</span><span class="sxs-lookup"><span data-stu-id="34e92-126">PIN security settings are applied to all of the phone numbers that are associated with a Microsoft bridge.</span></span> <span data-ttu-id="34e92-127">また、指定されたブリッジに関連付けられている電話番号を使用するすべての会議にも適用されます。</span><span class="sxs-lookup"><span data-stu-id="34e92-127">They will be applied to all meetings that use the phone numbers associated with a given bridge.</span></span> 
    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="34e92-128">Windows PowerShell の詳細情報</span><span class="sxs-lookup"><span data-stu-id="34e92-128">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="34e92-p107">Windows PowerShell は、ユーザーと、ユーザーに許可されていることと許可されていないことを管理するためにあるということです。Windows PowerShell があれば、一元管理を使用して Office 365 を管理し、複数のタスクを抱えているときに、日常の仕事を簡素化することができます。Windows PowerShell を開始するには、これらのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="34e92-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="34e92-132">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="34e92-132">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="34e92-133">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="34e92-133">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="34e92-134">Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="34e92-134">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
## <a name="related-topics"></a><span data-ttu-id="34e92-135">関連トピック</span><span class="sxs-lookup"><span data-stu-id="34e92-135">Related topics</span></span>

[<span data-ttu-id="34e92-136">Office 365 での電話会議を使用または購入する</span><span class="sxs-lookup"><span data-stu-id="34e92-136">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
