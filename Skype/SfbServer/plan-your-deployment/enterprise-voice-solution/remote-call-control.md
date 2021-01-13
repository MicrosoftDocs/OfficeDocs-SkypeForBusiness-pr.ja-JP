---
title: Skype for Business でのリモート通話コントロールの計画
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 688a0328-1aa7-449f-b5f7-98c876112ed2
description: リモート通話コントロールは、以前のバージョンの Lync Server の機能で、ユーザーは Lync Server を使用して PBX 電話を制御できます。 Skype for Business Server では、この機能は [Call Via Work] に置き換えられた機能です。 Skype for Business Server 2015 および今後のクライアント バージョンでは、リモート通話コントロールはクライアントで構成できなくなったので、使用するために削除されています。
ms.openlocfilehash: b48eeed656f5889d08fe892da7d7a6896f8a11c3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813517"
---
# <a name="plan-for-remote-call-control-in-skype-for-business"></a><span data-ttu-id="404eb-105">Skype for Business でのリモート通話コントロールの計画</span><span class="sxs-lookup"><span data-stu-id="404eb-105">Plan for remote call control in Skype for Business</span></span>
 
<span data-ttu-id="404eb-106">リモート通話コントロールは、以前のバージョンの Lync Server の機能で、ユーザーは Lync Server を使用して PBX 電話を制御できます。</span><span class="sxs-lookup"><span data-stu-id="404eb-106">Remote call control was a feature in previous versions of Lync Server which enabled users to control their PBX phones with Lync Server.</span></span> <span data-ttu-id="404eb-107">Skype for Business Server では、この機能は [Call Via Work] に置き換えられた機能です。</span><span class="sxs-lookup"><span data-stu-id="404eb-107">In Skype for Business Server, this feature has been replaced with Call Via Work.</span></span>  <span data-ttu-id="404eb-108">*Skype for Business Server 2015 および今後のクライアント バージョンでは、リモート通話コントロールはクライアントで構成できなくなったので、使用するために削除されています。*</span><span class="sxs-lookup"><span data-stu-id="404eb-108">*In the client versions for Skype for Business Server 2015 and going forward, remote call control is no longer available to configure in the client and has been removed for use.*</span></span> 
  
 <span data-ttu-id="404eb-109">Lync Server を実行しているフロントエンド サーバーに所属する組織内のリモート通話コントロール ユーザーは、Skype for Business クライアントを使用している場合でも、リモート通話コントロールを引き続き使用できます。</span><span class="sxs-lookup"><span data-stu-id="404eb-109">Remote call control users in your organization who are homed on Front End Servers running Lync Server can continue to use remote call control, even if they are using a Skype for Business client.</span></span> <span data-ttu-id="404eb-110">ただし、Skype for Business Server にホームを持つユーザーの場合、リモート通話コントロールはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="404eb-110">However, for any users homed on Skype for Business Server, remote call control is not supported.</span></span> <span data-ttu-id="404eb-111">サーバーとクライアントの組み合わせ、およびリモート通話コントロールまたは [作業から通話] をサポートできるかどうかについては、次の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="404eb-111">See the following table for server/client combinations and whether they can support remote call control or Call via Work.</span></span>
  
