---
title: Microsoft Teams で電話会議の PIN をリセットする
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 67866a47-89c1-4593-8766-3a68777e2be6
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
description: 'ピンについて何を理解する必要があり、マイクロソフトのチームでそれらをリセットする方法を紹介します。 '
ms.openlocfilehash: 56ea27ddf535f7ce23d5a25415b0a5921cfb2d6e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33912304"
---
# <a name="reset-the-audio-conferencing-pin-in-microsoft-teams"></a><span data-ttu-id="f163c-103">Microsoft Teams で電話会議の PIN をリセットする</span><span class="sxs-lookup"><span data-stu-id="f163c-103">Reset the Audio Conferencing PIN in Microsoft Teams</span></span>

<span data-ttu-id="f163c-104">PIN は、電話会議が有効になっているマイクロソフトのチームのユーザーごとに作成される番号のコードです。</span><span class="sxs-lookup"><span data-stu-id="f163c-104">A PIN is a code made up of numbers that is created for each Microsoft Teams user who is enabled for audio conferencing.</span></span> <span data-ttu-id="f163c-105">オーディオ会議のピンは、会議の開催者は、電話会議を開始することを許可することを識別するミーティングの開催者によって使用されます。</span><span class="sxs-lookup"><span data-stu-id="f163c-105">Audio conferencing PINs are used by meeting organizers to identify that they are the meeting organizer and allow them to start a meeting over the phone.</span></span> <span data-ttu-id="f163c-106">会議を開始するのには、マイクロソフトのチームのアプリケーションを使用する場合、暗証番号 (pin) は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="f163c-106">If they use the Microsoft Teams app to start the meeting, a PIN isn't required.</span></span> <span data-ttu-id="f163c-107">ユーザーが PIN を忘れたり、電話会議を有効になっていなかったときに送信された電子メールで見つけられないという場合は、管理者が自分の PIN をリセットできますか、独自の PIN をリセットすることができます。</span><span class="sxs-lookup"><span data-stu-id="f163c-107">If users forget their PIN and they can't find it in the email that was sent to them when they were enabled for audio conferencing, an administrator can reset their PIN, or they can reset their own PIN.</span></span>
  
<span data-ttu-id="f163c-108">マイクロソフト チームのアプリケーションまたは開催者参加させるとき、ユーザーの PIN と電話を使用して認証されたユーザーが参加するとき、会議を開始できます。</span><span class="sxs-lookup"><span data-stu-id="f163c-108">Meetings can be started when an authenticated user joins using the Microsoft Teams app or when the organizer joins with his or her PIN over the phone.</span></span> <span data-ttu-id="f163c-109">会議の開始に PIN が必要な場合、電話で参加するユーザーはロビーで待機し、会議が開始するまで保留音を聞くことになります。</span><span class="sxs-lookup"><span data-stu-id="f163c-109">When a meeting requires a PIN to start, users who join over the phone will be placed in the lobby and will listen to music on hold until the meeting starts.</span></span> <span data-ttu-id="f163c-110">会議の開催者が、電話で会議を開始するための PIN を要求しない場合、発信者は会議に参加しようとするときに PIN の提示を求められません。</span><span class="sxs-lookup"><span data-stu-id="f163c-110">If the organizer of a meeting doesn't require a PIN to start the meeting over the phone, then callers won't be asked to provide a PIN when they join the meeting.</span></span>

## <a name="reset-a-users-pin"></a><span data-ttu-id="f163c-111">ユーザーの PIN をリセットします。</span><span class="sxs-lookup"><span data-stu-id="f163c-111">Reset a user's PIN</span></span>

