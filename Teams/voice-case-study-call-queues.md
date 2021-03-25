---
title: Teams の音声 Contoso のケース スタディ
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
description: 多国籍企業向け Teams 音声ケース スタディ
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0cb8029a8f4e979a76afe069ee9b22e7be897913
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121295"
---
# <a name="contoso-case-study-auto-attendants-and-call-queues"></a><span data-ttu-id="1d3a4-103">Contoso のケース スタディ: 自動応答と通話キュー</span><span class="sxs-lookup"><span data-stu-id="1d3a4-103">Contoso case study: Auto attendants and call queues</span></span>

<span data-ttu-id="1d3a4-104">Contoso は、オンプレミスの Skype for Business 展開からの自動応答と通話キューに慣れ親しんでいます。</span><span class="sxs-lookup"><span data-stu-id="1d3a4-104">Contoso was familiar with auto attendants and call queues from their on-premises Skype for Business deployment.</span></span> <span data-ttu-id="1d3a4-105">クラウド自動応答と通話キューを設定する方法を理解するために、Teams の自動応答と通話キューのプラン [を確認しました](plan-auto-attendant-call-queue.md)。</span><span class="sxs-lookup"><span data-stu-id="1d3a4-105">To understand how to set up Cloud auto attendants and call queues, they reviewed [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md).</span></span>

## <a name="requirements-depending-on-site-type"></a><span data-ttu-id="1d3a4-106">サイトの種類に応じて要件</span><span class="sxs-lookup"><span data-stu-id="1d3a4-106">Requirements depending on site type</span></span>

<span data-ttu-id="1d3a4-107">サイトの種類に応じて、Contoso には次のニーズがありました。</span><span class="sxs-lookup"><span data-stu-id="1d3a4-107">Depending on the site type, Contoso had the following needs:</span></span>

- <span data-ttu-id="1d3a4-108">サイトの種類 A: 従来のレガシ テレフォニー システム</span><span class="sxs-lookup"><span data-stu-id="1d3a4-108">Site Type A: Traditional legacy telephony systems</span></span> 

  <span data-ttu-id="1d3a4-109">受付係に関連付けられているのと同じ電話番号を自動応答の番号として保持するために必要なサイトタイプ A。</span><span class="sxs-lookup"><span data-stu-id="1d3a4-109">Site Type A needed to keep the same phone number associated with the receptionist as the number for their auto attendants.</span></span> <span data-ttu-id="1d3a4-110">これらの各サイトの主要な部門には、チーム メンバーにルーティングされる独自の通話キューがあります。</span><span class="sxs-lookup"><span data-stu-id="1d3a4-110">The key departments for each of these sites would have their own call queues that would route to team members.</span></span> <span data-ttu-id="1d3a4-111">直接ルーティングを使用した電話システムと通話プラン付き電話システムを使用するサイトが混同されています。</span><span class="sxs-lookup"><span data-stu-id="1d3a4-111">There was a mixture of sites that used Phone System with Direct Routing and Phone System with Calling Plans.</span></span>  

- <span data-ttu-id="1d3a4-112">サイトの種類 B: Skype for Business エンタープライズ VoIP</span><span class="sxs-lookup"><span data-stu-id="1d3a4-112">Site Type B: Skype for Business Enterprise Voice</span></span> 

  <span data-ttu-id="1d3a4-113">サイトの種類 B には、Teams への移行に必要な既存の自動応答と通話キューがありました。</span><span class="sxs-lookup"><span data-stu-id="1d3a4-113">Site Type B had existing auto attendants and call queues that needed to migrate to Teams.</span></span> <span data-ttu-id="1d3a4-114">Contoso は、自動応答に関連付けられている電話番号を保持する必要がありました。</span><span class="sxs-lookup"><span data-stu-id="1d3a4-114">Contoso needed to keep the phone numbers associated with the auto attendants.</span></span> <span data-ttu-id="1d3a4-115">Contoso は、これらのサイトの大部分を通話プランを使用する電話システムに移行しました。</span><span class="sxs-lookup"><span data-stu-id="1d3a4-115">Contoso moved the majority of these sites to Phone System with Calling Plans.</span></span> <span data-ttu-id="1d3a4-116">ただし、通話プランを利用できないいくつかの場所で、Contoso はこれらのサイトを直接ルーティング構成に移動しました。</span><span class="sxs-lookup"><span data-stu-id="1d3a4-116">However, in the few locations where Calling Plans was not available, Contoso moved these sites to a Direct Routing configuration.</span></span>  

- <span data-ttu-id="1d3a4-117">サイトの種類 C: Skype for Business エンタープライズ VoIP &従来のテレフォニー システム</span><span class="sxs-lookup"><span data-stu-id="1d3a4-117">Site Type C: Skype for Business Enterprise Voice & traditional legacy telephony system</span></span> 

  <span data-ttu-id="1d3a4-118">サイトの種類 C には、従来のレガシ テレフォニー システムに存在する既存の自動応答がありました。</span><span class="sxs-lookup"><span data-stu-id="1d3a4-118">Site Type C had existing auto attendants that resided in the traditional legacy telephony system.</span></span> <span data-ttu-id="1d3a4-119">このサイトの決定と構成は、サイトの種類 A と同じでした。</span><span class="sxs-lookup"><span data-stu-id="1d3a4-119">The decisions and configurations for this site were the same as Site Type A.</span></span>   

