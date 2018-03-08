---
title: "ユーザーの音声会議の PIN をリセットします。"
mms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 67866a47-89c1-4593-8766-3a68777e2be6
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "ピンに関する重要事項とユーザー向けにリセットする方法を確認します。 "
ms.openlocfilehash: 1deacb0a00ccef585e220752ea94c678d1d5a4d3
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="reset-the-audio-conferencing-pin-for-a-user"></a><span data-ttu-id="a1f64-103">ユーザーの音声会議の PIN をリセットします。</span><span class="sxs-lookup"><span data-stu-id="a1f64-103">Reset the Audio Conferencing PIN for a user</span></span>

<span data-ttu-id="a1f64-p101">PIN は、各 Skype は電話会議用に有効なビジネスや Microsoft チームのユーザー用に作成される数値のコードです。電話会議の Pin が使用会議の開催者を特定してれており、会議の開催者は、電話で会議を開始することを許可します。会議を開始する Skype for Business または Microsoft チームのアプリを使用する場合、暗証番号 (pin) は必要ありません。ユーザーが自分の PIN を忘れた、電話会議が有効なときに送信されたメールで見つからない場合は、管理者が自分の PIN をリセットする必要があります。ユーザーが自分の PIN を再設定できません。</span><span class="sxs-lookup"><span data-stu-id="a1f64-p101">A PIN is a code made up of numbers that is created for each Skype for Business and Microsoft Teams user who is enabled for audio conferencing. Audio conferencing PINs are used by meeting organizers to identify that they are the meeting organizer and allow them to start a meeting over the phone. If they use the Skype for Business or Microsoft Teams app to start the meeting, a PIN isn't required. If users forget their PIN and they can't find it in the email that was sent to them when they were enabled for audio conferencing, an administrator will need to reset their PIN. A user can't reset their own PIN.</span></span>
  
<span data-ttu-id="a1f64-p102">認証されたユーザーに Business または Microsoft チームのアプリや、開催者が自分の PIN と、電話で参加するときに、Skype を使用して参加するときは、会議を開始することができます。会議に必要と PIN を開始する、電話で参加はロビーとは、ユーザー、会議まで保留中の音楽を聴くを開始します。会議の開催者が、電話で会議を開始する暗証番号 (pin) を必要としない場合は、会議に参加するとき、暗証番号 (pin) を発信者を求められるされません。</span><span class="sxs-lookup"><span data-stu-id="a1f64-p102">Meetings can be started when an authenticated user joins using a Skype for Business or Microsoft Teams app or when the organizer joins with his or her PIN over the phone. When a meeting requires a PIN to start, users who join over the phone will be placed in the lobby and will listen to music on hold until the meeting starts. If the organizer of a meeting doesn't require a PIN to start the meeting over the phone, then callers won't be asked to provide a PIN when they join the meeting.</span></span>
  
## <a name="reset-a-conference-organizers-pin"></a><span data-ttu-id="a1f64-112">会議の開催者の PIN をリセットします。</span><span class="sxs-lookup"><span data-stu-id="a1f64-112">Reset a conference organizer's PIN</span></span>

