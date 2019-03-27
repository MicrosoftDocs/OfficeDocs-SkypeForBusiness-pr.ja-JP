---
title: Skype ビジネス サーバーの作業時間を使用して呼び出しを配置します。
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4802d733-14ef-4509-92b9-07173614e45f
description: '概要: ビジネスのサーバーの一部またはすべてのユーザーの Skype の呼び出しを使用して作業を配置する方法を説明します。'
ms.openlocfilehash: d0cee2cbf3a88514983efd77e2b1728b2df1e792
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30879435"
---
# <a name="deploy-call-via-work-in-skype-for-business-server"></a><span data-ttu-id="73f80-103">Skype ビジネス サーバーの作業時間を使用して呼び出しを配置します。</span><span class="sxs-lookup"><span data-stu-id="73f80-103">Deploy Call Via Work in Skype for Business Server</span></span>
 
<span data-ttu-id="73f80-104">**の概要:** ビジネス サーバーの一部またはすべてのユーザーの Skype の呼び出しを使用して作業を配置する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="73f80-104">**Summary:** Learn how to deploy Call Via Work in Skype for Business Server for some or all of your users.</span></span>
  
<span data-ttu-id="73f80-105">ユーザーの作業を使用して呼び出しを配置するのにには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="73f80-105">Use these steps to deploy Call Via Work for your users.</span></span> <span data-ttu-id="73f80-106">計画に関する考慮事項については、 [Skype ビジネス サーバー用の呼び出しを使用して作業の計画](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)で説明します。</span><span class="sxs-lookup"><span data-stu-id="73f80-106">Planning considerations are discussed in [Plan for Call Via Work in Skype for Business Server](../plan-your-deployment/enterprise-voice-solution/call-via-work.md).</span></span> <span data-ttu-id="73f80-107">Lync Server のリモート呼び出しの以前のバージョンでは、コントロールは、Lync Server は PBX 電話を制御するユーザーを有効にする機能でした。</span><span class="sxs-lookup"><span data-stu-id="73f80-107">In previous versions of Lync Server remote call control was a feature which enabled users to control their PBX phones with Lync Server.</span></span> <span data-ttu-id="73f80-108">ビジネス サーバーの Skype は、この機能は作業時間を使用して呼び出しを交換済み。</span><span class="sxs-lookup"><span data-stu-id="73f80-108">In Skype for Business Server, this feature has been replaced with Call Via Work.</span></span> 
  
## <a name="prerequisites-for-call-via-work"></a><span data-ttu-id="73f80-109">作業を使用して呼び出すのための前提条件</span><span class="sxs-lookup"><span data-stu-id="73f80-109">Prerequisites for Call Via Work</span></span>

<span data-ttu-id="73f80-110">作業による呼び出しは、ユニファイド コミュニケーション Web API (UCWA)、ビジネス サーバーのフロント エンド サーバーのすべての Skype で自動的にインストールされるを使用します。</span><span class="sxs-lookup"><span data-stu-id="73f80-110">Call Via Work uses Unified Communications Web API (UCWA), which is automatically installed on all Skype for Business Server Front End Servers.</span></span> <span data-ttu-id="73f80-111">作業による呼び出しでユーザーを有効にするのにも必要次の前提条件の場所でです。</span><span class="sxs-lookup"><span data-stu-id="73f80-111">To enable users for Call Via Work, you must also have the following prerequisites in place:</span></span> 
  
- <span data-ttu-id="73f80-112">サーバーをフロント エンド サーバーの一部として、またはスタンドアロンの役割として展開するには、仲介サーバーが必要です。</span><span class="sxs-lookup"><span data-stu-id="73f80-112">You must have a Mediation Server deployed, either as part of a Front End Server or as a standalone role.</span></span> <span data-ttu-id="73f80-113">また、IP-PBX ゲートウェイの展開も必要です。</span><span class="sxs-lookup"><span data-stu-id="73f80-113">You must also deploy an IP-PBX gateway.</span></span>
    
