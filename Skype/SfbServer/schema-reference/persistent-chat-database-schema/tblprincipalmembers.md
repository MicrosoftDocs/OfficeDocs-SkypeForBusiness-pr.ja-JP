---
title: tblPrincipalMembers
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
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
ms.openlocfilehash: 130ca3cc7f57435f95add202f6af13660bf71610
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60842609"
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
   

