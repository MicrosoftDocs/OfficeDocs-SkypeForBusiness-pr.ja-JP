---
title: tblLastInviteId
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 222b3508-5963-4ddc-b4f3-e8412767e61b
description: tblLastInviteId には、ユーザーごとに生成された (および tblPrincipalInvites テーブルで使用されている) 最後の招待 ID が含まれています。
ms.openlocfilehash: 977911150992b2e90b7dc344af0550a25ad77221
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30873938"
---
# <a name="tbllastinviteid"></a>tblLastInviteId
 
tblLastInviteId には、ユーザーごとに生成された (および tblPrincipalInvites テーブルで使用されている) 最後の招待 ID が含まれています。
  
**列**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|prinID  <br/> |int 型、null でないです。  <br/> |プリンシパルの id。  <br/> |
|lastInviteID  <br/> |int 型、null でないです。  <br/> |最後の使用への招待の id。  <br/> |
   
**キー**

|**列**|**説明**|
|:-----|:-----|
|prinID  <br/> |プライマリ ・ キーです。  <br/> |
|prinID  <br/> |TblPrincipal.prinID テーブル内の参照と外部キーです。  <br/> |
   
## <a name="see-also"></a>関連項目

[tblPrincipalInvites](tblprincipalinvites.md)
