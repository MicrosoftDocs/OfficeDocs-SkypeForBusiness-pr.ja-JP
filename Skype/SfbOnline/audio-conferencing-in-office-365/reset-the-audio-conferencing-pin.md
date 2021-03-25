---
title: Skype for Business Online の電話会議 PIN をリセットする
ms.author: tonysmit
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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'PIN について知るべきことを確認し、Skype for Business Online で PIN をリセットする方法について確認します。 '
ms.openlocfilehash: 4b042775a5a0525099c0116d7d55d0092f560cdf
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51114203"
---
# <a name="reset-the-audio-conferencing-pin-in-skype-for-business-online"></a><span data-ttu-id="b0910-103">Skype for Business Online の電話会議 PIN をリセットする</span><span class="sxs-lookup"><span data-stu-id="b0910-103">Reset the Audio Conferencing PIN in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="b0910-104">Microsoft Teams で電話会議 PIN をリセットする方法については、「Microsoft Teams で電話会議 PIN をリセットする」 [を参照してください](/MicrosoftTeams/reset-the-audio-conferencing-pin-in-teams)。</span><span class="sxs-lookup"><span data-stu-id="b0910-104">For information about resetting Audio Conferencing PINs in Microsoft Teams, see [Reset the Audio Conferencing PIN in Microsoft Teams](/MicrosoftTeams/reset-the-audio-conferencing-pin-in-teams).</span></span>

<span data-ttu-id="b0910-105">PIN は、電話会議が有効になっている各 Skype for Business ユーザーに対して作成される番号で構成されるコードです。</span><span class="sxs-lookup"><span data-stu-id="b0910-105">A PIN is a code made up of numbers that is created for each Skype for Business user who is enabled for audio conferencing.</span></span> <span data-ttu-id="b0910-106">電話会議 PIN は、会議の開催者が自分が会議の開催者であり、電話で会議を開始するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="b0910-106">Audio conferencing PINs are used by meeting organizers to identify that they are the meeting organizer and allow them to start a meeting over the phone.</span></span> <span data-ttu-id="b0910-107">Skype for Business アプリを使用して会議を開始する場合、PIN は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="b0910-107">If they use the Skype for Business app to start the meeting, a PIN isn't required.</span></span> <span data-ttu-id="b0910-108">ユーザーが自分の PIN を忘れて、電話会議で有効になっていたときに送信されたメールで PIN を見つからなかった場合、管理者は自分の PIN をリセットするか、自分の PIN をリセットできます。</span><span class="sxs-lookup"><span data-stu-id="b0910-108">If users forget their PIN and they can't find it in the email that was sent to them when they were enabled for audio conferencing, an administrator can reset their PIN, or they can reset their own PIN.</span></span>
  
<span data-ttu-id="b0910-109">認証されたユーザーが Skype for Business アプリを使用して参加する場合、または開催者が自分の PIN で電話で参加すると、会議を開始できます。</span><span class="sxs-lookup"><span data-stu-id="b0910-109">Meetings can be started when an authenticated user joins using the Skype for Business app or when the organizer joins with his or her PIN over the phone.</span></span> <span data-ttu-id="b0910-110">会議の開始に PIN が必要な場合、電話で参加するユーザーはロビーで待機し、会議が開始するまで保留音を聞くことになります。</span><span class="sxs-lookup"><span data-stu-id="b0910-110">When a meeting requires a PIN to start, users who join over the phone will be placed in the lobby and will listen to music on hold until the meeting starts.</span></span> <span data-ttu-id="b0910-111">会議の開催者が、電話で会議を開始するための PIN を要求しない場合、発信者は会議に参加しようとするときに PIN の提示を求められません。</span><span class="sxs-lookup"><span data-stu-id="b0910-111">If the organizer of a meeting doesn't require a PIN to start the meeting over the phone, then callers won't be asked to provide a PIN when they join the meeting.</span></span>
  
## <a name="reset-a-users-pin"></a><span data-ttu-id="b0910-112">ユーザーの PIN をリセットする</span><span class="sxs-lookup"><span data-stu-id="b0910-112">Reset a user's PIN</span></span>

