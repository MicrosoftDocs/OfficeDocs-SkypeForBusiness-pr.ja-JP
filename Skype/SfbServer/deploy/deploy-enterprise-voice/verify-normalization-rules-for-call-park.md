---
title: Skype for Business のコール パークの正規化ルールを確認する
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
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: deaa170f-041e-45cb-8eab-f02931ab541e
description: Skype for Business Server エンタープライズ VoIP のコール パークの正規化ルールについて説明します。
ms.openlocfilehash: d1bcd6817b1f59f73a8c4ef1562e90253a99bd30
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830577"
---
# <a name="verify-normalization-rules-for-call-park-in-skype-for-business"></a><span data-ttu-id="dea52-103">Skype for Business のコール パークの正規化ルールを確認する</span><span class="sxs-lookup"><span data-stu-id="dea52-103">Verify normalization rules for Call Park in Skype for Business</span></span>
 
<span data-ttu-id="dea52-104">Skype for Business Server エンタープライズ VoIP のコール パークの正規化ルールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="dea52-104">Learn about normalization rules for Call Park in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="dea52-105">コール パーク オービットを正規化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dea52-105">Call Park orbits must not be normalized.</span></span> <span data-ttu-id="dea52-106">ダイヤル プランを確認して、オービット番号が正規化されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="dea52-106">Check your dial plans to be sure that your orbit numbers are not normalized.</span></span> <span data-ttu-id="dea52-107">オービットが正規化されるのを防ぐために追加の正規化ルールを作成する必要がある場合は [、「Create or modify a dial plan in Skype for Business Server](dial-plans.md) to define a new normalization rule, so that Pattern to **match** identifies the orbit range and **Translation pattern** is **$1**.</span><span class="sxs-lookup"><span data-stu-id="dea52-107">If you must create an additional normalization rule to prevent your orbits from being normalized, follow the procedure in [Create or modify a dial plan in Skype for Business Server](dial-plans.md) to define a new normalization rule, so that **Pattern to match** identifies the orbit range and **Translation pattern** is **$1**.</span></span> <span data-ttu-id="dea52-108">たとえば、コール パーク オービット範囲が 7000 ~ 7999 の場合、一致するパターンは **^(7\d {3} )$** で、**変換** パターンは **$1** です。 </span><span class="sxs-lookup"><span data-stu-id="dea52-108">For example, if your Call Park orbit range is 7000 - 7999, the **Pattern to match** is **^(7\d{3})$** and **Translation pattern** is **$1**.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="dea52-109">ダイヤル プランの既定の正規化ルールに **^(\d \* ) が含まれている必要があります**。</span><span class="sxs-lookup"><span data-stu-id="dea52-109">Be sure that the default normalization rule in your dial plans does not contain **^(\d\*)**.</span></span> <span data-ttu-id="dea52-110">そうしないと、コール パーク正規化ルールは実行されません。</span><span class="sxs-lookup"><span data-stu-id="dea52-110">Otherwise, your Call Park normalization rule will never run.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="dea52-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="dea52-111">See also</span></span>

[<span data-ttu-id="dea52-112">Skype for Business Server でダイヤル プランを作成または変更する</span><span class="sxs-lookup"><span data-stu-id="dea52-112">Create or modify a dial plan in Skype for Business Server</span></span>](dial-plans.md)

