---
title: Change the settings for an Audio Conferencing bridge
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 04/03/2018
ms.topic: article
ms.assetid: 783fad3f-b77c-422b-b91f-7c8b0af324fb
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "Get the steps you need to change settings for a conferencing bridge that's used to prompt callers and gather names and pins for meeting organizers when they're not using Skype for Business or Microsoft Teams apps. "
ms.openlocfilehash: 727392bc81bce2fb3cfd84029e6a275e1eed3e24
ms.sourcegitcommit: dea27df69d948b7b9cc017b7023c4013cee8e4d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2018
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a><span data-ttu-id="f3d3d-103">Change the settings for an Audio Conferencing bridge</span><span class="sxs-lookup"><span data-stu-id="f3d3d-103">Change the settings for an Audio Conferencing bridge</span></span>

<span data-ttu-id="f3d3d-104">When you are setting up Audio Conferencing in Office 365, you will receive phone numbers for your users from what is called an audio conferencing bridge.</span><span class="sxs-lookup"><span data-stu-id="f3d3d-104">When you are setting up Audio Conferencing in Office 365, you will receive phone numbers for your users from what is called an audio conferencing bridge.</span></span> <span data-ttu-id="f3d3d-105">A conferencing bridge can contain one or more phone numbers.</span><span class="sxs-lookup"><span data-stu-id="f3d3d-105">A conferencing bridge can contain one or more phone numbers.</span></span> <span data-ttu-id="f3d3d-106">These phone numbers are used when callers dial in to a meeting.</span><span class="sxs-lookup"><span data-stu-id="f3d3d-106">These phone numbers are used when callers dial in to a meeting.</span></span> <span data-ttu-id="f3d3d-107">The phone number is included at the bottom of the Skype for Business or Microsoft Teams meeting invite.</span><span class="sxs-lookup"><span data-stu-id="f3d3d-107">The phone number is included at the bottom of the Skype for Business or Microsoft Teams meeting invite.</span></span>
  
<span data-ttu-id="f3d3d-108">The conferencing bridge answers a call and prompts the caller with voice prompts using a meeting auto attendant, and then, depending on your settings, it can play notifications, ask callers to record their name, and control the PIN settings.</span><span class="sxs-lookup"><span data-stu-id="f3d3d-108">The conferencing bridge answers a call and prompts the caller with voice prompts using a meeting auto attendant, and then, depending on your settings, it can play notifications, ask callers to record their name, and control the PIN settings.</span></span> <span data-ttu-id="f3d3d-109">PINs are given to meeting organizers to allow them to start a meeting when they are aren't using a Skype for Business or Microsoft Teams app.</span><span class="sxs-lookup"><span data-stu-id="f3d3d-109">PINs are given to meeting organizers to allow them to start a meeting when they are aren't using a Skype for Business or Microsoft Teams app.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="f3d3d-110">A PIN is only required for the meeting organizer when a Skype for Business or Microsoft Teams app user hasn't already started the meeting.</span><span class="sxs-lookup"><span data-stu-id="f3d3d-110">A PIN is only required for the meeting organizer when a Skype for Business or Microsoft Teams app user hasn't already started the meeting.</span></span> <span data-ttu-id="f3d3d-111">If everyone is dialing in to the meeting, the PIN is required for the meeting organizer to start the meeting.</span><span class="sxs-lookup"><span data-stu-id="f3d3d-111">If everyone is dialing in to the meeting, the PIN is required for the meeting organizer to start the meeting.</span></span> 

> [!CAUTION]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="using-the-microsoft-teams-and-skype-for-business-admin-center"></a><span data-ttu-id="f3d3d-112">Using the Microsoft Teams and Skype for Business Admin Center</span><span class="sxs-lookup"><span data-stu-id="f3d3d-112">Using the Microsoft Teams and Skype for Business Admin Center</span></span>

1. <span data-ttu-id="f3d3d-113">In the left navigation, go to **Meetings** > **Conference bridges**.</span><span class="sxs-lookup"><span data-stu-id="f3d3d-113">In the left navigation, go to **Meetings** > **Conference bridges**.</span></span> 

