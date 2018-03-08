---
title: "電話会議の会議の PIN の長さを設定します。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: b86d31c6-1543-478f-b8c6-4b71e708403a
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
description: "Skype for Business の会議の長さを設定する方法を参照してくださいし、長さと PIN の要件のパラメーターを学習します。"
ms.openlocfilehash: 308bce9196f085c1f9473e74746bccd2f0ca96c5
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings"></a><span data-ttu-id="386b2-103">電話会議の会議の PIN の長さを設定します。</span><span class="sxs-lookup"><span data-stu-id="386b2-103">Set the PIN length for Audio Conferencing meetings</span></span>

<span data-ttu-id="386b2-p101">セットアップしているで電話会議の Skype for Business または Microsoft チーム、ときに、電話会議ブリッジが表示されます。会議ブリッジには、1 つ以上の電話番号を含めることができます。設定した電話番号は、その skype for Business とチームの Microsoft アプリ会議の出席依頼に含まれます。</span><span class="sxs-lookup"><span data-stu-id="386b2-p101">When you are setting up audio conferencing in for Skype for Business or Microsoft Teams, you will get an audio conferencing bridge. A conferencing bridge can contain one or more phone numbers. The phone number you set will be included on the meeting invites for Skype for Business and Microsoft Teams apps.</span></span>
  
<span data-ttu-id="386b2-p102">電話会議ブリッジ電話を使って会議にダイヤルインしているユーザーの通話に応答します。自動応答し、設定によってを促すボイス メッセージと発信者に応答、通知の再生および発信者が名前を記録するように依頼することができます。**Microsoft ブリッジの設定**を使用すると、会議の通知の設定を変更し、会議参加エクスペリエンス] と、会議の開催者によって使用される Pin の長さを設定します。会議の開催者は、会議を開始する場合は、Skype を for Business または Microsoft チームのアプリを使って会議に参加できないことの Pin を使用します。</span><span class="sxs-lookup"><span data-stu-id="386b2-p102">The audio conferencing bridge answers a call for people who are dialing in to a meeting using a phone. It answers the caller with voice prompts from an auto attendant and then, depending on your settings, can play notifications and ask callers to record their name. **Microsoft bridge settings** allow you to change the settings for meeting notifications and the meeting join experience, and set the length of the PINs that are used by meeting organizers. Meeting organizers use PINs to start meetings if they can't join the meeting using the Skype for Business or Microsoft Teams app.</span></span>
  
## <a name="setting-the-pin-length"></a><span data-ttu-id="386b2-111">PIN の長さを設定します。</span><span class="sxs-lookup"><span data-stu-id="386b2-111">Setting the PIN length</span></span>

1. <span data-ttu-id="386b2-112">職場または学校のアカウントで Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="386b2-112">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="386b2-113">**Office 365 管理センター**に移動 > **Skype for Business**します。</span><span class="sxs-lookup"><span data-stu-id="386b2-113">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="386b2-114">**Skype for Business 管理センター**、左のナビゲーションで**電話会議**に移動 > **Microsoft ブリッジの設定**します。</span><span class="sxs-lookup"><span data-stu-id="386b2-114">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="386b2-115">[**セキュリティ** > **PIN の長さ**、暗証番号 (pin)] の桁の番号を選択し、し、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="386b2-115">Under **Security** > **PIN length**, select the number of digits you want for the PIN, and then click **Save**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="386b2-p103">PIN は、会議 ID の相違点します。会議 Id は、会議に参加するときに、発信者で使用されます。会議の確認に使用されます。PIN を使用して、会議の開催者の発信者番号を認証します。</span><span class="sxs-lookup"><span data-stu-id="386b2-p103">A PIN is different from a conference ID. Conference IDs are used by callers when they join the meeting. They are used to identify the meeting. The PIN is used to authenticate a caller as the meeting organizer.</span></span> 
  
## <a name="want-to-know-more-about-pin-settings"></a><span data-ttu-id="386b2-120">PIN の設定について詳しく知りたいとしていますか。</span><span class="sxs-lookup"><span data-stu-id="386b2-120">Want to know more about PIN settings?</span></span>

