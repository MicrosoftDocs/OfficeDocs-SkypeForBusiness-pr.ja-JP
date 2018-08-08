---
title: ビジネス用の Skype でのリモート通話コントロールの計画
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 688a0328-1aa7-449f-b5f7-98c876112ed2
description: リモート通話コントロールでは、Lync Server は PBX 電話を制御するユーザーを有効にする Lync Server の以前のバージョンの機能をしました。 ビジネス サーバーの Skype は、この機能は作業時間を使用して呼び出しを交換済み。 Skype ビジネス サーバー 2015 と進行中の転送、リモート呼び出しのクライアント バージョンではコントロールは、クライアントで構成するのには使用できなく、使用するため削除されました
ms.openlocfilehash: d2203840672bfc73cf478254b9d115fd0375c902
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "21014544"
---
# <a name="plan-for-remote-call-control-in-skype-for-business"></a><span data-ttu-id="eae38-105">ビジネス用の Skype でのリモート通話コントロールの計画</span><span class="sxs-lookup"><span data-stu-id="eae38-105">Plan for remote call control in Skype for Business</span></span>
 
<span data-ttu-id="eae38-106">リモート通話コントロールでは、Lync Server は PBX 電話を制御するユーザーを有効にする Lync Server の以前のバージョンの機能をしました。</span><span class="sxs-lookup"><span data-stu-id="eae38-106">Remote call control was a feature in previous versions of Lync Server which enabled users to control their PBX phones with Lync Server.</span></span> <span data-ttu-id="eae38-107">ビジネス サーバーの Skype は、この機能は作業時間を使用して呼び出しを交換済み。</span><span class="sxs-lookup"><span data-stu-id="eae38-107">In Skype for Business Server, this feature has been replaced with Call Via Work.</span></span>  <span data-ttu-id="eae38-108">*Skype ビジネス サーバー 2015 と進行中の転送、リモート呼び出しのクライアント バージョンではコントロールは、クライアントで構成するのには使用できなく、使用するため削除されました*</span><span class="sxs-lookup"><span data-stu-id="eae38-108">*In the client versions for Skype for Business Server 2015 and going forward, remote call control is no longer available to configure in the client and has been removed for use.*</span></span> 
  
 <span data-ttu-id="eae38-109">ビジネス クライアント用の Skype を使用している場合でも、Lync Server を実行して、フロント エンド サーバーに置かれている組織内のリモート呼び出しコントロール ユーザーは、リモート通話コントロールを使用する続行できます。</span><span class="sxs-lookup"><span data-stu-id="eae38-109">Remote call control users in your organization who are homed on Front End Servers running Lync Server can continue to use remote call control, even if they are using a Skype for Business client.</span></span> <span data-ttu-id="eae38-110">ただし、すべてのユーザーは、Skype のビジネス サーバーのホームのリモート呼び出しコントロール サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="eae38-110">However, for any users homed on Skype for Business Server, remote call control is not supported.</span></span> <span data-ttu-id="eae38-111">サーバー/クライアントの組み合わせおよびリモート通話コントロールまたは「勤務先から電話」機能に対応しているかどうかについては次の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eae38-111">See the following table for server/client combinations and whether they can support remote call control or Call via Work.</span></span>
  