<span data-ttu-id="f163c-112">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Microsoft Teams 管理センターの使用**</span><span class="sxs-lookup"><span data-stu-id="f163c-112">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="f163c-113">左側のナビゲーションで、[**ユーザー**] をクリックしてから、空いているユーザーのリストからユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="f163c-113">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="f163c-114">[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f163c-114">Click **Edit**.</span></span>

3. <span data-ttu-id="f163c-115">**オーディオ会議**では、[ **PIN のリセット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f163c-115">Under **Audio Conferencing**, click **Reset PIN**.</span></span>

4. <span data-ttu-id="f163c-116">[**リセット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f163c-116">Click **Reset**.</span></span>
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-his-or-her-own-pin"></a><span data-ttu-id="f163c-117">ユーザーが自分の PIN のリセット</span><span class="sxs-lookup"><span data-stu-id="f163c-117">Have a user reset his or her own PIN</span></span>

1. <span data-ttu-id="f163c-118">ユーザーには、 [https://admin0m.online.lync.com/lscp/usp/pstnconferencing](https://admin0m.online.lync.com/lscp/usp/pstnconferencing)。</span><span class="sxs-lookup"><span data-stu-id="f163c-118">Have the user go to [https://admin0m.online.lync.com/lscp/usp/pstnconferencing](https://admin0m.online.lync.com/lscp/usp/pstnconferencing).</span></span>
2. <span data-ttu-id="f163c-119">**PIN のリセット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f163c-119">Click **Reset PIN**.</span></span> 


## <a name="what-else-should-you-know-about-pins"></a><span data-ttu-id="f163c-120">PIN について知っておくべきその他のこと</span><span class="sxs-lookup"><span data-stu-id="f163c-120">What else should you know about PINs?</span></span>

- <span data-ttu-id="f163c-121">セキュリティ保護のため、PIN のリセット時に PIN は 1 回だけ管理者に表示されます。</span><span class="sxs-lookup"><span data-stu-id="f163c-121">For security purposes, the PIN is only shown to an administrator on one time, when the PIN is reset.</span></span> <span data-ttu-id="f163c-122">暗証番号 (pin) は、管理者がリセットされますが後の暗証番号 (pin) が表示されます。。</span><span class="sxs-lookup"><span data-stu-id="f163c-122">After the PIN is reset by an administrator, the PIN will be listed as \*\*\*\*\*\*\*\*\*\*\*.</span></span>
    
- <span data-ttu-id="f163c-123">デフォルトで有効化は自動的にユーザーに電子メールを送信して、ユーザー音声会議や、PIN をリセットする場合は有効にしている場合、PIN の電子メールが送信されます。</span><span class="sxs-lookup"><span data-stu-id="f163c-123">Automatically sending emails to users is enabled by default, and users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset.</span></span> <span data-ttu-id="f163c-124">自動的に無効にした場合電子メールを送信するユーザーに PIN リセットの電子メールを送信しないユーザーに暗証番号 (pin) の情報を手動で送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f163c-124">But if you have disabled automatically sending emails, a PIN reset email won't be sent to a user and you will have to manually send the PIN information to the user.</span></span>
    
- <span data-ttu-id="f163c-p105">会議が始まると、ロビー内のすべてのユーザーは自動的にその会議に参加します。 たとえば、会議が始まる前に 2 人の参加者が会議に参加しようとすると、ロビーで待って保留音を聞くことになります。会議の開催者が自分の PIN を使用して電話で参加すると、会議が始まり、ロビーにいる参加者が会議に参加します。</span><span class="sxs-lookup"><span data-stu-id="f163c-p105">When a meeting starts, all of the users in the lobby will automatically join it. For example, if two participants try to join a meeting before it has been started, they will be put in the lobby and will listen to music on hold, and when the meeting organizer joins using his PIN via phone, the meeting will start and the participants in the lobby will join the meeting.</span></span>
    
- <span data-ttu-id="f163c-127">既定の設定では、匿名の呼び出しを開始するための会議を許可しないようにします。</span><span class="sxs-lookup"><span data-stu-id="f163c-127">The default setting is to not allow a meeting to be started by anonymous callers.</span></span>
    
- <span data-ttu-id="f163c-128">オーディオ会議のユーザーを有効にすると、既定で送信される会議の情報と PIN を含む電子メール。</span><span class="sxs-lookup"><span data-stu-id="f163c-128">When you enable a user for audio conferencing, by default they are sent emails that include conferencing information and their PIN.</span></span> <span data-ttu-id="f163c-129">ユーザーは PIN をリセットすると、新しい暗証番号 (pin) はでは、プライマリ SMTP アドレス (エイリアス)、ユーザーに設定されている電子メールのユーザーに送信されますので、Office 365 のメールボックスに必要です。</span><span class="sxs-lookup"><span data-stu-id="f163c-129">The user must have an Office 365 mailbox, because when a PIN is reset, a new PIN will be sent to the user in email to their primary SMTP address (alias) that is set for the user.</span></span>
    
- <span data-ttu-id="f163c-130">オーディオ会議を設定するときは、組織内のピンに必要な数字を設定します。</span><span class="sxs-lookup"><span data-stu-id="f163c-130">When you set up audio conferencing, you set the digits that are required for the PINs in your organization.</span></span> <span data-ttu-id="f163c-131">ピンは 12 桁、4 - デフォルトは 5 です。</span><span class="sxs-lookup"><span data-stu-id="f163c-131">PINs can be from 4 to 12 digits - the default is 5.</span></span> <span data-ttu-id="f163c-132">暗証番号 (pin) の長さの設定を変更すると、設定は、新しく生成されたピンの位置にのみ適用し、オーディオ会議を有効になっている既存のユーザーの暗証番号 (pin) の設定に適用されていません。</span><span class="sxs-lookup"><span data-stu-id="f163c-132">If you change the PIN length setting, the setting is only applied on newly generated PINs and isn't applied to the PIN setting for existing users that are enabled for audio conferencing.</span></span> <span data-ttu-id="f163c-133">[オーディオ会議の会議の暗証番号 (pin) の長さの設定](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f163c-133">See [Set the length of the PIN for Audio Conferencing meetings](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md).</span></span>
    
- <span data-ttu-id="f163c-134">既定で電子メールは、ユーザーの Office 365 のプライマリ SMTP アドレスに設定されます。</span><span class="sxs-lookup"><span data-stu-id="f163c-134">The email by default will be set to the Office 365 primary SMTP address of the user.</span></span> <span data-ttu-id="f163c-135">Office 365 以外のアドレス、Hotmail または MSN の電子メール アドレスに電子メールを送信できます。</span><span class="sxs-lookup"><span data-stu-id="f163c-135">You can send an email to a non-Office 365 address such as a Hotmail or MSN email address.</span></span> <span data-ttu-id="f163c-136">デフォルトの電子メール アドレスは、Windows PowerShell を使用してオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="f163c-136">You can override the default email address by using Windows PowerShell.</span></span> <span data-ttu-id="f163c-137">これは、ユーザーが Office 365 の Exchange メールボックスを持っていない場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="f163c-137">This is useful if the users don't have an Exchange mailbox in Office 365.</span></span>

    

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="f163c-138">Windows PowerShell の詳細情報</span><span class="sxs-lookup"><span data-stu-id="f163c-138">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="f163c-p109">Windows PowerShell で行うのは、ユーザーを管理し、ユーザーに何を許可して何を禁止するかを管理することです。Windows PowerShell を利用すると、Office 365 の管理を 1 か所で行うことができるので、複数のタスクを担当する管理者の日常業務を単純化できます。Windows PowerShell の使用を開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f163c-p109">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="f163c-142">Office 365 PowerShell を使用する必要がある理由</span><span class="sxs-lookup"><span data-stu-id="f163c-142">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="f163c-143">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="f163c-143">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="f163c-144">Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f163c-144">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="f163c-145">関連トピック</span><span class="sxs-lookup"><span data-stu-id="f163c-145">Related topics</span></span>

[<span data-ttu-id="f163c-146">ユーザーの会議 ID をリセットする</span><span class="sxs-lookup"><span data-stu-id="f163c-146">Reset a conference ID for a user</span></span>](reset-a-conference-id-for-a-user-in-teams.md)
