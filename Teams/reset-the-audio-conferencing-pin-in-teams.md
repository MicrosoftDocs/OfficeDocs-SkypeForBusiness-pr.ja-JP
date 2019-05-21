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
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Pin について知っておくべきことと、Microsoft Teams で Pin をリセットする方法について説明します。 '
ms.openlocfilehash: 7e69b883156a6aed331f0cd401eb87e371809695
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34306577"
---
# <a name="reset-the-audio-conferencing-pin-in-microsoft-teams"></a><span data-ttu-id="86363-103">Microsoft Teams で電話会議の PIN をリセットする</span><span class="sxs-lookup"><span data-stu-id="86363-103">Reset the Audio Conferencing PIN in Microsoft Teams</span></span>

<span data-ttu-id="86363-104">PIN は、電話会議が有効になっている Microsoft Teams ユーザーごとに作成された番号から構成されるコードです。</span><span class="sxs-lookup"><span data-stu-id="86363-104">A PIN is a code made up of numbers that is created for each Microsoft Teams user who is enabled for audio conferencing.</span></span> <span data-ttu-id="86363-105">電話会議の Pin は、会議の開催者が会議の開催者であり、電話で会議を開始できることを示すために使用されます。</span><span class="sxs-lookup"><span data-stu-id="86363-105">Audio conferencing PINs are used by meeting organizers to identify that they are the meeting organizer and allow them to start a meeting over the phone.</span></span> <span data-ttu-id="86363-106">Microsoft Teams アプリを使って会議を開始する場合、PIN は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="86363-106">If they use the Microsoft Teams app to start the meeting, a PIN isn't required.</span></span> <span data-ttu-id="86363-107">ユーザーが PIN を忘れた場合、電話会議用に有効にしたときに送信されたメールでその PIN が見つからない場合は、管理者が自分の pin をリセットするか、自分の pin をリセットすることができます。</span><span class="sxs-lookup"><span data-stu-id="86363-107">If users forget their PIN and they can't find it in the email that was sent to them when they were enabled for audio conferencing, an administrator can reset their PIN, or they can reset their own PIN.</span></span>
  
<span data-ttu-id="86363-108">会議を開始できるのは、認証されたユーザーが Microsoft Teams アプリを使って参加した場合、または開催者が電話で自分の PIN を使用して参加した場合です。</span><span class="sxs-lookup"><span data-stu-id="86363-108">Meetings can be started when an authenticated user joins using the Microsoft Teams app or when the organizer joins with his or her PIN over the phone.</span></span> <span data-ttu-id="86363-109">会議の開始に PIN が必要な場合、電話で参加するユーザーはロビーで待機し、会議が開始するまで保留音を聞くことになります。</span><span class="sxs-lookup"><span data-stu-id="86363-109">When a meeting requires a PIN to start, users who join over the phone will be placed in the lobby and will listen to music on hold until the meeting starts.</span></span> <span data-ttu-id="86363-110">会議の開催者が、電話で会議を開始するための PIN を要求しない場合、発信者は会議に参加しようとするときに PIN の提示を求められません。</span><span class="sxs-lookup"><span data-stu-id="86363-110">If the organizer of a meeting doesn't require a PIN to start the meeting over the phone, then callers won't be asked to provide a PIN when they join the meeting.</span></span>

## <a name="reset-a-users-pin"></a><span data-ttu-id="86363-111">ユーザーの PIN をリセットする</span><span class="sxs-lookup"><span data-stu-id="86363-111">Reset a user's PIN</span></span>