||<span data-ttu-id="eae38-112">**Skype ビジネス クライアント Skype UI を使用して有効になっているため**</span><span class="sxs-lookup"><span data-stu-id="eae38-112">**Skype for Business Client With Skype UI enabled**</span></span>|<span data-ttu-id="eae38-113">**Skype ビジネス クライアント Lync UI を使用して有効になっているため**</span><span class="sxs-lookup"><span data-stu-id="eae38-113">**Skype for Business Client With Lync UI enabled**</span></span>|<span data-ttu-id="eae38-114">**2016 クライアントのビジネス用の Skype**</span><span class="sxs-lookup"><span data-stu-id="eae38-114">**Skype for Business 2016 Client**</span></span>|<span data-ttu-id="eae38-115">**Lync 2013 クライアント**</span><span class="sxs-lookup"><span data-stu-id="eae38-115">**Lync 2013 Client**</span></span>|<span data-ttu-id="eae38-116">**Lync 2010 クライアント**</span><span class="sxs-lookup"><span data-stu-id="eae38-116">**Lync 2010 Client**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
| <span data-ttu-id="eae38-117">Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="eae38-117">Skype for Business Server</span></span> <br/> |<span data-ttu-id="eae38-118">勤務先から通話</span><span class="sxs-lookup"><span data-stu-id="eae38-118">Call via Work</span></span>  <br/> |<span data-ttu-id="eae38-119">1</span><span class="sxs-lookup"><span data-stu-id="eae38-119">1</span></span> <br/> |<span data-ttu-id="eae38-120">勤務先から通話</span><span class="sxs-lookup"><span data-stu-id="eae38-120">Call via Work</span></span>  <br/> |<span data-ttu-id="eae38-121">1</span><span class="sxs-lookup"><span data-stu-id="eae38-121">1</span></span> <br/> |<span data-ttu-id="eae38-122">1</span><span class="sxs-lookup"><span data-stu-id="eae38-122">1</span></span> <br/> |
| <span data-ttu-id="eae38-123">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eae38-123">Lync Server 2013</span></span> <br/> |<span data-ttu-id="eae38-124">リモート通話コントロール</span><span class="sxs-lookup"><span data-stu-id="eae38-124">Remote Call Control</span></span>  <br/> |<span data-ttu-id="eae38-125">リモート通話コントロール</span><span class="sxs-lookup"><span data-stu-id="eae38-125">Remote Call Control</span></span>  <br/> |<span data-ttu-id="eae38-126">1</span><span class="sxs-lookup"><span data-stu-id="eae38-126">1</span></span> <br/> |<span data-ttu-id="eae38-127">リモート通話コントロール</span><span class="sxs-lookup"><span data-stu-id="eae38-127">Remote Call Control</span></span>  <br/> |<span data-ttu-id="eae38-128">リモート通話コントロール</span><span class="sxs-lookup"><span data-stu-id="eae38-128">Remote Call Control</span></span>  <br/> |
| <span data-ttu-id="eae38-129">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="eae38-129">Lync Server 2010</span></span> <br/> |<span data-ttu-id="eae38-130">リモート通話コントロール</span><span class="sxs-lookup"><span data-stu-id="eae38-130">Remote Call Control</span></span>  <br/> |<span data-ttu-id="eae38-131">リモート通話コントロール</span><span class="sxs-lookup"><span data-stu-id="eae38-131">Remote Call Control</span></span>  <br/> |<span data-ttu-id="eae38-132">1</span><span class="sxs-lookup"><span data-stu-id="eae38-132">1</span></span> <br/> |<span data-ttu-id="eae38-133">リモート通話コントロール</span><span class="sxs-lookup"><span data-stu-id="eae38-133">Remote Call Control</span></span>  <br/> |<span data-ttu-id="eae38-134">リモート通話コントロール</span><span class="sxs-lookup"><span data-stu-id="eae38-134">Remote Call Control</span></span>  <br/> |
   
1. <span data-ttu-id="eae38-135">どちらの機能がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="eae38-135">Neither feature is supported.</span></span>
  
<span data-ttu-id="eae38-136">詳細については、[リモート通話コントロール](https://go.microsoft.com/fwlink/p/?LinkId=530208)Lync Server 2013 のマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="eae38-136">For more information, see [Remote Call Control](https://go.microsoft.com/fwlink/p/?LinkId=530208) in the Lync Server 2013 documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="eae38-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="eae38-137">See also</span></span>

[<span data-ttu-id="eae38-138">Skype ビジネス サーバーの作業時間を使用して呼び出すのための計画</span><span class="sxs-lookup"><span data-stu-id="eae38-138">Plan for Call Via Work in Skype for Business Server</span></span>](call-via-work.md)
  
[<span data-ttu-id="eae38-139">Skype for Business のデスクトップ クライアント機能の比較</span><span class="sxs-lookup"><span data-stu-id="eae38-139">Desktop client feature comparison for Skype for Business</span></span>](../../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)

[<span data-ttu-id="eae38-140">Skype のビジネスの呼び出しが PBX 卓上電話を使用して、オーディオの</span><span class="sxs-lookup"><span data-stu-id="eae38-140">Make a Skype for Business call but use your PBX desk phone for audio</span></span>](https://support.office.com/en-us/article/Make-a-Skype-for-Business-call-but-use-your-PBX-desk-phone-for-audio-6a316c11-a05e-460c-b969-32ff0ad848e6)

