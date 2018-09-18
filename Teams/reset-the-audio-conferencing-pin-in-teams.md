---
title: Microsoft Teams で電話会議の PIN をリセットする
mms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 67866a47-89c1-4593-8766-3a68777e2be6
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
description: 'PIN について知っておくべきことと、Microsoft Teams でそれらをリセットする方法について確認します。 '
ms.openlocfilehash: 9c63df504150dce7ba1d46329fc86a27c75ced8d
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/08/2018
ms.locfileid: "23892955"
---
# <a name="reset-the-audio-conferencing-pin-in-microsoft-teams"></a><span data-ttu-id="dc86a-103">Microsoft Teams で電話会議の PIN をリセットする</span><span class="sxs-lookup"><span data-stu-id="dc86a-103">Reset the Audio Conferencing PIN in Microsoft Teams</span></span>

<span data-ttu-id="dc86a-104">PIN は数で構成されるコードで、電話会議の利用が有効になっている各 Microsoft Teams ユーザーに対して作成されます。</span><span class="sxs-lookup"><span data-stu-id="dc86a-104">A PIN is a code made up of numbers that is created for each Microsoft Teams user who is enabled for audio conferencing.</span></span> <span data-ttu-id="dc86a-105">電話会議 PIN は会議の開催者によって、自分たちが会議の開催者であることを識別し、電話を経由して会議を開始することができるようにするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="dc86a-105">Audio conferencing PINs are used by meeting organizers to identify that they are the meeting organizer and allow them to start a meeting over the phone.</span></span> <span data-ttu-id="dc86a-106">会議を開始するために Microsoft Teams アプリを使用する場合、PIN は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="dc86a-106">If they use the Microsoft Teams app to start the meeting, a PIN isn't required.</span></span> <span data-ttu-id="dc86a-107">ユーザーが PIN を忘れてしまい、電話会議の利用が有効になったときに送られてきたメールから見つけることができない場合は、管理者がそれらのユーザーの PIN をリセットするか、ユーザー自身が自分の PIN をリセットすることができます。</span><span class="sxs-lookup"><span data-stu-id="dc86a-107">If users forget their PIN and they can't find it in the email that was sent to them when they were enabled for audio conferencing, an administrator can reset their PIN, or they can reset their own PIN.</span></span>
  
<span data-ttu-id="dc86a-108">会議を開始できるのは、認証済みユーザーが Microsoft Teams アプリを使用して参加する場合か、開催者が自分の PIN を使用して電話で参加する場合です。</span><span class="sxs-lookup"><span data-stu-id="dc86a-108">Meetings can be started when an authenticated user joins using a Skype for Business client or when the organizer joins with his or her PIN over the phone.</span></span> <span data-ttu-id="dc86a-109">会議の開始に PIN が必要な場合、電話で参加するユーザーはロビーで待機し、会議が開始するまで保留音を聞くことになります。</span><span class="sxs-lookup"><span data-stu-id="dc86a-109">When a meeting requires a PIN to start, users who join over the phone will be placed in the lobby and will listen to music on hold until the meeting starts.</span></span> <span data-ttu-id="dc86a-110">会議の開催者が、電話で会議を開始するための PIN を要求しない場合、発信者は会議に参加しようとするときに PIN の提示を求められません。</span><span class="sxs-lookup"><span data-stu-id="dc86a-110">If the organizer of a meeting doesn't require a PIN to start the meeting over the phone, then callers won't be asked to provide a PIN when they join the meeting.</span></span>

## <a name="reset-a-users-pin"></a><span data-ttu-id="dc86a-111">ユーザーの PIN をリセットする</span><span class="sxs-lookup"><span data-stu-id="dc86a-111">Reset a user's PIN</span></span>

1. <span data-ttu-id="dc86a-112">左側のナビゲーションで、[**ユーザー**] をクリックしてから、空いているユーザーのリストからユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="dc86a-112">In the left navigation of the **Office 365 admin center, go to UsersActive users**, and then select the user or users from the list of available users.</span></span>

2. <span data-ttu-id="dc86a-113">ページの上部で、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc86a-113">At the top of the Conference Bridges page, click Bridge Settings.</span></span>

