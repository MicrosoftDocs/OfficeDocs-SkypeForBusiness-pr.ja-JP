---
title: tblLastInviteId
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 222b3508-5963-4ddc-b4f3-e8412767e61b
description: tblLastInviteId には、各ユーザーに対して生成された (そして tblPrincipalInvites テーブルで使用された) 最後の招待 ID が格納されます。
ms.openlocfilehash: 56df4cf4002a67b665dfc33f1364493b07ac9ea7
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60855211"
---
# <a name="tbllastinviteid"></a>tblLastInviteId
 
tblLastInviteId には、各ユーザーに対して生成された (そして tblPrincipalInvites テーブルで使用された) 最後の招待 ID が格納されます。
  
**列**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|prinID  <br/> |NULL でない int  <br/> |プリンシパル ID。  <br/> |
|lastInviteID  <br/> |NULL でない int  <br/> |最後に使用された招待 ID。  <br/> |
   
**Keys**

|**列**|**説明**|
|:-----|:-----|
|prinID  <br/> |主キー。  <br/> |
|prinID  <br/> |tblPrincipal.prinID テーブル内の参照による外部キー。  <br/> |
   
## <a name="see-also"></a>関連項目

[tblPrincipalInvites](tblprincipalinvites.md)
