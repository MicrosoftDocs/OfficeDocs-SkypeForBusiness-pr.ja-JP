---
title: "オーディオ会議ブリッジの設定を変更します。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 783fad3f-b77c-422b-b91f-7c8b0af324fb
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "呼び出し元のメッセージを表示し、クライアントのビジネスの Skype を使用していないことと、名と会議の開催者のピンを収集するために使用されるマイクロソフトでは、ダイヤルイン会議ブリッジの設定を変更する必要があります手順を取得します。 "
ms.openlocfilehash: 5da33e083999f00d217a86455f61fd58ca2d1713
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/15/2017
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a><span data-ttu-id="e0240-103">オーディオ会議ブリッジの設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="e0240-103">Change the settings for an Audio Conferencing bridge</span></span>

<span data-ttu-id="e0240-104">Office 365 に電話会議を設定する場合、オーディオ会議ブリッジと呼ばれますから、ユーザーの電話番号が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e0240-104">When you are setting up Audio Conferencing in Office 365, you will receive phone numbers for your users from what is called an audio conferencing bridge.</span></span> <span data-ttu-id="e0240-105">会議用ブリッジは、1 つまたは複数の電話番号を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="e0240-105">A conferencing bridge can contain one or more phone numbers.</span></span> <span data-ttu-id="e0240-106">これらの電話番号は、呼び出し元が、会議にダイヤルインするときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="e0240-106">These phone numbers are used when callers dial in to a meeting.</span></span> <span data-ttu-id="e0240-107">電話番号では、ビジネスまたはマイクロソフトのチームの会議出席依頼の Skype の下部に含まれています。</span><span class="sxs-lookup"><span data-stu-id="e0240-107">The phone number is included at the bottom of the Skype for Business or Microsoft Teams meeting invite.</span></span>
  
<span data-ttu-id="e0240-108">会議用ブリッジが呼び出しに応答し、会議自動アテンダント、およびその後、設定によってを使用して音声メッセージを呼び出し元を確認できます通知を再生、自分の名前を記録するための呼び出し元を確認、暗証番号 (pin) の設定を制御します。</span><span class="sxs-lookup"><span data-stu-id="e0240-108">The conferencing bridge answers a call and prompts the caller with voice prompts using a meeting auto attendant, and then, depending on your settings, it can play notifications, ask callers to record their name, and control the PIN settings.</span></span> <span data-ttu-id="e0240-109">ピンはされたミーティングの開催者に許可するように、会議を開始するが使用していない、Skype アプリのビジネスまたはマイクロソフトのチームにします。</span><span class="sxs-lookup"><span data-stu-id="e0240-109">PINs are given to meeting organizers to allow them to start a meeting when they are aren't using a Skype for Business or Microsoft Teams app.</span></span>

    > [!IMPORTANT]
    > A PIN is only required for the meeting organizer when a Skype for Business or Microsoft Teams app user hasn't already started the meeting. If everyone is dialing in to the meeting, the PIN is required for the meeting organizer to start the meeting. 
  
## <a name="change-the-settings-for-an-audio-conferencing-bridge"></a><span data-ttu-id="e0240-110">オーディオ会議ブリッジの設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="e0240-110">Change the settings for an audio conferencing bridge</span></span>

 <span data-ttu-id="e0240-111">**呼び出し元がミーティングに参加するときに会議の経験を設定します。**</span><span class="sxs-lookup"><span data-stu-id="e0240-111">**Set up the meeting experience when callers join a meeting**</span></span>
  
