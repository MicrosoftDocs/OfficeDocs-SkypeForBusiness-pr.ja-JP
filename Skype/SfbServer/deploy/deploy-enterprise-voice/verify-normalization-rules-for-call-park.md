---
title: コール パークの正規化ルールをSkype for Business
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
description: コール パークの正規化ルールについては、Skype for Business Server エンタープライズ VoIP。
ms.openlocfilehash: 5c357a9ff9b2174ae414e1e4511cb7ebf267e19787091e19ce27f75f90b8a51e
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54298617"
---
# <a name="verify-normalization-rules-for-call-park-in-skype-for-business"></a>コール パークの正規化ルールをSkype for Business
 
コール パークの正規化ルールについては、Skype for Business Server エンタープライズ VoIP。
  
コール パーク オービットは正規化しなけり。 ダイヤル プランを確認して、オービット番号が正規化されていないことを確認します。 オービットが正規化されるのを防ぐために追加の正規化ルールを作成する必要がある場合は [、「Skype for Business Server](dial-plans.md)でダイヤル プランを作成または変更する」の手順に従って新しい正規化ルールを定義し、一致するパターンがオービット範囲を識別し、変換パターンが **$1** です。 たとえば、コール パーク オービット範囲が 7000 ~ 7999 の場合、一致するパターンは **^(7\d {3} )$** で、変換パターンは **$1** です。  
  
> [!IMPORTANT]
> ダイヤル プランの既定の正規化ルールに **^(\d ) が含されていないことを確認 \* します**。 それ以外の場合、コール パーク正規化ルールは実行されません。
  
## <a name="see-also"></a>関連項目

[ダイヤル プランを作成または変更するには、Skype for Business Server](dial-plans.md)

