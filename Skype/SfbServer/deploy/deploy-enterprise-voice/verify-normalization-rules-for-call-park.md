---
title: コール パークの正規化ルールをSkype for Business
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: deaa170f-041e-45cb-8eab-f02931ab541e
description: コール パークの正規化ルールについては、Skype for Business Server エンタープライズ VoIP。
ms.openlocfilehash: ca76c15d7f71afa75e9b9247eab9cd96e5baedb0
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60771532"
---
# <a name="verify-normalization-rules-for-call-park-in-skype-for-business"></a>コール パークの正規化ルールをSkype for Business
 
コール パークの正規化ルールについては、Skype for Business Server エンタープライズ VoIP。
  
コール パーク オービットは正規化しなけり。 ダイヤル プランを確認して、オービット番号が正規化されていないことを確認します。 オービットが正規化されるのを防ぐために追加の正規化ルールを作成する必要がある場合は [、「Skype for Business Server](dial-plans.md)でダイヤル プランを作成または変更する」の手順に従って新しい正規化ルールを定義し、一致するパターンがオービット範囲を識別し、変換パターンが **$1** です。 たとえば、コール パーク オービット範囲が 7000 ~ 7999 の場合、一致するパターンは **^(7\d {3} )$** で、変換パターンは **$1** です。  
  
> [!IMPORTANT]
> ダイヤル プランの既定の正規化ルールに **^(\d ) が含されていないことを確認 \* します**。 それ以外の場合、コール パーク正規化ルールは実行されません。
  
## <a name="see-also"></a>関連項目

[ダイヤル プランを作成または変更するには、Skype for Business Server](dial-plans.md)

