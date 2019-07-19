---
title: Skype for Business Online での電話会議の PIN の長さを設定する
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
f1keywords: None
ms.custom:
- Audio Conferencing
description: PIN の長さと要件のパラメーターについて説明し、「Skype for Business での会議の長さを設定する方法」を参照してください。
ms.openlocfilehash: 4e4308eab334b37d32cbd53d047ba5fd077a1cad
ms.sourcegitcommit: 4c041e8a7c39bd6517605ed7fc9aab18cf466596
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/18/2019
ms.locfileid: "35792739"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-skype-for-business-online"></a><span data-ttu-id="58aa3-103">Skype for Business Online での電話会議の PIN の長さを設定する</span><span class="sxs-lookup"><span data-stu-id="58aa3-103">Set the PIN length for Audio Conferencing meetings in Skype for Business Online</span></span>


> [!NOTE]
> <span data-ttu-id="58aa3-104">Microsoft Teams で PIN の長さを設定する方法については、「 [Microsoft teams で電話会議の pin の長さを設定](/en-us/MicrosoftTeams/Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="58aa3-104">For information about setting the PIN length in Microsoft Teams, see [Set the PIN length for Audio Conferencing meetings in Microsoft Teams](/en-us/MicrosoftTeams/Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams).</span></span>

<span data-ttu-id="58aa3-105">Skype for Business の電話会議をセットアップするときには、電話会議ブリッジを取得します。</span><span class="sxs-lookup"><span data-stu-id="58aa3-105">When you are setting up audio conferencing for Skype for Business, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="58aa3-106">電話会議ブリッジには 1 つまたは複数の電話番号を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="58aa3-106">A conferencing bridge can contain one or more phone numbers.</span></span> <span data-ttu-id="58aa3-107">設定した電話番号は、Skype for Business アプリの会議出席依頼に含まれます。</span><span class="sxs-lookup"><span data-stu-id="58aa3-107">The phone number you set will be included on the meeting invites for the Skype for Business app.</span></span>
  
<span data-ttu-id="58aa3-108">電話会議ブリッジは、電話を使って会議にダイヤルインしているユーザーに対して、通話に応答します。</span><span class="sxs-lookup"><span data-stu-id="58aa3-108">The audio conferencing bridge answers a call for people who are dialing in to a meeting using a phone.</span></span> <span data-ttu-id="58aa3-109">自動応答からの音声プロンプトで、発信者に応答し、設定に応じて、通知を再生し、発信者に名前を記録するように依頼することができます。</span><span class="sxs-lookup"><span data-stu-id="58aa3-109">It answers the caller with voice prompts from an auto attendant and then, depending on your settings, can play notifications and ask callers to record their name.</span></span> <span data-ttu-id="58aa3-110">**Microsoft bridge の設定**を使用すると、会議の通知と会議の参加エクスペリエンスの設定を変更したり、会議の開催者によって使用される pin の長さを設定したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="58aa3-110">**Microsoft bridge settings** allow you to change the settings for meeting notifications and the meeting join experience, and set the length of the PINs that are used by meeting organizers.</span></span> <span data-ttu-id="58aa3-111">会議の開催者が Skype for Business アプリを使って会議に参加できない場合は、Pin を使って会議を開始します。</span><span class="sxs-lookup"><span data-stu-id="58aa3-111">Meeting organizers use PINs to start meetings if they can't join the meeting using the Skype for Business app.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a><span data-ttu-id="58aa3-112">PIN の長さを設定する</span><span class="sxs-lookup"><span data-stu-id="58aa3-112">Setting the PIN length</span></span>
 
1. <span data-ttu-id="58aa3-113">**Skype for Business 管理センター**の左側のナビゲーション ウィンドウで、[**電話会議**]  >  [**Microsoft ブリッジ設定**] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="58aa3-113">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="58aa3-114">[**セキュリティ** > **pin の長さ**] で、pin に必要な数字の数を選び、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="58aa3-114">Under **Security** > **PIN length**, select the number of digits you want for the PIN, and then click **Save**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="58aa3-115">PIN が会議 ID とは異なります。</span><span class="sxs-lookup"><span data-stu-id="58aa3-115">A PIN is different from a conference ID.</span></span> <span data-ttu-id="58aa3-116">会議 Id は、発信者が会議に参加するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="58aa3-116">Conference IDs are used by callers when they join the meeting.</span></span> <span data-ttu-id="58aa3-117">会議を識別するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="58aa3-117">They are used to identify the meeting.</span></span> <span data-ttu-id="58aa3-118">PIN は、会議の開催者として発信者を認証するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="58aa3-118">The PIN is used to authenticate a caller as the meeting organizer.</span></span> 

## <a name="want-to-know-more-about-pin-settings"></a><span data-ttu-id="58aa3-119">PIN の設定について詳しく知りたいですか?</span><span class="sxs-lookup"><span data-stu-id="58aa3-119">Want to know more about PIN settings?</span></span>

- <span data-ttu-id="58aa3-120">Pin は 4 ~ 12 桁にすることができます。既定値は5です。</span><span class="sxs-lookup"><span data-stu-id="58aa3-120">PINs can be from 4 to 12 digits; the default is 5.</span></span> <span data-ttu-id="58aa3-121">数値はピンの作成時にのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="58aa3-121">Numbers are only used when creating PINs.</span></span> <span data-ttu-id="58aa3-122">文字と特殊文字は使用されません。</span><span class="sxs-lookup"><span data-stu-id="58aa3-122">Letters and special characters aren't used.</span></span>
    
- <span data-ttu-id="58aa3-123">PIN は、Skype for Business ユーザーが会議を開始していない場合に、会議の開催者にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="58aa3-123">A PIN is only required for the meeting organizer when a Skype for Business user hasn't already started the meeting.</span></span> <span data-ttu-id="58aa3-124">すべてのユーザーが会議にダイヤルインしている場合、会議の開催者が会議を開始するには、PIN が必要です。</span><span class="sxs-lookup"><span data-stu-id="58aa3-124">If everyone is dialing in to the meeting, then the PIN is required for the meeting organizer to start the meeting.</span></span>
    
- <span data-ttu-id="58aa3-125">PIN のセキュリティ設定は、Microsoft bridge に関連付けられているすべての電話番号に適用されます。</span><span class="sxs-lookup"><span data-stu-id="58aa3-125">PIN security settings are applied to all of the phone numbers that are associated with a Microsoft bridge.</span></span> <span data-ttu-id="58aa3-126">これらは、特定のブリッジに関連付けられている電話番号を使用するすべての会議に適用されます。</span><span class="sxs-lookup"><span data-stu-id="58aa3-126">They will be applied to all meetings that use the phone numbers associated with a given bridge.</span></span> 
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="58aa3-127">Windows PowerShell での管理方法について</span><span class="sxs-lookup"><span data-stu-id="58aa3-127">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="58aa3-128">時間を節約したり、自動化したりするには、 [-](https://go.microsoft.com/fwlink/?LinkId=715757)コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="58aa3-128">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757) cmdlet.</span></span>
    
- <span data-ttu-id="58aa3-129">PIN の桁の桁数を8に設定するには、次の操作を行います。`Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`</span><span class="sxs-lookup"><span data-stu-id="58aa3-129">To set the number of digits in the PIN to 8:  `Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`</span></span>
    
- <span data-ttu-id="58aa3-p107">Windows PowerShell で行うのは、ユーザーを管理し、ユーザーに何を許可して何を禁止するかを管理することです。Windows PowerShell を利用すると、Office 365 の管理を 1 か所で行うことができるので、複数のタスクを担当する管理者の日常業務を単純化できます。Windows PowerShell の使用を開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="58aa3-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="58aa3-133">Office 365 PowerShell を使用する必要がある理由</span><span class="sxs-lookup"><span data-stu-id="58aa3-133">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="58aa3-134">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="58aa3-134">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="58aa3-135">Windows PowerShell には、Microsoft 365 管理センターを使用する場合にのみ、速度、簡素化、生産性を高めるためのさまざまな利点があります。たとえば、多くのユーザーの設定を一度に変更する場合です。</span><span class="sxs-lookup"><span data-stu-id="58aa3-135">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="58aa3-136">次のトピックで、これらの利点を説明します。</span><span class="sxs-lookup"><span data-stu-id="58aa3-136">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="58aa3-137">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="58aa3-137">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="58aa3-138">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="58aa3-138">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
    [<span data-ttu-id="58aa3-139">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="58aa3-139">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="58aa3-140">Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行</span><span class="sxs-lookup"><span data-stu-id="58aa3-140">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="58aa3-p109">Skype for Business Online 用の Windows PowerShell モジュールがあれば、Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成できます。このモジュールは、64 ビット版のコンピューターでのみサポートされており、「[Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688)」の Microsoft ダウンロード センターからダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="58aa3-p109">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="see-also"></a><span data-ttu-id="58aa3-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="58aa3-143">See also</span></span>

[<span data-ttu-id="58aa3-144">Office 365 での電話会議を試用または購入する</span><span class="sxs-lookup"><span data-stu-id="58aa3-144">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
