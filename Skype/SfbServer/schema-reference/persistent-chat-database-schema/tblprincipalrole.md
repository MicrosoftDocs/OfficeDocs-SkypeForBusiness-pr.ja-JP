---
title: tblPrincipalRole
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: tblPrincipalRole には、ノードに割り当てられている、明確な役割が含まれています。
ms.openlocfilehash: 7c144f2f531af58c7c5693b28b224a2ee4456783
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33904182"
---
# <a name="tblprincipalrole"></a>tblPrincipalRole
 
tblPrincipalRole には、ノードに割り当てられている、明確な役割が含まれています。
  
**列**

|**列**|**型**|**説明**|
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
   