<span data-ttu-id="86363-112">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Microsoft Teams 管理センターの使用**</span><span class="sxs-lookup"><span data-stu-id="86363-112">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="86363-113">左側のナビゲーションで、[**ユーザー**] をクリックしてから、空いているユーザーのリストからユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="86363-113">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="86363-114">[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="86363-114">Click **Edit**.</span></span>

3. <span data-ttu-id="86363-115">[**電話会議**] の [ **PIN のリセット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="86363-115">Under **Audio Conferencing**, click **Reset PIN**.</span></span>

4. <span data-ttu-id="86363-116">[**リセット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="86363-116">Click **Reset**.</span></span>
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-his-or-her-own-pin"></a><span data-ttu-id="86363-117">ユーザーが自分の PIN をリセットする</span><span class="sxs-lookup"><span data-stu-id="86363-117">Have a user reset his or her own PIN</span></span>

1. <span data-ttu-id="86363-118">ユーザーにアクセス権を[https://admin0m.online.lync.com/lscp/usp/pstnconferencing](https://admin0m.online.lync.com/lscp/usp/pstnconferencing)付与します。</span><span class="sxs-lookup"><span data-stu-id="86363-118">Have the user go to [https://admin0m.online.lync.com/lscp/usp/pstnconferencing](https://admin0m.online.lync.com/lscp/usp/pstnconferencing).</span></span>
2. <span data-ttu-id="86363-119">[ **PIN のリセット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="86363-119">Click **Reset PIN**.</span></span> 


## <a name="what-else-should-you-know-about-pins"></a><span data-ttu-id="86363-120">PIN について知っておくべきその他のこと</span><span class="sxs-lookup"><span data-stu-id="86363-120">What else should you know about PINs?</span></span>

- <span data-ttu-id="86363-121">セキュリティ保護のため、PIN のリセット時に PIN は 1 回だけ管理者に表示されます。</span><span class="sxs-lookup"><span data-stu-id="86363-121">For security purposes, the PIN is only shown to an administrator on one time, when the PIN is reset.</span></span> <span data-ttu-id="86363-122">PIN が管理者によってリセットされると、PIN が "\* \* \* \* \*" と表示されます。</span><span class="sxs-lookup"><span data-stu-id="86363-122">After the PIN is reset by an administrator, the PIN will be listed as \*\*\*\*\*\*\*\*\*\*\*.</span></span>
    
- <span data-ttu-id="86363-123">ユーザーにメールを自動的に送信する機能は既定で有効になっています。電話会議が有効になっているか、PIN がリセットされると、ユーザーは PIN を含むメールを受信します。</span><span class="sxs-lookup"><span data-stu-id="86363-123">Automatically sending emails to users is enabled by default, and users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset.</span></span> <span data-ttu-id="86363-124">ただし、メールの自動送信を無効にした場合、PIN のリセットメールはユーザーに送信されず、ユーザーに PIN 情報を手動で送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="86363-124">But if you have disabled automatically sending emails, a PIN reset email won't be sent to a user and you will have to manually send the PIN information to the user.</span></span>
    
- <span data-ttu-id="86363-p105">会議が始まると、ロビー内のすべてのユーザーは自動的にその会議に参加します。 たとえば、会議が始まる前に 2 人の参加者が会議に参加しようとすると、ロビーで待って保留音を聞くことになります。会議の開催者が自分の PIN を使用して電話で参加すると、会議が始まり、ロビーにいる参加者が会議に参加します。</span><span class="sxs-lookup"><span data-stu-id="86363-p105">When a meeting starts, all of the users in the lobby will automatically join it. For example, if two participants try to join a meeting before it has been started, they will be put in the lobby and will listen to music on hold, and when the meeting organizer joins using his PIN via phone, the meeting will start and the participants in the lobby will join the meeting.</span></span>
    
- <span data-ttu-id="86363-127">既定の設定では、匿名の発信者が会議を開始することは許可されていません。</span><span class="sxs-lookup"><span data-stu-id="86363-127">The default setting is to not allow a meeting to be started by anonymous callers.</span></span>
    
- <span data-ttu-id="86363-128">電話会議のユーザーを有効にすると、既定では、会議の情報とその PIN を含むメールが送信されます。</span><span class="sxs-lookup"><span data-stu-id="86363-128">When you enable a user for audio conferencing, by default they are sent emails that include conferencing information and their PIN.</span></span> <span data-ttu-id="86363-129">PIN がリセットされると、ユーザーに対して設定されているプライマリ SMTP アドレス (エイリアス) 宛てに、ユーザーに Office 365 メールボックスがある必要があります。</span><span class="sxs-lookup"><span data-stu-id="86363-129">The user must have an Office 365 mailbox, because when a PIN is reset, a new PIN will be sent to the user in email to their primary SMTP address (alias) that is set for the user.</span></span>
    
- <span data-ttu-id="86363-130">電話会議をセットアップするときには、組織内の Pin に必要な数字を設定します。</span><span class="sxs-lookup"><span data-stu-id="86363-130">When you set up audio conferencing, you set the digits that are required for the PINs in your organization.</span></span> <span data-ttu-id="86363-131">Pin は 4 ~ 12 桁にすることができます。既定値は5です。</span><span class="sxs-lookup"><span data-stu-id="86363-131">PINs can be from 4 to 12 digits - the default is 5.</span></span> <span data-ttu-id="86363-132">PIN の長さの設定を変更した場合、設定は新しく生成された Pin にのみ適用され、電話会議用に有効になっている既存のユーザーの PIN の設定には適用されません。</span><span class="sxs-lookup"><span data-stu-id="86363-132">If you change the PIN length setting, the setting is only applied on newly generated PINs and isn't applied to the PIN setting for existing users that are enabled for audio conferencing.</span></span> <span data-ttu-id="86363-133">「[電話会議の PIN の長さを設定](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="86363-133">See [Set the length of the PIN for Audio Conferencing meetings](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md).</span></span>
    
- <span data-ttu-id="86363-134">既定では、メールはユーザーの Office 365 プライマリ SMTP アドレスに設定されます。</span><span class="sxs-lookup"><span data-stu-id="86363-134">The email by default will be set to the Office 365 primary SMTP address of the user.</span></span> <span data-ttu-id="86363-135">Hotmail または MSN のメールアドレスなど、Office 以外の365のアドレスにメールを送信することができます。</span><span class="sxs-lookup"><span data-stu-id="86363-135">You can send an email to a non-Office 365 address such as a Hotmail or MSN email address.</span></span> <span data-ttu-id="86363-136">Windows PowerShell を使用して、既定のメールアドレスを上書きできます。</span><span class="sxs-lookup"><span data-stu-id="86363-136">You can override the default email address by using Windows PowerShell.</span></span> <span data-ttu-id="86363-137">これは、ユーザーが Office 365 の Exchange メールボックスを持っていない場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="86363-137">This is useful if the users don't have an Exchange mailbox in Office 365.</span></span>

    

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="86363-138">Windows PowerShell の詳細情報</span><span class="sxs-lookup"><span data-stu-id="86363-138">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="86363-p109">Windows PowerShell で行うのは、ユーザーを管理し、ユーザーに何を許可して何を禁止するかを管理することです。Windows PowerShell を利用すると、Office 365 の管理を 1 か所で行うことができるので、複数のタスクを担当する管理者の日常業務を単純化できます。Windows PowerShell の使用を開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="86363-p109">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="86363-142">Office 365 PowerShell を使用する必要がある理由</span><span class="sxs-lookup"><span data-stu-id="86363-142">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="86363-143">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="86363-143">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="86363-144">Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="86363-144">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="86363-145">関連トピック</span><span class="sxs-lookup"><span data-stu-id="86363-145">Related topics</span></span>

[<span data-ttu-id="86363-146">ユーザーの会議 ID をリセットする</span><span class="sxs-lookup"><span data-stu-id="86363-146">Reset a conference ID for a user</span></span>](reset-a-conference-id-for-a-user-in-teams.md)
