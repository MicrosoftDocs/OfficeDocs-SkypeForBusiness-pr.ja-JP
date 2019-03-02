---
title: 電話システムの呼び出しキューを作成する
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: phans, wasseemh
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
- Strat_SB_PSTN
- M365-voice
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Learn how to set up phone system for Office 365 (Cloud PBX) call queues to give you an organizational greeting, music on hold, and redirecting calls to call agents in distribution lists and security groups. You can also set the maximum queue size, time out, and call handling options.
ms.openlocfilehash: 59054c1d73e002065db00ff1045ed8453fafa929
ms.sourcegitcommit: 59eda0c17ff39a3e6632810391d78bbadc214419
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/01/2019
ms.locfileid: "30351691"
---
# <a name="create-a-phone-system-call-queue"></a><span data-ttu-id="ec5b8-104">電話システムの呼び出しキューを作成する</span><span class="sxs-lookup"><span data-stu-id="ec5b8-104">Create a Phone System call queue</span></span>

<span data-ttu-id="ec5b8-105">電話システム キューには、保留中の呼び出しを自動的に配置する機能などを検索する人の中に呼び出しを処理するために次の呼び出しを使用可能なエージェントの機能の電話番号への呼び出し際に使用するあいさつ文が含まれています。呼び出しが保留中の音楽をリッスンしています。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-105">Phone System call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold.</span></span> <span data-ttu-id="ec5b8-106">組織の 1 つまたは複数の呼び出しキューを作成します。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-106">You can create single or multiple call queues for your organization.</span></span>
  
<span data-ttu-id="ec5b8-107">電話システムの通話キューは次の機能を提供します:</span><span class="sxs-lookup"><span data-stu-id="ec5b8-107">Phone System call queues can provide:</span></span>
  
- <span data-ttu-id="ec5b8-108">組織の応答メッセージ。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-108">An organizational greeting.</span></span>
- <span data-ttu-id="ec5b8-109">通話の保留中に再生される保留音。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-109">Music while people are waiting on hold.</span></span>
- <span data-ttu-id="ec5b8-110">メールが有効な配布リストおよびセキュリティ グループ内のエージェントを呼び出しへの呼び出しをリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-110">Redirecting of calls to call agents in mail-enabled distribution lists and security groups.</span></span>
- <span data-ttu-id="ec5b8-111">呼び出しキューの最大サイズ、タイムアウト、および呼び出しの処理オプションの設定を行っています。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-111">Making settings for call queue maximum size, timeout, and call handling options.</span></span>

<span data-ttu-id="ec5b8-112">あいさつのメッセージを聞くを呼び出し、[リソース アカウント](manage-resource-accounts.md)を使用してキューに関連付けられている電話番号呼び出し、(いずれかの設定されている) 場合、その後に、キューを保存して、次の呼び出しを使用可能なエージェントを待機します。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-112">When someone calls in to a phone number that is associated  with a call queue via a [resource account](manage-resource-accounts.md), they will hear a greeting first (if any is set up), and then they will be put in the queue and wait for the next available call agent.</span></span> <span data-ttu-id="ec5b8-113">待機中、保留中であるし、呼び出し*最初に、先入れ先出し*(FIFO) の順序で呼び出しエージェントに提供するときに、相手呼び出しは音楽を聞きます。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-113">The person calling in will hear music while they are on hold waiting, and the calls will be offered to the call agents in *First In, First Out* (FIFO) order.</span></span>
  
<span data-ttu-id="ec5b8-114">キューで待機しているすべての呼び出しは、アテンダントのルーティング モードまたはシリアル ルーティング モードを使用して配布されます。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-114">All calls waiting in the queue will be distributed using an attendant routing mode or serial routing mode:</span></span>
  
- <span data-ttu-id="ec5b8-115">応答のルーティングでは、キュー内の最初の呼び出しを同時にすべてのエージェントが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-115">With attendant routing, the first call in the queue will ring all agents at the same time.</span></span>
- <span data-ttu-id="ec5b8-116">シリアル・ルーティングでは、キュー内の最初の呼び出しがすべてのコールエージェントを一件ずつ呼び出します。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-116">With serial routing, the first call in the queue will ring all call agents one by one.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ec5b8-117">**オフライン**中のコールエージェントは、 **取り込み中** のプレゼンスを設定するか、通話キューからの呼び出しをオプトアウトしてください。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-117">Call agents who are **Offline**, have set their presence to **Do not Disturb,** or have opted out of the call queue won't be called.</span></span>
  
- <span data-ttu-id="ec5b8-118">一度に 1 回のみの着信通知 (キューの最初にある通話) がコール エージェントに送信されます。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-118">Only one incoming call notification (for the call at the head of the queue) at a time will be sent to the call agents.</span></span>
- <span data-ttu-id="ec5b8-119">コール エージェントが通話を受けると、キューにある次の着信がコール エージェントを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-119">After a call agent accepts the call, the next incoming call in the queue will start ringing call agents.</span></span>

> [!NOTE]
> <span data-ttu-id="ec5b8-120">この資料は、オンライン ビジネスは、マイクロソフトのチームと Skype の両方に適用されます。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-120">This article applies to both Microsoft Teams and Skype for Business Online.</span></span>

## <a name="step-1---getting-started"></a><span data-ttu-id="ec5b8-121">ステップ 1 - はじめに</span><span class="sxs-lookup"><span data-stu-id="ec5b8-121">Step 1 - Getting started</span></span>

