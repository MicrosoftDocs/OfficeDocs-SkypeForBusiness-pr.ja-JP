---
title: "電話会議ブリッジの設定を変更します。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 783fad3f-b77c-422b-b91f-7c8b0af324fb
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
description: "発信者に応答メッセージを表示して、for Business のクライアント Skype これらを使っていない場合は、名前との会議の開催者 pin を収集するに使用する Microsoft ダイヤルイン会議ブリッジの設定を変更するのには必要な手順を取得します。 "
ms.openlocfilehash: f37af15b4ab66eb5765cccbdba63b3bb6bb14597
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a><span data-ttu-id="8cdf7-103">電話会議ブリッジの設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="8cdf7-103">Change the settings for an Audio Conferencing bridge</span></span>

<span data-ttu-id="8cdf7-p101">Office 365 での電話会議をセットアップするときに、電話会議ブリッジと呼ばれるからユーザーの電話番号が表示されます。会議ブリッジには、1 つ以上の電話番号を含めることができます。これらの電話番号は、発信者が会議にダイヤルインするときに使用されます。電話番号が、Skype for Business または Microsoft チーム会議の出席依頼の下部に含まれています。</span><span class="sxs-lookup"><span data-stu-id="8cdf7-p101">When you are setting up Audio Conferencing in Office 365, you will receive phone numbers for your users from what is called an audio conferencing bridge. A conferencing bridge can contain one or more phone numbers. These phone numbers are used when callers dial in to a meeting. The phone number is included at the bottom of the Skype for Business or Microsoft Teams meeting invite.</span></span>
  
<span data-ttu-id="8cdf7-p102">会議ブリッジが呼び出しに応答と会議の自動応答、し、自分の設定によっての使用を促すボイス メッセージと発信者のプロンプトをできます通知を再生、発信者相手の名前を記録するように依頼し PIN の設定を制御します。Pin ができるようにするために、会議の開催者与えられる会議を開始する場合を使っていない Skype for Business または Microsoft チーム アプリです。</span><span class="sxs-lookup"><span data-stu-id="8cdf7-p102">The conferencing bridge answers a call and prompts the caller with voice prompts using a meeting auto attendant, and then, depending on your settings, it can play notifications, ask callers to record their name, and control the PIN settings. PINs are given to meeting organizers to allow them to start a meeting when they are aren't using a Skype for Business or Microsoft Teams app.</span></span>

    > [!IMPORTANT]
    > A PIN is only required for the meeting organizer when a Skype for Business or Microsoft Teams app user hasn't already started the meeting. If everyone is dialing in to the meeting, the PIN is required for the meeting organizer to start the meeting. 
  
## <a name="change-the-settings-for-an-audio-conferencing-bridge"></a><span data-ttu-id="8cdf7-110">電話会議ブリッジの設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="8cdf7-110">Change the settings for an audio conferencing bridge</span></span>

 <span data-ttu-id="8cdf7-111">**発信者が会議に参加するときに、会議のエクスペリエンスを設定します。**</span><span class="sxs-lookup"><span data-stu-id="8cdf7-111">**Set up the meeting experience when callers join a meeting**</span></span>
  
1. <span data-ttu-id="8cdf7-112">職場または学校のアカウントで Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="8cdf7-112">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="8cdf7-113">**Office 365 管理センター**に移動 > **Skype for Business**します。</span><span class="sxs-lookup"><span data-stu-id="8cdf7-113">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="8cdf7-114">**Skype for Business 管理センター**で、左のナビゲーションで移動**電話会議**に > **Microsoft ブリッジの設定**します。</span><span class="sxs-lookup"><span data-stu-id="8cdf7-114">In the **Skype for Business admin center**, in the left navigation go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="8cdf7-115">[ **Microsoft bridge の設定**] ページで、[**会議参加エクスペリエンス**を選択します。</span><span class="sxs-lookup"><span data-stu-id="8cdf7-115">On the **Microsoft bridge settings** page, under **Meeting join experience**, select:</span></span>
    
  - <span data-ttu-id="8cdf7-p103">**会議のエントリを有効にして終了通知を有効にするには**これが既定で選択されます。チェック ボックスをオフにする場合は、入力したり、会議のまま、会議に参加しているユーザーが通知されません。</span><span class="sxs-lookup"><span data-stu-id="8cdf7-p103">**Enable meeting entry and exit notifications to be turned on** This is selected by default. If you clear the check box, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
    <span data-ttu-id="8cdf7-118">**会議のエントリを有効にして終了通知を有効にする**] を選択するときに、**開始/終了のお知らせの種類**] の一覧からこれらのオプションを選択できます。</span><span class="sxs-lookup"><span data-stu-id="8cdf7-118">When you select **Enable meeting entry and exit notifications to be turned on**, you can select these options from the **Entry/exit announcement type** list:</span></span>
    
  - <span data-ttu-id="8cdf7-119">**名前や電話番号**ユーザーが会議にダイヤルインするときに参加するときに、電話番号が再生されます。</span><span class="sxs-lookup"><span data-stu-id="8cdf7-119">**Names or phone numbers** When users dial in to a meeting, their phone number will be played when they join it.</span></span>
    
  - <span data-ttu-id="8cdf7-120">**トーン**ユーザーが会議にダイヤルインするときに参加するときにオーディオのトーンが再生されます。</span><span class="sxs-lookup"><span data-stu-id="8cdf7-120">**Tones** When users dial in to a meeting, an audio tone will be played when they join it.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="8cdf7-121">プレビュー機能とすべての顧客に現時点でのお知らせの種類に**音**を使用してはします。</span><span class="sxs-lookup"><span data-stu-id="8cdf7-121">Using **Tone** as the announcement type is currently available to all customers as a preview feature.</span></span>
  
  - <span data-ttu-id="8cdf7-p104">**質問の発信者**これが既定で選択されます。チェック ボックスをオフにする場合、発信者が、会議に参加する前に、相手の名前を記録するように依頼されません。</span><span class="sxs-lookup"><span data-stu-id="8cdf7-p104">**Ask callers to record their name before joining the meeting** This is selected by default. If you clear the check box, callers won't be asked to record their name before they join a meeting.</span></span>
    
