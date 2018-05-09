---
title: 電話システム呼び出しキューを作成します。
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: makolomi
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
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
- Phone System
description: 'Learn how to set up phone system for Office 365 (Cloud PBX) call queues to give you an organizational greeting, music on hold, and redirecting calls to call agents in distribution lists and security groups. You can also set the maximum queue size, time out, and call handling options. '
ms.openlocfilehash: 81fbb40aad10687d3a75020a23b20cbeee7d5c2e
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="create-a-phone-system-call-queue"></a><span data-ttu-id="e2dda-104">電話システム呼び出しキューを作成します。</span><span class="sxs-lookup"><span data-stu-id="e2dda-104">Create a Phone System call queue</span></span>

<span data-ttu-id="e2dda-105">電話システム キューには、保留中の呼び出しを自動的に配置する機能などを検索する人の中に呼び出しを処理するために次の呼び出しを使用可能なエージェントの機能の電話番号への呼び出し際に使用するあいさつ文が含まれています。呼び出しが保留中の音楽をリッスンしています。</span><span class="sxs-lookup"><span data-stu-id="e2dda-105">Phone System call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold.</span></span> <span data-ttu-id="e2dda-106">組織の 1 つまたは複数の呼び出しキューを作成します。</span><span class="sxs-lookup"><span data-stu-id="e2dda-106">You can create single or multiple call queues for your organization.</span></span>
  
<span data-ttu-id="e2dda-107">電話システム コールのキューを提供します。</span><span class="sxs-lookup"><span data-stu-id="e2dda-107">Phone System call queues can provide:</span></span>
  
- <span data-ttu-id="e2dda-108">組織の応答メッセージ。</span><span class="sxs-lookup"><span data-stu-id="e2dda-108">An organizational greeting.</span></span>
    
- <span data-ttu-id="e2dda-109">通話の保留中に再生される保留音。</span><span class="sxs-lookup"><span data-stu-id="e2dda-109">Music while people are waiting on hold.</span></span>
    
- <span data-ttu-id="e2dda-110">メールが有効な配布リストおよびセキュリティ グループ内のエージェントを呼び出しへの呼び出しをリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="e2dda-110">Redirecting of calls to call agents in mail-enabled distribution lists and security groups.</span></span>
    
- <span data-ttu-id="e2dda-111">呼び出しキューの最大サイズ、タイムアウト、および呼び出しの処理オプションの設定を行っています。</span><span class="sxs-lookup"><span data-stu-id="e2dda-111">Making settings for call queue maximum size, timeout, and call handling options.</span></span>
    
<span data-ttu-id="e2dda-112">誰かを呼び出すと設定されている電話番号を呼び出しキューでは、それらが聞こえますあいさつ文 (いずれかの設定されている) 場合、その後に、キューを保存して、次の呼び出しを使用可能なエージェントを待機します。</span><span class="sxs-lookup"><span data-stu-id="e2dda-112">When someone calls in to a phone number that is set up up with a call queue, they will hear a greeting first (if any is set up), and then they will be put in the queue and wait for the next available call agent.</span></span> <span data-ttu-id="e2dda-113">待機中、保留中であるし、呼び出し*最初に、先入れ先出し*(FIFO) の方法で呼び出しエージェントに提供するときに、相手呼び出しは音楽を聞きます。</span><span class="sxs-lookup"><span data-stu-id="e2dda-113">The person calling in will hear music while they are on hold waiting, and the calls will be offered to the call agents in the  *First In, First Out*  (FIFO) manner.</span></span>
  
<span data-ttu-id="e2dda-114">キューで待機しているすべての呼び出しは、アテンダントのルーティング モードまたはシリアル ルーティング モードを使用して配布されます。</span><span class="sxs-lookup"><span data-stu-id="e2dda-114">All calls waiting in the queue will be distributed using an attendant routing mode or serial routing mode:</span></span>
  
- <span data-ttu-id="e2dda-115">応答のルーティングでは、キュー内の最初の呼び出しを同時にすべてのエージェントが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="e2dda-115">With attendant routing, the first call in the queue will ring all agents at the same time.</span></span>
    
- <span data-ttu-id="e2dda-116">シリアルのルーティングでは、キュー内の最初の呼び出しの呼び出しのすべてのエージェントで 1 つが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="e2dda-116">With serial routing, the first call in the queue will ring all call agents one by one.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e2dda-117">**オフライン**不可**、**自分の存在を設定して、呼び出しキューを選択して、エージェントを呼び出しハンドラーは呼び出されません。</span><span class="sxs-lookup"><span data-stu-id="e2dda-117">Call agents who are **Offline**, have set their presence to **Do not Disturb,** or have opted out of the call queue won't be called.</span></span>
  
- <span data-ttu-id="e2dda-118">一度に 1 回のみの着信通知 (キューの最初にある通話) がコール エージェントに送信されます。</span><span class="sxs-lookup"><span data-stu-id="e2dda-118">Only one incoming call notification (for the call at the head of the queue) at a time will be sent to the call agents.</span></span>
    
- <span data-ttu-id="e2dda-119">コール エージェントが通話を受けると、キューにある次の着信がコール エージェントを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="e2dda-119">After a call agent accepts the call, the next incoming call in the queue will start ringing call agents.</span></span>
    
## <a name="step-1---getting-started"></a><span data-ttu-id="e2dda-120">ステップ 1 - はじめに</span><span class="sxs-lookup"><span data-stu-id="e2dda-120">Step 1 - Getting started</span></span>

<span data-ttu-id="e2dda-121">通話キューを使用する場合は、次の重要な点について留意してください。</span><span class="sxs-lookup"><span data-stu-id="e2dda-121">To get started using call queues, it's important to remember a few things:</span></span>
  