||<span data-ttu-id="404eb-112">**Skype UI が有効な Skype for Business クライアント**</span><span class="sxs-lookup"><span data-stu-id="404eb-112">**Skype for Business Client With Skype UI enabled**</span></span>|<span data-ttu-id="404eb-113">**Lync UI が有効な Skype for Business クライアント**</span><span class="sxs-lookup"><span data-stu-id="404eb-113">**Skype for Business Client With Lync UI enabled**</span></span>|<span data-ttu-id="404eb-114">**Skype for Business 2016 クライアント**</span><span class="sxs-lookup"><span data-stu-id="404eb-114">**Skype for Business 2016 Client**</span></span>|<span data-ttu-id="404eb-115">**Lync 2013 クライアント**</span><span class="sxs-lookup"><span data-stu-id="404eb-115">**Lync 2013 Client**</span></span>|<span data-ttu-id="404eb-116">**Lync 2010 クライアント**</span><span class="sxs-lookup"><span data-stu-id="404eb-116">**Lync 2010 Client**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
| <span data-ttu-id="404eb-117">Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="404eb-117">Skype for Business Server</span></span> <br/> |<span data-ttu-id="404eb-118">[Call via Work] (仕事から通話)</span><span class="sxs-lookup"><span data-stu-id="404eb-118">Call via Work</span></span>  <br/> |<span data-ttu-id="404eb-119">1 </span><span class="sxs-lookup"><span data-stu-id="404eb-119">1</span></span> <br/> |<span data-ttu-id="404eb-120">[Call via Work] (仕事から通話)</span><span class="sxs-lookup"><span data-stu-id="404eb-120">Call via Work</span></span>  <br/> |<span data-ttu-id="404eb-121">1 </span><span class="sxs-lookup"><span data-stu-id="404eb-121">1</span></span> <br/> |<span data-ttu-id="404eb-122">1 </span><span class="sxs-lookup"><span data-stu-id="404eb-122">1</span></span> <br/> |
| <span data-ttu-id="404eb-123">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="404eb-123">Lync Server 2013</span></span> <br/> |<span data-ttu-id="404eb-124">リモート通話コントロール</span><span class="sxs-lookup"><span data-stu-id="404eb-124">Remote Call Control</span></span>  <br/> |<span data-ttu-id="404eb-125">リモート通話コントロール</span><span class="sxs-lookup"><span data-stu-id="404eb-125">Remote Call Control</span></span>  <br/> |<span data-ttu-id="404eb-126">1 </span><span class="sxs-lookup"><span data-stu-id="404eb-126">1</span></span> <br/> |<span data-ttu-id="404eb-127">リモート通話コントロール</span><span class="sxs-lookup"><span data-stu-id="404eb-127">Remote Call Control</span></span>  <br/> |<span data-ttu-id="404eb-128">リモート通話コントロール</span><span class="sxs-lookup"><span data-stu-id="404eb-128">Remote Call Control</span></span>  <br/> |
| <span data-ttu-id="404eb-129">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="404eb-129">Lync Server 2010</span></span> <br/> |<span data-ttu-id="404eb-130">リモート通話コントロール</span><span class="sxs-lookup"><span data-stu-id="404eb-130">Remote Call Control</span></span>  <br/> |<span data-ttu-id="404eb-131">リモート通話コントロール</span><span class="sxs-lookup"><span data-stu-id="404eb-131">Remote Call Control</span></span>  <br/> |<span data-ttu-id="404eb-132">1 </span><span class="sxs-lookup"><span data-stu-id="404eb-132">1</span></span> <br/> |<span data-ttu-id="404eb-133">リモート通話コントロール</span><span class="sxs-lookup"><span data-stu-id="404eb-133">Remote Call Control</span></span>  <br/> |<span data-ttu-id="404eb-134">リモート通話コントロール</span><span class="sxs-lookup"><span data-stu-id="404eb-134">Remote Call Control</span></span>  <br/> |
   
1. <span data-ttu-id="404eb-135">どちらの機能もサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="404eb-135">Neither feature is supported.</span></span>
  
<span data-ttu-id="404eb-136">詳細については、Lync [](https://go.microsoft.com/fwlink/p/?LinkId=530208) Server 2013 のドキュメントの「リモート通話コントロール」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="404eb-136">For more information, see [Remote Call Control](https://go.microsoft.com/fwlink/p/?LinkId=530208) in the Lync Server 2013 documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="404eb-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="404eb-137">See also</span></span>

[<span data-ttu-id="404eb-138">Plan for Call Via Work in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="404eb-138">Plan for Call Via Work in Skype for Business Server</span></span>](call-via-work.md)
  
[<span data-ttu-id="404eb-139">Skype for Business のデスクトップ クライアント機能の比較</span><span class="sxs-lookup"><span data-stu-id="404eb-139">Desktop client feature comparison for Skype for Business</span></span>](../../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)

[<span data-ttu-id="404eb-140">Skype for Business 通話を行うが、音声には PBX 電話を使用する</span><span class="sxs-lookup"><span data-stu-id="404eb-140">Make a Skype for Business call but use your PBX desk phone for audio</span></span>](https://support.office.com/article/Make-a-Skype-for-Business-call-but-use-your-PBX-desk-phone-for-audio-6a316c11-a05e-460c-b969-32ff0ad848e6)

