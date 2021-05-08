---
title: 電話で電話会議を開始し、PIN を使わずに電話会議を開始Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
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
description: '管理者センターから匿名の発信者が会議に参加Teams方法について学習します。 '
ms.openlocfilehash: 520bf720a01a686a103748cdbbf26cb8426e94f2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116965"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-microsoft-teams"></a><span data-ttu-id="b5688-103">Microsoft Teams で PIN を使用せずに電話で電話会議を開始する</span><span class="sxs-lookup"><span data-stu-id="b5688-103">Start an Audio Conference over the phone without a PIN in Microsoft Teams</span></span>

<span data-ttu-id="b5688-104">Microsoft Teams 会議の開催者が会議を開始しないので、会議にダイヤルインしたユーザーが音楽を聴いて会議のロビーで開催されるのは、いら立つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="b5688-104">It might be frustrating for users who dial in to a meeting to be held in the meeting's lobby listening to music because the Microsoft Teams meeting organizer hasn't started the meeting.</span></span> 
  
<span data-ttu-id="b5688-105">会議の開催者が会議にコールインする場合、既定では、会議を開始するために PIN が必要です。</span><span class="sxs-lookup"><span data-stu-id="b5688-105">If a meeting organizer calls in to the meeting, by default, a PIN is required to start a meeting.</span></span> <span data-ttu-id="b5688-106">誰でも会議にダイヤルインし、PIN で会議を開始するように求めららなく設定できます。</span><span class="sxs-lookup"><span data-stu-id="b5688-106">You can set it up so that anyone can dial in to a meeting and not be prompted for a PIN to start the meeting.</span></span> <span data-ttu-id="b5688-107">管理センターを使用して、1 人のユーザーに対してこの設定を有効または無効にできます。</span><span class="sxs-lookup"><span data-stu-id="b5688-107">You can use the admin center to enable or disable this setting for a single user.</span></span>
  
<span data-ttu-id="b5688-108">他のユーザーが会議アプリから会議を開始した場合、会議の開催者に PIN はMicrosoft Teamsではありません。</span><span class="sxs-lookup"><span data-stu-id="b5688-108">A PIN isn't required for the meeting organizer if someone has started the meeting from the Microsoft Teams app.</span></span> <span data-ttu-id="b5688-109">PIN が必要であるのは、会議の開催者が電話で自分の会議に参加する場合のみです。</span><span class="sxs-lookup"><span data-stu-id="b5688-109">A PIN is only required when a meeting organizer joins their meeting over a phone.</span></span> <span data-ttu-id="b5688-110">会議の PIN は、電話会議ライセンスが割り当て済みで電話会議が有効になると、音声ユーザーに送信されます。</span><span class="sxs-lookup"><span data-stu-id="b5688-110">The PIN for meetings is sent to the audio user when they are assigned the **Audio Conferencing** license and are enabled for Audio Conferencing.</span></span> <span data-ttu-id="b5688-111">「 [電話会議の設定が変](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md) わると自動的にユーザーに送信される電話会議情報とメールをユーザーに送信する [」を参照してください](emails-sent-to-users-when-their-settings-change-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="b5688-111">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md) and [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change-in-teams.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a><span data-ttu-id="b5688-112">匿名の発信者の会議への参加を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="b5688-112">Enable or disable anonymous callers from joining a meeting</span></span>