1. <span data-ttu-id="b0910-113">仕事用または学校用のアカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="b0910-113">Sign in with your work or school account.</span></span>
    
2. <span data-ttu-id="b0910-114">**Skype for Business** の管理センター>移動し、左側のナビゲーションで [電話会議]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="b0910-114">Go to the admin center > **Skype for Business**, and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="b0910-115">[ユーザー **] を** クリックし、PIN をリセットするユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="b0910-115">Click on **Users**, select the user that you want to reset the PIN for.</span></span>
    
4. <span data-ttu-id="b0910-116">PIN をリセットした後、PIN が表示されるのは 1 回だけです。</span><span class="sxs-lookup"><span data-stu-id="b0910-116">In the Action pane, under **PIN**, click **Reset**.</span></span>
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-his-or-her-own-pin"></a><span data-ttu-id="b0910-117">ユーザーに自分の PIN をリセットする</span><span class="sxs-lookup"><span data-stu-id="b0910-117">Have a user reset his or her own PIN</span></span>

<span data-ttu-id="b0910-118">ユーザーは、[ダイヤルイン会議] ページの **[PIN** のリセット] オプションを使用して PIN **をリセット** できます。</span><span class="sxs-lookup"><span data-stu-id="b0910-118">A user can reset a PIN by using the **Reset PIN** option on the **Dial-in Conferencing** page.</span></span> <span data-ttu-id="b0910-119">このページには、次の 3 つの方法のいずれかを使用してアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="b0910-119">This page can be accessed in one of three ways:</span></span>

