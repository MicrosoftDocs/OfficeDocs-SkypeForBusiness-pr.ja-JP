---
title: Microsoft Teams で PIN を使用せずに電話で電話会議を開始する
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
- Teams_ITAdmin_Help
- M365-collaboration
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: '匿名の発信者が Teams 管理センターから会議に参加することを有効または無効にする方法を説明します。 '
ms.openlocfilehash: 5f2dbd84b71058e75b710f37994e41c9adb488ef
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32227096"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-microsoft-teams"></a><span data-ttu-id="80d83-103">Microsoft Teams で PIN を使用せずに電話で電話会議を開始する</span><span class="sxs-lookup"><span data-stu-id="80d83-103">Start an Audio Conference over the phone without a PIN in Microsoft Teams</span></span>

<span data-ttu-id="80d83-104">ユーザーが会議にダイヤルインしたのに、Microsoft Teams 会議の開催者が会議を開始していないため、保留音の音楽を聞きながら会議のロビーで待たされると、不快な思いをしてしまう可能性があります。</span><span class="sxs-lookup"><span data-stu-id="80d83-104">It might be frustrating for users who dial in to a meeting to be held in the meeting's lobby listening to music because the Microsoft Teams meeting organizer hasn't started the meeting.</span></span> 
  
<span data-ttu-id="80d83-105">会議の開催者が会議にダイヤルインする場合、既定では、会議を開始するために PIN が必要です。</span><span class="sxs-lookup"><span data-stu-id="80d83-105">If a meeting organizer calls in to the meeting, by default, a PIN is required to start a meeting.</span></span> <span data-ttu-id="80d83-106">どのユーザーが会議にダイヤルインしても会議の開始で PIN を求められることがないように、会議を設定することができます。</span><span class="sxs-lookup"><span data-stu-id="80d83-106">You can set it up so that anyone can dial in to a meeting and not be prompted for a PIN to start the meeting.</span></span> <span data-ttu-id="80d83-107">管理センターを使用して、この設定を 1 人のユーザーに対して有効または無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="80d83-107">You can use the admin center to enable or disable this setting for a single user.</span></span>
  
<span data-ttu-id="80d83-108">あるユーザーが Microsoft Teams アプリから会議を開始した場合、会議の開催者に PIN が要求されることはありません。</span><span class="sxs-lookup"><span data-stu-id="80d83-108">A PIN isn't required for the meeting organizer if someone has started the meeting from the Microsoft Teams app.</span></span> <span data-ttu-id="80d83-109">PIN が必要になるのは、会議の開催者が電話で自分の会議に参加する場合のみです。</span><span class="sxs-lookup"><span data-stu-id="80d83-109">A PIN is only required when a meeting organizer joins their meeting over a phone.</span></span> <span data-ttu-id="80d83-110">ユーザーに**電話会議**ライセンスが割り当てられているか、ユーザーが電話会議会議で有効である場合、会議の PIN がその電話会議ユーザーに送信されます。</span><span class="sxs-lookup"><span data-stu-id="80d83-110">The PIN for meetings is sent to the audio user when they are assigned the **Audio Conferencing** license and are enabled for Audio Conferencing.</span></span> <span data-ttu-id="80d83-111">「[電話会議の情報が記載されたメールをユーザーに送信する](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)」および「[電話会議の設定が変更されたときにユーザーに自動的に送信されるメール](emails-sent-to-users-when-their-settings-change-in-teams.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="80d83-111">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md) and [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change-in-teams.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a><span data-ttu-id="80d83-112">匿名の発信者の会議への参加を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="80d83-112">Enable or disable anonymous callers from joining a meeting</span></span>