- <span data-ttu-id="1d3a4-120">すべてのサイトの種類について、Contoso は次の質問をしました。</span><span class="sxs-lookup"><span data-stu-id="1d3a4-120">For all site types, Contoso asked the following questions:</span></span>

  - <span data-ttu-id="1d3a4-121">Q: 新しい数値または既存の数値を使用しますか?</span><span class="sxs-lookup"><span data-stu-id="1d3a4-121">Q: Will we use new or existing numbers?</span></span> 
    <span data-ttu-id="1d3a4-122">A: Contoso は、自動応答のサービス アカウントに割り当てる既存の電話番号を使用することを決定しました。</span><span class="sxs-lookup"><span data-stu-id="1d3a4-122">A: Contoso decided to use existing phone numbers to be assigned to the service account for the auto attendant.</span></span> 

  - <span data-ttu-id="1d3a4-123">Q: 着信通話を受け取る自動応答は、いつ利用できますか?</span><span class="sxs-lookup"><span data-stu-id="1d3a4-123">Q: When will the auto attendant be available to accept incoming calls?</span></span> 
    <span data-ttu-id="1d3a4-124">A: Contoso は営業時間を設定し、営業時間が "営業時間外" の自動応答にリダイレクトされた後に着信を受信しました。</span><span class="sxs-lookup"><span data-stu-id="1d3a4-124">A: Contoso decided to set business hours and have calls received after business hours redirected to an "after-hours" auto attendant.</span></span>  

  - <span data-ttu-id="1d3a4-125">Q: 通話キュー内のメンバー (アテンダント、シリアル、ラウンド ロビン ルーティング) に通話をルーティングする方法</span><span class="sxs-lookup"><span data-stu-id="1d3a4-125">Q: How will the calls be routed to members in a call queue: attendant, serial, or round robin routing?</span></span> 
    <span data-ttu-id="1d3a4-126">A: Contoso はアテンダント ルーティングを使用することを決定しました。</span><span class="sxs-lookup"><span data-stu-id="1d3a4-126">A: Contoso decided to use Attendant routing,</span></span> 

  - <span data-ttu-id="1d3a4-127">Q: ユーザーがいついつ通話を受けるべきか、それとも受けるべきでないのかを判断するにはどうすればいいでしょうか。</span><span class="sxs-lookup"><span data-stu-id="1d3a4-127">Q: How will we determine when a user should or should not get a call?</span></span> 
    <span data-ttu-id="1d3a4-128">A: Contoso は、エージェントが利用可能かどうかを判断するために通話処理オプションを使用することを決定しました。プレゼンス ベースのルーティング。</span><span class="sxs-lookup"><span data-stu-id="1d3a4-128">A: Contoso decided to use call handling options to determine if the agent is available: presence-based routing.</span></span> 


## <a name="configuration"></a><span data-ttu-id="1d3a4-129">構成</span><span class="sxs-lookup"><span data-stu-id="1d3a4-129">Configuration</span></span>

<span data-ttu-id="1d3a4-130">自動応答と通話キューを設定する手順については、「リソース アカウントを管理する」で説明されている [次の手順が含まれます](manage-resource-accounts.md)。</span><span class="sxs-lookup"><span data-stu-id="1d3a4-130">The steps to set up an auto attendant and a call queue include the following outlined in [Manage resource accounts](manage-resource-accounts.md):</span></span> 

1. <span data-ttu-id="1d3a4-131">サービス番号を取得します。</span><span class="sxs-lookup"><span data-stu-id="1d3a4-131">Obtain a service number.</span></span> 

2. <span data-ttu-id="1d3a4-132">無料の電話システム - 仮想ユーザー ライセンスまたは有料の電話システム ライセンスを取得して、リソース アカウントまたは電話システム ライセンスで使用します。</span><span class="sxs-lookup"><span data-stu-id="1d3a4-132">Obtain a free Phone System - Virtual User license or a paid Phone System license to use with the resource account or a Phone System license.</span></span>

3. <span data-ttu-id="1d3a4-133">リソース アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="1d3a4-133">Create the resource account.</span></span> <span data-ttu-id="1d3a4-134">自動応答または通話キューは、関連付けられたリソース アカウントを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="1d3a4-134">An auto attendant or call queue is required to have an associated resource account.</span></span> 

4. <span data-ttu-id="1d3a4-135">電話システムまたは電話システム - 仮想ユーザー ライセンスをリソース アカウントに割り当てる。</span><span class="sxs-lookup"><span data-stu-id="1d3a4-135">Assign the Phone System or a Phone System - Virtual user license to the resource account.</span></span> <span data-ttu-id="1d3a4-136">詳細については [、「Microsoft 365 電話システム - 仮想ユーザー ライセンス」を参照してください](./teams-add-on-licensing/virtual-user.md)。</span><span class="sxs-lookup"><span data-stu-id="1d3a4-136">For more information, see [Microsoft 365 Phone System – Virtual User license](./teams-add-on-licensing/virtual-user.md).</span></span>

