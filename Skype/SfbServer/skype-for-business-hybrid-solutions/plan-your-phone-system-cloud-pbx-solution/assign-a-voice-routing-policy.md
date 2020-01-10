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
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: c7f78f23-b74f-402f-bedb-4cc308718f5b
description: '概要: このトピックでは、Office 365 で電話システムを使用して、オンプレミスの PSTN 接続を使用して、ユーザーに対して音声ポリシーを割り当てる方法について説明します。'
ms.openlocfilehash: fc1bf50eabc1b596ba54e3447c0357cfd304ad2c
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003037"
---
# <a name="assign-a-voice-routing-policy"></a><span data-ttu-id="8bbf4-103">音声ルーティング ポリシーの割り当て</span><span class="sxs-lookup"><span data-stu-id="8bbf4-103">Assign a Voice Routing Policy</span></span>
 
<span data-ttu-id="8bbf4-104">**概要:** このトピックでは、Office 365 の電話システムを使って、オンプレミスの PSTN 接続を使用して、ユーザーに対して音声ポリシーを割り当てる方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8bbf4-104">**Summary:** Read this topic to learn how to assign a voice policy for users using Phone System in Office 365 with on-premises PSTN connectivity.</span></span> 
  
<span data-ttu-id="8bbf4-105">ユーザーが Skype for Business Online を使用していて、Office 365 の電話システムをオンプレミスの PSTN 接続と共に使用すると、2つの音声ポリシーが適用されます。</span><span class="sxs-lookup"><span data-stu-id="8bbf4-105">Once a user is on Skype for Business Online and using Phone System in Office 365 with on-premises PSTN connectivity, two voice policies will apply to them.</span></span> <span data-ttu-id="8bbf4-106">1つはオンプレミスのボイスルーティングポリシーであり、オンプレミスで割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="8bbf4-106">One is an on-premises voice routing policy that you will assign on premises.</span></span> <span data-ttu-id="8bbf4-107">このポリシーはグローバルまたはユーザー固有のものにすることができ、ユーザーに関連付けられている PSTN 使用状況レコードを定義できます。</span><span class="sxs-lookup"><span data-stu-id="8bbf4-107">This policy can be global or user-specific and defines what PSTN usage records are associated with the user.</span></span> <span data-ttu-id="8bbf4-108">このトピックではこのポリシーを割り当てる方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8bbf4-108">This topic explains how to assign this policy.</span></span>
  
<span data-ttu-id="8bbf4-109">その他の音声ポリシーでは、ユーザーが使用できる通話機能を定義します。この音声ポリシーは、Microsoft によって定義され、Office 365 のすべての電話システムで、オンプレミスの PSTN 接続ユーザーとまったく同じです。</span><span class="sxs-lookup"><span data-stu-id="8bbf4-109">The other voice policy defines what calling features are available to the user; this voice policy is defined by Microsoft and is identical for all Phone System in Office 365 with on-premises PSTN connectivity users.</span></span> <span data-ttu-id="8bbf4-110">Office 365 ユーザーの電話システムに自動的に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="8bbf4-110">It is automatically assigned to Phone System in Office 365 users.</span></span>
  
||<span data-ttu-id="8bbf4-111">**オンプレミス ユーザー**</span><span class="sxs-lookup"><span data-stu-id="8bbf4-111">**On-premises user**</span></span>|<span data-ttu-id="8bbf4-112">**オンプレミスの PSTN 接続ユーザーとの Office 365 の電話システム**</span><span class="sxs-lookup"><span data-stu-id="8bbf4-112">**Phone System in Office 365 with on-premises PSTN connectivity user**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8bbf4-113">定義される通話機能</span><span class="sxs-lookup"><span data-stu-id="8bbf4-113">Calling features defined in</span></span>  <br/> |<span data-ttu-id="8bbf4-114">音声ポリシー</span><span class="sxs-lookup"><span data-stu-id="8bbf4-114">Voice policy</span></span>  <br/> |<span data-ttu-id="8bbf4-115">事前に定義された音声ポリシー。ユーザーが Office 365 で電話システムのライセンスを取得したときに自動的に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="8bbf4-115">Pre-defined voice policy, assigned automatically when the user is licensed for Phone System in Office 365.</span></span>  <br/> |
|<span data-ttu-id="8bbf4-116">関連付けられる PSTN 使用レコード</span><span class="sxs-lookup"><span data-stu-id="8bbf4-116">PSTN usage records associated with</span></span>  <br/> |<span data-ttu-id="8bbf4-117">音声ポリシー</span><span class="sxs-lookup"><span data-stu-id="8bbf4-117">Voice policy</span></span>  <br/> |<span data-ttu-id="8bbf4-118">音声ルーティングポリシー。ユーザーがまだオンプレミスに所属している間に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="8bbf4-118">Voice routing policy, assigned while the user is still homed on-premises.</span></span>  <br/> |
   
<span data-ttu-id="8bbf4-119">次の手順は、オンプレミスの展開を使用して実行しますが、ユーザーはオンプレミスの展開のままになっています。</span><span class="sxs-lookup"><span data-stu-id="8bbf4-119">You perform the following steps using your on-premises deployment, while the user is still homed in the on-premises deployment.</span></span>
  
