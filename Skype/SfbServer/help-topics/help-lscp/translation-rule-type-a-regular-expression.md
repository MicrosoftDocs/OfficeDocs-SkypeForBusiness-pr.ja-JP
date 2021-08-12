---
title: 変換ルール 正規表現を入力する
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
description: '[このパターンを照合] フィールドで、変換する番号を照合するために使用するパターンを指定します。 [変換ルール] フィールドで、変換される番号の形式のパターンを指定します。 たとえば、[このパターンの一致] フィールドに ^ (\d \d+)$ を入力し、[変換ルール] フィールドに \+ 011$1 を入力すると、ルールは +441235551010 から 011441235551010 に変換されます。 {9}'
ms.openlocfilehash: 294a179056455ee5d0d256bf6feeb1f39f52664fcf61d785649154f6c3290549
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54338335"
---
# <a name="translation-rule-type-a-regular-expression"></a>変換ルール: 正規表現の入力
 
[**このパターンを照合**] フィールドで、変換する番号を照合するために使用するパターンを指定します。 [**変換ルール**] フィールドで、変換される番号の形式のパターンを指定します。 たとえば、[このパターンの一致] フィールドに ^ (\d \d+)$ を入力し、[変換ルール] フィールドに \+ {9} 011$1を入力すると、ルールは +441235551010 を 011441235551010 に変換します。
  
コントロール パネルを使用して実行できるさまざまな手順の詳細については、「Skype for Business Server [2015」](../../manage/manage.md)を参照Skype for Business Serverしてください。
  

