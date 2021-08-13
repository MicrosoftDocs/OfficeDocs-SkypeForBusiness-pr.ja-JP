---
title: tblPrincipalRole
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: tblPrincipalRole には、ノードに割り当てられた明示的な役割が含まれます。
ms.openlocfilehash: 28e639a4894b89e449a70fc527b7c4315be57403e15bb582bcdae3933e3790a7
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54336387"
---
# <a name="tblprincipalrole"></a>tblPrincipalRole
 
tblPrincipalRole には、ノードに割り当てられた明示的な役割が含まれます。
  
**Columns**

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
   

