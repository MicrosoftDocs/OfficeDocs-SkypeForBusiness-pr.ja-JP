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
- seo-marvel-apr2020
description: MICROSOFT TEAMS でユーザーの電話会議 PIN をリセットする方法と、PIN に関する重要な事実について説明します。
ms.openlocfilehash: ece69ec231408cc860f2fad803d92d22feaca781
ms.sourcegitcommit: cae94cd5761baafde51aea1137e6d164722eead9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2021
ms.locfileid: "53075380"
---
# <a name="reset-the-audio-conferencing-pin-in-microsoft-teams"></a><span data-ttu-id="102a2-103">Microsoft Teams で電話会議の PIN をリセットする</span><span class="sxs-lookup"><span data-stu-id="102a2-103">Reset the Audio Conferencing PIN in Microsoft Teams</span></span>

<span data-ttu-id="102a2-104">PIN は、電話会議を有効にしているユーザーごとにMicrosoft Teams番号で構成されるコードです。</span><span class="sxs-lookup"><span data-stu-id="102a2-104">A PIN is a code made up of numbers that is created for each Microsoft Teams user who is enabled for audio conferencing.</span></span> <span data-ttu-id="102a2-105">電話会議 PIN は、会議の開催者が会議の開催者を識別し、電話で会議を開始するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="102a2-105">Audio conferencing PINs are used by meeting organizers to identify that they are the meeting organizer and allow them to start a meeting over the phone.</span></span> <span data-ttu-id="102a2-106">会議を開始Microsoft Teamsアプリを使用する場合、PIN は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="102a2-106">If they use the Microsoft Teams app to start the meeting, a PIN isn't required.</span></span> <span data-ttu-id="102a2-107">ユーザーが自分の PIN を忘れて、電話会議を有効にした場合に送信されたメールで PIN が見つからなかった場合、管理者は PIN をリセットするか、自分の PIN をリセットできます。</span><span class="sxs-lookup"><span data-stu-id="102a2-107">If users forget their PIN and they can't find it in the email that was sent to them when they were enabled for audio conferencing, an administrator can reset their PIN, or they can reset their own PIN.</span></span>
  
<span data-ttu-id="102a2-108">認証されたユーザーが Microsoft Teams アプリを使用して参加した場合、または開催者が電話で PIN を使用して参加するときに、会議を開始できます。</span><span class="sxs-lookup"><span data-stu-id="102a2-108">Meetings can be started when an authenticated user joins using the Microsoft Teams app or when the organizer joins with their PIN over the phone.</span></span> <span data-ttu-id="102a2-109">会議を開始するために PIN が必要な場合、電話で参加するユーザーはロビーに配置され、開催者が許可するまで保留音を聞きます。</span><span class="sxs-lookup"><span data-stu-id="102a2-109">When a meeting requires a PIN to start, users who join over the phone will be placed in the lobby and will listen to music on hold until the organizer admits them.</span></span> <span data-ttu-id="102a2-110">会議の開催者が、電話で会議を開始するための PIN を要求しない場合、発信者は会議に参加しようとするときに PIN の提示を求められません。</span><span class="sxs-lookup"><span data-stu-id="102a2-110">If the organizer of a meeting doesn't require a PIN to start the meeting over the phone, then callers won't be asked to provide a PIN when they join the meeting.</span></span>

## <a name="reset-a-users-pin"></a><span data-ttu-id="102a2-111">ユーザーの PIN をリセットする</span><span class="sxs-lookup"><span data-stu-id="102a2-111">Reset a user's PIN</span></span>

