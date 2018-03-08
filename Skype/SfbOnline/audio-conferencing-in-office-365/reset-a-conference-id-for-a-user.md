---
title: "ユーザーの会議 ID をリセットします。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
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
description: "ユーザーを再設定する手順は会議 ID、会議の更新と移行ツールの会議へのリンクを取得するかを説明します。 "
ms.openlocfilehash: ba76f3afb5d92dadc66d09e07aa16d3589f57e4d
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="reset-a-conference-id-for-a-user"></a><span data-ttu-id="35fb7-103">ユーザーの会議 ID をリセットします。</span><span class="sxs-lookup"><span data-stu-id="35fb7-103">Reset a conference ID for a user</span></span>

<span data-ttu-id="35fb7-p101">組織動的会議 Id を有効にされていない、プロバイダーとして Microsoft を使って音声会議に Skype for Business または Microsoft チームのユーザーが有効にすると、静的会議 ID が自動的に作成します。この会議 ID が会議出席依頼と発信者が会議にコールインするのに使用できるダイヤルイン電話番号の下部に含まれています。ユーザーは、電話番号をダイヤルするときに、会議の自動応答はに対して発信者を会議に参加ができるように、この会議 ID を入力を求められます。</span><span class="sxs-lookup"><span data-stu-id="35fb7-p101">When your organizations hasn't been enabled for dynamic conference IDs, a static conference ID is automatically created when a Skype for Business or Microsoft Teams user is enabled for Audio Conferencing using Microsoft as the provider. This conference ID is included at the bottom of meeting invitations along with the dial-in phone numbers that can be used by callers to call in to a meeting. When the user dials the phone number, the auto attendant for the meeting will ask the caller to enter this conference ID so they can attend the meeting.</span></span>
  
> [!NOTE]
> <span data-ttu-id="35fb7-p102">会議プロバイダーが Microsoft の場合は、ユーザーの会議 Id が既定で動的のみ] に設定されています。残念ながら、Skype for Business 管理センター」または「Windows Powershell を使用してに変更することはできません。Microsoft サポートに連絡する必要があります。</span><span class="sxs-lookup"><span data-stu-id="35fb7-p102">If your conferencing provider is Microsoft, your users' conference IDs are set to Dynamic Only by default. Unfortunately, you won't be able to change it in the Skype for Business Admin Center or using Windows Powershell. You will have to contact Microsoft support.</span></span> 
  
