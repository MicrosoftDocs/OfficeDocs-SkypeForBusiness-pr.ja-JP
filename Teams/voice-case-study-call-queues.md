---
title: チームボイスの Contoso のケーススタディ
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
description: 多国籍企業向けの Teams の音声のケーススタディ
appliesto:
- Microsoft Teams
ms.openlocfilehash: 780d812b4e6e56b28b867ace14dbf1d5f6170302
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786093"
---
# <a name="contoso-case-study-auto-attendants-and-call-queues"></a><span data-ttu-id="afba9-103">Contoso のケーススタディ: 自動応答と通話キュー</span><span class="sxs-lookup"><span data-stu-id="afba9-103">Contoso case study: Auto attendants and call queues</span></span>

<span data-ttu-id="afba9-104">Contoso は、オンプレミスの Skype for Business 展開の自動応答と通話キューに精通していました。</span><span class="sxs-lookup"><span data-stu-id="afba9-104">Contoso was familiar with auto attendants and call queues from their on-premises Skype for Business deployment.</span></span> <span data-ttu-id="afba9-105">クラウド自動応答のセットアップ方法を理解するために、[クラウド自動応答の](what-are-phone-system-auto-attendants.md)概要と[小規模ビジネスの例-自動応答のセットアップ](tutorial-org-aa.yml)に関するチュートリアルをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="afba9-105">To understand how to set up Cloud auto attendants, they reviewed [What are Cloud auto attendants?](what-are-phone-system-auto-attendants.md) and [Small business  example - Set up auto attendant tutorial](tutorial-org-aa.yml).</span></span> <span data-ttu-id="afba9-106">通話キューのセットアップに使用できるオプションの詳細については、[Contoso レビュー][クラウドの通話キューを作成](create-a-phone-system-call-queue.md)します。</span><span class="sxs-lookup"><span data-stu-id="afba9-106">To learn about the options available to set up call queues, Contoso reviewed [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>  

## <a name="requirements-depending-on-site-type"></a><span data-ttu-id="afba9-107">サイトの種類に応じた要件</span><span class="sxs-lookup"><span data-stu-id="afba9-107">Requirements depending on site type</span></span>

<span data-ttu-id="afba9-108">Contoso には、サイトの種類に応じて次の要件があります。</span><span class="sxs-lookup"><span data-stu-id="afba9-108">Depending on the site type, Contoso had the following needs:</span></span>

- <span data-ttu-id="afba9-109">サイトの種類 A: 従来の従来のテレフォニーシステム</span><span class="sxs-lookup"><span data-stu-id="afba9-109">Site Type A: Traditional legacy telephony systems</span></span> 

  <span data-ttu-id="afba9-110">[サイトの種類の場合、受付に関連付けられた電話番号を自動応答の番号として保持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="afba9-110">Site Type A needed to keep the same phone number associated with the receptionist as the number for their auto attendants.</span></span> <span data-ttu-id="afba9-111">各サイトの主要部署には、チームメンバーにルーティングされる専用の通話キューがあります。</span><span class="sxs-lookup"><span data-stu-id="afba9-111">The key departments for each of these sites would have their own call queues that would route to team members.</span></span> <span data-ttu-id="afba9-112">通話プランを使って、直通ルーティングと電話システムで電話システムを使用しているサイトが混在していました。</span><span class="sxs-lookup"><span data-stu-id="afba9-112">There was a mixture of sites that used Phone System with Direct Routing and Phone System with Calling Plans.</span></span>  

- <span data-ttu-id="afba9-113">サイトの種類 B: Skype for Business のエンタープライズボイス</span><span class="sxs-lookup"><span data-stu-id="afba9-113">Site Type B: Skype for Business Enterprise Voice</span></span> 

  <span data-ttu-id="afba9-114">サイトの種類 B には、チームへの移行に必要な既存の自動応答と通話キューがありました。</span><span class="sxs-lookup"><span data-stu-id="afba9-114">Site Type B had existing auto attendants and call queues that needed to migrate to Teams.</span></span> <span data-ttu-id="afba9-115">Contoso は、電話番号を自動応答に関連付けておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="afba9-115">Contoso needed to keep the phone numbers associated with the auto attendants.</span></span> <span data-ttu-id="afba9-116">Contoso がこれらのサイトの大部分を電話システムに移行しました。</span><span class="sxs-lookup"><span data-stu-id="afba9-116">Contoso moved the majority of these sites to Phone System with Calling Plans.</span></span> <span data-ttu-id="afba9-117">ただし、通話プランを利用できない場所では、Contoso がこれらのサイトを直接ルーティング構成に移行しました。</span><span class="sxs-lookup"><span data-stu-id="afba9-117">However, in the few locations where Calling Plans was not available, Contoso moved these sites to a Direct Routing configuration.</span></span>  

- <span data-ttu-id="afba9-118">サイトの種類 C: Skype for Business エンタープライズボイス & 従来の従来のテレフォニーシステム</span><span class="sxs-lookup"><span data-stu-id="afba9-118">Site Type C: Skype for Business Enterprise Voice & traditional legacy telephony system</span></span> 

  <span data-ttu-id="afba9-119">サイトの種類 C には、従来の従来のテレフォニーシステムに含まれていた既存の自動応答がありました。</span><span class="sxs-lookup"><span data-stu-id="afba9-119">Site Type C had existing auto attendants that resided in the traditional legacy telephony system.</span></span> <span data-ttu-id="afba9-120">このサイトの決定と構成は、サイトの種類 A と同じです。</span><span class="sxs-lookup"><span data-stu-id="afba9-120">The decisions and configurations for this site were the same as Site Type A.</span></span>   

- <span data-ttu-id="afba9-121">すべてのサイトの種類について、Contoso から以下の質問が寄せられています。</span><span class="sxs-lookup"><span data-stu-id="afba9-121">For all site types, Contoso asked the following questions:</span></span>

  - <span data-ttu-id="afba9-122">Q: 新規または既存の番号を使用しますか?</span><span class="sxs-lookup"><span data-stu-id="afba9-122">Q: Will we use new or existing numbers?</span></span> 
    <span data-ttu-id="afba9-123">A: Contoso は、自動応答のサービスアカウントに割り当てられる既存の電話番号を使用することを決定しました。</span><span class="sxs-lookup"><span data-stu-id="afba9-123">A: Contoso decided to use existing phone numbers to be assigned to the service account for the auto attendant.</span></span> 

  - <span data-ttu-id="afba9-124">Q: 自動応答はどのようなタイミングで着信を受け入れることができますか?</span><span class="sxs-lookup"><span data-stu-id="afba9-124">Q: When will the auto attendant be available to accept incoming calls?</span></span> 
    <span data-ttu-id="afba9-125">A: Contoso は、勤務時間を設定することを決定し、営業時間が "勤務時間" の自動応答にリダイレクトされた後で通話を受信することにしました。</span><span class="sxs-lookup"><span data-stu-id="afba9-125">A: Contoso decided to set business hours and have calls received after business hours redirected to an "after-hours" auto attendant.</span></span>  

  - <span data-ttu-id="afba9-126">Q: 通話キュー内のメンバーへの通話は、アテンダント、シリアル、またはラウンドロビンルーティングのどのようにルーティングされますか?</span><span class="sxs-lookup"><span data-stu-id="afba9-126">Q: How will the calls be routed to members in a call queue: attendant, serial, or round robin routing?</span></span> 
    <span data-ttu-id="afba9-127">A: Contoso は、アテンダントルーティングを使用することを決定しました。</span><span class="sxs-lookup"><span data-stu-id="afba9-127">A: Contoso decided to use Attendant routing,</span></span> 

  - <span data-ttu-id="afba9-128">Q: ユーザーが通話を受けるべきかどうかを判断する方法を教えてください。</span><span class="sxs-lookup"><span data-stu-id="afba9-128">Q: How will we determine when a user should or should not get a call?</span></span> 
    <span data-ttu-id="afba9-129">A: Contoso は、エージェントが利用可能かどうかを判断するために、通話処理オプションの使用を決定しました。プレゼンスベースのルーティング。</span><span class="sxs-lookup"><span data-stu-id="afba9-129">A: Contoso decided to use call handling options to determine if the agent is available: presence-based routing.</span></span> 


## <a name="configuration"></a><span data-ttu-id="afba9-130">構成</span><span class="sxs-lookup"><span data-stu-id="afba9-130">Configuration</span></span>

<span data-ttu-id="afba9-131">自動応答と通話キューを設定する手順については、「[リソースアカウントを管理](manage-resource-accounts.md)する」に記載されています。</span><span class="sxs-lookup"><span data-stu-id="afba9-131">The steps to set up an auto attendant and a call queue include the following outlined in [Manage resource accounts](manage-resource-accounts.md):</span></span> 

1. <span data-ttu-id="afba9-132">サービス番号を取得します。</span><span class="sxs-lookup"><span data-stu-id="afba9-132">Obtain a service number.</span></span> 

2. <span data-ttu-id="afba9-133">リソースアカウントまたは電話システムのライセンスと共に使用する、無料の電話システム仮想ユーザーライセンスまたは有料電話システムライセンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="afba9-133">Obtain a free Phone System - Virtual User license or a paid Phone System license to use with the resource account or a Phone System license.</span></span>

3. <span data-ttu-id="afba9-134">リソースアカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="afba9-134">Create the resource account.</span></span> <span data-ttu-id="afba9-135">関連付けられているリソースアカウントを持つには、自動応答または通話キューが必要です。</span><span class="sxs-lookup"><span data-stu-id="afba9-135">An auto attendant or call queue is required to have an associated resource account.</span></span> 

4. <span data-ttu-id="afba9-136">電話システムまたは電話システム仮想ユーザーライセンスをリソースアカウントに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="afba9-136">Assign the Phone System or a Phone System - Virtual user license to the resource account.</span></span> <span data-ttu-id="afba9-137">詳細については、「 [Microsoft 365 電話システム–仮想ユーザーライセンス](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/virtual-user)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="afba9-137">For more information, see [Microsoft 365 Phone System – Virtual User license](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/virtual-user).</span></span>

5. <span data-ttu-id="afba9-138">ライセンスを割り当てたリソースアカウントにサービスの電話番号を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="afba9-138">Assign a service phone number to the resource account you assigned licenses to.</span></span> 

6. <span data-ttu-id="afba9-139">電話システムの通話キューまたは自動応答を作成する</span><span class="sxs-lookup"><span data-stu-id="afba9-139">Create a Phone System call queue or auto attendant</span></span> 

7. <span data-ttu-id="afba9-140">リソースアカウントを通話キューまたは自動応答にリンクします。</span><span class="sxs-lookup"><span data-stu-id="afba9-140">Link the resource account with a call queue or auto attendant.</span></span> 


### <a name="sites-with-phone-system-with-direct-routing"></a><span data-ttu-id="afba9-141">直接ルーティングを使用する電話システムを使用しているサイト</span><span class="sxs-lookup"><span data-stu-id="afba9-141">Sites with Phone System with Direct routing</span></span> 

<span data-ttu-id="afba9-142">Contoso は、Office 365 のサービス番号として、ローカルの通信事業者から提供される電話番号を設定する必要がありました。</span><span class="sxs-lookup"><span data-stu-id="afba9-142">Contoso had to set up the phone number provided by the local carrier as the service number in Office 365.</span></span> 

- <span data-ttu-id="afba9-143">直接ルーティングによって利用可能な電話番号を設定するには、「[リソースアカウントの管理](manage-resource-accounts.md)」に記載された手順に従います。</span><span class="sxs-lookup"><span data-stu-id="afba9-143">To set up a phone number available through Direct Routing, Contoso followed the instructions located in [Manage Resource Accounts](manage-resource-accounts.md).</span></span> <span data-ttu-id="afba9-144">Office 365 はオンプレミスの電話番号を認識しないため、Contoso は PowerShell を使用してセットアップを完了します。</span><span class="sxs-lookup"><span data-stu-id="afba9-144">Because Office 365 is not aware of the on-premises phone numbers, Contoso used PowerShell to complete the setup.</span></span>   

- <span data-ttu-id="afba9-145">クラウド自動応答を構成するには、「[クラウド自動応答を設定](create-a-phone-system-auto-attendant.md)する」の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="afba9-145">To configure the Cloud auto attendant, Contoso followed the steps outlined in [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md).</span></span> 

- <span data-ttu-id="afba9-146">クラウド通話キューをセットアップするには、「[クラウド通話キューを作成](create-a-phone-system-call-queue.md)する」で説明した手順に従います。</span><span class="sxs-lookup"><span data-stu-id="afba9-146">To set up a Cloud call queue, Contoso followed the steps outlined in [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>  


### <a name="sites-with-phone-system-with-calling-plan"></a><span data-ttu-id="afba9-147">通話プランのある電話システムを使用するサイト</span><span class="sxs-lookup"><span data-stu-id="afba9-147">Sites with Phone System with Calling plan</span></span>

<span data-ttu-id="afba9-148">Contoso は、Skype for Business のエンタープライズボイス自動応答に使用された電話番号を、Office 365 電話システムに移植する必要がありました。</span><span class="sxs-lookup"><span data-stu-id="afba9-148">Contoso had to port the phone number that was used for Skype for Business Enterprise Voice auto attendants to Office 365 Phone System.</span></span> <span data-ttu-id="afba9-149">これにより、自動応答として使用するために、同じ番号をサービス番号として割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="afba9-149">This allowed the same number to be assigned as a service number for use as an auto attendant.</span></span> 

- <span data-ttu-id="afba9-150">電話番号を移植するには、「会社[に電話番号を移行](https://docs.microsoft.com/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams)する」の指示に従って、「[組織の電話番号を管理](https://docs.microsoft.com/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)する」で追加のガイダンスを入手します。</span><span class="sxs-lookup"><span data-stu-id="afba9-150">To port the phone number, Contoso followed the instructions in [Transfer phone numbers to Teams](https://docs.microsoft.com/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams) and obtained additional guidance at [Manage phone numbers for your organization](https://docs.microsoft.com/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization).</span></span>

- <span data-ttu-id="afba9-151">クラウド自動応答を構成するには、「[クラウド自動応答を設定](create-a-phone-system-auto-attendant.md)する」の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="afba9-151">To configure a Cloud auto attendant, Contoso followed the steps outlined in [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md).</span></span>

-  <span data-ttu-id="afba9-152">クラウド通話キューをセットアップするには、「[クラウド通話キューを作成](create-a-phone-system-call-queue.md)する」で説明した手順に従います。</span><span class="sxs-lookup"><span data-stu-id="afba9-152">To set up a Cloud call queue, Contoso followed the steps outlined in [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>  

 