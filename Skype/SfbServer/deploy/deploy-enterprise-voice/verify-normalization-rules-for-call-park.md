---
title: Skype for Business のコールパークの正規化ルールを確認する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: deaa170f-041e-45cb-8eab-f02931ab541e
description: Skype for Business Server Enterprise Voice のコールパークの正規化ルールについて説明します。
ms.openlocfilehash: 38de300970341d563f2a532847a39c2fe98e15e7
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240018"
---
# <a name="verify-normalization-rules-for-call-park-in-skype-for-business"></a><span data-ttu-id="38b3c-103">Skype for Business のコールパークの正規化ルールを確認する</span><span class="sxs-lookup"><span data-stu-id="38b3c-103">Verify normalization rules for Call Park in Skype for Business</span></span>
 
<span data-ttu-id="38b3c-104">Skype for Business Server Enterprise Voice のコールパークの正規化ルールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="38b3c-104">Learn about normalization rules for Call Park in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="38b3c-105">コールパーク orbits は正規化されていない必要があります。</span><span class="sxs-lookup"><span data-stu-id="38b3c-105">Call Park orbits must not be normalized.</span></span> <span data-ttu-id="38b3c-106">ダイヤル プランでオービット番号が正規化されていないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="38b3c-106">Check your dial plans to be sure that your orbit numbers are not normalized.</span></span> <span data-ttu-id="38b3c-107">追加の正規化ルールを作成して、orbits が正規化されないようにする必要がある場合は、「 [Skype For Business Server のダイヤルプランを作成または変更](dial-plans.md)する」の手順に従って、新しい正規化ルールを定義し、**パターンが一致する**ようにします。オービット範囲と**翻訳パターン**が **$1**であることを示します。</span><span class="sxs-lookup"><span data-stu-id="38b3c-107">If you must create an additional normalization rule to prevent your orbits from being normalized, follow the procedure in [Create or modify a dial plan in Skype for Business Server](dial-plans.md) to define a new normalization rule, so that **Pattern to match** identifies the orbit range and **Translation pattern** is **$1**.</span></span> <span data-ttu-id="38b3c-108">たとえば、"Call パーク" というコールパーク範囲が 7000 ~ 7999 の場合、**照合するパターン**は **^ ({3}7 \ d) $** で、**翻訳パターン**は **$1**です。</span><span class="sxs-lookup"><span data-stu-id="38b3c-108">For example, if your Call Park orbit range is 7000 - 7999, the **Pattern to match** is **^(7\d{3})$** and **Translation pattern** is **$1**.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="38b3c-109">ダイヤルプランの既定の正規化ルールに **^ (\d\*)** が含まれていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="38b3c-109">Be sure that the default normalization rule in your dial plans does not contain **^(\d\*)**.</span></span> <span data-ttu-id="38b3c-110">そうしないと、Call パークの正規化ルールは実行されません。</span><span class="sxs-lookup"><span data-stu-id="38b3c-110">Otherwise, your Call Park normalization rule will never run.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="38b3c-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="38b3c-111">See also</span></span>

[<span data-ttu-id="38b3c-112">Skype for Business Server でダイヤルプランを作成または変更する</span><span class="sxs-lookup"><span data-stu-id="38b3c-112">Create or modify a dial plan in Skype for Business Server</span></span>](dial-plans.md)

