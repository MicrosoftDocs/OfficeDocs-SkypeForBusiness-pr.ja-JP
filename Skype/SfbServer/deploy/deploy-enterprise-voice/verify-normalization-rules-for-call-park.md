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
# <a name="verify-normalization-rules-for-call-park-in-skype-for-business"></a>Skype for Business のコール パークの正規化ルールを確認する
 
Skype for Business Server エンタープライズ VoIP のコール パークの正規化ルールについて説明します。
  
コール パーク オービットを正規化する必要があります。 ダイヤル プランを確認して、オービット番号が正規化されていないことを確認します。 オービットが正規化されるのを防ぐために追加の正規化ルールを作成する必要がある場合は [、「Create or modify a dial plan in Skype for Business Server](dial-plans.md) to define a new normalization rule, so that Pattern to **match** identifies the orbit range and **Translation pattern** is **$1**. たとえば、コール パーク オービット範囲が 7000 ~ 7999 の場合、一致するパターンは **^(7\d {3} )$** で、**変換** パターンは **$1** です。 
  
> [!IMPORTANT]
> ダイヤル プランの既定の正規化ルールに **^(\d \* ) が含まれている必要があります**。 そうしないと、コール パーク正規化ルールは実行されません。
  
## <a name="see-also"></a>関連項目

[Skype for Business Server でダイヤル プランを作成または変更する](dial-plans.md)

