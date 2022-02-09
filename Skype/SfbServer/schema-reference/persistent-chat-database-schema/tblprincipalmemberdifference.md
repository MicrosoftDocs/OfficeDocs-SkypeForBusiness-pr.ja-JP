---
title: tblPrincipalMemberDifference
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 0b94f555-6888-4fe0-a048-4660a2513276
description: tblPrincipalMemberDifference には、後の Active Directory ドメイン サービス同期手順でまだ処理されていないグループ メンバーシップの変更 (追加メンバーと削除メンバーの両方) が含まれます。
ms.openlocfilehash: c52f1290eb0da442ffed9f8d8b645423b6f6c59c
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62410670"
---
# <a name="tblprincipalmemberdifference"></a>tblPrincipalMemberDifference
 
tblPrincipalMemberDifference には、後の Active Directory ドメイン サービス同期手順でまだ処理されていないグループ メンバーシップの変更 (追加メンバーと削除メンバーの両方) が含まれます。
  
**列**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|prinGuid  <br/> |NULL でない GUID  <br/> |変更されたグループのプリンシパル GUID。  <br/> |
|memberADPath  <br/> |nvarchar (256)  <br/> |メンバーの識別名。  <br/> |
|memberRemoved  <br/> |NULL でない bit  <br/> |メンバーが追加された場合は False。メンバーが削除された場合は True。  <br/> |
   
**キー**

|**列**|**説明**|
|:-----|:-----|
|\<prinGuid, memberADPath\>  <br/> |主キー。  <br/> |
   

