---
title: tblPrincipalRole
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: tblPrincipalRole には、ノードに割り当てられた明示的な役割が含まれます。
ms.openlocfilehash: 3c4af0f5022afc25212c50b44ff19c28946df97d
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62399571"
---
# <a name="tblprincipalrole"></a>tblPrincipalRole
 
tblPrincipalRole には、ノードに割り当てられた明示的な役割が含まれます。
  
**列**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|prinRoleNodeID  <br/> |NULL でない int  <br/> |役割が適用されるノード ID。  <br/> |
|prinRolePrinID  <br/> |NULL でない int  <br/> |プリンシパル ID。  <br/> |
|prinRoleTypeID  <br/> |NULL でない int  <br/> |役割の種類 ID (tblRoleType から)。  <br/> |
|prinRoleUpdatedBy  <br/> |NULL でない int  <br/> |このエントリを最後に更新したプリンシパルの ID。  <br/> |
   
**Keys**

|**列**|**説明**|
|:-----|:-----|
|\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\>  <br/> |主キー。  <br/> |
|prinRoleNodeID  <br/> |tblNode.nodeID テーブル内の参照による外部キー。  <br/> |
|prinRolePrinID  <br/> |tblPrincipal.prinID テーブル内の参照による外部キー。  <br/> |
|prinRoleTypeID  <br/> |tblRoleType.rtypeID テーブル内の参照を含む外部キー。  <br/> |
   

