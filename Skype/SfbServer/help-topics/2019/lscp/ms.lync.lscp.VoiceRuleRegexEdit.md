---
title: 変換ルールの正規表現の種類
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.VoiceRuleRegexEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 5ee83724-b399-4f8d-8f6d-4b53a26296b4
ROBOTS: NOINDEX, NOFOLLOW
description: '[このパターンを照合] フィールドで、変換する番号を照合するために使用するパターンを指定します。 [変換ルール] フィールドで、変換される番号の形式のパターンを指定します。 '
ms.openlocfilehash: a1e04cc94c004b520c077816ae535ca4154047ee
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49819987"
---
# <a name="translation-rule-type-a-regular-expression"></a><span data-ttu-id="f4351-104">変換ルール: 正規表現の入力</span><span class="sxs-lookup"><span data-stu-id="f4351-104">Translation Rule: Type a Regular Expression</span></span>
 
<span data-ttu-id="f4351-105">[**このパターンを照合**] フィールドで、変換する番号を照合するために使用するパターンを指定します。</span><span class="sxs-lookup"><span data-stu-id="f4351-105">In the **Match this pattern** field, specify the pattern that will be used to match the numbers to be translated.</span></span> <span data-ttu-id="f4351-106">[**変換ルール**] フィールドで、変換される番号の形式のパターンを指定します。</span><span class="sxs-lookup"><span data-stu-id="f4351-106">In the **Translation rule** field, specify a pattern for the format of translated numbers.</span></span> <span data-ttu-id="f4351-107">たとえば、[このパターンに一致] フィールドに ^ (\d \d+)$ を入力し、変換ルール フィールドに 011$1 を入力すると、ルールは \+ {9} +441235551010 を 011441235551010に変換します。</span><span class="sxs-lookup"><span data-stu-id="f4351-107">For example, if you enter ^\+(\d{9}\d+)$ in the **Match this pattern** field and 011$1 in the **Translation rule** field, the rule will translate +441235551010 to 011441235551010.</span></span> 
  
 
  

