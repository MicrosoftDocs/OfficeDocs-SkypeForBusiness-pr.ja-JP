---
title: ビジネス オンラインの Skype で電話会議の会議の暗証番号 (pin) の長さを設定します。
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: b86d31c6-1543-478f-b8c6-4b71e708403a
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
description: パラメーターの長さと、PIN の要件を説明し、ビジネスの Skype での会議の長さを設定する方法を参照してください。
ms.openlocfilehash: c5add9cff2855fd969b76d96647f05e6e6dab290
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23883597"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-skype-for-business-online"></a><span data-ttu-id="5de8b-103">ビジネス オンラインの Skype で電話会議の会議の暗証番号 (pin) の長さを設定します。</span><span class="sxs-lookup"><span data-stu-id="5de8b-103">Set the PIN length for Audio Conferencing meetings in Skype for Business Online</span></span>


> [!NOTE]
> <span data-ttu-id="5de8b-104">マイクロソフトのチームでの暗証番号 (pin) の長さを設定する方法については、[マイクロソフトのチーム内の電話会議の会議の暗証番号 (pin) の長さを設定する](/en-us/MicrosoftTeams/Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5de8b-104">For information about setting the PIN length in Microsoft Teams, see [Set the PIN length for Audio Conferencing meetings in Microsoft Teams](/en-us/MicrosoftTeams/Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams).</span></span>

<span data-ttu-id="5de8b-105">ビジネス用の Skype の電話会議を設定するときに、オーディオ会議ブリッジが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5de8b-105">When you are setting up audio conferencing for Skype for Business, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="5de8b-106">会議用ブリッジは、1 つまたは複数の電話番号を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="5de8b-106">A conferencing bridge can contain one or more phone numbers.</span></span> <span data-ttu-id="5de8b-107">設定した電話番号は、ビジネス アプリケーションの Skype の会議の招待に含まれます。</span><span class="sxs-lookup"><span data-stu-id="5de8b-107">The phone number you set will be included on the meeting invites for the Skype for Business app.</span></span>
  
<span data-ttu-id="5de8b-108">オーディオ会議ブリッジ、電話を使用して会議にダイヤルインしている人のための呼び出しに応答します。</span><span class="sxs-lookup"><span data-stu-id="5de8b-108">The audio conferencing bridge answers a call for people who are dialing in to a meeting using a phone.</span></span> <span data-ttu-id="5de8b-109">自動応答から、設定によっては、音声メッセージを呼び出し元に応答、通知を再生でき、自分の名前を記録するための呼び出し元に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="5de8b-109">It answers the caller with voice prompts from an auto attendant and then, depending on your settings, can play notifications and ask callers to record their name.</span></span> <span data-ttu-id="5de8b-110">**マイクロソフト ブリッジの設定**では、会議の通知の設定を変更することができ、会議の参加、会議の開催者によって使用されているピンの長さを設定します。</span><span class="sxs-lookup"><span data-stu-id="5de8b-110">**Microsoft bridge settings** allow you to change the settings for meeting notifications and the meeting join experience, and set the length of the PINs that are used by meeting organizers.</span></span> <span data-ttu-id="5de8b-111">ミーティングの開催者は、ビジネス アプリケーションに、Skype を使用してミーティングに参加することはできない場合は、会議を開始するためのピンを使用します。</span><span class="sxs-lookup"><span data-stu-id="5de8b-111">Meeting organizers use PINs to start meetings if they can't join the meeting using the Skype for Business app.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a><span data-ttu-id="5de8b-112">暗証番号 (pin) の長さを設定</span><span class="sxs-lookup"><span data-stu-id="5de8b-112">Setting the PIN length</span></span>
 
1. <span data-ttu-id="5de8b-113">既定値は 5 です。\*\*\*\*\*\*\*\* > \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="5de8b-113">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="5de8b-114">[**セキュリティ]** > **暗証番号 (pin) の長さ**を選択し、PIN の桁数を選択し、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5de8b-114">Under **Security** > **PIN length**, select the number of digits you want for the PIN, and then click **Save**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="5de8b-115">PIN とは異なる、会議の id です。</span><span class="sxs-lookup"><span data-stu-id="5de8b-115">A PIN is different from a conference ID.</span></span> <span data-ttu-id="5de8b-116">会議 Id は、ミーティングに参加するときに、呼び出し元が使用されます。</span><span class="sxs-lookup"><span data-stu-id="5de8b-116">Conference IDs are used by callers when they join the meeting.</span></span> <span data-ttu-id="5de8b-117">ミーティングに使用されます。</span><span class="sxs-lookup"><span data-stu-id="5de8b-117">They are used to identify the meeting.</span></span> <span data-ttu-id="5de8b-118">暗証番号 (pin) を使用して、会議の開催者は、呼び出し元を認証します。</span><span class="sxs-lookup"><span data-stu-id="5de8b-118">The PIN is used to authenticate a caller as the meeting organizer.</span></span> 

## <a name="want-to-know-more-about-pin-settings"></a><span data-ttu-id="5de8b-119">暗証番号 (pin) の設定の詳細を知りたいとしていますか。</span><span class="sxs-lookup"><span data-stu-id="5de8b-119">Want to know more about PIN settings?</span></span>

- <span data-ttu-id="5de8b-120">ピンすることが 4 から 12 桁の数字です。デフォルトは 5 です。</span><span class="sxs-lookup"><span data-stu-id="5de8b-120">PINs can be from 4 to 12 digits; the default is 5.</span></span> <span data-ttu-id="5de8b-121">番号は、ピンを作成するときにのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="5de8b-121">Numbers are only used when creating PINs.</span></span> <span data-ttu-id="5de8b-122">文字と特殊文字は使用されません。</span><span class="sxs-lookup"><span data-stu-id="5de8b-122">Letters and special characters aren't used.</span></span>
    
- <span data-ttu-id="5de8b-123">のみ、暗証番号 (pin) は、会議の開催者とビジネス ユーザーは、Skype は、会議を既に開始されていない場合は必須です。</span><span class="sxs-lookup"><span data-stu-id="5de8b-123">A PIN is only required for the meeting organizer when a Skype for Business user hasn't already started the meeting.</span></span> <span data-ttu-id="5de8b-124">場合はすべてのユーザーがダイヤルイン会議、PIN は、会議の開催者、会議を開始するために必要。</span><span class="sxs-lookup"><span data-stu-id="5de8b-124">If everyone is dialing in to the meeting, then the PIN is required for the meeting organizer to start the meeting.</span></span>
    
- <span data-ttu-id="5de8b-125">暗証番号 (pin) のセキュリティ設定は、すべての Microsoft のブリッジに関連付けられている電話番号に適用されます。</span><span class="sxs-lookup"><span data-stu-id="5de8b-125">PIN security settings are applied to all of the phone numbers that are associated with a Microsoft bridge.</span></span> <span data-ttu-id="5de8b-126">各ブリッジに関連付けられている電話番号を使用するすべての会議に適用されます。</span><span class="sxs-lookup"><span data-stu-id="5de8b-126">They will be applied to all meetings that use the phone numbers associated with a given bridge.</span></span> 
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="5de8b-127">Go to the Office 365 admin centerSkype for Business.</span><span class="sxs-lookup"><span data-stu-id="5de8b-127">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="5de8b-128">時間を短縮または、これを自動化するには、[セット CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757)コマンドレットを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="5de8b-128">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757) cmdlet.</span></span>
    
