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
description: 'チーム管理センターから、匿名の発信者が会議に参加することを有効または無効にする方法について説明します。 '
ms.openlocfilehash: 87588bc8edfcc4d50b5589339f92f56829ec38ef
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837917"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-microsoft-teams"></a><span data-ttu-id="0ffb1-103">Microsoft Teams で PIN を使用せずに電話で電話会議を開始する</span><span class="sxs-lookup"><span data-stu-id="0ffb1-103">Start an Audio Conference over the phone without a PIN in Microsoft Teams</span></span>

<span data-ttu-id="0ffb1-104">Microsoft Teams の会議の開催者が会議を開始していないために、会議にダイヤルインして音楽のロビーを待っているユーザーにとっては、ユーザーにとっては不快な場合があります。</span><span class="sxs-lookup"><span data-stu-id="0ffb1-104">It might be frustrating for users who dial in to a meeting to be held in the meeting's lobby listening to music because the Microsoft Teams meeting organizer hasn't started the meeting.</span></span> 
  
<span data-ttu-id="0ffb1-105">会議の開催者が会議にコールインする場合、既定では、会議を開始するために PIN が必要になります。</span><span class="sxs-lookup"><span data-stu-id="0ffb1-105">If a meeting organizer calls in to the meeting, by default, a PIN is required to start a meeting.</span></span> <span data-ttu-id="0ffb1-106">すべてのユーザーが会議にダイヤルインできるように設定することができます。また、会議を開始するために PIN の入力を求められることはありません。</span><span class="sxs-lookup"><span data-stu-id="0ffb1-106">You can set it up so that anyone can dial in to a meeting and not be prompted for a PIN to start the meeting.</span></span> <span data-ttu-id="0ffb1-107">管理センターを使用して、1人のユーザーに対してこの設定を有効または無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="0ffb1-107">You can use the admin center to enable or disable this setting for a single user.</span></span>
  
<span data-ttu-id="0ffb1-108">他のユーザーが Microsoft Teams アプリから会議を開始した場合、会議の開催者は PIN を指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="0ffb1-108">A PIN isn't required for the meeting organizer if someone has started the meeting from the Microsoft Teams app.</span></span> <span data-ttu-id="0ffb1-109">PIN が必要であるのは、会議の開催者が電話で自分の会議に参加する場合のみです。</span><span class="sxs-lookup"><span data-stu-id="0ffb1-109">A PIN is only required when a meeting organizer joins their meeting over a phone.</span></span> <span data-ttu-id="0ffb1-110">会議の PIN は、電話**会議**ライセンスが割り当てられており、電話会議用に有効になっている場合に、音声ユーザーに送信されます。</span><span class="sxs-lookup"><span data-stu-id="0ffb1-110">The PIN for meetings is sent to the audio user when they are assigned the **Audio Conferencing** license and are enabled for Audio Conferencing.</span></span> <span data-ttu-id="0ffb1-111">「電話会議の[設定が変更されたときにユーザーに自動的に送信される](emails-sent-to-users-when-their-settings-change-in-teams.md)[電話会議情報とメールをユーザーに送信](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0ffb1-111">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md) and [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change-in-teams.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a><span data-ttu-id="0ffb1-112">匿名の発信者の会議への参加を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="0ffb1-112">Enable or disable anonymous callers from joining a meeting</span></span>