1. <span data-ttu-id="e0240-112">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="e0240-112">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="e0240-113">**Office 365 管理センター**を参照して > **ビジネス用の Skype**です。</span><span class="sxs-lookup"><span data-stu-id="e0240-113">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="e0240-114">**ビジネス管理センターの Skype**では、左側のナビゲーションで移動**電話会議**に > **Microsoft ブリッジ設定**します。</span><span class="sxs-lookup"><span data-stu-id="e0240-114">In the **Skype for Business admin center**, in the left navigation go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="e0240-115">**Microsoft ブリッジの設定**ページで、[**会議参加の経験**をするには、次のコマンドを選択します。</span><span class="sxs-lookup"><span data-stu-id="e0240-115">On the **Microsoft bridge settings** page, under **Meeting join experience**, select:</span></span>
    
  - <span data-ttu-id="e0240-116">**会議エントリを有効にして終了の通知をオンにする**これがデフォルトで選択されます。</span><span class="sxs-lookup"><span data-stu-id="e0240-116">**Enable meeting entry and exit notifications to be turned on** This is selected by default.</span></span> <span data-ttu-id="e0240-117">チェック ボックスをオフにするとデータを入力したり、会議を離れると、会議に参加しているユーザーが通知はありません。</span><span class="sxs-lookup"><span data-stu-id="e0240-117">If you clear the check box, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
    <span data-ttu-id="e0240-118">**会議エントリを有効にして終了の通知をオンにする**を選択すると、**開始/終了のお知らせの種類**] ボックスの一覧からこれらのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="e0240-118">When you select **Enable meeting entry and exit notifications to be turned on**, you can select these options from the **Entry/exit announcement type** list:</span></span>
    
  - <span data-ttu-id="e0240-119">**名前や電話番号**ユーザーが会議にダイヤルインするときは、それに参加するときに、電話番号が再生されます。</span><span class="sxs-lookup"><span data-stu-id="e0240-119">**Names or phone numbers** When users dial in to a meeting, their phone number will be played when they join it.</span></span>
    
  - <span data-ttu-id="e0240-120">**トーン**ユーザーが会議にダイヤルインするときは、それに参加するときに、オーディオの音が再生されます。</span><span class="sxs-lookup"><span data-stu-id="e0240-120">**Tones** When users dial in to a meeting, an audio tone will be played when they join it.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e0240-121">**トーン**を使用して、お知らせの種類としては、すべてのお客様には、現在利用可能なプレビュー機能として。</span><span class="sxs-lookup"><span data-stu-id="e0240-121">Using **Tone** as the announcement type is currently available to all customers as a preview feature.</span></span>
  
  - <span data-ttu-id="e0240-122">**ミーティングに参加する前に自分の名前を記録する呼び出し元を確認**これがデフォルトで選択されます。</span><span class="sxs-lookup"><span data-stu-id="e0240-122">**Ask callers to record their name before joining the meeting** This is selected by default.</span></span> <span data-ttu-id="e0240-123">チェック ボックスをオフにした場合は、会議に参加する前に自分の名前を記録する呼び出し元を求められますされません。</span><span class="sxs-lookup"><span data-stu-id="e0240-123">If you clear the check box, callers won't be asked to record their name before they join a meeting.</span></span>
    
5. <span data-ttu-id="e0240-124">変更を行ったら、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e0240-124">After you make your changes, click **Save**.</span></span>
    
<span data-ttu-id="e0240-125">**会議の暗証番号 (pin) の長さを設定します。**</span><span class="sxs-lookup"><span data-stu-id="e0240-125">**Set the PIN length for meetings**</span></span>
  
