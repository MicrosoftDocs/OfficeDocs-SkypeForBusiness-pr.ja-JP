---
title: Skype for Business Online で PIN を使用せずに電話で電話会議を開始する
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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: '匿名の発信者による Skype for Business 管理センターからの会議への参加や PowerShell スクリプトの使用を有効または無効にする方法を説明します。 '
ms.openlocfilehash: af62ed29ed2bbe835ab811651152b231a85caaf8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34302772"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-skype-for-business-online"></a><span data-ttu-id="191d6-103">Skype for Business Online で PIN を使用せずに電話で電話会議を開始する</span><span class="sxs-lookup"><span data-stu-id="191d6-103">Start an Audio Conference over the phone without a PIN in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="191d6-104">Microsoft Teams で PIN を使用せずに電話会議を開始する場合の詳細については、「[Microsoft Teams で PIN を使用せずに 電話で電話会議を開始する](/MicrosoftTeams/start-an-audio-conference-over-the-phone-without-a-pin-in-teams)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="191d6-104">For information about starting an Audio Conference without a PIN in Microsoft Teams, see [Start an Audio Conference over the phone without a PIN  in Microsoft Teams](/MicrosoftTeams/start-an-audio-conference-over-the-phone-without-a-pin-in-teams).</span></span>

<span data-ttu-id="191d6-105">会議にダイヤルインしても、Skype for Business 会議の開催者が会議を開始していないために、音楽を聞く会議のロビーで保留になっているユーザーにとっては不快な場合があります。</span><span class="sxs-lookup"><span data-stu-id="191d6-105">It might be frustrating for users who dial in to a meeting to be held in the meeting's lobby listening to music because the Skype for Business meeting organizer hasn't started the meeting.</span></span> 
  
<span data-ttu-id="191d6-106">会議の開催者が会議にコールインする場合、既定では、会議を開始するために PIN が必要になります。</span><span class="sxs-lookup"><span data-stu-id="191d6-106">If a meeting organizer calls in to the meeting, by default, a PIN is required to start a meeting.</span></span> <span data-ttu-id="191d6-107">すべてのユーザーが会議にダイヤルインできるように設定することができます。また、会議を開始するために PIN の入力を求められることはありません。</span><span class="sxs-lookup"><span data-stu-id="191d6-107">You can set it up so that anyone can dial in to a meeting and not be prompted for a PIN to start the meeting.</span></span> <span data-ttu-id="191d6-108">Skype for Business 管理センターを使用すると、この設定を 1 人のユーザーに対して有効または無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="191d6-108">You can use the Skype for Business admin center to enable or disable this setting for a single user.</span></span>
  
<span data-ttu-id="191d6-109">他のユーザーが Skype for Business アプリから会議を開始した場合、会議の開催者に PIN は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="191d6-109">A PIN isn't required for the meeting organizer if someone has started the meeting from the Skype for Business app.</span></span> <span data-ttu-id="191d6-110">PIN が必要であるのは、会議の開催者が電話で自分の会議に参加する場合のみです。</span><span class="sxs-lookup"><span data-stu-id="191d6-110">A PIN is only required when a meeting organizer joins their meeting over a phone.</span></span> <span data-ttu-id="191d6-111">会議の PIN は、電話**会議**ライセンスが割り当てられており、電話会議用に有効になっている場合に、音声ユーザーに送信されます。</span><span class="sxs-lookup"><span data-stu-id="191d6-111">The PIN for meetings is sent to the audio user when they are assigned the **Audio Conferencing** license and are enabled for Audio Conferencing.</span></span> <span data-ttu-id="191d6-112">「電話会議の[設定が変更されたときにユーザーに自動的に送信される](emails-sent-to-users-when-their-settings-change.md)[電話会議情報とメールをユーザーに送信](send-an-email-to-a-user-with-their-dial-in-information.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="191d6-112">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md) and [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a><span data-ttu-id="191d6-113">匿名の発信者の会議への参加を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="191d6-113">Enable or disable anonymous callers from joining a meeting</span></span>
    
