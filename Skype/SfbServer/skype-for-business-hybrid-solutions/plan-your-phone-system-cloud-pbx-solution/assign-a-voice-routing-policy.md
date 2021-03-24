---
title: 音声ルーティング ポリシーの割り当て
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: c7f78f23-b74f-402f-bedb-4cc308718f5b
description: '概要: このトピックを参照して、オンプレミス PSTN 接続を使用して電話システムを使用するユーザーに音声ポリシーを割り当てる方法について説明します。'
ms.openlocfilehash: 43e2b560cc0886bacd6faaec6c113ee1f237eff7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092965"
---
# <a name="assign-a-voice-routing-policy"></a><span data-ttu-id="5a65e-103">音声ルーティング ポリシーの割り当て</span><span class="sxs-lookup"><span data-stu-id="5a65e-103">Assign a Voice Routing Policy</span></span>
 
> [!Important]
> <span data-ttu-id="5a65e-104">Skype for Business Online は 2021 年 7 月 31 日に廃止され、その後サービスにアクセスできなくなりました。</span><span class="sxs-lookup"><span data-stu-id="5a65e-104">Skype for Business Online will be retired on July 31, 2021 after which the service will no longer be accessible.</span></span>  <span data-ttu-id="5a65e-105">さらに、Skype for Business Server または Cloud Connector Edition と Skype for Business Online を介したオンプレミス環境間の PSTN 接続はサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="5a65e-105">In addition, PSTN connectivity between your on-premises environment whether through Skype for Business Server or Cloud Connector Edition and Skype for Business Online will no longer be supported.</span></span>  <span data-ttu-id="5a65e-106">直接ルーティングを使用してオンプレミスのテレフォニー ネットワークを Teams に接続する方法 [について説明します](/MicrosoftTeams/direct-routing-landing-page)。</span><span class="sxs-lookup"><span data-stu-id="5a65e-106">Learn how to connect your on-premises telephony network to Teams using [Direct Routing](/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="5a65e-107">**概要:** このトピックでは、オンプレミスの PSTN 接続を使用して電話システムを使用するユーザーに音声ポリシーを割り当てる方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5a65e-107">**Summary:** Read this topic to learn how to assign a voice policy for users using Phone System with on-premises PSTN connectivity.</span></span> 
  
<span data-ttu-id="5a65e-108">ユーザーが Skype for Business Online に接続し、オンプレミスの PSTN 接続で電話システムを使用すると、2 つの音声ポリシーが適用されます。</span><span class="sxs-lookup"><span data-stu-id="5a65e-108">Once a user is on Skype for Business Online and using Phone System with on-premises PSTN connectivity, two voice policies will apply to them.</span></span> <span data-ttu-id="5a65e-109">1 つは、オンプレミスで割り当てるオンプレミスの音声ルーティング ポリシーです。</span><span class="sxs-lookup"><span data-stu-id="5a65e-109">One is an on-premises voice routing policy that you will assign on premises.</span></span> <span data-ttu-id="5a65e-110">このポリシーはグローバルまたはユーザー固有で、ユーザーに関連付けられている PSTN 使用法レコードを定義します。</span><span class="sxs-lookup"><span data-stu-id="5a65e-110">This policy can be global or user-specific and defines what PSTN usage records are associated with the user.</span></span> <span data-ttu-id="5a65e-111">このトピックでは、このポリシーを割り当てる方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5a65e-111">This topic explains how to assign this policy.</span></span>
  
<span data-ttu-id="5a65e-112">他の音声ポリシーでは、ユーザーが使用できる通話機能を定義します。この音声ポリシーは Microsoft によって定義され、オンプレミスの PSTN 接続ユーザーを持つすべての電話システムで同じです。</span><span class="sxs-lookup"><span data-stu-id="5a65e-112">The other voice policy defines what calling features are available to the user; this voice policy is defined by Microsoft and is identical for all Phone System with on-premises PSTN connectivity users.</span></span> <span data-ttu-id="5a65e-113">電話システム のユーザーに自動的に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="5a65e-113">It is automatically assigned to Phone System users.</span></span>
  
||<span data-ttu-id="5a65e-114">**オンプレミス ユーザー**</span><span class="sxs-lookup"><span data-stu-id="5a65e-114">**On-premises user**</span></span>|<span data-ttu-id="5a65e-115">**オンプレミスの PSTN 接続ユーザーを持つ電話システム**</span><span class="sxs-lookup"><span data-stu-id="5a65e-115">**Phone System with on-premises PSTN connectivity user**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5a65e-116">で定義された機能の呼び出し</span><span class="sxs-lookup"><span data-stu-id="5a65e-116">Calling features defined in</span></span>  <br/> |<span data-ttu-id="5a65e-117">音声ポリシー</span><span class="sxs-lookup"><span data-stu-id="5a65e-117">Voice policy</span></span>  <br/> |<span data-ttu-id="5a65e-118">ユーザーが電話システムのライセンスを取得するときに自動的に割り当てられる、定義済みの音声ポリシー。</span><span class="sxs-lookup"><span data-stu-id="5a65e-118">Pre-defined voice policy, assigned automatically when the user is licensed for Phone System.</span></span>  <br/> |
|<span data-ttu-id="5a65e-119">関連付けられた PSTN 使用法レコード</span><span class="sxs-lookup"><span data-stu-id="5a65e-119">PSTN usage records associated with</span></span>  <br/> |<span data-ttu-id="5a65e-120">音声ポリシー</span><span class="sxs-lookup"><span data-stu-id="5a65e-120">Voice policy</span></span>  <br/> |<span data-ttu-id="5a65e-121">ユーザーがまだオンプレミスに存在している間に割り当てられた音声ルーティング ポリシー。</span><span class="sxs-lookup"><span data-stu-id="5a65e-121">Voice routing policy, assigned while the user is still homed on-premises.</span></span>  <br/> |
   
<span data-ttu-id="5a65e-122">ユーザーがオンプレミス展開にまだ存在している間、オンプレミス展開を使用して次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="5a65e-122">You perform the following steps using your on-premises deployment, while the user is still homed in the on-premises deployment.</span></span>
  
## <a name="using-a-global-voice-routing-policy"></a><span data-ttu-id="5a65e-123">グローバル音声ルーティング ポリシーの使用</span><span class="sxs-lookup"><span data-stu-id="5a65e-123">Using a global voice routing policy</span></span>

<span data-ttu-id="5a65e-124">オンプレミスの PSTN 接続ユーザーと電話システムのグローバル音声ルーティング ポリシーを使用する前に、PSTN 使用法レコードをポリシーに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a65e-124">Before using a global voice routing policy for your Phone System with on-premises PSTN connectivity users, you must add PSTN usage records to the policy.</span></span>
  
### <a name="to-assign-pstn-usage-records-to-the-global-voice-routing-policy"></a><span data-ttu-id="5a65e-125">PSTN 使用法レコードをグローバル音声ルーティング ポリシーに割り当てるには</span><span class="sxs-lookup"><span data-stu-id="5a65e-125">To assign PSTN usage records to the global voice routing policy</span></span>

1. <span data-ttu-id="5a65e-126">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="5a65e-126">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="5a65e-127">Skype for Business Server 管理シェルを開始する: **[スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[Skype for Business Server 管理シェル]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="5a65e-127">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="5a65e-128">PSTN 使用法レコードをポリシーに追加します。</span><span class="sxs-lookup"><span data-stu-id="5a65e-128">Add the PSTN usage records to the policy:</span></span>
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages <PSTNUsagesId> 
   ```

    <span data-ttu-id="5a65e-129">例:</span><span class="sxs-lookup"><span data-stu-id="5a65e-129">For example:</span></span>
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages "Local", "Long Distance" 
   ```

## <a name="creating-a-new-voice-routing-policy"></a><span data-ttu-id="5a65e-130">新しい音声ルーティング ポリシーの作成</span><span class="sxs-lookup"><span data-stu-id="5a65e-130">Creating a new voice routing policy</span></span>

### <a name="to-create-a-new-voice-routing-policy"></a><span data-ttu-id="5a65e-131">新しい音声ルーティング ポリシーを作成するには</span><span class="sxs-lookup"><span data-stu-id="5a65e-131">To create a new voice routing policy</span></span>

1. <span data-ttu-id="5a65e-132">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="5a65e-132">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="5a65e-133">Skype for Business Server 管理シェルを開始する: **[スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[Skype for Business Server 管理シェル]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="5a65e-133">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="5a65e-134">新しい音声ルーティング ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="5a65e-134">Create a new voice routing policy:</span></span>
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity <String> -Name <String> -PSTNUsages <PSTNUsagesId>
   ```

    <span data-ttu-id="5a65e-135">例:</span><span class="sxs-lookup"><span data-stu-id="5a65e-135">For example:</span></span>
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity HybridVoice -Name Hybrid -PSTNUsages "Local", "Long Distance"
   ```

<span data-ttu-id="5a65e-136">この例では、HybridVoice という新しい音声ルーティング ポリシーを作成します。これには、2 つの PSTN 使用法が関連付けされています。</span><span class="sxs-lookup"><span data-stu-id="5a65e-136">This example creates a new voice routing policy called HybridVoice, which has two PSTN usages associated with it.</span></span>
  
## <a name="assigning-a-voice-routing-policy"></a><span data-ttu-id="5a65e-137">音声ルーティング ポリシーの割り当て</span><span class="sxs-lookup"><span data-stu-id="5a65e-137">Assigning a voice routing policy</span></span>

<span data-ttu-id="5a65e-138">グローバル 音声ルーティング ポリシーまたはユーザー固有の音声ルーティング ポリシーを使用するかどうかに関係なく、次の手順を使用してポリシーをユーザーに割り当てる。</span><span class="sxs-lookup"><span data-stu-id="5a65e-138">No matter whether you use the global voice routing policy, or user-specific ones, use the following steps to assign the policy to a user.</span></span>
  
### <a name="to-assign-the-voice-routing-policy"></a><span data-ttu-id="5a65e-139">音声ルーティング ポリシーを割り当てるには</span><span class="sxs-lookup"><span data-stu-id="5a65e-139">To assign the voice routing policy</span></span>

1. <span data-ttu-id="5a65e-140">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="5a65e-140">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="5a65e-141">Skype for Business Server 管理シェルを開始する: **[スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[Skype for Business Server 管理シェル]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="5a65e-141">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="5a65e-142">既存の音声ポリシーをユーザーに割り当てる:</span><span class="sxs-lookup"><span data-stu-id="5a65e-142">Assign an existing voice policy to a user:</span></span>
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    <span data-ttu-id="5a65e-143">例:</span><span class="sxs-lookup"><span data-stu-id="5a65e-143">For example:</span></span>
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity "Bob Kelly" -PolicyName HybridVoice
   ```

<span data-ttu-id="5a65e-144">この例では、表示名 Bob Kelly を持つユーザーが、HybridVoice という名前の以前に作成した音声ポリシーに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="5a65e-144">In this example, the user with the display name Bob Kelly is assigned to the previously created voice policy with the name HybridVoice.</span></span>
  
<span data-ttu-id="5a65e-145">音声ルーティング ポリシーの詳細については、「音声ポリシーを作成または変更し[、Skype for Business 2015](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md) [、New-CsVoiceRoutingPolicy、](/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)[および Grant-CsVoicePolicy](/powershell/module/skype/grant-csvoicepolicy?view=skype-ps)で PSTN 使用法レコードを構成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a65e-145">For more details about voice routing policies, see [Create or modify a voice policy and configure PSTN usage records in Skype for Business 2015](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md), [New-CsVoiceRoutingPolicy](/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps), and [Grant-CsVoicePolicy](/powershell/module/skype/grant-csvoicepolicy?view=skype-ps).</span></span>
