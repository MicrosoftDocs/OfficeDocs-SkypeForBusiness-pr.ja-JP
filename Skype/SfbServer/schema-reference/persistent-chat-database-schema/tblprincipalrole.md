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
ms.openlocfilehash: 13c9c25db9ba1dbe281947468bbd834e80417899
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831557"
---
# <a name="tblprincipalrole"></a>tblPrincipalRole
 
tblPrincipalRole には、ノードに割り当てられた明示的な役割が含まれます。
  
**Columns**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|prinRoleNodeID  <br/> |NULL でない int  <br/> |ロールが適用されるノード ID。  <br/> |
|prinRolePrinID  <br/> |NULL でない int  <br/> |プリンシパル ID。  <br/> |
|prinRoleTypeID  <br/> |NULL でない int  <br/> |ロールの種類 ID (tblRoleType から)。  <br/> |
|prinRoleUpdatedBy  <br/> |NULL でない int  <br/> |このエントリを最後に更新したプリンシパルの ID。  <br/> |
   
**Keys**

|**列**|**説明**|
|:-----|:-----|
|\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\>  <br/> |主キー。  <br/> |
|prinRoleNodeID  <br/> |tblNode.nodeID テーブル内の参照による外部キー。  <br/> |
|prinRolePrinID  <br/> |tblPrincipal.prinID テーブル内の参照による外部キー。  <br/> |
|prinRoleTypeID  <br/> |tblRoleType.rtypeID テーブルを参照する外部キー。  <br/> |
   

