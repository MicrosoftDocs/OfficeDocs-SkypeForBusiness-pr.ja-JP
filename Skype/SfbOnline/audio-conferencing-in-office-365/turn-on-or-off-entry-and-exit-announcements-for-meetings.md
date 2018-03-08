---
title: "会議の出席と退席のお知らせ無効を切り替える"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: f2c7b5ea-07b6-4b77-8023-bec9596fcc32
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
description: "エントリを有効にして、終了する Skype for Business 管理センターの Skype を使用してビジネスのオンライン会議で発表をオンまたはオフにする方法について説明します。 "
ms.openlocfilehash: ca353400d78a37a4b7cc362df6ed44a7f25fd869
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings"></a><span data-ttu-id="48efc-103">会議の出席と退席のお知らせ無効を切り替える</span><span class="sxs-lookup"><span data-stu-id="48efc-103">Turn on or off entry and exit announcements for meetings</span></span>

<span data-ttu-id="48efc-p101">Office 365 での電話会議をセットアップするときに、電話会議ブリッジが表示されます。会議ブリッジには、Skype for Business または Microsoft チーム会議にコールインするユーザーを使用する 1 つ以上の電話番号を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="48efc-p101">When you are setting up Audio Conferencing in Office 365, you will get an audio conferencing bridge. A conferencing bridge can contain one or more phone numbers that people will use to call in to a Skype for Business or Microsoft Teams meeting.</span></span> 
  
<span data-ttu-id="48efc-p102">会議ブリッジが電話を使って会議にダイヤルインしたユーザーが呼び出しに応答します。会議ブリッジ、会議の自動応答からを促すボイス メッセージと発信者に応答しの設定によってできる再生、通知、発信者に相手の名前を記録し、暗証番号 (pin) のセキュリティ設定を依頼します。PIN を Skype for Business または Microsoft チーム会議の開催者、され for Business または Microsoft チーム アプリ Skype を使用して、会議を開始することができない場合は、会議を開始することができます。PIN は、会議を開始する要求されないように、それを設定ただし、できます。</span><span class="sxs-lookup"><span data-stu-id="48efc-p102">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone. The conferencing bridge answers the caller with voice prompts from a conferencing auto attendant, and then, depending on your settings, can play notifications, ask callers to record their name, and set up the PIN security. A PIN is given to a Skype for Business or Microsoft Teams meeting organizer, and it allows them to start a meeting if they can't start the meeting using a Skype for Business or Microsoft Teams app. You can, however, set it so that a PIN isn't required to start a meeting.</span></span>
  
## <a name="setting-meeting-join-options"></a><span data-ttu-id="48efc-110">会議に参加するオプションを設定します。</span><span class="sxs-lookup"><span data-stu-id="48efc-110">Setting meeting join options</span></span>

1. <span data-ttu-id="48efc-111">職場または学校のアカウントで Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="48efc-111">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="48efc-112">**Office 365 管理センター**に移動 > **Skype for Business**します。</span><span class="sxs-lookup"><span data-stu-id="48efc-112">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="48efc-113">**Skype for Business 管理センター**、左のナビゲーションで**電話会議**に移動 > **Microsoft ブリッジの設定**します。</span><span class="sxs-lookup"><span data-stu-id="48efc-113">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="48efc-p103">[**会議参加エクスペリエンス**をオンまたは**会議のエントリを有効にして終了通知をオンになって**をオフにします。これが既定で選択されます。場合は、このオプションをオフにすると、会議に参加しているユーザーはデータを入力したり、会議のままである場合に通知されません。</span><span class="sxs-lookup"><span data-stu-id="48efc-p103">Under **Meeting join experience**, select or clear **Enable meeting entry and exit notifications to be turned on**. This is selected by default. If you clear it, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
5. <span data-ttu-id="48efc-117">[**開始/終了のお知らせの種類**] で、**名前または電話番号**または**音**を選択します。</span><span class="sxs-lookup"><span data-stu-id="48efc-117">Under **Entry/exit announcement type**, select **Names or phone numbers** or **Tones**.</span></span>
    
6. <span data-ttu-id="48efc-118">オンまたは**Ask の発信者**をオフにします。</span><span class="sxs-lookup"><span data-stu-id="48efc-118">Check or uncheck **Ask callers to record their name before joining the meeting**.</span></span>
    
7. <span data-ttu-id="48efc-119">変更が終了したら、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="48efc-119">After you make your changes, click **Save**.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="48efc-120">Windows PowerShell で管理する方法を知りたいとしていますか。</span><span class="sxs-lookup"><span data-stu-id="48efc-120">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="48efc-121">時間を節約し、自動化したりには、[セット CsOnlineDialInConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 )コマンドレットを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="48efc-121">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 ) cmdlet.</span></span>
    
-  <span data-ttu-id="48efc-p104">Windows PowerShell する際に、Skype for Business Online はすべてを管理するユーザーとユーザーの許可または使用できません。Windows PowerShell で複数のタスクを実行するがある場合、日常業務を簡素化する管理の 1 つのポイントを使用して Office 365 を管理できます。Windows PowerShell で開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="48efc-p104">When it comes to Windows PowerShell, Skype for Business Online is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="48efc-125">Office 365 PowerShell を使用する必要がある理由</span><span class="sxs-lookup"><span data-stu-id="48efc-125">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="48efc-126">Windows PowerShell で Office 365 を管理する最善の方法</span><span class="sxs-lookup"><span data-stu-id="48efc-126">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="48efc-p105">Windows PowerShell では多くの利点速度、わかりやすいように、および生産性でのみ実行しようとする設定の変更、多くのユーザーに一度になどの Office 365 管理センターを使用します。次のトピックでこれらの利点について学習します。</span><span class="sxs-lookup"><span data-stu-id="48efc-p105">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making settings changes for many users at one time. Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="48efc-129">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="48efc-129">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="48efc-130">Windows PowerShell を使用して、Skype for Business Online の管理するには</span><span class="sxs-lookup"><span data-stu-id="48efc-130">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="48efc-131">Windows PowerShell を使用して、共通の Skype for Business Online の管理タスクを実行するには</span><span class="sxs-lookup"><span data-stu-id="48efc-131">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="48efc-p106">Skype for Business Online 用の Windows PowerShell モジュールを使用すると、Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成することができます。このモジュールでは、64 ビット コンピューター以外では、Microsoft ダウンロード センターからダウンロードできます[Skype for Business Online 用の Windows PowerShell モジュール](https://go.microsoft.com/fwlink/?LinkId=294688)。</span><span class="sxs-lookup"><span data-stu-id="48efc-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="48efc-134">関連トピック</span><span class="sxs-lookup"><span data-stu-id="48efc-134">Related topics</span></span>

[<span data-ttu-id="48efc-135">音声会議よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="48efc-135">Audio Conferencing common questions</span></span>](audio-conferencing-common-questions.md)

