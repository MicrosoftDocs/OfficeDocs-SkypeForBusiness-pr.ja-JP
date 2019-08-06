---
title: 呼び出しキューを作成する
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: phans, wasseemh
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Microsoft Teams でクラウド通話キューの電話システムをセットアップする方法について説明します。
ms.openlocfilehash: 887c92e398487d3e42f9fc560610683008760105
ms.sourcegitcommit: a49caec01ff724475d6670b303d851ddd8266c2c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2019
ms.locfileid: "36207183"
---
# <a name="create-a-cloud-call-queue"></a><span data-ttu-id="e9445-103">クラウドの通話キューを作成する</span><span class="sxs-lookup"><span data-stu-id="e9445-103">Create a Cloud call queue</span></span>

<span data-ttu-id="e9445-104">クラウド通話キューでは次の情報を提供できます。</span><span class="sxs-lookup"><span data-stu-id="e9445-104">Cloud call queues can provide:</span></span>
 
- <span data-ttu-id="e9445-105">あいさつメッセージ。</span><span class="sxs-lookup"><span data-stu-id="e9445-105">A greeting message.</span></span>
- <span data-ttu-id="e9445-106">通話の保留中に再生される保留音。</span><span class="sxs-lookup"><span data-stu-id="e9445-106">Music while people are waiting on hold.</span></span>
- <span data-ttu-id="e9445-107">メールが有効な配布リストとセキュリティグループでのコールエージェントへの通話のリダイレクト。</span><span class="sxs-lookup"><span data-stu-id="e9445-107">Redirecting of calls to call agents in mail-enabled distribution lists and security groups.</span></span>
- <span data-ttu-id="e9445-108">設定によって、キューの最大サイズ、タイムアウト、通話処理オプションなどのさまざまなパラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="e9445-108">Settings different parameters such as queue maximum size, timeout, and call handling options.</span></span>

<span data-ttu-id="e9445-109">他のユーザーが、[リソースアカウント](manage-resource-accounts.md)を使用して、通話キューに関連付けられている電話番号に通話を発信した場合:</span><span class="sxs-lookup"><span data-stu-id="e9445-109">When someone calls a phone number that is associated with a call queue via a [resource account](manage-resource-accounts.md):</span></span> 
1. <span data-ttu-id="e9445-110">応答メッセージ (設定されている場合) が聞こえます。</span><span class="sxs-lookup"><span data-stu-id="e9445-110">They  hear a greeting (if any is set up)</span></span> 
2. <span data-ttu-id="e9445-111">通話はキューに入れられ、次に使用可能な通話エージェントを待機します。</span><span class="sxs-lookup"><span data-stu-id="e9445-111">Their call is put in the queue to wait for the next available call agent.</span></span> 
 

<span data-ttu-id="e9445-112">発信者は、保留中の音楽を聞くことができます。通話は、*先入れ先出し*(FIFO) の順序で通話エージェントに接続します。</span><span class="sxs-lookup"><span data-stu-id="e9445-112">The caller hears music while they are on hold, and the call connects to the call agents in *First In, First Out* (FIFO) order.</span></span>
 
<span data-ttu-id="e9445-113">キュー内のすべての通話は、次のいずれかの方法でエージェントに送信されます。</span><span class="sxs-lookup"><span data-stu-id="e9445-113">All calls in the queue are sent to agents by one of the following methods:</span></span>
 
- <span data-ttu-id="e9445-114">アテンダントルーティングを使用すると、キューの最初の呼び出しですべてのエージェントが同時に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="e9445-114">With attendant routing, the first call in the queue  rings all agents at the same time.</span></span>
- <span data-ttu-id="e9445-115">シリアルルーティングでは、キューにある最初の呼び出しによって、すべてのコールエージェントが1つずつリングされます。</span><span class="sxs-lookup"><span data-stu-id="e9445-115">With serial routing, the first call in the queue rings all call agents one by one.</span></span>
- <span data-ttu-id="e9445-116">ラウンドロビンでは、着信のルーティングが分散され、各通話エージェントがキューから同じ数の通話を取得できるようになります。</span><span class="sxs-lookup"><span data-stu-id="e9445-116">With round robin, routing of incoming calls is balanced so that each call agent gets the same number of calls from the queue.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e9445-117">**オフライン**の通話エージェントは、自分のプレゼンスが [**応答不可]** に設定されています。または、通話キューを無効にしても、通話を受けることはできません。</span><span class="sxs-lookup"><span data-stu-id="e9445-117">Call agents who are **Offline**, have set their presence to **Do not Disturb,** or have opted out of the call queue will not recieve calls.</span></span>
 
- <span data-ttu-id="e9445-118">一度に1つの着信通知 (キューの先頭にある通話用) のみが通話エージェントに送信されます。</span><span class="sxs-lookup"><span data-stu-id="e9445-118">Only one incoming call notification (for the call at the head of the queue) at a time goes to the call agents.</span></span>
- <span data-ttu-id="e9445-119">コール エージェントが通話を受けると、キューにある次の着信がコール エージェントを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="e9445-119">After a call agent accepts the call, the next incoming call in the queue will start ringing call agents.</span></span>

> [!NOTE]
> <span data-ttu-id="e9445-120">この記事は、Microsoft Teams と Skype for Business Online の両方に適用されます。</span><span class="sxs-lookup"><span data-stu-id="e9445-120">This article applies to both Microsoft Teams and Skype for Business Online.</span></span>

## <a name="step-1--get-started"></a><span data-ttu-id="e9445-121">手順 1-はじめに</span><span class="sxs-lookup"><span data-stu-id="e9445-121">Step 1 — Get started</span></span>

<span data-ttu-id="e9445-122">通話キューを使用する場合は、次の重要な点について留意してください。</span><span class="sxs-lookup"><span data-stu-id="e9445-122">To get started using call queues, it's important to remember a few things:</span></span>
 
