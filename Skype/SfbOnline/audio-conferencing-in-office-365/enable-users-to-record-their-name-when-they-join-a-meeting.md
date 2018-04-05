---
title: ユーザーが会議に参加したときに自分の名前を記録できるようにする
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 1d649328-ada7-422d-a074-d6da4da36970
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
description: 'Learn how to enable or disable whether your users can record their names when they join a meeting '
ms.openlocfilehash: 6f1c5c9c86f4b0296340c9185acdc9d505baeda7
ms.sourcegitcommit: ffca287cf70db2cab14cc1a6cb7cea68317bedd1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/05/2018
---
# <a name="enable-users-to-record-their-name-when-they-join-a-meeting"></a><span data-ttu-id="3c931-103">ユーザーが会議に参加したときに自分の名前を記録できるようにする</span><span class="sxs-lookup"><span data-stu-id="3c931-103">Enable users to record their name when they join a meeting</span></span>

<span data-ttu-id="3c931-p101">[] Skype for Business Online でダイヤルイン会議をセットアップしているときには、電話番号とダイヤルインまたは電話会議ブリッジと呼ばれるものを受け取ります。会議ブリッジには、1 つ以上の電話番号 (専用または共有の電話番号の場合もある) が含まれることがあります。</span><span class="sxs-lookup"><span data-stu-id="3c931-p101">When you are setting up Audio Conferencing in Office 365, you will receive phone numbers and what is called an audio conferencing bridge. A conferencing bridge can contain one or more phone numbers that can be a dedicated or shared phone number.</span></span>
  
<span data-ttu-id="3c931-p102">ユーザーが電話を使って会議にダイヤルインすると、その通話は会議ブリッジによって応答されます。会議ブリッジでは、自動応答の音声プロンプトで発信者に応答してから、設定に応じて、お知らせを再生したり、発信者に名前を記録するように依頼したり、会議開催者の PIN セキュリティをセットアップしたりします。PIN が会議開催者に与えられて、開催者は会議を開始できるようになります。ただし、PIN がなくても会議を開始できるように設定できます。</span><span class="sxs-lookup"><span data-stu-id="3c931-p102">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone. The conferencing bridge answers the caller with voice prompts from an auto attendant, and then, depending on their settings, can play notifications, ask callers to record their name, and set up the PIN security for meeting organizers. PINs are given to meeting organizers to allow them to start a meeting. However, you can set it up so a PIN isn't required to start a meeting.</span></span>
  
## <a name="set-whether-callers-should-record-their-name"></a><span data-ttu-id="3c931-110">発信者が名前を記録すべきかどうかを設定する</span><span class="sxs-lookup"><span data-stu-id="3c931-110">Set whether callers should record their name</span></span>

<span data-ttu-id="3c931-111">**ビジネス管理センターは、マイクロソフトのチームと Skype を使用してください。**</span><span class="sxs-lookup"><span data-stu-id="3c931-111">**Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="3c931-112">左側のナビゲーションでは、**会議**に移動 > **会議ブリッジ**です。</span><span class="sxs-lookup"><span data-stu-id="3c931-112">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="3c931-113">**会議ブリッジ**のページの上部には、**ブリッジの設定**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3c931-113">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span> 

3. <span data-ttu-id="3c931-114">有効にするまたは**ミーティングのエントリを有効にして終了の通知をオンにする**を無効にします。</span><span class="sxs-lookup"><span data-stu-id="3c931-114">Enable or disable **Enable meeting entry and exit notifications to be turned on**.</span></span>

4. <span data-ttu-id="3c931-115">[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3c931-115">Click **Apply**.</span></span>


<span data-ttu-id="3c931-116">**ビジネス管理センターに、Skype を使用します。**</span><span class="sxs-lookup"><span data-stu-id="3c931-116">**Using the Skype for Business Admin Center**</span></span>
    
1. <span data-ttu-id="3c931-117">既定値は 5 です。</span><span class="sxs-lookup"><span data-stu-id="3c931-117">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="3c931-118">[ **会議参加エクスペリエンス**] の [ **会議の入退出の通知をオンにする**] で、次のいずれかを選びます。</span><span class="sxs-lookup"><span data-stu-id="3c931-118">Under **Meeting join experience**, see the check box labeled **Enable meeting entry and exit notifications to be turned on**.</span></span>
    
  - <span data-ttu-id="3c931-p103">**オン**: 発信者は、会議に参加する前に名前を記録するように依頼されます。 既定ではオンになっています。</span><span class="sxs-lookup"><span data-stu-id="3c931-p103">**Selected** Callers will be asked to record their name before they enter the meeting. This is selected by default.</span></span>
    
  - <span data-ttu-id="3c931-121">**オフ**: 発信者は、会議に参加する前に名前を記録するように依頼されません。</span><span class="sxs-lookup"><span data-stu-id="3c931-121">**Cleared** Callers won't be asked to record their name before they enter the meeting.</span></span>
    
3. <span data-ttu-id="3c931-122">変更したら [ **保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3c931-122">After you make your changes, click **Save**.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="3c931-123">Windows PowerShell で管理する方法</span><span class="sxs-lookup"><span data-stu-id="3c931-123">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="3c931-124">時間を節約したり、自動化したりするには、[Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757) コマンドレットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="3c931-124">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingTenantSettings ](https://go.microsoft.com/fwlink/?LinkId=715757) cmdlet.</span></span>
    
-  <span data-ttu-id="3c931-p104">Windows PowerShell の場合、Skype for Business Online はユーザーの管理と、ユーザーが許可されている操作や許可されていない操作の管理に使います。Windows PowerShell により、単一の管理ポイントを使って Office 365 を管理でき、複数の作業を実行する必要があるときに日常業務を合理化できます。Windows PowerShell を使い始めるには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3c931-p104">Windows PowerShell is all about managing users and what users are allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="3c931-128">Windows PowerShell で Office 365 を管理する 6 つの理由</span><span class="sxs-lookup"><span data-stu-id="3c931-128">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="3c931-129">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="3c931-129">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="3c931-p105">多くのユーザーの設定を同時に変更するときなどは、Office 365 管理センターのみを使用するよりも、Windows PowerShell の方に、速度、わかりやすさ、生産性の点で多くのメリットがあります。 次のトピックで、これらの利点を説明します。</span><span class="sxs-lookup"><span data-stu-id="3c931-p105">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="3c931-132">Windows PowerShell と Lync Online の概要</span><span class="sxs-lookup"><span data-stu-id="3c931-132">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="3c931-133">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="3c931-133">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="3c931-134">Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行</span><span class="sxs-lookup"><span data-stu-id="3c931-134">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="3c931-p106">[Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="3c931-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="3c931-137">このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「Skype for Business Online 用 Windows PowerShell モジュール」からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="3c931-137">Related topics</span></span>

[<span data-ttu-id="3c931-138">Office 365 での電話会議を使用または購入する</span><span class="sxs-lookup"><span data-stu-id="3c931-138">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
