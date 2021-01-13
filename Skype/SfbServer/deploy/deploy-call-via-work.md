---
title: Skype for Business Server での [作業から通話] の展開
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4802d733-14ef-4509-92b9-07173614e45f
description: '概要: 一部またはすべてのユーザーに対して Skype for Business Server で [通話から作業] を展開する方法について学習します。'
ms.openlocfilehash: 41a0ae8462b12cabf735a2501e5b22eac64abe42
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825007"
---
# <a name="deploy-call-via-work-in-skype-for-business-server"></a><span data-ttu-id="596e1-103">Skype for Business Server での [作業から通話] の展開</span><span class="sxs-lookup"><span data-stu-id="596e1-103">Deploy Call Via Work in Skype for Business Server</span></span>
 
<span data-ttu-id="596e1-104">**概要:** 一部またはすべてのユーザーに対して Skype for Business Server で [通話から作業] を展開する方法について学習します。</span><span class="sxs-lookup"><span data-stu-id="596e1-104">**Summary:** Learn how to deploy Call Via Work in Skype for Business Server for some or all of your users.</span></span>
  
<span data-ttu-id="596e1-105">以下の手順を使用して、ユーザーに [通話の実行] を展開します。</span><span class="sxs-lookup"><span data-stu-id="596e1-105">Use these steps to deploy Call Via Work for your users.</span></span> <span data-ttu-id="596e1-106">計画に関する考慮事項については [、「Plan for Call Via Work in Skype for Business Server」を参照してください](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)。</span><span class="sxs-lookup"><span data-stu-id="596e1-106">Planning considerations are discussed in [Plan for Call Via Work in Skype for Business Server](../plan-your-deployment/enterprise-voice-solution/call-via-work.md).</span></span> <span data-ttu-id="596e1-107">以前のバージョンの Lync Server のリモート通話コントロールは、ユーザーが Lync Server を使用して PBX 電話を制御できる機能でした。</span><span class="sxs-lookup"><span data-stu-id="596e1-107">In previous versions of Lync Server remote call control was a feature which enabled users to control their PBX phones with Lync Server.</span></span> <span data-ttu-id="596e1-108">Skype for Business Server では、この機能は [Call Via Work] に置き換えられた機能です。</span><span class="sxs-lookup"><span data-stu-id="596e1-108">In Skype for Business Server, this feature has been replaced with Call Via Work.</span></span> 
  
## <a name="prerequisites-for-call-via-work"></a><span data-ttu-id="596e1-109">[仕事から通話] の前提条件</span><span class="sxs-lookup"><span data-stu-id="596e1-109">Prerequisites for Call Via Work</span></span>

<span data-ttu-id="596e1-110">Call Via Work は、すべての Skype for Business Server フロントエンド サーバーに自動的にインストールされる Unified Communications Web API (UCWA) を使用します。</span><span class="sxs-lookup"><span data-stu-id="596e1-110">Call Via Work uses Unified Communications Web API (UCWA), which is automatically installed on all Skype for Business Server Front End Servers.</span></span> <span data-ttu-id="596e1-111">ユーザーが [仕事から通話] を有効にするには、次の前提条件も満たされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="596e1-111">To enable users for Call Via Work, you must also have the following prerequisites in place:</span></span> 
  
- <span data-ttu-id="596e1-112">フロントエンド サーバーの一部として、またはスタンドアロンの役割として、仲介サーバーを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="596e1-112">You must have a Mediation Server deployed, either as part of a Front End Server or as a standalone role.</span></span> <span data-ttu-id="596e1-113">IP-PBX ゲートウェイも展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="596e1-113">You must also deploy an IP-PBX gateway.</span></span>
    
- <span data-ttu-id="596e1-114">[仕事から通話] が有効になるすべてのユーザーは、PBX 電話システムに Direct Inward Dialing (DID) が必要です。</span><span class="sxs-lookup"><span data-stu-id="596e1-114">All users who will be enabled for Call Via Work must have a Direct Inward Dialing (DID) on the PBX phone system.</span></span> 
    
- <span data-ttu-id="596e1-115">すべての [通話の実行] を有効にする必要エンタープライズ VoIP。</span><span class="sxs-lookup"><span data-stu-id="596e1-115">You must enable all Call Via Work users for Enterprise Voice.</span></span> <span data-ttu-id="596e1-116">これを行う場合は、各ユーザーの Skype for Business DID 番号を、対応する PBX 電話システムの対応する DID 番号に構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="596e1-116">When you do this, you must configure the Skype for Business DID number for each user to the corresponding DID number for the corresponding PBX phone system.</span></span> 
    
- <span data-ttu-id="596e1-117">[仕事から通話] を使用するユーザーはすべて、Skype for Businessクライアントの [詳細設定接続] オプションで [自動構成] を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="596e1-117">All users who will be using Call Via Work must have **Automatic Configuration** selected in their **Advanced Connections** option in their Skype for Business client.</span></span> <span data-ttu-id="596e1-118">これにより、クライアントは UCWA URL を検出できます。</span><span class="sxs-lookup"><span data-stu-id="596e1-118">This enables the client to discover the UCWA URLs.</span></span> <span data-ttu-id="596e1-119">**自動構成は** 既定の選択です。</span><span class="sxs-lookup"><span data-stu-id="596e1-119">**Automatic Configuration** is the default selection.</span></span>
    
- <span data-ttu-id="596e1-120">[Call Via Work] ユーザーごとに、通話の転送と同時呼び出しを有効にします。</span><span class="sxs-lookup"><span data-stu-id="596e1-120">For each Call Via Work user, enable call forwarding and simultaneous ringing.</span></span> 
    