<span data-ttu-id="b5688-113">![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**</span><span class="sxs-lookup"><span data-stu-id="b5688-113">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="b5688-114">左側のナビゲーションで、[ユーザー] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="b5688-114">In the left navigation, click **Users**.</span></span> 

2. <span data-ttu-id="b5688-115">一覧でユーザーを選択し、ページの上部にある **[編集** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b5688-115">Select a user in the list, and then click **Edit** at the top of the page.</span></span> 

3. <span data-ttu-id="b5688-116">[**電話会議**] の横の [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b5688-116">Next to **Audio Conferencing**, click **Edit**.</span></span>

4. <span data-ttu-id="b5688-117">[電話 **会議] ウィンドウで**、ダイヤルイン発信者を有効または無効に **できます。**</span><span class="sxs-lookup"><span data-stu-id="b5688-117">In the **Audio Conferencing** pane, enable or disable **Dial-in callers can be the first person in a meeting**.</span></span>
    
4. <span data-ttu-id="b5688-118">[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b5688-118">Click **Apply**.</span></span> 

<span data-ttu-id="b5688-119">**Windows PowerShell を使用する**</span><span class="sxs-lookup"><span data-stu-id="b5688-119">**Using Windows PowerShell**</span></span>
  
<span data-ttu-id="b5688-120">詳細については、[Microsoft Teams PowerShell のリファレンス](/powershell/module/teams/?view=teams-ps)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b5688-120">See the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>

## <a name="what-else-should-you-know"></a><span data-ttu-id="b5688-121">その他の情報</span><span class="sxs-lookup"><span data-stu-id="b5688-121">What else should you know?</span></span>

- <span data-ttu-id="b5688-122">PIN をリセットする場合は、「電話会議 PIN をリセット [する」を参照してください](reset-the-audio-conferencing-pin-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="b5688-122">If you want to reset the PIN, see [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin-in-teams.md).</span></span>
    
- <span data-ttu-id="b5688-123">匿名アクセス (会議を開始するために PIN を必要としない) が無効になっている場合:</span><span class="sxs-lookup"><span data-stu-id="b5688-123">If anonymous access, or not requiring a PIN to start a meeting, is disabled:</span></span>
    
  - <span data-ttu-id="b5688-124">会議が開始されていない場合 (会議にまだ誰もいない場合): 開催者の場合、発信者にメッセージが表示されます。「はい」と言った場合は、PIN の入力を求めるメッセージが表示され、PIN を入力すると、会議が開始され、ユーザーが会議に参加します。</span><span class="sxs-lookup"><span data-stu-id="b5688-124">If the meeting hasn't started (there's no one in the meeting yet): A caller will be prompted if he's the organizer; if he says yes, he'll be prompted for his PIN, and after he inputs the PIN, the meeting will start and the user will join the meeting.</span></span>
    
  - <span data-ttu-id="b5688-125">会議が既に開始されている場合 (他のユーザーが既に会議に参加している場合): 発信者に開催者の場合はメッセージが表示されません。PIN の入力を求めるメッセージは表示されません。会議が既に開始され、呼び出し元が会議に参加します。</span><span class="sxs-lookup"><span data-stu-id="b5688-125">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if he's the organizer and he'll never be prompted for the PIN; the meeting is already started, and the caller will join it.</span></span>
    
- <span data-ttu-id="b5688-126">匿名アクセス (会議を開始するために PIN を必要としない) が有効になっている場合:</span><span class="sxs-lookup"><span data-stu-id="b5688-126">If anonymous access, or not requiring a PIN to start a meeting, is enabled:</span></span>
    
  - <span data-ttu-id="b5688-127">会議が開始されていない場合 (まだ会議に誰もいない場合): 発信者に開催者の場合はメッセージが表示されません。PIN の入力を求めるメッセージは表示されません。</span><span class="sxs-lookup"><span data-stu-id="b5688-127">If the meeting hasn't started (there's no one in the meeting yet): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN.</span></span> <span data-ttu-id="b5688-128">開催者の設定がオフになっているため、会議が始まり、匿名の発信者が会議に参加します。</span><span class="sxs-lookup"><span data-stu-id="b5688-128">Because the setting of the organizer is set to off, the meeting will start and the anonymous callers will join the meeting.</span></span>
    
  - <span data-ttu-id="b5688-129">会議が既に開始されている場合 (他のユーザーが既に会議に参加している場合):発信者に開催者の場合はメッセージが表示されません。PIN の入力を求めるメッセージは表示されません。会議は既に開始され、発信者はその会議に参加します。</span><span class="sxs-lookup"><span data-stu-id="b5688-129">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN,;the meeting is already started, and the caller will join it.</span></span>
    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="b5688-130">Windows PowerShell の詳細情報</span><span class="sxs-lookup"><span data-stu-id="b5688-130">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="b5688-131">Windows PowerShellは、ユーザーの管理と、ユーザーが許可または許可されていない操作についてすべて行います。</span><span class="sxs-lookup"><span data-stu-id="b5688-131">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="b5688-132">このWindows PowerShell、1 つの管理Microsoft 365または Office 365 を管理し、複数のタスクを実行する場合に毎日の作業を簡略化できます。</span><span class="sxs-lookup"><span data-stu-id="b5688-132">With Windows PowerShell, you can manage Microsoft 365 or Office 365 by using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="b5688-133">Windows PowerShell の使用を開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b5688-133">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="b5688-134">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="b5688-134">Why you need to use Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="b5688-135">[アプリを使用してMicrosoft 365またはOffice 365を管理Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="b5688-135">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
<span data-ttu-id="b5688-136">Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](/powershell/module/teams/?view=teams-ps)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b5688-136">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="b5688-137">関連トピック</span><span class="sxs-lookup"><span data-stu-id="b5688-137">Related topics</span></span>

[<span data-ttu-id="b5688-138">電話会議を試用または購入するには、Microsoft 365またはOffice 365</span><span class="sxs-lookup"><span data-stu-id="b5688-138">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)