<span data-ttu-id="0ffb1-113">![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターの使用**</span><span class="sxs-lookup"><span data-stu-id="0ffb1-113">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="0ffb1-114">左側のナビゲーションで [**ユーザー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0ffb1-114">In the left navigation, click **Users**.</span></span> 

2. <span data-ttu-id="0ffb1-115">リストでユーザーを選択し、ページの上部にある [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0ffb1-115">Select a user in the list, and then click **Edit** at the top of the page.</span></span> 

3. <span data-ttu-id="0ffb1-116">[**電話会議**] の横の [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0ffb1-116">Next to **Audio Conferencing**, click **Edit**.</span></span>

4. <span data-ttu-id="0ffb1-117">[**電話会議**] ウィンドウで、ダイヤルインの発信者を有効または無効にするには、**会議の最初の人になることができ**ます。</span><span class="sxs-lookup"><span data-stu-id="0ffb1-117">In the **Audio Conferencing** pane, enable or disable **Dial-in callers can be the first person in a meeting**.</span></span>
    
4. <span data-ttu-id="0ffb1-118">[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0ffb1-118">Click **Apply**.</span></span> 

<span data-ttu-id="0ffb1-119">**Windows PowerShell を使用する**</span><span class="sxs-lookup"><span data-stu-id="0ffb1-119">**Using Windows PowerShell**</span></span>
  
<span data-ttu-id="0ffb1-120">詳細については、[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0ffb1-120">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>

## <a name="what-else-should-you-know"></a><span data-ttu-id="0ffb1-121">その他の情報</span><span class="sxs-lookup"><span data-stu-id="0ffb1-121">What else should you know?</span></span>

- <span data-ttu-id="0ffb1-122">PIN をリセットする場合は、「[電話会議の pin をリセット](reset-the-audio-conferencing-pin-in-teams.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0ffb1-122">If you want to reset the PIN, see [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin-in-teams.md).</span></span>
    
- <span data-ttu-id="0ffb1-123">匿名アクセスが許可されている場合、または会議の開始に PIN が必要な場合は無効になります。</span><span class="sxs-lookup"><span data-stu-id="0ffb1-123">If anonymous access, or not requiring a PIN to start a meeting, is disabled:</span></span>
    
  - <span data-ttu-id="0ffb1-124">会議が開始されていない (会議にまだ参加していない) 場合: 発信者が開催者であるかどうかを確認するメッセージが表示されます。「はい」というメッセージが表示されると、PIN の入力が求められます。 PIN を入力すると、会議が開始され、ユーザーが会議に参加します。</span><span class="sxs-lookup"><span data-stu-id="0ffb1-124">If the meeting hasn't started (there's no one in the meeting yet): A caller will be prompted if he's the organizer; if he says yes, he'll be prompted for his PIN, and after he inputs the PIN, the meeting will start and the user will join the meeting.</span></span>
    
  - <span data-ttu-id="0ffb1-125">会議が既に始まっている場合 (他のユーザーが既に会議に参加している場合): 発信者は開催者であるかどうかを確認するメッセージは表示されず、PIN の入力を求められることはありません。会議が既に始まっていて、発信者が会議に参加します。</span><span class="sxs-lookup"><span data-stu-id="0ffb1-125">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if he's the organizer and he'll never be prompted for the PIN; the meeting is already started, and the caller will join it.</span></span>
    
- <span data-ttu-id="0ffb1-126">匿名アクセスが許可されている場合、または会議の開始に PIN が必要ではない場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="0ffb1-126">If anonymous access, or not requiring a PIN to start a meeting, is enabled:</span></span>
    
  - <span data-ttu-id="0ffb1-127">会議が開始されていない (会議にまだ参加していない) 場合: 発信者が開催者であるかどうかを確認するメッセージは表示されません。 PIN の入力を求められることはありません。</span><span class="sxs-lookup"><span data-stu-id="0ffb1-127">If the meeting hasn't started (there's no one in the meeting yet): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN.</span></span> <span data-ttu-id="0ffb1-128">開催者の設定がオフになっているため、会議が始まり、匿名の発信者が会議に参加します。</span><span class="sxs-lookup"><span data-stu-id="0ffb1-128">Because the setting of the organizer is set to off, the meeting will start and the anonymous callers will join the meeting.</span></span>
    
  - <span data-ttu-id="0ffb1-129">会議が既に開始されている場合 (他のユーザーが既に会議に参加している場合): 発信者であるかどうかを確認するメッセージは表示されません。会議は既に始まっていて、発信者はその会議に参加します。</span><span class="sxs-lookup"><span data-stu-id="0ffb1-129">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN,;the meeting is already started, and the caller will join it.</span></span>
    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="0ffb1-130">Windows PowerShell の詳細情報</span><span class="sxs-lookup"><span data-stu-id="0ffb1-130">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="0ffb1-p104">Windows PowerShell で行うのは、ユーザーを管理し、ユーザーに何を許可して何を禁止するかを管理することです。Windows PowerShell を利用すると、Office 365 の管理を 1 か所で行うことができるので、複数のタスクを担当する管理者の日常業務を単純化できます。Windows PowerShell の使用を開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0ffb1-p104">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="0ffb1-134">Office 365 PowerShell を使用する必要がある理由</span><span class="sxs-lookup"><span data-stu-id="0ffb1-134">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="0ffb1-135">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="0ffb1-135">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="0ffb1-136">Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0ffb1-136">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="0ffb1-137">関連トピック</span><span class="sxs-lookup"><span data-stu-id="0ffb1-137">Related topics</span></span>

[<span data-ttu-id="0ffb1-138">Office 365 での電話会議を試用または購入する</span><span class="sxs-lookup"><span data-stu-id="0ffb1-138">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