- <span data-ttu-id="73f80-114">作業を使用して呼び出しを有効化するすべてのユーザーには、PBX 電話システムに直接内側ダイヤル (DID) 必要があります。</span><span class="sxs-lookup"><span data-stu-id="73f80-114">All users who will be enabled for Call Via Work must have a Direct Inward Dialing (DID) on the PBX phone system.</span></span> 
    
- <span data-ttu-id="73f80-115">エンタープライズ VoIP のすべての作業の呼び出しを使用してユーザーを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="73f80-115">You must enable all Call Via Work users for Enterprise Voice.</span></span> <span data-ttu-id="73f80-116">これを行うと、対応する PBX 電話システムの対応する DID 番号を各ユーザーの数のビジネスでしたの Skype を構成しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="73f80-116">When you do this, you must configure the Skype for Business DID number for each user to the corresponding DID number for the corresponding PBX phone system.</span></span> 
    
- <span data-ttu-id="73f80-117">作業を使用して呼び出しを使用するすべてのユーザーには、ビジネス クライアント用の Skype では、その**接続の高度な**オプションで選択されている**自動構成**が必要です。</span><span class="sxs-lookup"><span data-stu-id="73f80-117">All users who will be using Call Via Work must have **Automatic Configuration** selected in their **Advanced Connections** option in their Skype for Business client.</span></span> <span data-ttu-id="73f80-118">これにより、クライアントが UCWA の Url を検出します。</span><span class="sxs-lookup"><span data-stu-id="73f80-118">This enables the client to discover the UCWA URLs.</span></span> <span data-ttu-id="73f80-119">[**自動構成**] は既定で選択されています。</span><span class="sxs-lookup"><span data-stu-id="73f80-119">**Automatic Configuration** is the default selection.</span></span>
    
- <span data-ttu-id="73f80-120">作業の呼び出しを使用してユーザーごとに、着信の転送および同時呼び出しを有効にします。</span><span class="sxs-lookup"><span data-stu-id="73f80-120">For each Call Via Work user, enable call forwarding and simultaneous ringing.</span></span> 
    
- <span data-ttu-id="73f80-121">作業の呼び出しを使用して、ユーザーごとにダイヤルイン会議および会議のダイヤル ・ アウトが有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="73f80-121">For each Call Via Work user, ensure that dial-in conferencing and conferencing dial-out are enabled.</span></span> <span data-ttu-id="73f80-122">これにより、これらのユーザーにビジネス会議のために、Skype を取得します。</span><span class="sxs-lookup"><span data-stu-id="73f80-122">This enables these users to get into and out of Skype for Business conferences.</span></span>
    
- <span data-ttu-id="73f80-123">作業を使用して呼び出しのすべてのユーザーの委任、チーム呼び出し、および応答グループが無効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="73f80-123">Ensure that delegation, team call, and response group are disabled for every Call Via Work user.</span></span>
    
## <a name="deploy-call-via-work"></a><span data-ttu-id="73f80-124">"勤務先から通話" の展開</span><span class="sxs-lookup"><span data-stu-id="73f80-124">Deploy Call Via Work</span></span>

<span data-ttu-id="73f80-125">前提条件が満たされたら、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="73f80-125">After the prerequisites are in place, do the following:</span></span>
  
- <span data-ttu-id="73f80-126">ビジネス用の Skype を作業の呼び出しを使用して呼び出しを行うユーザーの PBX の呼び出し元 ID の表示を展開するためのグローバル電話番号を作成します。</span><span class="sxs-lookup"><span data-stu-id="73f80-126">Create a global phone number for your deployment which Skype for Business displays on the PBX caller ID of users who are making Call Via Work calls.</span></span> 
    
- <span data-ttu-id="73f80-127">1 つまたは複数の作業の呼び出しを使用してポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="73f80-127">Create one or more Call Via Work policies</span></span>
    
- <span data-ttu-id="73f80-128">作業を使用して呼び出しを有効化する各ユーザーに作業を使用して呼び出すポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="73f80-128">Assign a Call Via Work policy to each user who will be enabled for Call Via Work</span></span>
    
