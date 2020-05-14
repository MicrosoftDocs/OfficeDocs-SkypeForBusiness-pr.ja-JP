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
ms.openlocfilehash: 141d3cca560201df921fb4195db55ac60103a3d6
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221861"
---
# <a name="assign-a-voice-routing-policy"></a><span data-ttu-id="6d6e9-103">音声ルーティング ポリシーの割り当て</span><span class="sxs-lookup"><span data-stu-id="6d6e9-103">Assign a Voice Routing Policy</span></span>
 
<span data-ttu-id="6d6e9-104">**概要:** このトピックでは、オンプレミスの PSTN 接続を備えた電話システムを使用するユーザーに音声ポリシーを割り当てる方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6d6e9-104">**Summary:** Read this topic to learn how to assign a voice policy for users using Phone System with on-premises PSTN connectivity.</span></span> 
  
<span data-ttu-id="6d6e9-105">ユーザーが Skype for Business Online を使用していて、オンプレミスの PSTN 接続を備えた電話システムを使用すると、2つの音声ポリシーが適用されます。</span><span class="sxs-lookup"><span data-stu-id="6d6e9-105">Once a user is on Skype for Business Online and using Phone System with on-premises PSTN connectivity, two voice policies will apply to them.</span></span> <span data-ttu-id="6d6e9-106">1つはオンプレミスで割り当てられる社内音声ルーティングポリシーです。</span><span class="sxs-lookup"><span data-stu-id="6d6e9-106">One is an on-premises voice routing policy that you will assign on premises.</span></span> <span data-ttu-id="6d6e9-107">このポリシーは、グローバルまたはユーザー固有のものであり、ユーザーに関連付けられている PSTN 使用法レコードを定義します。</span><span class="sxs-lookup"><span data-stu-id="6d6e9-107">This policy can be global or user-specific and defines what PSTN usage records are associated with the user.</span></span> <span data-ttu-id="6d6e9-108">このトピックでは、このポリシーを割り当てる方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6d6e9-108">This topic explains how to assign this policy.</span></span>
  
<span data-ttu-id="6d6e9-109">その他の音声ポリシーでは、ユーザーが使用できる通話機能を定義します。この音声ポリシーは、Microsoft によって定義されており、オンプレミスの PSTN 接続ユーザーを含むすべての電話システムで同一です。</span><span class="sxs-lookup"><span data-stu-id="6d6e9-109">The other voice policy defines what calling features are available to the user; this voice policy is defined by Microsoft and is identical for all Phone System with on-premises PSTN connectivity users.</span></span> <span data-ttu-id="6d6e9-110">これは、電話システムのユーザーに自動的に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="6d6e9-110">It is automatically assigned to Phone System users.</span></span>
  
||<span data-ttu-id="6d6e9-111">**オンプレミスのユーザー**</span><span class="sxs-lookup"><span data-stu-id="6d6e9-111">**On-premises user**</span></span>|<span data-ttu-id="6d6e9-112">**オンプレミスの PSTN 接続ユーザーが搭載された電話システム**</span><span class="sxs-lookup"><span data-stu-id="6d6e9-112">**Phone System with on-premises PSTN connectivity user**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6d6e9-113">で定義されている通話機能</span><span class="sxs-lookup"><span data-stu-id="6d6e9-113">Calling features defined in</span></span>  <br/> |<span data-ttu-id="6d6e9-114">音声ポリシー</span><span class="sxs-lookup"><span data-stu-id="6d6e9-114">Voice policy</span></span>  <br/> |<span data-ttu-id="6d6e9-115">事前に定義された音声ポリシー。ユーザーが電話システムのライセンスを受けたときに自動的に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="6d6e9-115">Pre-defined voice policy, assigned automatically when the user is licensed for Phone System.</span></span>  <br/> |
|<span data-ttu-id="6d6e9-116">に関連付けられている PSTN 使用法レコード</span><span class="sxs-lookup"><span data-stu-id="6d6e9-116">PSTN usage records associated with</span></span>  <br/> |<span data-ttu-id="6d6e9-117">音声ポリシー</span><span class="sxs-lookup"><span data-stu-id="6d6e9-117">Voice policy</span></span>  <br/> |<span data-ttu-id="6d6e9-118">音声ルーティングポリシー。ユーザーがまだオンプレミスに所属している間に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="6d6e9-118">Voice routing policy, assigned while the user is still homed on-premises.</span></span>  <br/> |
   
<span data-ttu-id="6d6e9-119">次の手順は、オンプレミス展開を使用して実行しますが、ユーザーは引き続き社内展開に所属しています。</span><span class="sxs-lookup"><span data-stu-id="6d6e9-119">You perform the following steps using your on-premises deployment, while the user is still homed in the on-premises deployment.</span></span>
  
## <a name="using-a-global-voice-routing-policy"></a><span data-ttu-id="6d6e9-120">グローバル音声ルーティングポリシーを使用する</span><span class="sxs-lookup"><span data-stu-id="6d6e9-120">Using a global voice routing policy</span></span>

<span data-ttu-id="6d6e9-121">オンプレミスの PSTN 接続ユーザーを使用して電話システムにグローバル音声ルーティングポリシーを使用する前に、PSTN 使用法レコードをポリシーに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d6e9-121">Before using a global voice routing policy for your Phone System with on-premises PSTN connectivity users, you must add PSTN usage records to the policy.</span></span>
  
