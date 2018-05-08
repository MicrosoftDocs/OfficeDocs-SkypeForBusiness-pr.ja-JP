---
title: Skype for Business 2015 でのコール パーク正規化ルールの確認
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: deaa170f-041e-45cb-8eab-f02931ab541e
description: ビジネス サーバーのエンタープライズ VoIP は、Skype のコール パークの正規化規則について説明します。
ms.openlocfilehash: c637240d4c193bbec05228d167d77f7bd18c0d04
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="verify-normalization-rules-for-call-park-in-skype-for-business-2015"></a><span data-ttu-id="a2346-103">Skype for Business 2015 でのコール パーク正規化ルールの確認</span><span class="sxs-lookup"><span data-stu-id="a2346-103">Verify normalization rules for Call Park in Skype for Business 2015</span></span>
 
<span data-ttu-id="a2346-104">ビジネス サーバーのエンタープライズ VoIP は、Skype のコール パークの正規化規則について説明します。</span><span class="sxs-lookup"><span data-stu-id="a2346-104">Learn about normalization rules for Call Park in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="a2346-105">パーク軌道を正規化する必要がありますはありません。</span><span class="sxs-lookup"><span data-stu-id="a2346-105">Call Park orbits must not be normalized.</span></span> <span data-ttu-id="a2346-106">ダイヤル プランでオービット番号が正規化されていないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="a2346-106">Check your dial plans to be sure that your orbit numbers are not normalized.</span></span> <span data-ttu-id="a2346-107">軌道が正規化されていることを防ぐため、追加の正規化ルールを作成する必要がある場合の手順を[を作成するビジネス サーバー 2015 の Skype のダイヤル プランを変更するまたは](dial-plans.md)ため、新しい正規化ルールを定義するのにはその**パターンに一致するには**軌道範囲を識別**変換パターン**は、 **$1**とします。</span><span class="sxs-lookup"><span data-stu-id="a2346-107">If you must create an additional normalization rule to prevent your orbits from being normalized, follow the procedure in [Create or modify a dial plan in Skype for Business Server 2015](dial-plans.md) to define a new normalization rule, so that **Pattern to match** identifies the orbit range and **Translation pattern** is **$1**.</span></span> <span data-ttu-id="a2346-108">などの場合、コール パークの移動範囲は 7000-7999 の場合、**一致させるパターン**は、 **^(7\d{3})$** **$1**で、**翻訳のパターン**です。</span><span class="sxs-lookup"><span data-stu-id="a2346-108">For example, if your Call Park orbit range is 7000 - 7999, the **Pattern to match** is **^(7\d{3})$** and **Translation pattern** is **$1**.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="a2346-109">ダイヤル プランの既定正規化ルールが含まれていないかどうかを必ず **^(\d\*)**。</span><span class="sxs-lookup"><span data-stu-id="a2346-109">Be sure that the default normalization rule in your dial plans does not contain **^(\d\*)**.</span></span> <span data-ttu-id="a2346-110">それ以外の場合、コール パーク正規化ルールは実行されません。</span><span class="sxs-lookup"><span data-stu-id="a2346-110">Otherwise, your Call Park normalization rule will never run.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a2346-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="a2346-111">See also</span></span>

#### 

[<span data-ttu-id="a2346-112">作成またはビジネス サーバー 2015 の Skype のダイヤル プランを変更します。</span><span class="sxs-lookup"><span data-stu-id="a2346-112">Create or modify a dial plan in Skype for Business Server 2015</span></span>](dial-plans.md)

