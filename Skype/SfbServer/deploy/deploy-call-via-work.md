---
title: Skype for Business Server での作業による通話の展開
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4802d733-14ef-4509-92b9-07173614e45f
description: '概要: 一部またはすべてのユーザーに対して、Skype for Business Server で作業を通じて通話を展開する方法について説明します。'
ms.openlocfilehash: a2d4783f39ca19fd751295f4725f686d843f8d5b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286391"
---
# <a name="deploy-call-via-work-in-skype-for-business-server"></a><span data-ttu-id="62f17-103">Skype for Business Server での作業による通話の展開</span><span class="sxs-lookup"><span data-stu-id="62f17-103">Deploy Call Via Work in Skype for Business Server</span></span>
 
<span data-ttu-id="62f17-104">**概要:** 一部またはすべてのユーザーに対して、Skype for Business Server で作業を通じて通話を展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="62f17-104">**Summary:** Learn how to deploy Call Via Work in Skype for Business Server for some or all of your users.</span></span>
  
<span data-ttu-id="62f17-105">次の手順を使用して、ユーザーの勤務先で通話を展開します。</span><span class="sxs-lookup"><span data-stu-id="62f17-105">Use these steps to deploy Call Via Work for your users.</span></span> <span data-ttu-id="62f17-106">計画の考慮事項については、「 [Skype For Business Server での作業による通話の計画](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)」をご紹介します。</span><span class="sxs-lookup"><span data-stu-id="62f17-106">Planning considerations are discussed in [Plan for Call Via Work in Skype for Business Server](../plan-your-deployment/enterprise-voice-solution/call-via-work.md).</span></span> <span data-ttu-id="62f17-107">以前のバージョンの Lync Server リモート通話コントロールは、ユーザーが Lync Server を使って PBX 電話を制御できるようにする機能です。</span><span class="sxs-lookup"><span data-stu-id="62f17-107">In previous versions of Lync Server remote call control was a feature which enabled users to control their PBX phones with Lync Server.</span></span> <span data-ttu-id="62f17-108">Skype for Business Server では、この機能は勤務先からの通話に置き換えられました。</span><span class="sxs-lookup"><span data-stu-id="62f17-108">In Skype for Business Server, this feature has been replaced with Call Via Work.</span></span> 
  
## <a name="prerequisites-for-call-via-work"></a><span data-ttu-id="62f17-109">勤務先での通話の前提条件</span><span class="sxs-lookup"><span data-stu-id="62f17-109">Prerequisites for Call Via Work</span></span>

<span data-ttu-id="62f17-110">勤務先での通話ユニファイドコミュニケーション Web API (UCWA) は、すべての Skype for Business Server フロントエンドサーバーに自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="62f17-110">Call Via Work uses Unified Communications Web API (UCWA), which is automatically installed on all Skype for Business Server Front End Servers.</span></span> <span data-ttu-id="62f17-111">勤務先のユーザーによる通話を有効にするには、次の前提条件が設定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="62f17-111">To enable users for Call Via Work, you must also have the following prerequisites in place:</span></span> 
  
- <span data-ttu-id="62f17-112">フロントエンドサーバーの一部として、またはスタンドアロンの役割として、仲介サーバーが展開されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="62f17-112">You must have a Mediation Server deployed, either as part of a Front End Server or as a standalone role.</span></span> <span data-ttu-id="62f17-113">また、IP-PBX ゲートウェイの展開も必要です。</span><span class="sxs-lookup"><span data-stu-id="62f17-113">You must also deploy an IP-PBX gateway.</span></span>
    
- <span data-ttu-id="62f17-114">職場経由で通話を有効にするすべてのユーザーは、PBX 電話システムで、直接の内側ダイヤル (DID) を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="62f17-114">All users who will be enabled for Call Via Work must have a Direct Inward Dialing (DID) on the PBX phone system.</span></span> 
    
- <span data-ttu-id="62f17-115">エンタープライズ Voip の勤務先ユーザーから、すべての通話を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="62f17-115">You must enable all Call Via Work users for Enterprise Voice.</span></span> <span data-ttu-id="62f17-116">この操作を行う場合、各ユーザーの Skype for Business の電話番号を、対応する PBX 電話システムの対応する DID 番号に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="62f17-116">When you do this, you must configure the Skype for Business DID number for each user to the corresponding DID number for the corresponding PBX phone system.</span></span> 
    
- <span data-ttu-id="62f17-117">勤務先で通話を使用するすべてのユーザーは、Skype for Business クライアントの **[Advanced Connections** ] オプションで**自動構成**を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="62f17-117">All users who will be using Call Via Work must have **Automatic Configuration** selected in their **Advanced Connections** option in their Skype for Business client.</span></span> <span data-ttu-id="62f17-118">これにより、クライアントは UCWA Url を検出できるようになります。</span><span class="sxs-lookup"><span data-stu-id="62f17-118">This enables the client to discover the UCWA URLs.</span></span> <span data-ttu-id="62f17-119">[**自動構成**] は既定で選択されています。</span><span class="sxs-lookup"><span data-stu-id="62f17-119">**Automatic Configuration** is the default selection.</span></span>
    
- <span data-ttu-id="62f17-120">職場ユーザーからの通話ごとに、着信の転送と同時呼び出しを有効にします。</span><span class="sxs-lookup"><span data-stu-id="62f17-120">For each Call Via Work user, enable call forwarding and simultaneous ringing.</span></span> 
    
