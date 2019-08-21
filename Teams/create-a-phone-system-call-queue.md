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
f1keywords:
- ms.teamsadmincenter.callqueues.overview"
ms.custom:
- Phone System
description: Microsoft Teams でクラウド通話キューの電話システムをセットアップする方法について説明します。
ms.openlocfilehash: 8ae41603e3899c379fa09b2b08dd5e111b8405da
ms.sourcegitcommit: d4e69d46de564c445feb855cbee55954a7063bba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2019
ms.locfileid: "36483317"
---
# <a name="create-a-cloud-call-queue"></a><span data-ttu-id="23456-103">クラウドの通話キューを作成する</span><span class="sxs-lookup"><span data-stu-id="23456-103">Create a Cloud call queue</span></span>

<span data-ttu-id="23456-104">クラウド通話キューでは次の情報を提供できます。</span><span class="sxs-lookup"><span data-stu-id="23456-104">Cloud call queues can provide:</span></span>

- <span data-ttu-id="23456-105">あいさつメッセージ。</span><span class="sxs-lookup"><span data-stu-id="23456-105">A greeting message.</span></span>
- <span data-ttu-id="23456-106">通話の保留中に再生される保留音。</span><span class="sxs-lookup"><span data-stu-id="23456-106">Music while people are waiting on hold.</span></span>
- <span data-ttu-id="23456-107">メール対応配布リストとセキュリティ グループを使用した、コール エージェントへの通話のリダイレクト。</span><span class="sxs-lookup"><span data-stu-id="23456-107">Redirecting calls to call agents in mail-enabled distribution lists and security groups.</span></span>
- <span data-ttu-id="23456-108">キューの最大サイズ、タイムアウト、通話処理オプションなどのさまざまなパラメーターを設定します。</span><span class="sxs-lookup"><span data-stu-id="23456-108">Setting different parameters such as queue maximum size, timeout, and call handling options.</span></span>

<span data-ttu-id="23456-109">[リソースアカウント](manage-resource-accounts.md)を使用して、電話番号を通話キューに関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="23456-109">You would associate a phone number to a call queue using a [resource account](manage-resource-accounts.md).</span></span> <span data-ttu-id="23456-110">通話キューには、自動応答の選択によって直接ダイヤルするか、アクセスすることができます。</span><span class="sxs-lookup"><span data-stu-id="23456-110">A call queue can be dialed directly or accessed by a selection on an auto attendant.</span></span>

<span data-ttu-id="23456-111">発信者は、保留中の音楽を聞くことができます。通話は、*先入れ先出し*(FIFO) の順序で通話エージェントに接続します。</span><span class="sxs-lookup"><span data-stu-id="23456-111">The caller hears music while they are on hold, and the call connects to the call agents in *First In, First Out* (FIFO) order.</span></span>

<span data-ttu-id="23456-112">キュー内のすべての通話は、次のいずれかの方法でエージェントに送信されます。</span><span class="sxs-lookup"><span data-stu-id="23456-112">All calls in the queue are sent to agents by one of the following methods:</span></span>

- <span data-ttu-id="23456-113">アテンダントルーティングを使用すると、キューの最初の呼び出しですべてのエージェントが同時に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="23456-113">With attendant routing, the first call in the queue  rings all agents at the same time.</span></span>
- <span data-ttu-id="23456-114">シリアルルーティングでは、キューにある最初の呼び出しによって、すべてのコールエージェントが1つずつリングされます。</span><span class="sxs-lookup"><span data-stu-id="23456-114">With serial routing, the first call in the queue rings all call agents one by one.</span></span>
- <span data-ttu-id="23456-115">ラウンドロビンでは、着信のルーティングが分散され、各通話エージェントがキューから同じ数の通話を取得できるようになります。</span><span class="sxs-lookup"><span data-stu-id="23456-115">With round robin, routing of incoming calls is balanced so that each call agent gets the same number of calls from the queue.</span></span>

    > [!NOTE]
    > <span data-ttu-id="23456-116">**オフライン**の通話エージェントは、自分のプレゼンスが [**応答不可]** に設定されています。または、通話キューを無効にしても、通話を受けることはできません。</span><span class="sxs-lookup"><span data-stu-id="23456-116">Call agents who are **Offline**, have set their presence to **Do not Disturb,** or have opted out of the call queue will not recieve calls.</span></span>

- <span data-ttu-id="23456-117">一度に1つの着信通知 (キューの先頭にある通話用) のみが通話エージェントに送信されます。</span><span class="sxs-lookup"><span data-stu-id="23456-117">Only one incoming call notification (for the call at the head of the queue) at a time goes to the call agents.</span></span>
- <span data-ttu-id="23456-118">コール エージェントが通話を受けると、キューにある次の着信がコール エージェントを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="23456-118">After a call agent accepts the call, the next incoming call in the queue will start ringing call agents.</span></span>

> [!NOTE]
> <span data-ttu-id="23456-119">この記事は、Microsoft Teams と Skype for Business Online の両方に適用されます。</span><span class="sxs-lookup"><span data-stu-id="23456-119">This article applies to both Microsoft Teams and Skype for Business Online.</span></span>

## <a name="step-1--get-started"></a><span data-ttu-id="23456-120">手順 1-はじめに</span><span class="sxs-lookup"><span data-stu-id="23456-120">Step 1 — Get started</span></span>

<span data-ttu-id="23456-121">通話キューを使用する場合は、次の重要な点について留意してください。</span><span class="sxs-lookup"><span data-stu-id="23456-121">To get started using call queues, it's important to remember a few things:</span></span>

