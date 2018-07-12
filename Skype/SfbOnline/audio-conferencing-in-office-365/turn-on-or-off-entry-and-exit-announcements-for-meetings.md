---
title: 会議の入退室通知をオンまたはオフにする
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: f2c7b5ea-07b6-4b77-8023-bec9596fcc32
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'エントリを有効にして、Skype、Skype を使用するビジネス管理センターのオンライン ビジネスの会議のためにアナウンスをオンまたはオフを終了する方法について説明します。 '
ms.openlocfilehash: 9cd2c95d0dde2e61ca1f0378fe91a215bdfc2682
ms.sourcegitcommit: 57c8211047e6e6501cd1f9eefddfe4da36cb7d7f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2018
ms.locfileid: "20302153"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings"></a><span data-ttu-id="3929d-103">会議の入退室通知をオンまたはオフにする</span><span class="sxs-lookup"><span data-stu-id="3929d-103">Turn on or off entry and exit announcements for meetings</span></span>

<span data-ttu-id="3929d-104">Office 365 に電話会議を設定する場合、オーディオ会議ブリッジが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3929d-104">When you are setting up Audio Conferencing in Office 365, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="3929d-105">会議用ブリッジは、ビジネスまたはマイクロソフトのチームの会議のため、Skype へのコールを使用する 1 つまたは複数の電話番号を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="3929d-105">A conferencing bridge can contain one or more phone numbers that people will use to call in to a Skype for Business or Microsoft Teams meeting.</span></span> 
  
<span data-ttu-id="3929d-106">会議用ブリッジの電話を使用して会議にダイヤルインするユーザーが呼び出しに応答します。</span><span class="sxs-lookup"><span data-stu-id="3929d-106">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="3929d-107">会議用ブリッジ会議自動アテンダントからの音声メッセージを呼び出し元に応答しの設定によってことができます再生の通知は、呼び出し元が自分の名前を記録し、暗証番号 (pin) のセキュリティを設定するに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="3929d-107">The conferencing bridge answers the caller with voice prompts from a conferencing auto attendant, and then, depending on your settings, can play notifications, ask callers to record their name, and set up the PIN security.</span></span> <span data-ttu-id="3929d-108">Skype をビジネスまたはマイクロソフトのチーム会議の開催者に、暗証番号 (pin) が与えられたことができ、Skype を使用してアプリケーションのビジネスまたはマイクロソフトのチームのミーティングを開始することはできない場合は、会議を開始することです。</span><span class="sxs-lookup"><span data-stu-id="3929d-108">A PIN is given to a Skype for Business or Microsoft Teams meeting organizer, and it allows them to start a meeting if they can't start the meeting using a Skype for Business or Microsoft Teams app.</span></span> <span data-ttu-id="3929d-109">できます、ただし、ように設定すると、暗証番号 (pin) が会議を開始する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="3929d-109">You can, however, set it so that a PIN isn't required to start a meeting.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a><span data-ttu-id="3929d-110">ミーティングの参加オプションの設定</span><span class="sxs-lookup"><span data-stu-id="3929d-110">Setting meeting join options</span></span>

<span data-ttu-id="3929d-111">![チーム ・ ロゴ ・ 30x30.png](../images/teams-logo-30x30.png) **、マイクロソフトのチームとビジネス管理センターの Skype を使用します。**</span><span class="sxs-lookup"><span data-stu-id="3929d-111">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="3929d-112">左側のナビゲーションでは、**会議**に移動 > **会議ブリッジ**です。</span><span class="sxs-lookup"><span data-stu-id="3929d-112">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="3929d-113">**会議ブリッジ**のページの上部には、**ブリッジの設定**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3929d-113">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span> 