<span data-ttu-id="102a2-112">![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**</span><span class="sxs-lookup"><span data-stu-id="102a2-112">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="102a2-113">左側のナビゲーションで、[**ユーザー**] をクリックしてから、空いているユーザーのリストからユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="102a2-113">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="102a2-114">[編集] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="102a2-114">Click **Edit**.</span></span>

3. <span data-ttu-id="102a2-115">[ **電話会議] の [PIN** のリセット **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="102a2-115">Under **Audio Conferencing**, click **Reset PIN**.</span></span>

4. <span data-ttu-id="102a2-116">[リセット] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="102a2-116">Click **Reset**.</span></span>
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-their-own-pin"></a><span data-ttu-id="102a2-117">ユーザーに自分の PIN をリセットする</span><span class="sxs-lookup"><span data-stu-id="102a2-117">Have a user reset their own PIN</span></span>

1. <span data-ttu-id="102a2-118">ユーザーに に移動します [https://admin0m.online.lync.com/lscp/usp/pstnconferencing](https://admin0m.online.lync.com/lscp/usp/pstnconferencing) 。</span><span class="sxs-lookup"><span data-stu-id="102a2-118">Have the user go to [https://admin0m.online.lync.com/lscp/usp/pstnconferencing](https://admin0m.online.lync.com/lscp/usp/pstnconferencing).</span></span>
2. <span data-ttu-id="102a2-119">[PIN **のリセット] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="102a2-119">Click **Reset PIN**.</span></span> 

> [!NOTE]
> <span data-ttu-id="102a2-120">GCCH の場合は、 に移動します https://webdir2g.online.gov.skypeforbusiness.us/lscp/usp/pstnconferencing 。</span><span class="sxs-lookup"><span data-stu-id="102a2-120">For GCCH go to: https://webdir2g.online.gov.skypeforbusiness.us/lscp/usp/pstnconferencing.</span></span>

## <a name="what-else-should-you-know-about-pins"></a><span data-ttu-id="102a2-121">PIN について知っておくべきその他のこと</span><span class="sxs-lookup"><span data-stu-id="102a2-121">What else should you know about PINs?</span></span>

- <span data-ttu-id="102a2-122">セキュリティ上の目的で、PIN がリセットされた場合、PIN は管理者に 1 回だけ表示されます。</span><span class="sxs-lookup"><span data-stu-id="102a2-122">For security purposes, the PIN is only shown to an administrator one time, when the PIN is reset.</span></span> <span data-ttu-id="102a2-123">管理者が PIN をリセットすると、PIN は \*\*\*\*\*\*\*\*\*\*\* と表示されます。</span><span class="sxs-lookup"><span data-stu-id="102a2-123">After the PIN is reset by an administrator, the PIN will be listed as \*\*\*\*\*\*\*\*\*\*\*.</span></span>
    
- <span data-ttu-id="102a2-124">ユーザーへのメールの自動送信は既定で有効になっています。ユーザーが電話会議を有効にした場合、または PIN がリセットされた場合、ユーザーは PIN を含むメールを受信します。</span><span class="sxs-lookup"><span data-stu-id="102a2-124">Automatically sending emails to users is enabled by default, and users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset.</span></span> <span data-ttu-id="102a2-125">ただし、メールの自動送信を無効にした場合、PIN リセット メールはユーザーに送信されません。PIN 情報をユーザーに手動で送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="102a2-125">But if you have disabled automatically sending emails, a PIN reset email won't be sent to a user and you will have to manually send the PIN information to the user.</span></span>
    
- <span data-ttu-id="102a2-126">会議が開始されると、ロビーのすべてのユーザーが自動的に会議に参加します。</span><span class="sxs-lookup"><span data-stu-id="102a2-126">When a meeting starts, all of the users in the lobby will automatically join it.</span></span> <span data-ttu-id="102a2-127">たとえば、2 人の参加者が開始される前に会議に参加しようとする場合、その参加者はロビーに配置され、保留音を聞き、会議の開催者が電話で PIN を使用して参加すると、会議が開始され、ロビーの参加者が会議に参加します。</span><span class="sxs-lookup"><span data-stu-id="102a2-127">For example, if two participants try to join a meeting before it has been started, they will be put in the lobby and will listen to music on hold, and when the meeting organizer joins using their PIN via phone, the meeting will start and the participants in the lobby will join the meeting.</span></span>
    
- <span data-ttu-id="102a2-128">既定の設定では、匿名の発信者による会議の開始を許可しません。</span><span class="sxs-lookup"><span data-stu-id="102a2-128">The default setting is to not allow a meeting to be started by anonymous callers.</span></span>
    
- <span data-ttu-id="102a2-129">ユーザーが電話会議を有効にした場合、既定では、会議情報と PIN を含むメールが送信されます。</span><span class="sxs-lookup"><span data-stu-id="102a2-129">When you enable a user for audio conferencing, by default they are sent emails that include conferencing information and their PIN.</span></span> <span data-ttu-id="102a2-130">PIN をリセットすると、ユーザーに設定されているプライマリ SMTP アドレス (エイリアス) に新しい PIN が電子メールで送信されるので、ユーザーは Microsoft 365 または Office 365 メールボックスを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="102a2-130">The user must have a Microsoft 365 or Office 365 mailbox, because when a PIN is reset, a new PIN will be sent to the user in email to their primary SMTP address (alias) that is set for the user.</span></span>
    
- <span data-ttu-id="102a2-131">電話会議を設定するときに、組織内の PIN に必要な数字を設定します。</span><span class="sxs-lookup"><span data-stu-id="102a2-131">When you set up audio conferencing, you set the digits that are required for the PINs in your organization.</span></span> <span data-ttu-id="102a2-132">PIN は 4 桁から 12 桁まで指定できます。既定値は 5 です。</span><span class="sxs-lookup"><span data-stu-id="102a2-132">PINs can be from 4 to 12 digits - the default is 5.</span></span> <span data-ttu-id="102a2-133">PIN の長さの設定を変更した場合、この設定は新しく生成された PIN にのみ適用され、電話会議が有効になっている既存のユーザーの PIN 設定には適用されません。</span><span class="sxs-lookup"><span data-stu-id="102a2-133">If you change the PIN length setting, the setting is only applied on newly generated PINs and isn't applied to the PIN setting for existing users that are enabled for audio conferencing.</span></span> <span data-ttu-id="102a2-134">「 [電話会議会議の PIN の長さを設定する」を参照してください](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="102a2-134">See [Set the length of the PIN for Audio Conferencing meetings](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md).</span></span>
    
- <span data-ttu-id="102a2-135">既定では、メールはユーザーのプライマリ SMTP Microsoft 365またはOffice 365に設定されます。</span><span class="sxs-lookup"><span data-stu-id="102a2-135">The email by default will be set to the Microsoft 365 or Office 365 primary SMTP address of the user.</span></span> <span data-ttu-id="102a2-136">メールアドレスは、Microsoft 365または MSN メール Office 365など、Hotmailアドレスに送信できます。</span><span class="sxs-lookup"><span data-stu-id="102a2-136">You can send an email to a non-Microsoft 365 or non-Office 365 address such as a Hotmail or MSN email address.</span></span> <span data-ttu-id="102a2-137">既定のメール アドレスは、既定のメール アドレスを無効にWindows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="102a2-137">You can override the default email address by using Windows PowerShell.</span></span> <span data-ttu-id="102a2-138">これは、ユーザーがメールボックス内にメールボックスを持Exchange持Microsoft 365場合Office 365。</span><span class="sxs-lookup"><span data-stu-id="102a2-138">This is useful if the users don't have an Exchange mailbox in Microsoft 365 or Office 365.</span></span>

    

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="102a2-139">Windows PowerShell の詳細情報</span><span class="sxs-lookup"><span data-stu-id="102a2-139">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="102a2-140">Windows PowerShellは、ユーザーの管理と、ユーザーが許可または許可されていない操作についてすべて行います。</span><span class="sxs-lookup"><span data-stu-id="102a2-140">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="102a2-141">このWindows PowerShell、1 つの管理Microsoft 365または Office 365 を管理し、複数のタスクを実行する場合に毎日の作業を簡略化できます。</span><span class="sxs-lookup"><span data-stu-id="102a2-141">With Windows PowerShell, you can manage Microsoft 365 or Office 365 by using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="102a2-142">Windows PowerShell の使用を開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="102a2-142">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="102a2-143">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="102a2-143">Why you need to use Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="102a2-144">[アプリを使用してMicrosoft 365またはOffice 365を管理Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="102a2-144">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
<span data-ttu-id="102a2-145">Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](/powershell/module/teams/?view=teams-ps)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="102a2-145">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="102a2-146">関連トピック</span><span class="sxs-lookup"><span data-stu-id="102a2-146">Related topics</span></span>

[<span data-ttu-id="102a2-147">ユーザーの会議 ID をリセットする</span><span class="sxs-lookup"><span data-stu-id="102a2-147">Reset a conference ID for a user</span></span>](reset-a-conference-id-for-a-user-in-teams.md)
