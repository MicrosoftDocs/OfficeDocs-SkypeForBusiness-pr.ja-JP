---
title: コール パークの正規化ルールをSkype for Business
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
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
ms.custom: null
ms.assetid: deaa170f-041e-45cb-8eab-f02931ab541e
description: コール パークの正規化ルールについては、Skype for Business Server エンタープライズ VoIP。
---

# <a name="verify-normalization-rules-for-call-park-in-skype-for-business"></a>コール パークの正規化ルールをSkype for Business
 
コール パークの正規化ルールについては、Skype for Business Server エンタープライズ VoIP。
  
コール パーク オービットは正規化しなけり。 ダイヤル プランを確認して、オービット番号が正規化されていないことを確認します。 オービットが正規化されるのを防ぐために追加の正規化ルールを作成する必要がある場合は、「[Skype for Business Server](dial-plans.md) でダイヤル プランを作成または変更する」の手順に従って新しい正規化ルールを定義し、一致するパターンがオービット範囲を識別し、変換パターンが **$1** です。 たとえば、コール パークオービット範囲が 7000 ~ 7999 の場合、一致するパターンは **^(7\d{3})$**、変換パターンは  **$1** です。
  
> [!IMPORTANT]
> ダイヤル プランの既定の正規化ルールに **^(\d) が含されていないことを確認\*します**。 それ以外の場合、コール パーク正規化ルールは実行されません。
  
## <a name="see-also"></a>関連項目

[ダイヤル プランを作成または変更するには、Skype for Business Server](dial-plans.md)

