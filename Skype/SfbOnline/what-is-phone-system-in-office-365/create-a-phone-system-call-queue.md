---
title: "電話システムで通話キューを作成します。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: makolomi
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
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
- Phone System
- Strat_SB_PSTN
description: "電話システムで Office 365 (クラウド PBX) 通話キューを提供する組織あいさつ文]、[保留中の音楽配布リストとセキュリティ グループのエージェントの電話の通話をリダイレクトを設定する方法について説明します。キューの最大サイズ、タイムアウト、および通話処理オプションを設定することもできます。 "
ms.openlocfilehash: 363c6d7eefd63d1f89eb5d1420e516894d432b6b
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="create-a-phone-system-call-queue"></a><span data-ttu-id="ede46-104">電話システムで通話キューを作成します。</span><span class="sxs-lookup"><span data-stu-id="ede46-104">Create a Phone System call queue</span></span>

<span data-ttu-id="ede46-p102">電話システム キューには、組織、機能を自動的に、通話を保留する、および他のユーザーの中に通話の処理は、次の使用可能な通話エージェントの検索機能の電話番号着信あるときに使用されるあいさつ文が含まれています。通話は、[保留中に音楽を待機しています。組織の 1 つまたは複数の通話キューを作成できます。</span><span class="sxs-lookup"><span data-stu-id="ede46-p102">Phone System call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold. You can create single or multiple call queues for your organization.</span></span>
  
<span data-ttu-id="ede46-107">電話システム通話キューを提供できます。</span><span class="sxs-lookup"><span data-stu-id="ede46-107">Phone System call queues can provide:</span></span>
  
- <span data-ttu-id="ede46-108">組織のあいさつ文の場合。</span><span class="sxs-lookup"><span data-stu-id="ede46-108">An organizational greeting.</span></span>
    
- <span data-ttu-id="ede46-109">ユーザーが待機しているときに音楽を保持します。</span><span class="sxs-lookup"><span data-stu-id="ede46-109">Music while people are waiting on hold.</span></span>
    
- <span data-ttu-id="ede46-110">メールが有効な配布リストとセキュリティ グループの担当者に着信のリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="ede46-110">Redirecting of calls to call agents in mail-enabled distribution lists and security groups.</span></span>
    
- <span data-ttu-id="ede46-111">通話キューの最大サイズ、タイムアウト、および通話処理オプションの設定を行っています。</span><span class="sxs-lookup"><span data-stu-id="ede46-111">Making settings for call queue maximum size, timeout, and call handling options.</span></span>
    
<span data-ttu-id="ede46-p103">他のユーザーを呼び出すと設定されている電話番号を通話キュー、それらが聞くあいさつ文を (いずれかを設定している) 場合は、最初にし、キューを保存して、次の使用可能な通話エージェントを待ちます。呼び出し先の人が呼び出し*最初に、最初に*(FIFO) のように通話エージェントに提供するは待機している場合、保留中に音楽を聞きます。</span><span class="sxs-lookup"><span data-stu-id="ede46-p103">When someone calls in to a phone number that is set up up with a call queue, they will hear a greeting first (if any is set up), and then they will be put in the queue and wait for the next available call agent. The person calling in will hear music while they are on hold waiting, and the calls will be offered to the call agents in the  *First In, First Out*  (FIFO) manner.</span></span>
  
<span data-ttu-id="ede46-114">キュー内で待機しているすべての通話は応答ルーティング モードまたはシリアル ルーティング モードを使用して配布します。</span><span class="sxs-lookup"><span data-stu-id="ede46-114">All calls waiting in the queue will be distributed using an attendant routing mode or serial routing mode:</span></span>
  
- <span data-ttu-id="ede46-115">応答ルーティングでは、キュー内の最初の呼び出しは、同時にすべてのエージェントを呼び出しします。</span><span class="sxs-lookup"><span data-stu-id="ede46-115">With attendant routing, the first call in the queue will ring all agents at the same time.</span></span>
    
- <span data-ttu-id="ede46-116">シリアル ルーティングでは、キュー内の最初の呼び出しは 1 つずつのすべての通話エージェントをリングします。</span><span class="sxs-lookup"><span data-stu-id="ede46-116">With serial routing, the first call in the queue will ring all call agents one by one.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ede46-117">**オフライン**では、**応答不可]**に自分のプレゼンスを設定してあるまたは通話キューから選んだ通話担当者と呼ばれるされません。</span><span class="sxs-lookup"><span data-stu-id="ede46-117">Call agents who are **Offline**, have set their presence to **Do not Disturb,** or have opted out of the call queue won't be called.</span></span>
  
- <span data-ttu-id="ede46-118">1 つだけ着信通知 (キューの先頭にある電話) への同時呼び出しエージェントに送信されます。</span><span class="sxs-lookup"><span data-stu-id="ede46-118">Only one incoming call notification (for the call at the head of the queue) at a time will be sent to the call agents.</span></span>
    
- <span data-ttu-id="ede46-119">通話のエージェントでは、通話を承諾、着信通話エージェント キュー内の次の着信通話が開始されます。</span><span class="sxs-lookup"><span data-stu-id="ede46-119">After a call agent accepts the call, the next incoming call in the queue will start ringing call agents.</span></span>
    
## <a name="step-1---getting-started"></a><span data-ttu-id="ede46-120">手順 1 - 作業の開始</span><span class="sxs-lookup"><span data-stu-id="ede46-120">Step 1 - Getting started</span></span>

<span data-ttu-id="ede46-121">通話キューの使用を開始するには、点に注意する必要は。</span><span class="sxs-lookup"><span data-stu-id="ede46-121">To get started using call queues, it's important to remember a few things:</span></span>
  
- <span data-ttu-id="ede46-p104">組織は、Enterprise E3 および**電話システム**のライセンスまたは Enterprise E5 ライセンス (最低) が必要です。割り当てられている**電話システムで**ユーザーのライセンスの数では、通話キューのために利用できるサービス番号の数に反映されます。ことが通話キューの数は、組織内で割り当てられている**電話システム**と**電話会議**のライセンスの数とは異なります。詳細については、ライセンス、[[次のとおり](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)です。</span><span class="sxs-lookup"><span data-stu-id="ede46-p104">Your organization must have (at a minimum) an Enterprise E3 plus **Phone System** license or an Enterprise E5 license. The number of **Phone System** user licenses that are assigned affects the number of service numbers that are available to be used for call queues. The number of call queues you can have is dependent on the number of **Phone System** and **Audio Conferencing** licenses that are assigned in your organization. To learn more about licensing, go [here](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ede46-p105">オンラインである、組織内のユーザーに通話をリダイレクトするには、エンタープライズ ボイスを有効にするや、Office 365 のプランを呼び出すことがある、**電話システムで**のライセンスが必要があります。[ビジネスや Microsoft チームのライセンスを割り当てる Skype](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)を参照してください。エンタープライズ ボイスを有効に Windows PowerShell を使用することができます。例を実行します。`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="ede46-p105">To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans. See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). To enable them for Enterprise Voice, you can use Windows PowerShell. For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>
  
- <span data-ttu-id="ede46-130">Office 365 のプランを呼び出すの詳細については、次を参照してください。[とは、Office 365 のプランの呼び出しですか?](../what-are-calling-plans-in-office-365/what-are-calling-plans-in-office-365.md) [for Office 365 プランの呼び出し](../skype-for-business-and-microsoft-teams-add-on-licensing/calling-plans-for-office-365.md)とします。</span><span class="sxs-lookup"><span data-stu-id="ede46-130">To learn more about Office 365 Calling Plans, see [What are Calling Plans in Office 365?](../what-are-calling-plans-in-office-365/what-are-calling-plans-in-office-365.md) and [Calling Plans for Office 365](../skype-for-business-and-microsoft-teams-add-on-licensing/calling-plans-for-office-365.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ede46-131">ユーザーが内部設置型にホストされている Lync Server 2010 を使用して通話のキュー エージェントとしてはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="ede46-131">Users hosted on-premises using Lync Server 2010 aren't supported as a Call Queue Agents.</span></span> 
  
- <span data-ttu-id="ede46-p106">のみ、有料電話番号と**Skype for Business 管理センター**で使用しているか、別のサービス プロバイダーから電話システムで通話キューに転送するサービスのフリー ダイヤル電話番号を割り当てることができます。サービスのフリー ダイヤル番号を使用して、アクセスするには、クレジットの通信を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ede46-p106">You can only assign toll and toll-free service phone numbers that you got in the **Skype for Business admin center** or transferred from another service provider to Phone System call queues. To get and use toll-free service numbers, you need to set up Communications Credits.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ede46-134">キューの通話のみ有料サービスを提供するユーザー (サブスクライバー) の電話番号を割り当てることができませんまたはフリー ダイヤル電話番号を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="ede46-134">User (subscriber) phone numbers can't be assigned to call queues - only service toll or toll-free phone numbers can be used.</span></span> 
  
- <span data-ttu-id="ede46-135">電話システムで通話キューから着信を配布する場合は、これらのクライアントが通話エージェントでサポートされます。</span><span class="sxs-lookup"><span data-stu-id="ede46-135">When you are distributing the incoming calls from an Phone System call queue, these clients are supported for call agents:</span></span>
    
  - <span data-ttu-id="ede46-136">Skype for Business デスクトップ クライアント 2016 (32 と 64 ビット バージョン)</span><span class="sxs-lookup"><span data-stu-id="ede46-136">Skype for Business desktop client 2016 (32 and 64-bit versions)</span></span>
    
  - <span data-ttu-id="ede46-137">Lync デスクトップ クライアント 2013 (32 と 64 ビット バージョン)</span><span class="sxs-lookup"><span data-stu-id="ede46-137">Lync desktop client 2013 (32 and 64-bit versions)</span></span>
    
  - <span data-ttu-id="ede46-p107">すべての IP 電話モデルが Skype for Business Online に対応します。[Skype for Business Online の取得電話](getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ede46-p107">All IP phone models supported for Skype for Business Online. See [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online.md).</span></span>
    
  - <span data-ttu-id="ede46-140">Mac の Skype for Business クライアント (バージョン 16.8.196 以降)</span><span class="sxs-lookup"><span data-stu-id="ede46-140">Mac Skype for Business Client (version 16.8.196 and later)</span></span> 
    
  - <span data-ttu-id="ede46-141">Android の Skype for Business クライアント (バージョン 6.16.0.9 以降)</span><span class="sxs-lookup"><span data-stu-id="ede46-141">Android Skype for Business Client (version 6.16.0.9 and later)</span></span>
    
  - <span data-ttu-id="ede46-142">iPhone の Skype for Business クライアント (バージョン 6.16.0 以降)</span><span class="sxs-lookup"><span data-stu-id="ede46-142">iPhone Skype for Business Client (version 6.16.0 and later)</span></span>
    
  - <span data-ttu-id="ede46-143">iPad Skype for Business クライアント (バージョン 6.16.0 以降)</span><span class="sxs-lookup"><span data-stu-id="ede46-143">iPad Skype for Business Client (version 6.16.0 and later)</span></span>
    
## <a name="step-2---getting-or-transferring-toll-or-toll-free-service-phone-numbers"></a><span data-ttu-id="ede46-144">手順 2 - 取得または有料またはフリー ダイヤルのサービスの電話番号に転送します。</span><span class="sxs-lookup"><span data-stu-id="ede46-144">Step 2 - Getting or transferring toll or toll-free service phone numbers</span></span>

<span data-ttu-id="ede46-p108">作成して、通話キューを設定する、前にしたり、既存の有料またはフリー ダイヤルのサービスに転送する必要があります。 数値。**Skype for Business 管理センター**で表示されますが、有料またはフリー ダイヤルのサービスの電話番号が表示されたら後、 > **音声** > **電話番号**、およびとして登録されている**サービス - 無料**数値型**の一覧に表示されます。**.サービス番号を移動するには、 [Skype for Business とチームの Microsoft の取得サービスの電話番号](getting-service-phone-numbers.md)が表示されるまたは転送を既存のサービス番号の場合は、 [Office 365 への電話番号に転送](../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ede46-p108">Before you can create and set up your call queues, you will need to get or transfer your existing toll or toll-free service numbers. After you get the toll or toll-free service phone numbers, they will show up in **Skype for Business admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**. To get your service numbers, see [Getting service phone numbers for Skype for Business and Microsoft Teams](getting-service-phone-numbers.md) or if you want to transfer and existing service number, see [Transfer phone numbers to Office 365](../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="ede46-p109">米国外の場合は、Skype for Business 管理センターを使ってサービス番号を取得することはできません。米国の外部から行う方法を表示する代わりに[、組織の管理の電話番号](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)を移動します。</span><span class="sxs-lookup"><span data-stu-id="ede46-p109">If you are outside the United States, you can't use the Skype for Business admin center to get service numbers. Go [Manage phone numbers for your organization](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) instead to see how to do it from the outside of the United States.</span></span>
  
## <a name="step-3---create-a-new-call-queue"></a><span data-ttu-id="ede46-150">手順 3 - 新しい通話キューを作成します。</span><span class="sxs-lookup"><span data-stu-id="ede46-150">Step 3 - Create a new Call Queue</span></span>

<span data-ttu-id="ede46-151">**Skype for Business 管理センター**で、[**着信のルーティング**] をクリックします > **キューの通話**をには、[**新規追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ede46-151">In the **Skype for Business admin center**, click **Call routing** > **Call queues**, then click **Add new**:</span></span>
  
### <a name="set-the-call-queue-display-name-phone-number-and-domain-if-any"></a><span data-ttu-id="ede46-152">通話キューの表示名、電話番号 (ある場合)、ドメインを設定します。</span><span class="sxs-lookup"><span data-stu-id="ede46-152">Set the call queue display name, phone number and domain (if any)</span></span>

![通話キューを設定します。](../images/37ecc300-a108-4294-8463-fce570dfce72.png)
***
<span data-ttu-id="ede46-154">![数値 1](../images/sfbcallout1.png)</span><span class="sxs-lookup"><span data-stu-id="ede46-154">![Number 1](../images/sfbcallout1.png)</span></span><br/>
<span data-ttu-id="ede46-p110">**名**通話キューのわかりやすい表示名を入力します。これは必須であり、スペースも含めて、最大 64 文字を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="ede46-p110">**Name** Enter a descriptive display name for the call queue. This is required and can contain up to 64 characters, including spaces. </span></span><br/> <span data-ttu-id="ede46-157">着信通話の通知には、この名前が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ede46-157">This name will be displayed in the notification for the incoming call.</span></span>
***
<span data-ttu-id="ede46-158">![数値 2](../images/sfbcallout2.png)</span><span class="sxs-lookup"><span data-stu-id="ede46-158">![Number 2](../images/sfbcallout2.png)</span></span><br/><span data-ttu-id="ede46-p111">**電話番号**サービスの有料通話キューのフリー ダイヤル電話番号を選択します。これはオプションです。</span><span class="sxs-lookup"><span data-stu-id="ede46-p111">**Phone number** Select a service toll or toll-free phone number for the call queue. This is optional. </span></span><br/> <span data-ttu-id="ede46-p112">いずれかを使用する必要がある場合にこの通話キューを作成する前に、サービスの番号を取得する必要がありますが表示されます。サービス番号を移動するには、 [Skype for Business とチームの Microsoft の取得サービスの電話番号](getting-service-phone-numbers.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ede46-p112">If there aren't any listed, you need to get service numbers before you can create this call queue. To get your service numbers, see [Getting service phone numbers for Skype for Business and Microsoft Teams](getting-service-phone-numbers.md)</span></span>
***
<span data-ttu-id="ede46-163">![数値 3](../images/sfbcallout3.png)</span><span class="sxs-lookup"><span data-stu-id="ede46-163">![Number 3](../images/sfbcallout3.png)</span></span><br/><span data-ttu-id="ede46-p113">**ドメイン**これを利用できる場合は、使用する Office 365 ドメインを選びます。これは、Office 365 で使用されている 1 つ以上のドメインがある場合にのみ。場合は、1 つ以上ある場合は、一覧からドメイン名を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ede46-p113">**Domain** If this is available, choose the Office 365 domain you want to use. This is only available if you have more than one domain being used with Office 365. If you have more than one, you must chose the domain name from the list. </span></span><br/> <span data-ttu-id="ede46-167">たとえばなどのドメインがある可能性があります: _contoso.com または redmond.contoso.com_</span><span class="sxs-lookup"><span data-stu-id="ede46-167">For example, you could have a domain like:  _contoso.com or redmond.contoso.com_</span></span>
   
### <a name="set-the-greeting-and-music-played-while-on-hold"></a><span data-ttu-id="ede46-168">あいさつ文と再生保留中に音楽を設定します。</span><span class="sxs-lookup"><span data-stu-id="ede46-168">Set the greeting and music played while on hold</span></span>

![通話キューを設定します。](../images/1d395a93-7cab-4178-9295-12d5379e20de.png)
  
***
<span data-ttu-id="ede46-170">![数値 1](../images/sfbcallout1.png)</span><span class="sxs-lookup"><span data-stu-id="ede46-170">![Number 1](../images/sfbcallout1.png)</span></span><br/><span data-ttu-id="ede46-p114">**[あいさつ文**は省略可能です。これは、通話キュー番号に電話の発信元のユーザーに再生されるあいさつ文です。</span><span class="sxs-lookup"><span data-stu-id="ede46-p114">**Greeting** is optional. This is the greeting that is played for people who call in to the call queue number. </span></span><br/> <span data-ttu-id="ede46-173">オーディオ ファイル (.wav、.mp3、または .wma 形式) をアップロードすることができます。</span><span class="sxs-lookup"><span data-stu-id="ede46-173">You can upload an audio file (.wav, .mp3, or .wma formats).</span></span>
***
<span data-ttu-id="ede46-174">![数値 2](../images/sfbcallout2.png)</span><span class="sxs-lookup"><span data-stu-id="ede46-174">![Number 2](../images/sfbcallout2.png)</span></span><br/><span data-ttu-id="ede46-175">**上の音楽を保持**通話キューで提供されている保留中で、既定の音楽を使用することができますか、または保留中のユーザー設定の音楽として使用する .wav、mp3、または .wma 形式でのオーディオ ファイルをアップロードすることができます。</span><span class="sxs-lookup"><span data-stu-id="ede46-175">**Music on hold** You can either use the default Music on Hold provided with the call queue, or you can upload an audio file in .wav, mp3, or .wma formats to use as your custom Music on Hold.</span></span> 
   

### <a name="select-the-call-distribution-method"></a><span data-ttu-id="ede46-176">通話の配布方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="ede46-176">Select the call distribution method</span></span>

![配布方法のオプションを表示するには、通話](../images/5d249515-d532-4af2-90da-011404028b89.png)
  
***
<span data-ttu-id="ede46-178">![数値 1](../images/sfbcallout1.png)</span><span class="sxs-lookup"><span data-stu-id="ede46-178">![Number 1](../images/sfbcallout1.png)</span></span><br/><span data-ttu-id="ede46-p115">**着信の配布方法****応答**または**シリアル**通話キュー配布方法を選択できます。すべての新規または既存の通話キュー アテンダント ルーティングが既定で選択されている必要があります。シリアルをルーティングする機能を使用するのには、明示的に UI とコマンドレットの**シリアル**ルーティング オプションを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ede46-p115">**Call distribution method** You can choose either **Attendant** or **Serial** for your call queue distribution method. All new and existing call queues will have attendant routing selected by default. To use serial routing, you must explicitly choose the **Serial** routing option in UI and cmdlets. </span></span><br/><br/> <span data-ttu-id="ede46-p116">シリアル ルーティングを選択すると、通話キューが保存されている、キューからの通話はエージェントのリストの先頭から 1 つずつエージェントをリングします。エージェント閉じ、通話は選択されない場合、通話はリストには、次のエージェントを呼び出し、エージェントの 1 つずつまで選択してまたはキュー待機して時刻をすべてしようとします。</span><span class="sxs-lookup"><span data-stu-id="ede46-p116">When serial routing is chosen and the call queue is saved, the calls from the queue will ring your agents one by one, starting from the beginning of the agent list. If an agent dismisses or does not pick up a call, the call will ring the next agent on the list and will try all agents one by one until it is picked up or times out waiting in the queue.  </span></span><br/><br/>  <span data-ttu-id="ede46-184">**メモ:**シリアル ルーティングが**オフライン****応答不可**] に自分のプレゼンスを設定している、またはのこのキューから通話を開始して**使用を停止した**担当者をスキップします。</span><span class="sxs-lookup"><span data-stu-id="ede46-184">**Note:** Serial routing will skip agents who are **Offline**, have set their presence to **Do not Disturb**, or have **opted out** of getting calls from this queue.</span></span>  
   
### <a name="select-an-agent-opt-out-option"></a><span data-ttu-id="ede46-185">オプション脱退、エージェントの選択</span><span class="sxs-lookup"><span data-stu-id="ede46-185">Select an agent opt out option</span></span>

![表示する、エージェントの利用を停止] チェック ボックス](../images/99279eff-db61-4acf-9b62-64be84b6414b.png)
  
***
<span data-ttu-id="ede46-187">![数値 1](../images/sfbcallout1.png)</span><span class="sxs-lookup"><span data-stu-id="ede46-187">![Number 1](../images/sfbcallout1.png)</span></span><br/><span data-ttu-id="ede46-188">**エージェントが脱退オプション**通話キュー エージェント**エージェントが脱退] オプション**を選択して、特定のキューからの通話の応答を停止するには、次のように許可することができます。</span><span class="sxs-lookup"><span data-stu-id="ede46-188">**Agent Opt out option** You can choose to allow call queue agents to opt out of taking calls from a particular queue by selecting **Agent Opt out option**.</span></span>  <br/> <span data-ttu-id="ede46-p117">このオプションを有効にするには、このキュー内のすべてのエージェント開始または停止するのには、この通話キューから電話を受けるにはことができます。ことで取り消せますエージェント オプトアウト特権いつでも、チェック ボックスをオフにしてエージェントになる自動的に加入してでこのキューでもう一度 (すべてのエージェントの既定の設定) する原因になっています。</span><span class="sxs-lookup"><span data-stu-id="ede46-p117">Enabling this option allows all agents in this queue to start or stop receiving call from this call queue at will. You can revoke the agent opt-out privilege at any time by clearing the check box, causing agents to become automatically opted in for this queue again (the default setting for all agents).  </span></span><br/><br/> <span data-ttu-id="ede46-191">脱退オプションを使用するには、エージェントは、次の操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="ede46-191">To access the opt-out option, agents can do the following:</span></span>
 1. <span data-ttu-id="ede46-192">デスクトップ、Skype for Business クライアントでは、**オプション**を開きます。</span><span class="sxs-lookup"><span data-stu-id="ede46-192">Open **Options** in their desktop Skype for Business client.</span></span> 
 2. <span data-ttu-id="ede46-193">[**着信の転送**] タブの**オンライン設定の編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ede46-193">On the **Call Forwarding** tab, click the **Edit settings online** link.</span></span>
 3. <span data-ttu-id="ede46-194">[ユーザー設定] ページは、**通話キュー**をクリックし、利用を停止する、キューのチェック ボックスをオフにし、します。</span><span class="sxs-lookup"><span data-stu-id="ede46-194">On the user settings page, click **Call Queues**, and then clear the check boxes for any queues for which they want to opt out.</span></span>
   
### <a name="add-call-agents-to-a-call-queue"></a><span data-ttu-id="ede46-195">通話キューに通話エージェントを追加します。</span><span class="sxs-lookup"><span data-stu-id="ede46-195">Add call agents to a call queue</span></span>

![通話キューを設定します。](../images/skype-for-business-add-agents-to-call-queue.png)
  
***
![数値 1](../images/sfbcallout1.png)<br/><br/><span data-ttu-id="ede46-198">通話エージェント (最大 50) があります。</span><span class="sxs-lookup"><span data-stu-id="ede46-198">Call agents (50 maximum) can be:</span></span>
*    <span data-ttu-id="ede46-199">**電話システムで**ライセンスを使って、オンラインのユーザーと、エンタープライズ ボイスや通話プランを有効にします。</span><span class="sxs-lookup"><span data-stu-id="ede46-199">An Online user with a **Phone System** license and enabled for Enterprise Voice or with a Calling Plan.</span></span> <br/><br/> <span data-ttu-id="ede46-p118">**メモ:** オンラインである、組織内のユーザーに通話をリダイレクトするには、エンタープライズ ボイスを有効にするや、通話プランを使って、**電話システムで**のライセンスが必要があります。[ビジネスや Microsoft チームのライセンスを割り当てる Skype](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)を参照してください。エンタープライズ ボイスを有効に Windows PowerShell を使用することができます。例を実行します。`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="ede46-p118">**Note:**  To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have a Calling Plan. See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). To enable them for Enterprise Voice, you can use Windows PowerShell. For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span> <br/><br/>
*    <span data-ttu-id="ede46-p119">オンラインのユーザーに、**電話システムで**ライセンスされた通話プランは Office 365 グループをメールが有効な配布リスト、またはセキュリティ グループに追加するとします。配布リストまたは通話キューからの通話の受信を開始するセキュリティ グループに追加された新しいエージェントの 30 分ほどかかる場合があります。新しく作成された配布リストまたはセキュリティ グループは、通話キューで使用する使用可能になるまで 48 時間以内にかかる場合があります。新しく作成された Office 365 グループを利用すぐできます。</span><span class="sxs-lookup"><span data-stu-id="ede46-p119">Online users with a with a **Phone System** license and a Calling Plan that are added to an Office 365 Group, a mail-enabled Distribution List, or a Security Group. It might take up to 30 minutes for a new agent added for a distribution list or a security group to start receiving calls from a call queue. A newly created distribution list or security group might take up to 48 hours to become available to be used with call queues. Newly created Office 365 Groups are available almost immediately. </span></span><br/> 

    > [!NOTE] 
    > <span data-ttu-id="ede46-208">ユーザーが内部設置型にホストされている Lync Server 2010 の使用はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="ede46-208">Users hosted on-premises using Lync Server 2010 aren't supported.</span></span>           
   
### <a name="set-the-maximum-queue-size-and-maximum-wait-time"></a><span data-ttu-id="ede46-209">キューの最大サイズと最大待機時間を設定します。</span><span class="sxs-lookup"><span data-stu-id="ede46-209">Set the maximum queue size and maximum wait time</span></span>

![通話キューを設定します。](../images/3f018734-16fe-458b-827d-71fc25155cde.png)
  
***
<span data-ttu-id="ede46-211">![数値 1](../images/sfbcallout1.png)</span><span class="sxs-lookup"><span data-stu-id="ede46-211">![Number 1](../images/sfbcallout1.png)</span></span><br/><br/><span data-ttu-id="ede46-p120">**最大通話キュー**同時にキュー内の待機できる、呼び出しの最大数を設定するのには、これを使用します。既定では、50 が範囲は 0 を取り出します。 この制限に達したときに、通話は、下の [**通話の最大数に達した場合**設定で設定した方法で処理されます。</span><span class="sxs-lookup"><span data-stu-id="ede46-p120">**Maximum calls in the queue** Use this to set the maximum calls that can wait in the queue at the same time. The default is 50, but it can range from 0 to 200.When this limit is reached, the call will be handled in way you have set on the **When the maximum number of calls is reached** setting below.</span></span>
***
<span data-ttu-id="ede46-214">![数値 2](../images/sfbcallout2.png)</span><span class="sxs-lookup"><span data-stu-id="ede46-214">![Number 2](../images/sfbcallout2.png)</span></span><br/><br/><span data-ttu-id="ede46-215">**通話の最大数に達した場合**通話キューには、(**最大通話キュー**設定を使用する設定) の最大サイズになると、新しい着信通話はどうなりますかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="ede46-215">**When the maximum number of calls is reached** When the call queue reaches its maximum size (set using the **Maximum calls in the queue** setting), you can choose what happens to new incoming calls.</span></span>
*    <span data-ttu-id="ede46-216">**通話を切断**通話は切断されます。</span><span class="sxs-lookup"><span data-stu-id="ede46-216">**Disconnect with a busy signal** The call will be disconnected.</span></span>
*    <span data-ttu-id="ede46-217">**この通話を転送します。**この場合は、これらのオプション必要があります。</span><span class="sxs-lookup"><span data-stu-id="ede46-217">**Forward this call to** When you choose this, you will have these options:</span></span>
     *    <span data-ttu-id="ede46-p121">**社内のユーザー****電話システムで**ライセンスを使って、オンラインのユーザーとのエンタープライズ ボイスを有効にする、または通話プランを使っています。相手呼び出しをボイス メールを送信できないようにする設定ことができます。これを行うには、**社内のユーザー**を選択し、着信が直接ボイス メールに転送するのには、この人を設定します。</span><span class="sxs-lookup"><span data-stu-id="ede46-p121">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have a Calling Plan. You can set it up so the person calling in can be sent to voicemail. To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail. </span></span><br/>
     
        > [!Note]
        > <span data-ttu-id="ede46-221">ユーザーが内部設置型にホストされている Lync Server 2010 の使用はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="ede46-221">Users hosted on-premises using Lync Server 2010 aren't supported.</span></span><br/>
     
     *    <span data-ttu-id="ede46-222">**キューを呼び出す**必要があります既に作成している別の通話キューが、その通話キューを選択できます。</span><span class="sxs-lookup"><span data-stu-id="ede46-222">**Call Queue** You must have already created another call queue, but after you do, you can select that call queue.</span></span>
     *    <span data-ttu-id="ede46-p122">**自動応答**必要がありますが既に作成して、自動応答は、後は、その自動応答を選択することができます。[電話システムでの自動応答を設定する](set-up-a-phone-system-auto-attendant.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ede46-p122">**Auto Attendant** You must have already created an auto attendant, but after you do, you can select that auto attendant. See [Set up a Phone System auto attendant](set-up-a-phone-system-auto-attendant.md).</span></span>
***
<span data-ttu-id="ede46-225">![数値 3](../images/sfbcallout3.png)</span><span class="sxs-lookup"><span data-stu-id="ede46-225">![Number 3](../images/sfbcallout3.png)</span></span><br/><br/><span data-ttu-id="ede46-p123">**通話を開始できるキューで待機する時間を確認します。**キュー内の保留中の通話時間ができることもできます前に、タイムアウトが発生して、リダイレクト、または接続が切断する必要があります。リダイレクト先は、**電話をかけるタイムアウトが発生する場合**の設定を設定する方法に基づいています。45 分を 0 から時刻を設定できます。</span><span class="sxs-lookup"><span data-stu-id="ede46-p123">**How long a call can wait in the queue** You can also decide how much time a call can be on hold in the queue before it times out and needs to be redirected or disconnected. Where it will be redirected is based on how you set the **When a call times out** setting. You can set a time from 0 to 45 minutes. </span></span><br/><br/> <span data-ttu-id="ede46-p124">15 秒間隔で秒単位でタイムアウト値を設定できます。これにより、細かくと通話の流れを操作することができます。たとえば、30 秒以内にエージェントが応答しないすべての呼び出しをディレクトリの検索の自動応答に移動することを指定した可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ede46-p124">The timeout value can be set in seconds, at 15-second intervals. This allows you to manipulate the call flow with finer granularity. For example, you could specify that any calls that are not answered by an agent within 30 seconds go to a Directory Search Auto Attendant.</span></span> 

***
<span data-ttu-id="ede46-232">![番号 4](../images/sfbcallout4.png)</span><span class="sxs-lookup"><span data-stu-id="ede46-232">![Number 4](../images/sfbcallout4.png)</span></span><br/><br/><span data-ttu-id="ede46-233">**電話をかけるタイムアウトが発生する場合**通話には、**電話をかけることができますキューで待機する時間**の設定で設定した制限に達すると、この呼び出しの動作を選択します。</span><span class="sxs-lookup"><span data-stu-id="ede46-233">**When a call times out** When the call reaches the limit you set on the **How long a call can wait in the queue** setting, you can choose what happens to this call:</span></span>
*    <span data-ttu-id="ede46-234">**切断**通話は切断されます。</span><span class="sxs-lookup"><span data-stu-id="ede46-234">**Disconnect** The call will be disconnected.</span></span>
*    <span data-ttu-id="ede46-235">**この通話を転送します。**この場合は、これらのオプション必要があります。</span><span class="sxs-lookup"><span data-stu-id="ede46-235">**Forward this call to** When you choose this, you will have these options:</span></span>
     *    <span data-ttu-id="ede46-p125">**社内のユーザー****電話システムで**ライセンスを使って、オンラインのユーザーのエンタープライズ ボイスを有効にするし、プランの呼び出しがあります。相手呼び出しをボイス メールを送信できないようにする設定ことができます。これを行うには、**社内のユーザー**を選択し、着信が直接ボイス メールに転送するのには、この人を設定します。</span><span class="sxs-lookup"><span data-stu-id="ede46-p125">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have Calling Plans. You can set it up so the person calling in can be sent to voicemail. To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span> 

        > [!Note]
        > <span data-ttu-id="ede46-239">ユーザーが内部設置型にホストされている Lync Server 2010 の使用はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="ede46-239">Users hosted on-premises using Lync Server 2010 aren't supported.</span></span><br/>

     *    <span data-ttu-id="ede46-240">**キューを呼び出す**必要があります既に作成している別の通話キューが、その通話キューを選択できます。</span><span class="sxs-lookup"><span data-stu-id="ede46-240">**Call Queue** You must have already created another call queue, but after you do, you can select that call queue.</span></span>
     *    <span data-ttu-id="ede46-p126">**自動応答**必要がありますが既に作成して、自動応答は、後は、その自動応答を選択することができます。[電話システムでの自動応答を設定する](set-up-a-phone-system-auto-attendant.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ede46-p126">**Auto Attendant** You must have already created an auto attendant, but after you do, you can select that auto attendant. See [Set up a Phone System auto attendant](set-up-a-phone-system-auto-attendant.md).</span></span>
   
## <a name="changing-the-users-caller-id-to-be-a-call-queues-phone-number"></a><span data-ttu-id="ede46-243">ユーザーの発信者番号に通話キューの電話番号を変更します。</span><span class="sxs-lookup"><span data-stu-id="ede46-243">Changing the user's Caller ID to be a call queue's phone number</span></span>

<span data-ttu-id="ede46-244">ユーザーの代わりに**新しい CallingLineIdentity**コマンドレットを使用してポリシーを作成して、発信者番号の呼び出しキューに発信を変更することによって保護できます。</span><span class="sxs-lookup"><span data-stu-id="ede46-244">You can protect a user's identity by changing their caller ID for the outbound calls to a call queue instead by creating a policy using the **New-CallingLineIdentity** cmdlet.</span></span>
  
<span data-ttu-id="ede46-245">これを行うには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="ede46-245">To do this, run:</span></span>
  
```
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

<span data-ttu-id="ede46-p127">**許可を付与する CallingLineIdentity**コマンドレットを使用してユーザーにポリシーを適用します。これを行うには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="ede46-p127">Then apply the policy to the user using the **Grant-CallingLineIdentity** cmdlet. To do this, run:</span></span>
  
```
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

<span data-ttu-id="ede46-248">組織内の発信者 ID の設定を変更する方法の詳細についてご[次のとおり](../what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization.md)です。</span><span class="sxs-lookup"><span data-stu-id="ede46-248">You can get more information on how to make changes to caller ID settings in your organization [here](../what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
## <a name="want-to-know-more"></a><span data-ttu-id="ede46-249">詳細を知りたいですか。</span><span class="sxs-lookup"><span data-stu-id="ede46-249">Want to know more?</span></span>

<span data-ttu-id="ede46-250">Windows PowerShell を使ってを作成し、通話キューを設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="ede46-250">You can also use Windows PowerShell to create and set up call queues.</span></span>
  
### <a name="call-queue-cmdlets"></a><span data-ttu-id="ede46-251">通話キュー コマンドレット</span><span class="sxs-lookup"><span data-stu-id="ede46-251">Call queue cmdlets</span></span>

<span data-ttu-id="ede46-252">通話キューを管理する必要があるコマンドレットを紹介します。</span><span class="sxs-lookup"><span data-stu-id="ede46-252">Here are the cmdlets that you need to manage a call queue.</span></span>
  
- [<span data-ttu-id="ede46-253">新しい-CsHuntgroup</span><span class="sxs-lookup"><span data-stu-id="ede46-253">New-CsHuntgroup</span></span>](https://technet.microsoft.com/en-us/library/mt796459.aspx)
    
- [<span data-ttu-id="ede46-254">設定 CsHuntgroup</span><span class="sxs-lookup"><span data-stu-id="ede46-254">Set-CsHuntgroup</span></span>](https://technet.microsoft.com/en-us/library/mt796457.aspx)
    
- [<span data-ttu-id="ede46-255">Get CsHuntgroup</span><span class="sxs-lookup"><span data-stu-id="ede46-255">Get-CsHuntgroup</span></span>](https://technet.microsoft.com/en-us/library/mt796458.aspx)
    
- [<span data-ttu-id="ede46-256">削除 CsHuntgroup</span><span class="sxs-lookup"><span data-stu-id="ede46-256">Remove-CsHuntgroup</span></span>](https://technet.microsoft.com/en-us/library/mt796456.aspx)
    
### <a name="more-about-windows-powershell"></a><span data-ttu-id="ede46-257">Windows PowerShell の詳細</span><span class="sxs-lookup"><span data-stu-id="ede46-257">More about Windows PowerShell</span></span>

- <span data-ttu-id="ede46-p128">Windows powershell となるはすべてを管理するユーザーとユーザーの許可または使用できません。Windows PowerShell で Office 365 と Skype for Business Online の複数のタスクを実行するがある場合、日常業務を簡素化する管理の 1 つのポイントを使用して管理できます。Windows PowerShell で開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ede46-p128">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="ede46-261">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="ede46-261">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="ede46-262">Office 365 PowerShell を使用する必要がある理由</span><span class="sxs-lookup"><span data-stu-id="ede46-262">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="ede46-p129">Windows PowerShell では多くの利点速度、わかりやすいように、および生産性でのみ実行しようとする設定の変更、多くのユーザーに一度になどの Office 365 管理センターを使用します。次のトピックでこれらの利点について学習します。</span><span class="sxs-lookup"><span data-stu-id="ede46-p129">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="ede46-265">Windows PowerShell で Office 365 を管理する最善の方法</span><span class="sxs-lookup"><span data-stu-id="ede46-265">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="ede46-266">Windows PowerShell を使用して、Skype for Business Online の管理するには</span><span class="sxs-lookup"><span data-stu-id="ede46-266">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="ede46-267">Windows PowerShell を使用して、共通の Skype for Business Online の管理タスクを実行するには</span><span class="sxs-lookup"><span data-stu-id="ede46-267">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="ede46-268">関連トピック</span><span class="sxs-lookup"><span data-stu-id="ede46-268">Related topics</span></span>
[<span data-ttu-id="ede46-269">ここではされた電話システムで Office 365 での表示</span><span class="sxs-lookup"><span data-stu-id="ede46-269">Here's what you get with Phone System in Office 365</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="ede46-270">Skype for Business とチームの Microsoft サービスの電話番号を取得します。</span><span class="sxs-lookup"><span data-stu-id="ede46-270">Getting service phone numbers for Skype for Business and Microsoft Teams</span></span>](getting-service-phone-numbers.md)

[<span data-ttu-id="ede46-271">電話会議とプランの呼び出しの国と地域の空き時間情報</span><span class="sxs-lookup"><span data-stu-id="ede46-271">Country and region availability for Audio Conferencing and Calling Plans</span></span>](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
