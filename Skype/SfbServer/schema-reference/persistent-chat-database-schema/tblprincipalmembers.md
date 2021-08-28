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
ms.localizationpriority: medium
ms.assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
description: tblPrincipalMembers には、プリンシパル メンバーシップが含まれています。
ms.openlocfilehash: e35b64a34114a7135133175211ecec5a806332b6
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58626459"
---
# <a name="tblprincipalmembers"></a>tblPrincipalMembers
 
tblPrincipalMembers には、プリンシパル メンバーシップが含まれています。
  
**列**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|prinID  <br/> |NULL でない int  <br/> |プリンシパル ID。  <br/> |
|memberADPath  <br/> |NULL でない nvarchar (384)  <br/> |メンバーの識別名。メンバーは (tblPrincipal テーブル内の) プリンシパルでなくてもかまいません。  <br/> |
   
**Keys**

|**列**|**説明**|
|:-----|:-----|
|\<prinID, memberADPath\>  <br/> |主キー。  <br/> |
|prinID  <br/> |tblPrincipal.prinID の検索に使用する外部キー。  <br/> |
   

