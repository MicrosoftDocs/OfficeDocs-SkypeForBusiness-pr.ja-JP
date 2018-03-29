---
title: tblPrincipalRole
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: tblPrincipalRole には、ノードに割り当てられている、明確な役割が含まれています。
ms.openlocfilehash: 0e6c7f60f372bc14542567ccaa1b1b1a837c6c6d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="tblprincipalrole"></a>tblPrincipalRole
 
tblPrincipalRole には、ノードに割り当てられている、明確な役割が含まれています。
  
**列**

|**列**|**タイプ**|**説明**|
|:-----|:-----|:-----|
|prinRoleNodeID  <br/> |int 型、null でないです。  <br/> |ロールに適用するノードの ID。  <br/> |
|prinRolePrinID  <br/> |int 型、null でないです。  <br/> |プリンシパルの id。  <br/> |
|prinRoleTypeID  <br/> |int 型、null でないです。  <br/> |(TblRoleType) からの役割の種類の ID です。  <br/> |
|prinRoleUpdatedBy  <br/> |int 型、null でないです。  <br/> |このエントリを最後に更新したプリンシパルの ID です。  <br/> |
   
**キー**

|**列**|**説明**|
|:-----|:-----|
|\<prinRoleNodeID、prinRolePrinID、prinRoleTypeID\>  <br/> |プライマリ ・ キーです。  <br/> |
|prinRoleNodeID  <br/> |TblNode.nodeID テーブル内の参照と外部キーです。  <br/> |
|prinRolePrinID  <br/> |TblPrincipal.prinID テーブル内の参照と外部キーです。  <br/> |
|prinRoleTypeID  <br/> |TblRoleType.rtypeID テーブル内の参照と外部キーです。  <br/> |
   