<span data-ttu-id="35fb7-p103">静的な Id は、組織内のユーザーをランダムな番号を保存したくない場合に使用します。特定の番号を選択したり、覚えやすいものを使用することができます。動的会議 Id を使用する場合各会議ユーザーのスケジュールが取得割り当て会議の一意の id。場合は、割り当てる静的会議 Id、[ここ](using-audio-conferencing-dynamic-ids-in-your-organization.md)ではなく動的します。</span><span class="sxs-lookup"><span data-stu-id="35fb7-p103">Static IDs are used when people in your organization don't want to remember a random number; they can select a certain number or use one that's easy to remember. When dynamic conference IDs are used, each meeting that a user schedules will get assigned a unique conference ID. If you want to assign dynamic rather than static conference IDs, [go here](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span></span>
  
<span data-ttu-id="35fb7-p104">会議 Id が自動的に設定だけ Skype for Business や Microsoft チームのユーザーが電話会議用に有効に、電話会議プロバイダーとして Microsoft を使用してです。サードパーティ電話会議プロバイダー (ACP) を使用しているユーザーの会議 ID をリセットする必要がある場合は、[プロパティ] ページで、ユーザーの会議 ID を手動で入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="35fb7-p104">Conference IDs are only automatically set only for Skype for Business and Microsoft Teams users enabled for Audio Conferencing using Microsoft as their audio conferencing provider. If you need to reset a conference ID for a user who is using a third-party audio conferencing provider (ACP), you will need to manually enter a conference ID on the properties page for the user.</span></span>
  
## <a name="resetting-the-conference-id-for-a-user"></a><span data-ttu-id="35fb7-115">ユーザーの会議 ID をリセットします。</span><span class="sxs-lookup"><span data-stu-id="35fb7-115">Resetting the conference ID for a user</span></span>

1. <span data-ttu-id="35fb7-116">職場または学校のアカウントで Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="35fb7-116">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="35fb7-117">**Office 365 管理センター**に移動 > **Skype for Business**します。</span><span class="sxs-lookup"><span data-stu-id="35fb7-117">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="35fb7-118">**Skype for Business 管理センター**では、**電話会議**をクリックします。 > **ユーザー**の場合は、は、ユーザーを選択し、[操作ウィンドウの [**電話会議 ID** **をリセット**する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="35fb7-118">In the **Skype for Business admin center**, click **Audio conferencing** > **Users**, select a user, and then in the Action pane under **Conference ID** click **Reset**.</span></span>
    
4. <span data-ttu-id="35fb7-p105">**会議 ID をリセットですか?**ウィンドウで、[**はい**] をクリックします。会議 ID が自動的に作成し、新しい会議 ID を持つユーザーに送信されたメール既定では、ユーザーにメールが送られますが、これを無効にできます。</span><span class="sxs-lookup"><span data-stu-id="35fb7-p105">In the **Reset conference ID?** window, click **Yes**. A conference ID will be automatically created and an email sent to the user with the new conference ID. By default, emails are sent to users, but this can be turned off.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="35fb7-p106">会議 ID をリセットすると後、新しい会議 ID を含む電子メールをユーザーに送信されます。このメールが送信、プライマリ メール アドレスに多くの場合、Office 365 メールボックス。電子メールには、新しい会議 ID、既定のダイヤルイン電話番号と Skype for Business 会議を更新するツールを使用して既存の会議を更新する手順が含まれています。</span><span class="sxs-lookup"><span data-stu-id="35fb7-p106">After you reset the conference ID, an email with the new conference ID will be sent to the user. This email will be sent to the primary email address, in many cases, their Office 365 mailbox. The email contains the new conference ID, default dial-in phone number(s) and instructions to use the Skype for Business Meeting Update Tool to update existing meetings.</span></span> 
  
## <a name="what-else-should-i-know"></a><span data-ttu-id="35fb7-125">他に必要な情報はありますか?</span><span class="sxs-lookup"><span data-stu-id="35fb7-125">What else should I know?</span></span>

- <span data-ttu-id="35fb7-p107">操作ウィンドウで、ユーザーの**会議情報を電子メールで送信する**] をクリックして、会議 ID とのダイヤルイン電話番号を含むメール内のユーザーには、すべての会議情報を送信できます。PIN も送信されません。</span><span class="sxs-lookup"><span data-stu-id="35fb7-p107">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking **Send conference info via email** for the user in the Action pane. It doesn't send the PIN.</span></span>
    
- <span data-ttu-id="35fb7-128">会議 ID を 7 つの数字とでは、Skype for Business 管理センター、または Windows PowerShell を使用して、その長さを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="35fb7-128">A conference ID will contain 7 digits, and you can't change its length in the Skype for Business admin center or by using Windows PowerShell.</span></span>
    
- <span data-ttu-id="35fb7-129">リセットすると後、は、[**電話会議 ID**にリストされた新しい会議 ID を表示できます。</span><span class="sxs-lookup"><span data-stu-id="35fb7-129">After it has been reset, you can see the new conference ID listed under **Conference ID**.</span></span>
    
- <span data-ttu-id="35fb7-130">[**ユーザー** ] ページでユーザーを選択すると、[**電話会議**の [アクション] ウィンドウの下部にある電話会議のユーザーの会議 ID を表示できます。</span><span class="sxs-lookup"><span data-stu-id="35fb7-130">The conference ID for a user for audio conferencing can be viewed at the bottom of the Action pane under **Audio conferencing** when you select the user on the **Users** page.</span></span>
    
- <span data-ttu-id="35fb7-p108">新しい会議 ID を作成したら、発信者に応答して古い会議 ID を使用できません。既存ように招待状に ID が追加された新しい会議出席依頼を会議のスケジュールを変更するユーザーに通知する必要があります。ユーザーは、Skype for Business 会議のツールを使用して、既存の会議を更新することができます。ダウンロード、インストール、および Business Meeting Update Tool の Skype を実行する方法を参照してください。</span><span class="sxs-lookup"><span data-stu-id="35fb7-p108">After a new conference ID is created, the old conference ID can't be used by callers. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. The users can use Skype for Business Meeting Tool to update their existing meetings. To see how to download, install, and run the Skype for Business Meeting Update Tool, see:</span></span>
    
  - [<span data-ttu-id="35fb7-135">Skype for Business と Lync の meeting Update Tool</span><span class="sxs-lookup"><span data-stu-id="35fb7-135">Meeting Update Tool for Skype for Business and Lync</span></span>](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)
    
  - [<span data-ttu-id="35fb7-136">Skype for Business をオンラインで会議の移行ツール (64 ビット)</span><span class="sxs-lookup"><span data-stu-id="35fb7-136">Skype for Business Online, Meeting Migration Tool (64-bit)</span></span>](https://go.microsoft.com/fwlink/?LinkID=626047)
    
  - [<span data-ttu-id="35fb7-137">Skype for Business をオンラインで会議の移行ツール (32 ビット)</span><span class="sxs-lookup"><span data-stu-id="35fb7-137">Skype for Business Online, Meeting Migration Tool (32-bit)</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=54079)
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="35fb7-138">Windows PowerShell で管理する方法を知りたいとしていますか。</span><span class="sxs-lookup"><span data-stu-id="35fb7-138">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="35fb7-p109">Windows powershell となるはすべてを管理するユーザーとユーザーの許可または使用できません。Windows PowerShell で Office 365 と Skype for Business Online の複数のタスクを実行するがある場合、日常業務を簡素化する管理の 1 つのポイントを使用して管理できます。Windows PowerShell で開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="35fb7-p109">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="35fb7-142">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="35fb7-142">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="35fb7-143">Office 365 PowerShell を使用する必要がある理由</span><span class="sxs-lookup"><span data-stu-id="35fb7-143">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="35fb7-p110">Windows PowerShell では多くの利点速度、わかりやすいように、および生産性でのみ実行しようとする設定の変更、多くのユーザーに一度になどの Office 365 管理センターを使用します。次のトピックでこれらの利点について学習します。</span><span class="sxs-lookup"><span data-stu-id="35fb7-p110">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="35fb7-146">Windows PowerShell で Office 365 を管理する最善の方法</span><span class="sxs-lookup"><span data-stu-id="35fb7-146">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="35fb7-147">Windows PowerShell を使用して、Skype for Business Online の管理するには</span><span class="sxs-lookup"><span data-stu-id="35fb7-147">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="35fb7-148">Windows PowerShell を使用して、共通の Skype for Business Online の管理タスクを実行するには</span><span class="sxs-lookup"><span data-stu-id="35fb7-148">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="35fb7-149">関連トピック</span><span class="sxs-lookup"><span data-stu-id="35fb7-149">Related topics</span></span>

[<span data-ttu-id="35fb7-150">ユーザーの音声会議の PIN をリセットします。</span><span class="sxs-lookup"><span data-stu-id="35fb7-150">Reset the Audio Conferencing PIN for a user</span></span>](reset-the-audio-conferencing-pin-for-a-user.md)