1. <span data-ttu-id="a1f64-113">職場または学校のアカウントで Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="a1f64-113">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="a1f64-114">**Office 365 管理センター**に移動 > **Skype for Business**の場合は、左のナビゲーションで [**電話会議**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a1f64-114">Go to the **Office 365 admin center** > **Skype for Business**, and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="a1f64-115">[**ユーザー**] をクリックしての PIN をリセットするユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="a1f64-115">Click on **Users**, select the user that you want to reset the PIN for.</span></span>
    
4. <span data-ttu-id="a1f64-116">操作ウィンドウで、**暗証番号 (pin)**、[**リセット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a1f64-116">In the Action pane, under **PIN**, click **Reset**.</span></span>
    
## <a name="what-else-should-you-know-about-pins"></a><span data-ttu-id="a1f64-117">ピンについて他を把握してする必要がありますか。</span><span class="sxs-lookup"><span data-stu-id="a1f64-117">What else should you know about PINs?</span></span>

- <span data-ttu-id="a1f64-p103">セキュリティのために、PIN にのみ表示管理者 PIN をリセットすると、1 つの時間にします。管理者による PIN をリセットすると、として、暗証番号 (pin) が表示されます。 **Skype for Business 管理センター**で、Windows PowerShell で取得 CsCsOnlineDialInConfencingUser を使用する場合の結果にします。</span><span class="sxs-lookup"><span data-stu-id="a1f64-p103">For security purposes, the PIN is only shown to an administrator on one time, when the PIN is reset. After the PIN is reset by an administrator, the PIN will be listed as \*\*\*\*\*\*\*\*\*\*\* in the **Skype for Business admin center** and in the results when they use Get-CsCsOnlineDialInConfencingUser in Windows PowerShell.</span></span>
    
- <span data-ttu-id="a1f64-p104">既定では、有効になっているユーザーにメールを自動的に送信して、電話会議の PIN をリセットするときの有効なしているとき、ユーザーは自分の PIN を含む電子メールに届きます。自動的に無効にした場合、メールを送信する PIN リセットのメールをユーザーに送られませんし、手動で PIN 情報をユーザーに送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a1f64-p104">Automatically sending emails to users is enabled by default, and users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset. But if you have disabled automatically sending emails, a PIN reset email won't be sent to a user and you will have to manually send the PIN information to the user.</span></span>
    
- <span data-ttu-id="a1f64-p105">会議を起動すると、すべてのユーザーがロビー内で自動的に参加します。たとえば場合は、次の 2 つの参加者が開始する前に、会議に参加しようとするがロビー内で配置されます保留中の音楽を聴くし、会議の開催者は、電話で自分の PIN を使用して参加する場合、会議が開始されますロビー内で参加者に参加 会議します。</span><span class="sxs-lookup"><span data-stu-id="a1f64-p105">When a meeting starts, all of the users in the lobby will automatically join it. For example, if two participants try to join a meeting before it has been started, they will be put in the lobby and will listen to music on hold, and when the meeting organizer joins using his PIN via phone, the meeting will start and the participants in the lobby will join the meeting.</span></span>
    
- <span data-ttu-id="a1f64-124">匿名の呼び出しが開始されるように会議に参加を許可する既定の設定。</span><span class="sxs-lookup"><span data-stu-id="a1f64-124">The default setting to not allow a meeting to be started by anonymous callers.</span></span>
    
- <span data-ttu-id="a1f64-p106">電話会議のユーザーを有効にしたときに既定で、送信された会議の情報と自分の PIN を含むメールします。ユーザーは、PIN をリセットすると、新しい PIN がユーザーのプライマリ SMTP アドレス (alias) ユーザー用に設定されているへのメールに送られますので、Office 365 メールボックスが必要です。</span><span class="sxs-lookup"><span data-stu-id="a1f64-p106">When you enable a user for audio conferencing, by default they are sent emails that include conferencing information and their PIN. The user must have an Office 365 mailbox, because when a PIN is reset, a new PIN will be sent to the user in email to their primary SMTP address (alias) that is set for the user.</span></span>
    
- <span data-ttu-id="a1f64-p107">電話会議を設定する際に、組織内のピンのために必要な数字を設定します。Pin は 4 ~ 12 桁に必要]: 既定値は 5 します。PIN の長さの設定を変更すると、設定は、新しく生成されたピンの位置にのみ適用し、電話会議を有効になっている既存のユーザーに対して PIN の設定に適用されないです。[電話会議の会議の PIN の長さを設定する](Set-the-PIN-length-for-Audio-Conferencing-meetings.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a1f64-p107">When you set up audio conferencing, you set the digits that are required for the PINs in your organization. PINs can be from 4 to 12 digits - the default is 5. If you change the PIN length setting, the setting is only applied on newly generated PINs and isn't applied to the PIN setting for existing users that are enabled for audio conferencing. See [Set the length of the PIN for Audio Conferencing meetings](Set-the-PIN-length-for-Audio-Conferencing-meetings.md).</span></span>
    
- <span data-ttu-id="a1f64-p108">既定のメール ユーザーの Office 365 のプライマリ SMTP アドレスに設定されます。Hotmail などの Office 365 以外のアドレスまたは MSN メール アドレスにメールを送信できます。Windows PowerShell を使用して既定のメール アドレスを上書きできます。これは、ユーザーが Office 365 の Exchange メールボックスを持っていない場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="a1f64-p108">The email by default will be set to the Office 365 primary SMTP address of the user. You can send an email to a non-Office 365 address such as a Hotmail or MSN email address. You can override the default email address by using Windows PowerShell. This is useful if the users don't have an Exchange mailbox in Office 365.</span></span>
    
- <span data-ttu-id="a1f64-p109">電子メールを送信する先の既定のユーザーのアドレスを上書きするには、テナント管理者が、次のコマンドレットを使用できます。 セット CsOnlineDialInConferencingUser-amos.marble - ResetLeaderPIN-SendEmail SendEmailToAddress"u@hotmail.com"します。ユーザーのメール アドレスを上書きするため、SendEmail パラメーターが必要です。</span><span class="sxs-lookup"><span data-stu-id="a1f64-p109">To override the default user address where the email is sent, the tenant admin can use the following cmdlet: Set-CsOnlineDialInConferencingUser -amos.marble -ResetLeaderPIN -SendEmail -SendEmailToAddress "u@hotmail.com". The SendEmail parameter is required to override the email address of the user.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="a1f64-137">Windows PowerShell で管理する方法を知りたいとしていますか。</span><span class="sxs-lookup"><span data-stu-id="a1f64-137">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="a1f64-138">時間を節約し、自動化したりには、[セット CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 )コマンドレットを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="a1f64-138">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) cmdlet.</span></span>
    
- <span data-ttu-id="a1f64-139">実行して Amos 大理石の PIN を設定できます。</span><span class="sxs-lookup"><span data-stu-id="a1f64-139">You can set the PIN for Amos Marble by running:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com -ResetLeaderPIN
  ```

- <span data-ttu-id="a1f64-p110">Windows PowerShell がユーザーを管理するユーザーを許可または使用できません。Windows PowerShell で複数のタスクを実行するがある場合、日常業務を簡素化する管理の 1 つのポイントを使用して Office 365 を管理できます。Windows PowerShell で開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a1f64-p110">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="a1f64-143">Office 365 PowerShell を使用する必要がある理由</span><span class="sxs-lookup"><span data-stu-id="a1f64-143">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="a1f64-144">Windows PowerShell で Office 365 を管理する最善の方法</span><span class="sxs-lookup"><span data-stu-id="a1f64-144">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="a1f64-p111">Windows PowerShell では多くの利点速度、わかりやすいように、および生産性でのみ実行しようとする設定の変更、多くのユーザーに一度になど、Office 365 管理センターを使用します。次のトピックでこれらの利点について学習します。</span><span class="sxs-lookup"><span data-stu-id="a1f64-p111">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="a1f64-147">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="a1f64-147">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [<span data-ttu-id="a1f64-148">Windows PowerShell を使用して、Skype for Business Online の管理するには</span><span class="sxs-lookup"><span data-stu-id="a1f64-148">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="a1f64-149">Windows PowerShell を使用して、共通の Skype for Business Online の管理タスクを実行するには</span><span class="sxs-lookup"><span data-stu-id="a1f64-149">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="a1f64-p112">Skype for Business Online 用の Windows PowerShell モジュールを使用すると、Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成することができます。このモジュールでは、64 ビット コンピューター以外では、Microsoft ダウンロード センターからダウンロードできます[Skype for Business Online 用の Windows PowerShell モジュール](https://go.microsoft.com/fwlink/?LinkId=294688)。</span><span class="sxs-lookup"><span data-stu-id="a1f64-p112">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="a1f64-152">関連トピック</span><span class="sxs-lookup"><span data-stu-id="a1f64-152">Related topics</span></span>

[<span data-ttu-id="a1f64-153">ユーザーの会議 ID をリセットします。</span><span class="sxs-lookup"><span data-stu-id="a1f64-153">Reset a conference ID for a user</span></span>](reset-a-conference-id-for-a-user.md)
