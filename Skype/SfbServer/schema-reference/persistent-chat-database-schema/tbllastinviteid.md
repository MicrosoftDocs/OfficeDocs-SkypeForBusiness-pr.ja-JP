---
title: tblLastInviteId
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
ms.openlocfilehash: 5f94714bfe42d6777907f3ce3e467e4add7a00d8
ms.sourcegitcommit: b14cfca231b618ec28cf9f4efe11cb3e8aceb34b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2018
ms.locfileid: "19504853"
---
# <a name="tbllastinviteid"></a>tblLastInviteId
 
tblLastInviteId には、ユーザーごとに生成された (および tblPrincipalInvites テーブルで使用されている) 最後の招待 ID が含まれています。
  
**列**

|**列**|**種類**|**説明**|
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