- <span data-ttu-id="e2dda-122">組織は、エンタープライズの E3 と**電話システム**のライセンスまたはエンタープライズ E5 のライセンス (最低) が必要です。</span><span class="sxs-lookup"><span data-stu-id="e2dda-122">Your organization must have (at a minimum) an Enterprise E3 plus **Phone System** license or an Enterprise E5 license.</span></span> <span data-ttu-id="e2dda-123">キューの呼び出しに使用する利用可能なサービス番号の番号を割り当てられている**電話システム**のユーザー ライセンスの数に影響します。</span><span class="sxs-lookup"><span data-stu-id="e2dda-123">The number of **Phone System** user licenses that are assigned affects the number of service numbers that are available to be used for call queues.</span></span> <span data-ttu-id="e2dda-124">呼び出しキューを持つことができます数は、組織に割り当てられている**電話システム**および**オーディオ会議**のライセンスの数に依存しています。</span><span class="sxs-lookup"><span data-stu-id="e2dda-124">The number of call queues you can have is dependent on the number of **Phone System** and **Audio Conferencing** licenses that are assigned in your organization.</span></span> <span data-ttu-id="e2dda-125">、ライセンスに関する詳細については、移動[は、ここ](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)です。</span><span class="sxs-lookup"><span data-stu-id="e2dda-125">To learn more about licensing, go [here](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e2dda-126">オンラインにいる人が、組織内への呼び出しをリダイレクトするには、エンタープライズ VoIP を有効にするし、Office 365 のプランを呼び出すことがある、**電話システム**のライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="e2dda-126">To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="e2dda-127">「[Skype for Business と Microsoft Teams のライセンスを割り当てる](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e2dda-127">See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span> <span data-ttu-id="e2dda-128">エンタープライズ VoIP を有効にするには、Windows PowerShell を使用できます。</span><span class="sxs-lookup"><span data-stu-id="e2dda-128">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="e2dda-129">例を実行します。`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="e2dda-129">For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>
  
- <span data-ttu-id="e2dda-130">Office 365 のプランを呼び出す方法の詳細についてを参照してください[Office 365 のプランを呼び出すことは何ですか?](../what-are-calling-plans-in-office-365/what-are-calling-plans-in-office-365.md) [Office 365 のプランを呼び出す](../skype-for-business-and-microsoft-teams-add-on-licensing/calling-plans-for-office-365.md)とします。</span><span class="sxs-lookup"><span data-stu-id="e2dda-130">To learn more about Office 365 Calling Plans, see [What are Calling Plans in Office 365?](../what-are-calling-plans-in-office-365/what-are-calling-plans-in-office-365.md) and [Calling Plans for Office 365](../skype-for-business-and-microsoft-teams-add-on-licensing/calling-plans-for-office-365.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e2dda-131">ユーザーには、設置がホストされているキューを呼び出すエージェントとしては、Lync Server 2010 を使用してがサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="e2dda-131">Users hosted on-premises using Lync Server 2010 aren't supported as a Call Queue Agents.</span></span> 
  
- <span data-ttu-id="e2dda-132">有料電話番号と**Skype**でまたは別のサービス プロバイダーからの呼び出しの電話システムのキューに転送する電話番号をフリー ダイヤル サービスをのみ割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="e2dda-132">You can only assign toll and toll-free service phone numbers that you got in the **Skype for Business admin center** or transferred from another service provider to Phone System call queues.</span></span> <span data-ttu-id="e2dda-133">取得し、サービスのフリー ダイヤル番号を使用して、通信のクレジットを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2dda-133">To get and use toll-free service numbers, you need to set up Communications Credits.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e2dda-134">ユーザー (購読者) の電話番号を通話キューに割り当てることはできません。サービスの有料電話番号または無料電話番号のみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="e2dda-134">User (subscriber) phone numbers can't be assigned to call queues - only service toll or toll-free phone numbers can be used.</span></span> 
  
- <span data-ttu-id="e2dda-135">電話システム呼び出しキューからの着信呼び出しを配布するときは、コール エージェントのこれらのクライアントがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="e2dda-135">When you are distributing the incoming calls from an Phone System call queue, these clients are supported for call agents:</span></span>
    
  - <span data-ttu-id="e2dda-136">Skype for Business デスクトップ クライアント 2016 (32 および 64 ビット バージョン)</span><span class="sxs-lookup"><span data-stu-id="e2dda-136">Skype for Business desktop client 2016 (32 and 64-bit versions)</span></span>
    
  - <span data-ttu-id="e2dda-137">Lync デスクトップ クライアント 2013 (32 および 64 ビット バージョン)</span><span class="sxs-lookup"><span data-stu-id="e2dda-137">Lync desktop client 2013 (32 and 64-bit versions)</span></span>
    
  - <span data-ttu-id="e2dda-138">すべての IP 電話の機種が、Skype for Business Online でサポートされます。</span><span class="sxs-lookup"><span data-stu-id="e2dda-138">All IP phone models supported for Skype for Business Online.</span></span> <span data-ttu-id="e2dda-139">[ビジネス オンラインの Skype の電話を取得](getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2dda-139">See [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online.md).</span></span>
    
  - <span data-ttu-id="e2dda-140">ビジネス クライアントの Mac Skype (バージョン 16.8.196 以降)</span><span class="sxs-lookup"><span data-stu-id="e2dda-140">Mac Skype for Business Client (version 16.8.196 and later)</span></span> 
    
  - <span data-ttu-id="e2dda-141">ビジネス クライアント用の android の Skype (バージョン 6.16.0.9 以降)</span><span class="sxs-lookup"><span data-stu-id="e2dda-141">Android Skype for Business Client (version 6.16.0.9 and later)</span></span>
    
  - <span data-ttu-id="e2dda-142">iPhone ビジネス クライアント用の Skype (バージョン 6.16.0 以降)</span><span class="sxs-lookup"><span data-stu-id="e2dda-142">iPhone Skype for Business Client (version 6.16.0 and later)</span></span>
    
  - <span data-ttu-id="e2dda-143">iPad ビジネス クライアント用の Skype (バージョン 6.16.0 以降)</span><span class="sxs-lookup"><span data-stu-id="e2dda-143">iPad Skype for Business Client (version 6.16.0 and later)</span></span>
    
## <a name="step-2---getting-or-transferring-toll-or-toll-free-service-phone-numbers"></a><span data-ttu-id="e2dda-144">ステップ 2 - 有料またはフリーダイヤルのサービス電話番号の取得または移行</span><span class="sxs-lookup"><span data-stu-id="e2dda-144">Step 2 - Getting or transferring toll or toll-free service phone numbers</span></span>

<span data-ttu-id="e2dda-145">Before you can create and set up your call queues, you will need to get or transfer your existing toll or toll-free service numbers.</span><span class="sxs-lookup"><span data-stu-id="e2dda-145">Before you can create and set up your call queues, you will need to get or transfer your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="e2dda-146">有料または無料のサービスの電話番号を取得した後が表示されます**ビジネス管理センターの Skype** > **音声** > **電話番号**と**番号の種類**の一覧には、無料**サービスとして一覧表示されます**.</span><span class="sxs-lookup"><span data-stu-id="e2dda-146">After you get the toll or toll-free service phone numbers, they will show up in **Skype for Business admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="e2dda-147">サービス番号を取得するには、 [Skype のビジネスおよびマイクロソフトのチームの取得サービスの電話番号](getting-service-phone-numbers.md)を参照するか、転送し、既存のサービス番号にする場合は、 [Office 365 に電話番号を転送する](../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2dda-147">To get your service numbers, see [Getting service phone numbers for Skype for Business and Microsoft Teams](getting-service-phone-numbers.md) or if you want to transfer and existing service number, see [Transfer phone numbers to Office 365](../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="e2dda-148">米国以外のユーザーは、サービス番号を取得するビジネス管理センターの Skype を使うことはできません。</span><span class="sxs-lookup"><span data-stu-id="e2dda-148">If you are outside the United States, you can't use the Skype for Business admin center to get service numbers.</span></span> <span data-ttu-id="e2dda-149">[組織の電話番号を管理](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)する代わりに、米国の外側から行う方法を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2dda-149">Go to [Manage phone numbers for your organization](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) instead to see how to do it from the outside of the United States.</span></span>
  
## <a name="step-3---create-a-new-call-queue"></a><span data-ttu-id="e2dda-150">ステップ 3 - 新しい通話キューの作成</span><span class="sxs-lookup"><span data-stu-id="e2dda-150">Step 3 - Create a new Call Queue</span></span>

<span data-ttu-id="e2dda-151">In the **Skype for Business admin center**, click **Call routing** > **Call queues**, then click **Add new**:</span><span class="sxs-lookup"><span data-stu-id="e2dda-151">In the **Skype for Business admin center**, click **Call routing** > **Call queues**, then click **Add new**:</span></span>
  
### <a name="set-the-call-queue-display-name-phone-number-and-domain-if-any"></a><span data-ttu-id="e2dda-152">通話キューの表示名、電話番号、ドメイン (存在する場合) を設定します。</span><span class="sxs-lookup"><span data-stu-id="e2dda-152">Set the call queue display name, phone number and domain (if any)</span></span>

![Setting up a call queue.](../images/37ecc300-a108-4294-8463-fce570dfce72.png)
***
<span data-ttu-id="e2dda-154">![番号 1](../images/sfbcallout1.png)</span><span class="sxs-lookup"><span data-stu-id="e2dda-154">![Number 1](../images/sfbcallout1.png)</span></span><br/>
<span data-ttu-id="e2dda-p110">**名前** 通話キューの分かりやすい名前を入力します。この項目は必須で、空白を含む最大 64 文字を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="e2dda-p110">**Name** Enter a descriptive display name for the call queue. This is required and can contain up to 64 characters, including spaces. </span></span><br/> <span data-ttu-id="e2dda-157">この名前は着信の通知に表示されます。</span><span class="sxs-lookup"><span data-stu-id="e2dda-157">This name will be displayed in the notification for the incoming call.</span></span>
***
<span data-ttu-id="e2dda-158">![番号 2](../images/sfbcallout2.png)</span><span class="sxs-lookup"><span data-stu-id="e2dda-158">![Number 2](../images/sfbcallout2.png)</span></span><br/><span data-ttu-id="e2dda-159">**電話番号** 通話キューのサービスの有料電話番号または無料電話番号を選択します。</span><span class="sxs-lookup"><span data-stu-id="e2dda-159">**Phone number** Select a service toll or toll-free phone number for the call queue.</span></span> <span data-ttu-id="e2dda-160">これは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="e2dda-160">This is optional.</span></span> <br/> <span data-ttu-id="e2dda-161">一覧表示されない場合は、この通話キューを作成する前にサービス番号を取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2dda-161">If there aren't any listed, you need to get service numbers before you can create this call queue.</span></span> <span data-ttu-id="e2dda-162">サービス番号を取得するには、 [Skype のビジネスおよびマイクロソフトのチームの取得サービスの電話番号](getting-service-phone-numbers.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2dda-162">To get your service numbers, see [Getting service phone numbers for Skype for Business and Microsoft Teams](getting-service-phone-numbers.md)</span></span>
***
<span data-ttu-id="e2dda-163">![番号 3](../images/sfbcallout3.png)</span><span class="sxs-lookup"><span data-stu-id="e2dda-163">![Number 3](../images/sfbcallout3.png)</span></span><br/><span data-ttu-id="e2dda-p113">**ドメイン** 利用可能な場合は、使用する Office 365 ドメインを選択します。この項目は、Office 365 で使用しているドメインが 1 つ以上存在する場合にのみ利用できます。1 つ以上存在する場合は、リストからドメイン名を選択します。</span><span class="sxs-lookup"><span data-stu-id="e2dda-p113">**Domain** If this is available, choose the Office 365 domain you want to use. This is only available if you have more than one domain being used with Office 365. If you have more than one, you must chose the domain name from the list. </span></span><br/> <span data-ttu-id="e2dda-167">たとえば、次のようなドメインが存在します。 _contoso.com or redmond.contoso.com_</span><span class="sxs-lookup"><span data-stu-id="e2dda-167">For example, you could have a domain like:  _contoso.com or redmond.contoso.com_</span></span>
   
### <a name="set-the-greeting-and-music-played-while-on-hold"></a><span data-ttu-id="e2dda-168">応答メッセージおよび保留中の保留音を設定する</span><span class="sxs-lookup"><span data-stu-id="e2dda-168">Set the greeting and music played while on hold</span></span>

![Setting up a call queue.](../images/1d395a93-7cab-4178-9295-12d5379e20de.png)
  
***
<span data-ttu-id="e2dda-170">![番号 1](../images/sfbcallout1.png)</span><span class="sxs-lookup"><span data-stu-id="e2dda-170">![Number 1](../images/sfbcallout1.png)</span></span><br/><span data-ttu-id="e2dda-171">**応答メッセージ**は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="e2dda-171">**Greeting** is optional.</span></span> <span data-ttu-id="e2dda-172">これは、応答メッセージが、キューの番号に電話通話する相手を再生します。</span><span class="sxs-lookup"><span data-stu-id="e2dda-172">This is the greeting that is played for people who call in to the call queue number.</span></span> <br/> <span data-ttu-id="e2dda-173">オーディオ ファイル (.wav、.mp3、.wma 形式) をアップロードすることができます。</span><span class="sxs-lookup"><span data-stu-id="e2dda-173">You can upload an audio file (.wav, .mp3, or .wma formats).</span></span>
***
<span data-ttu-id="e2dda-174">![番号 2](../images/sfbcallout2.png)</span><span class="sxs-lookup"><span data-stu-id="e2dda-174">![Number 2](../images/sfbcallout2.png)</span></span><br/><span data-ttu-id="e2dda-175">**上の音楽を保持**呼び出しキューで提供されている保留中のデフォルトの音楽を使用するか、または保留中のカスタムの音楽として使用する .wav、mp3、または .wma ファイルの形式でのオーディオ ファイルをアップロードすることができます。</span><span class="sxs-lookup"><span data-stu-id="e2dda-175">**Music on hold** You can either use the default Music on Hold provided with the call queue, or you can upload an audio file in .wav, mp3, or .wma formats to use as your custom Music on Hold.</span></span> 
   

### <a name="select-the-call-distribution-method"></a><span data-ttu-id="e2dda-176">呼び出しの配布方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="e2dda-176">Select the call distribution method</span></span>

![呼び出しの配布方法のオプションを示しています](../images/5d249515-d532-4af2-90da-011404028b89.png)
  
***
<span data-ttu-id="e2dda-178">![番号 1](../images/sfbcallout1.png)</span><span class="sxs-lookup"><span data-stu-id="e2dda-178">![Number 1](../images/sfbcallout1.png)</span></span><br/><span data-ttu-id="e2dda-179">**配布メソッドを呼び出す**呼び出しキューの配布方法の**アテンダント**または**シリアル**のいずれかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="e2dda-179">**Call distribution method** You can choose either **Attendant** or **Serial** for your call queue distribution method.</span></span> <span data-ttu-id="e2dda-180">新規および既存の呼び出しのすべてのキューは、応答のルーティングが既定で選択されているがあります。</span><span class="sxs-lookup"><span data-stu-id="e2dda-180">All new and existing call queues will have attendant routing selected by default.</span></span> <span data-ttu-id="e2dda-181">シリアルのルーティングを使用するには、UI およびコマンドレットの**シリアル**のルーティング オプションを明示的に選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2dda-181">To use serial routing, you must explicitly choose the **Serial** routing option in UI and cmdlets.</span></span> <br/><br/> <span data-ttu-id="e2dda-182">シリアルのルーティングを選択すると、呼び出しキューを保存する、キューからの呼び出しは、[エージェント] ボックスの一覧の先頭から開始、エージェント、1 つずつをリングします。</span><span class="sxs-lookup"><span data-stu-id="e2dda-182">When serial routing is chosen and the call queue is saved, the calls from the queue will ring your agents one by one, starting from the beginning of the agent list.</span></span> <span data-ttu-id="e2dda-183">エージェントを閉じる、または呼び出しを受けない呼び出しがリストには、次のエージェントが呼び出され、すべてのエージェントによって 1 つ選択して、または、キューで待機していた時間を試みます。</span><span class="sxs-lookup"><span data-stu-id="e2dda-183">If an agent dismisses or does not pick up a call, the call will ring the next agent on the list and will try all agents one by one until it is picked up or times out waiting in the queue.</span></span>  <br/><br/>  <span data-ttu-id="e2dda-184">**注:** シリアルのルーティングと、**オフライン**は、自分の存在を**不可**に設定している、または**削除**このキューからの呼び出しを取得するユーザー エージェントはスキップされます。</span><span class="sxs-lookup"><span data-stu-id="e2dda-184">**Note:** Serial routing will skip agents who are **Offline**, have set their presence to **Do not Disturb**, or have **opted out** of getting calls from this queue.</span></span>  
   
### <a name="select-an-agent-opt-out-option"></a><span data-ttu-id="e2dda-185">エージェントの選択] のオプションが脱退します。</span><span class="sxs-lookup"><span data-stu-id="e2dda-185">Select an agent opt out option</span></span>

![エージェントの選択を表示する] チェック ボックス](../images/99279eff-db61-4acf-9b62-64be84b6414b.png)
  
***
<span data-ttu-id="e2dda-187">![番号 1](../images/sfbcallout1.png)</span><span class="sxs-lookup"><span data-stu-id="e2dda-187">![Number 1](../images/sfbcallout1.png)</span></span><br/><span data-ttu-id="e2dda-188">**エージェントは、オプションを選択****エージェントの選択] オプションを**選択すると、特定のキューからの呼び出しを実行することを辞退するキュー エージェントの呼び出しを許可することができます。</span><span class="sxs-lookup"><span data-stu-id="e2dda-188">**Agent Opt out option** You can choose to allow call queue agents to opt out of taking calls from a particular queue by selecting **Agent Opt out option**.</span></span>  <br/> <span data-ttu-id="e2dda-189">このオプションを有効にすると、このキュー内のすべてのエージェントを開始または停止するのには、この呼び出しキューからの呼び出しを受信するには使用できます。</span><span class="sxs-lookup"><span data-stu-id="e2dda-189">Enabling this option allows all agents in this queue to start or stop receiving call from this call queue at will.</span></span> <span data-ttu-id="e2dda-190">ことができます権限を取り消す、エージェント脱退はいつでも、チェック ボックスをオフにしてに自動的に有効になってこのキューに対して再度 (すべてのエージェントの既定の設定) するようにエージェントを引き起こしています。</span><span class="sxs-lookup"><span data-stu-id="e2dda-190">You can revoke the agent opt-out privilege at any time by clearing the check box, causing agents to become automatically opted in for this queue again (the default setting for all agents).</span></span>  <br/><br/> <span data-ttu-id="e2dda-191">脱退オプションにアクセスするにエージェントは次の操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="e2dda-191">To access the opt-out option, agents can do the following:</span></span>
 1. <span data-ttu-id="e2dda-192">ビジネス クライアント用のデスクトップ、Skype では、**オプション**を開きます。</span><span class="sxs-lookup"><span data-stu-id="e2dda-192">Open **Options** in their desktop Skype for Business client.</span></span> 
 2. <span data-ttu-id="e2dda-193">**呼び出しの転送**] タブでは、**オンラインの設定を編集**] リンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e2dda-193">On the **Call Forwarding** tab, click the **Edit settings online** link.</span></span>
 3. <span data-ttu-id="e2dda-194">[ユーザー設定] ページで、**キューの呼び出し**、] をクリックし、脱退する任意のキューのチェック ボックスをオフにし、します。</span><span class="sxs-lookup"><span data-stu-id="e2dda-194">On the user settings page, click **Call Queues**, and then clear the check boxes for any queues for which they want to opt out.</span></span>
 
    > [!NOTE] 
    > <span data-ttu-id="e2dda-195">Mac を使用してエージェントでは、モバイル、または Lync 2013 クライアント、またはハイブリッド音声ユーザーにホストの設置型ビジネス 2015年サーバーでは、Skype を使用することができますには、 [https://aka.ms/cqsettings](https://aka.ms/cqsettings) 、opt out オプションにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="e2dda-195">Agents using Mac, mobile, or Lync 2013 clients, or Hybrid Voice users who are hosted on-premises using Skype for Business 2015 server, can go to [https://aka.ms/cqsettings](https://aka.ms/cqsettings) to access the opt out option.</span></span>
   
### <a name="add-call-agents-to-a-call-queue"></a><span data-ttu-id="e2dda-196">コール エージェントを通話キューに追加する</span><span class="sxs-lookup"><span data-stu-id="e2dda-196">Add call agents to a call queue</span></span>

![Set up call queues.](../images/skype-for-business-add-agents-to-call-queue.png)
  
***
![番号 1](../images/sfbcallout1.png)<br/><br/><span data-ttu-id="e2dda-199">コール エージェント (最大 50) を指定できます。</span><span class="sxs-lookup"><span data-stu-id="e2dda-199">Call agents (50 maximum) can be:</span></span>
*    <span data-ttu-id="e2dda-200">**電話システム**のライセンスを持つオンラインのユーザー、またはエンタープライズ VoIP の計画を呼び出すことを有効にします。</span><span class="sxs-lookup"><span data-stu-id="e2dda-200">An Online user with a **Phone System** license and enabled for Enterprise Voice or with a Calling Plan.</span></span> <br/><br/> <span data-ttu-id="e2dda-201">**注:** オンラインにいる人が、組織内への呼び出しをリダイレクトするのには、**電話システム**のライセンスが必要しエンタープライズ VoIP を有効にすることも計画を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="e2dda-201">**Note:**  To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have a Calling Plan.</span></span> <span data-ttu-id="e2dda-202">「[Skype for Business と Microsoft Teams のライセンスを割り当てる](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e2dda-202">See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span> <span data-ttu-id="e2dda-203">エンタープライズ VoIP を有効にするには、Windows PowerShell を使用できます。</span><span class="sxs-lookup"><span data-stu-id="e2dda-203">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="e2dda-204">例を実行します。`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="e2dda-204">For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span> <br/><br/>
*    <span data-ttu-id="e2dda-205">オンラインのユーザーに、**電話システム**のライセンスを呼び出す計画、Office 365 のグループ、メールが有効な配布リスト、またはセキュリティ グループに追加されるとします。</span><span class="sxs-lookup"><span data-stu-id="e2dda-205">Online users with a with a **Phone System** license and a Calling Plan that are added to an Office 365 Group, a mail-enabled Distribution List, or a Security Group.</span></span> <span data-ttu-id="e2dda-206">配布リストまたは通話キューからの呼び出しの受信を開始するのにはセキュリティ グループに追加された新しいエージェントの最大 30 分間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="e2dda-206">It might take up to 30 minutes for a new agent added for a distribution list or a security group to start receiving calls from a call queue.</span></span> <span data-ttu-id="e2dda-207">新しく作成した配布リストまたはセキュリティ グループでは、呼び出しキューで使用できるようになるには最大で 48 時間をかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="e2dda-207">A newly created distribution list or security group might take up to 48 hours to become available to be used with call queues.</span></span> <span data-ttu-id="e2dda-208">新しく作成された Office 365 グループは、利用可能なほぼ瞬時に。</span><span class="sxs-lookup"><span data-stu-id="e2dda-208">Newly created Office 365 Groups are available almost immediately.</span></span> <br/> 

    > [!NOTE] 
    > <span data-ttu-id="e2dda-209">ユーザーには、設置がホストされている Lync Server 2010 の使用はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="e2dda-209">Users hosted on-premises using Lync Server 2010 aren't supported.</span></span>           
   
### <a name="set-the-maximum-queue-size-and-maximum-wait-time"></a><span data-ttu-id="e2dda-210">最大キュー サイズと最大待機時間を設定する</span><span class="sxs-lookup"><span data-stu-id="e2dda-210">Set the maximum queue size and maximum wait time</span></span>

![Set up a call queue.](../images/3f018734-16fe-458b-827d-71fc25155cde.png)
  
***
<span data-ttu-id="e2dda-212">![番号 1](../images/sfbcallout1.png)</span><span class="sxs-lookup"><span data-stu-id="e2dda-212">![Number 1](../images/sfbcallout1.png)</span></span><br/><br/><span data-ttu-id="e2dda-213">**キュー内の最大通話数** この項目を使用して、同時に通話がキュー内で待機できる最大通話数を設定します。</span><span class="sxs-lookup"><span data-stu-id="e2dda-213">**Maximum calls in the queue** Use this to set the maximum calls that can wait in the queue at the same time.</span></span> <span data-ttu-id="e2dda-214">既定値 50 が、その範囲は 0 から 200. この制限に達すると、呼び出しは、**呼び出しの最大数に達すると**下の設定で設定した方法で処理します。</span><span class="sxs-lookup"><span data-stu-id="e2dda-214">The default is 50, but it can range from 0 to 200.When this limit is reached, the call will be handled in way you have set on the **When the maximum number of calls is reached** setting below.</span></span>
***
<span data-ttu-id="e2dda-215">![番号 2](../images/sfbcallout2.png)</span><span class="sxs-lookup"><span data-stu-id="e2dda-215">![Number 2](../images/sfbcallout2.png)</span></span><br/><br/><span data-ttu-id="e2dda-216">**呼び出しの最大数に達したとき**呼び出しキューでは、(**キューの最大数を呼び出す**設定を使用して設定) の最大のサイズに達すると、新しくかかってきた呼び出しの動作を選択します。</span><span class="sxs-lookup"><span data-stu-id="e2dda-216">**When the maximum number of calls is reached** When the call queue reaches its maximum size (set using the **Maximum calls in the queue** setting), you can choose what happens to new incoming calls.</span></span>
*    <span data-ttu-id="e2dda-217">**ビジー信号を切断します** 通話は切断されます。</span><span class="sxs-lookup"><span data-stu-id="e2dda-217">**Disconnect with a busy signal** The call will be disconnected.</span></span>
*    <span data-ttu-id="e2dda-218">**呼び出しを転送します。**これを選択するとこれらのオプションが用意されます。</span><span class="sxs-lookup"><span data-stu-id="e2dda-218">**Forward this call to** When you choose this, you will have these options:</span></span>
     *    <span data-ttu-id="e2dda-219">**あなたの会社の人****電話システム**のライセンスを持つオンラインのユーザーとエンタープライズ VoIP を有効にすることも計画を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="e2dda-219">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have a Calling Plan.</span></span> <span data-ttu-id="e2dda-220">発信中のユーザーがボイスメールに送信されるように設定できます。</span><span class="sxs-lookup"><span data-stu-id="e2dda-220">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="e2dda-221">これを行うは、 **、会社の担当者**を選択し、通話をボイスメールに直接転送されるには、このユーザーを設定します。</span><span class="sxs-lookup"><span data-stu-id="e2dda-221">To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span> <br/> <br/><span data-ttu-id="e2dda-222">ボイスメールに必要なライセンスについては、[電話システムのボイス メールの設定](../what-is-phone-system-in-office-365/phone-system-voicemail/set-up-phone-system-voicemail.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2dda-222">To learn about licensing required for voicemail, see [Set up Phone System voicemail](../what-is-phone-system-in-office-365/phone-system-voicemail/set-up-phone-system-voicemail.md).</span></span> 
     
        > [!Note]
        > <span data-ttu-id="e2dda-223">ユーザーには、設置がホストされている Lync Server 2010 の使用はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="e2dda-223">Users hosted on-premises using Lync Server 2010 aren't supported.</span></span><br/>
     
     *    <span data-ttu-id="e2dda-224">**キューを呼び出す**作成する必要が既に別の呼び出しは、キューが、その呼び出しキューを選択するには後、。</span><span class="sxs-lookup"><span data-stu-id="e2dda-224">**Call Queue** You must have already created another call queue, but after you do, you can select that call queue.</span></span>
     *    <span data-ttu-id="e2dda-225">**自動応答**必要があります作成済みの自動応答が行うと、その自動アテンダントを選択できます。</span><span class="sxs-lookup"><span data-stu-id="e2dda-225">**Auto Attendant** You must have already created an auto attendant, but after you do, you can select that auto attendant.</span></span> <span data-ttu-id="e2dda-226">[電話システムの自動応答の設定](set-up-a-phone-system-auto-attendant.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2dda-226">See [Set up a Phone System auto attendant](set-up-a-phone-system-auto-attendant.md).</span></span>
***
<span data-ttu-id="e2dda-227">![番号 3](../images/sfbcallout3.png)</span><span class="sxs-lookup"><span data-stu-id="e2dda-227">![Number 3](../images/sfbcallout3.png)</span></span><br/><br/><span data-ttu-id="e2dda-p123">**通話のキュー内での待機時間** タイムアウトが発生し、通話のリダイレクトまたは切断が必要となるまでに、通話をキュー内で保留できる時間を決定することもできます。リダイレクト先は [ **通話がタイムアウトした場合**] 設定に基づきます。0 から 45 分に設定できます。</span><span class="sxs-lookup"><span data-stu-id="e2dda-p123">**How long a call can wait in the queue** You can also decide how much time a call can be on hold in the queue before it times out and needs to be redirected or disconnected. Where it will be redirected is based on how you set the **When a call times out** setting. You can set a time from 0 to 45 minutes. </span></span><br/><br/> <span data-ttu-id="e2dda-231">15 秒間隔で、秒単位でタイムアウト値を設定できます。</span><span class="sxs-lookup"><span data-stu-id="e2dda-231">The timeout value can be set in seconds, at 15-second intervals.</span></span> <span data-ttu-id="e2dda-232">これにより、細かい粒度での呼び出しの流れを操作することができます。</span><span class="sxs-lookup"><span data-stu-id="e2dda-232">This allows you to manipulate the call flow with finer granularity.</span></span> <span data-ttu-id="e2dda-233">たとえば、ディレクトリ検索の自動応答を 30 秒以内に、エージェントが応答しないすべての呼び出しを移動することを指定できます。</span><span class="sxs-lookup"><span data-stu-id="e2dda-233">For example, you could specify that any calls that are not answered by an agent within 30 seconds go to a Directory Search Auto Attendant.</span></span> 

***
<span data-ttu-id="e2dda-234">![番号 4](../images/sfbcallout4.png)</span><span class="sxs-lookup"><span data-stu-id="e2dda-234">![Number 4](../images/sfbcallout4.png)</span></span><br/><br/><span data-ttu-id="e2dda-235">**通話がタイムアウトした場合** [ **通話のキュー内での待機時間**] 設定で指定した制限に達した通話に対する処理方法を選択できます。</span><span class="sxs-lookup"><span data-stu-id="e2dda-235">**When a call times out** When the call reaches the limit you set on the **How long a call can wait in the queue** setting, you can choose what happens to this call:</span></span>
*    <span data-ttu-id="e2dda-236">**切断** 通話は切断されます。</span><span class="sxs-lookup"><span data-stu-id="e2dda-236">**Disconnect** The call will be disconnected.</span></span>
*    <span data-ttu-id="e2dda-237">**呼び出しを転送します。**これを選択するとこれらのオプションが用意されます。</span><span class="sxs-lookup"><span data-stu-id="e2dda-237">**Forward this call to** When you choose this, you will have these options:</span></span>
     *    <span data-ttu-id="e2dda-238">**あなたの会社の人****電話システム**のライセンスを持つオンラインのユーザーのエンタープライズ VoIP を有効にするか、計画を呼び出すことがあるとします。</span><span class="sxs-lookup"><span data-stu-id="e2dda-238">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have Calling Plans.</span></span> <span data-ttu-id="e2dda-239">発信中のユーザーがボイスメールに送信されるように設定できます。</span><span class="sxs-lookup"><span data-stu-id="e2dda-239">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="e2dda-240">これを行うは、 **、会社の担当者**を選択し、通話をボイスメールに直接転送されるには、このユーザーを設定します。</span><span class="sxs-lookup"><span data-stu-id="e2dda-240">To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span> </br><br/>  <span data-ttu-id="e2dda-241">ボイスメールに必要なライセンスについては、[電話システムのボイス メールの設定](../what-is-phone-system-in-office-365/phone-system-voicemail/set-up-phone-system-voicemail.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2dda-241">To learn about licensing required for voicemail, see [Set up Phone System voicemail](../what-is-phone-system-in-office-365/phone-system-voicemail/set-up-phone-system-voicemail.md).</span></span> 

        > [!Note]
        > <span data-ttu-id="e2dda-242">ユーザーには、設置がホストされている Lync Server 2010 の使用はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="e2dda-242">Users hosted on-premises using Lync Server 2010 aren't supported.</span></span><br/>

     *    <span data-ttu-id="e2dda-243">**キューを呼び出す**作成する必要が既に別の呼び出しは、キューが、その呼び出しキューを選択するには後、。</span><span class="sxs-lookup"><span data-stu-id="e2dda-243">**Call Queue** You must have already created another call queue, but after you do, you can select that call queue.</span></span>
     *    <span data-ttu-id="e2dda-244">**自動応答**必要があります作成済みの自動応答が行うと、その自動アテンダントを選択できます。</span><span class="sxs-lookup"><span data-stu-id="e2dda-244">**Auto Attendant** You must have already created an auto attendant, but after you do, you can select that auto attendant.</span></span> <span data-ttu-id="e2dda-245">[電話システムの自動応答の設定](set-up-a-phone-system-auto-attendant.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2dda-245">See [Set up a Phone System auto attendant](set-up-a-phone-system-auto-attendant.md).</span></span>
   
## <a name="changing-the-users-caller-id-to-be-a-call-queues-phone-number"></a><span data-ttu-id="e2dda-246">呼び出しキューの電話番号を使用するユーザーの呼び出し元の ID を変更します。</span><span class="sxs-lookup"><span data-stu-id="e2dda-246">Changing the user's Caller ID to be a call queue's phone number</span></span>

<span data-ttu-id="e2dda-247">**新規 CallingLineIdentity**コマンドレットを使用してポリシーを作成して代わりに呼び出しキューに発信呼び出しの発信者番号通知を変更することによって、ユーザーの id を保護できます。</span><span class="sxs-lookup"><span data-stu-id="e2dda-247">You can protect a user's identity by changing their caller ID for the outbound calls to a call queue instead by creating a policy using the **New-CallingLineIdentity** cmdlet.</span></span>
  
<span data-ttu-id="e2dda-248">これを行う場合は、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="e2dda-248">To do this, run:</span></span>
  
```
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

<span data-ttu-id="e2dda-249">**許可 CallingLineIdentity**コマンドレットを使用してユーザーにポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="e2dda-249">Then apply the policy to the user using the **Grant-CallingLineIdentity** cmdlet.</span></span> <span data-ttu-id="e2dda-250">これを行う場合は、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="e2dda-250">To do this, run:</span></span>
  
```
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

<span data-ttu-id="e2dda-251">すれば、組織内の呼び出し元 ID の設定を変更する方法の詳細について[は、ここ](../what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization.md)です。</span><span class="sxs-lookup"><span data-stu-id="e2dda-251">You can get more information on how to make changes to caller ID settings in your organization [here](../what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
## <a name="want-to-know-more"></a><span data-ttu-id="e2dda-252">詳細情報</span><span class="sxs-lookup"><span data-stu-id="e2dda-252">Want to know more?</span></span>

<span data-ttu-id="e2dda-253">Windows PowerShell を使用して通話キューを作成し、設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="e2dda-253">You can also use Windows PowerShell to create and set up call queues.</span></span>
  
### <a name="call-queue-cmdlets"></a><span data-ttu-id="e2dda-254">通話キューのコマンドレット</span><span class="sxs-lookup"><span data-stu-id="e2dda-254">Call queue cmdlets</span></span>

<span data-ttu-id="e2dda-255">通話キューの管理で必要なコマンドレットを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="e2dda-255">Here are the cmdlets that you need to manage a call queue.</span></span>
  
- [<span data-ttu-id="e2dda-256">新しい-CsHuntgroup</span><span class="sxs-lookup"><span data-stu-id="e2dda-256">New-CsHuntgroup</span></span>](https://technet.microsoft.com/en-us/library/mt796459.aspx)
    
- [<span data-ttu-id="e2dda-257">セット CsHuntgroup</span><span class="sxs-lookup"><span data-stu-id="e2dda-257">Set-CsHuntgroup</span></span>](https://technet.microsoft.com/en-us/library/mt796457.aspx)
    
- [<span data-ttu-id="e2dda-258">Get CsHuntgroup</span><span class="sxs-lookup"><span data-stu-id="e2dda-258">Get-CsHuntgroup</span></span>](https://technet.microsoft.com/en-us/library/mt796458.aspx)
    
- [<span data-ttu-id="e2dda-259">削除 CsHuntgroup</span><span class="sxs-lookup"><span data-stu-id="e2dda-259">Remove-CsHuntgroup</span></span>](https://technet.microsoft.com/en-us/library/mt796456.aspx)
    
### <a name="more-about-windows-powershell"></a><span data-ttu-id="e2dda-260">Windows PowerShell の詳細について</span><span class="sxs-lookup"><span data-stu-id="e2dda-260">More about Windows PowerShell</span></span>

- <span data-ttu-id="e2dda-p128">Windows PowerShell で行うのは、ユーザーを管理し、ユーザーに何を許可して何を禁止するかを管理することです。Windows PowerShell を利用すると、Office 365 と Skype for Business Online の管理を 1 か所で行うことができるので、複数のタスクを担当する管理者の日常業務を単純化できます。Windows PowerShell の使用を開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2dda-p128">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="e2dda-264">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="e2dda-264">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="e2dda-265">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="e2dda-265">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="e2dda-p129">Windows PowerShell には、ただ Office 365 管理センターを使用するだけではなく、速度、単純さ、生産性において多くの利点があります。次のトピックでこれらの利点について説明します。</span><span class="sxs-lookup"><span data-stu-id="e2dda-p129">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="e2dda-268">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="e2dda-268">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="e2dda-269">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="e2dda-269">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="e2dda-270">クイック リファレンス: Windows PowerShell を使用した一般的な Lync Online の管理タスクの実行</span><span class="sxs-lookup"><span data-stu-id="e2dda-270">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="e2dda-271">See also</span><span class="sxs-lookup"><span data-stu-id="e2dda-271">Related topics</span></span>
[<span data-ttu-id="e2dda-272">Office 365 での電話システムで利用できる機能</span><span class="sxs-lookup"><span data-stu-id="e2dda-272">Here's what you get with Phone System in Office 365</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="e2dda-273">Skype for Business および Microsoft Teams のサービス電話番号の取得</span><span class="sxs-lookup"><span data-stu-id="e2dda-273">Getting service phone numbers for Skype for Business and Microsoft Teams</span></span>](getting-service-phone-numbers.md)

[<span data-ttu-id="e2dda-274">国および地域ごとの電話会議および通話プランの利用可能性</span><span class="sxs-lookup"><span data-stu-id="e2dda-274">Country and region availability for Audio Conferencing and Calling Plans</span></span>](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

  
 