- <span data-ttu-id="596e1-121">[Call Via Work] ユーザーごとに、ダイヤルイン会議と会議ダイヤルアウトが有効になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="596e1-121">For each Call Via Work user, ensure that dial-in conferencing and conferencing dial-out are enabled.</span></span> <span data-ttu-id="596e1-122">これにより、これらのユーザーは Skype for Business 会議に参加および会議から抜け出すできます。</span><span class="sxs-lookup"><span data-stu-id="596e1-122">This enables these users to get into and out of Skype for Business conferences.</span></span>
    
- <span data-ttu-id="596e1-123">すべての [Call Via Work] ユーザーに対して、委任、チーム通話、および応答グループが無効に設定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="596e1-123">Ensure that delegation, team call, and response group are disabled for every Call Via Work user.</span></span>
    
## <a name="deploy-call-via-work"></a><span data-ttu-id="596e1-124">勤務先から通話の展開</span><span class="sxs-lookup"><span data-stu-id="596e1-124">Deploy Call Via Work</span></span>

<span data-ttu-id="596e1-125">前提条件が満たされた後、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="596e1-125">After the prerequisites are in place, do the following:</span></span>
  
- <span data-ttu-id="596e1-126">展開用のグローバル電話番号を作成します。Skype for Business は、通話を行っているユーザーの PBX 発信者番号に表示されます。</span><span class="sxs-lookup"><span data-stu-id="596e1-126">Create a global phone number for your deployment which Skype for Business displays on the PBX caller ID of users who are making Call Via Work calls.</span></span> 
    
- <span data-ttu-id="596e1-127">1 つ以上の [仕事から通話] ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="596e1-127">Create one or more Call Via Work policies</span></span>
    
- <span data-ttu-id="596e1-128">[仕事から通話] ポリシーを、[仕事から通話] が有効になる各ユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="596e1-128">Assign a Call Via Work policy to each user who will be enabled for Call Via Work</span></span>
    
### <a name="create-the-call-via-work-global-phone-number"></a><span data-ttu-id="596e1-129">[Call Via Work] グローバル電話番号を作成する</span><span class="sxs-lookup"><span data-stu-id="596e1-129">Create the Call Via Work global phone number</span></span>

- <span data-ttu-id="596e1-130">次のコマンドレットを入力します。</span><span class="sxs-lookup"><span data-stu-id="596e1-130">Type the following cmdlet</span></span>
    
  ```powershell
  Set-CsRoutingConfiguration -CallViaWorkCallerId +<PhoneNumber>
  ```

    <span data-ttu-id="596e1-131">たとえば、次のコマンドレットは、グローバル電話番号を 1-555-123-4567 に設定します。</span><span class="sxs-lookup"><span data-stu-id="596e1-131">For example, the following cmdlet sets the global phone number to 1-555-123-4567.</span></span>
    
  ```powershell
  Set-CsRoutingConfiguration -CallViaWorkCallerId +15551234567
  ```

### <a name="create-a-call-via-work-policy"></a><span data-ttu-id="596e1-132">[仕事から通話] ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="596e1-132">Create a Call Via Work policy</span></span>

- <span data-ttu-id="596e1-133">次のコマンドレットを入力します。</span><span class="sxs-lookup"><span data-stu-id="596e1-133">Type the following cmdlet</span></span>
    
  ```powershell
  New-CsCallViaWorkPolicy [-Identity] <XdsIdentity> [-Tenant <guid>] [-Enabled <bool>] [-UseAdminCallbackNumber  <bool>] [-AdminCallbackNumber <string>] [-InMemory] [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]
  ```

    <span data-ttu-id="596e1-134">たとえば、次のコマンドレットでは、ContosoUser1CvWP という Call Via Work ポリシーを作成し、ユーザーに管理者コールバック番号の使用を要求し、そのコールバック番号を 1-555-789-1234 に設定します。</span><span class="sxs-lookup"><span data-stu-id="596e1-134">For example, the following cmdlet creates a Call Via Work policy called ContosoUser1CvWP, requires the user to use an admin callback number, and sets that callback number to 1-555-789-1234.</span></span>
    
  ```powershell
  New-CsCallViaWorkPolicy -Identity Tag:ContosoUser1CvWP -Enabled $true -UseAdminCallbackNumber $true -AdminCallbackNumber +15557891234
  ```

### <a name="assign-a-call-via-work-policy-to-a-user"></a><span data-ttu-id="596e1-135">[仕事から通話] ポリシーをユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="596e1-135">Assign a Call Via Work policy to a user</span></span>

- <span data-ttu-id="596e1-136">次のコマンドレットを入力します。</span><span class="sxs-lookup"><span data-stu-id="596e1-136">Type the following cmdlet</span></span>
    
  ```powershell
  Grant-CsCallViaWorkPolicy -Identity <UserName> -PolicyName Tag:<PolicyName>
  ```

    <span data-ttu-id="596e1-137">たとえば、次のコマンドレットは、"ContosoUser1CvWP" という Call Via Work ポリシーを ContosoUser1 という名前のユーザーに割り **当てるとします**。</span><span class="sxs-lookup"><span data-stu-id="596e1-137">For example, the following cmdlet assigns the Call Via Work policy "ContosoUser1CvWP" to the user named **ContosoUser1**.</span></span>
    
  ```powershell
  Grant-CsCallViaWorkPolicy -Identity ContosoUser1 -PolicyName Tag:ContosoUser1CvWP
  ```

## <a name="see-also"></a><span data-ttu-id="596e1-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="596e1-138">See also</span></span>

[<span data-ttu-id="596e1-139">Plan for Call Via Work in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="596e1-139">Plan for Call Via Work in Skype for Business Server</span></span>](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)

