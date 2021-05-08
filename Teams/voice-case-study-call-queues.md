---
title: Teams Contoso のケース スタディ
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: Teams企業向け音声ケース スタディ
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0cb8029a8f4e979a76afe069ee9b22e7be897913
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121295"
---
# <a name="contoso-case-study-auto-attendants-and-call-queues"></a><span data-ttu-id="dac4a-103">Contoso のケース スタディ: 自動応答と通話キュー</span><span class="sxs-lookup"><span data-stu-id="dac4a-103">Contoso case study: Auto attendants and call queues</span></span>

<span data-ttu-id="dac4a-104">Contoso は、オンプレミスのサービスのデプロイから自動応答と通話キューをSkype for Businessでした。</span><span class="sxs-lookup"><span data-stu-id="dac4a-104">Contoso was familiar with auto attendants and call queues from their on-premises Skype for Business deployment.</span></span> <span data-ttu-id="dac4a-105">クラウド自動応答と通話キューを設定する方法を理解するために、「自動応答と通話キューの計画Teams」[を確認しました](plan-auto-attendant-call-queue.md)。</span><span class="sxs-lookup"><span data-stu-id="dac4a-105">To understand how to set up Cloud auto attendants and call queues, they reviewed [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md).</span></span>

## <a name="requirements-depending-on-site-type"></a><span data-ttu-id="dac4a-106">サイトの種類に応じて要件</span><span class="sxs-lookup"><span data-stu-id="dac4a-106">Requirements depending on site type</span></span>

<span data-ttu-id="dac4a-107">サイトの種類に応じて、Contoso には次のニーズがありました。</span><span class="sxs-lookup"><span data-stu-id="dac4a-107">Depending on the site type, Contoso had the following needs:</span></span>

- <span data-ttu-id="dac4a-108">サイトの種類 A: 従来のレガシ テレフォニー システム</span><span class="sxs-lookup"><span data-stu-id="dac4a-108">Site Type A: Traditional legacy telephony systems</span></span> 

  <span data-ttu-id="dac4a-109">サイトの種類 A は、受付に関連付けられている電話番号を、自動応答の番号と同じに維持するために必要です。</span><span class="sxs-lookup"><span data-stu-id="dac4a-109">Site Type A needed to keep the same phone number associated with the receptionist as the number for their auto attendants.</span></span> <span data-ttu-id="dac4a-110">これらの各サイトの主要な部門には、チーム メンバーにルーティングされる独自の呼び出しキューがあります。</span><span class="sxs-lookup"><span data-stu-id="dac4a-110">The key departments for each of these sites would have their own call queues that would route to team members.</span></span> <span data-ttu-id="dac4a-111">直接ルーティングと呼び出しプランで電話システムサイトが電話システムいました。</span><span class="sxs-lookup"><span data-stu-id="dac4a-111">There was a mixture of sites that used Phone System with Direct Routing and Phone System with Calling Plans.</span></span>  

- <span data-ttu-id="dac4a-112">サイトの種類 B: Skype for Business エンタープライズ VoIP</span><span class="sxs-lookup"><span data-stu-id="dac4a-112">Site Type B: Skype for Business Enterprise Voice</span></span> 

  <span data-ttu-id="dac4a-113">サイトタイプ B には、既存の自動応答と通話キューが含み、このキューをサイトに移行する必要Teams。</span><span class="sxs-lookup"><span data-stu-id="dac4a-113">Site Type B had existing auto attendants and call queues that needed to migrate to Teams.</span></span> <span data-ttu-id="dac4a-114">Contoso は、自動応答に関連付けられている電話番号を保持する必要がありました。</span><span class="sxs-lookup"><span data-stu-id="dac4a-114">Contoso needed to keep the phone numbers associated with the auto attendants.</span></span> <span data-ttu-id="dac4a-115">Contoso は、これらのサイトの大部分を通話プラン電話システムに移動しました。</span><span class="sxs-lookup"><span data-stu-id="dac4a-115">Contoso moved the majority of these sites to Phone System with Calling Plans.</span></span> <span data-ttu-id="dac4a-116">ただし、通話プランを利用できないいくつかの場所で、Contoso はこれらのサイトを直接ルーティング構成に移動しました。</span><span class="sxs-lookup"><span data-stu-id="dac4a-116">However, in the few locations where Calling Plans was not available, Contoso moved these sites to a Direct Routing configuration.</span></span>  

- <span data-ttu-id="dac4a-117">サイトの種類 C: Skype for Business エンタープライズ VoIP &レガシ テレフォニー システム</span><span class="sxs-lookup"><span data-stu-id="dac4a-117">Site Type C: Skype for Business Enterprise Voice & traditional legacy telephony system</span></span> 

  <span data-ttu-id="dac4a-118">サイト タイプ C には、従来のレガシ テレフォニー システムに存在する既存の自動応答がありました。</span><span class="sxs-lookup"><span data-stu-id="dac4a-118">Site Type C had existing auto attendants that resided in the traditional legacy telephony system.</span></span> <span data-ttu-id="dac4a-119">このサイトの決定と構成は、サイトタイプ A と同じでした。</span><span class="sxs-lookup"><span data-stu-id="dac4a-119">The decisions and configurations for this site were the same as Site Type A.</span></span>   