5. <span data-ttu-id="8cdf7-124">変更が終了したら、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8cdf7-124">After you make your changes, click **Save**.</span></span>
    
<span data-ttu-id="8cdf7-125">**会議の PIN の長さを設定します。**</span><span class="sxs-lookup"><span data-stu-id="8cdf7-125">**Set the PIN length for meetings**</span></span>
  
1. <span data-ttu-id="8cdf7-126">職場または学校のアカウントで Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="8cdf7-126">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="8cdf7-127">**Office 365 管理センター**に移動 > **Skype for Business**します。</span><span class="sxs-lookup"><span data-stu-id="8cdf7-127">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="8cdf7-128">**Skype for Business 管理センター**、左のナビゲーションで**電話会議**に移動 > **Microsoft ブリッジの設定**します。</span><span class="sxs-lookup"><span data-stu-id="8cdf7-128">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="8cdf7-129">**Microsoft ブリッジの設定**] ページで、[**セキュリティ**]、[ **PIN の長さ**] ボックスの一覧で、[PIN の桁数を入力し、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8cdf7-129">On the **Microsoft bridge settings** page, under **Security**, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="8cdf7-130">4、12 桁の数字の間、暗証番号 (pin) があります。</span><span class="sxs-lookup"><span data-stu-id="8cdf7-130">The PIN must be between 4 and 12 digits.</span></span> 
  
<span data-ttu-id="8cdf7-131">**ユーザーにメールを送信するかどうかを選択します。**</span><span class="sxs-lookup"><span data-stu-id="8cdf7-131">**Select whether to send email to your users**</span></span>
  
1. <span data-ttu-id="8cdf7-132">職場または学校のアカウントで Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="8cdf7-132">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="8cdf7-133">**Office 365 管理センター**に移動 > **Skype for Business**します。</span><span class="sxs-lookup"><span data-stu-id="8cdf7-133">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="8cdf7-134">**Skype for Business 管理センター**、左のナビゲーションで**電話会議**に移動 > **Microsoft ブリッジの設定**します。</span><span class="sxs-lookup"><span data-stu-id="8cdf7-134">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="8cdf7-135">[ **Microsoft bridge の設定**] ページで、選択や**、電話会議の設定を変更した場合、ユーザーにメールを自動的に送信**] をオフにし、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8cdf7-135">On the **Microsoft bridge settings** page, select or clear **Automatically send emails to users if their audio conferencing configuration changes**, and then click **Save**.</span></span>
    
    <span data-ttu-id="8cdf7-136">詳細については[、電話会議の設定を変更する場合にユーザーにメールが自動的に送信](emails-sent-to-users-when-their-settings-change.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8cdf7-136">See [Emails automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md) for more information.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="8cdf7-137">Windows PowerShell で管理する方法を知りたいとしていますか。</span><span class="sxs-lookup"><span data-stu-id="8cdf7-137">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="8cdf7-138">時刻を保存するか、このプロセスを自動化に、[セット CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 )コマンドレットを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="8cdf7-138">To save time or automate this process, you can use the [Set-CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 ) cmdlet.</span></span>
    
- <span data-ttu-id="8cdf7-p105">Windows PowerShell がユーザーを管理するユーザーを許可または使用できません。Windows PowerShell で複数のタスクを実行するがある場合、日常業務を簡素化する管理の 1 つのポイントを使用して Office 365 を管理できます。Windows PowerShell で開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8cdf7-p105">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="8cdf7-142">Office 365 PowerShell を使用する必要がある理由</span><span class="sxs-lookup"><span data-stu-id="8cdf7-142">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="8cdf7-143">Windows PowerShell で Office 365 を管理する最善の方法</span><span class="sxs-lookup"><span data-stu-id="8cdf7-143">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="8cdf7-p106">Windows PowerShell では多くの利点速度、わかりやすいように、および生産性でのみ実行しようとする設定の変更、多くのユーザーに一度になど、Office 365 管理センターを使用します。次のトピックでこれらの利点について学習します。</span><span class="sxs-lookup"><span data-stu-id="8cdf7-p106">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="8cdf7-146">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="8cdf7-146">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="8cdf7-147">Windows PowerShell を使用して、Skype for Business Online の管理するには</span><span class="sxs-lookup"><span data-stu-id="8cdf7-147">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="8cdf7-148">Windows PowerShell を使用して、共通の Skype for Business Online の管理タスクを実行するには</span><span class="sxs-lookup"><span data-stu-id="8cdf7-148">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="8cdf7-p107">Skype for Business Online 用の Windows PowerShell モジュールを使用すると、Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成することができます。このモジュールでは、64 ビット コンピューター以外では、Microsoft ダウンロード センターからダウンロードできます[Skype for Business Online 用の Windows PowerShell モジュール](https://go.microsoft.com/fwlink/?LinkId=294688)。</span><span class="sxs-lookup"><span data-stu-id="8cdf7-p107">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="8cdf7-151">関連トピック</span><span class="sxs-lookup"><span data-stu-id="8cdf7-151">Related topics</span></span>

[<span data-ttu-id="8cdf7-152">Skype for Business とチームの Microsoft の音声会議をセットアップする設定します。</span><span class="sxs-lookup"><span data-stu-id="8cdf7-152">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](set-up-audio-conferencing.md)