### <a name="to-assign-pstn-usage-records-to-the-global-voice-routing-policy"></a><span data-ttu-id="6d6e9-122">PSTN 使用法レコードをグローバル音声ルーティングポリシーに割り当てるには</span><span class="sxs-lookup"><span data-stu-id="6d6e9-122">To assign PSTN usage records to the global voice routing policy</span></span>

1. <span data-ttu-id="6d6e9-123">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="6d6e9-123">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="6d6e9-124">Skype for Business Server 管理シェルを起動します。 [**スタート**]、[**すべてのプログラム**]、[ **skype for business 2015**] の順にクリックし、[ **skype for business server 管理シェル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d6e9-124">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="6d6e9-125">PSTN 使用法レコードをポリシーに追加します。</span><span class="sxs-lookup"><span data-stu-id="6d6e9-125">Add the PSTN usage records to the policy:</span></span>
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages <PSTNUsagesId> 
   ```

    <span data-ttu-id="6d6e9-126">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="6d6e9-126">For example:</span></span>
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages "Local", "Long Distance" 
   ```

## <a name="creating-a-new-voice-routing-policy"></a><span data-ttu-id="6d6e9-127">新しい音声ルーティングポリシーの作成</span><span class="sxs-lookup"><span data-stu-id="6d6e9-127">Creating a new voice routing policy</span></span>

### <a name="to-create-a-new-voice-routing-policy"></a><span data-ttu-id="6d6e9-128">新しい音声ルーティングポリシーを作成するには</span><span class="sxs-lookup"><span data-stu-id="6d6e9-128">To create a new voice routing policy</span></span>

1. <span data-ttu-id="6d6e9-129">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="6d6e9-129">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="6d6e9-130">Skype for Business Server 管理シェルを起動します。 [**スタート**]、[**すべてのプログラム**]、[ **skype for business 2015**] の順にクリックし、[ **skype for business server 管理シェル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d6e9-130">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="6d6e9-131">新しい音声ルーティングポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="6d6e9-131">Create a new voice routing policy:</span></span>
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity <String> -Name <String> -PSTNUsages <PSTNUsagesId>
   ```

    <span data-ttu-id="6d6e9-132">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="6d6e9-132">For example:</span></span>
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity HybridVoice -Name Hybrid -PSTNUsages "Local", "Long Distance"
   ```

<span data-ttu-id="6d6e9-133">この例では、HybridVoice という名前の新しい音声ルーティングポリシーを作成します。これには、2つの PSTN 使用法が関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="6d6e9-133">This example creates a new voice routing policy called HybridVoice, which has two PSTN usages associated with it.</span></span>
  
## <a name="assigning-a-voice-routing-policy"></a><span data-ttu-id="6d6e9-134">音声ルーティングポリシーの割り当て</span><span class="sxs-lookup"><span data-stu-id="6d6e9-134">Assigning a voice routing policy</span></span>

<span data-ttu-id="6d6e9-135">グローバル音声ルーティングポリシーまたはユーザー固有のポリシーのどちらを使用するかに関係なく、次の手順を使用して、ポリシーをユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="6d6e9-135">No matter whether you use the global voice routing policy, or user-specific ones, use the following steps to assign the policy to a user.</span></span>
  
### <a name="to-assign-the-voice-routing-policy"></a><span data-ttu-id="6d6e9-136">音声ルーティングポリシーを割り当てるには</span><span class="sxs-lookup"><span data-stu-id="6d6e9-136">To assign the voice routing policy</span></span>

1. <span data-ttu-id="6d6e9-137">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="6d6e9-137">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="6d6e9-138">Skype for Business Server 管理シェルを起動します。 [**スタート**]、[**すべてのプログラム**]、[ **skype for business 2015**] の順にクリックし、[ **skype for business server 管理シェル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d6e9-138">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="6d6e9-139">既存の音声ポリシーをユーザーに割り当てる:</span><span class="sxs-lookup"><span data-stu-id="6d6e9-139">Assign an existing voice policy to a user:</span></span>
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    <span data-ttu-id="6d6e9-140">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="6d6e9-140">For example:</span></span>
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity "Bob Kelly" -PolicyName HybridVoice
   ```

<span data-ttu-id="6d6e9-141">この例では、Bob 友野という表示名を持つユーザーが、HybridVoice という名前で以前に作成した音声ポリシーに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="6d6e9-141">In this example, the user with the display name Bob Kelly is assigned to the previously created voice policy with the name HybridVoice.</span></span>
  
<span data-ttu-id="6d6e9-142">音声ルーティングポリシーの詳細については、「 [Create or modify a voice policy」および「CONFIGURE PSTN usage records In Skype For business 2015](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md)」、「 [grant-csvoiceroutingpolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)」、および「 [set-csvoicepolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoicepolicy?view=skype-ps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6d6e9-142">For more details about voice routing policies, see [Create or modify a voice policy and configure PSTN usage records in Skype for Business 2015](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md), [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps), and [Grant-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoicepolicy?view=skype-ps).</span></span>
  