2. <span data-ttu-id="f3d3d-114">At the top of the **Conference bridges** page, click **Bridge settings**.</span><span class="sxs-lookup"><span data-stu-id="f3d3d-114">At the top of the **Conference bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="f3d3d-115">In the **Bridge settings** pane, select:</span><span class="sxs-lookup"><span data-stu-id="f3d3d-115">In the **Bridge settings** pane, select:</span></span> 
  - <span data-ttu-id="f3d3d-116">**Meeting entry and exit notifications** If you turn this off, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span><span class="sxs-lookup"><span data-stu-id="f3d3d-116">**Meeting entry and exit notifications** If you turn this off, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
    <span data-ttu-id="f3d3d-117">When you turn on **Meeting entry and exit notifications**, you can select these options:</span><span class="sxs-lookup"><span data-stu-id="f3d3d-117">When you turn on **Meeting entry and exit notifications**, you can select these options:</span></span>
    
  - <span data-ttu-id="f3d3d-118">**Names or phone numbers** When users dial in to a meeting, their phone number will be played when they join it.</span><span class="sxs-lookup"><span data-stu-id="f3d3d-118">**Names or phone numbers** When users dial in to a meeting, their phone number will be played when they join it.</span></span>
    
  - <span data-ttu-id="f3d3d-119">**Tones** When users dial in to a meeting, an audio tone will be played when they join it.</span><span class="sxs-lookup"><span data-stu-id="f3d3d-119">**Tones** When users dial in to a meeting, an audio tone will be played when they join it.</span></span>
      
  - <span data-ttu-id="f3d3d-120">**Ask callers to record their name before joining the meeting** If you turn this off, callers won't be asked to record their name before they join a meeting.</span><span class="sxs-lookup"><span data-stu-id="f3d3d-120">**Ask callers to record their name before joining the meeting** If you turn this off, callers won't be asked to record their name before they join a meeting.</span></span>

4. <span data-ttu-id="f3d3d-121">To set the PIN length for meetings, select the number of digits you want for the PIN in the **PIN length** list.</span><span class="sxs-lookup"><span data-stu-id="f3d3d-121">To set the PIN length for meetings, select the number of digits you want for the PIN in the **PIN length** list.</span></span>

5. <span data-ttu-id="f3d3d-122">To specify whether to send email to your users, enable or disable **Automatically send emails to users if their audio conferencing configuration changes**.</span><span class="sxs-lookup"><span data-stu-id="f3d3d-122">To specify whether to send email to your users, enable or disable **Automatically send emails to users if their audio conferencing configuration changes**.</span></span>
    <span data-ttu-id="f3d3d-123">See [Emails automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md) for more information.</span><span class="sxs-lookup"><span data-stu-id="f3d3d-123">See [Emails automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md) for more information.</span></span>
 
