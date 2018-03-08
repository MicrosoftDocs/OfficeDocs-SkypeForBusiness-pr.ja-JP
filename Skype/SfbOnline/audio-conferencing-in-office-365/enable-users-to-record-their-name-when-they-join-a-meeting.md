---
title: "会議に参加するときに、相手の名前を記録するようにユーザーを有効にします。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 1d649328-ada7-422d-a074-d6da4da36970
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
description: "有効にする、またはユーザーが会議に参加するときの名前を記録できるかどうかを無効にする方法をについてください。 "
ms.openlocfilehash: 6fa5fe6968976bfc25b2ff8e1a2115ca2619f10a
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="enable-users-to-record-their-name-when-they-join-a-meeting"></a><span data-ttu-id="88f66-103">会議に参加するときに、相手の名前を記録するようにユーザーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="88f66-103">Enable users to record their name when they join a meeting</span></span>

<span data-ttu-id="88f66-p101">Office 365 での電話会議をセットアップすると電話番号と、電話会議ブリッジと呼ばれるものが提供されます。会議ブリッジには、専用または共有の電話番号をことができる 1 つ以上の電話番号を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="88f66-p101">When you are setting up Audio Conferencing in Office 365, you will receive phone numbers and what is called an audio conferencing bridge. A conferencing bridge can contain one or more phone numbers that can be a dedicated or shared phone number.</span></span>
  
<span data-ttu-id="88f66-p102">会議ブリッジが電話を使って会議にダイヤルインしたユーザーが呼び出しに応答します。会議ブリッジ、自動応答からを促すボイス メッセージと発信者に応答し、その設定に応じて再生できる、通知質問する相手の名前を記録し、会議の開催者 PIN のセキュリティ設定の発信者に応答します。Pin は、会議を開始するようにするため、会議の開催者に与えられます。ただし、することができます設定 PIN は、会議を開始する要求されないようにします。</span><span class="sxs-lookup"><span data-stu-id="88f66-p102">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone. The conferencing bridge answers the caller with voice prompts from an auto attendant, and then, depending on their settings, can play notifications, ask callers to record their name, and set up the PIN security for meeting organizers. PINs are given to meeting organizers to allow them to start a meeting. However, you can set it up so a PIN isn't required to start a meeting.</span></span>
  
## <a name="set-whether-callers-should-record-their-name"></a><span data-ttu-id="88f66-110">発信者の名前を記録すべきかどうかを設定します。</span><span class="sxs-lookup"><span data-stu-id="88f66-110">Set whether callers should record their name</span></span>

1. <span data-ttu-id="88f66-111">職場または学校のアカウントで Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="88f66-111">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="88f66-112">**Office 365 管理センター**に移動 > **Skype for Business**します。</span><span class="sxs-lookup"><span data-stu-id="88f66-112">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="88f66-113">**Skype for Business 管理センター**、左のナビゲーションで**電話会議**に移動 > **Microsoft ブリッジの設定**します。</span><span class="sxs-lookup"><span data-stu-id="88f66-113">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="88f66-114">[**会議参加エクスペリエンス**を**会議のエントリを有効にして終了通知を有効にする**] チェック ボックスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="88f66-114">Under **Meeting join experience**, see the check box labeled **Enable meeting entry and exit notifications to be turned on**.</span></span>
    
  - <span data-ttu-id="88f66-p103">**選択されています。**発信者は、会議に参加する前に、相手の名前を記録するように求められます。これが既定で選択されます。</span><span class="sxs-lookup"><span data-stu-id="88f66-p103">**Selected** Callers will be asked to record their name before they enter the meeting. This is selected by default.</span></span>
    
  - <span data-ttu-id="88f66-117">**オフになっています。**発信者は、会議に参加する前に、相手の名前を記録するように依頼されません。</span><span class="sxs-lookup"><span data-stu-id="88f66-117">**Cleared** Callers won't be asked to record their name before they enter the meeting.</span></span>
    
5. <span data-ttu-id="88f66-118">変更が終了したら、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="88f66-118">After you make your changes, click **Save**.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="88f66-119">Windows PowerShell で管理する方法を知りたいとしていますか。</span><span class="sxs-lookup"><span data-stu-id="88f66-119">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="88f66-120">時間を節約し、自動化したりには、[セット CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757)コマンドレットを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="88f66-120">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingTenantSettings ](https://go.microsoft.com/fwlink/?LinkId=715757) cmdlet.</span></span>
    
-  <span data-ttu-id="88f66-p104">Windows PowerShell がユーザーとは、ユーザーの許可を管理できます。Windows PowerShell で複数のタスクを実行するがある場合、日常業務を簡素化する管理の 1 つのポイントを使用して Office 365 を管理できます。Windows PowerShell で開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="88f66-p104">Windows PowerShell is all about managing users and what users are allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="88f66-124">Office 365 PowerShell を使用する必要がある理由</span><span class="sxs-lookup"><span data-stu-id="88f66-124">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="88f66-125">Windows PowerShell で Office 365 を管理する最善の方法</span><span class="sxs-lookup"><span data-stu-id="88f66-125">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="88f66-p105">Windows PowerShell では多くの利点速度、わかりやすいように、および生産性でのみ実行しようとする設定の変更、多くのユーザーに一度になど、Office 365 管理センターを使用します。次のトピックでこれらの利点について学習します。</span><span class="sxs-lookup"><span data-stu-id="88f66-p105">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="88f66-128">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="88f66-128">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="88f66-129">Windows PowerShell を使用して、Skype for Business Online の管理するには</span><span class="sxs-lookup"><span data-stu-id="88f66-129">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="88f66-130">Windows PowerShell を使用して、共通の Skype for Business Online の管理タスクを実行するには</span><span class="sxs-lookup"><span data-stu-id="88f66-130">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="88f66-p106">Skype for Business Online 用の Windows PowerShell モジュールを使用すると、Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成することができます。このモジュールでは、64 ビット コンピューター以外では、Microsoft ダウンロード センターからダウンロードできます[Skype for Business Online 用の Windows PowerShell モジュール](https://go.microsoft.com/fwlink/?LinkId=294688)。</span><span class="sxs-lookup"><span data-stu-id="88f66-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="88f66-133">関連トピック</span><span class="sxs-lookup"><span data-stu-id="88f66-133">Related topics</span></span>

[<span data-ttu-id="88f66-134">Skype for Business とチームの Microsoft の音声会議をセットアップする設定します。</span><span class="sxs-lookup"><span data-stu-id="88f66-134">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](set-up-audio-conferencing.md)

