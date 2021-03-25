---
title: ユーザーが Skype for Business Online で会議に参加するときに自分の名前を記録する
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1d649328-ada7-422d-a074-d6da4da36970
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
description: ユーザーが Skype for Business Online で会議に参加するときに自分の名前を記録できるかどうかを有効または無効にする方法について学習します。
ms.openlocfilehash: 7fd8afb71ee524b20f24f9583ec847adbec2ff43
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51114243"
---
# <a name="enable-users-to-record-their-name-when-they-join-a-meeting-in-skype-for-business-online"></a><span data-ttu-id="91f7c-103">ユーザーが Skype for Business Online で会議に参加するときに自分の名前を記録する</span><span class="sxs-lookup"><span data-stu-id="91f7c-103">Enable users to record their name when they join a meeting in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="91f7c-104">ユーザーが自分の名前を Teams に記録できるようにする必要がある場合は、「[Microsoft Teams で会議に参加するときにユーザーが自分の名前を記録できるようにする](/MicrosoftTeams/enable-users-to-record-their-name-when-they-join-a-meeting-in-teams)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="91f7c-104">If you want to allow users to record their names in Teams, see [Enable users to record their name when they join a meeting in Microsoft Teams](/MicrosoftTeams/enable-users-to-record-their-name-when-they-join-a-meeting-in-teams).</span></span>

<span data-ttu-id="91f7c-105">Microsoft 365 または Office 365 で電話会議をセットアップすると、電話番号と電話会議ブリッジと呼ばれる情報を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="91f7c-105">When you are setting up Audio Conferencing in Microsoft 365 or Office 365, you will receive phone numbers and what is called an audio conferencing bridge.</span></span> <span data-ttu-id="91f7c-106">会議ブリッジには、専用または共有の電話番号である可能性がある 1 つ以上の電話番号を含めできます。</span><span class="sxs-lookup"><span data-stu-id="91f7c-106">A conferencing bridge can contain one or more phone numbers that can be a dedicated or shared phone number.</span></span>
  
<span data-ttu-id="91f7c-p102">ユーザーが電話を使って会議にダイヤルインすると、その通話は会議ブリッジによって応答されます。会議ブリッジでは、自動応答の音声プロンプトで発信者に応答してから、設定に応じて、お知らせを再生したり、発信者に名前を記録するように依頼したり、会議開催者の PIN セキュリティをセットアップしたりします。PIN が会議開催者に与えられて、開催者は会議を開始できるようになります。ただし、PIN がなくても会議を開始できるように設定できます。</span><span class="sxs-lookup"><span data-stu-id="91f7c-p102">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone. The conferencing bridge answers the caller with voice prompts from an auto attendant, and then, depending on their settings, can play notifications, ask callers to record their name, and set up the PIN security for meeting organizers. PINs are given to meeting organizers to allow them to start a meeting. However, you can set it up so a PIN isn't required to start a meeting.</span></span>

## <a name="set-whether-callers-should-record-their-name"></a><span data-ttu-id="91f7c-111">発信者に名前を記録するかどうかを設定する</span><span class="sxs-lookup"><span data-stu-id="91f7c-111">Set whether callers should record their name</span></span>
    
1. <span data-ttu-id="91f7c-112">**Skype for Business 管理センター** の左側のナビゲーション ウィンドウで、[**電話会議**]  >  [**Microsoft ブリッジ設定**] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="91f7c-112">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="91f7c-113">[ **会議参加エクスペリエンス**] の [ **会議の入退出の通知をオンにする**] で、次のいずれかを選びます。</span><span class="sxs-lookup"><span data-stu-id="91f7c-113">Under **Meeting join experience**, see the check box labeled **Enable meeting entry and exit notifications to be turned on**.</span></span>
    
   - <span data-ttu-id="91f7c-p103">**オン**: 発信者は、会議に参加する前に名前を記録するように依頼されます。 既定ではオンになっています。</span><span class="sxs-lookup"><span data-stu-id="91f7c-p103">**Selected** Callers will be asked to record their name before they enter the meeting. This is selected by default.</span></span>
    
   - <span data-ttu-id="91f7c-116">**オフ**: 発信者は、会議に参加する前に名前を記録するように依頼されません。</span><span class="sxs-lookup"><span data-stu-id="91f7c-116">**Cleared** Callers won't be asked to record their name before they enter the meeting.</span></span>
    
3. <span data-ttu-id="91f7c-117">変更したら [ **保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="91f7c-117">After you make your changes, click **Save**.</span></span>
    
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="91f7c-118">Windows PowerShell で管理する方法</span><span class="sxs-lookup"><span data-stu-id="91f7c-118">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="91f7c-119">時間を節約したり、自動化したりするために [、Set-CsOnlineDialInConferencingTenantSettings コマンドレットを使用](/powershell/module/skype/Set-CsOnlineDialInConferencingTenantSettings) できます。</span><span class="sxs-lookup"><span data-stu-id="91f7c-119">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Set-CsOnlineDialInConferencingTenantSettings) cmdlet.</span></span>
    
- <span data-ttu-id="91f7c-120">Windows PowerShellは、ユーザーの管理と、ユーザーに許可されている操作の管理に使います。</span><span class="sxs-lookup"><span data-stu-id="91f7c-120">Windows PowerShell is all about managing users and what users are allowed to do.</span></span> <span data-ttu-id="91f7c-121">Windows PowerShell では、単一の管理ポイントを使用して Microsoft 365 または Office 365 を管理できます。複数のタスクを実行する必要がある場合に毎日の作業を簡略化できます。</span><span class="sxs-lookup"><span data-stu-id="91f7c-121">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="91f7c-122">Windows PowerShell の使用を開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="91f7c-122">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="91f7c-123">Microsoft 365 または Office 365 PowerShell を使用する必要がある理由</span><span class="sxs-lookup"><span data-stu-id="91f7c-123">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="91f7c-124">[Microsoft 365 または Office 365 を他のユーザーとWindows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="91f7c-124">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
- <span data-ttu-id="91f7c-125">Windows PowerShellは、多くのユーザーに対して一度に設定変更を行う場合など、Microsoft 365 管理センターのみを使用する場合と同様に、速度、シンプルさ、生産性に多くの利点があります。</span><span class="sxs-lookup"><span data-stu-id="91f7c-125">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="91f7c-126">次のトピックで、これらの利点を説明します。</span><span class="sxs-lookup"><span data-stu-id="91f7c-126">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="91f7c-127">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="91f7c-127">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="91f7c-128">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="91f7c-128">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="91f7c-129">Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行</span><span class="sxs-lookup"><span data-stu-id="91f7c-129">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > <span data-ttu-id="91f7c-p106">Skype for Business Online 用の Windows PowerShell モジュールがあれば、Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成できます。このモジュールは、64 ビット版のコンピューターでのみサポートされており、「[Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688)」の Microsoft ダウンロード センターからダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="91f7c-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="91f7c-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="91f7c-132">Related topics</span></span>

[<span data-ttu-id="91f7c-133">Microsoft 365 または Office 365 で電話会議を試用または購入する</span><span class="sxs-lookup"><span data-stu-id="91f7c-133">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)