<span data-ttu-id="80d83-113">![チーム ・ ロゴ ・ 30x30.png](media/teams-logo-30x30.png) **、マイクロソフトのチーム管理センターを使用して**</span><span class="sxs-lookup"><span data-stu-id="80d83-113">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="80d83-114">左側のナビゲーションで [**ユーザー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="80d83-114">In the left navigation, click **Users**.</span></span> 

2. <span data-ttu-id="80d83-115">リスト内でユーザーを選択し、ページ上部にある [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="80d83-115">Select a user in the list, and then click **Edit** at the top of the page.</span></span> 

3. <span data-ttu-id="80d83-116">[**電話会議**] の隣で、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="80d83-116">Next to **Audio Conferencing**, click **Edit**.</span></span>

4. <span data-ttu-id="80d83-117">[**電話会議**] ペインで、[**Unauthenticated callers can be the first person in a meeting (認証されてない発信者を会議の最初のユーザーにすることができる)**] を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="80d83-117">In the **Audio Conferencing** pane, enable or disable **Unauthenticated callers can be the first person in a meeting**.</span></span>
    
4. <span data-ttu-id="80d83-118">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="80d83-118">Click **Save**.</span></span> 

<span data-ttu-id="80d83-119">**Windows PowerShell を使用する**</span><span class="sxs-lookup"><span data-stu-id="80d83-119">**Using Windows Powershell**</span></span>
  
<span data-ttu-id="80d83-120">詳細については、[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="80d83-120">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>

## <a name="what-else-should-you-know"></a><span data-ttu-id="80d83-121">その他の情報</span><span class="sxs-lookup"><span data-stu-id="80d83-121">What else should you know?</span></span>

- <span data-ttu-id="80d83-122">PIN をリセットする必要がある場合は、「[電話会議の PIN をリセットする](reset-the-audio-conferencing-pin-in-teams.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="80d83-122">If you want to reset the PIN, see [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin-in-teams.md).</span></span>
    
- <span data-ttu-id="80d83-123">匿名アクセスが有効、または会議の開始に PIN が必要でない設定になっている場合:</span><span class="sxs-lookup"><span data-stu-id="80d83-123">If anonymous access, or not requiring a PIN to start a meeting, is enabled:</span></span>
    
  - <span data-ttu-id="80d83-124">会議がまだ開始していない場合 (会議にまだ誰もいない場合): 発信者には開催者であるかどうかを確認するメッセージが表示されます。発信者が「はい」と答えると、PIN の入力を求められます。PIN を入力した後、会議が始まり、そのユーザーが会議に参加します。</span><span class="sxs-lookup"><span data-stu-id="80d83-124">If the meeting hasn't started (there's no one in the meeting yet): A caller will be prompted if he's the organizer; if he says yes, he'll be prompted for his PIN, and after he inputs the PIN, the meeting will start and the user will join the meeting.</span></span>
    
  - <span data-ttu-id="80d83-125">会議が既に開始している場合 (会議に既に他のユーザーがいる場合): 発信者に開催者であるかどうかを確認するメッセージが表示されることはなく、PIN の入力も求められません。会議は既に始まっていて、発信者はその会議に参加します。</span><span class="sxs-lookup"><span data-stu-id="80d83-125">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if he's the organizer and he'll never be prompted for the PIN; the meeting is already started, and the caller will join it.</span></span>
    
- <span data-ttu-id="80d83-126">匿名アクセスが無効、または会議の開始に PIN が必要な設定になっている場合:</span><span class="sxs-lookup"><span data-stu-id="80d83-126">If anonymous access, or not requiring a PIN to start a meeting, is disabled:</span></span>
    
  - <span data-ttu-id="80d83-127">会議がまだ開始していない場合 (会議にまだ誰もいない場合): 発信者に開催者であるかどうかを確認するメッセージが表示されることはなく、PIN の入力も求められません。</span><span class="sxs-lookup"><span data-stu-id="80d83-127">If the meeting hasn't started (there's no one in the meeting yet): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN.</span></span> <span data-ttu-id="80d83-128">開催者の設定がオフになっているため、会議が始まり、匿名の発信者が会議に参加します。</span><span class="sxs-lookup"><span data-stu-id="80d83-128">Because the setting of the organizer is set to off, the meeting will start and the anonymous callers will join the meeting.</span></span>
    
  - <span data-ttu-id="80d83-129">会議が既に開始している場合 (会議に既に他のユーザーがいる場合): 発信者に開催者であるかどうかを確認するメッセージが表示されることはなく、PIN の入力も求められません。会議は既に始まっていて、発信者はその会議に参加します。</span><span class="sxs-lookup"><span data-stu-id="80d83-129">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN,;the meeting is already started, and the caller will join it.</span></span>
    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="80d83-130">Windows PowerShell の詳細情報</span><span class="sxs-lookup"><span data-stu-id="80d83-130">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="80d83-p104">Windows PowerShell は、ユーザーと、ユーザーに許可されていることと許可されていないことを管理するためにあるということです。Windows PowerShell があれば、一元管理を使用して Office 365 を管理し、複数のタスクを抱えているときに、日常の仕事を簡素化することができます。Windows PowerShell を開始するには、これらのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="80d83-p104">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="80d83-134">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="80d83-134">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="80d83-135">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="80d83-135">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="80d83-136">Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="80d83-136">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="80d83-137">関連トピック</span><span class="sxs-lookup"><span data-stu-id="80d83-137">Related topics</span></span>

[<span data-ttu-id="80d83-138">Office 365 での電話会議を使用または購入する</span><span class="sxs-lookup"><span data-stu-id="80d83-138">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
