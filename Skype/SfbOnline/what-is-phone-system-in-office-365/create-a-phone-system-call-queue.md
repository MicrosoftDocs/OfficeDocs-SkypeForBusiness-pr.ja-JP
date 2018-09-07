---
title: 電話システムの通話キューを作成する
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: makolomi
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
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
description: 'Office 365 (Cloud PBX) のシステムの通話キュー設定方法　組織のメッセージ、保留音、流通リスト内の企業及びセキュリティ　グループを呼び出すリダイレクト通話。通話キューの最大サイズ、タイムアウトそして通話処理オプションの設定も可能です。 '
ms.openlocfilehash: bb9812eb880ce7451c2fd30f93fa080d6ec84c87
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23854449"
---
# <a name="create-a-phone-system-call-queue"></a><span data-ttu-id="8a0dd-104">電話システムの通話キューを作成する</span><span class="sxs-lookup"><span data-stu-id="8a0dd-104">Create a Phone System call queue</span></span>

<span data-ttu-id="8a0dd-105">電話システムの通話キューには、組織の電話番号への着信時に使用する応答メッセージ機能、自動的に通話を保留する機能、発信者が保留音を聴いている間に次に対応可能なコール エージェントを検索する機能が含まれます。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-105">Skype for Business Online Cloud PBX Call Queues include greetings that are used when someone calls into a phone number for your organization, the ability to automatically put the calls on hold and search for the next available call agent to handle the call while the people who call are listening to music on hold.</span></span> <span data-ttu-id="8a0dd-106">組織では単一または複数の通話キューを作成できます。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-106">You can create a single or multiple call queues for your organization.</span></span>
  
<span data-ttu-id="8a0dd-107">電話システムの通話キューは次の機能を提供します:</span><span class="sxs-lookup"><span data-stu-id="8a0dd-107">Phone System call queues can provide:</span></span>
  
- <span data-ttu-id="8a0dd-108">組織の応答メッセージ。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-108">An organizational greeting.</span></span>
    
- <span data-ttu-id="8a0dd-109">通話の保留中に再生される保留音。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-109">Music while people are waiting on hold.</span></span>
    
- <span data-ttu-id="8a0dd-110">メール対応配布リストとセキュリティ グループを使用した、コール エージェントへの通話のリダイレクト。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-110">Redirecting calls to call agents in mail-enabled distribution lists and security groups.</span></span>
    
- <span data-ttu-id="8a0dd-111">通話キューの最大サイズ、タイムアウト、通話対応オプションの設定。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-111">Making settings for call queue maximum size, timeout and call handling options.</span></span>
    
<span data-ttu-id="8a0dd-112">通話キューが設定されている電話番号に発信すると、最初に応答メッセージ (設定されている場合) が再生され、通話はキューに入れられ、次に対応可能なコールエージェントの対応を待ちます。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-112">When someone calls in to a phone number that is setup up with a call queue, they will hear a greeting first (if any is setup), and then they will be put in the queue and wait for the next available call agent. The person calling in will hear music while they are on hold waiting, and the calls will be offered to the call agents in the  First In, First Out  (FIFO) manner.</span></span> <span data-ttu-id="8a0dd-113">対応を待っている発信者が保留音を聞いている間に、通話は *先入先出法*  (FIFO) でコール エージェントに送られます。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-113">When someone calls in to a phone number that is setup up with a call queue, they will hear a greeting first (if any is setup), and then they will be put in the queue and wait for the next available call agent. The person calling in will hear music while they are on hold waiting, and the calls will be offered to the call agents in the  *First In, First Out*  (FIFO) manner.</span></span>
  
<span data-ttu-id="8a0dd-114">キューで待機しているすべての通話は、応答ルーティング モードまたはシリアル・ルーティングモードを使用して配布されます。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-114">All calls waiting in the queue will be distributed using an attendant routing mode:</span></span>
  
- <span data-ttu-id="8a0dd-115">応答のルーティングでは、キューにある最初の呼び出しはすべてのエージェントを同時に呼び出します。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-115">The first call in the queue will ring all call agents at the same time.</span></span>
    
- <span data-ttu-id="8a0dd-116">シリアル・ルーティングでは、キュー内の最初の呼び出しがすべてのコールエージェントを一件ずつ呼び出します。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-116">With serial routing, the first call in the queue will ring all call agents one by one.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="8a0dd-117">**オフライン**中のコールエージェントは、 **取り込み中** のプレゼンスを設定するか、通話キューからの呼び出しをオプトアウトしてください。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-117">Call agents who are **Offline**, have set their presence to **Do not Disturb,** or have opted out of the call queue won't be called.</span></span>
  
- <span data-ttu-id="8a0dd-118">一度に 1 回のみの着信通知 (キューの最初にある通話) がコール エージェントに送信されます。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-118">Only one incoming call notification (for the call at the head of the queue) at a time will be sent to the call agents.</span></span>
    
- <span data-ttu-id="8a0dd-119">コール エージェントが通話を受けると、キューにある次の着信がコール エージェントを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-119">After a call agent accepts the call, the next incoming call in the queue will start ringing call agents.</span></span>
    
## <a name="step-1---getting-started"></a><span data-ttu-id="8a0dd-120">ステップ 1 - はじめに</span><span class="sxs-lookup"><span data-stu-id="8a0dd-120">Step 1 - Getting started</span></span>

<span data-ttu-id="8a0dd-121">通話キューを使用する場合は、次の重要な点にご注意ください。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-121">To get started using call queues, it's important to remember a few things:</span></span>
  