3. <span data-ttu-id="3929d-114">**ブリッジの設定**ウィンドウを有効にするまたは**ミーティングのエントリを有効にして終了の通知をオンにする**を無効にします。</span><span class="sxs-lookup"><span data-stu-id="3929d-114">In the **Bridge settings** pane, enable or disable **Enable meeting entry and exit notifications to be turned on**.</span></span> <span data-ttu-id="3929d-115">これがデフォルトで選択されます。</span><span class="sxs-lookup"><span data-stu-id="3929d-115">This is selected by default.</span></span> <span data-ttu-id="3929d-116">場合はこのオプションをオフにすると、データを入力したり、会議を離れると、会議に参加しているユーザーが通知されません。</span><span class="sxs-lookup"><span data-stu-id="3929d-116">If you clear it, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
4. <span data-ttu-id="3929d-117">[**開始/終了のお知らせの種類****名前や電話番号**」または「**トーン**を選択します。</span><span class="sxs-lookup"><span data-stu-id="3929d-117">Under **Entry/exit announcement type**, select **Names or phone numbers** or **Tones**.</span></span>
    
5. <span data-ttu-id="3929d-118">有効にするか、**ミーティングに参加する前に自分の名前を記録するための呼び出し元の確認**を無効にします。</span><span class="sxs-lookup"><span data-stu-id="3929d-118">Enable or disable **Ask callers to record their name before joining the meeting**.</span></span>
    
6. <span data-ttu-id="3929d-119">変更を行ったら、[**適用**を] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3929d-119">After you make your changes, click **Apply**.</span></span>

<span data-ttu-id="3929d-120">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Skype for Business の管理センターを使用する**</span><span class="sxs-lookup"><span data-stu-id="3929d-120">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
    
1. <span data-ttu-id="3929d-121">既定値は 5 です。</span><span class="sxs-lookup"><span data-stu-id="3929d-121">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="3929d-122">**会議参加の経験**をするには、[をオンまたはオフの**ミーティングのエントリを有効にしてオンにする通知を終了**します。</span><span class="sxs-lookup"><span data-stu-id="3929d-122">Under **Meeting join experience**, select or clear **Enable meeting entry and exit notifications to be turned on**.</span></span> <span data-ttu-id="3929d-123">これがデフォルトで選択されます。</span><span class="sxs-lookup"><span data-stu-id="3929d-123">This is selected by default.</span></span> <span data-ttu-id="3929d-124">場合はこのオプションをオフにすると、データを入力したり、会議を離れると、会議に参加しているユーザーが通知されません。</span><span class="sxs-lookup"><span data-stu-id="3929d-124">If you clear it, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
3. <span data-ttu-id="3929d-125">[**開始/終了のお知らせの種類****名前や電話番号**」または「**トーン**を選択します。</span><span class="sxs-lookup"><span data-stu-id="3929d-125">Under **Entry/exit announcement type**, select **Names or phone numbers** or **Tones**.</span></span>
    
4. <span data-ttu-id="3929d-126">確認するか、**ミーティングに参加する前に自分の名前を記録するための呼び出し元の確認**をオフにします。</span><span class="sxs-lookup"><span data-stu-id="3929d-126">Check or uncheck **Ask callers to record their name before joining the meeting**.</span></span>
    
5. <span data-ttu-id="3929d-127">変更したら [ **保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3929d-127">After you make your changes, click **Save**.</span></span>
    

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="3929d-128">Windows PowerShell で管理する方法</span><span class="sxs-lookup"><span data-stu-id="3929d-128">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="3929d-129">時間を短縮または、これを自動化するには、[セット CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/en-us/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps)コマンドレットを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="3929d-129">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/en-us/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet.</span></span>
    
-  <span data-ttu-id="3929d-p105">Windows PowerShell の場合、Skype for Business Online はユーザーの管理と、ユーザーが許可されている操作や許可されていない操作の管理に使います。Windows PowerShell により、単一の管理ポイントを使って Office 365 を管理でき、複数の作業を実行する必要があるときに日常業務を合理化できます。Windows PowerShell を使い始めるには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3929d-p105">When it comes to Windows PowerShell, Skype for Business Online is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="3929d-133">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="3929d-133">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="3929d-134">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="3929d-134">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="3929d-135">Windows PowerShell には、実行しようとする設定の変更多くのユーザーを一度に 1 つなどの Office 365 管理センターを使用するだけでスピード、シンプルさと生産性に多くの利点があります。</span><span class="sxs-lookup"><span data-stu-id="3929d-135">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="3929d-136">次のトピックで、これらの利点を説明します。</span><span class="sxs-lookup"><span data-stu-id="3929d-136">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="3929d-137">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="3929d-137">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="3929d-138">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="3929d-138">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="3929d-139">Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行</span><span class="sxs-lookup"><span data-stu-id="3929d-139">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="3929d-p107">[Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="3929d-p107">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="3929d-142">このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「Skype for Business Online 用 Windows PowerShell モジュール」からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="3929d-142">Related topics</span></span>

[<span data-ttu-id="3929d-143">電話会議に関するよくある質問</span><span class="sxs-lookup"><span data-stu-id="3929d-143">Audio Conferencing common questions</span></span>](audio-conferencing-common-questions.md)
