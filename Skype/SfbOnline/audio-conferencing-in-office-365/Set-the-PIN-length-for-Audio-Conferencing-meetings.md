---
title: Skype for Business Online で電話会議会議の PIN の長さを設定する
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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: PIN の長さと要件のパラメーターについて説明し、会議の長さを設定する方法Skype for Business。
ms.openlocfilehash: 2e4e1d087ad6e0f91d034c6a5abe513e8b3aab01
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238602"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-skype-for-business-online"></a><span data-ttu-id="875b8-103">Skype for Business Online で電話会議会議の PIN の長さを設定する</span><span class="sxs-lookup"><span data-stu-id="875b8-103">Set the PIN length for Audio Conferencing meetings in Skype for Business Online</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]


> [!NOTE]
> <span data-ttu-id="875b8-104">PIN の長さを設定する方法については、「Microsoft Teams で電話会議の PIN の長さを設定する[」をMicrosoft Teams。](/en-us/MicrosoftTeams/Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams)</span><span class="sxs-lookup"><span data-stu-id="875b8-104">For information about setting the PIN length in Microsoft Teams, see [Set the PIN length for Audio Conferencing meetings in Microsoft Teams](/en-us/MicrosoftTeams/Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams).</span></span>

<span data-ttu-id="875b8-105">会議用に電話会議を設定Skype for Business、電話会議ブリッジが表示されます。</span><span class="sxs-lookup"><span data-stu-id="875b8-105">When you are setting up audio conferencing for Skype for Business, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="875b8-106">電話会議ブリッジには 1 つまたは複数の電話番号を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="875b8-106">A conferencing bridge can contain one or more phone numbers.</span></span> <span data-ttu-id="875b8-107">設定した電話番号は、新しいアプリの会議出席Skype for Businessされます。</span><span class="sxs-lookup"><span data-stu-id="875b8-107">The phone number you set will be included on the meeting invites for the Skype for Business app.</span></span>
  
<span data-ttu-id="875b8-108">電話会議ブリッジは、電話を使用して会議にダイヤルインしようとしているユーザーの呼び出しに応答します。</span><span class="sxs-lookup"><span data-stu-id="875b8-108">The audio conferencing bridge answers a call for people who are dialing in to a meeting using a phone.</span></span> <span data-ttu-id="875b8-109">自動応答からの音声プロンプトで呼び出し元に応答し、設定に応じて通知を再生し、発信者に自分の名前を記録するよう要求できます。</span><span class="sxs-lookup"><span data-stu-id="875b8-109">It answers the caller with voice prompts from an auto attendant and then, depending on your settings, can play notifications and ask callers to record their name.</span></span> <span data-ttu-id="875b8-110">**Microsoft Bridge の設定** を使用すると、会議通知と会議参加エクスペリエンスの設定を変更し、会議開催者が使用する PIN の長さを設定できます。</span><span class="sxs-lookup"><span data-stu-id="875b8-110">**Microsoft bridge settings** allow you to change the settings for meeting notifications and the meeting join experience, and set the length of the PINs that are used by meeting organizers.</span></span> <span data-ttu-id="875b8-111">会議の開催者は、新しいアプリを使用して会議に参加できない場合、PIN を使用してSkype for Businessします。</span><span class="sxs-lookup"><span data-stu-id="875b8-111">Meeting organizers use PINs to start meetings if they can't join the meeting using the Skype for Business app.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a><span data-ttu-id="875b8-112">PIN の長さの設定</span><span class="sxs-lookup"><span data-stu-id="875b8-112">Setting the PIN length</span></span>
 
1. <span data-ttu-id="875b8-113">**Skype for Business 管理センター** の左側のナビゲーション ウィンドウで、[**電話会議**]  >  [**Microsoft ブリッジ設定**] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="875b8-113">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="875b8-114">[**セキュリティ**  >  **PIN の長さ**] で、PIN に使用する桁数を選択し、[保存] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="875b8-114">Under **Security** > **PIN length**, select the number of digits you want for the PIN, and then click **Save**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="875b8-115">PIN は会議 ID とは異なります。</span><span class="sxs-lookup"><span data-stu-id="875b8-115">A PIN is different from a conference ID.</span></span> <span data-ttu-id="875b8-116">会議 ID は、発信者が会議に参加するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="875b8-116">Conference IDs are used by callers when they join the meeting.</span></span> <span data-ttu-id="875b8-117">会議を識別するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="875b8-117">They are used to identify the meeting.</span></span> <span data-ttu-id="875b8-118">PIN は、発信者を会議開催者として認証するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="875b8-118">The PIN is used to authenticate a caller as the meeting organizer.</span></span> 

