---
title: tblPrincipalMembers
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
ms.assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
description: tblPrincipalMembers にプリンシパルメンバーシップが含まれています。
ms.openlocfilehash: c56ab16f96322cb295c4eff6fc63e01ba887dd22
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813945"
---
# <a name="tblprincipalmembers"></a>tblPrincipalMembers
 
tblPrincipalMembers にプリンシパルメンバーシップが含まれています。
  
**行**

|**列**|**種類**|**説明**|
|:-----|:-----|:-----|
|prinID  <br/> |int (null ではない)  <br/> |プリンシパル ID。  <br/> |
|memberADPath  <br/> |nvarchar (384)、null ではない  <br/> |メンバーの識別名。 メンバーは、プリンシパル (tblPrincipal テーブル内) である必要はありません。  <br/> |
   
**機能**

|**列**|**説明**|
|:-----|:-----|
|\<prinID、memberADPath\>  <br/> |主キー。  <br/> |
|prinID  <br/> |TblPrincipal Id で参照する外部キー。  <br/> |
   