- <span data-ttu-id="e9445-123">通話キューには、関連するリソースアカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="e9445-123">A call queue is required to have an associated resource account.</span></span> <span data-ttu-id="e9445-124">リソースアカウントの詳細については、「[チームのリソースアカウントを管理](manage-resource-accounts.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9445-124">See [Manage resource accounts in Teams](manage-resource-accounts.md) for details on resource accounts.</span></span>
- <span data-ttu-id="e9445-125">リソースアカウントに電話番号を割り当てると、無料電話システムの[仮想ユーザーライセンス](teams-add-on-licensing/virtual-user.md)を使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="e9445-125">When you assign a phone number to a resource account, you can now use the cost-free Phone System [Virtual User license](teams-add-on-licensing/virtual-user.md).</span></span> <span data-ttu-id="e9445-126">電話システムでは、低コストの自動応答と通話キューサービスを使用するために、組織レベルで電話番号を使うことができます。</span><span class="sxs-lookup"><span data-stu-id="e9445-126">Phone System allows phone numbers at the organizational level for use with low-cost auto attendant and call queue services.</span></span>

> [!NOTE]
> <span data-ttu-id="e9445-127">通話キューの直接ルーティングサービス番号は、Microsoft Teams ユーザーとエージェントに対してのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="e9445-127">Direct Routing service numbers for call queues are supported for Microsoft Teams users and agents only.</span></span>

> [!NOTE]
> <span data-ttu-id="e9445-128">インターネットに接続している組織内のユーザーに通話をリダイレクトするには、**電話システム**のライセンスが必要です。また、エンタープライズ voip に対応しているか、Office 365 の通話プランを使用している必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9445-128">To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="e9445-129">「 [Skype For business ライセンスの割り当て](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)」または「 [Microsoft Teams ライセンスの割り当て](assign-teams-licenses.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9445-129">See [Assign Skype for Business licenses](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) or [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="e9445-130">エンタープライズ VoIP を有効にするには、Windows PowerShell を使用できます。</span><span class="sxs-lookup"><span data-stu-id="e9445-130">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="e9445-131">たとえば、次のように実行します。`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="e9445-131">For example run: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>
 
- <span data-ttu-id="e9445-132">Office 365 の通話プランの詳細については、「[電話システムと通話プラン](calling-plan-landing-page.md)」および「 [Office 365 の通話プラン](calling-plans-for-office-365.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9445-132">To learn more about Office 365 Calling Plans, see [Phone System and Calling Plans](calling-plan-landing-page.md) and [Calling Plans for Office 365](calling-plans-for-office-365.md).</span></span>

- <span data-ttu-id="e9445-133">クラウド通話キューを割り当てることができるのは、 **Microsoft Teams 管理センター**で取得した、または別のサービスプロバイダーから転送された有料またはフリーダイヤルのサービス電話番号だけです。</span><span class="sxs-lookup"><span data-stu-id="e9445-133">You can only assign Cloud call queues toll and toll-free service phone numbers that you got in the **Microsoft Teams admin center** or transferred from another service provider.</span></span> <span data-ttu-id="e9445-134">無料サービス番号には、通信クレジットが必要です。</span><span class="sxs-lookup"><span data-stu-id="e9445-134">Communications Credits are required for toll-free service numbers.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e9445-135">ユーザー (購読者) の電話番号を通話キューに割り当てることはできません。サービスの有料電話番号または無料電話番号のみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="e9445-135">User (subscriber) phone numbers can't be assigned to call queues - only service toll or toll-free phone numbers can be used.</span></span>
 
- <span data-ttu-id="e9445-136">クラウドの通話キューに関連付けられた通話エージェントは、次のクライアントでサポートされます。</span><span class="sxs-lookup"><span data-stu-id="e9445-136">The following clients are supported for call agents associated to a Cloud call queue:</span></span>

  - <span data-ttu-id="e9445-137">Skype for Business デスクトップクライアント 2016 (32 ビットバージョンと64ビットバージョン)</span><span class="sxs-lookup"><span data-stu-id="e9445-137">Skype for Business desktop client 2016 (32-bit and 64-bit versions)</span></span>

  - <span data-ttu-id="e9445-138">Lync デスクトップクライアント 2013 (32 ビットバージョンと64ビットバージョン)</span><span class="sxs-lookup"><span data-stu-id="e9445-138">Lync desktop client 2013 (32-bit and 64-bit versions)</span></span>

  - <span data-ttu-id="e9445-139">Microsoft Teams でサポートされているすべての IP 電話モデル。</span><span class="sxs-lookup"><span data-stu-id="e9445-139">All IP phone models supported for Microsoft Teams.</span></span> <span data-ttu-id="e9445-140">「 [Skype For Business Online の電話を取得する」を](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online)参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9445-140">See [Getting phones for Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span></span>

  - <span data-ttu-id="e9445-141">Mac版  Skype for Business クライアント (バージョン 16.8.196 以降)</span><span class="sxs-lookup"><span data-stu-id="e9445-141">Mac Skype for Business Client (version 16.8.196 and later)</span></span>

  - <span data-ttu-id="e9445-142">Aandroid Skype for Business クライアント (バージョン 6.16.0.9 以降)</span><span class="sxs-lookup"><span data-stu-id="e9445-142">Android Skype for Business Client (version 6.16.0.9 and later)</span></span>

  - <span data-ttu-id="e9445-143">iPhone Skype for Business Client クライアント(バージョン 6.16.0 以降)</span><span class="sxs-lookup"><span data-stu-id="e9445-143">iPhone Skype for Business Client (version 6.16.0 and later)</span></span>

  - <span data-ttu-id="e9445-144">Mac版  Skype for Business クライアント (バージョン 6.16.0 以降)</span><span class="sxs-lookup"><span data-stu-id="e9445-144">iPad Skype for Business Client (version 6.16.0 and later)</span></span>

  - <span data-ttu-id="e9445-145">Microsoft Teams Windows クライアント (32 ビット版と64ビット版)</span><span class="sxs-lookup"><span data-stu-id="e9445-145">Microsoft Teams Windows client (32-bit and 64-bit versions)</span></span>

  - <span data-ttu-id="e9445-146">Microsoft Teams Mac クライアント</span><span class="sxs-lookup"><span data-stu-id="e9445-146">Microsoft Teams Mac client</span></span>

  - <span data-ttu-id="e9445-147">Microsoft Teams iPhone アプリ</span><span class="sxs-lookup"><span data-stu-id="e9445-147">Microsoft Teams iPhone app</span></span>

  - <span data-ttu-id="e9445-148">Microsoft Teams Android アプリ</span><span class="sxs-lookup"><span data-stu-id="e9445-148">Microsoft Teams Android app</span></span>

## <a name="step-2---getting-or-transferring-toll-or-toll-free-service-phone-numbers"></a><span data-ttu-id="e9445-149">ステップ 2 - 有料またはフリーダイヤルのサービス電話番号の取得または移行</span><span class="sxs-lookup"><span data-stu-id="e9445-149">Step 2 - Getting or transferring toll or toll-free service phone numbers</span></span>

<span data-ttu-id="e9445-150">通話キューを作成して設定する前に、既存の有料または無料のサービス番号を取得または移行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9445-150">Before you can create and set up your call queues, you need to get or transfer your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="e9445-151">有料またはフリーダイヤルのサービス電話番号を取得すると、 **Microsoft Teams 管理センター** > **従来のポータル** > **ボイス** > **電話番号**に表示され、**番号の種類**は以下のようになります。**サービス-無料通話**。</span><span class="sxs-lookup"><span data-stu-id="e9445-151">After you get the toll or toll-free service phone numbers, they will show up in **Microsoft Teams admin center** > **Legacy Portal** > **Voice** > **Phone numbers**, and the **Number type** will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="e9445-152">サービス番号を取得するには、「[サービスの電話番号を取得](getting-service-phone-numbers.md)する」または「既存のサービス番号を移行する」を参照してください。「 [Office 365 に電話番号を転送](transfer-phone-numbers-to-office-365.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9445-152">To get your service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md) or if you want to transfer an existing service number, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>
 
> [!NOTE]
> <span data-ttu-id="e9445-153">米国外の場合は、Microsoft Teams 管理センターを使用してサービス番号を取得することはできません。</span><span class="sxs-lookup"><span data-stu-id="e9445-153">If you are outside the United States, you can't use the Microsoft Teams admin center to get service numbers.</span></span> <span data-ttu-id="e9445-154">「[組織の電話番号を管理](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)する」に移動して、米国以外の地域での実行方法を確認します。</span><span class="sxs-lookup"><span data-stu-id="e9445-154">Go to [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) instead to see how to do it from the outside of the United States.</span></span>

<span data-ttu-id="e9445-155">複数の自動応答を設定している場合は、電話番号をメインの自動応答のリソースアカウントに割り当てなければならない場合があります。これにより、発信者は通話キューまたは入れ子になった自動応答に転送されます。</span><span class="sxs-lookup"><span data-stu-id="e9445-155">If you are setting up multiple auto attendants, you may only need to assign a phone number to the main auto attendant's resource account, which can direct callers to your call queues or nested auto attendants.</span></span> <span data-ttu-id="e9445-156">このような場合は、ダイヤルパッドオプションを割り当てずに、システムですべての自動応答と通話キューを作成し、後で設定を編集する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9445-156">In those situations you should create all auto attendants and call queues in your system without assigning dialpad options, and then edit the settings later.</span></span> <span data-ttu-id="e9445-157">このことが必要になるのは、まだ存在していない通話キューまたは自動応答にリンクするオプションを作成できないためです。</span><span class="sxs-lookup"><span data-stu-id="e9445-157">This is necessary because you aren't allowed to create an option linking to a call queue or auto attendant that does not yet exist.</span></span>
 
## <a name="step-3---create-a-new-call-queue"></a><span data-ttu-id="e9445-158">手順 3-新しい通話キューを作成する</span><span class="sxs-lookup"><span data-stu-id="e9445-158">Step 3 - Create a new call queue</span></span>

[!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

> [!IMPORTANT]
> <span data-ttu-id="e9445-159">すべての通話キューには、[リソースアカウント](manage-resource-accounts.md)が関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9445-159">Every call queue is required to have an associated [resource account](manage-resource-accounts.md).</span></span> <span data-ttu-id="e9445-160">最初にリソースアカウントを作成してから、それを通話キューに関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="e9445-160">You must create the resource account first, then you can associate it to the call queue.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="e9445-161">Microsoft Teams 管理センターの使用</span><span class="sxs-lookup"><span data-stu-id="e9445-161">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="e9445-162">**Microsoft Teams 管理センター**の [**音声** > **通話キュー**] で、[ **+ Add new**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e9445-162">In the **Microsoft Teams admin center**, **Voice** > **Call queues**, then click **+ Add new**:</span></span>

### <a name="set-the-call-queue-display-name-and-resource-account"></a><span data-ttu-id="e9445-163">通話キューの表示名とリソースアカウントを設定する</span><span class="sxs-lookup"><span data-stu-id="e9445-163">Set the call queue display name and resource account</span></span>

![番号付き吹き出しが含まれる新しい通話キューのスクリーンショット](media/37ecc300-a108-4294-8463-fce570dfce72.png)

* * *

<span data-ttu-id="e9445-165">![番号1のアイコン、前のスクリーンショット](media/sfbcallout1.png)
**名**で吹き出しを参照する通話キューのわかりやすい表示名を入力します。</span><span class="sxs-lookup"><span data-stu-id="e9445-165">![Icon of the number 1, referencing a callout in the previous screenshot](media/sfbcallout1.png)
**Name** Enter a descriptive display name for the call queue.</span></span> <span data-ttu-id="e9445-166">この名前は必須であり、スペースなどの最大64文字を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="e9445-166">This name is required and can contain up to 64 characters, including spaces.</span></span>

 <span data-ttu-id="e9445-167">この名前は、着信通話の通知に表示されます。</span><span class="sxs-lookup"><span data-stu-id="e9445-167">This name is displayed in the notification for the incoming call.</span></span>

* * *

![前のスクリーンショットで吹き出しを参照している数値2のアイコン](media/sfbcallout2.png)

<span data-ttu-id="e9445-169">**アカウントを追加**するリソースアカウントを選択します。</span><span class="sxs-lookup"><span data-stu-id="e9445-169">**Add Accounts** Select a resource account.</span></span> <span data-ttu-id="e9445-170">リソースアカウントは、通話キューの有料または無料の電話番号と関連付けられている場合と関連付けられていない場合もありますが、各通話キューには関連するリソースアカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="e9445-170">The resource account may or may not be associated with a service toll or toll-free phone number for the call queue, but each call queue requires an associated resource account.</span></span>

<span data-ttu-id="e9445-171">リストが表示されない場合は、前に説明したように、サービス番号を取得してリソースアカウントに割り当てておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9445-171">If there aren't any listed, you need to get service numbers and assign them to a Resource account before you can create this call queue, as described earlier.</span></span> <span data-ttu-id="e9445-172">サービス番号を取得するには、「[サービスの電話番号を取得](getting-service-phone-numbers.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9445-172">To get your service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md).</span></span> <span data-ttu-id="e9445-173">通話キューに関連付けられた電話番号が必要な場合は、「 [Teams のリソースアカウントを管理](manage-resource-accounts.md)する」の説明に従ってリソースアカウントを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9445-173">You'll need to create a resource account as described in [Manage resource accounts in Teams](manage-resource-accounts.md) if you want your call queue to have an associated phone number.</span></span>

> [!NOTE]
> <span data-ttu-id="e9445-174">**ドメイン**を割り当てる必要がある場合は、それを呼び出しキューのリソースアカウントに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="e9445-174">If you want or need to assign a **Domain** you would do so by assigning it to the resource account for the call queue.</span></span>

### <a name="set-the-greeting-and-music-played-while-on-hold"></a><span data-ttu-id="e9445-175">応答メッセージおよび保留中の保留音を設定する</span><span class="sxs-lookup"><span data-stu-id="e9445-175">Set the greeting and music played while on hold</span></span>

![[応答メッセージ] と [音楽] オプションのスクリーンショット。番号付き吹き出し](media/1d395a93-7cab-4178-9295-12d5379e20de.png)
 
* * *

![前のスクリーンショットで吹き出しを参照する数値1のアイコン](media/sfbcallout1.png)

<span data-ttu-id="e9445-178">**応答メッセージ**は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="e9445-178">**Greeting** is optional.</span></span> <span data-ttu-id="e9445-179">これは、通話キュー番号にコールインした相手に対して再生される応答メッセージです。</span><span class="sxs-lookup"><span data-stu-id="e9445-179">This is the greeting that is played for people who call in to the call queue number.</span></span>

<span data-ttu-id="e9445-180">オーディオファイル (.wav、.mp3、または .wma 形式) をアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="e9445-180">You can upload an audio file (.wav, .mp3, or .wma formats).</span></span>

![前のスクリーンショットで吹き出しを参照している数値2のアイコン](media/sfbcallout2.png)

<span data-ttu-id="e9445-182">**保留中の音楽**通話キューで提供される既定の保留中の音楽を使用するか、または .wav、mp3、または .wma 形式のオーディオファイルをアップロードして、カスタム音楽を保留にすることができます。</span><span class="sxs-lookup"><span data-stu-id="e9445-182">**Music on hold** You can either use the default Music on Hold provided with the call queue, or you can upload an audio file in .wav, mp3, or .wma formats to use as your custom Music on Hold.</span></span>

* * *

### <a name="select-the-call-answering-options"></a><span data-ttu-id="e9445-183">通話応答のオプションを選択する</span><span class="sxs-lookup"><span data-stu-id="e9445-183">Select the call answering options</span></span>

![番号付き吹き出しが含まれる通話応答オプションのスクリーンショット](media/5d249515-d532-4af2-90da-011404028b89.png)

![前のスクリーンショットで吹き出しを参照する数値1のアイコン](media/sfbcallout1.png)

<span data-ttu-id="e9445-186">以下のメーリングリストまたはグループのいずれかに属する、最大200の通話エージェントを選択できます。</span><span class="sxs-lookup"><span data-stu-id="e9445-186">You can select up to 200 call agents who belong to any of the following mailing lists or groups:</span></span>

- <span data-ttu-id="e9445-187">Office 365 グループ</span><span class="sxs-lookup"><span data-stu-id="e9445-187">Office 365 group</span></span>
- <span data-ttu-id="e9445-188">セキュリティグループ</span><span class="sxs-lookup"><span data-stu-id="e9445-188">Security group</span></span>
- <span data-ttu-id="e9445-189">配布リスト</span><span class="sxs-lookup"><span data-stu-id="e9445-189">Distribution list</span></span>

<span data-ttu-id="e9445-190">選択された通話エージェントは、**電話システム**のライセンスを持つオンラインユーザーか\*\*\*\* 、エンタープライズボイスを有効にしている**か**、通話プランを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9445-190">Call agents selected must **either** be online users with a **Phone System** license and Enterprise Voice enabled **or** have a Calling Plan.</span></span>

  > [!NOTE]
  > <span data-ttu-id="e9445-191">これは、オンラインの組織内のユーザーに通話をリダイレクトする場合にも該当します。</span><span class="sxs-lookup"><span data-stu-id="e9445-191">This also applies if you want to redirect calls to people in your organization who are online.</span></span> <span data-ttu-id="e9445-192">これらの個人は、**電話システム**のライセンスとエンタープライズボイスを有効にしている**か**、通話プランを利用している必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9445-192">These individuals must have a **Phone System** license and Enterprise Voice enabled **or** have a Calling Plan.</span></span> <span data-ttu-id="e9445-193">詳細については、「 [Skype For business ライセンスの割り当て](/Skype/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)、 [Microsoft Teams ライセンスの割り当て](https://docs.microsoft.com/microsoftteams/assign-teams-licenses)、または[最適な通話プラン](https://docs.microsoft.com/microsoftteams/calling-plan-landing-page)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9445-193">For more information see [Assign Skype for Business licenses](/Skype/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md), [Assign Microsoft Teams licenses](https://docs.microsoft.com/microsoftteams/assign-teams-licenses), or [Which Calling Plan is right for you?](https://docs.microsoft.com/microsoftteams/calling-plan-landing-page)</span></span>

 <span data-ttu-id="e9445-194">エンタープライズ Voip のエージェントを有効にするには、Windows PowerShell を使用します。</span><span class="sxs-lookup"><span data-stu-id="e9445-194">To enable an agent for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="e9445-195">たとえば、次のように実行します。`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="e9445-195">For example run: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

- <span data-ttu-id="e9445-196">**電話システム**のライセンスを持っているか、Office 365 グループに追加された通話プランを使用しているオンラインユーザーメールが有効な配布リストまたはセキュリティグループ。</span><span class="sxs-lookup"><span data-stu-id="e9445-196">Online users with a **Phone System** license or a Calling Plan that are added to either an Office 365 Group; a mail-enabled Distribution List; or a Security Group.</span></span> <span data-ttu-id="e9445-197">配布リストまたはセキュリティグループに新しく追加されたエージェントが、通話キューからの着信の受信を開始するまでに最大3時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="e9445-197">It might take up to three hours for a newly added agent in a distribution list, or a security group, to start receiving calls from a call queue.</span></span> <span data-ttu-id="e9445-198">新しく作成した分配リストまたはセキュリティ グループでは、通話キューで使用可能になるまで最大で48時間を要する場合があります。</span><span class="sxs-lookup"><span data-stu-id="e9445-198">A newly created distribution list or security group might take up to 48 hours to become available to be used with call queues.</span></span> <span data-ttu-id="e9445-199">新しく作成された Office 365 グループは、ほぼ瞬時にご利用可能です。</span><span class="sxs-lookup"><span data-stu-id="e9445-199">Newly created Office 365 Groups are available almost immediately.</span></span>

- <span data-ttu-id="e9445-200">担当者が Microsoft Teams アプリを使って着信キューの呼び出しを受信している場合は、チームメンバーが Teams Sonly モードである必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9445-200">If your agents are using Microsoft Teams App to receive call queue calls, they need to be in TeamsOnly mode.</span></span>

![[コールエージェントの追加] ウィンドウのスクリーンショット](media/skype-for-business-add-agents-to-call-queue.png)

![前のスクリーンショットで吹き出しを参照している数値2のアイコン](media/sfbcallout2.png)

<span data-ttu-id="e9445-203">**ルーティング方法**通話キューの配布方法には、**アテンダント**、**シリアル**、または**ラウンドロビン**のいずれかを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="e9445-203">**Routing method** You can choose either **Attendant**, **Serial**, or **Round Robin** for your call queue distribution method.</span></span> <span data-ttu-id="e9445-204">新規および既存のすべての通話キューは、応答のルーティングが既定値で選択されます。</span><span class="sxs-lookup"><span data-stu-id="e9445-204">All new and existing call queues will have attendant routing selected by default.</span></span> <span data-ttu-id="e9445-205">アテンダントルーティングを使うと、キュー内の最初の呼び出しによって、すべてのコールエージェントが同時に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="e9445-205">When attendant routing is used, the first call in the queue will ring all of the call agents at the same time.</span></span> <span data-ttu-id="e9445-206">通話を受ける最初のコールエージェントは、通話を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="e9445-206">The first call agent to pick up the call gets the call.</span></span>

- <span data-ttu-id="e9445-207">**アテンダントルーティング**を行うと、キュー内の最初の呼び出しがすべてのコールエージェントを同時に呼び出します。</span><span class="sxs-lookup"><span data-stu-id="e9445-207">**Attendant routing** causes the first call in the queue to ring all call agents at the same time.</span></span> <span data-ttu-id="e9445-208">通話を受ける最初のコールエージェントは、通話を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="e9445-208">The first call agent to pick up the call gets the call.</span></span>
- <span data-ttu-id="e9445-209">**シリアルルーティング**は、通話エージェントの一覧の先頭から、通話エージェントを1つずつ呼び出します。</span><span class="sxs-lookup"><span data-stu-id="e9445-209">**Serial routing** incoming calls will ring call agents one by one, starting from the beginning of the call agent list.</span></span> <span data-ttu-id="e9445-210">通話エージェントの一覧内では、エージェントを注文することはできません。</span><span class="sxs-lookup"><span data-stu-id="e9445-210">Agents cannot be ordered within the call agent list.</span></span> <span data-ttu-id="e9445-211">エージェントが退出中、または応答しない場合、リスト上の次のエージェントを呼び出し、キューで待機中の発信が応答するかタイムアウトになるまで、すべてのエージェントの呼び出しを 1 件ずつ試みます。</span><span class="sxs-lookup"><span data-stu-id="e9445-211">If an agent dismisses or does not pick up a call, the call will ring the next agent on the list and will try all agents one by one until it is picked up or times out waiting in the queue.</span></span>
  > [!NOTE]
  > <span data-ttu-id="e9445-212">**オフライン**中、**取り込み中**表示、またはこのキューからの着信を **オプトアウト** したエージェントは、シリアルルーティングからスキップされます。</span><span class="sxs-lookup"><span data-stu-id="e9445-212">Serial routing will skip agents who are **Offline**, have set their presence to **Do not Disturb**, or have **opted out** of getting calls from this queue.</span></span>
- <span data-ttu-id="e9445-213">**ラウンドロビン**は、着信呼び出しのルーティングを分散して、各通話エージェントがキューから同じ数の通話を取得できるようにします。</span><span class="sxs-lookup"><span data-stu-id="e9445-213">**Round robin** balances routing of incoming calls so that each call agent will get the same number of calls from the queue.</span></span> <span data-ttu-id="e9445-214">これは、すべての通話エージェントで同一の営業案件を確保するために、着信の販売環境で非常に望ましい場合があります。</span><span class="sxs-lookup"><span data-stu-id="e9445-214">This may be very desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

### <a name="select-an-agent-opt-out-option"></a><span data-ttu-id="e9445-215">エージェントのオプトアウトオプションを選択する</span><span class="sxs-lookup"><span data-stu-id="e9445-215">Select an agent opt-out option</span></span>

![番号付き吹き出しが含まれる、エージェントのオプトアウトオプションのスクリーンショット](media/99279eff-db61-4acf-9b62-64be84b6414b.png)
 
* * *

![前のスクリーンショットで吹き出しを参照する数値1のアイコン](media/sfbcallout1.png)

<span data-ttu-id="e9445-218">**エージェントが通話を受けることができ**ないこのオプションを有効にすると、通話キューエージェントが特定のキューからの呼び出しを行わないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="e9445-218">**Agent can opt out of getting calls** You can choose to allow call queue agents to opt-out of taking calls from a particular queue by enabling this option.</span></span>

<span data-ttu-id="e9445-219">このオプションを有効にすると、このキュー内のすべてのエージェントは、この通話キューからの着信の受信を開始または停止することができます。</span><span class="sxs-lookup"><span data-stu-id="e9445-219">Enabling this option allows all agents in this queue to start or stop receiving calls from this call queue at will.</span></span> <span data-ttu-id="e9445-220">チェックボックスの削除することによっていつでもオプトアウトの取消しが可能で、オプトアウトされたエージェントはこの通話キューへ自動的にもう一度オプトインされます。 (すべてのエージェントの初期設定)</span><span class="sxs-lookup"><span data-stu-id="e9445-220">You can revoke the agent opt-out privilege at any time by clearing the check box, causing agents to become automatically opted in for this queue again (the default setting for all agents).</span></span>

<span data-ttu-id="e9445-221">エージェントは次の操作を行うと、オプトアウトのオプションにアクセスできます:</span><span class="sxs-lookup"><span data-stu-id="e9445-221">To access the opt-out option, agents can do the following:</span></span>

 1. <span data-ttu-id="e9445-222">Skype for Business クライアントデスクトップで、 **オプション** を開きます。</span><span class="sxs-lookup"><span data-stu-id="e9445-222">Open **Options** in their desktop Skype for Business client.</span></span>
 2. <span data-ttu-id="e9445-223">**[通話転送]** タブで、 **[オンライン編集の設定]** リンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e9445-223">On the **Call Forwarding** tab, click the **Edit settings online** link.</span></span>
 3. <span data-ttu-id="e9445-224">[ユーザー設定] ページで、[**通話キュー**] をクリックし、脱退するキューのチェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="e9445-224">On the user settings page, click **Call Queues**, and then clear the check boxes for any queues for which they want to opt-out.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e9445-225">Skype for Business デスクトップ以外のアプリまたはエンドポイントを使用するエージェントは、ユーザー設定ポータル[https://aka.ms/cqsettings](https://aka.ms/cqsettings)から脱退オプションにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="e9445-225">Agents using apps or endpoints other than Skype for Business Desktop can access the opt-out option from the user settings portal [https://aka.ms/cqsettings](https://aka.ms/cqsettings).</span></span>

<span data-ttu-id="e9445-226">![前のスクリーンショット](media/sfbcallout2.png)
の**通知設定**で吹き出しを参照している番号2のアイコン</span><span class="sxs-lookup"><span data-stu-id="e9445-226">![Icon of the number 2, referencing a callout in the previous screenshot](media/sfbcallout2.png)
**Agent Alert setting**</span></span>

<span data-ttu-id="e9445-227">これは、シリアルまたはラウンドロビンルーティングメソッドが次のエージェントに移動する前に、通話の通知を受けるエージェントの期間を定義します。</span><span class="sxs-lookup"><span data-stu-id="e9445-227">This defines the duration of an agent being notified of a call before the Serial or Round Robin routing methods move to the next agent.</span></span>

<span data-ttu-id="e9445-228">既定の設定は30秒ですが、最大3分に設定することができます。</span><span class="sxs-lookup"><span data-stu-id="e9445-228">The default setting is 30 seconds, but it can be set for up to 3 minutes.</span></span>

* * *

### <a name="set-the-call-overflow-and-timeout-handling-options"></a><span data-ttu-id="e9445-229">通話のオーバーフローとタイムアウト処理のオプションを設定する</span><span class="sxs-lookup"><span data-stu-id="e9445-229">Set the call overflow and timeout handling options</span></span>

![番号付き吹き出しが含まれるオーバーフロー処理オプションのスクリーンショット](media/3f018734-16fe-458b-827d-71fc25155cde.png)
 
* * *

![前のスクリーンショットで吹き出しを参照する数値1のアイコン](media/sfbcallout1.png)

<span data-ttu-id="e9445-232">**キュー内の最大通話数** この項目を使用して、同時に通話がキュー内で待機できる最大通話数を設定します。</span><span class="sxs-lookup"><span data-stu-id="e9445-232">**Maximum calls in the queue** Use this to set the maximum calls that can wait in the queue at the same time.</span></span> <span data-ttu-id="e9445-233">既定値は50ですが、0 ~ 200 の範囲で指定できます。</span><span class="sxs-lookup"><span data-stu-id="e9445-233">The default is 50, but it can range from 0 to 200.</span></span> <span data-ttu-id="e9445-234">この制限に達すると、通話は次の [ **呼び出しの最大数に達した場合**] 設定で指定した方法で処理されます。</span><span class="sxs-lookup"><span data-stu-id="e9445-234">When this limit is reached, the call will be handled in way you have set on the **When the maximum number of calls is reached** setting below.</span></span>

* * *

![前のスクリーンショットで吹き出しを参照している数値2のアイコン](media/sfbcallout2.png)

<span data-ttu-id="e9445-236">**通話の最大数に達した場合**通話キューが最大サイズ (**キュー設定の最大の通話**を使用して設定) に達すると、新しい着信呼び出しに何が起こるかを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="e9445-236">**When the maximum number of calls is reached** When the call queue reaches its maximum size (set using the **Maximum calls in the queue** setting), you can choose what happens to new incoming calls.</span></span>

- <span data-ttu-id="e9445-237">**切断** 通話は切断されます。</span><span class="sxs-lookup"><span data-stu-id="e9445-237">**Disconnect** The call will be disconnected.</span></span>
- <span data-ttu-id="e9445-238">**リダイレクト先**選択する場合は、次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="e9445-238">**Redirect to** When you choose this, select one of the following:</span></span>

  - <span data-ttu-id="e9445-239">**社内のユーザー** **電話システム** のライセンスを持つオンラインのユーザーそしてエンタープライズ ボイス を有効にするか通話プランを取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9445-239">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have a Calling Plan.</span></span> <span data-ttu-id="e9445-240">発信中のユーザーがボイスメールに送信されるように設定できます。</span><span class="sxs-lookup"><span data-stu-id="e9445-240">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="e9445-241">これを行うには、**社内のユーザ**を選択して、そのユーザが直接ボイスメールに転送するように設定します。</span><span class="sxs-lookup"><span data-stu-id="e9445-241">To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span>

  <span data-ttu-id="e9445-242">ボイスメールに必要なライセンスについては、「[クラウドボイスメール](set-up-phone-system-voicemail.md)をセットアップする」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e9445-242">To learn about licensing required for voicemail, see [Set up Cloud Voicemail](set-up-phone-system-voicemail.md).</span></span>

  - <span data-ttu-id="e9445-243">**音声アプリケーション**既に作成されている通話キューまたは自動応答のいずれかの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="e9445-243">**Voice application** Select the name of either a call queue or auto attendant that has already been created.</span></span>

* * *

![前のスクリーンショットで吹き出しを参照している数値3のアイコン](media/sfbcallout3.png)

<span data-ttu-id="e9445-245">**通話タイムアウト: 最大待機時間**また、通話がタイムアウトとなり、リダイレクトまたは切断する必要があるときに、通話を保留する時間を決定することもできます。</span><span class="sxs-lookup"><span data-stu-id="e9445-245">**Call Timeout: maximum wait time** You can also decide how much time a call can be on hold in the queue before it times out and needs to be redirected or disconnected.</span></span> <span data-ttu-id="e9445-246">リダイレクト先は [ **通話がタイムアウトした場合**] 設定に基づきます。</span><span class="sxs-lookup"><span data-stu-id="e9445-246">Where it will be redirected is based on how you set the **When a call times out** setting.</span></span> <span data-ttu-id="e9445-247">0 から 45 分に設定できます。</span><span class="sxs-lookup"><span data-stu-id="e9445-247">You can set a time from 0 to 45 minutes.</span></span>

<span data-ttu-id="e9445-248">タイムアウト値は秒単位で、 15 秒間隔で設定することができます。</span><span class="sxs-lookup"><span data-stu-id="e9445-248">The timeout value can be set in seconds, at 15-second intervals.</span></span> <span data-ttu-id="e9445-249">これにより、通話フローを細かく操作することができます。</span><span class="sxs-lookup"><span data-stu-id="e9445-249">This allows you to manipulate the call flow with finer granularity.</span></span> <span data-ttu-id="e9445-250">たとえば、エージェントによって応答されないすべての通話を30秒以内に指定して、ディレクトリ検索の自動応答に移動することができます。</span><span class="sxs-lookup"><span data-stu-id="e9445-250">For example, you could specify that any calls that are not answered by an agent within 30 seconds go to a Directory Search auto attendant.</span></span>

![前のスクリーンショットで吹き出しを参照している数値4のアイコン](media/sfbcallout4.png)

<span data-ttu-id="e9445-252">**通話がタイムアウトになったとき**通話が [キュー] 設定で、通話の**待ち時間**として設定した限度額に達した場合は、この通話に対する処理を選択できます。</span><span class="sxs-lookup"><span data-stu-id="e9445-252">**When call times out** When the call reaches the limit you set on the **How long a call can wait in the queue** setting, you can choose what happens to this call:</span></span>

- <span data-ttu-id="e9445-253">**切断** 通話は切断されます。</span><span class="sxs-lookup"><span data-stu-id="e9445-253">**Disconnect** The call will be disconnected.</span></span>
- <span data-ttu-id="e9445-254">**この通話のリダイレクト先**このオプションを選択すると、次のオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e9445-254">**Redirect this call to** When you choose this, you will have these options:</span></span>
  - <span data-ttu-id="e9445-255">**社内のユーザー** **電話システム** のライセンスを持つオンラインユーザーで、エンタープライズ ボイス が有効化されているまたは、通話プランを取得済みである必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9445-255">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have Calling Plans.</span></span> <span data-ttu-id="e9445-256">発信中のユーザーがボイスメールに送信されるように設定できます。</span><span class="sxs-lookup"><span data-stu-id="e9445-256">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="e9445-257">これを行うには、**社内のユーザ**を選択して、そのユーザが直接ボイスメールに転送するように設定します。</span><span class="sxs-lookup"><span data-stu-id="e9445-257">To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span>

  <span data-ttu-id="e9445-258">ボイスメールに必要なライセンスについては、「[クラウドボイスメール](set-up-phone-system-voicemail.md)をセットアップする」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e9445-258">To learn about licensing required for voicemail, see [Set up Cloud Voicemail](set-up-phone-system-voicemail.md).</span></span>

  - <span data-ttu-id="e9445-259">**音声アプリケーション**既に作成されている通話キューまたは自動応答のいずれかの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="e9445-259">**Voice application** Select the name of either a call queue or auto attendant that has already been created.</span></span>

## <a name="changing-a-users-caller-id-for-outbound-calls"></a><span data-ttu-id="e9445-260">発信通話用にユーザーの発信者番号認識を変更する</span><span class="sxs-lookup"><span data-stu-id="e9445-260">Changing a user's Caller ID for outbound calls</span></span>

<span data-ttu-id="e9445-261">ユーザーの id を保護するには、 **CsCallingLineIdentity**コマンドレットを使用してポリシーを作成する代わりに、通話キュー、自動応答、または任意のサービス番号への発信通話の発信者番号を変更します。</span><span class="sxs-lookup"><span data-stu-id="e9445-261">You can protect a user's identity by changing their caller ID for outbound calls to a call queue, auto attendant, or any service number instead by creating a policy using the **New-CsCallingLineIdentity** cmdlet.</span></span>

<span data-ttu-id="e9445-262">これを行う場合は、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="e9445-262">To do this, run:</span></span>

``` Powershell
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

<span data-ttu-id="e9445-263">**Grant-CallingLineIdentity** コマンドレットを使用してユーザーのポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="e9445-263">Then apply the policy to the user using the **Grant-CallingLineIdentity** cmdlet.</span></span> <span data-ttu-id="e9445-264">これを行う場合は、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="e9445-264">To do this, run:</span></span>
 
``` Powershell
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

<span data-ttu-id="e9445-265">組織内の発信者番号通知設定を変更する方法については、「[組織での発信者番号の使用方法](/microsoftteams/how-can-caller-id-be-used-in-your-organization)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e9445-265">You can get more information on how to make changes to caller ID settings in your organization in the article [How can caller ID be used in your organization](/microsoftteams/how-can-caller-id-be-used-in-your-organization).</span></span>

## <a name="call-queue-cmdlets"></a><span data-ttu-id="e9445-266">通話キューのコマンドレット</span><span class="sxs-lookup"><span data-stu-id="e9445-266">Call queue cmdlets</span></span>

<span data-ttu-id="e9445-267">Windows PowerShell を使用して通話キューを作成し、設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="e9445-267">You can also use Windows PowerShell to create and set up call queues.</span></span> <span data-ttu-id="e9445-268">通話キューの管理で必要なコマンドレットを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="e9445-268">Here are the cmdlets that you need to manage a call queue.</span></span>
 
- [<span data-ttu-id="e9445-269">新規-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="e9445-269">New-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="e9445-270">Set-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="e9445-270">Set-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/set-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="e9445-271">Get-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="e9445-271">Get-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/get-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="e9445-272">Remove-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="e9445-272">Remove-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-CsCallQueue?view=skype-ps)

### <a name="more-about-windows-powershell"></a><span data-ttu-id="e9445-273">Windows PowerShell の詳細について</span><span class="sxs-lookup"><span data-stu-id="e9445-273">More about Windows PowerShell</span></span>

- <span data-ttu-id="e9445-274">Windows PowerShell では、ユーザーの管理と、許可または許可されていないユーザーの操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="e9445-274">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="e9445-275">Windows PowerShell を使用すると、複数のタスクがある場合に、1つの管理ポイントを使用して Office 365 および Microsoft Teams を管理することができます。</span><span class="sxs-lookup"><span data-stu-id="e9445-275">With Windows PowerShell, you can manage Office 365 and Microsoft Teams using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="e9445-276">Windows PowerShell の使用を開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9445-276">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="e9445-277">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="e9445-277">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [<span data-ttu-id="e9445-278">Office 365 PowerShell を使用する必要がある理由</span><span class="sxs-lookup"><span data-stu-id="e9445-278">Why you need to use Office 365 PowerShell</span></span>](https://docs.microsoft.com/en-us/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- <span data-ttu-id="e9445-279">Windows PowerShell には、多くのユーザーについて同時に設定を変更する場合など、Microsoft Teams 管理センターを使用する場合にのみ、速度、シンプルさ、生産性を高めることができます。</span><span class="sxs-lookup"><span data-stu-id="e9445-279">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft Teams admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="e9445-280">次のトピックでこれらの利点について説明します。</span><span class="sxs-lookup"><span data-stu-id="e9445-280">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="e9445-281">Windows PowerShell を使用して Office 365 を管理する</span><span class="sxs-lookup"><span data-stu-id="e9445-281">Manage Office 365 with Windows PowerShell</span></span>](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [<span data-ttu-id="e9445-282">Windows PowerShell 用にコンピューターをセットアップする</span><span class="sxs-lookup"><span data-stu-id="e9445-282">Set up your computer for Windows PowerShell</span></span>](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a><span data-ttu-id="e9445-283">関連トピック</span><span class="sxs-lookup"><span data-stu-id="e9445-283">Related topics</span></span>

[<span data-ttu-id="e9445-284">Office 365 の電話システムでできること</span><span class="sxs-lookup"><span data-stu-id="e9445-284">Here's what you get with Phone System in Office 365</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="e9445-285">サービス電話番号を取得する</span><span class="sxs-lookup"><span data-stu-id="e9445-285">Getting service phone numbers</span></span>](getting-service-phone-numbers.md)

[<span data-ttu-id="e9445-286">国および地域ごとの電話会議および通話プランの利用可能性</span><span class="sxs-lookup"><span data-stu-id="e9445-286">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="e9445-287">新しい Csonline Applicationinstance</span><span class="sxs-lookup"><span data-stu-id="e9445-287">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
