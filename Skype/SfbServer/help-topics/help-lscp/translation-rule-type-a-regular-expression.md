---
title: 正規表現の翻訳規則の種類
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceRuleRegexEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5ee83724-b399-4f8d-8f6d-4b53a26296b4
description: このパターンのフィールドの一致を使用して、変換する番号と一致するパターンを指定します。 変換ルール] フィールドに、変換後の番号の書式のパターンを指定します。 入力する場合など、^\+(\d{9}\d+)$ このパターンを一致フィールドと 011$ 1 の変換ルール] フィールドに、ルールは +441235551010 が 011441235551010 に変換されます。
ms.openlocfilehash: f6fa4b1d0225f081d041adfeb1b0a86385813b8f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32200444"
---
# <a name="translation-rule-type-a-regular-expression"></a><span data-ttu-id="772df-105">変換ルール: 正規表現の入力</span><span class="sxs-lookup"><span data-stu-id="772df-105">Translation Rule: Type a Regular Expression</span></span>
 
<span data-ttu-id="772df-106">**このパターンに一致する**フィールドに変換するのには数値が一致するように使用するパターンを指定します。</span><span class="sxs-lookup"><span data-stu-id="772df-106">In the **Match this pattern** field, specify the pattern that will be used to match the numbers to be translated.</span></span> <span data-ttu-id="772df-107">**変換ルール**] フィールドに、変換後の番号の書式のパターンを指定します。</span><span class="sxs-lookup"><span data-stu-id="772df-107">In the **Translation rule** field, specify a pattern for the format of translated numbers.</span></span> <span data-ttu-id="772df-108">入力する場合など、^\+(\d{9}\d+)$ で、**このパターンに一致する**フィールドと 011 +441235551010 が 011441235551010 に変換**変換ルール**] フィールドに、ルールでは 1 ドルです。</span><span class="sxs-lookup"><span data-stu-id="772df-108">For example, if you enter ^\+(\d{9}\d+)$ in the **Match this pattern** field and 011$1 in the **Translation rule** field, the rule will translate +441235551010 to 011441235551010.</span></span>
  
<span data-ttu-id="772df-109">詳細ビジネス サーバーのコントロール パネルの Skype を使用して実行できるさまざまな手順については、[ビジネス サーバー 2015 の Skype の管理](../../manage/manage.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="772df-109">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>
  

