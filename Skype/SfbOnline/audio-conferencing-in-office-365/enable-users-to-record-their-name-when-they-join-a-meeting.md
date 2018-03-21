---
title: "ユーザーが会議に参加したときに自分の名前を記録できるようにする"
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
ms.openlocfilehash: cee842570c6cfaca6402803a66df9bbc6f0c08d6
ms.sourcegitcommit: 997c03395fd1966607cef0df8ee884303401cd64
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2018
---
# <a name="enable-users-to-record-their-name-when-they-join-a-meeting"></a><span data-ttu-id="32bb1-103">ユーザーが会議に参加したときに自分の名前を記録できるようにする</span><span class="sxs-lookup"><span data-stu-id="32bb1-103">Enable users to record their name when they join a meeting</span></span>

<span data-ttu-id="32bb1-p101">[] Skype for Business Online でダイヤルイン会議をセットアップしているときには、電話番号とダイヤルインまたは電話会議ブリッジと呼ばれるものを受け取ります。会議ブリッジには、1 つ以上の電話番号 (専用または共有の電話番号の場合もある) が含まれることがあります。</span><span class="sxs-lookup"><span data-stu-id="32bb1-p101">When you are setting up Audio Conferencing in Office 365, you will receive phone numbers and what is called an audio conferencing bridge. A conferencing bridge can contain one or more phone numbers that can be a dedicated or shared phone number.</span></span>
  
<span data-ttu-id="32bb1-p102">ユーザーが電話を使って会議にダイヤルインすると、その通話は会議ブリッジによって応答されます。会議ブリッジでは、自動応答の音声プロンプトで発信者に応答してから、設定に応じて、お知らせを再生したり、発信者に名前を記録するように依頼したり、会議開催者の PIN セキュリティをセットアップしたりします。PIN が会議開催者に与えられて、開催者は会議を開始できるようになります。ただし、PIN がなくても会議を開始できるように設定できます。</span><span class="sxs-lookup"><span data-stu-id="32bb1-p102">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone. The conferencing bridge answers the caller with voice prompts from an auto attendant, and then, depending on their settings, can play notifications, ask callers to record their name, and set up the PIN security for meeting organizers. PINs are given to meeting organizers to allow them to start a meeting. However, you can set it up so a PIN isn't required to start a meeting.</span></span>
  
## <a name="set-whether-callers-should-record-their-name"></a><span data-ttu-id="32bb1-110">発信者が名前を記録すべきかどうかを設定する</span><span class="sxs-lookup"><span data-stu-id="32bb1-110">Set whether callers should record their name</span></span>

1. <span data-ttu-id="32bb1-111">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="32bb1-111">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="32bb1-112">Sign in to Office 365 with your work or school account.</span><span class="sxs-lookup"><span data-stu-id="32bb1-112">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="32bb1-113">既定値は 5 です。</span><span class="sxs-lookup"><span data-stu-id="32bb1-113">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="32bb1-114">[ **会議参加エクスペリエンス**] の [ **会議の入退出の通知をオンにする**] で、次のいずれかを選びます。</span><span class="sxs-lookup"><span data-stu-id="32bb1-114">Under **Meeting join experience**, see the check box labeled **Enable meeting entry and exit notifications to be turned on**.</span></span>
    
  - <span data-ttu-id="32bb1-p103">**オン**: 発信者は、会議に参加する前に名前を記録するように依頼されます。 既定ではオンになっています。</span><span class="sxs-lookup"><span data-stu-id="32bb1-p103">**Selected** Callers will be asked to record their name before they enter the meeting. This is selected by default.</span></span>
    
  - <span data-ttu-id="32bb1-117">**オフ**: 発信者は、会議に参加する前に名前を記録するように依頼されません。</span><span class="sxs-lookup"><span data-stu-id="32bb1-117">**Cleared** Callers won't be asked to record their name before they enter the meeting.</span></span>
    
5. <span data-ttu-id="32bb1-118">変更したら [ **保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="32bb1-118">After you make your changes, click **Save**.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="32bb1-119">Windows PowerShell で管理する方法</span><span class="sxs-lookup"><span data-stu-id="32bb1-119">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="32bb1-120">時間を節約したり、自動化したりするには、[Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757) コマンドレットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="32bb1-120">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingTenantSettings ](https://go.microsoft.com/fwlink/?LinkId=715757) cmdlet.</span></span>
    
-  <span data-ttu-id="32bb1-p104">Windows PowerShell の場合、Skype for Business Online はユーザーの管理と、ユーザーが許可されている操作や許可されていない操作の管理に使います。Windows PowerShell により、単一の管理ポイントを使って Office 365 を管理でき、複数の作業を実行する必要があるときに日常業務を合理化できます。Windows PowerShell を使い始めるには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="32bb1-p104">Windows PowerShell is all about managing users and what users are allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="32bb1-124">Windows PowerShell で Office 365 を管理する 6 つの理由</span><span class="sxs-lookup"><span data-stu-id="32bb1-124">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="32bb1-125">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="32bb1-125">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="32bb1-p105">多くのユーザーの設定を同時に変更するときなどは、Office 365 管理センターのみを使用するよりも、Windows PowerShell の方に、速度、わかりやすさ、生産性の点で多くのメリットがあります。 次のトピックで、これらの利点を説明します。</span><span class="sxs-lookup"><span data-stu-id="32bb1-p105">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="32bb1-128">Windows PowerShell と Lync Online の概要</span><span class="sxs-lookup"><span data-stu-id="32bb1-128">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="32bb1-129">Windows PowerShell による Lync Online の管理</span><span class="sxs-lookup"><span data-stu-id="32bb1-129">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="32bb1-130">クイック リファレンス: Windows PowerShell を使用した一般的な Lync Online の管理タスクの実行</span><span class="sxs-lookup"><span data-stu-id="32bb1-130">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="32bb1-p106">Skype for Business Online 用 Windows PowerShell モジュールでは、リモート Windows PowerShell セッションを作成して Skype for Business Online に接続できます。 このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「[Skype for Business Online 用 Windows PowerShell モジュール](https://go.microsoft.com/fwlink/?LinkId=294688)」からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="32bb1-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="32bb1-133">See also</span><span class="sxs-lookup"><span data-stu-id="32bb1-133">Related topics</span></span>

[<span data-ttu-id="32bb1-134">Office 365 でのダイヤルイン会議</span><span class="sxs-lookup"><span data-stu-id="32bb1-134">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](set-up-audio-conferencing.md)