- <span data-ttu-id="8a0dd-122">組織には、(最低でも) Enterprise E3 plus **電話システム**ライセンスまたは Enterprise E5 ライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-122">Your organization must have (at a minimum) an Enterprise E3 plus Skype for Business Cloud PBX license or an Enterprise E5 license.</span></span> <span data-ttu-id="8a0dd-123">**電話システム**のユーザーライセンス番号は、通話キューに使用する利用可能なサービス番号に影響する番号に割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-123">The number of Skype for Business Cloud PBX user licenses that are assigned impacts the number of service numbers that are available to be used for call queues.</span></span> <span data-ttu-id="8a0dd-124">保有できる通話キューの数は、組織で割り当てられた**電話システム**と**電話会議**ライセンスの数によって異なります。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-124">The number of call queues you can have is dependent on the number Skype for Business Cloud PBX and PSTN Conferencing licenses that are assigned in your organization.</span></span> <span data-ttu-id="8a0dd-125">ライセンスに関する詳細については、 [こちらを](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md) ご覧下さい。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-125">To learn more about licensing, go [here](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="8a0dd-126">オンライン中である組織内のユーザーにリダイレクトするには、**電話システム**のライセンスを取得し、エンタープライズ VoIP を有効にするか、Office 365通話プランを取得することが必要です。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-126">To redirect calls to people in your organization that are Online, they must have a Cloud PBX license and be enabled for Enterprise Voice or have PSTN calling plan.</span></span> <span data-ttu-id="8a0dd-127">「[Skype for Business と Microsoft Teams のライセンスを割り当てる](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-127">See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span> <span data-ttu-id="8a0dd-128">エンタープライズ VoIP を有効にするには、Windows PowerShell を使用できます。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-128">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="8a0dd-129">たとえば、以下を実行します。  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="8a0dd-129">For example, run:`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>
  
- <span data-ttu-id="8a0dd-130">Office 365通話プランの詳細については、「[Office 365 通話プランと何ですか？](/microsoftteams/what-are-calling-plans-in-office-365)」及び「[Office 365の通話プラン](/microsoftteams/calling-plans-for-office-365)」をご覧下さい。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-130">To learn more about Office 365 Calling Plans, see [What are Calling Plans in Office 365?](/microsoftteams/what-are-calling-plans-in-office-365) and [Calling Plans for Office 365](/microsoftteams/calling-plans-for-office-365).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="8a0dd-131">Lync Server 2010 を使用中のオンプレミスでホストされているユーザーは、通話キューのエージェントとしてサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-131">Users hosted on-premises using Skype for Business Server 2015 or Lync Server 2013 and 2010 aren't supported as a Call Queue Agents.</span></span> 
  
- <span data-ttu-id="8a0dd-132">**Skype for Business 管理センター**で取得または 別のサービスプロバイダーから電話システム通話キューへ移行した、有料またはフリーダイヤルの番号のみを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-132">You can only assign a toll and toll-free service phone number that you got in the Skype for Business admin center or transferred from another service provider to Cloud PBX Call Queues.</span></span> <span data-ttu-id="8a0dd-133">フリー ダイヤル番号の取得および使用には、コミュニケーションク レジットを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-133">To get and use toll-free service numbers, you need to set up PSTN Consumption Billing.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="8a0dd-134">ユーザー (購読者) の電話番号を通話キューに割り当てることはできません。サービスの有料電話番号または無料電話番号のみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-134">User (subscriber) phone numbers can't be assigned to call queues - only service toll or toll-free phone numbers can be used.</span></span> 
  
- <span data-ttu-id="8a0dd-135">電話システム通話キューからの着信通話を配布している場合、以下のクライアントが通話エージェントでサポートされます。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-135">When you are distributing the incoming calls from a Cloud PBX Call Queue, these clients are supported for call agents:</span></span>
    
  - <span data-ttu-id="8a0dd-136">Skype for Business デスクトップ クライアント 2016 (32 および 64 ビット バージョン)</span><span class="sxs-lookup"><span data-stu-id="8a0dd-136">Skype for Business desktop client 2016 (32 and 64-bit versions)</span></span>
    
  - <span data-ttu-id="8a0dd-137">Lync デスクトップ クライアント 2013 (32 および 64 ビット バージョン)</span><span class="sxs-lookup"><span data-stu-id="8a0dd-137">Lync desktop client 2013 (32 and 64-bit versions)</span></span>
    
  - <span data-ttu-id="8a0dd-138">Skype for Business Online でサポートされているすべての IP 電話の機種</span><span class="sxs-lookup"><span data-stu-id="8a0dd-138">All IP phone models supported for Skype for Business Online.</span></span> <span data-ttu-id="8a0dd-139">「[Skype for Business Online で使う電話を入手する](getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-139">See, [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online.md).</span></span>
    
  - <span data-ttu-id="8a0dd-140">Mac版  Skype for Business クライアント (バージョン 16.8.196 以降)</span><span class="sxs-lookup"><span data-stu-id="8a0dd-140">Mac Skype for Business Client (version 16.8.196 and later)</span></span> 
    
  - <span data-ttu-id="8a0dd-141">Aandroid Skype for Business クライアント (バージョン 6.16.0.9 以降)</span><span class="sxs-lookup"><span data-stu-id="8a0dd-141">Android Skype for Business Client (version 6.16.0.9 and later)</span></span>
    
  - <span data-ttu-id="8a0dd-142">iPhone Skype for Business Client クライアント(バージョン 6.16.0 以降)</span><span class="sxs-lookup"><span data-stu-id="8a0dd-142">iPhone Skype for Business Client (version 6.16.0 and later)</span></span>
    
  - <span data-ttu-id="8a0dd-143">Mac版  Skype for Business クライアント (バージョン 6.16.0 以降)</span><span class="sxs-lookup"><span data-stu-id="8a0dd-143">iPad Skype for Business Client (version 6.16.0 and later)</span></span>

  - <span data-ttu-id="8a0dd-144">Microsoft Teams Windows クライアント (バージョン 32 および 64 ビット)</span><span class="sxs-lookup"><span data-stu-id="8a0dd-144">Microsoft Teams Windows client (32 and 64-bit versions)</span></span>

  - <span data-ttu-id="8a0dd-145">Microsoft Teams Mac クライアント</span><span class="sxs-lookup"><span data-stu-id="8a0dd-145">Microsoft Teams Mac client</span></span>

  - <span data-ttu-id="8a0dd-146">Microsoft Teams iPhone 用 アプリ</span><span class="sxs-lookup"><span data-stu-id="8a0dd-146">Microsoft Teams app</span></span>

  - <span data-ttu-id="8a0dd-147">Microsoft Teams Android 用 アプリ</span><span class="sxs-lookup"><span data-stu-id="8a0dd-147">Microsoft Teams app</span></span>
    
## <a name="step-2---getting-or-transferring-toll-or-toll-free-service-phone-numbers"></a><span data-ttu-id="8a0dd-148">ステップ 2 - 有料または無料のサービス電話番号の取得または移行</span><span class="sxs-lookup"><span data-stu-id="8a0dd-148">Step 2 - Getting or transferring toll or toll-free service phone numbers</span></span>

<span data-ttu-id="8a0dd-149">通話キューを作成し設定する前に、既存の有料または無料のサービス番号を取得もしくは転送する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-149">Before you can create and set up your call queues, you will need to get or transfer your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="8a0dd-150">有料または無料のサービスの電話番号を取得した後、  **Skype for Business 管理センター** > **音声** > **電話番号** に番号が表示され、  **番号の種類** のリストには、 **サービスー無料** として一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-150">After you get the toll or toll-free service phone numbers, they will show up in **Skype for Business admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="8a0dd-151">サービス番号を取得するには、  [Skype for Business と Microsoft Teams 用のサービス電話番号の取得](getting-service-phone-numbers.md) を参照するか、既存のサービス番号を転送する場合は、  [Office 365 に電話番号を転送する](/microsoftteams/transfer-phone-numbers-to-office-365) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-151">To get your service numbers, see [Getting service phone numbers for Skype for Business and Microsoft Teams](getting-service-phone-numbers.md) or if you want to transfer and existing service number, see [Transfer phone numbers to Office 365](/microsoftteams/transfer-phone-numbers-to-office-365).</span></span>
  
> [!NOTE]
> <span data-ttu-id="8a0dd-152">米国以外の国では、Skype for Business 管理センターを使用してサービス番号を取得することはできません。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-152">If you are outside the U.S., you can't use the Skype for Business admin center to get service numbers.</span></span> <span data-ttu-id="8a0dd-153">米国以外の国でサービス番号を取得する方法については、「[組織の電話番号を管理する](/microsoftteams/manage-phone-numbers-for-your-organization)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-153">Go [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) instead to see how to do it from the outside of the U.S.</span></span>
  
## <a name="step-3---create-a-new-call-queue"></a><span data-ttu-id="8a0dd-154">ステップ 3 - 新しい通話キューの作成</span><span class="sxs-lookup"><span data-stu-id="8a0dd-154">Step 3 - Create a new Call Queue</span></span>

<span data-ttu-id="8a0dd-155">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Skype for Business の管理センターを使用する**</span><span class="sxs-lookup"><span data-stu-id="8a0dd-155">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

<span data-ttu-id="8a0dd-156">**Skype for Business 管理センター**で、 「**通話ルーティング**」  >  「**通話キュー**」をクリックし、次に「**新しく追加**」をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-156">In the **Skype for Business admin center**, click **Call routing** > **Call queues**, then click **Add new**:</span></span>
  
### <a name="set-the-call-queue-display-name-phone-number-and-domain-if-any"></a><span data-ttu-id="8a0dd-157">通話キューの表示名、電話番号、ドメイン (存在する場合) を設定します。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-157">Set the call queue display name, phone number and domain (if any)</span></span>

![通話キューの設定](../images/37ecc300-a108-4294-8463-fce570dfce72.png)
***
<span data-ttu-id="8a0dd-159">![1](../images/sfbcallout1.png)</span><span class="sxs-lookup"><span data-stu-id="8a0dd-159">![Number 1](../images/sfbcallout1.png)</span></span><br/>
<span data-ttu-id="8a0dd-p110">**名前** 通話キューの表示名をわかりやすい名前にして入力します。この項目は必須で、空白を含む最大 64 文字を使用できます。 </span><span class="sxs-lookup"><span data-stu-id="8a0dd-p110">**Name** Enter a descriptive display name for the call queue. This is required and can contain up to 64 characters, including spaces. </span></span><br/> <span data-ttu-id="8a0dd-162">この名前は着信の通知に表示されます。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-162">This name will be displayed in the notification for the incoming call.</span></span>
***
<span data-ttu-id="8a0dd-163">![2](../images/sfbcallout2.png)</span><span class="sxs-lookup"><span data-stu-id="8a0dd-163">![Number 2](../images/sfbcallout2.png)</span></span><br/><span data-ttu-id="8a0dd-164">**電話番号** 通話キューのサービスの有料電話番号または無料電話番号を選択します。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-164">**Phone number** Select a service toll or toll-free phone number for the call queue.</span></span> <span data-ttu-id="8a0dd-165">これはオプションです。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-165">This procedure is optional.</span></span> <br/> <span data-ttu-id="8a0dd-166">何も一覧表示されない場合は、この通話キューを作成する前にサービス番号を取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-166">If there aren't any listed, you need to get service numbers before you can create this call queue.</span></span> <span data-ttu-id="8a0dd-167">サービス番号を取得するには、「[ Skype for Business および Microsoft Teams のサービス電話番号の取得](getting-service-phone-numbers.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-167">To get your service numbers, see [Getting service phone numbers for Skype for Business and Microsoft Teams](getting-service-phone-numbers.md) or if you want to transfer and existing service number, see Transfer phone numbers to Office 365.</span></span>
***
<span data-ttu-id="8a0dd-168">![3](../images/sfbcallout3.png)</span><span class="sxs-lookup"><span data-stu-id="8a0dd-168">![Number 3](../images/sfbcallout3.png)</span></span><br/><span data-ttu-id="8a0dd-p113">**ドメイン** 利用可能な場合は、使用する Office 365 ドメインを選択します。この項目は、Office 365 で使用しているドメインが 1 つ以上存在する場合にのみ利用できます。1 つ以上存在する場合は、リストからドメイン名を選択します。 </span><span class="sxs-lookup"><span data-stu-id="8a0dd-p113">**Domain** If this is available, choose the Office 365 domain you want to use. This is only available if you have more than one domain being used with Office 365. If you have more than one, you must chose the domain name from the list. </span></span><br/> <span data-ttu-id="8a0dd-172">たとえば、次のようなドメインが存在します。 _contoso.com or redmond.contoso.com_</span><span class="sxs-lookup"><span data-stu-id="8a0dd-172">For example, you could have a domain like:  _contoso.com or redmond.contoso.com_</span></span>
   
### <a name="set-the-greeting-and-music-played-while-on-hold"></a><span data-ttu-id="8a0dd-173">応答メッセージおよび保留中の保留音を設定する</span><span class="sxs-lookup"><span data-stu-id="8a0dd-173">Set the greeting and music played while on hold</span></span>

![通話キューの設定](../images/1d395a93-7cab-4178-9295-12d5379e20de.png)
  
***
<span data-ttu-id="8a0dd-175">![1](../images/sfbcallout1.png)</span><span class="sxs-lookup"><span data-stu-id="8a0dd-175">![Number 1](../images/sfbcallout1.png)</span></span><br/><span data-ttu-id="8a0dd-176">**応答メッセージ**は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-176">**Greeting** is optional.</span></span> <span data-ttu-id="8a0dd-177">これは、発信者が通話キュー番号に通話する際に再生される応答メッセージです。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-177">This is the greeting that is played for people that call into the call queue number.</span></span> <br/> <span data-ttu-id="8a0dd-178">音声ファイル (.wav, .mp3 または .wma 形式) をアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-178">You can upload an audio file (.wav, .mp3 or .wma formats).</span></span>
***
<span data-ttu-id="8a0dd-179">![2](../images/sfbcallout2.png)</span><span class="sxs-lookup"><span data-stu-id="8a0dd-179">![Number 2](../images/sfbcallout2.png)</span></span><br/><span data-ttu-id="8a0dd-180">**保留音** 通話キューに提供されている既定の保留音を使用するか、カスタムの保留音として使用する音声ファイルを .wav、mp3 または .wma 形式でアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-180">**Music on hold**, You can either use the default Music on Hold provided with the Call Queue, or you can upload an audio file in .wav, mp3 or .wma formats to use as your custom Music on Hold.</span></span> 
   

### <a name="select-the-call-distribution-method"></a><span data-ttu-id="8a0dd-181">着信分配メソッドを選択する</span><span class="sxs-lookup"><span data-stu-id="8a0dd-181">Select the call distribution method</span></span>

![着信分配メソッドのオプションを表示する](../images/5d249515-d532-4af2-90da-011404028b89.png)
  
***
<span data-ttu-id="8a0dd-183">![1](../images/sfbcallout1.png)</span><span class="sxs-lookup"><span data-stu-id="8a0dd-183">![Number 1](../images/sfbcallout1.png)</span></span><br/><span data-ttu-id="8a0dd-184">**着信分配メソッド** 通話キュー分配メソッドでは、 **[Attendant]** または **[Serial]** のいずれかを選択することができます。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-184">**Call distribution method** You can choose either **Attendant** or **Serial** for your call queue distribution method.</span></span> <span data-ttu-id="8a0dd-185">新規および既存のすべての通話キューは、応答のルーティングが既定値で選択されます。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-185">All new and existing call queues will have attendant routing selected by default.</span></span> <span data-ttu-id="8a0dd-186">シリアル ルーティングを使用するには、UI およびコマンドレットの **シリアル** のルーティング オプションを明示的に選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-186">To use serial routing, you must explicitly choose the **Serial** routing option in UI and cmdlets.</span></span> <br/><br/> <span data-ttu-id="8a0dd-187">シリアルのルーティングを選択して通話キューを保存すると、通話キューからの発信は、エージェントリストの先頭から1つずつ行われます。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-187">When serial routing is chosen and the call queue is saved, the calls from the queue will ring your agents one by one, starting from the beginning of the agent list.</span></span> <span data-ttu-id="8a0dd-188">エージェントが退出中、または応答しない場合、リスト上の次のエージェントを呼び出し、キューで待機中の発信が応答するかタイムアウトになるまで、すべてのエージェントの呼び出しを 1 件ずつ試みます。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-188">If an agent dismisses or does not pick up a call, the call will ring the next agent on the list and will try all agents one by one until it is picked up or times out waiting in the queue.</span></span>   

> [!NOTE]
> <span data-ttu-id="8a0dd-189">**オフライン**中、**取り込み中**表示、またはこのキューからの着信を **オプトアウト** したエージェントは、シリアルルーティングからスキップされます。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-189">Serial routing will skip agents who are **Offline**, have set their presence to **Do not Disturb**, or have **opted out** of getting calls from this queue.</span></span> 
   
### <a name="select-an-agent-opt-out-option"></a><span data-ttu-id="8a0dd-190">エージェントのオプトアウトのオプションを選択する</span><span class="sxs-lookup"><span data-stu-id="8a0dd-190">Select an agent opt out option</span></span>

![オプトアウトするエージェントのチェック ボックスの表示](../images/99279eff-db61-4acf-9b62-64be84b6414b.png)
  
***
<span data-ttu-id="8a0dd-192">![1](../images/sfbcallout1.png)</span><span class="sxs-lookup"><span data-stu-id="8a0dd-192">![Number 1](../images/sfbcallout1.png)</span></span><br/><span data-ttu-id="8a0dd-193">**エージェント オプトアウト オプション** **エージェントのオプトアウト オプション**選択して特定のキューからの着信をオプトアウトすることができます。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-193">**Agent Opt out option** You can choose to allow call queue agents to opt out of taking calls from a particular queue by selecting **Agent Opt out option**.</span></span>  <br/> <span data-ttu-id="8a0dd-194">このオプションを有効にすると、このキュー内のすべてのエージェントはこの通話からの着信を自由に開始または停止することができます。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-194">Enabling this option allows all agents in this queue to start or stop receiving call from this call queue at will.</span></span> <span data-ttu-id="8a0dd-195">チェックボックスの削除することによっていつでもオプトアウトの取消しが可能で、オプトアウトされたエージェントはこの通話キューへ自動的にもう一度オプトインされます。 (すべてのエージェントの初期設定)</span><span class="sxs-lookup"><span data-stu-id="8a0dd-195">You can revoke the agent opt-out privilege at any time by clearing the check box, causing agents to become automatically opted in for this queue again (the default setting for all agents).</span></span>  <br/><br/> <span data-ttu-id="8a0dd-196">エージェントは次の操作を行うと、オプトアウトのオプションにアクセスできます:</span><span class="sxs-lookup"><span data-stu-id="8a0dd-196">To access the opt-out option, agents can do the following:</span></span>
 1. <span data-ttu-id="8a0dd-197">Skype for Business クライアントデスクトップで、 **オプション** を開きます。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-197">Open **Options** in their desktop Skype for Business client.</span></span> 
 2. <span data-ttu-id="8a0dd-198">**[通話転送]** タブで、 **[オンライン編集の設定]** リンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-198">On the **Call Forwarding** tab, click the **Edit settings online** link.</span></span>
 3. <span data-ttu-id="8a0dd-199">ユーザー設定ページで、 **通話キュー**をクリックし、次にオプトアウトしたいキューのチェック ボックスを削除します。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-199">On the user settings page, click **Call Queues**, and then clear the check boxes for any queues for which they want to opt out.</span></span>
 
    > [!NOTE] 
    > <span data-ttu-id="8a0dd-200">Mac、モバイル、または Lync 2013 クライアントを使用しているエージェント、または Skype for Business 2015 サーバーを使用しているオンプレミスでホストされている Hybrid Voice ユーザーは、 [https://aka.ms/cqsettings](https://aka.ms/cqsettings) で、オプトアウトのオプションにアクセスすることができます。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-200">Agents using Mac, mobile, or Lync 2013 clients, or Hybrid Voice users who are hosted on-premises using Skype for Business 2015 server, can go to [https://aka.ms/cqsettings](https://aka.ms/cqsettings) to access the opt out option.</span></span>
   
### <a name="add-call-agents-to-a-call-queue"></a><span data-ttu-id="8a0dd-201">コール エージェントを通話キューに追加する</span><span class="sxs-lookup"><span data-stu-id="8a0dd-201">Add call agents to a call queue</span></span>

![通話キューの設定](../images/skype-for-business-add-agents-to-call-queue.png)
  
***
![1](../images/sfbcallout1.png)<br/><br/><span data-ttu-id="8a0dd-204">コール エージェント (最大数 50 件) は以下のことができます：</span><span class="sxs-lookup"><span data-stu-id="8a0dd-204">Call agents (50 maximum) can be:</span></span>
*    <span data-ttu-id="8a0dd-205">**電話システム** のライセンスを持つオンラインのユーザーとして、エンタープライズ ボイスまたは 通話の計画を有効にします。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-205">An Online user with a **Phone System** license and enabled for Enterprise Voice or with a Calling Plan.</span></span> <br/><br/> <span data-ttu-id="8a0dd-206">**注:** オンライン中である組織内のユーザーにリダイレクトするには、 **電話システム** のライセンスを取得し、エンタープライズ VoIP を有効にするか、通話プランを取得することが必要です。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-206">To redirect calls to people in your organization that are Online, they must have a Cloud PBX license and be enabled for Enterprise Voice or have PSTN calling plan.</span></span> <span data-ttu-id="8a0dd-207">「[Skype for Business と Microsoft Teams のライセンスを割り当てる](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-207">See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span> <span data-ttu-id="8a0dd-208">エンタープライズ VoIP を有効にするには、Windows PowerShell を使用できます。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-208">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="8a0dd-209">たとえば、以下を実行します。  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="8a0dd-209">For example, run:`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span> <br/><br/>
*    <span data-ttu-id="8a0dd-210">**電話システム** ライセンスおよび通話プランを取得しているオンラインユーザーは、計画を呼び出すと、Office 365 グループ、有効なメールの分配リスト、またはセキュリティ グループに追加されます。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-210">Online users with a **Phone System** license and a Calling Plan that are added to an Office 365 Group, a mail-enabled Distribution List, or a Security Group.</span></span> <span data-ttu-id="8a0dd-211">分配リストまたはセキュリティグループに追加された新しいエージェントは、通話キューからの受信を開始するのには最大 30 分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-211">It might take up to 30 minutes for a new agent added for a distribution list or a security group to start receiving calls from a call queue.</span></span> <span data-ttu-id="8a0dd-212">新しく作成した分配リストまたはセキュリティ グループでは、通話キューで使用可能になるまで最大で48時間を要する場合があります。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-212">A newly created distribution list or security group might take up to 48 hours to become available to be used with call queues.</span></span> <span data-ttu-id="8a0dd-213">新しく作成された Office 365 グループは、ほぼ瞬時にご利用可能です。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-213">Newly created Office 365 Groups are available almost immediately.</span></span> <br/> 

    > [!NOTE] 
    > <span data-ttu-id="8a0dd-214">Lync Server 2010 を使用中のオンプレミスでホストされているユーザーはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-214">Users hosted on-premises using Skype for Business Server 2015, Lync Server 2013 and 2010 aren't supported.</span></span>           
   
### <a name="set-the-maximum-queue-size-and-maximum-wait-time"></a><span data-ttu-id="8a0dd-215">最大キュー サイズと最大待機時間を設定する</span><span class="sxs-lookup"><span data-stu-id="8a0dd-215">Set the maximum queue size and maximum wait time</span></span>

![通話キューの設定](../images/3f018734-16fe-458b-827d-71fc25155cde.png)
  
***
<span data-ttu-id="8a0dd-217">![1](../images/sfbcallout1.png)</span><span class="sxs-lookup"><span data-stu-id="8a0dd-217">![Number 1](../images/sfbcallout1.png)</span></span><br/><br/><span data-ttu-id="8a0dd-218">**キュー内の最大通話数** この項目を使用して、同時にキュー内で待機できる最大通話数を設定します。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-218">**Maximum calls in the queue** Use this to set the maximum calls that can wait in the queue at the same time.</span></span> <span data-ttu-id="8a0dd-219">既定値は 50 ですが、0 から 200 の幅で変更できます。最大通話数に達した場合、 **で設定した方法で処理します。最大通話数が以下の** 設定に達した場合:</span><span class="sxs-lookup"><span data-stu-id="8a0dd-219">When this limit is reached, the call will be handled in way you have set on the **When the maximum number of calls is reached** setting below.</span></span>
***
<span data-ttu-id="8a0dd-220">![2](../images/sfbcallout2.png)</span><span class="sxs-lookup"><span data-stu-id="8a0dd-220">![Number 2](../images/sfbcallout2.png)</span></span><br/><br/><span data-ttu-id="8a0dd-221">**最大通話数に達した場合** 通話キューが最大サイズに達した場合 ([ **キュー内の最大通話数** ] 設定を使用して設定) 、新しい着信の処理を選択できます。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-221">**When the maximum number of calls is reached** When the call queue reaches it's maximum size (set using the **Maximum calls in the queue** setting), you can choose what happens to new incoming calls.</span></span>
*    <span data-ttu-id="8a0dd-222">**ビジー信号を発行して切断** 通話は切断されます。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-222">**Disconnect with a busy signal** The call will be disconnected.</span></span>
*    <span data-ttu-id="8a0dd-223">**転送先** この項目を選択する場合は、次のオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-223">**Forward to** When you choose this, you will have these options:</span></span>
     *    <span data-ttu-id="8a0dd-224">**社内のユーザー** **電話システム** のライセンスを持つオンラインのユーザーそしてエンタープライズ ボイス を有効にするか通話プランを取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-224">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have a Calling Plan.</span></span> <span data-ttu-id="8a0dd-225">発信者がボイスメールに送られるように設定できます。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-225">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="8a0dd-226">この設定を行うには、**[社内のユーザー]** を選択して、そのユーザーの呼び出しが直接ボイスメールに転送されるように設定します。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-226">To do this, select a **Person in your company** and set this person's calls to be forwarded directly to voicemail.</span></span> <br/> <br/><span data-ttu-id="8a0dd-227">ボイスメールに必要なライセンスについては、 [電話システムのボイス メールの設定](/microsoftteams/set-up-phone-system-voicemail)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-227">To learn about licensing required for voicemail, see [Set up Phone System voicemail](/microsoftteams/set-up-phone-system-voicemail).</span></span> 
     
        > [!Note]
        > <span data-ttu-id="8a0dd-228">Lync Server 2010 を使用中のオンプレミスでホストされているユーザーはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-228">Users hosted on-premises using Skype for Business Server 2015, Lync Server 2013 and 2010 aren't supported.</span></span><br/>
     
     *    <span data-ttu-id="8a0dd-229">**通話キュー** 別の通話キューを選択するには、まずその通話キューを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-229">>  Users hosted on-premises using Skype for Business Server 2015 and Lync Server 2013 and 2010 aren't supported.          **Call Queue** You must have already created another call queue, but after you do, then you can select that call queue.</span></span>
     *    <span data-ttu-id="8a0dd-230">**自動応答** 自動応答を選択するには、まずその自動応答を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-230">**Auto Attendant** You must have already created an auto attendant, but after you do, then you can select that auto attendant. SeeSet up a Cloud PBX auto attendant.</span></span> <span data-ttu-id="8a0dd-231">[「電話システムの自動応答を設定する」](set-up-a-phone-system-auto-attendant.md)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-231">[Set up a Phone System auto attendant](set-up-a-phone-system-auto-attendant.md)</span></span>
***
<span data-ttu-id="8a0dd-232">![3](../images/sfbcallout3.png)</span><span class="sxs-lookup"><span data-stu-id="8a0dd-232">![Number 3](../images/sfbcallout3.png)</span></span><br/><br/><span data-ttu-id="8a0dd-p123">**通話のキュー内での待機時間** タイムアウトが発生し、通話のリダイレクトまたは切断が必要となるまでに、通話をキュー内で保留できる時間を決定することもできます。リダイレクト先は [ **通話がタイムアウトした場合**] 設定に基づきます。0 から 45 分に設定できます。 </span><span class="sxs-lookup"><span data-stu-id="8a0dd-p123">**How long a call can wait in the queue** You can also decide how much time a call can be on hold in the queue before it times out and needs to be redirected or disconnected. Where it will be redirected is based on how you set the **When a call times out** setting. You can set a time from 0 to 45 minutes. </span></span><br/><br/> <span data-ttu-id="8a0dd-236">タイムアウト値は秒単位で、 15 秒間隔で設定することができます。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-236">The timeout value can be set in seconds, at 15-second intervals.</span></span> <span data-ttu-id="8a0dd-237">これにより、通話フローを細かく操作することができます。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-237">This allows you to manipulate the call flow with finer granularity.</span></span> <span data-ttu-id="8a0dd-238">たとえば、エージェントが 30 秒以内に応答しなかった場合、ディレクトリ検索の自動応答に転送するように指定することができます。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-238">For example, you could specify that any calls that are not answered by an agent within 30 seconds go to a Directory Search Auto Attendant.</span></span> 

***
<span data-ttu-id="8a0dd-239">![4](../images/sfbcallout4.png)</span><span class="sxs-lookup"><span data-stu-id="8a0dd-239">![Number 4](../images/sfbcallout4.png)</span></span><br/><br/><span data-ttu-id="8a0dd-240">**通話がタイムアウトした場合** [ **通話のキュー内での待機時間**] 設定で指定した制限に達した通話に対する処理方法を選択できます。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-240">**When a call times out** When the call reaches the limit you set on the **How long a call can wait in the queue** setting, you can choose what happens to this call:</span></span>
*    <span data-ttu-id="8a0dd-241">**切断** 通話は切断されます。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-241">**Disconnect** The call will be disconnected.</span></span>
*    <span data-ttu-id="8a0dd-242">**転送先** この項目を選択する場合は、次のオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-242">**Forward to** When you choose this, you will have these options:</span></span>
     *    <span data-ttu-id="8a0dd-243">**社内のユーザー** **電話システム** のライセンスを持つオンラインユーザーで、エンタープライズ ボイス が有効化されているまたは、通話プランを取得済みである必要があります。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-243">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have Calling Plans.</span></span> <span data-ttu-id="8a0dd-244">発信者がボイスメールに送られるように設定できます。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-244">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="8a0dd-245">この設定を行うには、**[社内のユーザー]** を選択して、そのユーザーの呼び出しが直接ボイスメールに転送されるように設定します。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-245">To do this, select a **Person in your company** and set this person's calls to be forwarded directly to voicemail.</span></span> </br><br/>  <span data-ttu-id="8a0dd-246">ボイスメールに必要なライセンスについては、 [「電話システムのボイスメールの設定」](/microsoftteams/set-up-phone-system-voicemail) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-246">To learn about licensing required for voicemail, see [Set up Phone System voicemail](/microsoftteams/set-up-phone-system-voicemail).</span></span> 

        > [!Note]
        > <span data-ttu-id="8a0dd-247">Lync Server 2010 を使用中のオンプレミスでホストされているユーザーはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-247">Users hosted on-premises using Skype for Business Server 2015, Lync Server 2013 and 2010 aren't supported.</span></span><br/>

     *    <span data-ttu-id="8a0dd-248">**通話キュー** 別の通話キューを選択するには、まずその通話キューを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-248">>  Users hosted on-premises using Skype for Business Server 2015 and Lync Server 2013 and 2010 aren't supported.          **Call Queue** You must have already created another call queue, but after you do, then you can select that call queue.</span></span>
     *    <span data-ttu-id="8a0dd-249">**自動応答** 自動応答を選択するには、まずその自動応答を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-249">**Auto Attendant** You must have already created an auto attendant, but after you do, then you can select that auto attendant. SeeSet up a Cloud PBX auto attendant.</span></span> <span data-ttu-id="8a0dd-250">[「電話システムの自動応答を設定する」](set-up-a-phone-system-auto-attendant.md)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-250">[Set up a Phone System auto attendant](set-up-a-phone-system-auto-attendant.md)</span></span>
   
## <a name="changing-the-users-caller-id-to-be-a-call-queues-phone-number"></a><span data-ttu-id="8a0dd-251">ユーザーの発信者番号通知を通話キューの電話番号に変更する</span><span class="sxs-lookup"><span data-stu-id="8a0dd-251">Changing the user's Caller ID to be a call queue's phone number</span></span>

<span data-ttu-id="8a0dd-252">**New-CallingLineIdentity** コマンドレットを使用してポリシーを作成する代わりに、アウトバウンドコールの発信者番号通知を通話キューに変更することでユーザーIDを保護します。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-252">You can protect a user's identity by changing their caller ID for the outbound calls to a call queue instead by creating a policy using the **New-CallingLineIdentity** cmdlet.</span></span>
  
<span data-ttu-id="8a0dd-253">これを行う場合は、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-253">To do this, run:</span></span>
  
```
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

<span data-ttu-id="8a0dd-254">**Grant-CallingLineIdentity** コマンドレットを使用してユーザーのポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-254">Then apply the policy to the user using the **Grant-CallingLineIdentity** cmdlet.</span></span> <span data-ttu-id="8a0dd-255">これを行う場合は、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-255">To do this, run:</span></span>
  
```
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

<span data-ttu-id="8a0dd-256">組織内の発信者番号通知の変更方法の詳細については、 [こちら](../what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization.md)です。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-256">You can get more information on how to make changes to caller ID settings in your organization [here](../what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
## <a name="want-to-know-more"></a><span data-ttu-id="8a0dd-257">詳細情報</span><span class="sxs-lookup"><span data-stu-id="8a0dd-257">Want to know more?</span></span>

<span data-ttu-id="8a0dd-258">Windows PowerShell を使用して通話キューを作成し、設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-258">You can also use Windows PowerShell to create and set up call queues.</span></span>
  
### <a name="call-queue-cmdlets"></a><span data-ttu-id="8a0dd-259">通話キューのコマンドレット</span><span class="sxs-lookup"><span data-stu-id="8a0dd-259">Call queue cmdlets</span></span>

<span data-ttu-id="8a0dd-260">通話キューの管理で必要なコマンドレットを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-260">Here are the cmdlets that you need to manage a call queue.</span></span>
  
- [<span data-ttu-id="8a0dd-261">New--CsHuntgroup</span><span class="sxs-lookup"><span data-stu-id="8a0dd-261">New-CsHuntgroup</span></span>](https://technet.microsoft.com/en-us/library/mt796459.aspx)
    
- [<span data-ttu-id="8a0dd-262">Set-CsHuntgroup</span><span class="sxs-lookup"><span data-stu-id="8a0dd-262">Set-CsHuntgroup</span></span>](https://technet.microsoft.com/en-us/library/mt796457.aspx)
    
- [<span data-ttu-id="8a0dd-263">Get-CsHuntgroup</span><span class="sxs-lookup"><span data-stu-id="8a0dd-263">Get-CsHuntgroup</span></span>](https://technet.microsoft.com/en-us/library/mt796458.aspx)
    
- [<span data-ttu-id="8a0dd-264">Remove-CsHuntgroup</span><span class="sxs-lookup"><span data-stu-id="8a0dd-264">Remove-CsHuntgroup</span></span>](https://technet.microsoft.com/en-us/library/mt796456.aspx)
    
### <a name="more-about-windows-powershell"></a><span data-ttu-id="8a0dd-265">Windows PowerShell の詳細について</span><span class="sxs-lookup"><span data-stu-id="8a0dd-265">More about Windows PowerShell</span></span>

- <span data-ttu-id="8a0dd-266">Windows PowerShell は、ユーザーと、ユーザーが実行できる作業範囲を管理します。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-266">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="8a0dd-267">Windows PowerShell を利用すると、Office 365 と Skype for Business Online の管理を 1 か所で行うことができるので、複数のタスクを担当する管理者の日常業務を単純化できます。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-267">With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="8a0dd-268">Windows PowerShell の使用を開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-268">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="8a0dd-269">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="8a0dd-269">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="8a0dd-270">Office 365 PowerShell をお使いいただく理由</span><span class="sxs-lookup"><span data-stu-id="8a0dd-270">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="8a0dd-p129">Windows PowerShell には、ただ Office 365 管理センターを使用するだけではなく、速度、単純さ、生産性において多くの利点があります。次のトピックでこれらの利点について説明します。</span><span class="sxs-lookup"><span data-stu-id="8a0dd-p129">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="8a0dd-273">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="8a0dd-273">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="8a0dd-274">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="8a0dd-274">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="8a0dd-275">クイック リファレンス: Windows PowerShell を使用した一般的な Lync Online の管理タスクの実行</span><span class="sxs-lookup"><span data-stu-id="8a0dd-275">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="8a0dd-276">関連トピック</span><span class="sxs-lookup"><span data-stu-id="8a0dd-276">Related topics</span></span>
[<span data-ttu-id="8a0dd-277">Office 365 の電話システムで利用できる機能</span><span class="sxs-lookup"><span data-stu-id="8a0dd-277">Here's what you get with Phone System in Office 365</span></span>](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[<span data-ttu-id="8a0dd-278">Skype for Business および Microsoft Teams のサービス電話番号の取得</span><span class="sxs-lookup"><span data-stu-id="8a0dd-278">Getting service phone numbers for Skype for Business and Microsoft Teams</span></span>](getting-service-phone-numbers.md)

[<span data-ttu-id="8a0dd-279">国および地域ごとの電話会議および通話プランの利用可能性</span><span class="sxs-lookup"><span data-stu-id="8a0dd-279">Country and region availability for Audio Conferencing and Calling Plans</span></span>](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

  
 
