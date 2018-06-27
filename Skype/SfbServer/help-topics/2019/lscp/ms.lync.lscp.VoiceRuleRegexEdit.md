---
title: 正規表現の翻訳規則の種類
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceRuleRegexEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5ee83724-b399-4f8d-8f6d-4b53a26296b4
description: このパターンのフィールドの一致を使用して、変換する番号と一致するパターンを指定します。 変換ルール] フィールドに、変換後の番号の書式のパターンを指定します。 入力する場合など、^\+(\d{9}\d+)$ このパターンを一致フィールドと 011$ 1 の変換ルール] フィールドに、ルールは +441235551010 が 011441235551010 に変換されます。
ms.openlocfilehash: f7218ae5b10b0e0b9ad4358eed37f181141f3469
ms.sourcegitcommit: b42a6a56a0e1e4be1239174c1c3b4ab86517d043
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "20049185"
---
# <a name="translation-rule-type-a-regular-expression"></a><span data-ttu-id="108c8-105">翻訳規則: 正規表現を入力します。</span><span class="sxs-lookup"><span data-stu-id="108c8-105">Translation Rule: Type a Regular Expression</span></span>
 
<span data-ttu-id="108c8-106">**このパターンに一致する**フィールドに変換するのには数値が一致するように使用するパターンを指定します。</span><span class="sxs-lookup"><span data-stu-id="108c8-106">In the **Match this pattern** field, specify the pattern that will be used to match the numbers to be translated.</span></span> <span data-ttu-id="108c8-107">**変換ルール**] フィールドに、変換後の番号の書式のパターンを指定します。</span><span class="sxs-lookup"><span data-stu-id="108c8-107">In the **Translation rule** field, specify a pattern for the format of translated numbers.</span></span> <span data-ttu-id="108c8-108">入力する場合など、^\+(\d{9}\d+)$ で、**このパターンに一致する**フィールドと 011 +441235551010 が 011441235551010 に変換**変換ルール**] フィールドに、ルールでは 1 ドルです。</span><span class="sxs-lookup"><span data-stu-id="108c8-108">For example, if you enter ^\+(\d{9}\d+)$ in the **Match this pattern** field and 011$1 in the **Translation rule** field, the rule will translate +441235551010 to 011441235551010.</span></span>
  
 
  