- <span data-ttu-id="62f17-121">職場ユーザーからの通話ごとに、ダイヤルイン会議と会議のダイヤルアウトが有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="62f17-121">For each Call Via Work user, ensure that dial-in conferencing and conferencing dial-out are enabled.</span></span> <span data-ttu-id="62f17-122">こうすることで、これらのユーザーは Skype for Business 会議にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="62f17-122">This enables these users to get into and out of Skype for Business conferences.</span></span>
    
- <span data-ttu-id="62f17-123">すべての通話について、[委任]、[チーム呼び出し]、[応答] グループが [すべて] で無効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="62f17-123">Ensure that delegation, team call, and response group are disabled for every Call Via Work user.</span></span>
    
## <a name="deploy-call-via-work"></a><span data-ttu-id="62f17-124">"勤務先から通話" の展開</span><span class="sxs-lookup"><span data-stu-id="62f17-124">Deploy Call Via Work</span></span>

<span data-ttu-id="62f17-125">前提条件が満たされたら、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="62f17-125">After the prerequisites are in place, do the following:</span></span>
  
- <span data-ttu-id="62f17-126">展開用のグローバル電話番号を作成します。 Skype for Business では、勤務先から通話を発信しているユーザーの PBX の発信者番号認識が表示されます。</span><span class="sxs-lookup"><span data-stu-id="62f17-126">Create a global phone number for your deployment which Skype for Business displays on the PBX caller ID of users who are making Call Via Work calls.</span></span> 
    
- <span data-ttu-id="62f17-127">勤務先ポリシーを使用して1つ以上の通話を作成する</span><span class="sxs-lookup"><span data-stu-id="62f17-127">Create one or more Call Via Work policies</span></span>
    
- <span data-ttu-id="62f17-128">勤務先ポリシー経由で通話を有効にする各ユーザーに、職場ポリシー経由で通話を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="62f17-128">Assign a Call Via Work policy to each user who will be enabled for Call Via Work</span></span>
    
### <a name="create-the-call-via-work-global-phone-number"></a><span data-ttu-id="62f17-129">"勤務先から通話" グローバル電話番号の作成</span><span class="sxs-lookup"><span data-stu-id="62f17-129">Create the Call Via Work global phone number</span></span>

- <span data-ttu-id="62f17-130">次のコマンドレットを入力します。</span><span class="sxs-lookup"><span data-stu-id="62f17-130">Type the following cmdlet</span></span>
    
  ```
  Set-CsRoutingConfiguration -CallViaWorkCallerId +<PhoneNumber>
  ```

    <span data-ttu-id="62f17-131">たとえば、次のコマンドレットではグローバル電話番号が 1-555-123-4567 に設定されます。</span><span class="sxs-lookup"><span data-stu-id="62f17-131">For example, the following cmdlet sets the global phone number to 1-555-123-4567.</span></span>
    
  ```
  Set-CsRoutingConfiguration -CallViaWorkCallerId +15551234567
  ```

### <a name="create-a-call-via-work-policy"></a><span data-ttu-id="62f17-132">"勤務先から通話" ポリシーの作成</span><span class="sxs-lookup"><span data-stu-id="62f17-132">Create a Call Via Work policy</span></span>

- <span data-ttu-id="62f17-133">次のコマンドレットを入力します。</span><span class="sxs-lookup"><span data-stu-id="62f17-133">Type the following cmdlet</span></span>
    
  ```
  New-CsCallViaWorkPolicy [-Identity] <XdsIdentity> [-Tenant <guid>] [-Enabled <bool>] [-UseAdminCallbackNumber  <bool>] [-AdminCallbackNumber <string>] [-InMemory] [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]
  ```

    <span data-ttu-id="62f17-134">たとえば、次のコマンドレットでは、ContosoUser1CvWP という勤務ポリシーを使って通話を作成し、管理者のコールバック番号を使用するようにユーザーに要求し、そのコールバック番号を1-555-789-1234 に設定します。</span><span class="sxs-lookup"><span data-stu-id="62f17-134">For example, the following cmdlet creates a Call Via Work policy called ContosoUser1CvWP, requires the user to use an admin callback number, and sets that callback number to 1-555-789-1234.</span></span>
    
  ```
  New-CsCallViaWorkPolicy -Identity Tag:ContosoUser1CvWP -Enabled $true -UseAdminCallbackNumber $true -AdminCallbackNumber +15557891234
  ```

### <a name="assign-a-call-via-work-policy-to-a-user"></a><span data-ttu-id="62f17-135">勤務ポリシーを使ってユーザーに通話を割り当てる</span><span class="sxs-lookup"><span data-stu-id="62f17-135">Assign a Call Via Work policy to a user</span></span>

- <span data-ttu-id="62f17-136">次のコマンドレットを入力します。</span><span class="sxs-lookup"><span data-stu-id="62f17-136">Type the following cmdlet</span></span>
    
  ```
  Grant-CsCallViaWorkPolicy -Identity <UserName> -PolicyName Tag:<PolicyName>
  ```

    <span data-ttu-id="62f17-137">たとえば、次のコマンドレットは、Work policy "ContosoUser1CvWP" を使って呼び出しを、 **ContosoUser1**という名前のユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="62f17-137">For example, the following cmdlet assigns the Call Via Work policy "ContosoUser1CvWP" to the user named **ContosoUser1**.</span></span>
    
  ```
  Grant-CsCallViaWorkPolicy -Identity ContosoUser1 -PolicyName Tag:ContosoUser1CvWP
  ```

## <a name="see-also"></a><span data-ttu-id="62f17-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="62f17-138">See also</span></span>

[<span data-ttu-id="62f17-139">Skype for Business Server での勤務先での通話の計画</span><span class="sxs-lookup"><span data-stu-id="62f17-139">Plan for Call Via Work in Skype for Business Server</span></span>](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)

