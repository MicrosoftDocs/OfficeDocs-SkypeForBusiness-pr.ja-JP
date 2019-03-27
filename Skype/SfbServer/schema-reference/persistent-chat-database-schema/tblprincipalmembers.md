---
title: tblPrincipalMembers
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
description: tblPrincipalMembers には、プリンシパルのメンバーシップが含まれています。
ms.openlocfilehash: 2b2b9616c76095ec27178887e69dd482bcf6da92
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874253"
---
# <a name="tblprincipalmembers"></a>tblPrincipalMembers
 
tblPrincipalMembers には、プリンシパルのメンバーシップが含まれています。
  
**列**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|prinID  <br/> |int 型、null でないです。  <br/> |プリンシパルの id。  <br/> |
|memberADPath  <br/> |nvarchar (384)、null でないです。  <br/> |メンバーの識別名です。 メンバーは (tblPrincipal のテーブル) 内の主体ではありません。  <br/> |
   
**キー**

|**列**|**説明**|
|:-----|:-----|
|\<prinID、memberADPath\>  <br/> |プライマリ ・ キーです。  <br/> |
|prinID  <br/> |TblPrincipal.prinID の検索での外部キー。  <br/> |
   

