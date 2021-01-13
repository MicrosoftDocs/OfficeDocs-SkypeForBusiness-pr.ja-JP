---
title: 変換ルールの正規表現の種類
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.VoiceRuleRegexEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5ee83724-b399-4f8d-8f6d-4b53a26296b4
description: '[このパターンを照合] フィールドで、変換する番号を照合するために使用するパターンを指定します。 [変換ルール] フィールドで、変換される番号の形式のパターンを指定します。 たとえば、[このパターンに一致] フィールドに ^ (\d \d+)$ を入力し、変換ルール フィールドに 011$1 を入力すると、ルールは \+ {9} +441235551010 を 011441235551010 に変換します。'
ms.openlocfilehash: badbc5a34325e6bc2b5bef7e67ae39a4c8f02dc7
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49818857"
---
# <a name="translation-rule-type-a-regular-expression"></a><span data-ttu-id="59a43-105">変換ルール: 正規表現の入力</span><span class="sxs-lookup"><span data-stu-id="59a43-105">Translation Rule: Type a Regular Expression</span></span>
 
<span data-ttu-id="59a43-106">[**このパターンを照合**] フィールドで、変換する番号を照合するために使用するパターンを指定します。</span><span class="sxs-lookup"><span data-stu-id="59a43-106">In the **Match this pattern** field, specify the pattern that will be used to match the numbers to be translated.</span></span> <span data-ttu-id="59a43-107">[**変換ルール**] フィールドで、変換される番号の形式のパターンを指定します。</span><span class="sxs-lookup"><span data-stu-id="59a43-107">In the **Translation rule** field, specify a pattern for the format of translated numbers.</span></span> <span data-ttu-id="59a43-108">たとえば、[このパターンに一致] フィールドに ^ (\d \d+)$ を入力し、変換ルール フィールドに 011$1 を入力すると、ルールは \+ {9} +441235551010 を 011441235551010に変換します。</span><span class="sxs-lookup"><span data-stu-id="59a43-108">For example, if you enter ^\+(\d{9}\d+)$ in the **Match this pattern** field and 011$1 in the **Translation rule** field, the rule will translate +441235551010 to 011441235551010.</span></span>
  
<span data-ttu-id="59a43-109">Skype for Business Server コントロール パネルを使用して実行できるさまざまな手順の詳細については [、「Skype for Business Server 2015](../../manage/manage.md)の管理」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="59a43-109">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>
  

