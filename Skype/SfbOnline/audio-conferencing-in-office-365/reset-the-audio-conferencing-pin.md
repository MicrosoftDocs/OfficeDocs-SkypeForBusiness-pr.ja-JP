---
title: Skype for Business Online で電話会議の PIN をリセットする
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
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Pin について知っておくべきことと、Skype for Business Online で Pin をリセットする方法について説明します。 '
ms.openlocfilehash: a00c36475059a05bb7cf3a9057920b63a09e9a43
ms.sourcegitcommit: afc7edd03f4baa1d75f9642d4dbce767fec69b00
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "40962695"
---
# <a name="reset-the-audio-conferencing-pin-in-skype-for-business-online"></a><span data-ttu-id="bd83a-103">Skype for Business Online で電話会議の PIN をリセットする</span><span class="sxs-lookup"><span data-stu-id="bd83a-103">Reset the Audio Conferencing PIN in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="bd83a-104">Microsoft Teams で電話会議の pin をリセットする方法については、「 [Microsoft teams で電話会議の pin をリセットする](/MicrosoftTeams/reset-the-audio-conferencing-pin-in-teams)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd83a-104">For information about resetting Audio Conferencing PINs in Microsoft Teams, see [Reset the Audio Conferencing PIN in Microsoft Teams](/MicrosoftTeams/reset-the-audio-conferencing-pin-in-teams).</span></span>

<span data-ttu-id="bd83a-105">PIN は、電話会議用に有効になっている各 Skype for Business ユーザー用に作成された番号で構成されるコードです。</span><span class="sxs-lookup"><span data-stu-id="bd83a-105">A PIN is a code made up of numbers that is created for each Skype for Business user who is enabled for audio conferencing.</span></span> <span data-ttu-id="bd83a-106">電話会議の Pin は、会議の開催者が会議の開催者であり、電話で会議を開始できることを示すために使用されます。</span><span class="sxs-lookup"><span data-stu-id="bd83a-106">Audio conferencing PINs are used by meeting organizers to identify that they are the meeting organizer and allow them to start a meeting over the phone.</span></span> <span data-ttu-id="bd83a-107">Skype for Business アプリを使用して会議を開始する場合、PIN は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="bd83a-107">If they use the Skype for Business app to start the meeting, a PIN isn't required.</span></span> <span data-ttu-id="bd83a-108">ユーザーが PIN を忘れた場合、電話会議用に有効にしたときに送信されたメールでその PIN が見つからない場合は、管理者が自分の pin をリセットするか、自分の pin をリセットすることができます。</span><span class="sxs-lookup"><span data-stu-id="bd83a-108">If users forget their PIN and they can't find it in the email that was sent to them when they were enabled for audio conferencing, an administrator can reset their PIN, or they can reset their own PIN.</span></span>
  
<span data-ttu-id="bd83a-109">認証されたユーザーが Skype for Business アプリを使用して参加している場合、または開催者が電話を介して自分の PIN を使って参加している場合、会議を開始できます。</span><span class="sxs-lookup"><span data-stu-id="bd83a-109">Meetings can be started when an authenticated user joins using the Skype for Business app or when the organizer joins with his or her PIN over the phone.</span></span> <span data-ttu-id="bd83a-110">会議の開始に PIN が必要な場合、電話で参加するユーザーはロビーで待機し、会議が開始するまで保留音を聞くことになります。</span><span class="sxs-lookup"><span data-stu-id="bd83a-110">When a meeting requires a PIN to start, users who join over the phone will be placed in the lobby and will listen to music on hold until the meeting starts.</span></span> <span data-ttu-id="bd83a-111">会議の開催者が、電話で会議を開始するための PIN を要求しない場合、発信者は会議に参加しようとするときに PIN の提示を求められません。</span><span class="sxs-lookup"><span data-stu-id="bd83a-111">If the organizer of a meeting doesn't require a PIN to start the meeting over the phone, then callers won't be asked to provide a PIN when they join the meeting.</span></span>
  
