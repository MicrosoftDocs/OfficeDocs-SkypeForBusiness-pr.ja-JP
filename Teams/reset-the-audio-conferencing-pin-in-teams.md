---
title: Microsoft Teams で電話会議の PIN をリセットする
mms.author: tonysmit
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
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'PIN について知っておくべきことと、Microsoft Teams でそれらをリセットする方法について確認します。 '
ms.openlocfilehash: 44229d57a8f09b8b687f6fc0367686e81e898c5a
ms.sourcegitcommit: 31827526894ffb75d64fcb0a7c76ee874ad3c269
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2019
ms.locfileid: "29754114"
---
# <a name="reset-the-audio-conferencing-pin-in-microsoft-teams"></a><span data-ttu-id="238f4-103">Microsoft Teams で電話会議の PIN をリセットする</span><span class="sxs-lookup"><span data-stu-id="238f4-103">Reset the Audio Conferencing PIN in Microsoft Teams</span></span>

<span data-ttu-id="238f4-104">PIN は数で構成されるコードで、電話会議の利用が有効になっている各 Microsoft Teams ユーザーに対して作成されます。</span><span class="sxs-lookup"><span data-stu-id="238f4-104">A PIN is a code made up of numbers that is created for each Microsoft Teams user who is enabled for audio conferencing.</span></span> <span data-ttu-id="238f4-105">電話会議 PIN は会議の開催者によって、自分たちが会議の開催者であることを識別し、電話を経由して会議を開始することができるようにするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="238f4-105">Audio conferencing PINs are used by meeting organizers to identify that they are the meeting organizer and allow them to start a meeting over the phone.</span></span> <span data-ttu-id="238f4-106">会議を開始するために Microsoft Teams アプリを使用する場合、PIN は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="238f4-106">If they use the Microsoft Teams app to start the meeting, a PIN isn't required.</span></span> <span data-ttu-id="238f4-107">ユーザーが PIN を忘れてしまい、電話会議の利用が有効になったときに送られてきたメールから見つけることができない場合は、管理者がそれらのユーザーの PIN をリセットするか、ユーザー自身が自分の PIN をリセットすることができます。</span><span class="sxs-lookup"><span data-stu-id="238f4-107">If users forget their PIN and they can't find it in the email that was sent to them when they were enabled for audio conferencing, an administrator can reset their PIN, or they can reset their own PIN.</span></span>
  
<span data-ttu-id="238f4-108">会議を開始できるのは、認証済みユーザーが Microsoft Teams アプリを使用して参加する場合か、開催者が自分の PIN を使用して電話で参加する場合です。</span><span class="sxs-lookup"><span data-stu-id="238f4-108">Meetings can be started when an authenticated user joins using the Microsoft Teams app or when the organizer joins with his or her PIN over the phone.</span></span> <span data-ttu-id="238f4-109">会議の開始に PIN が必要な場合、電話で参加するユーザーはロビーで待機し、会議が開始するまで保留音を聞くことになります。</span><span class="sxs-lookup"><span data-stu-id="238f4-109">When a meeting requires a PIN to start, users who join over the phone will be placed in the lobby and will listen to music on hold until the meeting starts.</span></span> <span data-ttu-id="238f4-110">会議の開催者が、電話で会議を開始するための PIN を要求しない場合、発信者は会議に参加しようとするときに PIN の提示を求められません。</span><span class="sxs-lookup"><span data-stu-id="238f4-110">If the organizer of a meeting doesn't require a PIN to start the meeting over the phone, then callers won't be asked to provide a PIN when they join the meeting.</span></span>

## <a name="reset-a-users-pin"></a><span data-ttu-id="238f4-111">ユーザーの PIN をリセットする</span><span class="sxs-lookup"><span data-stu-id="238f4-111">Reset a user's PIN</span></span>