## <a name="using-a-global-voice-routing-policy"></a><span data-ttu-id="8bbf4-120">グローバル音声ルーティング ポリシーの使用</span><span class="sxs-lookup"><span data-stu-id="8bbf4-120">Using a global voice routing policy</span></span>

<span data-ttu-id="8bbf4-121">Office 365 で電話システムのグローバルボイスルーティングポリシーをオンプレミスの PSTN 接続ユーザーと共に使用する前に、PSTN 使用状況レコードをポリシーに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8bbf4-121">Before using a global voice routing policy for your Phone System in Office 365 with on-premises PSTN connectivity users, you must add PSTN usage records to the policy.</span></span>
  
### <a name="to-assign-pstn-usage-records-to-the-global-voice-routing-policy"></a><span data-ttu-id="8bbf4-122">PSTN 使用レコードをグローバル音声ルーティング ポリシーに割り当てるには</span><span class="sxs-lookup"><span data-stu-id="8bbf4-122">To assign PSTN usage records to the global voice routing policy</span></span>

1. <span data-ttu-id="8bbf4-123">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="8bbf4-123">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="8bbf4-124">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="8bbf4-124">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="8bbf4-125">PSTN 使用状況レコードをポリシーに追加します。</span><span class="sxs-lookup"><span data-stu-id="8bbf4-125">Add the PSTN usage records to the policy:</span></span>
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages <PSTNUsagesId> 
   ```

    <span data-ttu-id="8bbf4-126">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="8bbf4-126">For example:</span></span>
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages "Local", "Long Distance" 
   ```

## <a name="creating-a-new-voice-routing-policy"></a><span data-ttu-id="8bbf4-127">新しい音声ルーティング ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="8bbf4-127">Creating a new voice routing policy</span></span>

### <a name="to-create-a-new-voice-routing-policy"></a><span data-ttu-id="8bbf4-128">新しい音声ルーティング ポリシーを作成するには</span><span class="sxs-lookup"><span data-stu-id="8bbf4-128">To create a new voice routing policy</span></span>

1. <span data-ttu-id="8bbf4-129">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="8bbf4-129">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="8bbf4-130">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="8bbf4-130">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="8bbf4-131">新しい音声ルーティング ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="8bbf4-131">Create a new voice routing policy:</span></span>
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity <String> -Name <String> -PSTNUsages <PSTNUsagesId>
   ```

    <span data-ttu-id="8bbf4-132">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="8bbf4-132">For example:</span></span>
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity HybridVoice -Name Hybrid -PSTNUsages "Local", "Long Distance"
   ```

<span data-ttu-id="8bbf4-133">この例では、HybridVoice という新しい音声ルーティング ポリシーを作成します。このポリシーには 2 つの PSTN 使用レコードが関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="8bbf4-133">This example creates a new voice routing policy called HybridVoice, which has two PSTN usages associated with it.</span></span>
  
## <a name="assigning-a-voice-routing-policy"></a><span data-ttu-id="8bbf4-134">音声ルーティング ポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="8bbf4-134">Assigning a voice routing policy</span></span>

<span data-ttu-id="8bbf4-135">グローバル音声ルーティング ポリシーまたはユーザー固有のポリシーのどちらを使用する場合でも、次の手順を使用してポリシーをユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="8bbf4-135">No matter whether you use the global voice routing policy, or user-specific ones, use the following steps to assign the policy to a user.</span></span>
  
### <a name="to-assign-the-voice-routing-policy"></a><span data-ttu-id="8bbf4-136">音声ルーティング ポリシーを割り当てるには</span><span class="sxs-lookup"><span data-stu-id="8bbf4-136">To assign the voice routing policy</span></span>

1. <span data-ttu-id="8bbf4-137">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="8bbf4-137">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="8bbf4-138">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="8bbf4-138">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="8bbf4-139">既存の音声ポリシーをユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="8bbf4-139">Assign an existing voice policy to a user:</span></span>
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    <span data-ttu-id="8bbf4-140">例:</span><span class="sxs-lookup"><span data-stu-id="8bbf4-140">For example:</span></span>
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity "Bob Kelly" -PolicyName HybridVoice
   ```

<span data-ttu-id="8bbf4-141">次の例では、表示名 Bob Kelly のユーザーを、以前に作成した HybridVoice という名前の音声ポリシーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="8bbf4-141">In this example, the user with the display name Bob Kelly is assigned to the previously created voice policy with the name HybridVoice.</span></span>
  
<span data-ttu-id="8bbf4-142">音声ルーティングポリシーの詳細については、「Skype for Business 2015、[新規-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)、および[CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoicepolicy?view=skype-ps)[での音声ポリシーの作成と変更」および「PSTN 使用状況レコードの構成](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8bbf4-142">For more details about voice routing policies, see [Create or modify a voice policy and configure PSTN usage records in Skype for Business 2015](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md), [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps), and [Grant-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoicepolicy?view=skype-ps).</span></span>
  