<span data-ttu-id="ec5b8-122">通話キューを使用する場合は、次の重要な点について留意してください。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-122">To get started using call queues, it's important to remember a few things:</span></span>
  
- <span data-ttu-id="ec5b8-123">組織は、エンタープライズの E3 と**電話システム**のライセンスまたはエンタープライズ E5 のライセンス (最低) が必要です。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-123">Your organization must have (at a minimum) an Enterprise E3 plus **Phone System** license or an Enterprise E5 license.</span></span> <span data-ttu-id="ec5b8-124">キューの呼び出しに使用する利用可能なサービス番号の番号を割り当てられている**電話システム**のユーザー ライセンスの数に影響します。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-124">The number of **Phone System** user licenses that are assigned affects the number of service numbers that are available to be used for call queues.</span></span> <span data-ttu-id="ec5b8-125">呼び出しキューを持つことができます数は、組織に割り当てられている**電話システム**および**オーディオ会議**のライセンスの数に依存しています。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-125">The number of call queues you can have is dependent on the number of **Phone System** and **Audio Conferencing** licenses that are assigned in your organization.</span></span> <span data-ttu-id="ec5b8-126">ライセンスに関する詳細については、 [Skype](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-126">To learn more about licensing, see [Skype for Business and Microsoft Teams add-on licensing](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>

    > [!NOTE]
    > <span data-ttu-id="ec5b8-127">オンラインにいる人が、組織内への呼び出しをリダイレクトするには、エンタープライズ VoIP を有効にするし、Office 365 のプランを呼び出すことがある、**電話システム**のライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-127">To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="ec5b8-128">[ビジネスおよびマイクロソフトのチームのライセンスを Skype を割り当てる](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-128">See  [Assign Skype for Business and Microsoft Teams licenses](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span> <span data-ttu-id="ec5b8-129">エンタープライズ VoIP を有効にするには、Windows PowerShell を使用できます。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-129">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="ec5b8-130">たとえば、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-130">For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>
  
- <span data-ttu-id="ec5b8-131">Office 365通話プランの詳細については、「[Office 365 通話プランと何ですか？](what-are-calling-plans-in-office-365.md)」及び「[Office 365の通話プラン](calling-plans-for-office-365.md)」をご覧下さい。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-131">To learn more about Office 365 Calling Plans, see [What are Calling Plans in Office 365?](what-are-calling-plans-in-office-365.md) and [Calling Plans for Office 365](calling-plans-for-office-365.md).</span></span>

    > [!NOTE]
    > <span data-ttu-id="ec5b8-132">ユーザーには、設置がホストされている呼び出しキュー エージェントとしては、Lync Server 2010 を使用してがサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-132">Users hosted on-premises using Lync Server 2010 aren't supported as a call queue Agents.</span></span>
  
- <span data-ttu-id="ec5b8-133">有料電話番号と**マイクロソフトのチーム管理センター**でまたは別のサービス プロバイダーからの呼び出しの電話システムのキューに転送する電話番号をフリー ダイヤル サービスをのみ割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-133">You can only assign toll and toll-free service phone numbers that you got in the **Microsoft Teams admin center** or transferred from another service provider to Phone System call queues.</span></span> <span data-ttu-id="ec5b8-134">取得し、サービスのフリー ダイヤル番号を使用して、通信のクレジットを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-134">To get and use toll-free service numbers, you need to set up Communications Credits.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ec5b8-135">ユーザー (購読者) の電話番号を通話キューに割り当てることはできません。サービスの有料電話番号または無料電話番号のみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-135">User (subscriber) phone numbers can't be assigned to call queues - only service toll or toll-free phone numbers can be used.</span></span>
  
- <span data-ttu-id="ec5b8-136">電話システム呼び出しキューからの着信呼び出しを配布するときは、コール エージェントのこれらのクライアントがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-136">When you are distributing the incoming calls from an Phone System call queue, these clients are supported for call agents:</span></span>

  - <span data-ttu-id="ec5b8-137">Skype for Business デスクトップ クライアント 2016 (32 および 64 ビット バージョン)</span><span class="sxs-lookup"><span data-stu-id="ec5b8-137">Skype for Business desktop client 2016 (32 and 64-bit versions)</span></span>

  - <span data-ttu-id="ec5b8-138">Lync デスクトップ クライアント 2013 (32 および 64 ビット バージョン)</span><span class="sxs-lookup"><span data-stu-id="ec5b8-138">Lync desktop client 2013 (32 and 64-bit versions)</span></span>

  - <span data-ttu-id="ec5b8-139">マイクロソフトのチームでサポートされているすべての IP 電話モデル。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-139">All IP phone models supported for Microsoft Teams.</span></span> <span data-ttu-id="ec5b8-140">[ビジネス オンラインの Skype の電話を取得](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-140">See [Getting phones for Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online.md).</span></span>

  - <span data-ttu-id="ec5b8-141">Mac版  Skype for Business クライアント (バージョン 16.8.196 以降)</span><span class="sxs-lookup"><span data-stu-id="ec5b8-141">Mac Skype for Business Client (version 16.8.196 and later)</span></span>

  - <span data-ttu-id="ec5b8-142">Aandroid Skype for Business クライアント (バージョン 6.16.0.9 以降)</span><span class="sxs-lookup"><span data-stu-id="ec5b8-142">Android Skype for Business Client (version 6.16.0.9 and later)</span></span>

  - <span data-ttu-id="ec5b8-143">iPhone Skype for Business Client クライアント(バージョン 6.16.0 以降)</span><span class="sxs-lookup"><span data-stu-id="ec5b8-143">iPhone Skype for Business Client (version 6.16.0 and later)</span></span>

  - <span data-ttu-id="ec5b8-144">Mac版  Skype for Business クライアント (バージョン 6.16.0 以降)</span><span class="sxs-lookup"><span data-stu-id="ec5b8-144">iPad Skype for Business Client (version 6.16.0 and later)</span></span>

  - <span data-ttu-id="ec5b8-145">Microsoft Teams Windows クライアント (バージョン 32 および 64 ビット)</span><span class="sxs-lookup"><span data-stu-id="ec5b8-145">Microsoft Teams Windows client (32 and 64-bit versions)</span></span>

  - <span data-ttu-id="ec5b8-146">Microsoft Teams Mac クライアント</span><span class="sxs-lookup"><span data-stu-id="ec5b8-146">Microsoft Teams Mac client</span></span>

  - <span data-ttu-id="ec5b8-147">マイクロソフト チームの iPhone アプリ</span><span class="sxs-lookup"><span data-stu-id="ec5b8-147">Microsoft Teams iPhone app</span></span>

  - <span data-ttu-id="ec5b8-148">マイクロソフト チーム Android アプリ</span><span class="sxs-lookup"><span data-stu-id="ec5b8-148">Microsoft Teams Android app</span></span>

## <a name="step-2---getting-or-transferring-toll-or-toll-free-service-phone-numbers"></a><span data-ttu-id="ec5b8-149">ステップ 2 - 有料またはフリーダイヤルのサービス電話番号の取得または移行</span><span class="sxs-lookup"><span data-stu-id="ec5b8-149">Step 2 - Getting or transferring toll or toll-free service phone numbers</span></span>

<span data-ttu-id="ec5b8-150">通話キューを作成し設定する前に、既存の有料または無料のサービス番号を取得もしくは転送する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-150">Before you can create and set up your call queues, you will need to get or transfer your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="ec5b8-151">有料または無料のサービスの電話番号を取得した後表示されます**マイクロソフトのチーム管理センター**の > **音声** > **の電話番号**、および記述されている**数値型**は、**サービスのフリー ダイヤル**として一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-151">After you get the toll or toll-free service phone numbers, they will show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="ec5b8-152">サービス番号を取得するには、[取得サービスの電話番号](/skypeforbusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers.md)を参照するか、既存のサービス番号に転送する場合は、 [Office 365 に転送電話の番号](transfer-phone-numbers-to-office-365.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-152">To get your service numbers, see [Getting service phone numbers](/skypeforbusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers.md) or if you want to transfer an existing service number, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="ec5b8-153">米国以外のユーザーは、サービス番号を取得するマイクロソフトのチームの管理センターを使うことはできません。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-153">If you are outside the United States, you can't use the Microsoft Teams admin center to get service numbers.</span></span> <span data-ttu-id="ec5b8-154">[組織の電話番号を管理](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)する代わりに、米国の外側から行う方法を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-154">Go to [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) instead to see how to do it from the outside of the United States.</span></span>

<span data-ttu-id="ec5b8-155">設定する場合も自動応答をメインの自動アテンダントのリソースのアカウントに電話番号を割り当てると、直接の呼び出し元、呼び出しキューに必要がありますだけです。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-155">If you are also setting up auto attendants, you may only need to assign a phone number to the main auto attendant's resource account, and then have it direct callers to your call queue.</span></span> <span data-ttu-id="ec5b8-156">この場合は、呼び出しキュー呼び出しキューを選択する自動応答のオプションを作成する前に作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-156">If that's the case, the call queue will need to be created before you can create an option in the auto attendant that selects the call queue.</span></span>
  
## <a name="step-3---create-a-new-call-queue"></a><span data-ttu-id="ec5b8-157">手順 3 - 新しい呼び出しキューを作成します。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-157">Step 3 - Create a new call queue</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ec5b8-158">呼び出しのすべてのキューは、関連付けられている[リソースのアカウント](manage-resource-accounts.md)を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-158">Every call queue is required to have an associated [resource account](manage-resource-accounts.md).</span></span> <span data-ttu-id="ec5b8-159">最初に、リソース アカウントを作成する必要がありますし、呼び出しのキューに関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-159">You must create the resource account first, then you can associate it to the call queue.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="ec5b8-160">マイクロソフトのチーム管理センターを使用してください。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-160">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="ec5b8-161">で**マイクロソフトのチーム管理センター**、**音声** >  **キューを呼び出す**には、 **+ 新規追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-161">In the **Microsoft Teams admin center**, **Voice** >  **Call queues**, then click **+ Add new**:</span></span>

### <a name="set-the-call-queue-display-name-and-resource-account"></a><span data-ttu-id="ec5b8-162">呼び出しキューの表示名とリソース アカウントを設定します。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-162">Set the call queue display name and resource account</span></span>

![Setting up a call queue.](media/37ecc300-a108-4294-8463-fce570dfce72.png)

* * *

<span data-ttu-id="ec5b8-164">![1](media/sfbcallout1.png)
**名**呼び出しキューの説明的な表示名を入力します。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-164">![Number 1](media/sfbcallout1.png)
**Name** Enter a descriptive display name for the call queue.</span></span> <span data-ttu-id="ec5b8-165">この項目は必須で、空白を含む最大 64 文字を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-165">This is required and can contain up to 64 characters, including spaces.</span></span>

 <span data-ttu-id="ec5b8-166">この名前は着信の通知に表示されます。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-166">This name will be displayed in the notification for the incoming call.</span></span>

* * *

![ナンバー 2](media/sfbcallout2.png)

<span data-ttu-id="ec5b8-168">**アカウントを追加します。** リソース アカウントを選択します。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-168">**Add Accounts** Select a resource account.</span></span> <span data-ttu-id="ec5b8-169">リソース アカウントは、有料のサービスや、呼び出しキューの無料電話番号に関連付けられていない場合がありますが、各呼び出しキューに関連付けられているリソース アカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-169">The resource account may or may not be associated with a service toll or toll-free phone number for the call queue, but each call queue requires an associated resource account.</span></span>

<span data-ttu-id="ec5b8-170">いずれかを使用する必要がある場合は、一覧に表示する必要がありますサービスの番号を取得し、割り当てるリソース アカウントに、この呼び出しキューを作成する前に前述のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-170">If there aren't any listed, you need to get service numbers and assign them to a Resource account before you can create this call queue, as described earlier.</span></span> <span data-ttu-id="ec5b8-171">サービス番号を取得するには、[サービスの電話番号の取得](/skypeforbusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-171">To get your service numbers, see [Getting service phone numbers](/skypeforbusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers.md).</span></span> <span data-ttu-id="ec5b8-172">に従って[チームにリソース アカウントを管理](manage-resource-accounts.md)する場合は、呼び出しのキューに関連付けられている電話番号は、リソース アカウントを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-172">You'll need to create a resource account as described in [Manage resource accounts in Teams](manage-resource-accounts.md) if you want your call queue to have an associated phone number.</span></span>

> [!NOTE]
> <span data-ttu-id="ec5b8-173">**ドメイン**を割り当てる必要のある場合で行う呼び出しキューのリソース アカウントに割り当てるとします。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-173">If you want or need to assign a **Domain** you would do so by assigning it to the resource account for the call queue.</span></span>

### <a name="set-the-greeting-and-music-played-while-on-hold"></a><span data-ttu-id="ec5b8-174">応答メッセージおよび保留中の保留音を設定する</span><span class="sxs-lookup"><span data-stu-id="ec5b8-174">Set the greeting and music played while on hold</span></span>

![Setting up a call queue.](media/1d395a93-7cab-4178-9295-12d5379e20de.png)
  
* * *

![1](media/sfbcallout1.png)

<span data-ttu-id="ec5b8-177">**応答メッセージ**は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-177">**Greeting** is optional.</span></span> <span data-ttu-id="ec5b8-178">これは、応答メッセージが、キューの番号に電話通話する相手を再生します。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-178">This is the greeting that is played for people who call in to the call queue number.</span></span>

<span data-ttu-id="ec5b8-179">オーディオ ファイル (.wav、.mp3、.wma 形式) をアップロードすることができます。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-179">You can upload an audio file (.wav, .mp3, or .wma formats).</span></span>

![ナンバー 2](media/sfbcallout2.png)

<span data-ttu-id="ec5b8-181">**上の音楽を保持**呼び出しキューで提供されている保留中のデフォルトの音楽を使用するか、または保留中のカスタムの音楽として使用する .wav、mp3、または .wma ファイルの形式でのオーディオ ファイルをアップロードすることができます。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-181">**Music on hold** You can either use the default Music on Hold provided with the call queue, or you can upload an audio file in .wav, mp3, or .wma formats to use as your custom Music on Hold.</span></span>

* * *

### <a name="select-the-call-answering-options"></a><span data-ttu-id="ec5b8-182">呼び出しへの応答のオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-182">Select the call answering options</span></span>

![着信分配メソッドのオプションを表示する](media/5d249515-d532-4af2-90da-011404028b89.png)

![1](media/sfbcallout1.png)

<span data-ttu-id="ec5b8-185">指定されたメーリング リストまたはグループに属する 200 人までのコール エージェントを選択します。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-185">You can select up to 200 call agents belonging to specified mailing lists or groups.</span></span> <span data-ttu-id="ec5b8-186">コール エージェントは、いずれかの方法である必要があります。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-186">Call agents must be either:</span></span>

- <span data-ttu-id="ec5b8-187">**電話システム** のライセンスを持つオンラインのユーザーとして、エンタープライズ ボイスまたは 通話の計画を有効にします。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-187">An Online user with a **Phone System** license and enabled for Enterprise Voice or with a Calling Plan.</span></span>

  > [!NOTE]
  > <span data-ttu-id="ec5b8-188">オンラインにいる人が、組織内への呼び出しをリダイレクトするのには、**電話システム**のライセンスが必要しエンタープライズ VoIP を有効にすることも計画を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-188">To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have a Calling Plan.</span></span> <span data-ttu-id="ec5b8-189">「[Skype for Business と Microsoft Teams のライセンスを割り当てる](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-189">See [Assign Skype for Business and Microsoft Teams licenses](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>

 <span data-ttu-id="ec5b8-190">エンタープライズ VoIP を有効にするには、Windows PowerShell を使用できます。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-190">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="ec5b8-191">たとえば、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-191">For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

- <span data-ttu-id="ec5b8-192">**電話システム** ライセンスおよび通話プランを取得しているオンラインユーザーは、計画を呼び出すと、Office 365 グループ、有効なメールの分配リスト、またはセキュリティ グループに追加されます。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-192">Online users with a **Phone System** license and a Calling Plan that are added to an Office 365 Group, a mail-enabled Distribution List, or a Security Group.</span></span> <span data-ttu-id="ec5b8-193">分配リストまたはセキュリティグループに追加された新しいエージェントは、通話キューからの受信を開始するのには最大 30 分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-193">It might take up to 30 minutes for a new agent added for a distribution list or a security group to start receiving calls from a call queue.</span></span> <span data-ttu-id="ec5b8-194">新しく作成した分配リストまたはセキュリティ グループでは、通話キューで使用可能になるまで最大で48時間を要する場合があります。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-194">A newly created distribution list or security group might take up to 48 hours to become available to be used with call queues.</span></span> <span data-ttu-id="ec5b8-195">新しく作成された Office 365 グループは、ほぼ瞬時にご利用可能です。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-195">Newly created Office 365 Groups are available almost immediately.</span></span>

  > [!NOTE]
  > <span data-ttu-id="ec5b8-196">ユーザーには、設置がホストされている Lync Server 2010 の使用はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-196">Users hosted on-premises using Lync Server 2010 aren't supported.</span></span>

![Set up call queues.](media/skype-for-business-add-agents-to-call-queue.png)

![ナンバー 2](media/sfbcallout2.png)

<span data-ttu-id="ec5b8-199">**ルーティングの方法**呼び出しキューの配布方法を**アテンダント**、**シリアル**、または**ラウンド ロビン方式**を選択できます。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-199">**Routing method** You can choose either **Attendant**,  **Serial**, or **Round Robin** for your call queue distribution method.</span></span> <span data-ttu-id="ec5b8-200">新規および既存のすべての通話キューは、応答のルーティングが既定値で選択されます。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-200">All new and existing call queues will have attendant routing selected by default.</span></span> <span data-ttu-id="ec5b8-201">応答のルーティングを使用すると、キューの最初の呼び出しはリング コール エージェントのすべてを同時に。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-201">When attendant routing is used, the first call in the queue will ring all of the call agents at the same time.</span></span> <span data-ttu-id="ec5b8-202">呼び出しを取得する最初の呼び出しエージェントは、呼び出しを取得します。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-202">The first call agent to pick up the call gets the call.</span></span>

- <span data-ttu-id="ec5b8-203">**応答ルーティング**の呼び出しのすべてのエージェントを同時にリングにキュー内の最初の呼び出しが発生します。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-203">**Attendant routing** causes the first call in the queue to ring all call agents at the same time.</span></span> <span data-ttu-id="ec5b8-204">呼び出しを取得する最初の呼び出しエージェントは、呼び出しを取得します。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-204">The first call agent to pick up the call gets the call.</span></span>
- <span data-ttu-id="ec5b8-205">**シリアル ルーティング**着信呼び出しエージェントによって 1 つのコール エージェント] ボックスの一覧の先頭から開始するのには、着信呼び出しが発生します。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-205">**Serial routing** causes incoming calls to ring call agents one by one, starting from the beginning of the call agent list.</span></span> <span data-ttu-id="ec5b8-206">エージェントが退出中、または応答しない場合、リスト上の次のエージェントを呼び出し、キューで待機中の発信が応答するかタイムアウトになるまで、すべてのエージェントの呼び出しを 1 件ずつ試みます。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-206">If an agent dismisses or does not pick up a call, the call will ring the next agent on the list and will try all agents one by one until it is picked up or times out waiting in the queue.</span></span>
  > [!NOTE]
  > <span data-ttu-id="ec5b8-207">**オフライン**中、**取り込み中**表示、またはこのキューからの着信を **オプトアウト** したエージェントは、シリアルルーティングからスキップされます。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-207">Serial routing will skip agents who are **Offline**, have set their presence to **Do not Disturb**, or have **opted out** of getting calls from this queue.</span></span>
- <span data-ttu-id="ec5b8-208">**ラウンド ロビン方式**では、各担当者は、キューから同じ呼び出しの数を取得できるように、着信通話のルーティングを分散します。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-208">**Round robin** balances routing of incoming calls so that each call agent will get the same number of calls from the queue.</span></span> <span data-ttu-id="ec5b8-209">着信呼び出しのすべてのエージェントの間で平等な機会を確保するために販売環境で非常に望ましいことがあります。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-209">This may be very desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

### <a name="select-an-agent-opt-out-option"></a><span data-ttu-id="ec5b8-210">エージェントのオプトアウトのオプションを選択する</span><span class="sxs-lookup"><span data-stu-id="ec5b8-210">Select an agent opt out option</span></span>

![オプトアウトするエージェントのチェック ボックスの表示](media/99279eff-db61-4acf-9b62-64be84b6414b.png)
  
* * *

![ナンバー 1](media/sfbcallout1.png)

<span data-ttu-id="ec5b8-213">**エージェント オプトアウト オプション** **エージェントのオプトアウト オプション**選択して特定のキューからの着信をオプトアウトすることができます。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-213">**Agent Opt out option** You can choose to allow call queue agents to opt out of taking calls from a particular queue by selecting **Agent Opt out option**.</span></span>

<span data-ttu-id="ec5b8-214">このオプションを有効にすると、このキュー内のすべてのエージェントを開始または停止するのには、この呼び出しキューからの呼び出しを受信するには使用できます。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-214">Enabling this option allows all agents in this queue to start or stop receiving calls from this call queue at will.</span></span> <span data-ttu-id="ec5b8-215">チェックボックスの削除することによっていつでもオプトアウトの取消しが可能で、オプトアウトされたエージェントはこの通話キューへ自動的にもう一度オプトインされます。 (すべてのエージェントの初期設定)</span><span class="sxs-lookup"><span data-stu-id="ec5b8-215">You can revoke the agent opt-out privilege at any time by clearing the check box, causing agents to become automatically opted in for this queue again (the default setting for all agents).</span></span>

<span data-ttu-id="ec5b8-216">エージェントは次の操作を行うと、オプトアウトのオプションにアクセスできます:</span><span class="sxs-lookup"><span data-stu-id="ec5b8-216">To access the opt-out option, agents can do the following:</span></span>

 1. <span data-ttu-id="ec5b8-217">Skype for Business クライアントデスクトップで、 **オプション** を開きます。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-217">Open **Options** in their desktop Skype for Business client.</span></span>
 2. <span data-ttu-id="ec5b8-218">**[通話転送]** タブで、 **[オンライン編集の設定]** リンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-218">On the **Call Forwarding** tab, click the **Edit settings online** link.</span></span>
 3. <span data-ttu-id="ec5b8-219">ユーザー設定ページで、 **通話キュー**をクリックし、次にオプトアウトしたいキューのチェック ボックスを削除します。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-219">On the user settings page, click **Call Queues**, and then clear the check boxes for any queues for which they want to opt out.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ec5b8-220">Mac、モバイル、または Lync 2013 クライアントを使用しているエージェント、または Skype for Business 2015 サーバーを使用しているオンプレミスでホストされている Hybrid Voice ユーザーは、 [https://aka.ms/cqsettings](https://aka.ms/cqsettings) で、オプトアウトのオプションにアクセスすることができます。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-220">Agents using Mac, mobile, or Lync 2013 clients, or Hybrid Voice users who are hosted on-premises using Skype for Business 2015 server, can go to [https://aka.ms/cqsettings](https://aka.ms/cqsettings) to access the opt out option.</span></span>

<span data-ttu-id="ec5b8-221">![2](media/sfbcallout2.png)
**エージェント ・ アラートの設定**</span><span class="sxs-lookup"><span data-stu-id="ec5b8-221">![Number 2](media/sfbcallout2.png)
**Agent Alert setting**</span></span>

<span data-ttu-id="ec5b8-222">これはシリアル ポートの前に呼び出しの通知エージェントの期間を定義またはラウンド ロビンのルーティング方法は、次のエージェントに移動します。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-222">This defines the duration of an agent being notified of a call before the Serial or Round Robin routing methods move to the next agent.</span></span>

<span data-ttu-id="ec5b8-223">既定の設定は 30 秒ですが、最大 3 分間に設定できます。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-223">The default setting is 30 seconds, but it can be set for up to 3 minutes.</span></span>

* * *

### <a name="set-the-call-overflow-and-timeout-handling-options"></a><span data-ttu-id="ec5b8-224">処理オプションを使用した呼び出しのオーバーフローやタイムアウトの設定します。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-224">Set the call overflow and timeout handling options</span></span>

![Set up a call queue.](media/3f018734-16fe-458b-827d-71fc25155cde.png)
  
* * *

![1](media/sfbcallout1.png)

<span data-ttu-id="ec5b8-227">**キュー内の最大通話数** この項目を使用して、同時に通話がキュー内で待機できる最大通話数を設定します。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-227">**Maximum calls in the queue** Use this to set the maximum calls that can wait in the queue at the same time.</span></span> <span data-ttu-id="ec5b8-228">デフォルトは 50 ですが、それの範囲は 0 から 200 です。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-228">The default is 50, but it can range from 0 to 200.</span></span> <span data-ttu-id="ec5b8-229">この制限に達すると、通話は次の [ **呼び出しの最大数に達した場合**] 設定で指定した方法で処理されます。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-229">When this limit is reached, the call will be handled in way you have set on the **When the maximum number of calls is reached** setting below.</span></span>

* * *

![ナンバー 2](media/sfbcallout2.png)

<span data-ttu-id="ec5b8-231">**呼び出しの最大数に達したとき**呼び出しキューでは、(**キューの最大数を呼び出す**設定を使用して設定) の最大のサイズに達すると、新しくかかってきた呼び出しの動作を選択します。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-231">**When the maximum number of calls is reached** When the call queue reaches its maximum size (set using the **Maximum calls in the queue** setting), you can choose what happens to new incoming calls.</span></span>

- <span data-ttu-id="ec5b8-232">**切断** 通話は切断されます。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-232">**Disconnect** The call will be disconnected.</span></span>
- <span data-ttu-id="ec5b8-233">**リダイレクト**これを選択するときは、次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-233">**Redirect to** When you choose this, select one of the following:</span></span>

  - <span data-ttu-id="ec5b8-234">**社内のユーザー** **電話システム** のライセンスを持つオンラインのユーザーそしてエンタープライズ ボイス を有効にするか通話プランを取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-234">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have a Calling Plan.</span></span> <span data-ttu-id="ec5b8-235">発信中のユーザーがボイスメールに送信されるように設定できます。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-235">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="ec5b8-236">これを行うは、 **、会社の担当者**を選択し、通話をボイスメールに直接転送されるには、このユーザーを設定します。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-236">To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span>

  <span data-ttu-id="ec5b8-237">ボイスメールに必要なライセンスについては、 [「電話システムのボイスメールの設定」](set-up-phone-system-voicemail.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-237">To learn about licensing required for voicemail, see [Set up Phone System voicemail](set-up-phone-system-voicemail.md).</span></span>

    > [!Note]
    > <span data-ttu-id="ec5b8-238">ユーザーには、設置がホストされている Lync Server 2010 の使用はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-238">Users hosted on-premises using Lync Server 2010 aren't supported.</span></span>
  - <span data-ttu-id="ec5b8-239">**音声アプリケーション**呼び出しキューのいずれかの名前を選択または自動アテンダントが既に作成されています。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-239">**Voice application** Select the name of either a call queue or auto attendant that has already been created.</span></span>

* * *

![ナンバー 3](media/sfbcallout3.png)

<span data-ttu-id="ec5b8-241">**の呼び出しのタイムアウト: 最大待機時間**できます、キュー内の保留中の呼び出しにかかった時間は、前にタイムアウトし、リダイレクトするか、切断する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-241">**Call Timeout: maximum wait time** You can also decide how much time a call can be on hold in the queue before it times out and needs to be redirected or disconnected.</span></span> <span data-ttu-id="ec5b8-242">リダイレクト先は [ **通話がタイムアウトした場合**] 設定に基づきます。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-242">Where it will be redirected is based on how you set the **When a call times out** setting.</span></span> <span data-ttu-id="ec5b8-243">0 から 45 分に設定できます。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-243">You can set a time from 0 to 45 minutes.</span></span>

<span data-ttu-id="ec5b8-244">タイムアウト値は秒単位で、 15 秒間隔で設定することができます。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-244">The timeout value can be set in seconds, at 15-second intervals.</span></span> <span data-ttu-id="ec5b8-245">これにより、通話フローを細かく操作することができます。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-245">This allows you to manipulate the call flow with finer granularity.</span></span> <span data-ttu-id="ec5b8-246">たとえば、ディレクトリ検索の自動応答を 30 秒以内に、エージェントが応答しないすべての呼び出しを移動することを指定できます。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-246">For example, you could specify that any calls that are not answered by an agent within 30 seconds go to a Directory Search auto attendant.</span></span>

![ナンバー 4](media/sfbcallout4.png)

<span data-ttu-id="ec5b8-248">**呼び出しがタイムアウトしたとき**呼び出しは、**呼び出しがキューで待機できる時間**の設定で設定した制限に達すると、この呼び出しの動作を選択できます。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-248">**When call times out** When the call reaches the limit you set on the **How long a call can wait in the queue** setting, you can choose what happens to this call:</span></span>

- <span data-ttu-id="ec5b8-249">**切断** 通話は切断されます。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-249">**Disconnect** The call will be disconnected.</span></span>
- <span data-ttu-id="ec5b8-250">**呼び出しをリダイレクトします。** これを選択するとこれらのオプションが用意されます。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-250">**Redirect this call to** When you choose this, you will have these options:</span></span>
  - <span data-ttu-id="ec5b8-251">**社内のユーザー** **電話システム** のライセンスを持つオンラインユーザーで、エンタープライズ ボイス が有効化されているまたは、通話プランを取得済みである必要があります。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-251">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have Calling Plans.</span></span> <span data-ttu-id="ec5b8-252">発信中のユーザーがボイスメールに送信されるように設定できます。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-252">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="ec5b8-253">これを行うは、 **、会社の担当者**を選択し、通話をボイスメールに直接転送されるには、このユーザーを設定します。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-253">To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span>

  <span data-ttu-id="ec5b8-254">ボイスメールに必要なライセンスについては、 [「電話システムのボイスメールの設定」](set-up-phone-system-voicemail.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-254">To learn about licensing required for voicemail, see [Set up Phone System voicemail](set-up-phone-system-voicemail.md).</span></span>

    > [!Note]
    > <span data-ttu-id="ec5b8-255">ユーザーには、設置がホストされている Lync Server 2010 の使用はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-255">Users hosted on-premises using Lync Server 2010 aren't supported.</span></span>

  - <span data-ttu-id="ec5b8-256">**音声アプリケーション**呼び出しキューのいずれかの名前を選択または自動アテンダントが既に作成されています。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-256">**Voice application** Select the name of either a call queue or auto attendant that has already been created.</span></span>

## <a name="changing-a-users-caller-id-to-be-a-call-queues-phone-number"></a><span data-ttu-id="ec5b8-257">呼び出しキューの電話番号を使用するユーザーの呼び出し元の ID を変更します。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-257">Changing a user's Caller ID to be a call queue's phone number</span></span>

<span data-ttu-id="ec5b8-258">**New-CallingLineIdentity** コマンドレットを使用してポリシーを作成する代わりに、アウトバウンドコールの発信者番号通知を通話キューに変更することでユーザーIDを保護します。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-258">You can protect a user's identity by changing their caller ID for the outbound calls to a call queue instead by creating a policy using the **New-CallingLineIdentity** cmdlet.</span></span>

<span data-ttu-id="ec5b8-259">これを行う場合は、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-259">To do this, run:</span></span>

``` Powershell
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

<span data-ttu-id="ec5b8-260">**Grant-CallingLineIdentity** コマンドレットを使用してユーザーのポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-260">Then apply the policy to the user using the **Grant-CallingLineIdentity** cmdlet.</span></span> <span data-ttu-id="ec5b8-261">これを行う場合は、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-261">To do this, run:</span></span>
  
``` Powershell
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

<span data-ttu-id="ec5b8-262">[呼び出し元 ID 利用する方法、組織内](/skypeforbusiness/what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization.md)の記事で、組織内の呼び出し元 ID の設定を変更する方法の詳細を取得できます。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-262">You can get more information on how to make changes to caller ID settings in your organization in the article [How can caller ID be used in your organization](/skypeforbusiness/what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
## <a name="want-to-know-more"></a><span data-ttu-id="ec5b8-263">詳細情報</span><span class="sxs-lookup"><span data-stu-id="ec5b8-263">Want to know more?</span></span>

<span data-ttu-id="ec5b8-264">Windows PowerShell を使用して通話キューを作成し、設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-264">You can also use Windows PowerShell to create and set up call queues.</span></span>
  
### <a name="call-queue-cmdlets"></a><span data-ttu-id="ec5b8-265">通話キューのコマンドレット</span><span class="sxs-lookup"><span data-stu-id="ec5b8-265">Call queue cmdlets</span></span>

<span data-ttu-id="ec5b8-266">通話キューの管理で必要なコマンドレットを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-266">Here are the cmdlets that you need to manage a call queue.</span></span>
  
- [<span data-ttu-id="ec5b8-267">New--CsHuntgroup</span><span class="sxs-lookup"><span data-stu-id="ec5b8-267">New-CsHuntgroup</span></span>](https://technet.microsoft.com/en-us/library/mt796459.aspx)

- [<span data-ttu-id="ec5b8-268">Set-CsHuntgroup</span><span class="sxs-lookup"><span data-stu-id="ec5b8-268">Set-CsHuntgroup</span></span>](https://technet.microsoft.com/en-us/library/mt796457.aspx)

- [<span data-ttu-id="ec5b8-269">Get-CsHuntgroup</span><span class="sxs-lookup"><span data-stu-id="ec5b8-269">Get-CsHuntgroup</span></span>](https://technet.microsoft.com/en-us/library/mt796458.aspx)

- [<span data-ttu-id="ec5b8-270">Remove-CsHuntgroup</span><span class="sxs-lookup"><span data-stu-id="ec5b8-270">Remove-CsHuntgroup</span></span>](https://technet.microsoft.com/en-us/library/mt796456.aspx)

### <a name="more-about-windows-powershell"></a><span data-ttu-id="ec5b8-271">Windows PowerShell の詳細について</span><span class="sxs-lookup"><span data-stu-id="ec5b8-271">More about Windows PowerShell</span></span>

- <span data-ttu-id="ec5b8-272">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span><span class="sxs-lookup"><span data-stu-id="ec5b8-272">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="ec5b8-273">Windows PowerShell では、Office 365 と一元管理を行う複数のタスクがある場合、日常的な作業を簡素化するを使用してマイクロソフトのチームを管理できます。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-273">With Windows PowerShell, you can manage Office 365 and Microsoft Teams using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="ec5b8-274">Windows PowerShell の使用を開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-274">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="ec5b8-275">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="ec5b8-275">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [<span data-ttu-id="ec5b8-276">Windows PowerShell で Office 365 を管理するための最善の方法</span><span class="sxs-lookup"><span data-stu-id="ec5b8-276">Why you need to use Office 365 PowerShell</span></span>](https://docs.microsoft.com/en-us/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- <span data-ttu-id="ec5b8-277">Windows PowerShell には、実行しようとする設定の変更多くのユーザーを一度に 1 つなどのマイクロソフトのチーム管理センターを使用するだけでスピード、シンプルさと生産性に多くの利点があります。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-277">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft Teams admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="ec5b8-278">次のトピックでこれらの利点について説明します。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-278">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="ec5b8-279">Windows PowerShell では、Office 365 を管理します。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-279">Manage Office 365 with Windows PowerShell</span></span>](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [<span data-ttu-id="ec5b8-280">Windows PowerShell 用にコンピューターをセットアップする</span><span class="sxs-lookup"><span data-stu-id="ec5b8-280">Set up your computer for Windows PowerShell</span></span>](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a><span data-ttu-id="ec5b8-281">関連トピック</span><span class="sxs-lookup"><span data-stu-id="ec5b8-281">Related topics</span></span>

[<span data-ttu-id="ec5b8-282">Office 365 での電話システムで利用できる機能</span><span class="sxs-lookup"><span data-stu-id="ec5b8-282">Here's what you get with Phone System in Office 365</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="ec5b8-283">サービスの電話番号の取得</span><span class="sxs-lookup"><span data-stu-id="ec5b8-283">Getting service phone numbers</span></span>](/Skypeforbusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers.md)

[<span data-ttu-id="ec5b8-284">国および地域ごとの電話会議および通話プランの利用可能性</span><span class="sxs-lookup"><span data-stu-id="ec5b8-284">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="ec5b8-285">新しい-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="ec5b8-285">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
