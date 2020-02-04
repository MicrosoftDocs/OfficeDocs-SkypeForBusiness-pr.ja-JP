---
title: 翻訳ルール正規表現を入力する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.VoiceRuleRegexEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5ee83724-b399-4f8d-8f6d-4b53a26296b4
description: '[次のパターンに一致] フィールドに、翻訳する数値と一致させるために使用するパターンを指定します。 [翻訳ルール] フィールドで、翻訳された番号の書式のパターンを指定します。 たとえば、「^\+(\d{9}\d +) $」と入力すると、[次のパターンに一致します] フィールドと [翻訳ルール] フィールドに 011 $ 1 と入力すると、ルールが + 441235551010 から011441235551010に変換されます。'
ms.openlocfilehash: 98a04d3c7346557bcb095e7187a13f2e93646075
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41699352"
---
# <a name="translation-rule-type-a-regular-expression"></a><span data-ttu-id="a2587-105">変換ルール: 正規表現の入力</span><span class="sxs-lookup"><span data-stu-id="a2587-105">Translation Rule: Type a Regular Expression</span></span>
 
<span data-ttu-id="a2587-106">[**次のパターンに一致**] フィールドに、翻訳する数値と一致させるために使用するパターンを指定します。</span><span class="sxs-lookup"><span data-stu-id="a2587-106">In the **Match this pattern** field, specify the pattern that will be used to match the numbers to be translated.</span></span> <span data-ttu-id="a2587-107">[**翻訳ルール**] フィールドで、翻訳された番号の書式のパターンを指定します。</span><span class="sxs-lookup"><span data-stu-id="a2587-107">In the **Translation rule** field, specify a pattern for the format of translated numbers.</span></span> <span data-ttu-id="a2587-108">\+たとえば、「^ (\d{9}\d +) $」と入力すると、[次のパターンに**一致**します] フィールドと [**翻訳ルール**] フィールドに 011 $ 1 と入力すると、ルールが + 441235551010 から011441235551010に変換されます。</span><span class="sxs-lookup"><span data-stu-id="a2587-108">For example, if you enter ^\+(\d{9}\d+)$ in the **Match this pattern** field and 011$1 in the **Translation rule** field, the rule will translate +441235551010 to 011441235551010.</span></span>
  
<span data-ttu-id="a2587-109">Skype for Business Server コントロールパネルを使用して実行できるさまざまな手順の詳細については、「Skype for business [server 2015 を管理](../../manage/manage.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2587-109">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>
  

