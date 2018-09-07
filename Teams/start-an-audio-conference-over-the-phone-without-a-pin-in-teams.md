---
title: マイクロソフトのチームで暗証番号 (pin) に電話で、オーディオ会議の開始します。
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
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
description: '有効にするか、チームの管理センターからミーティングへの参加からの匿名の呼び出しを無効にする方法を説明します。 '
ms.openlocfilehash: f85cd3e2ae0c1f87810f5b5312ba8bc9dc9d34c9
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23861044"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-microsoft-teams"></a><span data-ttu-id="104a4-103">マイクロソフトのチームで暗証番号 (pin) に電話で、オーディオ会議の開始します。</span><span class="sxs-lookup"><span data-stu-id="104a4-103">Start an Audio Conference over the phone without a PIN in Microsoft Teams</span></span>

<span data-ttu-id="104a4-104">マイクロソフトのチーム会議の開催者に会議が開始されていないために、音楽を聞いたり、会議のロビーで開催される会議にダイヤルインするユーザーに不満がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="104a4-104">It might be frustrating for users who dial in to a meeting to be held in the meeting's lobby listening to music because the Microsoft Teams meeting organizer hasn't started the meeting.</span></span> 
  
<span data-ttu-id="104a4-105">会議の開催者を呼び出す場合、会議出席依頼には、既定では、会議を開始するのには、暗証番号 (pin) が必要です。</span><span class="sxs-lookup"><span data-stu-id="104a4-105">If a meeting organizer calls in to the meeting, by default, a PIN is required to start a meeting.</span></span> <span data-ttu-id="104a4-106">できますを設定することをだれでも会議にダイヤルイン会議を開始するのには暗証番号 (pin) には求められません。</span><span class="sxs-lookup"><span data-stu-id="104a4-106">You can set it up so that anyone can dial in to a meeting and not be prompted for a PIN to start the meeting.</span></span> <span data-ttu-id="104a4-107">有効にするか、1 人のユーザーに対してこの設定を無効にするのには、管理センターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="104a4-107">You can use the admin center to enable or disable this setting for a single user.</span></span>
  
<span data-ttu-id="104a4-108">誰かマイクロソフトのチームのアプリケーションから会議が開始された場合、暗証番号 (pin) は会議の開催者のために必要はありません。</span><span class="sxs-lookup"><span data-stu-id="104a4-108">A PIN isn't required for the meeting organizer if someone has started the meeting from the Microsoft Teams app.</span></span> <span data-ttu-id="104a4-109">PIN が必要であるのは、会議の開催者が電話で自分の会議に参加する場合のみです。</span><span class="sxs-lookup"><span data-stu-id="104a4-109">A PIN is only required when a meeting organizer joins their meeting over a phone.</span></span> <span data-ttu-id="104a4-110">会議の暗証番号 (pin) は、**オーディオ会議**のライセンスが割り当てられている音声会議が有効になっていると、オーディオのユーザーに送信されます。</span><span class="sxs-lookup"><span data-stu-id="104a4-110">The PIN for meetings is sent to the audio user when they are assigned the **Audio Conferencing** license and are enabled for Audio Conferencing.</span></span> <span data-ttu-id="104a4-111">[オーディオ会議の情報を持つユーザーに電子メールを送信](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)し、[ユーザーが電話会議の設定を変更するときに自動的に送信される電子メール](emails-sent-to-users-when-their-settings-change-in-teams.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="104a4-111">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md) and [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change-in-teams.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a><span data-ttu-id="104a4-112">匿名の発信者の会議への参加を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="104a4-112">Enable or disable anonymous callers from joining a meeting</span></span>

<span data-ttu-id="104a4-113">![チーム ・ ロゴ ・ 30x30.png](media/teams-logo-30x30.png) **、マイクロソフトのチームとビジネス管理センターの Skype を使用します。**</span><span class="sxs-lookup"><span data-stu-id="104a4-113">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="104a4-114">左側のナビゲーションでは、**ユーザー**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="104a4-114">In the left navigation, click **Users**.</span></span> 

2. <span data-ttu-id="104a4-115">の一覧でユーザーを選択し、ページの上部にある**編集**を] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="104a4-115">Select a user in the list, and then click **Edit** at the top of the page.</span></span> 

