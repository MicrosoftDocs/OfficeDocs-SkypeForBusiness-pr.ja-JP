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
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32229293"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-skype-for-business-online"></a><span data-ttu-id="2d842-103">ビジネス オンラインの Skype で電話会議の会議の暗証番号 (pin) の長さを設定します。</span><span class="sxs-lookup"><span data-stu-id="2d842-103">Set the PIN length for Audio Conferencing meetings in Skype for Business Online</span></span>


> [!NOTE]
> <span data-ttu-id="2d842-104">マイクロソフトのチームでの暗証番号 (pin) の長さを設定する方法については、[マイクロソフトのチーム内の電話会議の会議の暗証番号 (pin) の長さを設定する](/en-us/MicrosoftTeams/Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2d842-104">For information about setting the PIN length in Microsoft Teams, see [Set the PIN length for Audio Conferencing meetings in Microsoft Teams](/en-us/MicrosoftTeams/Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams).</span></span>

<span data-ttu-id="2d842-105">ビジネス用の Skype の電話会議を設定するときに、オーディオ会議ブリッジが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2d842-105">When you are setting up audio conferencing for Skype for Business, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="2d842-106">会議用ブリッジは、1 つまたは複数の電話番号を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="2d842-106">A conferencing bridge can contain one or more phone numbers.</span></span> <span data-ttu-id="2d842-107">設定した電話番号は、ビジネス アプリケーションの Skype の会議の招待に含まれます。</span><span class="sxs-lookup"><span data-stu-id="2d842-107">The phone number you set will be included on the meeting invites for the Skype for Business app.</span></span>
  
<span data-ttu-id="2d842-108">オーディオ会議ブリッジ、電話を使用して会議にダイヤルインしている人のための呼び出しに応答します。</span><span class="sxs-lookup"><span data-stu-id="2d842-108">The audio conferencing bridge answers a call for people who are dialing in to a meeting using a phone.</span></span> <span data-ttu-id="2d842-109">自動応答から、設定によっては、音声メッセージを呼び出し元に応答、通知を再生でき、自分の名前を記録するための呼び出し元に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="2d842-109">It answers the caller with voice prompts from an auto attendant and then, depending on your settings, can play notifications and ask callers to record their name.</span></span> <span data-ttu-id="2d842-110">**マイクロソフト ブリッジの設定**では、会議の通知の設定を変更することができ、会議の参加、会議の開催者によって使用されているピンの長さを設定します。</span><span class="sxs-lookup"><span data-stu-id="2d842-110">**Microsoft bridge settings** allow you to change the settings for meeting notifications and the meeting join experience, and set the length of the PINs that are used by meeting organizers.</span></span> <span data-ttu-id="2d842-111">ミーティングの開催者は、ビジネス アプリケーションに、Skype を使用してミーティングに参加することはできない場合は、会議を開始するためのピンを使用します。</span><span class="sxs-lookup"><span data-stu-id="2d842-111">Meeting organizers use PINs to start meetings if they can't join the meeting using the Skype for Business app.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a><span data-ttu-id="2d842-112">暗証番号 (pin) の長さを設定</span><span class="sxs-lookup"><span data-stu-id="2d842-112">Setting the PIN length</span></span>
 
1. <span data-ttu-id="2d842-113">既定値は 5 です。\*\*\*\*\*\*\*\* > \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="2d842-113">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="2d842-114">[**セキュリティ]** > **暗証番号 (pin) の長さ**を選択し、PIN の桁数を選択し、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2d842-114">Under **Security** > **PIN length**, select the number of digits you want for the PIN, and then click **Save**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="2d842-115">PIN とは異なる、会議の id です。</span><span class="sxs-lookup"><span data-stu-id="2d842-115">A PIN is different from a conference ID.</span></span> <span data-ttu-id="2d842-116">会議 Id は、ミーティングに参加するときに、呼び出し元が使用されます。</span><span class="sxs-lookup"><span data-stu-id="2d842-116">Conference IDs are used by callers when they join the meeting.</span></span> <span data-ttu-id="2d842-117">ミーティングに使用されます。</span><span class="sxs-lookup"><span data-stu-id="2d842-117">They are used to identify the meeting.</span></span> <span data-ttu-id="2d842-118">暗証番号 (pin) を使用して、会議の開催者は、呼び出し元を認証します。</span><span class="sxs-lookup"><span data-stu-id="2d842-118">The PIN is used to authenticate a caller as the meeting organizer.</span></span> 

## <a name="want-to-know-more-about-pin-settings"></a><span data-ttu-id="2d842-119">暗証番号 (pin) の設定の詳細を知りたいとしていますか。</span><span class="sxs-lookup"><span data-stu-id="2d842-119">Want to know more about PIN settings?</span></span>

- <span data-ttu-id="2d842-120">ピンすることが 4 から 12 桁の数字です。デフォルトは 5 です。</span><span class="sxs-lookup"><span data-stu-id="2d842-120">PINs can be from 4 to 12 digits; the default is 5.</span></span> <span data-ttu-id="2d842-121">番号は、ピンを作成するときにのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="2d842-121">Numbers are only used when creating PINs.</span></span> <span data-ttu-id="2d842-122">文字と特殊文字は使用されません。</span><span class="sxs-lookup"><span data-stu-id="2d842-122">Letters and special characters aren't used.</span></span>
    
- <span data-ttu-id="2d842-123">のみ、暗証番号 (pin) は、会議の開催者とビジネス ユーザーは、Skype は、会議を既に開始されていない場合は必須です。</span><span class="sxs-lookup"><span data-stu-id="2d842-123">A PIN is only required for the meeting organizer when a Skype for Business user hasn't already started the meeting.</span></span> <span data-ttu-id="2d842-124">場合はすべてのユーザーがダイヤルイン会議、PIN は、会議の開催者、会議を開始するために必要。</span><span class="sxs-lookup"><span data-stu-id="2d842-124">If everyone is dialing in to the meeting, then the PIN is required for the meeting organizer to start the meeting.</span></span>
    
- <span data-ttu-id="2d842-125">暗証番号 (pin) のセキュリティ設定は、すべての Microsoft のブリッジに関連付けられている電話番号に適用されます。</span><span class="sxs-lookup"><span data-stu-id="2d842-125">PIN security settings are applied to all of the phone numbers that are associated with a Microsoft bridge.</span></span> <span data-ttu-id="2d842-126">各ブリッジに関連付けられている電話番号を使用するすべての会議に適用されます。</span><span class="sxs-lookup"><span data-stu-id="2d842-126">They will be applied to all meetings that use the phone numbers associated with a given bridge.</span></span> 
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="2d842-127">Windows PowerShell での管理方法について</span><span class="sxs-lookup"><span data-stu-id="2d842-127">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="2d842-128">時間を短縮または、これを自動化するには、[セット CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757)コマンドレットを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="2d842-128">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757) cmdlet.</span></span>
    
