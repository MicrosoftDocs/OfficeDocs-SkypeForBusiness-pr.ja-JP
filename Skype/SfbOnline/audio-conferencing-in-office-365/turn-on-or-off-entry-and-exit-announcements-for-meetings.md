---
title: Skype for Business Online で会議のエントリと退出のお知らせを有効または無効にする
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: f2c7b5ea-07b6-4b77-8023-bec9596fcc32
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Skype for Business 管理センターを使用して、Skype for Business Online 会議で、エントリと退出のお知らせを有効または無効にする方法を説明します。 '
ms.openlocfilehash: b9341a2011127b5a188d3d8ae2c507b097aaea65
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2018
ms.locfileid: "26531119"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-skype-for-business-online"></a><span data-ttu-id="cbd87-103">Skype for Business Online で会議のエントリと退出のお知らせを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="cbd87-103">Turn on or off entry and exit announcements for meetings in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="cbd87-104">Microsoft Teams でのエントリと退出のお知らせについては、「[Microsoft Teams でエントリと退出のお知らせを有効または無効にする](/MicrosoftTeams/turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cbd87-104">For information about entry and exit announcements in Microsoft Teams, see [Turn on or off entry and exit announcements for meetings in Microsoft Teams](/MicrosoftTeams/turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams).</span></span>

<span data-ttu-id="cbd87-p101">When you are setting up Audio Conferencing in Office 365, you will get an audio conferencing bridge. A conferencing bridge can contain one or more phone numbers that people will use to call in to a Skype for Business meeting.</span><span class="sxs-lookup"><span data-stu-id="cbd87-p101">When you are setting up Audio Conferencing in Office 365, you will get an audio conferencing bridge. A conferencing bridge can contain one or more phone numbers that people will use to call in to a Skype for Business meeting.</span></span> 
  
<span data-ttu-id="cbd87-p102">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone. The conferencing bridge answers the caller with voice prompts from a conferencing auto attendant, and then, depending on your settings, can play notifications, ask callers to record their name, and set up the PIN security. A PIN is given to a Skype for Business meeting organizer, and it allows them to start a meeting if they can't start the meeting using the Skype for Business app. You can, however, set it so that a PIN isn't required to start a meeting.</span><span class="sxs-lookup"><span data-stu-id="cbd87-p102">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone. The conferencing bridge answers the caller with voice prompts from a conferencing auto attendant, and then, depending on your settings, can play notifications, ask callers to record their name, and set up the PIN security. A PIN is given to a Skype for Business meeting organizer, and it allows them to start a meeting if they can't start the meeting using the Skype for Business app. You can, however, set it so that a PIN isn't required to start a meeting.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a><span data-ttu-id="cbd87-111">会議の参加オプションの設定</span><span class="sxs-lookup"><span data-stu-id="cbd87-111">Setting meeting join options</span></span>
    
1. <span data-ttu-id="cbd87-112">既定値は 5 です。\*\*\*\*\*\*\*\* > \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="cbd87-112">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="cbd87-p103">Under **Meeting join experience**, select or clear **Enable meeting entry and exit notifications to be turned on**. This is selected by default. If you clear it, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span><span class="sxs-lookup"><span data-stu-id="cbd87-p103">Under **Meeting join experience**, select or clear **Enable meeting entry and exit notifications to be turned on**. This is selected by default. If you clear it, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
3. <span data-ttu-id="cbd87-116">[**エントリ/退出のお知らせの種類**] の下にある [**名前または電話番号**] または [**トーン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cbd87-116">Under **Entry/exit announcement type**, select **Names or phone numbers** or **Tones**.</span></span>
    
4. <span data-ttu-id="cbd87-117">確認するか、**ミーティングに参加する前に自分の名前を記録するための呼び出し元の確認**をオフにします。</span><span class="sxs-lookup"><span data-stu-id="cbd87-117">Check or uncheck **Ask callers to record their name before joining the meeting**.</span></span>
    
5. <span data-ttu-id="cbd87-118">変更したら [ **保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cbd87-118">After you make your changes, click **Save**.</span></span>
    

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="cbd87-119">Windows PowerShell で管理する方法</span><span class="sxs-lookup"><span data-stu-id="cbd87-119">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="cbd87-120">時間を短縮または、これを自動化するには、[セット CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps)コマンドレットを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="cbd87-120">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet.</span></span>
    
- <span data-ttu-id="cbd87-p104">Windows PowerShell の場合、Skype for Business Online はユーザーの管理と、ユーザーが許可されている操作や許可されていない操作の管理に使います。Windows PowerShell により、単一の管理ポイントを使って Office 365 を管理でき、複数の作業を実行する必要があるときに日常業務を合理化できます。Windows PowerShell を使い始めるには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cbd87-p104">When it comes to Windows PowerShell, Skype for Business Online is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="cbd87-124">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="cbd87-124">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="cbd87-125">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="cbd87-125">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="cbd87-p105">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making settings changes for many users at one time. Learn about these advantages in the following topics:</span><span class="sxs-lookup"><span data-stu-id="cbd87-p105">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making settings changes for many users at one time. Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="cbd87-128">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="cbd87-128">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="cbd87-129">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="cbd87-129">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="cbd87-130">クイック リファレンス: Windows PowerShell を使用した一般的な Lync Online の管理タスクの実行</span><span class="sxs-lookup"><span data-stu-id="cbd87-130">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="cbd87-p106">Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行[](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="cbd87-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="cbd87-133">関連トピック</span><span class="sxs-lookup"><span data-stu-id="cbd87-133">Related topics</span></span>

[<span data-ttu-id="cbd87-134">電話会議に関するよくある質問</span><span class="sxs-lookup"><span data-stu-id="cbd87-134">Audio Conferencing common questions</span></span>](/MicrosoftTeams/audio-conferencing-common-questions)