1. <span data-ttu-id="e0240-126">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="e0240-126">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="e0240-127">**Office 365 管理センター**を参照して > **ビジネス用の Skype**です。</span><span class="sxs-lookup"><span data-stu-id="e0240-127">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="e0240-128">**電話会議**には、**ビジネス管理センターの Skype**、左側のナビゲーションでの > **Microsoft ブリッジ設定**します。</span><span class="sxs-lookup"><span data-stu-id="e0240-128">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="e0240-129">**Microsoft ブリッジの設定**] ページの [**セキュリティ**] の下に**暗証番号 (pin) の長さ**] ボックスの一覧で、[暗証番号 (pin) に使用桁の番号を入力し、し、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e0240-129">On the **Microsoft bridge settings** page, under **Security**, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="e0240-130">暗証番号 (pin) は、4 桁から 12 桁の間である必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0240-130">The PIN must be between 4 and 12 digits.</span></span> 
  
<span data-ttu-id="e0240-131">**ユーザーに電子メールを送信するかどうかを選択します。**</span><span class="sxs-lookup"><span data-stu-id="e0240-131">**Select whether to send email to your users**</span></span>
  
1. <span data-ttu-id="e0240-132">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="e0240-132">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="e0240-133">**Office 365 管理センター**を参照して > **ビジネス用の Skype**です。</span><span class="sxs-lookup"><span data-stu-id="e0240-133">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="e0240-134">**電話会議**には、**ビジネス管理センターの Skype**、左側のナビゲーションでの > **Microsoft ブリッジ設定**します。</span><span class="sxs-lookup"><span data-stu-id="e0240-134">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="e0240-135">**Microsoft ブリッジの設定**] ページを選択や**、オーディオ会議の構成が変更された場合、ユーザーに e メールを自動的に送信**するには、オフにし、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e0240-135">On the **Microsoft bridge settings** page, select or clear **Automatically send emails to users if their audio conferencing configuration changes**, and then click **Save**.</span></span>
    
    <span data-ttu-id="e0240-136">詳細については、[電子メールは、ユーザーが電話会議の設定を変更するときに自動的に送信](emails-sent-to-users-when-their-settings-change.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0240-136">See [Emails automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md) for more information.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="e0240-137">Windows PowerShell で管理する方法</span><span class="sxs-lookup"><span data-stu-id="e0240-137">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="e0240-138">時間を節約またはこのプロセスを自動化するには、[セット CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 )コマンドレットを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="e0240-138">To save time or automate this process, you can use the [Set-CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 ) cmdlet.</span></span>
    
- <span data-ttu-id="e0240-139">Windows PowerShell は、ユーザーを管理するユーザーを許可または許可されません。</span><span class="sxs-lookup"><span data-stu-id="e0240-139">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="e0240-140">Windows PowerShell を実行する複数のタスクがある場合、日常的な作業を簡素化する管理の単一ポイントを使用して Office 365 を管理できます。</span><span class="sxs-lookup"><span data-stu-id="e0240-140">With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="e0240-141">Windows PowerShell を使い始めるには、以下のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0240-141">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="e0240-142">Office 365 の PowerShell を使用する必要がある理由</span><span class="sxs-lookup"><span data-stu-id="e0240-142">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="e0240-143">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="e0240-143">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="e0240-144">Windows PowerShell には、実行しようとする設定の変更多くのユーザーを一度に 1 つなど、Office 365 管理センターを使用するだけでスピード、シンプルさと生産性に多くの利点があります。</span><span class="sxs-lookup"><span data-stu-id="e0240-144">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="e0240-145">次のトピックで、これらの利点について学習します。</span><span class="sxs-lookup"><span data-stu-id="e0240-145">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="e0240-146">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="e0240-146">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="e0240-147">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="e0240-147">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="e0240-148">Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行</span><span class="sxs-lookup"><span data-stu-id="e0240-148">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="e0240-p107">Skype for Business Online 用 Windows PowerShell モジュールでは、リモート Windows PowerShell セッションを作成して Skype for Business Online に接続できます。このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「[Skype for Business Online 用 Windows PowerShell モジュール](https://go.microsoft.com/fwlink/?LinkId=294688)」からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="e0240-p107">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="e0240-151">関連トピック</span><span class="sxs-lookup"><span data-stu-id="e0240-151">Related topics</span></span>

[<span data-ttu-id="e0240-152">Skype for Business および Microsoft Teams の電話会議のセットアップ</span><span class="sxs-lookup"><span data-stu-id="e0240-152">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](set-up-audio-conferencing.md)