- <span data-ttu-id="2d842-129">8 PIN の桁数を設定します。`Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`</span><span class="sxs-lookup"><span data-stu-id="2d842-129">To set the number of digits in the PIN to 8:  `Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`</span></span>
    
- <span data-ttu-id="2d842-p107">Windows PowerShell で行うのは、ユーザーを管理し、ユーザーに何を許可して何を禁止するかを管理することです。Windows PowerShell を利用すると、Office 365 の管理を 1 か所で行うことができるので、複数のタスクを担当する管理者の日常業務を単純化できます。Windows PowerShell の使用を開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2d842-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="2d842-133">Office 365 PowerShell を使用する必要がある理由</span><span class="sxs-lookup"><span data-stu-id="2d842-133">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="2d842-134">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="2d842-134">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="2d842-p108">多くのユーザーの設定を同時に変更するときなどは、Office 365 管理センターのみを使用するよりも、Windows PowerShell の方に、速度、わかりやすさ、生産性の点で多くのメリットがあります。</span><span class="sxs-lookup"><span data-stu-id="2d842-p108">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time. Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="2d842-137">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="2d842-137">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="2d842-138">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="2d842-138">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
    [<span data-ttu-id="2d842-139">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="2d842-139">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="2d842-140">Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行</span><span class="sxs-lookup"><span data-stu-id="2d842-140">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="2d842-p109">Skype for Business Online 用の Windows PowerShell モジュールがあれば、Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成できます。このモジュールは、64 ビット版のコンピューターでのみサポートされており、「[Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688)」の Microsoft ダウンロード センターからダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="2d842-p109">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2d842-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="2d842-143">See also</span></span>

[<span data-ttu-id="2d842-144">Office 365 での電話会議を試用または購入する</span><span class="sxs-lookup"><span data-stu-id="2d842-144">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
