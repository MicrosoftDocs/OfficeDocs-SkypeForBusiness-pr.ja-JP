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
description: '概要: このトピックでは、オンプレミスの PSTN 接続を使用する電話システムを使用するユーザーに音声ポリシーを割り当てる方法について説明します。'
ms.openlocfilehash: 5d56d4f88e30b605276296b35cd9f316348342ca
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359323"
---
# <a name="assign-a-voice-routing-policy"></a><span data-ttu-id="d1182-103">音声ルーティング ポリシーの割り当て</span><span class="sxs-lookup"><span data-stu-id="d1182-103">Assign a Voice Routing Policy</span></span>
 
> [!Important]
> <span data-ttu-id="d1182-104">Skype for Business Online は、2021年7月31日に廃止されます。その後、サービスにアクセスできなくなります。</span><span class="sxs-lookup"><span data-stu-id="d1182-104">Skype for Business Online will be retired on July 31, 2021 after which the service will no longer be accessible.</span></span>  <span data-ttu-id="d1182-105">さらに、Skype for Business Server または Cloud Connector Edition と Skype for Business Online のどちらを使用しても、オンプレミス環境との間の PSTN 接続がサポートされなくなります。</span><span class="sxs-lookup"><span data-stu-id="d1182-105">In addition, PSTN connectivity between your on-premises environment whether through Skype for Business Server or Cloud Connector Edition and Skype for Business Online will no longer be supported.</span></span>  <span data-ttu-id="d1182-106">[直接ルーティング](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)を使用してオンプレミスのテレフォニーネットワークを Teams に接続する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d1182-106">Learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="d1182-107">**概要:** このトピックでは、オンプレミスの PSTN 接続を備えた電話システムを使用するユーザーに音声ポリシーを割り当てる方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d1182-107">**Summary:** Read this topic to learn how to assign a voice policy for users using Phone System with on-premises PSTN connectivity.</span></span> 
  
<span data-ttu-id="d1182-108">ユーザーが Skype for Business Online を使用していて、オンプレミスの PSTN 接続を備えた電話システムを使用すると、2つの音声ポリシーが適用されます。</span><span class="sxs-lookup"><span data-stu-id="d1182-108">Once a user is on Skype for Business Online and using Phone System with on-premises PSTN connectivity, two voice policies will apply to them.</span></span> <span data-ttu-id="d1182-109">1つはオンプレミスで割り当てられる社内音声ルーティングポリシーです。</span><span class="sxs-lookup"><span data-stu-id="d1182-109">One is an on-premises voice routing policy that you will assign on premises.</span></span> <span data-ttu-id="d1182-110">このポリシーは、グローバルまたはユーザー固有のものであり、ユーザーに関連付けられている PSTN 使用法レコードを定義します。</span><span class="sxs-lookup"><span data-stu-id="d1182-110">This policy can be global or user-specific and defines what PSTN usage records are associated with the user.</span></span> <span data-ttu-id="d1182-111">このトピックでは、このポリシーを割り当てる方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d1182-111">This topic explains how to assign this policy.</span></span>
  
<span data-ttu-id="d1182-112">その他の音声ポリシーでは、ユーザーが使用できる通話機能を定義します。この音声ポリシーは、Microsoft によって定義されており、オンプレミスの PSTN 接続ユーザーを含むすべての電話システムで同一です。</span><span class="sxs-lookup"><span data-stu-id="d1182-112">The other voice policy defines what calling features are available to the user; this voice policy is defined by Microsoft and is identical for all Phone System with on-premises PSTN connectivity users.</span></span> <span data-ttu-id="d1182-113">これは、電話システムのユーザーに自動的に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="d1182-113">It is automatically assigned to Phone System users.</span></span>
  
||<span data-ttu-id="d1182-114">**オンプレミスのユーザー**</span><span class="sxs-lookup"><span data-stu-id="d1182-114">**On-premises user**</span></span>|<span data-ttu-id="d1182-115">**オンプレミスの PSTN 接続ユーザーが搭載された電話システム**</span><span class="sxs-lookup"><span data-stu-id="d1182-115">**Phone System with on-premises PSTN connectivity user**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d1182-116">で定義されている通話機能</span><span class="sxs-lookup"><span data-stu-id="d1182-116">Calling features defined in</span></span>  <br/> |<span data-ttu-id="d1182-117">音声ポリシー</span><span class="sxs-lookup"><span data-stu-id="d1182-117">Voice policy</span></span>  <br/> |<span data-ttu-id="d1182-118">事前に定義された音声ポリシー。ユーザーが電話システムのライセンスを受けたときに自動的に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="d1182-118">Pre-defined voice policy, assigned automatically when the user is licensed for Phone System.</span></span>  <br/> |
|<span data-ttu-id="d1182-119">に関連付けられている PSTN 使用法レコード</span><span class="sxs-lookup"><span data-stu-id="d1182-119">PSTN usage records associated with</span></span>  <br/> |<span data-ttu-id="d1182-120">音声ポリシー</span><span class="sxs-lookup"><span data-stu-id="d1182-120">Voice policy</span></span>  <br/> |<span data-ttu-id="d1182-121">音声ルーティングポリシー。ユーザーがまだオンプレミスに所属している間に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="d1182-121">Voice routing policy, assigned while the user is still homed on-premises.</span></span>  <br/> |
   
<span data-ttu-id="d1182-122">次の手順は、オンプレミス展開を使用して実行しますが、ユーザーは引き続き社内展開に所属しています。</span><span class="sxs-lookup"><span data-stu-id="d1182-122">You perform the following steps using your on-premises deployment, while the user is still homed in the on-premises deployment.</span></span>
  
