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
# <a name="verify-normalization-rules-for-call-park-in-skype-for-business"></a>Skype for Business のコールパークの正規化ルールを確認する
 
Skype for Business Server Enterprise Voice のコールパークの正規化ルールについて説明します。
  
コールパーク orbits は正規化されていない必要があります。 ダイヤル プランでオービット番号が正規化されていないことを確認してください。 追加の正規化ルールを作成して、orbits が正規化されないようにする必要がある場合は、「 [Skype For Business Server のダイヤルプランを作成または変更](dial-plans.md)する」の手順に従って、新しい正規化ルールを定義し、**パターンが一致する**ようにします。オービット範囲と**翻訳パターン**が **$1**であることを示します。 たとえば、"Call パーク" というコールパーク範囲が 7000 ~ 7999 の場合、**照合するパターン**は **^ ({3}7 \ d) $** で、**翻訳パターン**は **$1**です。
  
> [!IMPORTANT]
> ダイヤルプランの既定の正規化ルールに **^ (\d\*)** が含まれていないことを確認します。 そうしないと、Call パークの正規化ルールは実行されません。
  
## <a name="see-also"></a>関連項目

[Skype for Business Server でダイヤルプランを作成または変更する](dial-plans.md)