<span data-ttu-id="238f4-112">![チーム ・ ロゴ ・ 30x30.png](media/teams-logo-30x30.png) **、マイクロソフトのチーム管理センターを使用して**</span><span class="sxs-lookup"><span data-stu-id="238f4-112">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="238f4-113">左側のナビゲーションでは、**ユーザー**] をクリックしてで使用可能なユーザーの一覧からユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="238f4-113">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="238f4-114">[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="238f4-114">Click **Edit**.</span></span>

3. <span data-ttu-id="238f4-115">**オーディオ会議**では、[ **PIN のリセット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="238f4-115">Under **Audio Conferencing**, click **Reset PIN**.</span></span>

4. <span data-ttu-id="238f4-116">[**リセット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="238f4-116">Click **Reset**.</span></span>
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-his-or-her-own-pin"></a><span data-ttu-id="238f4-117">ユーザーが自分の PIN のリセット</span><span class="sxs-lookup"><span data-stu-id="238f4-117">Have a user reset his or her own PIN</span></span>

1. <span data-ttu-id="238f4-118">ユーザーには、 [https://admin0m.online.lync.com/lscp/usp/pstnconferencing](https://admin0m.online.lync.com/lscp/usp/pstnconferencing)。</span><span class="sxs-lookup"><span data-stu-id="238f4-118">Have the user go to [https://admin0m.online.lync.com/lscp/usp/pstnconferencing](https://admin0m.online.lync.com/lscp/usp/pstnconferencing).</span></span>
2. <span data-ttu-id="238f4-119">**PIN のリセット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="238f4-119">Click **Reset PIN**.</span></span> 


## <a name="what-else-should-you-know-about-pins"></a><span data-ttu-id="238f4-120">PIN について知っておくべきその他のこと</span><span class="sxs-lookup"><span data-stu-id="238f4-120">What else should you know about PINs?</span></span>

- <span data-ttu-id="238f4-121">セキュリティ保護のため、PIN のリセット時に PIN は 1 回だけ管理者に表示されます。</span><span class="sxs-lookup"><span data-stu-id="238f4-121">For security purposes, the PIN is only shown to an administrator on one time, when the PIN is reset.</span></span> <span data-ttu-id="238f4-122">暗証番号 (pin) は、管理者がリセットされますが後の暗証番号 (pin) が表示されます。。</span><span class="sxs-lookup"><span data-stu-id="238f4-122">After the PIN is reset by an administrator, the PIN will be listed as \*\*\*\*\*\*\*\*\*\*\*.</span></span>
    
- <span data-ttu-id="238f4-123">デフォルトで有効化は自動的にユーザーに電子メールを送信して、ユーザー音声会議や、PIN をリセットする場合は有効にしている場合、PIN の電子メールが送信されます。</span><span class="sxs-lookup"><span data-stu-id="238f4-123">Automatically sending emails to users is enabled by default, and users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset.</span></span> <span data-ttu-id="238f4-124">自動的に無効にした場合電子メールを送信するユーザーに PIN リセットの電子メールを送信しないユーザーに暗証番号 (pin) の情報を手動で送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="238f4-124">But if you have disabled automatically sending emails, a PIN reset email won't be sent to a user and you will have to manually send the PIN information to the user.</span></span>
    
- <span data-ttu-id="238f4-p105">会議が始まると、ロビー内のすべてのユーザーは自動的にその会議に参加します。 たとえば、会議が始まる前に 2 人の参加者が会議に参加しようとすると、ロビーで待って保留音を聞くことになります。会議の開催者が自分の PIN を使用して電話で参加すると、会議が始まり、ロビーにいる参加者が会議に参加します。</span><span class="sxs-lookup"><span data-stu-id="238f4-p105">When a meeting starts, all of the users in the lobby will automatically join it. For example, if two participants try to join a meeting before it has been started, they will be put in the lobby and will listen to music on hold, and when the meeting organizer joins using his PIN via phone, the meeting will start and the participants in the lobby will join the meeting.</span></span>
    
- <span data-ttu-id="238f4-127">既定の設定では、匿名の呼び出しを開始するための会議を許可しないようにします。</span><span class="sxs-lookup"><span data-stu-id="238f4-127">The default setting is to not allow a meeting to be started by anonymous callers.</span></span>
    
- <span data-ttu-id="238f4-128">オーディオ会議のユーザーを有効にすると、既定で送信される会議の情報と PIN を含む電子メール。</span><span class="sxs-lookup"><span data-stu-id="238f4-128">When you enable a user for audio conferencing, by default they are sent emails that include conferencing information and their PIN.</span></span> <span data-ttu-id="238f4-129">ユーザーは PIN をリセットすると、新しい暗証番号 (pin) はでは、プライマリ SMTP アドレス (エイリアス)、ユーザーに設定されている電子メールのユーザーに送信されますので、Office 365 のメールボックスに必要です。</span><span class="sxs-lookup"><span data-stu-id="238f4-129">The user must have an Office 365 mailbox, because when a PIN is reset, a new PIN will be sent to the user in email to their primary SMTP address (alias) that is set for the user.</span></span>
    
- <span data-ttu-id="238f4-130">オーディオ会議を設定するときは、組織内のピンに必要な数字を設定します。</span><span class="sxs-lookup"><span data-stu-id="238f4-130">When you set up audio conferencing, you set the digits that are required for the PINs in your organization.</span></span> <span data-ttu-id="238f4-131">ピンは 12 桁、4 - デフォルトは 5 です。</span><span class="sxs-lookup"><span data-stu-id="238f4-131">PINs can be from 4 to 12 digits - the default is 5.</span></span> <span data-ttu-id="238f4-132">暗証番号 (pin) の長さの設定を変更すると、設定は、新しく生成されたピンの位置にのみ適用し、オーディオ会議を有効になっている既存のユーザーの暗証番号 (pin) の設定に適用されていません。</span><span class="sxs-lookup"><span data-stu-id="238f4-132">If you change the PIN length setting, the setting is only applied on newly generated PINs and isn't applied to the PIN setting for existing users that are enabled for audio conferencing.</span></span> <span data-ttu-id="238f4-133">[オーディオ会議の会議の暗証番号 (pin) の長さの設定](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="238f4-133">See [Set the length of the PIN for Audio Conferencing meetings](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md).</span></span>
    
- <span data-ttu-id="238f4-134">既定で電子メールは、ユーザーの Office 365 のプライマリ SMTP アドレスに設定されます。</span><span class="sxs-lookup"><span data-stu-id="238f4-134">The email by default will be set to the Office 365 primary SMTP address of the user.</span></span> <span data-ttu-id="238f4-135">Office 365 以外のアドレス、Hotmail または MSN の電子メール アドレスに電子メールを送信できます。</span><span class="sxs-lookup"><span data-stu-id="238f4-135">You can send an email to a non-Office 365 address such as a Hotmail or MSN email address.</span></span> <span data-ttu-id="238f4-136">デフォルトの電子メール アドレスは、Windows PowerShell を使用してオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="238f4-136">You can override the default email address by using Windows PowerShell.</span></span> <span data-ttu-id="238f4-137">これは、ユーザーが Office 365 の Exchange メールボックスを持っていない場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="238f4-137">This is useful if the users don't have an Exchange mailbox in Office 365.</span></span>

    

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="238f4-138">Windows PowerShell の詳細情報</span><span class="sxs-lookup"><span data-stu-id="238f4-138">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="238f4-p109">Windows PowerShell は、ユーザーと、ユーザーに許可されていることと許可されていないことを管理するためにあるということです。Windows PowerShell があれば、一元管理を使用して Office 365 を管理し、複数のタスクを抱えているときに、日常の仕事を簡素化することができます。Windows PowerShell を開始するには、これらのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="238f4-p109">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="238f4-142">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="238f4-142">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="238f4-143">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="238f4-143">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="238f4-144">Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="238f4-144">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="238f4-145">関連トピック</span><span class="sxs-lookup"><span data-stu-id="238f4-145">Related topics</span></span>

[<span data-ttu-id="238f4-146">ユーザーの会議 ID をリセットする</span><span class="sxs-lookup"><span data-stu-id="238f4-146">Reset a conference ID for a user</span></span>](reset-a-conference-id-for-a-user-in-teams.md)