## <a name="using-a-global-voice-routing-policy"></a><span data-ttu-id="d1182-123">グローバル音声ルーティングポリシーを使用する</span><span class="sxs-lookup"><span data-stu-id="d1182-123">Using a global voice routing policy</span></span>

<span data-ttu-id="d1182-124">オンプレミスの PSTN 接続ユーザーを使用して電話システムにグローバル音声ルーティングポリシーを使用する前に、PSTN 使用法レコードをポリシーに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1182-124">Before using a global voice routing policy for your Phone System with on-premises PSTN connectivity users, you must add PSTN usage records to the policy.</span></span>
  
### <a name="to-assign-pstn-usage-records-to-the-global-voice-routing-policy"></a><span data-ttu-id="d1182-125">PSTN 使用法レコードをグローバル音声ルーティングポリシーに割り当てるには</span><span class="sxs-lookup"><span data-stu-id="d1182-125">To assign PSTN usage records to the global voice routing policy</span></span>

1. <span data-ttu-id="d1182-126">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="d1182-126">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="d1182-127">Skype for Business Server 管理シェルを起動します。 [ **スタート**]、[ **すべてのプログラム**]、[ **skype for business 2015**] の順にクリックし、[ **skype for business server 管理シェル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d1182-127">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="d1182-128">PSTN 使用法レコードをポリシーに追加します。</span><span class="sxs-lookup"><span data-stu-id="d1182-128">Add the PSTN usage records to the policy:</span></span>
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages <PSTNUsagesId> 
   ```

    <span data-ttu-id="d1182-129">例:</span><span class="sxs-lookup"><span data-stu-id="d1182-129">For example:</span></span>
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages "Local", "Long Distance" 
   ```

## <a name="creating-a-new-voice-routing-policy"></a><span data-ttu-id="d1182-130">新しい音声ルーティングポリシーの作成</span><span class="sxs-lookup"><span data-stu-id="d1182-130">Creating a new voice routing policy</span></span>

### <a name="to-create-a-new-voice-routing-policy"></a><span data-ttu-id="d1182-131">新しい音声ルーティングポリシーを作成するには</span><span class="sxs-lookup"><span data-stu-id="d1182-131">To create a new voice routing policy</span></span>

1. <span data-ttu-id="d1182-132">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="d1182-132">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="d1182-133">Skype for Business Server 管理シェルを起動します。 [ **スタート**]、[ **すべてのプログラム**]、[ **skype for business 2015**] の順にクリックし、[ **skype for business server 管理シェル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d1182-133">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="d1182-134">新しい音声ルーティングポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="d1182-134">Create a new voice routing policy:</span></span>
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity <String> -Name <String> -PSTNUsages <PSTNUsagesId>
   ```

    <span data-ttu-id="d1182-135">例:</span><span class="sxs-lookup"><span data-stu-id="d1182-135">For example:</span></span>
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity HybridVoice -Name Hybrid -PSTNUsages "Local", "Long Distance"
   ```

<span data-ttu-id="d1182-136">この例では、HybridVoice という名前の新しい音声ルーティングポリシーを作成します。これには、2つの PSTN 使用法が関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="d1182-136">This example creates a new voice routing policy called HybridVoice, which has two PSTN usages associated with it.</span></span>
  
## <a name="assigning-a-voice-routing-policy"></a><span data-ttu-id="d1182-137">音声ルーティングポリシーの割り当て</span><span class="sxs-lookup"><span data-stu-id="d1182-137">Assigning a voice routing policy</span></span>

<span data-ttu-id="d1182-138">グローバル音声ルーティングポリシーまたはユーザー固有のポリシーのどちらを使用するかに関係なく、次の手順を使用して、ポリシーをユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="d1182-138">No matter whether you use the global voice routing policy, or user-specific ones, use the following steps to assign the policy to a user.</span></span>
  
### <a name="to-assign-the-voice-routing-policy"></a><span data-ttu-id="d1182-139">音声ルーティングポリシーを割り当てるには</span><span class="sxs-lookup"><span data-stu-id="d1182-139">To assign the voice routing policy</span></span>

1. <span data-ttu-id="d1182-140">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="d1182-140">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="d1182-141">Skype for Business Server 管理シェルを起動します。 [ **スタート**]、[ **すべてのプログラム**]、[ **skype for business 2015**] の順にクリックし、[ **skype for business server 管理シェル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d1182-141">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="d1182-142">既存の音声ポリシーをユーザーに割り当てる:</span><span class="sxs-lookup"><span data-stu-id="d1182-142">Assign an existing voice policy to a user:</span></span>
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    <span data-ttu-id="d1182-143">例:</span><span class="sxs-lookup"><span data-stu-id="d1182-143">For example:</span></span>
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity "Bob Kelly" -PolicyName HybridVoice
   ```

<span data-ttu-id="d1182-144">この例では、Bob 友野という表示名を持つユーザーが、HybridVoice という名前で以前に作成した音声ポリシーに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="d1182-144">In this example, the user with the display name Bob Kelly is assigned to the previously created voice policy with the name HybridVoice.</span></span>
  
<span data-ttu-id="d1182-145">音声ルーティングポリシーの詳細については、「 [Create or modify a voice policy」および「CONFIGURE PSTN usage records In Skype For business 2015](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md)」、「 [grant-csvoiceroutingpolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)」、および「 [set-csvoicepolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoicepolicy?view=skype-ps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1182-145">For more details about voice routing policies, see [Create or modify a voice policy and configure PSTN usage records in Skype for Business 2015](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md), [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps), and [Grant-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoicepolicy?view=skype-ps).</span></span>
  