- <span data-ttu-id="5de8b-129">8 PIN の桁数を設定します。`Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`</span><span class="sxs-lookup"><span data-stu-id="5de8b-129">To set the number of digits in the PIN to 8:  `Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`</span></span>
    
- <span data-ttu-id="5de8b-p107">Windows PowerShell は、ユーザーと、ユーザーに許可されていることと許可されていないことを管理するためにあるということです。Windows PowerShell があれば、一元管理を使用して Office 365 を管理し、複数のタスクを抱えているときに、日常の仕事を簡素化することができます。Windows PowerShell を開始するには、これらのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5de8b-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="5de8b-133">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="5de8b-133">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="5de8b-134">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="5de8b-134">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="5de8b-p108">多くのユーザーの設定を同時に変更するときなどは、Office 365 管理センターのみを使用するよりも、Windows PowerShell の方に、速度、わかりやすさ、生産性の点で多くのメリットがあります。</span><span class="sxs-lookup"><span data-stu-id="5de8b-p108">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time. Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="5de8b-137">Windows PowerShell と Lync Online の概要</span><span class="sxs-lookup"><span data-stu-id="5de8b-137">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="5de8b-138">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="5de8b-138">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
    [<span data-ttu-id="5de8b-139">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="5de8b-139">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="5de8b-140">クイック リファレンス: Windows PowerShell を使用した一般的な Lync Online の管理タスクの実行</span><span class="sxs-lookup"><span data-stu-id="5de8b-140">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="5de8b-p109">Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行[](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="5de8b-p109">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5de8b-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="5de8b-143">See also</span></span>

[<span data-ttu-id="5de8b-144">Office 365 での電話会議を使用または購入する</span><span class="sxs-lookup"><span data-stu-id="5de8b-144">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
