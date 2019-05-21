---
title: tblPrincipalRole
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: tblPrincipalRole には、ノードに割り当てられている明示的な役割が含まれます。
ms.openlocfilehash: 9675713afba5753378f4d01b70489d0eee93b8bf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295238"
---
# <a name="tblprincipalrole"></a>tblPrincipalRole
 
tblPrincipalRole には、ノードに割り当てられている明示的な役割が含まれます。
  
**行**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|Prinrolid  <br/> |int (null ではない)  <br/> |役割が適用されるノード ID。  <br/> |
|prinRolePrinID  <br/> |int (null ではない)  <br/> |プリンシパル ID。  <br/> |
|prinRoleTypeID  <br/> |int (null ではない)  <br/> |役割の種類の ID (tblRoleType から)。  <br/> |
|prinroleupdat  <br/> |int (null ではない)  <br/> |このエントリを最後に更新したプリンシパルの ID です。  <br/> |
   
**機能**

|**列**|**説明**|
|:-----|:-----|
|\<Prinroldeid、prinRolePrinID、prinRoleTypeID\>  <br/> |主キー。  <br/> |
|Prinrolid  <br/> |TblNode テーブルで参照される外部キー。  <br/> |
|prinRolePrinID  <br/> |TblPrincipal Id テーブルで参照される外部キー。  <br/> |
|prinRoleTypeID  <br/> |TblRoleType の Typeid テーブルで参照される外部キー。  <br/> |
   