1. <span data-ttu-id="191d6-114">**Skype for business 管理センター**の左側のナビゲーションで、[**電話会議** > **ユーザー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="191d6-114">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**.</span></span> 
    
2. <span data-ttu-id="191d6-115">リストでユーザーを選び、操作ウィンドウで [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="191d6-115">In the list, select the user and in the Action pane click **Edit**.</span></span> 
    
3. <span data-ttu-id="191d6-116">ユーザーのプロパティページの [**会議オプション**] で、[**認証されていない発信者が会議の最初のユーザーになることを許可する] をオンまたはオフにします。満たされていない場合は、認証されたユーザーが参加するまでロビーで待機**します。</span><span class="sxs-lookup"><span data-stu-id="191d6-116">On the user's properties page, under **Meeting options**, select or clear **Allow unauthenticated callers to be the first people in a meeting. If not, then they will wait in the lobby until an authenticated user joins**.</span></span>
    
4. <span data-ttu-id="191d6-117">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="191d6-117">Click **Save**.</span></span> 


    
 <span data-ttu-id="191d6-118">**Windows Powershell を使用する**</span><span class="sxs-lookup"><span data-stu-id="191d6-118">**Using Windows Powershell**</span></span>
  
- <span data-ttu-id="191d6-119">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="191d6-119">Run the following:</span></span> 
    
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true | $false
  ```

## <a name="what-else-should-you-know"></a><span data-ttu-id="191d6-120">その他の情報</span><span class="sxs-lookup"><span data-stu-id="191d6-120">What else should you know?</span></span>

- <span data-ttu-id="191d6-121">PIN をリセットする場合は、「[電話会議の pin をリセット](reset-the-audio-conferencing-pin.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="191d6-121">If you want to reset the PIN, see [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin.md).</span></span>
    
- <span data-ttu-id="191d6-122">匿名アクセスが許可されている場合、または会議の開始に PIN が必要ではない場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="191d6-122">If anonymous access, or not requiring a PIN to start a meeting, is enabled:</span></span>
    
  - <span data-ttu-id="191d6-123">会議が開始されていない (会議にまだ参加していない) 場合: 発信者が開催者であるかどうかを確認するメッセージが表示されます。「はい」というメッセージが表示されると、PIN の入力が求められます。 PIN を入力すると、会議が開始され、ユーザーが会議に参加します。</span><span class="sxs-lookup"><span data-stu-id="191d6-123">If the meeting hasn't started (there's no one in the meeting yet): A caller will be prompted if he's the organizer; if he says yes, he'll be prompted for his PIN, and after he inputs the PIN, the meeting will start and the user will join the meeting.</span></span>
    
  - <span data-ttu-id="191d6-124">会議が既に始まっている場合 (他のユーザーが既に会議に参加している場合): 発信者は開催者であるかどうかを確認するメッセージは表示されず、PIN の入力を求められることはありません。会議が既に始まっていて、発信者が会議に参加します。</span><span class="sxs-lookup"><span data-stu-id="191d6-124">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if he's the organizer and he'll never be prompted for the PIN; the meeting is already started, and the caller will join it.</span></span>
    
- <span data-ttu-id="191d6-125">匿名アクセスが許可されている場合、または会議の開始に PIN が必要な場合は無効になります。</span><span class="sxs-lookup"><span data-stu-id="191d6-125">If anonymous access, or not requiring a PIN to start a meeting, is disabled:</span></span>
    
  - <span data-ttu-id="191d6-126">会議が開始されていない (会議にまだ参加していない) 場合: 発信者が開催者であるかどうかを確認するメッセージは表示されません。 PIN の入力を求められることはありません。</span><span class="sxs-lookup"><span data-stu-id="191d6-126">If the meeting hasn't started (there's no one in the meeting yet): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN.</span></span> <span data-ttu-id="191d6-127">開催者の設定がオフになっているため、会議が始まり、匿名の発信者が会議に参加します。</span><span class="sxs-lookup"><span data-stu-id="191d6-127">Because the setting of the organizer is set to off, the meeting will start and the anonymous callers will join the meeting.</span></span>
    
  - <span data-ttu-id="191d6-128">会議が既に開始されている場合 (他のユーザーが既に会議に参加している場合): 発信者であるかどうかを確認するメッセージは表示されません。会議は既に始まっていて、発信者はその会議に参加します。</span><span class="sxs-lookup"><span data-stu-id="191d6-128">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN,;the meeting is already started, and the caller will join it.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="191d6-129">Windows PowerShell での管理方法について</span><span class="sxs-lookup"><span data-stu-id="191d6-129">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="191d6-130">時間を節約したり、複数のユーザーに対してこの動作を自動化したりするには、[Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) コマンドレットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="191d6-130">To save time or automate this for more than one user, you can use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) cmdlet.</span></span>
    
- <span data-ttu-id="191d6-p104">Windows PowerShell の場合、Skype for Business Online はユーザーの管理と、ユーザーが許可されている操作や許可されていない操作の管理に使います。Windows PowerShell により、単一の管理ポイントを使って Office 365 を管理でき、複数の作業を実行する必要があるときに日常業務を合理化できます。Windows PowerShell を使い始めるには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="191d6-p104">When it comes to Windows PowerShell, Skype for Business Online is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="191d6-134">Office 365 PowerShell を使用する必要がある理由</span><span class="sxs-lookup"><span data-stu-id="191d6-134">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="191d6-135">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="191d6-135">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="191d6-p105">多くのユーザーの設定を同時に変更するときなどは、Office 365 管理センターのみを使用するよりも、Windows PowerShell の方に、速度、わかりやすさ、生産性の点で多くのメリットがあります。</span><span class="sxs-lookup"><span data-stu-id="191d6-p105">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time. Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="191d6-138">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="191d6-138">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [<span data-ttu-id="191d6-139">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="191d6-139">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="191d6-140">Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行</span><span class="sxs-lookup"><span data-stu-id="191d6-140">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="191d6-p106">Skype for Business Online 用の Windows PowerShell モジュールがあれば、Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成できます。このモジュールは、64 ビット版のコンピューターでのみサポートされており、「[Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688)」の Microsoft ダウンロード センターからダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="191d6-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="191d6-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="191d6-143">Related topics</span></span>

[<span data-ttu-id="191d6-144">Office 365 での電話会議を試用または購入する</span><span class="sxs-lookup"><span data-stu-id="191d6-144">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