- <span data-ttu-id="dac4a-120">すべてのサイトの種類について、Contoso は次の質問をしました。</span><span class="sxs-lookup"><span data-stu-id="dac4a-120">For all site types, Contoso asked the following questions:</span></span>

  - <span data-ttu-id="dac4a-121">Q: 新規または既存の数値を使用しますか。</span><span class="sxs-lookup"><span data-stu-id="dac4a-121">Q: Will we use new or existing numbers?</span></span> 
    <span data-ttu-id="dac4a-122">A: Contoso は、自動応答のサービス アカウントに割り当てる既存の電話番号を使用することを決定しました。</span><span class="sxs-lookup"><span data-stu-id="dac4a-122">A: Contoso decided to use existing phone numbers to be assigned to the service account for the auto attendant.</span></span> 

  - <span data-ttu-id="dac4a-123">Q: 着信通話を受け入れる自動応答を利用できるのは、いつですか。</span><span class="sxs-lookup"><span data-stu-id="dac4a-123">Q: When will the auto attendant be available to accept incoming calls?</span></span> 
    <span data-ttu-id="dac4a-124">A: Contoso は営業時間を設定し、営業時間後に "時間外" 自動応答にリダイレクトされた通話を受信しました。</span><span class="sxs-lookup"><span data-stu-id="dac4a-124">A: Contoso decided to set business hours and have calls received after business hours redirected to an "after-hours" auto attendant.</span></span>  

  - <span data-ttu-id="dac4a-125">Q: 呼び出しは、応答、シリアル、ラウンド ロビン ルーティングの呼び出しキュー内のメンバーにルーティングされますか。</span><span class="sxs-lookup"><span data-stu-id="dac4a-125">Q: How will the calls be routed to members in a call queue: attendant, serial, or round robin routing?</span></span> 
    <span data-ttu-id="dac4a-126">A: Contoso は、アテンダント ルーティングを使用することを決定しました。</span><span class="sxs-lookup"><span data-stu-id="dac4a-126">A: Contoso decided to use Attendant routing,</span></span> 

  - <span data-ttu-id="dac4a-127">Q: ユーザーが通話を受け取る必要があるかどうかは、どのように判断しますか。</span><span class="sxs-lookup"><span data-stu-id="dac4a-127">Q: How will we determine when a user should or should not get a call?</span></span> 
    <span data-ttu-id="dac4a-128">A: Contoso は、通話処理オプションを使用して、エージェントが使用可能かどうかを判断することを決定しました。プレゼンス ベースのルーティングです。</span><span class="sxs-lookup"><span data-stu-id="dac4a-128">A: Contoso decided to use call handling options to determine if the agent is available: presence-based routing.</span></span> 


## <a name="configuration"></a><span data-ttu-id="dac4a-129">構成</span><span class="sxs-lookup"><span data-stu-id="dac4a-129">Configuration</span></span>

<span data-ttu-id="dac4a-130">自動応答と通話キューを設定する手順については、リソース アカウントの管理に関するページ [で説明されています](manage-resource-accounts.md)。</span><span class="sxs-lookup"><span data-stu-id="dac4a-130">The steps to set up an auto attendant and a call queue include the following outlined in [Manage resource accounts](manage-resource-accounts.md):</span></span> 

1. <span data-ttu-id="dac4a-131">サービス番号を取得します。</span><span class="sxs-lookup"><span data-stu-id="dac4a-131">Obtain a service number.</span></span> 

2. <span data-ttu-id="dac4a-132">無料の電話システム - 仮想ユーザー ライセンスまたは有料の 電話システム ライセンスを取得して、リソース アカウントまたはリソース ライセンスで使用電話システムします。</span><span class="sxs-lookup"><span data-stu-id="dac4a-132">Obtain a free Phone System - Virtual User license or a paid Phone System license to use with the resource account or a Phone System license.</span></span>

3. <span data-ttu-id="dac4a-133">リソース アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="dac4a-133">Create the resource account.</span></span> <span data-ttu-id="dac4a-134">自動応答または通話キューは、関連付けられているリソース アカウントを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="dac4a-134">An auto attendant or call queue is required to have an associated resource account.</span></span> 

4. <span data-ttu-id="dac4a-135">リソース アカウント電話システムまたは仮想電話システム - 仮想ユーザー ライセンスを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="dac4a-135">Assign the Phone System or a Phone System - Virtual user license to the resource account.</span></span> <span data-ttu-id="dac4a-136">詳細については、「仮想ユーザー ライセンス[Microsoft 365 電話システム 」 を参照してください](./teams-add-on-licensing/virtual-user.md)。</span><span class="sxs-lookup"><span data-stu-id="dac4a-136">For more information, see [Microsoft 365 Phone System – Virtual User license](./teams-add-on-licensing/virtual-user.md).</span></span>