## <a name="reset-a-users-pin"></a><span data-ttu-id="bd83a-112">ユーザーの PIN をリセットする</span><span class="sxs-lookup"><span data-stu-id="bd83a-112">Reset a user's PIN</span></span>

1. <span data-ttu-id="bd83a-113">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="bd83a-113">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="bd83a-114">**Skype For business**> 管理センターに移動し、左側のナビゲーションで [**電話会議**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bd83a-114">Go to the admin center > **Skype for Business**, and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="bd83a-115">[**ユーザー**] をクリックし、PIN をリセットするユーザーを選びます。</span><span class="sxs-lookup"><span data-stu-id="bd83a-115">Click on **Users**, select the user that you want to reset the PIN for.</span></span>
    
4. <span data-ttu-id="bd83a-116">PIN をリセットした後、PIN が表示されるのは 1 回だけです。\*\*\*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="bd83a-116">In the Action pane, under **PIN**, click **Reset**.</span></span>
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-his-or-her-own-pin"></a><span data-ttu-id="bd83a-117">ユーザーが自分の PIN をリセットする</span><span class="sxs-lookup"><span data-stu-id="bd83a-117">Have a user reset his or her own PIN</span></span>

<span data-ttu-id="bd83a-118">ユーザーは、**ダイヤルイン会議**ページの [ **pin のリセット**] オプションを使用して pin をリセットできます。</span><span class="sxs-lookup"><span data-stu-id="bd83a-118">A user can reset a PIN by using the **Reset PIN** option on the **Dial-in Conferencing** page.</span></span> <span data-ttu-id="bd83a-119">このページにアクセスするには、次の3つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="bd83a-119">This page can be accessed in one of three ways:</span></span>

* <span data-ttu-id="bd83a-120">ブラウザーで、に[https://mysettings.lync.com/pstncalling](https://mysettings.lync.com/pstncalling)アクセスします。</span><span class="sxs-lookup"><span data-stu-id="bd83a-120">In a browser, go to [https://mysettings.lync.com/pstncalling](https://mysettings.lync.com/pstncalling).</span></span>
* <span data-ttu-id="bd83a-121">Skype for business で、[**オプション**] の横にある [**メニューを表示する]** 矢印をクリックし、[**ツール** > ] の [**ダイヤルイン会議の設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bd83a-121">In Skype for Business, click the **Show Menu** arrow next to **Options**, and then click **Tools** > **Dial-in Conference Settings**.</span></span>
* <span data-ttu-id="bd83a-122">Skype for Business で、[**オプション**] をクリックし、左側のメニューの [**着信の転送**] をクリックします。次に、[**通話の詳細設定**] セクションで、[**オンラインで設定を編集**する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bd83a-122">In Skype for Business, click **Options**, click **Call Forwarding** in the left menu, and then in the **More Call Settings** section, click **Edit settings online**.</span></span> 

## <a name="what-else-should-you-know-about-pins"></a><span data-ttu-id="bd83a-123">PIN について知っておくべきその他のこと</span><span class="sxs-lookup"><span data-stu-id="bd83a-123">What else should you know about PINs?</span></span>

- <span data-ttu-id="bd83a-124">セキュリティ保護のため、PIN のリセット時に PIN は 1 回だけ管理者に表示されます。</span><span class="sxs-lookup"><span data-stu-id="bd83a-124">For security purposes, the PIN is only shown to an administrator on one time, when the PIN is reset.</span></span> <span data-ttu-id="bd83a-125">PIN が管理者によってリセットされた後は、Windows PowerShell で CsCsOnlineDialInConfencingUser を使用すると、 **Skype For business 管理センター**と結果に pin が \* \* \* \* \* \* \* \* \* \* \* \* \* と表示されます。</span><span class="sxs-lookup"><span data-stu-id="bd83a-125">After the PIN is reset by an administrator, the PIN will be listed as \*\*\*\*\*\*\*\*\*\*\* in the **Skype for Business admin center** and in the results when they use Get-CsCsOnlineDialInConfencingUser in Windows PowerShell.</span></span>
    
- <span data-ttu-id="bd83a-126">ユーザーにメールを自動的に送信する機能は既定で有効になっています。電話会議が有効になっているか、PIN がリセットされると、ユーザーは PIN を含むメールを受信します。</span><span class="sxs-lookup"><span data-stu-id="bd83a-126">Automatically sending emails to users is enabled by default, and users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset.</span></span> <span data-ttu-id="bd83a-127">ただし、メールの自動送信を無効にした場合、PIN のリセットメールはユーザーに送信されず、ユーザーに PIN 情報を手動で送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd83a-127">But if you have disabled automatically sending emails, a PIN reset email won't be sent to a user and you will have to manually send the PIN information to the user.</span></span>
    
- <span data-ttu-id="bd83a-p106">会議が始まると、ロビー内のすべてのユーザーは自動的にその会議に参加します。 たとえば、会議が始まる前に 2 人の参加者が会議に参加しようとすると、ロビーで待って保留音を聞くことになります。会議の開催者が自分の PIN を使用して電話で参加すると、会議が始まり、ロビーにいる参加者が会議に参加します。</span><span class="sxs-lookup"><span data-stu-id="bd83a-p106">When a meeting starts, all of the users in the lobby will automatically join it. For example, if two participants try to join a meeting before it has been started, they will be put in the lobby and will listen to music on hold, and when the meeting organizer joins using his PIN via phone, the meeting will start and the participants in the lobby will join the meeting.</span></span>
    
- <span data-ttu-id="bd83a-130">既定の設定では、匿名の発信者が会議を開始することは許可されていません。</span><span class="sxs-lookup"><span data-stu-id="bd83a-130">The default setting is to not allow a meeting to be started by anonymous callers.</span></span>
    
- <span data-ttu-id="bd83a-131">電話会議のユーザーを有効にすると、既定では、会議の情報とその PIN を含むメールが送信されます。</span><span class="sxs-lookup"><span data-stu-id="bd83a-131">When you enable a user for audio conferencing, by default they are sent emails that include conferencing information and their PIN.</span></span> <span data-ttu-id="bd83a-132">PIN がリセットされると、ユーザーに対して設定されているプライマリ SMTP アドレス (エイリアス) 宛てに、ユーザーに Office 365 メールボックスがある必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd83a-132">The user must have an Office 365 mailbox, because when a PIN is reset, a new PIN will be sent to the user in email to their primary SMTP address (alias) that is set for the user.</span></span>
    
- <span data-ttu-id="bd83a-133">電話会議をセットアップするときには、組織内の Pin に必要な数字を設定します。</span><span class="sxs-lookup"><span data-stu-id="bd83a-133">When you set up audio conferencing, you set the digits that are required for the PINs in your organization.</span></span> <span data-ttu-id="bd83a-134">Pin は 4 ~ 12 桁にすることができます。既定値は5です。</span><span class="sxs-lookup"><span data-stu-id="bd83a-134">PINs can be from 4 to 12 digits - the default is 5.</span></span> <span data-ttu-id="bd83a-135">PIN の長さの設定を変更した場合、設定は新しく生成された Pin にのみ適用され、電話会議用に有効になっている既存のユーザーの PIN の設定には適用されません。</span><span class="sxs-lookup"><span data-stu-id="bd83a-135">If you change the PIN length setting, the setting is only applied on newly generated PINs and isn't applied to the PIN setting for existing users that are enabled for audio conferencing.</span></span> <span data-ttu-id="bd83a-136">「[電話会議の PIN の長さを設定](Set-the-PIN-length-for-Audio-Conferencing-meetings.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd83a-136">See [Set the length of the PIN for Audio Conferencing meetings](Set-the-PIN-length-for-Audio-Conferencing-meetings.md).</span></span>
    
- <span data-ttu-id="bd83a-137">既定では、メールはユーザーの Office 365 プライマリ SMTP アドレスに設定されます。</span><span class="sxs-lookup"><span data-stu-id="bd83a-137">The email by default will be set to the Office 365 primary SMTP address of the user.</span></span> <span data-ttu-id="bd83a-138">Hotmail または MSN のメールアドレスなど、Office 以外の365のアドレスにメールを送信することができます。</span><span class="sxs-lookup"><span data-stu-id="bd83a-138">You can send an email to a non-Office 365 address such as a Hotmail or MSN email address.</span></span> <span data-ttu-id="bd83a-139">Windows PowerShell を使用して、既定のメールアドレスを上書きできます。</span><span class="sxs-lookup"><span data-stu-id="bd83a-139">You can override the default email address by using Windows PowerShell.</span></span> <span data-ttu-id="bd83a-140">これは、ユーザーが Office 365 の Exchange メールボックスを持っていない場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="bd83a-140">This is useful if the users don't have an Exchange mailbox in Office 365.</span></span>
    
- <span data-ttu-id="bd83a-141">メールを送信する既定のユーザーアドレスを上書きするには、テナント管理者が次のコマンドレットを使用できます: Get-csonlinedialinconferencinguser-amos-SendEmail-SendEmailToAddress "u@hotmail.com"</span><span class="sxs-lookup"><span data-stu-id="bd83a-141">To override the default user address where the email is sent, the tenant admin can use the following cmdlet: Set-CsOnlineDialInConferencingUser -amos.marble -ResetLeaderPIN -SendEmail -SendEmailToAddress "u@hotmail.com".</span></span> <span data-ttu-id="bd83a-142">ユーザーのメールアドレスを上書きするには、SendEmail パラメーターが必要です。</span><span class="sxs-lookup"><span data-stu-id="bd83a-142">The SendEmail parameter is required to override the email address of the user.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="bd83a-143">Windows PowerShell での管理方法について</span><span class="sxs-lookup"><span data-stu-id="bd83a-143">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="bd83a-144">時間を節約したり、自動化したりするには、[Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) コマンドレットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="bd83a-144">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) cmdlet.</span></span>
    
- <span data-ttu-id="bd83a-145">次のコマンドレットを実行すると、Amos Marble の PIN を設定できます。</span><span class="sxs-lookup"><span data-stu-id="bd83a-145">You can set the PIN for Amos Marble by running:</span></span>
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com -ResetLeaderPIN
  ```

- <span data-ttu-id="bd83a-p111">Windows PowerShell で行うのは、ユーザーを管理し、ユーザーに何を許可して何を禁止するかを管理することです。Windows PowerShell を利用すると、Office 365 の管理を 1 か所で行うことができるので、複数のタスクを担当する管理者の日常業務を単純化できます。Windows PowerShell の使用を開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd83a-p111">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="bd83a-149">Office 365 PowerShell を使用する必要がある理由</span><span class="sxs-lookup"><span data-stu-id="bd83a-149">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="bd83a-150">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="bd83a-150">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="bd83a-151">Windows PowerShell には、Microsoft 365 管理センターを使用する場合にのみ、速度、簡素化、生産性を高めるためのさまざまな利点があります。たとえば、多くのユーザーの設定を一度に変更する場合です。</span><span class="sxs-lookup"><span data-stu-id="bd83a-151">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="bd83a-152">次のトピックで、これらの利点を説明します。</span><span class="sxs-lookup"><span data-stu-id="bd83a-152">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="bd83a-153">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="bd83a-153">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [<span data-ttu-id="bd83a-154">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="bd83a-154">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="bd83a-155">Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行</span><span class="sxs-lookup"><span data-stu-id="bd83a-155">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="bd83a-p113">Skype for Business Online 用の Windows PowerShell モジュールがあれば、Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成できます。このモジュールは、64 ビット版のコンピューターでのみサポートされており、「[Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688)」の Microsoft ダウンロード センターからダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="bd83a-p113">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="bd83a-158">関連項目</span><span class="sxs-lookup"><span data-stu-id="bd83a-158">Related topics</span></span>

[<span data-ttu-id="bd83a-159">ユーザーの会議 ID をリセットする</span><span class="sxs-lookup"><span data-stu-id="bd83a-159">Reset a conference ID for a user</span></span>](reset-a-conference-id-for-a-user.md)