6. <span data-ttu-id="f3d3d-124">[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f3d3d-124">Click **Apply**.</span></span> 

## <a name="using-skype-for-business-admin-center"></a><span data-ttu-id="f3d3d-125">Using Skype for Business admin center</span><span class="sxs-lookup"><span data-stu-id="f3d3d-125">Using Skype for Business admin center</span></span>

 <span data-ttu-id="f3d3d-126">**Set up the meeting experience when callers join a meeting**</span><span class="sxs-lookup"><span data-stu-id="f3d3d-126">**Set up the meeting experience when callers join a meeting**</span></span>
    
1. <span data-ttu-id="f3d3d-127">In the **Skype for Business admin center**, in the left navigation go to **Audio conferencing** > **Microsoft bridge settings**.</span><span class="sxs-lookup"><span data-stu-id="f3d3d-127">In the **Skype for Business admin center**, in the left navigation go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="f3d3d-128">On the **Microsoft bridge settings** page, under **Meeting join experience**, select:</span><span class="sxs-lookup"><span data-stu-id="f3d3d-128">On the **Microsoft bridge settings** page, under **Meeting join experience**, select:</span></span>
    
  - <span data-ttu-id="f3d3d-129">**Enable meeting entry and exit notifications to be turned on** This is selected by default.</span><span class="sxs-lookup"><span data-stu-id="f3d3d-129">**Enable meeting entry and exit notifications to be turned on** This is selected by default.</span></span> <span data-ttu-id="f3d3d-130">If you clear the check box, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span><span class="sxs-lookup"><span data-stu-id="f3d3d-130">If you clear the check box, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
    <span data-ttu-id="f3d3d-131">When you select **Enable meeting entry and exit notifications to be turned on**, you can select these options from the **Entry/exit announcement type** list:</span><span class="sxs-lookup"><span data-stu-id="f3d3d-131">When you select **Enable meeting entry and exit notifications to be turned on**, you can select these options from the **Entry/exit announcement type** list:</span></span>
    
  - <span data-ttu-id="f3d3d-132">**Names or phone numbers** When users dial in to a meeting, their phone number will be played when they join it.</span><span class="sxs-lookup"><span data-stu-id="f3d3d-132">**Names or phone numbers** When users dial in to a meeting, their phone number will be played when they join it.</span></span>
    
  - <span data-ttu-id="f3d3d-133">**Tones** When users dial in to a meeting, an audio tone will be played when they join it.</span><span class="sxs-lookup"><span data-stu-id="f3d3d-133">**Tones** When users dial in to a meeting, an audio tone will be played when they join it.</span></span>
  
  - <span data-ttu-id="f3d3d-134">**会議の PIN の長さを設定する**</span><span class="sxs-lookup"><span data-stu-id="f3d3d-134">**Ask callers to record their name before joining the meeting** This is selected by default.</span></span> <span data-ttu-id="f3d3d-135">If you clear the check box, callers won't be asked to record their name before they join a meeting.</span><span class="sxs-lookup"><span data-stu-id="f3d3d-135">If you clear the check box, callers won't be asked to record their name before they join a meeting.</span></span>
    
3. <span data-ttu-id="f3d3d-136">Sign in to Office 365 with your work or school account.</span><span class="sxs-lookup"><span data-stu-id="f3d3d-136">After you make your changes, click **Save**.</span></span>
    
<span data-ttu-id="f3d3d-137">In the Skype for Business admin center, in the left navigation go to dial-in conferencingMicrosoft bridge settings.</span><span class="sxs-lookup"><span data-stu-id="f3d3d-137">**Set the PIN length for meetings**</span></span>
  
1. <span data-ttu-id="f3d3d-138">PIN の桁数は 4 から 12 の間にする必要があります。既定値は 5 です。</span><span class="sxs-lookup"><span data-stu-id="f3d3d-138">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="f3d3d-139">Sign in to Office 365 with your work or school account.</span><span class="sxs-lookup"><span data-stu-id="f3d3d-139">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="f3d3d-140">既定値は 5 です。</span><span class="sxs-lookup"><span data-stu-id="f3d3d-140">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="f3d3d-141">On the **Microsoft bridge settings** page, under **Security**, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span><span class="sxs-lookup"><span data-stu-id="f3d3d-141">On the **Microsoft bridge settings** page, under **Security**, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="f3d3d-142">The default is 5.</span><span class="sxs-lookup"><span data-stu-id="f3d3d-142">The PIN must be between 4 and 12 digits.</span></span> 
  
<span data-ttu-id="f3d3d-143">**Select whether to send email to your users**</span><span class="sxs-lookup"><span data-stu-id="f3d3d-143">**Select whether to send email to your users**</span></span>
  
1. <span data-ttu-id="f3d3d-144">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="f3d3d-144">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="f3d3d-145">Sign in to Office 365 with your work or school account.</span><span class="sxs-lookup"><span data-stu-id="f3d3d-145">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="f3d3d-146">既定値は 5 です。</span><span class="sxs-lookup"><span data-stu-id="f3d3d-146">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="f3d3d-147">On the **Microsoft bridge settings** page, select or clear **Automatically send emails to users if their dial-in information changes**, and then click **Save**.</span><span class="sxs-lookup"><span data-stu-id="f3d3d-147">On the **Microsoft bridge settings** page, select or clear **Automatically send emails to users if their dial-in information changes**, and then click **Save**.</span></span>
    
    <span data-ttu-id="f3d3d-148">See [Emails automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md) for more information.</span><span class="sxs-lookup"><span data-stu-id="f3d3d-148">See [Emails automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md) for more information.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="f3d3d-149">Go to the Office 365 admin centerSkype for Business.</span><span class="sxs-lookup"><span data-stu-id="f3d3d-149">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="f3d3d-150">To save time or automate this process, you can use the [Set-CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 ) cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f3d3d-150">To save time or automate this process, you can use the [Set-CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 ) cmdlet.</span></span>
    
- <span data-ttu-id="f3d3d-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span><span class="sxs-lookup"><span data-stu-id="f3d3d-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="f3d3d-154">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="f3d3d-154">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="f3d3d-155">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="f3d3d-155">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="f3d3d-p108">多くのユーザーの設定を同時に変更するときなどは、Office 365 管理センターのみを使用するよりも、Windows PowerShell の方に、速度、わかりやすさ、生産性の点で多くのメリットがあります。 次のトピックで、これらの利点を説明します。</span><span class="sxs-lookup"><span data-stu-id="f3d3d-p108">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="f3d3d-158">Windows PowerShell と Lync Online の概要</span><span class="sxs-lookup"><span data-stu-id="f3d3d-158">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="f3d3d-159">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="f3d3d-159">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="f3d3d-160">Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行</span><span class="sxs-lookup"><span data-stu-id="f3d3d-160">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="f3d3d-p109">[Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="f3d3d-p109">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="f3d3d-163">このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「Skype for Business Online 用 Windows PowerShell モジュール」からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="f3d3d-163">Related topics</span></span>

[<span data-ttu-id="f3d3d-164">電話会議をセットアップする</span><span class="sxs-lookup"><span data-stu-id="f3d3d-164">Set up Audio Conferencing</span></span>](set-up-audio-conferencing.md)