### <a name="create-the-call-via-work-global-phone-number"></a><span data-ttu-id="73f80-129">"勤務先から通話" グローバル電話番号の作成</span><span class="sxs-lookup"><span data-stu-id="73f80-129">Create the Call Via Work global phone number</span></span>

- <span data-ttu-id="73f80-130">次のコマンドレットを入力します。</span><span class="sxs-lookup"><span data-stu-id="73f80-130">Type the following cmdlet</span></span>
    
  ```
  Set-CsRoutingConfiguration -CallViaWorkCallerId +<PhoneNumber>
  ```

    <span data-ttu-id="73f80-131">たとえば、次のコマンドレットではグローバル電話番号が 1-555-123-4567 に設定されます。</span><span class="sxs-lookup"><span data-stu-id="73f80-131">For example, the following cmdlet sets the global phone number to 1-555-123-4567.</span></span>
    
  ```
  Set-CsRoutingConfiguration -CallViaWorkCallerId +15551234567
  ```

### <a name="create-a-call-via-work-policy"></a><span data-ttu-id="73f80-132">"勤務先から通話" ポリシーの作成</span><span class="sxs-lookup"><span data-stu-id="73f80-132">Create a Call Via Work policy</span></span>

- <span data-ttu-id="73f80-133">次のコマンドレットを入力します。</span><span class="sxs-lookup"><span data-stu-id="73f80-133">Type the following cmdlet</span></span>
    
  ```
  New-CsCallViaWorkPolicy [-Identity] <XdsIdentity> [-Tenant <guid>] [-Enabled <bool>] [-UseAdminCallbackNumber  <bool>] [-AdminCallbackNumber <string>] [-InMemory] [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]
  ```

    <span data-ttu-id="73f80-134">などの次のコマンドレット ContosoUser1CvWP と呼ばれる作業の呼び出しを使用してポリシーを作成、管理のコールバック番号を使用するユーザーが必要で、コールバック番号を 1-555-789-1234 に設定。</span><span class="sxs-lookup"><span data-stu-id="73f80-134">For example, the following cmdlet creates a Call Via Work policy called ContosoUser1CvWP, requires the user to use an admin callback number, and sets that callback number to 1-555-789-1234.</span></span>
    
  ```
  New-CsCallViaWorkPolicy -Identity Tag:ContosoUser1CvWP -Enabled $true -UseAdminCallbackNumber $true -AdminCallbackNumber +15557891234
  ```

### <a name="assign-a-call-via-work-policy-to-a-user"></a><span data-ttu-id="73f80-135">作業の呼び出しを使用してポリシーをユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="73f80-135">Assign a Call Via Work policy to a user</span></span>

- <span data-ttu-id="73f80-136">次のコマンドレットを入力します。</span><span class="sxs-lookup"><span data-stu-id="73f80-136">Type the following cmdlet</span></span>
    
  ```
  Grant-CsCallViaWorkPolicy -Identity <UserName> -PolicyName Tag:<PolicyName>
  ```

    <span data-ttu-id="73f80-137">たとえば、次のコマンドレットでは、 **ContosoUser1**をという名前のユーザーに作業の呼び出しを使用してポリシーの"ContosoUser1CvWP"が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="73f80-137">For example, the following cmdlet assigns the Call Via Work policy "ContosoUser1CvWP" to the user named **ContosoUser1**.</span></span>
    
  ```
  Grant-CsCallViaWorkPolicy -Identity ContosoUser1 -PolicyName Tag:ContosoUser1CvWP
  ```

## <a name="see-also"></a><span data-ttu-id="73f80-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="73f80-138">See also</span></span>

[<span data-ttu-id="73f80-139">Skype ビジネス サーバーの作業時間を使用して呼び出すのための計画</span><span class="sxs-lookup"><span data-stu-id="73f80-139">Plan for Call Via Work in Skype for Business Server</span></span>](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)