## <a name="want-to-know-more-about-pin-settings"></a><span data-ttu-id="875b8-119">PIN 設定の詳細については、次のページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="875b8-119">Want to know more about PIN settings?</span></span>

- <span data-ttu-id="875b8-120">PIN は 4 ~ 12 桁です。既定値は 5 です。</span><span class="sxs-lookup"><span data-stu-id="875b8-120">PINs can be from 4 to 12 digits; the default is 5.</span></span> <span data-ttu-id="875b8-121">数値は、PIN を作成するときにのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="875b8-121">Numbers are only used when creating PINs.</span></span> <span data-ttu-id="875b8-122">文字と特殊文字は使用されません。</span><span class="sxs-lookup"><span data-stu-id="875b8-122">Letters and special characters aren't used.</span></span>
    
- <span data-ttu-id="875b8-123">PIN は、ユーザーが会議を開始していないSkype for Business開催者にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="875b8-123">A PIN is only required for the meeting organizer when a Skype for Business user hasn't already started the meeting.</span></span> <span data-ttu-id="875b8-124">全員が会議にダイヤルインしている場合、会議の開催者が会議を開始するには PIN が必要です。</span><span class="sxs-lookup"><span data-stu-id="875b8-124">If everyone is dialing in to the meeting, then the PIN is required for the meeting organizer to start the meeting.</span></span>
    
- <span data-ttu-id="875b8-125">PIN のセキュリティ設定は、Microsoft ブリッジに関連付けられているすべての電話番号に適用されます。</span><span class="sxs-lookup"><span data-stu-id="875b8-125">PIN security settings are applied to all of the phone numbers that are associated with a Microsoft bridge.</span></span> <span data-ttu-id="875b8-126">特定のブリッジに関連付けられている電話番号を使用する会議に適用されます。</span><span class="sxs-lookup"><span data-stu-id="875b8-126">They will be applied to all meetings that use the phone numbers associated with a given bridge.</span></span> 
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="875b8-127">Windows PowerShell での管理方法について</span><span class="sxs-lookup"><span data-stu-id="875b8-127">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="875b8-128">時間を節約したり、自動化したりするには [、Set-CsOnlineDialInConferencingTenantSettings コマンドレットを使用](/powershell/module/skype/Set-CsOnlineDialInConferencingTenantSettings) できます。</span><span class="sxs-lookup"><span data-stu-id="875b8-128">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Set-CsOnlineDialInConferencingTenantSettings) cmdlet.</span></span>
    
- <span data-ttu-id="875b8-129">PIN の桁数を 8 に設定するには:  `Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`</span><span class="sxs-lookup"><span data-stu-id="875b8-129">To set the number of digits in the PIN to 8:  `Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`</span></span>
    
- <span data-ttu-id="875b8-130">Windows PowerShellは、ユーザーの管理と、ユーザーが許可または許可されていない操作についてすべて行います。</span><span class="sxs-lookup"><span data-stu-id="875b8-130">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="875b8-131">このWindows PowerShell、1 つの管理Microsoft 365またはOffice 365を管理し、複数のタスクを実行する場合に毎日の作業を簡略化できます。</span><span class="sxs-lookup"><span data-stu-id="875b8-131">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="875b8-132">Windows PowerShell の使用を開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="875b8-132">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="875b8-133">PowerShell で使用する必要があるMicrosoft 365またはOffice 365理由</span><span class="sxs-lookup"><span data-stu-id="875b8-133">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="875b8-134">[アプリを使用してMicrosoft 365またはOffice 365を管理Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="875b8-134">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
- <span data-ttu-id="875b8-p108">多くのユーザーの設定を同時に変更するときなどは、Microsoft 365 管理センターのみを使用するよりも、Windows PowerShell を使用した方が、速度、わかりやすさ、生産性の点で多くのメリットがあります。次のトピックで、これらの利点を説明します。</span><span class="sxs-lookup"><span data-stu-id="875b8-p108">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making settings changes for many users at one time. Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="875b8-137">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="875b8-137">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="875b8-138">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="875b8-138">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    [<span data-ttu-id="875b8-139">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="875b8-139">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="875b8-140">Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行</span><span class="sxs-lookup"><span data-stu-id="875b8-140">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > <span data-ttu-id="875b8-p109">Skype for Business Online 用の Windows PowerShell モジュールがあれば、Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成できます。このモジュールは、64 ビット版のコンピューターでのみサポートされており、「[Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688)」の Microsoft ダウンロード センターからダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="875b8-p109">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="see-also"></a><span data-ttu-id="875b8-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="875b8-143">See also</span></span>

[<span data-ttu-id="875b8-144">電話会議を試用または購入するには、Microsoft 365またはOffice 365</span><span class="sxs-lookup"><span data-stu-id="875b8-144">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