- <span data-ttu-id="23456-122">通話キューには、関連するリソースアカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="23456-122">A call queue is required to have an associated resource account.</span></span> <span data-ttu-id="23456-123">リソースアカウントの詳細については、「[チームのリソースアカウントを管理](manage-resource-accounts.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="23456-123">See [Manage resource accounts in Teams](manage-resource-accounts.md) for details on resource accounts.</span></span>
- <span data-ttu-id="23456-124">リソースアカウントに電話番号を割り当てると、無料電話システムの[仮想ユーザーライセンス](teams-add-on-licensing/virtual-user.md)を使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="23456-124">When you assign a phone number to a resource account, you can now use the cost-free Phone System [Virtual User license](teams-add-on-licensing/virtual-user.md).</span></span> <span data-ttu-id="23456-125">電話システムでは、低コストの自動応答と通話キューサービスを使用するために、組織レベルで電話番号を使うことができます。</span><span class="sxs-lookup"><span data-stu-id="23456-125">Phone System allows phone numbers at the organizational level for use with low-cost auto attendant and call queue services.</span></span>

> [!NOTE]
> <span data-ttu-id="23456-126">通話キューの直接ルーティングサービス番号は、Microsoft Teams ユーザーとエージェントに対してのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="23456-126">Direct Routing service numbers for call queues are supported for Microsoft Teams users and agents only.</span></span>

> [!NOTE]
> <span data-ttu-id="23456-127">インターネットに接続している組織内のユーザーに通話をリダイレクトするには、**電話システム**のライセンスが必要です。また、エンタープライズ voip に対応しているか、Office 365 の通話プランを使用している必要があります。</span><span class="sxs-lookup"><span data-stu-id="23456-127">To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="23456-128">「 [Skype For business ライセンスの割り当て](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses)」または「 [Microsoft Teams ライセンスの割り当て](assign-teams-licenses.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="23456-128">See [Assign Skype for Business licenses](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) or [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="23456-129">エンタープライズ VoIP を有効にするには、Windows PowerShell を使用できます。</span><span class="sxs-lookup"><span data-stu-id="23456-129">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="23456-130">たとえば、次のように実行します。`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="23456-130">For example run: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

- <span data-ttu-id="23456-131">Office 365 の通話プランの詳細については、「[電話システムと通話プラン](calling-plan-landing-page.md)」および「 [Office 365 の通話プラン](calling-plans-for-office-365.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="23456-131">To learn more about Office 365 Calling Plans, see [Phone System and Calling Plans](calling-plan-landing-page.md) and [Calling Plans for Office 365](calling-plans-for-office-365.md).</span></span>

- <span data-ttu-id="23456-132">クラウド通話キューを割り当てることができるのは、 **Microsoft Teams 管理センター**で取得した、または別のサービスプロバイダーから転送された有料またはフリーダイヤルのサービス電話番号だけです。</span><span class="sxs-lookup"><span data-stu-id="23456-132">You can only assign Cloud call queues toll and toll-free service phone numbers that you got in the **Microsoft Teams admin center** or transferred from another service provider.</span></span> <span data-ttu-id="23456-133">無料サービス番号には、通信クレジットが必要です。</span><span class="sxs-lookup"><span data-stu-id="23456-133">Communications Credits are required for toll-free service numbers.</span></span>

    > [!NOTE]
    > <span data-ttu-id="23456-134">ユーザー (購読者) の電話番号を通話キューに割り当てることはできません。サービスの有料電話番号または無料電話番号のみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="23456-134">User (subscriber) phone numbers can't be assigned to call queues - only service toll or toll-free phone numbers can be used.</span></span>

- <span data-ttu-id="23456-135">クラウドの通話キューに関連付けられた通話エージェントは、次のクライアントでサポートされます。</span><span class="sxs-lookup"><span data-stu-id="23456-135">The following clients are supported for call agents associated to a Cloud call queue:</span></span>

  - <span data-ttu-id="23456-136">Skype for Business デスクトップクライアント 2016 (32 ビットバージョンと64ビットバージョン)</span><span class="sxs-lookup"><span data-stu-id="23456-136">Skype for Business desktop client 2016 (32-bit and 64-bit versions)</span></span>

  - <span data-ttu-id="23456-137">Lync デスクトップクライアント 2013 (32 ビットバージョンと64ビットバージョン)</span><span class="sxs-lookup"><span data-stu-id="23456-137">Lync desktop client 2013 (32-bit and 64-bit versions)</span></span>

  - <span data-ttu-id="23456-138">Microsoft Teams でサポートされているすべての IP 電話モデル。</span><span class="sxs-lookup"><span data-stu-id="23456-138">All IP phone models supported for Microsoft Teams.</span></span> <span data-ttu-id="23456-139">「 [Skype For Business Online の電話を取得する」を](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online)参照してください。</span><span class="sxs-lookup"><span data-stu-id="23456-139">See [Getting phones for Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span></span>

  - <span data-ttu-id="23456-140">Mac版  Skype for Business クライアント (バージョン 16.8.196 以降)</span><span class="sxs-lookup"><span data-stu-id="23456-140">Mac Skype for Business Client (version 16.8.196 and later)</span></span>

  - <span data-ttu-id="23456-141">Aandroid Skype for Business クライアント (バージョン 6.16.0.9 以降)</span><span class="sxs-lookup"><span data-stu-id="23456-141">Android Skype for Business Client (version 6.16.0.9 and later)</span></span>

  - <span data-ttu-id="23456-142">iPhone Skype for Business Client クライアント(バージョン 6.16.0 以降)</span><span class="sxs-lookup"><span data-stu-id="23456-142">iPhone Skype for Business Client (version 6.16.0 and later)</span></span>

  - <span data-ttu-id="23456-143">Mac版  Skype for Business クライアント (バージョン 6.16.0 以降)</span><span class="sxs-lookup"><span data-stu-id="23456-143">iPad Skype for Business Client (version 6.16.0 and later)</span></span>

  - <span data-ttu-id="23456-144">Microsoft Teams Windows クライアント (32 ビット版と64ビット版)</span><span class="sxs-lookup"><span data-stu-id="23456-144">Microsoft Teams Windows client (32-bit and 64-bit versions)</span></span>

  - <span data-ttu-id="23456-145">Microsoft Teams Mac クライアント</span><span class="sxs-lookup"><span data-stu-id="23456-145">Microsoft Teams Mac client</span></span>

  - <span data-ttu-id="23456-146">Microsoft Teams iPhone アプリ</span><span class="sxs-lookup"><span data-stu-id="23456-146">Microsoft Teams iPhone app</span></span>

  - <span data-ttu-id="23456-147">Microsoft Teams Android アプリ</span><span class="sxs-lookup"><span data-stu-id="23456-147">Microsoft Teams Android app</span></span>

## <a name="step-2--getting-or-transferring-toll-or-toll-free-service-phone-numbers"></a><span data-ttu-id="23456-148">手順 2-有料またはフリーダイヤルのサービス電話番号を取得または移行する</span><span class="sxs-lookup"><span data-stu-id="23456-148">Step 2 — Getting or transferring toll or toll-free service phone numbers</span></span>

<span data-ttu-id="23456-149">通話キューを作成して設定する前に、既存の有料または無料のサービス番号を取得または移行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="23456-149">Before you can create and set up your call queues, you need to get or transfer your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="23456-150">有料またはフリーダイヤルのサービス電話番号を取得すると、 **Microsoft Teams 管理センター** > **従来のポータル** > **ボイス** > **電話番号**に表示され、**番号の種類**は以下のようになります。**サービス: フリーダイヤル**。</span><span class="sxs-lookup"><span data-stu-id="23456-150">After you get the toll or toll-free service phone numbers, they will show up in **Microsoft Teams admin center** > **Legacy Portal** > **Voice** > **Phone numbers**, and the **Number type** will be listed as **Service — Toll-Free**.</span></span> <span data-ttu-id="23456-151">サービス番号を取得するには、「[サービスの電話番号を取得](getting-service-phone-numbers.md)する」または「既存のサービス番号を移行する」を参照してください。「 [Office 365 に電話番号を転送](transfer-phone-numbers-to-office-365.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="23456-151">To get your service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md) or if you want to transfer an existing service number, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>

> [!NOTE]
> <span data-ttu-id="23456-152">米国外の場合は、Microsoft Teams 管理センターを使用してサービス番号を取得することはできません。</span><span class="sxs-lookup"><span data-stu-id="23456-152">If you are outside the United States, you can't use the Microsoft Teams admin center to get service numbers.</span></span> <span data-ttu-id="23456-153">「[組織の電話番号を管理](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)する」に移動して、米国以外の地域での実行方法を確認します。</span><span class="sxs-lookup"><span data-stu-id="23456-153">Go to [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) instead to see how to do it from the outside of the United States.</span></span>

<span data-ttu-id="23456-154">複数の自動応答を設定すると、メインの自動応答のリソースアカウントに電話番号を割り当てることができます。これにより、発信者は通話キューまたはネストされた自動応答になります。</span><span class="sxs-lookup"><span data-stu-id="23456-154">When setting up multiple auto attendants you may only assign a phone number to the main auto attendant's resource account, which can direct callers to your call queues or nested auto attendants.</span></span> <span data-ttu-id="23456-155">このような場合は、ダイヤルパッドオプションを割り当てずに、システムですべての自動応答と通話キューを作成し、後で設定を編集します。</span><span class="sxs-lookup"><span data-stu-id="23456-155">In those situations, you create all auto attendants and call queues in your system without assigning dialpad options, and then edit the settings later.</span></span> <span data-ttu-id="23456-156">このことが必要になるのは、まだ存在していない通話キューまたは自動応答にリンクするオプションを作成できないためです。</span><span class="sxs-lookup"><span data-stu-id="23456-156">This is necessary because you aren't allowed to create an option linking to a call queue or auto attendant that does not yet exist.</span></span>

## <a name="step-3--create-a-new-call-queue"></a><span data-ttu-id="23456-157">手順 3-新しい通話キューを作成する</span><span class="sxs-lookup"><span data-stu-id="23456-157">Step 3 — Create a new call queue</span></span>

[!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

> [!IMPORTANT]
> <span data-ttu-id="23456-158">すべての通話キューには、[リソースアカウント](manage-resource-accounts.md)が関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="23456-158">Every call queue is required to have an associated [resource account](manage-resource-accounts.md).</span></span> <span data-ttu-id="23456-159">最初にリソースアカウントを作成してから、それを通話キューに関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="23456-159">You must create the resource account first, then you can associate it to the call queue.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="23456-160">Microsoft Teams 管理センターの使用</span><span class="sxs-lookup"><span data-stu-id="23456-160">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="23456-161">**Microsoft Teams 管理センター**の [**音声** > **通話キュー**] で、[ **+ Add new**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="23456-161">In the **Microsoft Teams admin center**, **Voice** > **Call queues**, then click **+ Add new**:</span></span>

### <a name="set-the-call-queue-display-name-and-resource-account"></a><span data-ttu-id="23456-162">通話キューの表示名とリソースアカウントを設定する</span><span class="sxs-lookup"><span data-stu-id="23456-162">Set the call queue display name and resource account</span></span>

![番号付き吹き出しが含まれる新しい通話キューのスクリーンショット](media/37ecc300-a108-4294-8463-fce570dfce72.png)

* * *

<span data-ttu-id="23456-164">![番号1のアイコン、前のスクリーンショット](media/sfbcallout1.png)
**名**で吹き出しを参照する通話キューのわかりやすい表示名を入力します。</span><span class="sxs-lookup"><span data-stu-id="23456-164">![Icon of the number 1, referencing a callout in the previous screenshot](media/sfbcallout1.png)
**Name** Enter a descriptive display name for the call queue.</span></span> <span data-ttu-id="23456-165">この名前は必須であり、スペースなどの最大64文字を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="23456-165">This name is required and can contain up to 64 characters, including spaces.</span></span>

 <span data-ttu-id="23456-166">この名前は、着信通話の通知に表示されます。</span><span class="sxs-lookup"><span data-stu-id="23456-166">This name is displayed in the notification for the incoming call.</span></span>

* * *

![前のスクリーンショットで吹き出しを参照している数値2のアイコン](media/sfbcallout2.png)

<span data-ttu-id="23456-168">**アカウントを追加**するリソースアカウントを選択します。</span><span class="sxs-lookup"><span data-stu-id="23456-168">**Add Accounts** Select a resource account.</span></span> <span data-ttu-id="23456-169">リソースアカウントは、通話キューの有料または無料の電話番号と関連付けられている場合と関連付けられていない場合もありますが、各通話キューには関連するリソースアカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="23456-169">The resource account may or may not be associated with a service toll or toll-free phone number for the call queue, but each call queue requires an associated resource account.</span></span>

<span data-ttu-id="23456-170">リストが表示されない場合は、前に説明したように、サービス番号を取得してリソースアカウントに割り当てておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="23456-170">If there aren't any listed, you need to get service numbers and assign them to a Resource account before you can create this call queue, as described earlier.</span></span> <span data-ttu-id="23456-171">サービス番号を取得するには、「[サービスの電話番号を取得](getting-service-phone-numbers.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="23456-171">To get your service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md).</span></span> <span data-ttu-id="23456-172">通話キューに関連付けられた電話番号が必要な場合は、「 [Teams のリソースアカウントを管理](manage-resource-accounts.md)する」の説明に従ってリソースアカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="23456-172">You create a resource account as described in [Manage resource accounts in Teams](manage-resource-accounts.md) if you want your call queue to have an associated phone number.</span></span>

> [!NOTE]
> <span data-ttu-id="23456-173">**ドメイン**を割り当てる必要がある場合は、それを呼び出しキューのリソースアカウントに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="23456-173">If you want or need to assign a **Domain** you would do so by assigning it to the resource account for the call queue.</span></span>

### <a name="set-the-greeting-and-music-played-while-on-hold"></a><span data-ttu-id="23456-174">応答メッセージおよび保留中の保留音を設定する</span><span class="sxs-lookup"><span data-stu-id="23456-174">Set the greeting and music played while on hold</span></span>

![[応答メッセージ] と [音楽] オプションのスクリーンショット。番号付き吹き出し](media/1d395a93-7cab-4178-9295-12d5379e20de.png)

* * *

![前のスクリーンショットで吹き出しを参照する数値1のアイコン](media/sfbcallout1.png)

<span data-ttu-id="23456-177">**応答メッセージ**は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="23456-177">**Greeting** is optional.</span></span> <span data-ttu-id="23456-178">これは、通話キュー番号にコールインした相手に対して再生される応答メッセージです。</span><span class="sxs-lookup"><span data-stu-id="23456-178">This is the greeting that is played for people who call in to the call queue number.</span></span>

<span data-ttu-id="23456-179">オーディオファイル (.wav、.mp3、または .wma 形式) をアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="23456-179">You can upload an audio file (.wav, .mp3, or .wma formats).</span></span>

![前のスクリーンショットで吹き出しを参照している数値2のアイコン](media/sfbcallout2.png)

<span data-ttu-id="23456-181">**保留中の音楽**通話キューで提供される既定の保留中の音楽を使用するか、または .wav、mp3、または .wma 形式のオーディオファイルをアップロードして、カスタム音楽を保留にすることができます。</span><span class="sxs-lookup"><span data-stu-id="23456-181">**Music on hold** You can either use the default Music on Hold provided with the call queue, or you can upload an audio file in .wav, mp3, or .wma formats to use as your custom Music on Hold.</span></span>

* * *

### <a name="select-the-call-answering-options"></a><span data-ttu-id="23456-182">通話応答のオプションを選択する</span><span class="sxs-lookup"><span data-stu-id="23456-182">Select the call answering options</span></span>

![番号付き吹き出しが含まれる通話応答オプションのスクリーンショット](media/5d249515-d532-4af2-90da-011404028b89.png)

![前のスクリーンショットで吹き出しを参照する数値1のアイコン](media/sfbcallout1.png)

<span data-ttu-id="23456-185">以下のメーリングリストまたはグループのいずれかに属する、最大200の通話エージェントを選択できます。</span><span class="sxs-lookup"><span data-stu-id="23456-185">You can select up to 200 call agents who belong to any of the following mailing lists or groups:</span></span>

- <span data-ttu-id="23456-186">Office 365 グループ</span><span class="sxs-lookup"><span data-stu-id="23456-186">Office 365 group</span></span>
- <span data-ttu-id="23456-187">セキュリティグループ</span><span class="sxs-lookup"><span data-stu-id="23456-187">Security group</span></span>
- <span data-ttu-id="23456-188">配布リスト</span><span class="sxs-lookup"><span data-stu-id="23456-188">Distribution list</span></span>

<span data-ttu-id="23456-189">選択された通話エージェントは、**電話システム**のライセンスを持つオンラインユーザーか\*\*\*\* 、エンタープライズボイスを有効にしている**か**、通話プランを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="23456-189">Call agents selected must **either** be online users with a **Phone System** license and Enterprise Voice enabled **or** have a Calling Plan.</span></span>

  > [!NOTE]
  > <span data-ttu-id="23456-190">これは、オンラインの組織内のユーザーに通話をリダイレクトする場合にも該当します。</span><span class="sxs-lookup"><span data-stu-id="23456-190">This also applies if you want to redirect calls to people in your organization who are online.</span></span> <span data-ttu-id="23456-191">これらの個人は、**電話システム**のライセンスとエンタープライズボイスを有効にしている**か**、通話プランを利用している必要があります。</span><span class="sxs-lookup"><span data-stu-id="23456-191">These individuals must have a **Phone System** license and Enterprise Voice enabled **or** have a Calling Plan.</span></span> <span data-ttu-id="23456-192">詳細については、「 [Skype For business ライセンスの割り当て](/Skype/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)、 [Microsoft Teams ライセンスの割り当て](https://docs.microsoft.com/microsoftteams/assign-teams-licenses)、または[適切な通話プラン](https://docs.microsoft.com/microsoftteams/calling-plan-landing-page)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="23456-192">For more information, see [Assign Skype for Business licenses](/Skype/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md), [Assign Microsoft Teams licenses](https://docs.microsoft.com/microsoftteams/assign-teams-licenses), or [Which Calling Plan is right for you?](https://docs.microsoft.com/microsoftteams/calling-plan-landing-page)</span></span>

 <span data-ttu-id="23456-193">エンタープライズ Voip のエージェントを有効にするには、Windows PowerShell を使用します。</span><span class="sxs-lookup"><span data-stu-id="23456-193">To enable an agent for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="23456-194">たとえば、次を実行します。`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="23456-194">For example, run: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

- <span data-ttu-id="23456-195">**電話システム**のライセンスを持っているか、Office 365 グループに追加された通話プランを持っているユーザーメールが有効な配布リストまたはセキュリティグループ。</span><span class="sxs-lookup"><span data-stu-id="23456-195">Users with a **Phone System** license or a Calling Plan that are added to either an Office 365 Group; a mail-enabled Distribution List; or a Security Group.</span></span> <span data-ttu-id="23456-196">配布リストまたはセキュリティグループに新しく追加されたエージェントが、通話キューからの着信の受信を開始するまでに最大3時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="23456-196">It might take up to three hours for a newly added agent in a distribution list, or a security group, to start receiving calls from a call queue.</span></span> <span data-ttu-id="23456-197">新しく作成した分配リストまたはセキュリティ グループでは、通話キューで使用可能になるまで最大で48時間を要する場合があります。</span><span class="sxs-lookup"><span data-stu-id="23456-197">A newly created distribution list or security group might take up to 48 hours to become available to be used with call queues.</span></span> <span data-ttu-id="23456-198">新しく作成された Office 365 グループは、ほぼ瞬時にご利用可能です。</span><span class="sxs-lookup"><span data-stu-id="23456-198">Newly created Office 365 Groups are available almost immediately.</span></span>

- <span data-ttu-id="23456-199">担当者が Microsoft Teams アプリを使って通話キューの呼び出しを実行している場合は、チームメンバーが Teams Sonly モードである必要があります。</span><span class="sxs-lookup"><span data-stu-id="23456-199">If your agents are using Microsoft Teams App to take call queue calls, they need to be in TeamsOnly mode.</span></span>

![[コールエージェントの追加] ウィンドウのスクリーンショット](media/skype-for-business-add-agents-to-call-queue.png)

![前のスクリーンショットで吹き出しを参照している数値2のアイコン](media/sfbcallout2.png)

<span data-ttu-id="23456-202">**ルーティング方法**通話キューの配布方法には、**アテンダント**、**シリアル**、または**ラウンドロビン**のいずれかを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="23456-202">**Routing method** You can choose either **Attendant**, **Serial**, or **Round Robin** for your call queue distribution method.</span></span> <span data-ttu-id="23456-203">新規および既存のすべての通話キューは、応答のルーティングが既定値で選択されます。</span><span class="sxs-lookup"><span data-stu-id="23456-203">All new and existing call queues will have attendant routing selected by default.</span></span> <span data-ttu-id="23456-204">アテンダントルーティングを使うと、キューの最初の呼び出しによって、すべてのコールエージェントが同時に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="23456-204">When attendant routing is used, the first call in the queue rings all call agents at the same time.</span></span> <span data-ttu-id="23456-205">通話を受ける最初のコールエージェントは、通話を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="23456-205">The first call agent to pick up the call gets the call.</span></span>

- <span data-ttu-id="23456-206">**アテンダントルーティング**を行うと、キュー内の最初の呼び出しがすべてのコールエージェントを同時に呼び出します。</span><span class="sxs-lookup"><span data-stu-id="23456-206">**Attendant routing** causes the first call in the queue to ring all call agents at the same time.</span></span> <span data-ttu-id="23456-207">通話を受ける最初のコールエージェントは、通話を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="23456-207">The first call agent to pick up the call gets the call.</span></span>
- <span data-ttu-id="23456-208">**シリアルルーティング**着信エージェントの一覧の先頭から1つずつ呼び出しエージェントが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="23456-208">**Serial routing** incoming calls ring call agents one by one, starting from the beginning of the call agent list.</span></span> <span data-ttu-id="23456-209">通話エージェントの一覧内では、エージェントを注文することはできません。</span><span class="sxs-lookup"><span data-stu-id="23456-209">Agents cannot be ordered within the call agent list.</span></span> <span data-ttu-id="23456-210">エージェントが退出中、または応答しない場合、リスト上の次のエージェントを呼び出し、キューで待機中の発信が応答するかタイムアウトになるまで、すべてのエージェントの呼び出しを 1 件ずつ試みます。</span><span class="sxs-lookup"><span data-stu-id="23456-210">If an agent dismisses or does not pick up a call, the call will ring the next agent on the list and will try all agents one by one until it is picked up or times out waiting in the queue.</span></span>
  > [!NOTE]
  > <span data-ttu-id="23456-211">**オフライン**中、**取り込み中**表示、またはこのキューからの着信を **オプトアウト** したエージェントは、シリアルルーティングからスキップされます。</span><span class="sxs-lookup"><span data-stu-id="23456-211">Serial routing will skip agents who are **Offline**, have set their presence to **Do not Disturb**, or have **opted out** of getting calls from this queue.</span></span>
- <span data-ttu-id="23456-212">**ラウンドロビン**は、着信呼び出しのルーティングを分散し、各呼び出しエージェントがキューから同じ数の通話を取得できるようにします。</span><span class="sxs-lookup"><span data-stu-id="23456-212">**Round robin** balances routing of incoming calls so that each call agent gets the same number of calls from the queue.</span></span> <span data-ttu-id="23456-213">これは、すべての通話エージェントで同一の営業案件を確保するために、着信の販売環境で望ましい場合があります。</span><span class="sxs-lookup"><span data-stu-id="23456-213">This may be desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

### <a name="select-an-agent-opt-out-option"></a><span data-ttu-id="23456-214">エージェントのオプトアウトオプションを選択する</span><span class="sxs-lookup"><span data-stu-id="23456-214">Select an agent opt-out option</span></span>

![番号付き吹き出しが含まれる、エージェントのオプトアウトオプションのスクリーンショット](media/99279eff-db61-4acf-9b62-64be84b6414b.png)

* * *

![前のスクリーンショットで吹き出しを参照する数値1のアイコン](media/sfbcallout1.png)

<span data-ttu-id="23456-217">**エージェントが通話を受けることができ**ないこのオプションを有効にすると、通話キューエージェントが特定のキューからの呼び出しを行わないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="23456-217">**Agent can opt out of getting calls** You can choose to allow call queue agents to opt-out of taking calls from a particular queue by enabling this option.</span></span>

<span data-ttu-id="23456-218">このオプションを有効にすると、このキュー内のすべてのエージェントは、この通話キューからの着信の受信を開始または停止することができます。</span><span class="sxs-lookup"><span data-stu-id="23456-218">Enabling this option allows all agents in this queue to start or stop receiving calls from this call queue at will.</span></span> <span data-ttu-id="23456-219">チェックボックスの削除することによっていつでもオプトアウトの取消しが可能で、オプトアウトされたエージェントはこの通話キューへ自動的にもう一度オプトインされます。 (すべてのエージェントの初期設定)</span><span class="sxs-lookup"><span data-stu-id="23456-219">You can revoke the agent opt-out privilege at any time by clearing the check box, causing agents to become automatically opted in for this queue again (the default setting for all agents).</span></span>

<span data-ttu-id="23456-220">エージェントは次の操作を行うと、オプトアウトのオプションにアクセスできます:</span><span class="sxs-lookup"><span data-stu-id="23456-220">To access the opt-out option, agents can do the following:</span></span>

 1. <span data-ttu-id="23456-221">Skype for Business クライアントデスクトップで、 **オプション** を開きます。</span><span class="sxs-lookup"><span data-stu-id="23456-221">Open **Options** in their desktop Skype for Business client.</span></span>
 2. <span data-ttu-id="23456-222">**[通話転送]** タブで、 **[オンライン編集の設定]** リンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="23456-222">On the **Call Forwarding** tab, click the **Edit settings online** link.</span></span>
 3. <span data-ttu-id="23456-223">[ユーザー設定] ページで、[**通話キュー**] をクリックし、脱退するキューのチェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="23456-223">On the user settings page, click **Call Queues**, and then clear the check boxes for any queues for which they want to opt-out.</span></span>

    > [!NOTE]
    > <span data-ttu-id="23456-224">Skype for Business デスクトップ以外のアプリまたはエンドポイントを使用するエージェントは、ユーザー設定ポータル[https://aka.ms/cqsettings](https://aka.ms/cqsettings)から脱退オプションにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="23456-224">Agents using apps or endpoints other than Skype for Business Desktop can access the opt-out option from the user settings portal [https://aka.ms/cqsettings](https://aka.ms/cqsettings).</span></span>

<span data-ttu-id="23456-225">![前のスクリーンショット](media/sfbcallout2.png)
の**通知設定**で吹き出しを参照している番号2のアイコン</span><span class="sxs-lookup"><span data-stu-id="23456-225">![Icon of the number 2, referencing a callout in the previous screenshot](media/sfbcallout2.png)
**Agent Alert setting**</span></span>

<span data-ttu-id="23456-226">これは、シリアルまたはラウンドロビンルーティングメソッドが次のエージェントに移動する前に、通話の通知を受けるエージェントの期間を定義します。</span><span class="sxs-lookup"><span data-stu-id="23456-226">This defines the duration of an agent being notified of a call before the Serial or Round Robin routing methods move to the next agent.</span></span>

<span data-ttu-id="23456-227">既定の設定は30秒ですが、最大3分に設定することができます。</span><span class="sxs-lookup"><span data-stu-id="23456-227">The default setting is 30 seconds, but it can be set for up to 3 minutes.</span></span>

* * *

### <a name="set-the-call-overflow-and-timeout-handling-options"></a><span data-ttu-id="23456-228">通話のオーバーフローとタイムアウト処理のオプションを設定する</span><span class="sxs-lookup"><span data-stu-id="23456-228">Set the call overflow and timeout handling options</span></span>

![番号付き吹き出しが含まれるオーバーフロー処理オプションのスクリーンショット](media/3f018734-16fe-458b-827d-71fc25155cde.png)

* * *

![前のスクリーンショットで吹き出しを参照する数値1のアイコン](media/sfbcallout1.png)

<span data-ttu-id="23456-231">**キュー内の最大通話数** この項目を使用して、同時に通話がキュー内で待機できる最大通話数を設定します。</span><span class="sxs-lookup"><span data-stu-id="23456-231">**Maximum calls in the queue** Use this to set the maximum calls that can wait in the queue at the same time.</span></span> <span data-ttu-id="23456-232">既定値は50ですが、0 ~ 200 の範囲で指定できます。</span><span class="sxs-lookup"><span data-stu-id="23456-232">The default is 50, but it can range from 0 to 200.</span></span> <span data-ttu-id="23456-233">この制限に達すると、通話は以下の [**通話の最大数に達した場合**] 設定で設定した方法で処理されます。</span><span class="sxs-lookup"><span data-stu-id="23456-233">When this limit is reached, the call is handled in the way you set on the **When the maximum number of calls is reached** setting below.</span></span>

* * *

![前のスクリーンショットで吹き出しを参照している数値2のアイコン](media/sfbcallout2.png)

<span data-ttu-id="23456-235">**通話の最大数に達した場合**通話キューが最大サイズ (**キュー設定の最大の通話**を使用して設定) に達すると、新しい着信呼び出しに何が起こるかを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="23456-235">**When the maximum number of calls is reached** When the call queue reaches its maximum size (set using the **Maximum calls in the queue** setting), you can choose what happens to new incoming calls.</span></span>

- <span data-ttu-id="23456-236">**切断**通話が切断されます。</span><span class="sxs-lookup"><span data-stu-id="23456-236">**Disconnect** The call is disconnected.</span></span>
- <span data-ttu-id="23456-237">**リダイレクト先**選択する場合は、次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="23456-237">**Redirect to** When you choose this, select one of the following:</span></span>

  - <span data-ttu-id="23456-238">**社内のユーザー** **電話システム** のライセンスを持つオンラインのユーザーそしてエンタープライズ ボイス を有効にするか通話プランを取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="23456-238">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have a Calling Plan.</span></span> <span data-ttu-id="23456-239">発信者がボイスメールに送信できるように設定できます。</span><span class="sxs-lookup"><span data-stu-id="23456-239">You can set it up so the caller can be sent to voicemail.</span></span> <span data-ttu-id="23456-240">これを行うには、**社内のユーザ**を選択して、そのユーザが直接ボイスメールに転送するように設定します。</span><span class="sxs-lookup"><span data-stu-id="23456-240">To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span>

  <span data-ttu-id="23456-241">ボイスメールに必要なライセンスについては、「[クラウドボイスメールのセットアップ](set-up-phone-system-voicemail.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="23456-241">To learn about licenses required for voicemail, see [Set up Cloud Voicemail](set-up-phone-system-voicemail.md).</span></span>

  - <span data-ttu-id="23456-242">**音声アプリケーション**既に作成されている通話キューまたは自動応答に関連付けられているリソースアカウントの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="23456-242">**Voice application** Select the name of a resource account associated to either a call queue or auto attendant that has already been created.</span></span>

* * *

![前のスクリーンショットで吹き出しを参照している数値3のアイコン](media/sfbcallout3.png)

<span data-ttu-id="23456-244">**通話タイムアウト: 最大待機時間**また、通話がタイムアウトとなり、リダイレクトまたは切断する必要があるときに、通話を保留する時間を決定することもできます。</span><span class="sxs-lookup"><span data-stu-id="23456-244">**Call Timeout: maximum wait time** You can also decide how much time a call can be on hold in the queue before it times out and needs to be redirected or disconnected.</span></span> <span data-ttu-id="23456-245">リダイレクトされる場所は、**通話**のタイムアウト設定を設定する方法に基づいています。</span><span class="sxs-lookup"><span data-stu-id="23456-245">Where it is redirected is based on how you set the **When a call times out** setting.</span></span> <span data-ttu-id="23456-246">0 から 45 分に設定できます。</span><span class="sxs-lookup"><span data-stu-id="23456-246">You can set a time from 0 to 45 minutes.</span></span>

<span data-ttu-id="23456-247">タイムアウト値は秒単位で、 15 秒間隔で設定することができます。</span><span class="sxs-lookup"><span data-stu-id="23456-247">The timeout value can be set in seconds, at 15-second intervals.</span></span> <span data-ttu-id="23456-248">これにより、通話フローを細かく操作することができます。</span><span class="sxs-lookup"><span data-stu-id="23456-248">This allows you to manipulate the call flow with finer granularity.</span></span> <span data-ttu-id="23456-249">たとえば、エージェントによって応答されないすべての通話を30秒以内に指定して、ディレクトリ検索の自動応答に移動することができます。</span><span class="sxs-lookup"><span data-stu-id="23456-249">For example, you could specify that any calls that are not answered by an agent within 30 seconds go to a Directory Search auto attendant.</span></span>

![前のスクリーンショットで吹き出しを参照している数値4のアイコン](media/sfbcallout4.png)

<span data-ttu-id="23456-251">**通話がタイムアウトになったとき**通話が [キュー] 設定で、通話の**待ち時間**として設定した限度額に達した場合は、この通話に対する処理を選択できます。</span><span class="sxs-lookup"><span data-stu-id="23456-251">**When call times out** When the call reaches the limit you set on the **How long a call can wait in the queue** setting, you can choose what happens to this call:</span></span>

- <span data-ttu-id="23456-252">**切断**通話が切断されます。</span><span class="sxs-lookup"><span data-stu-id="23456-252">**Disconnect** The call is disconnected.</span></span>
- <span data-ttu-id="23456-253">**この通話のリダイレクト先**このオプションを選択すると、次のオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="23456-253">**Redirect this call to** When you choose this, you have these options:</span></span>
  - <span data-ttu-id="23456-254">**社内のユーザー** **電話システム** のライセンスを持つオンラインユーザーで、エンタープライズ ボイス が有効化されているまたは、通話プランを取得済みである必要があります。</span><span class="sxs-lookup"><span data-stu-id="23456-254">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have Calling Plans.</span></span> <span data-ttu-id="23456-255">発信中のユーザーがボイスメールに送信されるように設定できます。</span><span class="sxs-lookup"><span data-stu-id="23456-255">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="23456-256">これを行うには、**社内のユーザ**を選択して、そのユーザが直接ボイスメールに転送するように設定します。</span><span class="sxs-lookup"><span data-stu-id="23456-256">To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span>

  <span data-ttu-id="23456-257">ボイスメールに必要なライセンスについては、「[クラウドボイスメール](set-up-phone-system-voicemail.md)をセットアップする」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="23456-257">To learn about licensing required for voicemail, see [Set up Cloud Voicemail](set-up-phone-system-voicemail.md).</span></span>

  - <span data-ttu-id="23456-258">**音声アプリケーション**既に作成されている通話キューまたは自動応答のいずれかに関連付けられているリソースアカウントの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="23456-258">**Voice application** Select the name of a resource account associated with either a call queue or auto attendant that has already been created.</span></span>

## <a name="change-a-users-caller-id-for-outbound-calls"></a><span data-ttu-id="23456-259">発信通話のユーザーの発信者番号認識を変更する</span><span class="sxs-lookup"><span data-stu-id="23456-259">Change a user's Caller ID for outbound calls</span></span>

<span data-ttu-id="23456-260">ユーザーの id を保護するには、 **CsCallingLineIdentity**コマンドレットを使用する代わりに、通話キュー、自動応答、または任意のサービス番号への発信通話の発信者番号を変更します。</span><span class="sxs-lookup"><span data-stu-id="23456-260">You can protect a user's identity by changing their caller ID for outbound calls to a call queue, auto attendant, or any service number instead using the **New-CsCallingLineIdentity** cmdlet.</span></span>

<span data-ttu-id="23456-261">これを行う場合は、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="23456-261">To do this, run:</span></span>

``` Powershell
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

<span data-ttu-id="23456-262">**Grant-CallingLineIdentity** コマンドレットを使用してユーザーのポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="23456-262">Then apply the policy to the user using the **Grant-CallingLineIdentity** cmdlet.</span></span> <span data-ttu-id="23456-263">これを行う場合は、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="23456-263">To do this, run:</span></span>

``` Powershell
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

<span data-ttu-id="23456-264">組織で発信者番号の設定を行う方法については、「[組織での発信者番号の使用方法](/microsoftteams/how-can-caller-id-be-used-in-your-organization)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="23456-264">You can get more information on how to set caller ID settings in your organization in the article [How can caller ID be used in your organization](/microsoftteams/how-can-caller-id-be-used-in-your-organization).</span></span>

## <a name="call-queue-cmdlets"></a><span data-ttu-id="23456-265">通話キューのコマンドレット</span><span class="sxs-lookup"><span data-stu-id="23456-265">Call queue cmdlets</span></span>

<span data-ttu-id="23456-266">Windows PowerShell を使用して通話キューを作成し、設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="23456-266">You can also use Windows PowerShell to create and set up call queues.</span></span> <span data-ttu-id="23456-267">通話キューを管理するために使用するコマンドレットを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="23456-267">Here are the cmdlets that you use to manage a call queue.</span></span>

- [<span data-ttu-id="23456-268">新規-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="23456-268">New-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="23456-269">Set-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="23456-269">Set-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/set-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="23456-270">Get-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="23456-270">Get-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/get-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="23456-271">Remove-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="23456-271">Remove-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-CsCallQueue?view=skype-ps)

### <a name="more-about-windows-powershell"></a><span data-ttu-id="23456-272">Windows PowerShell の詳細について</span><span class="sxs-lookup"><span data-stu-id="23456-272">More about Windows PowerShell</span></span>

- <span data-ttu-id="23456-273">Windows PowerShell では、ユーザーの管理と、許可または許可されていないユーザーの操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="23456-273">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="23456-274">Windows PowerShell を使用すると、複数のタスクがある場合に、1つの管理ポイントを使用して Office 365 および Microsoft Teams を管理し、日常的な作業を簡略化することができます。</span><span class="sxs-lookup"><span data-stu-id="23456-274">With Windows PowerShell, you can manage Office 365 and Microsoft Teams with a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="23456-275">Windows PowerShell の使用を開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="23456-275">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="23456-276">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="23456-276">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [<span data-ttu-id="23456-277">Office 365 PowerShell を使用する必要がある理由</span><span class="sxs-lookup"><span data-stu-id="23456-277">Why you need to use Office 365 PowerShell</span></span>](https://docs.microsoft.com/en-us/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- <span data-ttu-id="23456-278">Windows PowerShell には、多くのユーザーに対して同時に設定を変更する場合など、Microsoft Teams 管理センターでの速度、シンプルさ、生産性を高めるためのさまざまな利点があります。</span><span class="sxs-lookup"><span data-stu-id="23456-278">Windows PowerShell has many advantages in speed, simplicity, and productivity over the Microsoft Teams admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="23456-279">次のトピックでこれらの利点について説明します。</span><span class="sxs-lookup"><span data-stu-id="23456-279">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="23456-280">Windows PowerShell を使用して Office 365 を管理する</span><span class="sxs-lookup"><span data-stu-id="23456-280">Manage Office 365 with Windows PowerShell</span></span>](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [<span data-ttu-id="23456-281">Windows PowerShell 用にコンピューターをセットアップする</span><span class="sxs-lookup"><span data-stu-id="23456-281">Set up your computer for Windows PowerShell</span></span>](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a><span data-ttu-id="23456-282">関連トピック</span><span class="sxs-lookup"><span data-stu-id="23456-282">Related topics</span></span>

[<span data-ttu-id="23456-283">Office 365 の電話システムでできること</span><span class="sxs-lookup"><span data-stu-id="23456-283">Here's what you get with Phone System in Office 365</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="23456-284">サービス電話番号を取得する</span><span class="sxs-lookup"><span data-stu-id="23456-284">Getting service phone numbers</span></span>](getting-service-phone-numbers.md)

[<span data-ttu-id="23456-285">国および地域ごとの電話会議および通話プランの利用可能性</span><span class="sxs-lookup"><span data-stu-id="23456-285">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="23456-286">新しい Csonline Applicationinstance</span><span class="sxs-lookup"><span data-stu-id="23456-286">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
