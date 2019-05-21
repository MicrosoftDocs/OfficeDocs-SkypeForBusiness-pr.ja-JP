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
localization_priority: Normal
ms.assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
description: tblPrincipalMembers にプリンシパルメンバーシップが含まれています。
ms.openlocfilehash: 12c3bf86b7416665f0f2355af0bfc9f98e3c1f1a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295287"
---
# <a name="tblprincipalmembers"></a>tblPrincipalMembers
 
tblPrincipalMembers にプリンシパルメンバーシップが含まれています。
  
**行**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|prinID  <br/> |int (null ではない)  <br/> |プリンシパル ID。  <br/> |
|memberADPath  <br/> |nvarchar (384)、null ではない  <br/> |メンバーの識別名。 メンバーは、プリンシパル (tblPrincipal テーブル内) である必要はありません。  <br/> |
   
**機能**

|**列**|**説明**|
|:-----|:-----|
|\<prinID、memberADPath\>  <br/> |主キー。  <br/> |
|prinID  <br/> |TblPrincipal Id で参照する外部キー。  <br/> |
   