* <span data-ttu-id="b0910-120">ブラウザーで、 [https://mysettings.lync.com/pstncalling](https://mysettings.lync.com/pstncalling)</span><span class="sxs-lookup"><span data-stu-id="b0910-120">In a browser, go to [https://mysettings.lync.com/pstncalling](https://mysettings.lync.com/pstncalling).</span></span>
* <span data-ttu-id="b0910-121">Skype for Business で、[オプション] の横にある [メニューの表示] 矢印をクリックし、[ツール] の [ダイヤルイン会議の設定]  >  **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="b0910-121">In Skype for Business, click the **Show Menu** arrow next to **Options**, and then click **Tools** > **Dial-in Conference Settings**.</span></span>
* <span data-ttu-id="b0910-122">Skype for Businessで、[オプション] をクリックし、左側のメニューで[通話の転送] をクリックし、[その他の通話設定] セクションで [オンラインで設定の編集] をクリック **します**。 </span><span class="sxs-lookup"><span data-stu-id="b0910-122">In Skype for Business, click **Options**, click **Call Forwarding** in the left menu, and then in the **More Call Settings** section, click **Edit settings online**.</span></span> 

## <a name="what-else-should-you-know-about-pins"></a><span data-ttu-id="b0910-123">PIN について知っておくべきその他のこと</span><span class="sxs-lookup"><span data-stu-id="b0910-123">What else should you know about PINs?</span></span>

- <span data-ttu-id="b0910-124">セキュリティ保護のため、PIN のリセット時に PIN は 1 回だけ管理者に表示されます。</span><span class="sxs-lookup"><span data-stu-id="b0910-124">For security purposes, the PIN is only shown to an administrator on one time, when the PIN is reset.</span></span> <span data-ttu-id="b0910-125">管理者によって PIN がリセットされた後 **、SKYPE for Business** 管理センターと、管理者が Windows PowerShell で Get-CsCsOnlineDialInConfencingUser を使用すると、PIN が \*\*\*\*\*\*\*\*\*\*\* として表示されます。</span><span class="sxs-lookup"><span data-stu-id="b0910-125">After the PIN is reset by an administrator, the PIN will be listed as \*\*\*\*\*\*\*\*\*\*\* in the **Skype for Business admin center** and in the results when they use Get-CsCsOnlineDialInConfencingUser in Windows PowerShell.</span></span>
    
- <span data-ttu-id="b0910-126">ユーザーへのメールの自動送信は既定で有効になっています。ユーザーが電話会議で有効になっている場合、または PIN がリセットされた場合、ユーザーは自分の PIN が記載されたメールを受信します。</span><span class="sxs-lookup"><span data-stu-id="b0910-126">Automatically sending emails to users is enabled by default, and users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset.</span></span> <span data-ttu-id="b0910-127">ただし、メールの自動送信を無効にした場合、PIN リセット メールはユーザーに送信されません。PIN 情報を手動でユーザーに送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b0910-127">But if you have disabled automatically sending emails, a PIN reset email won't be sent to a user and you will have to manually send the PIN information to the user.</span></span>
    
- <span data-ttu-id="b0910-p106">会議が始まると、ロビー内のすべてのユーザーは自動的にその会議に参加します。 たとえば、会議が始まる前に 2 人の参加者が会議に参加しようとすると、ロビーで待って保留音を聞くことになります。会議の開催者が自分の PIN を使用して電話で参加すると、会議が始まり、ロビーにいる参加者が会議に参加します。</span><span class="sxs-lookup"><span data-stu-id="b0910-p106">When a meeting starts, all of the users in the lobby will automatically join it. For example, if two participants try to join a meeting before it has been started, they will be put in the lobby and will listen to music on hold, and when the meeting organizer joins using his PIN via phone, the meeting will start and the participants in the lobby will join the meeting.</span></span>
    
- <span data-ttu-id="b0910-130">既定の設定では、匿名の発信者による会議の開始を許可しません。</span><span class="sxs-lookup"><span data-stu-id="b0910-130">The default setting is to not allow a meeting to be started by anonymous callers.</span></span>
    
- <span data-ttu-id="b0910-131">ユーザーを電話会議用に有効にした場合、既定では、ユーザーは会議情報と PIN を含むメールを送信します。</span><span class="sxs-lookup"><span data-stu-id="b0910-131">When you enable a user for audio conferencing, by default they are sent emails that include conferencing information and their PIN.</span></span> <span data-ttu-id="b0910-132">PIN がリセットされた場合、ユーザーに設定されているプライマリ SMTP アドレス (エイリアス) に新しい PIN がメールで送信されるので、ユーザーは Microsoft 365 または Office 365 メールボックスを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b0910-132">The user must have a Microsoft 365 or Office 365 mailbox, because when a PIN is reset, a new PIN will be sent to the user in email to their primary SMTP address (alias) that is set for the user.</span></span>
    
- <span data-ttu-id="b0910-133">電話会議をセットアップするときに、組織内の PIN に必要な数字を設定します。</span><span class="sxs-lookup"><span data-stu-id="b0910-133">When you set up audio conferencing, you set the digits that are required for the PINs in your organization.</span></span> <span data-ttu-id="b0910-134">PIN は 4 ~ 12 桁で指定できます。既定値は 5 です。</span><span class="sxs-lookup"><span data-stu-id="b0910-134">PINs can be from 4 to 12 digits - the default is 5.</span></span> <span data-ttu-id="b0910-135">PIN の長さの設定を変更した場合、この設定は新しく生成された PIN にのみ適用され、電話会議で有効になっている既存のユーザーの PIN 設定には適用されません。</span><span class="sxs-lookup"><span data-stu-id="b0910-135">If you change the PIN length setting, the setting is only applied on newly generated PINs and isn't applied to the PIN setting for existing users that are enabled for audio conferencing.</span></span> <span data-ttu-id="b0910-136">「 [電話会議の PIN の長さを設定する」を参照してください](Set-the-PIN-length-for-Audio-Conferencing-meetings.md)。</span><span class="sxs-lookup"><span data-stu-id="b0910-136">See [Set the length of the PIN for Audio Conferencing meetings](Set-the-PIN-length-for-Audio-Conferencing-meetings.md).</span></span>
    
- <span data-ttu-id="b0910-137">既定では、メールはユーザーの Microsoft 365 Office 365 プライマリ SMTP アドレスに設定されます。</span><span class="sxs-lookup"><span data-stu-id="b0910-137">The email by default will be set to the Microsoft 365 or Office 365 primary SMTP address of the user.</span></span> <span data-ttu-id="b0910-138">Microsoft 365 以外のアドレスまたは Office 365 以外のアドレス (Hotmail や MSN のメール アドレスなど) にメールを送信できます。</span><span class="sxs-lookup"><span data-stu-id="b0910-138">You can send an email to a non-Microsoft 365 or non-Office 365 address, such as a Hotmail or MSN email address.</span></span> <span data-ttu-id="b0910-139">既定のメール アドレスを上書きするには、既定のメール Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="b0910-139">You can override the default email address by using Windows PowerShell.</span></span> <span data-ttu-id="b0910-140">これは、ユーザーが Microsoft 365 または 365 に Exchange メールボックスを持Office便利です。</span><span class="sxs-lookup"><span data-stu-id="b0910-140">This is useful if the users don't have an Exchange mailbox in Microsoft 365 or Office 365.</span></span>
    
- <span data-ttu-id="b0910-141">メールが送信される既定のユーザー アドレスを上書きするには、テナント管理者は次のコマンドレットを使用できます: Set-CsOnlineDialInConferencingUser -amos.marble -ResetLeaderPIN -SendEmail -SendEmailToAddress "u@hotmail.com。</span><span class="sxs-lookup"><span data-stu-id="b0910-141">To override the default user address where the email is sent, the tenant admin can use the following cmdlet: Set-CsOnlineDialInConferencingUser -amos.marble -ResetLeaderPIN -SendEmail -SendEmailToAddress "u@hotmail.com".</span></span> <span data-ttu-id="b0910-142">ユーザーのメール アドレスを上書きするには、SendEmail パラメーターが必要です。</span><span class="sxs-lookup"><span data-stu-id="b0910-142">The SendEmail parameter is required to override the email address of the user.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="b0910-143">Windows PowerShell での管理方法について</span><span class="sxs-lookup"><span data-stu-id="b0910-143">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="b0910-144">時間を節約したり、自動化したりするには、[Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) コマンドレットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="b0910-144">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) cmdlet.</span></span>
    
- <span data-ttu-id="b0910-145">次のコマンドレットを実行すると、Amos Marble の PIN を設定できます。</span><span class="sxs-lookup"><span data-stu-id="b0910-145">You can set the PIN for Amos Marble by running:</span></span>
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com -ResetLeaderPIN
  ```

- <span data-ttu-id="b0910-146">Windows PowerShellは、ユーザーの管理と、ユーザーに許可する操作と許可しない操作の管理に使います。</span><span class="sxs-lookup"><span data-stu-id="b0910-146">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="b0910-147">Windows PowerShell を使用すると、単一の管理ポイントを使用して Microsoft 365 または Office 365 を管理し、複数のタスクを実行する必要があるときに日常業務を簡略化できます。</span><span class="sxs-lookup"><span data-stu-id="b0910-147">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="b0910-148">Windows PowerShell の使用を開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0910-148">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="b0910-149">Microsoft 365 または Office 365 PowerShell を使用する必要がある理由</span><span class="sxs-lookup"><span data-stu-id="b0910-149">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="b0910-150">[Microsoft 365 または Office 365 を管理するための最適Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="b0910-150">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
- <span data-ttu-id="b0910-p112">多くのユーザーの設定を同時に変更するときなどは、Microsoft 365 管理センターのみを使用するよりも、Windows PowerShell を使用した方が、速度、わかりやすさ、生産性の点で多くのメリットがあります。次のトピックで、これらの利点を説明します。</span><span class="sxs-lookup"><span data-stu-id="b0910-p112">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making settings changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="b0910-153">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="b0910-153">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    [<span data-ttu-id="b0910-154">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="b0910-154">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="b0910-155">Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行</span><span class="sxs-lookup"><span data-stu-id="b0910-155">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > <span data-ttu-id="b0910-p113">Skype for Business Online 用の Windows PowerShell モジュールがあれば、Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成できます。このモジュールは、64 ビット版のコンピューターでのみサポートされており、「[Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688)」の Microsoft ダウンロード センターからダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="b0910-p113">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="b0910-158">関連項目</span><span class="sxs-lookup"><span data-stu-id="b0910-158">Related topics</span></span>

[<span data-ttu-id="b0910-159">ユーザーの会議 ID をリセットする</span><span class="sxs-lookup"><span data-stu-id="b0910-159">Reset a conference ID for a user</span></span>](reset-a-conference-id-for-a-user.md)