5. <span data-ttu-id="dac4a-137">ライセンスを割り当てたリソース アカウントにサービス電話番号を割り当てる。</span><span class="sxs-lookup"><span data-stu-id="dac4a-137">Assign a service phone number to the resource account you assigned licenses to.</span></span> 

6. <span data-ttu-id="dac4a-138">通話キュー電話システム自動応答を作成する</span><span class="sxs-lookup"><span data-stu-id="dac4a-138">Create a Phone System call queue or auto attendant</span></span> 

7. <span data-ttu-id="dac4a-139">リソース アカウントを通話キューまたは自動応答にリンクします。</span><span class="sxs-lookup"><span data-stu-id="dac4a-139">Link the resource account with a call queue or auto attendant.</span></span> 


### <a name="sites-with-phone-system-with-direct-routing"></a><span data-ttu-id="dac4a-140">直接ルーティングを電話システムサイト</span><span class="sxs-lookup"><span data-stu-id="dac4a-140">Sites with Phone System with Direct routing</span></span> 

<span data-ttu-id="dac4a-141">Contoso は、ローカル通信会社から提供された電話番号を、サービス番号として設定する必要Office 365。</span><span class="sxs-lookup"><span data-stu-id="dac4a-141">Contoso had to set up the phone number provided by the local carrier as the service number in Office 365.</span></span> 

- <span data-ttu-id="dac4a-142">直接ルーティングで利用できる電話番号を設定するために、Contoso は「リソース アカウントの管理」にある手順 [に従いました](manage-resource-accounts.md)。</span><span class="sxs-lookup"><span data-stu-id="dac4a-142">To set up a phone number available through Direct Routing, Contoso followed the instructions located in [Manage Resource Accounts](manage-resource-accounts.md).</span></span> <span data-ttu-id="dac4a-143">オンプレミスOffice 365を認識していないので、Contoso は PowerShell を使用してセットアップを完了しました。</span><span class="sxs-lookup"><span data-stu-id="dac4a-143">Because Office 365 is not aware of the on-premises phone numbers, Contoso used PowerShell to complete the setup.</span></span>   

- <span data-ttu-id="dac4a-144">クラウド自動応答を構成するために、Contoso は「クラウド自動応答を設定する」で説明 [されている手順に従いました](create-a-phone-system-auto-attendant.md)。</span><span class="sxs-lookup"><span data-stu-id="dac4a-144">To configure the Cloud auto attendant, Contoso followed the steps outlined in [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md).</span></span> 

- <span data-ttu-id="dac4a-145">クラウド通話キューを設定するために、Contoso は「クラウド通話キューを作成する」で説明 [されている手順に従いました](create-a-phone-system-call-queue.md)。</span><span class="sxs-lookup"><span data-stu-id="dac4a-145">To set up a Cloud call queue, Contoso followed the steps outlined in [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>  


### <a name="sites-with-phone-system-with-calling-plan"></a><span data-ttu-id="dac4a-146">通話プラン電話システムサイト</span><span class="sxs-lookup"><span data-stu-id="dac4a-146">Sites with Phone System with Calling plan</span></span>

<span data-ttu-id="dac4a-147">Contoso は、自動応答に使用された電話番号をSkype for Business エンタープライズ VoIPに移行Office 365 電話システム。</span><span class="sxs-lookup"><span data-stu-id="dac4a-147">Contoso had to port the phone number that was used for Skype for Business Enterprise Voice auto attendants to Office 365 Phone System.</span></span> <span data-ttu-id="dac4a-148">これにより、自動応答として使用するサービス番号として同じ番号を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="dac4a-148">This allowed the same number to be assigned as a service number for use as an auto attendant.</span></span> 

- <span data-ttu-id="dac4a-149">Contoso は、電話番号を移行するために、「電話番号を Teams[](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md)に転送する」の手順に従い、「組織の電話番号を管理する」で追加のガイダンス[を取得しました](./manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="dac4a-149">To port the phone number, Contoso followed the instructions in [Transfer phone numbers to Teams](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md) and obtained additional guidance at [Manage phone numbers for your organization](./manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).</span></span>

- <span data-ttu-id="dac4a-150">クラウド自動応答を構成するために、Contoso は「クラウド自動応答を設定する」で [説明されている手順に従いました](create-a-phone-system-auto-attendant.md)。</span><span class="sxs-lookup"><span data-stu-id="dac4a-150">To configure a Cloud auto attendant, Contoso followed the steps outlined in [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md).</span></span>

-  <span data-ttu-id="dac4a-151">クラウド通話キューを設定するために、Contoso は「クラウド通話キューを作成する」で説明 [されている手順に従いました](create-a-phone-system-call-queue.md)。</span><span class="sxs-lookup"><span data-stu-id="dac4a-151">To set up a Cloud call queue, Contoso followed the steps outlined in [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>  