3. <span data-ttu-id="104a4-116">**オーディオ会議**の横にある [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="104a4-116">Next to **Audio Conferencing**, click **Edit**.</span></span>

4. <span data-ttu-id="104a4-117">**オーディオ会議**のウィンドウでを有効にするまたは**認証されていない呼び出し元は、会議の最初の人**を無効にします。</span><span class="sxs-lookup"><span data-stu-id="104a4-117">In the **Audio Conferencing** pane, enable or disable **Unauthenticated callers can be the first person in a meeting**.</span></span>
    
4. <span data-ttu-id="104a4-118">[ **保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="104a4-118">Click **Save**.</span></span> 

<span data-ttu-id="104a4-119">**Windows Powershell を使用します。**</span><span class="sxs-lookup"><span data-stu-id="104a4-119">**Using Windows Powershell**</span></span>
  
<span data-ttu-id="104a4-120">詳細については[マイクロソフト チームの PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="104a4-120">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>

## <a name="what-else-should-you-know"></a><span data-ttu-id="104a4-121">その他の情報</span><span class="sxs-lookup"><span data-stu-id="104a4-121">What else should you know?</span></span>

- <span data-ttu-id="104a4-122">PIN をリセットする場合は、[オーディオ会議の PIN のリセット](reset-the-audio-conferencing-pin-in-teams.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="104a4-122">If you want to reset the PIN, see [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin-in-teams.md).</span></span>
    
- <span data-ttu-id="104a4-123">匿名アクセス、または、会議を開始するのには暗証番号 (pin) を必要としない] がオンの場合</span><span class="sxs-lookup"><span data-stu-id="104a4-123">If anonymous access, or not requiring a PIN to start a meeting, is enabled:</span></span>
    
  - <span data-ttu-id="104a4-124">会議が開始されていない場合 (は誰もまだ会議で): 彼は、開催者の場合、呼び出し元が求められます、PIN のよう求められますその場合、[はい] と PIN を入力した後、ミーティングを開始し、ユーザーがミーティングに参加します。</span><span class="sxs-lookup"><span data-stu-id="104a4-124">If the meeting hasn't started (there's no one in the meeting yet): A caller will be prompted if he's the organizer; if he says yes, he'll be prompted for his PIN, and after he inputs the PIN, the meeting will start and the user will join the meeting.</span></span>
    
  - <span data-ttu-id="104a4-125">会議が既に開始されている場合 (他のユーザーが既に会議): 開催者は、彼とはしないよう求められます暗証番号 (pin) の場合、呼び出し元は要求されません。会議は既に開始されていると、呼び出し元に参加します。</span><span class="sxs-lookup"><span data-stu-id="104a4-125">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if he's the organizer and he'll never be prompted for the PIN; the meeting is already started, and the caller will join it.</span></span>
    
- <span data-ttu-id="104a4-126">匿名アクセス、または、会議を開始するのには暗証番号 (pin) を必要としないが無効の場合</span><span class="sxs-lookup"><span data-stu-id="104a4-126">If anonymous access, or not requiring a PIN to start a meeting, is disabled:</span></span>
    
  - <span data-ttu-id="104a4-127">会議が開始されていない場合 (は誰もまだ会議で): 開催者は、彼女と彼女がするメッセージは表示されません、暗証番号 (pin) の場合、呼び出し元は要求されません。</span><span class="sxs-lookup"><span data-stu-id="104a4-127">If the meeting hasn't started (there's no one in the meeting yet): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN.</span></span> <span data-ttu-id="104a4-128">開催者の設定がオフになっているため、会議が始まり、匿名の発信者が会議に参加します。</span><span class="sxs-lookup"><span data-stu-id="104a4-128">Because the setting of the organizer is set to off, the meeting will start and the anonymous callers will join the meeting.</span></span>
    
  - <span data-ttu-id="104a4-129">会議が既に開始されている場合 (他のユーザーが既に会議): 場合は、開催者は、彼女と暗証番号 (pin) の彼女を求められますことはありませんが、呼び出し元は要求されません; 会議は既に開始されていると、呼び出し元に参加します。</span><span class="sxs-lookup"><span data-stu-id="104a4-129">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN,;the meeting is already started, and the caller will join it.</span></span>
    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="104a4-130">Windows PowerShell の詳細情報</span><span class="sxs-lookup"><span data-stu-id="104a4-130">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="104a4-p104">Windows PowerShell は、ユーザーと、ユーザーに許可されていることと許可されていないことを管理するためにあるということです。Windows PowerShell があれば、一元管理を使用して Office 365 を管理し、複数のタスクを抱えているときに、日常の仕事を簡素化することができます。Windows PowerShell を開始するには、これらのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="104a4-p104">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="104a4-134">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="104a4-134">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="104a4-135">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="104a4-135">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="104a4-136">Windows PowerShell の詳細については、[マイクロソフト チームの PowerShell の参照](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)の詳細についてを参照してください。</span><span class="sxs-lookup"><span data-stu-id="104a4-136">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="104a4-137">このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「Skype for Business Online 用 Windows PowerShell モジュール」からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="104a4-137">Related topics</span></span>

[<span data-ttu-id="104a4-138">Office 365 での電話会議を使用または購入する</span><span class="sxs-lookup"><span data-stu-id="104a4-138">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
