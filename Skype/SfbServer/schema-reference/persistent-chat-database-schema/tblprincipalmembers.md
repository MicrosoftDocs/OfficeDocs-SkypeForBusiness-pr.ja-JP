---
title: tblPrincipalMembers
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
ms.assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
description: tblPrincipalMembers には、プリンシパル メンバーシップが含まれています。
ms.openlocfilehash: 93a012ea82acf071a28752eb79682866c0faa418
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831597"
---
# <a name="tblprincipalmembers"></a>tblPrincipalMembers
 
tblPrincipalMembers には、プリンシパル メンバーシップが含まれています。
  
**Columns**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|prinID  <br/> |NULL でない int  <br/> |プリンシパル ID。  <br/> |
|memberADPath  <br/> |NULL でない nvarchar (384)  <br/> |メンバーの識別名。メンバーは (tblPrincipal テーブル内の) プリンシパルでなくてもかまいません。  <br/> |
   
**Keys**

|**列**|**説明**|
|:-----|:-----|
|\<prinID, memberADPath\>  <br/> |主キー。  <br/> |
|prinID  <br/> |tblPrincipal.prinID の検索に使用する外部キー。  <br/> |
   

