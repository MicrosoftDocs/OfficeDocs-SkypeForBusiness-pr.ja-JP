---
title: Skype for Business のリモート通話コントロールを計画する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: リモート通話コントロールは、ユーザーが Lync Server で PBX 電話を制御できるようにする以前のバージョンの Lync Server の機能です。 Skype for Business Server では、この機能は勤務先からの通話に置き換えられました。 Skype for Business Server 2015 のクライアントバージョンでは、リモート通話コントロールはクライアントでの構成に使用できなくなり、使用するために削除されました。
ms.openlocfilehash: 67010a0bc74ef46dcf204e3b2a905be87c182daf
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802507"
---
# <a name="plan-for-remote-call-control-in-skype-for-business"></a><span data-ttu-id="219df-105">Skype for Business のリモート通話コントロールを計画する</span><span class="sxs-lookup"><span data-stu-id="219df-105">Plan for remote call control in Skype for Business</span></span>
 
<span data-ttu-id="219df-106">リモート通話コントロールは、ユーザーが Lync Server で PBX 電話を制御できるようにする以前のバージョンの Lync Server の機能です。</span><span class="sxs-lookup"><span data-stu-id="219df-106">Remote call control was a feature in previous versions of Lync Server which enabled users to control their PBX phones with Lync Server.</span></span> <span data-ttu-id="219df-107">Skype for Business Server では、この機能は勤務先からの通話に置き換えられました。</span><span class="sxs-lookup"><span data-stu-id="219df-107">In Skype for Business Server, this feature has been replaced with Call Via Work.</span></span>  <span data-ttu-id="219df-108">*Skype for Business Server 2015 のクライアントバージョンでは、リモート通話コントロールはクライアントでの構成に使用できなくなり、使用するために削除されました。*</span><span class="sxs-lookup"><span data-stu-id="219df-108">*In the client versions for Skype for Business Server 2015 and going forward, remote call control is no longer available to configure in the client and has been removed for use.*</span></span> 
  
 <span data-ttu-id="219df-109">リモート通話コントロール Lync Server を実行しているフロントエンドサーバーを使っている組織内のユーザーは、Skype for Business クライアントを使用している場合でも、引き続きリモート通話コントロールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="219df-109">Remote call control users in your organization who are homed on Front End Servers running Lync Server can continue to use remote call control, even if they are using a Skype for Business client.</span></span> <span data-ttu-id="219df-110">ただし、Skype for Business Server を使用しているすべてのユーザーは、リモート通話コントロールはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="219df-110">However, for any users homed on Skype for Business Server, remote call control is not supported.</span></span> <span data-ttu-id="219df-111">サーバー/クライアントの組み合わせおよびリモート通話コントロールまたは「勤務先から電話」機能に対応しているかどうかについては次の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="219df-111">See the following table for server/client combinations and whether they can support remote call control or Call via Work.</span></span>
  
