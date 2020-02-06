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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: tblPrincipalRole には、ノードに割り当てられている明示的な役割が含まれます。
ms.openlocfilehash: 1cc606ec3825bb664d4123154e97fabb15678cfd
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813365"
---
# <a name="tblprincipalrole"></a>tblPrincipalRole
 
tblPrincipalRole には、ノードに割り当てられている明示的な役割が含まれます。
  
**行**

|**列**|**種類**|**説明**|
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
   