3. <span data-ttu-id="dc86a-114">[**電話会議**] の下で、[**PIN のリセット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc86a-114">Under **Audio Conferencing**, click **Reset PIN**.</span></span>
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-his-or-her-own-pin"></a><span data-ttu-id="dc86a-115">ユーザーに自分の PIN をリセットさせる</span><span class="sxs-lookup"><span data-stu-id="dc86a-115">Have a user reset his or her own PIN</span></span>

1. <span data-ttu-id="dc86a-116">ユーザーに [https://admin0m.online.lync.com/lscp/usp/pstnconferencing](https://admin0m.online.lync.com/lscp/usp/pstnconferencing) に移動してもらいます。</span><span class="sxs-lookup"><span data-stu-id="dc86a-116">Have the user go to [https://admin0m.online.lync.com/lscp/usp/pstnconferencing](https://admin0m.online.lync.com/lscp/usp/pstnconferencing).</span></span>
2. <span data-ttu-id="dc86a-117">[**PIN のリセット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc86a-117">Click **Reset PIN**.</span></span> 


## <a name="what-else-should-you-know-about-pins"></a><span data-ttu-id="dc86a-118">PIN について知っておくべきその他のこと</span><span class="sxs-lookup"><span data-stu-id="dc86a-118">What else should you know about PINs?</span></span>

- <span data-ttu-id="dc86a-119">セキュリティ保護のため、PIN のリセット時に PIN は管理者に 1 回だけ表示されます。</span><span class="sxs-lookup"><span data-stu-id="dc86a-119">For security purposes, the PIN is only shown to an administrator on one time, when the PIN is reset.</span></span> <span data-ttu-id="dc86a-120">PIN は管理者によってリセットされた後、\*\*\*\*\*\*\*\*\*\*\* とリストに表示されます。</span><span class="sxs-lookup"><span data-stu-id="dc86a-120">After the PIN is reset by an administrator, the PIN will be listed as \*\*\*\*\*\*\*\*\*\*\* in the Skype for Business admin center and in the results when they use Get-CsCsOnlineDialInConfencingUser in the Windows PowerShell.</span></span>
    
- <span data-ttu-id="dc86a-121">ユーザーへのメールの自動送信は既定で有効です。ユーザーが電話会議で有効になるか、PIN がリセットされると、ユーザーは自分の PIN が記載されたメールを受信します。</span><span class="sxs-lookup"><span data-stu-id="dc86a-121">Automatically sending emails to users is enabled by default and users will receive an email with their PIN when they're enabled for dial-in conferencing or when the PIN is reset. But if you have disabled automatically sending emails, then a PIN reset email won't be sent to a user and you will have to manually send the PIN information to the user.</span></span> <span data-ttu-id="dc86a-122">ただし、メールの自動送信を無効にしても、ユーザーには PIN リセットのメールは送信されず、そのユーザーには手動で PIN 情報を送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc86a-122">But if you have disabled automatically sending emails, a PIN reset email won't be sent and you will have to manually send the PIN to the user.</span></span>
    
- <span data-ttu-id="dc86a-p105">会議が始まると、ロビー内のすべてのユーザーは自動的にその会議に参加します。 たとえば、会議が始まる前に 2 人の参加者が会議に参加しようとすると、ロビーで待って保留音を聞くことになります。会議の開催者が自分の PIN を使用して電話で参加すると、会議が始まり、ロビーにいる参加者が会議に参加します。</span><span class="sxs-lookup"><span data-stu-id="dc86a-p105">When a meeting starts, all of the users in the lobby will automatically join it. For example, if two participants try to join a meeting before it has been started, they will be put in the lobby and will listen to music on hold, and when the meeting organizer joins using his PIN via phone, the meeting will start and the participants in the lobby will join the meeting.</span></span>
    
- <span data-ttu-id="dc86a-125">既定の設定では、匿名の発信者が会議を開始することはできません。</span><span class="sxs-lookup"><span data-stu-id="dc86a-125">The default setting isn't to allow a meeting to be started by an anonymous callers.</span></span>
    
- <span data-ttu-id="dc86a-126">電話会議でユーザーを有効にすると、既定でユーザーに電話会議の情報と PIN が記載されたメールが送信されます。</span><span class="sxs-lookup"><span data-stu-id="dc86a-126">When you enable a user for audio conferencing, by default they are sent emails that include conferencing information and their PIN.</span></span> <span data-ttu-id="dc86a-127">ユーザーは Office 365 メールボックスを持っている必要があります。PIN がリセットされると、ユーザーに設定されているプライマリ SMTP アドレス (エイリアス) へのメールで、新しい PIN がユーザーに送信されるためです。</span><span class="sxs-lookup"><span data-stu-id="dc86a-127">When you enable a user for dial-in conferencing, by default they are sent emails that includes conferencing information and their PIN. The user must have an Office 365 mailbox because when a PIN is reset, a new PIN will be sent to the user in email to their primary SMTP address (alias) that is set for the user.</span></span>
    
- <span data-ttu-id="dc86a-128">電話会議をセットアップすると、所属する組織の PIN で必要な桁数を設定することになります。</span><span class="sxs-lookup"><span data-stu-id="dc86a-128">When you set up audio conferencing, you set the digits that are required for the PINs in your organization.</span></span> <span data-ttu-id="dc86a-129">PIN は 4 桁から 12 桁の間にすることができます。既定では 5 桁です。</span><span class="sxs-lookup"><span data-stu-id="dc86a-129">PINs can be from 4 to 12 digits - the default is 5.</span></span> <span data-ttu-id="dc86a-130">PIN の長さの設定を変更すると、その設定は新たに生成された PIN のみに適用され、電話会議で有効になっている既存のユーザーの PIN 設定には適用されません。</span><span class="sxs-lookup"><span data-stu-id="dc86a-130">If you change the PIN length setting, the setting is only applied on newly generated PINs and isn't applied to the PIN setting for existing users that are enabled for audio conferencing.</span></span> <span data-ttu-id="dc86a-131">「[Set the length of the PIN for Audio Conferencing meetings (電話会議の PIN の長さを設定する)](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="dc86a-131">See [Set the length of the PIN for Audio Conferencing meetings](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md).</span></span>
    
- <span data-ttu-id="dc86a-132">既定では、メールはユーザーの Office 365 プライマリ SMTP アドレスに送信されるように設定されています。</span><span class="sxs-lookup"><span data-stu-id="dc86a-132">The email by default will be set to the Office 365 primary SMTP address of the user you can send an email to a non-Office 365 address such as a Hotmail or MSN email address.</span></span> <span data-ttu-id="dc86a-133">Hotmail や MSN のメール アドレスなどの Office 365 以外のアドレスにメールを送信することもできます。</span><span class="sxs-lookup"><span data-stu-id="dc86a-133">The email by default will be set to the Office 365 primary SMTP address of the user you can send an email to a non-Office 365 address such as a Hotmail or MSN email address.</span></span> <span data-ttu-id="dc86a-134">Windows PowerShell を使用して、既定のメール アドレスを上書きすることができます。</span><span class="sxs-lookup"><span data-stu-id="dc86a-134">You can override the default email address by using Windows PowerShell.</span></span> <span data-ttu-id="dc86a-135">これは、ユーザーが Office 365 の Exchange メールボックスを持っていない場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="dc86a-135">This is useful if the users don't have an Exchange mailbox in Office 365.</span></span>

    

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="dc86a-136">Windows PowerShell の詳細情報</span><span class="sxs-lookup"><span data-stu-id="dc86a-136">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="dc86a-p109">Windows PowerShell は、ユーザーと、ユーザーに許可されていることと許可されていないことを管理するためにあるということです。Windows PowerShell があれば、一元管理を使用して Office 365 を管理し、複数のタスクを抱えているときに、日常の仕事を簡素化することができます。Windows PowerShell を開始するには、これらのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc86a-p109">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="dc86a-140">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="dc86a-140">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="dc86a-141">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="dc86a-141">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="dc86a-142">Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="dc86a-142">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="dc86a-143">関連トピック</span><span class="sxs-lookup"><span data-stu-id="dc86a-143">Related topics</span></span>

[<span data-ttu-id="dc86a-144">ユーザーのために会議 ID をリセットする</span><span class="sxs-lookup"><span data-stu-id="dc86a-144">Reset a conference ID for a user</span></span>](reset-a-conference-id-for-a-user-in-teams.md)