||<span data-ttu-id="219df-112">**Skype UI を有効にした skype for Business クライアント**</span><span class="sxs-lookup"><span data-stu-id="219df-112">**Skype for Business Client With Skype UI enabled**</span></span>|<span data-ttu-id="219df-113">**Lync UI を有効にした Skype for Business クライアント**</span><span class="sxs-lookup"><span data-stu-id="219df-113">**Skype for Business Client With Lync UI enabled**</span></span>|<span data-ttu-id="219df-114">**Skype for Business 2016 クライアント**</span><span class="sxs-lookup"><span data-stu-id="219df-114">**Skype for Business 2016 Client**</span></span>|<span data-ttu-id="219df-115">**Lync 2013 クライアント**</span><span class="sxs-lookup"><span data-stu-id="219df-115">**Lync 2013 Client**</span></span>|<span data-ttu-id="219df-116">**Lync 2010 クライアント**</span><span class="sxs-lookup"><span data-stu-id="219df-116">**Lync 2010 Client**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
| <span data-ttu-id="219df-117">Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="219df-117">Skype for Business Server</span></span> <br/> |<span data-ttu-id="219df-118">勤務先から通話</span><span class="sxs-lookup"><span data-stu-id="219df-118">Call via Work</span></span>  <br/> |<span data-ttu-id="219df-119">1</span><span class="sxs-lookup"><span data-stu-id="219df-119">1</span></span> <br/> |<span data-ttu-id="219df-120">勤務先から通話</span><span class="sxs-lookup"><span data-stu-id="219df-120">Call via Work</span></span>  <br/> |<span data-ttu-id="219df-121">1</span><span class="sxs-lookup"><span data-stu-id="219df-121">1</span></span> <br/> |<span data-ttu-id="219df-122">1</span><span class="sxs-lookup"><span data-stu-id="219df-122">1</span></span> <br/> |
| <span data-ttu-id="219df-123">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="219df-123">Lync Server 2013</span></span> <br/> |<span data-ttu-id="219df-124">リモート通話コントロール</span><span class="sxs-lookup"><span data-stu-id="219df-124">Remote Call Control</span></span>  <br/> |<span data-ttu-id="219df-125">リモート通話コントロール</span><span class="sxs-lookup"><span data-stu-id="219df-125">Remote Call Control</span></span>  <br/> |<span data-ttu-id="219df-126">件</span><span class="sxs-lookup"><span data-stu-id="219df-126">1</span></span> <br/> |<span data-ttu-id="219df-127">リモート通話コントロール</span><span class="sxs-lookup"><span data-stu-id="219df-127">Remote Call Control</span></span>  <br/> |<span data-ttu-id="219df-128">リモート通話コントロール</span><span class="sxs-lookup"><span data-stu-id="219df-128">Remote Call Control</span></span>  <br/> |
| <span data-ttu-id="219df-129">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="219df-129">Lync Server 2010</span></span> <br/> |<span data-ttu-id="219df-130">リモート通話コントロール</span><span class="sxs-lookup"><span data-stu-id="219df-130">Remote Call Control</span></span>  <br/> |<span data-ttu-id="219df-131">リモート通話コントロール</span><span class="sxs-lookup"><span data-stu-id="219df-131">Remote Call Control</span></span>  <br/> |<span data-ttu-id="219df-132">件</span><span class="sxs-lookup"><span data-stu-id="219df-132">1</span></span> <br/> |<span data-ttu-id="219df-133">リモート通話コントロール</span><span class="sxs-lookup"><span data-stu-id="219df-133">Remote Call Control</span></span>  <br/> |<span data-ttu-id="219df-134">リモート通話コントロール</span><span class="sxs-lookup"><span data-stu-id="219df-134">Remote Call Control</span></span>  <br/> |
   
1. <span data-ttu-id="219df-135">どちらの機能もサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="219df-135">Neither feature is supported.</span></span>
  
<span data-ttu-id="219df-136">詳細については、「Lync Server 2013 ドキュメントの[リモート通話コントロール](https://go.microsoft.com/fwlink/p/?LinkId=530208)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="219df-136">For more information, see [Remote Call Control](https://go.microsoft.com/fwlink/p/?LinkId=530208) in the Lync Server 2013 documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="219df-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="219df-137">See also</span></span>

[<span data-ttu-id="219df-138">Skype for Business Server での勤務先での通話の計画</span><span class="sxs-lookup"><span data-stu-id="219df-138">Plan for Call Via Work in Skype for Business Server</span></span>](call-via-work.md)
  
[<span data-ttu-id="219df-139">Skype for Business のデスクトップ クライアント機能の比較</span><span class="sxs-lookup"><span data-stu-id="219df-139">Desktop client feature comparison for Skype for Business</span></span>](../../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)

[<span data-ttu-id="219df-140">Skype for Business 通話を発信するが、PBX デスクフォンを使ってオーディオを作成する</span><span class="sxs-lookup"><span data-stu-id="219df-140">Make a Skype for Business call but use your PBX desk phone for audio</span></span>](https://support.office.com/en-us/article/Make-a-Skype-for-Business-call-but-use-your-PBX-desk-phone-for-audio-6a316c11-a05e-460c-b969-32ff0ad848e6)

