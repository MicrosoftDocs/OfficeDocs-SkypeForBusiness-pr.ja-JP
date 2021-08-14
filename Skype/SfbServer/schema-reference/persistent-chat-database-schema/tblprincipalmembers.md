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
ms.openlocfilehash: 4b7ab1ca644fae9d6cf3029e555c7bdaf476a3e5113634a4c73fd1778bc3a0dd
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54346343"
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
   