- <span data-ttu-id="386b2-p104">Pin は 4 ~ 12 桁; に必要既定では 5 です。数値は、Pin を作成するときにのみ使用されます。文字と特殊文字は使用されません。</span><span class="sxs-lookup"><span data-stu-id="386b2-p104">PINs can be from 4 to 12 digits; the default is 5. Numbers are only used when creating PINs. Letters and special characters aren't used.</span></span>
    
- <span data-ttu-id="386b2-p105">PIN がのみが必要なときに Skype for Business または Microsoft チームのユーザー、会議の開催者が会議を既に開始していません。会議にダイヤルインすべてのユーザーがいる場合は、PIN 会議の開催者、会議を開始するために必要なです。</span><span class="sxs-lookup"><span data-stu-id="386b2-p105">A PIN is only required for the meeting organizer when a Skype for Business or Microsoft Teams user hasn't already started the meeting. If everyone is dialing in to the meeting, then the PIN is required for the meeting organizer to start the meeting.</span></span>
    
- <span data-ttu-id="386b2-p106">PIN のセキュリティ設定は、Microsoft ブリッジに関連付けられている電話番号のすべてに適用されます。指定されたブリッジに関連付けられている電話番号を使用するすべての会議が適用されます。</span><span class="sxs-lookup"><span data-stu-id="386b2-p106">PIN security settings are applied to all of the phone numbers that are associated with a Microsoft bridge. They will be applied to all meetings that use the phone numbers associated with a given bridge.</span></span> 
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="386b2-128">Windows PowerShell で管理する方法を知りたいとしていますか。</span><span class="sxs-lookup"><span data-stu-id="386b2-128">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="386b2-129">時間を節約し、自動化したりには、[セット CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757)コマンドレットを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="386b2-129">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757) cmdlet.</span></span>
    
- <span data-ttu-id="386b2-130">8 暗証番号 (pin) では、以下の桁数を設定します。`Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`</span><span class="sxs-lookup"><span data-stu-id="386b2-130">To set the number of digits in the PIN to 8:  `Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`</span></span>
    
- <span data-ttu-id="386b2-p107">Windows PowerShell がユーザーを管理するユーザーを許可または使用できません。Windows PowerShell で複数のタスクを実行するがある場合、日常業務を簡素化する管理の 1 つのポイントを使用して Office 365 を管理できます。Windows PowerShell で開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="386b2-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="386b2-134">Office 365 PowerShell を使用する必要がある理由</span><span class="sxs-lookup"><span data-stu-id="386b2-134">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="386b2-135">Windows PowerShell で Office 365 を管理する最善の方法</span><span class="sxs-lookup"><span data-stu-id="386b2-135">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="386b2-p108">Windows PowerShell では多くの利点速度、わかりやすいように、および生産性でのみ実行しようとする設定の変更、多くのユーザーに一度になど、Office 365 管理センターを使用します。次のトピックでこれらの利点について学習します。</span><span class="sxs-lookup"><span data-stu-id="386b2-p108">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time. Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="386b2-138">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="386b2-138">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="386b2-139">Windows PowerShell を使用して、Skype for Business Online の管理するには</span><span class="sxs-lookup"><span data-stu-id="386b2-139">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
    [<span data-ttu-id="386b2-140">Windows PowerShell を使用して、Skype for Business Online の管理するには</span><span class="sxs-lookup"><span data-stu-id="386b2-140">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="386b2-141">Windows PowerShell を使用して、共通の Skype for Business Online の管理タスクを実行するには</span><span class="sxs-lookup"><span data-stu-id="386b2-141">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="386b2-p109">Skype for Business Online 用の Windows PowerShell モジュールを使用すると、Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成することができます。このモジュールでは、64 ビット コンピューター以外では、Microsoft ダウンロード センターからダウンロードできます[Skype for Business Online 用の Windows PowerShell モジュール](https://go.microsoft.com/fwlink/?LinkId=294688)。</span><span class="sxs-lookup"><span data-stu-id="386b2-p109">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="see-also"></a><span data-ttu-id="386b2-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="386b2-144">See also</span></span>

[<span data-ttu-id="386b2-145">Skype for Business とチームの Microsoft の音声会議をセットアップする設定します。</span><span class="sxs-lookup"><span data-stu-id="386b2-145">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](set-up-audio-conferencing.md)