5. <span data-ttu-id="1d3a4-137">ライセンスを割り当てたリソース アカウントにサービス電話番号を割り当てる。</span><span class="sxs-lookup"><span data-stu-id="1d3a4-137">Assign a service phone number to the resource account you assigned licenses to.</span></span> 

6. <span data-ttu-id="1d3a4-138">電話システム通話キューまたは自動応答を作成する</span><span class="sxs-lookup"><span data-stu-id="1d3a4-138">Create a Phone System call queue or auto attendant</span></span> 

7. <span data-ttu-id="1d3a4-139">リソース アカウントを通話キューまたは自動応答にリンクします。</span><span class="sxs-lookup"><span data-stu-id="1d3a4-139">Link the resource account with a call queue or auto attendant.</span></span> 


### <a name="sites-with-phone-system-with-direct-routing"></a><span data-ttu-id="1d3a4-140">直接ルーティングが設定された電話システムを使用するサイト</span><span class="sxs-lookup"><span data-stu-id="1d3a4-140">Sites with Phone System with Direct routing</span></span> 

<span data-ttu-id="1d3a4-141">Contoso は、365 年 365 日にローカルの通信事業者から提供された電話番号をサービス番号としてOffice必要でした。</span><span class="sxs-lookup"><span data-stu-id="1d3a4-141">Contoso had to set up the phone number provided by the local carrier as the service number in Office 365.</span></span> 

- <span data-ttu-id="1d3a4-142">Contoso は、直接ルーティングで利用できる電話番号を設定するために、「リソース アカウントの管理」の手順 [に従いました](manage-resource-accounts.md)。</span><span class="sxs-lookup"><span data-stu-id="1d3a4-142">To set up a phone number available through Direct Routing, Contoso followed the instructions located in [Manage Resource Accounts](manage-resource-accounts.md).</span></span> <span data-ttu-id="1d3a4-143">365 Officeオンプレミスの電話番号を認識していないので、Contoso は PowerShell を使用してセットアップを完了しました。</span><span class="sxs-lookup"><span data-stu-id="1d3a4-143">Because Office 365 is not aware of the on-premises phone numbers, Contoso used PowerShell to complete the setup.</span></span>   

- <span data-ttu-id="1d3a4-144">クラウド自動応答を構成するには、「クラウド自動応答を設定する」で説明されている手順 [に従います](create-a-phone-system-auto-attendant.md)。</span><span class="sxs-lookup"><span data-stu-id="1d3a4-144">To configure the Cloud auto attendant, Contoso followed the steps outlined in [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md).</span></span> 

- <span data-ttu-id="1d3a4-145">クラウド通話キューを設定するには、「クラウド通話キューを作成する」で説明されている手順 [に従います](create-a-phone-system-call-queue.md)。</span><span class="sxs-lookup"><span data-stu-id="1d3a4-145">To set up a Cloud call queue, Contoso followed the steps outlined in [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>  


### <a name="sites-with-phone-system-with-calling-plan"></a><span data-ttu-id="1d3a4-146">通話プランが設定された電話システムを使用するサイト</span><span class="sxs-lookup"><span data-stu-id="1d3a4-146">Sites with Phone System with Calling plan</span></span>

<span data-ttu-id="1d3a4-147">Contoso は、Skype for Business の自動応答に使用された電話番号を 365 エンタープライズ VoIP 365 電話システムOffice移行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1d3a4-147">Contoso had to port the phone number that was used for Skype for Business Enterprise Voice auto attendants to Office 365 Phone System.</span></span> <span data-ttu-id="1d3a4-148">これにより、自動応答として使用するサービス番号として同じ番号を割り当てる必要がありました。</span><span class="sxs-lookup"><span data-stu-id="1d3a4-148">This allowed the same number to be assigned as a service number for use as an auto attendant.</span></span> 

- <span data-ttu-id="1d3a4-149">電話番号を移行するために、Contoso は [「電話番号](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md) を Teams に移行する」の手順に従い、組織の電話番号の管理に関する追加のガイダンス [を取得しました](./manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="1d3a4-149">To port the phone number, Contoso followed the instructions in [Transfer phone numbers to Teams](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md) and obtained additional guidance at [Manage phone numbers for your organization](./manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).</span></span>

- <span data-ttu-id="1d3a4-150">クラウド自動応答を構成するには、「クラウド自動応答を設定する」で説明されている [手順に従います](create-a-phone-system-auto-attendant.md)。</span><span class="sxs-lookup"><span data-stu-id="1d3a4-150">To configure a Cloud auto attendant, Contoso followed the steps outlined in [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md).</span></span>

-  <span data-ttu-id="1d3a4-151">クラウド通話キューを設定するには、「クラウド通話キューを作成する」で説明されている手順 [に従います](create-a-phone-system-call-queue.md)。</span><span class="sxs-lookup"><span data-stu-id="1d3a4-151">To set up a Cloud call queue, Contoso followed the steps outlined in [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>  

