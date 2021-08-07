---
title: tblPrincipalMemberDifference
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
ms.assetid: 0b94f555-6888-4fe0-a048-4660a2513276
description: tblPrincipalMemberDifference には、後の Active Directory ドメイン サービス同期手順でまだ処理されていないグループ メンバーシップの変更 (追加メンバーと削除メンバーの両方) が含まれます。
ms.openlocfilehash: c1d5a0d492d228b5a8292fde608fbd66c3b586c393aba8eb5bc0fbbddd45a5e2
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54276582"
---
# <a name="tblprincipalmemberdifference"></a>tblPrincipalMemberDifference
 
tblPrincipalMemberDifference には、後の Active Directory ドメイン サービス同期手順でまだ処理されていないグループ メンバーシップの変更 (追加メンバーと削除メンバーの両方) が含まれます。
  
**Columns**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|prinGuid  <br/> |NULL でない GUID  <br/> |変更されたグループのプリンシパル GUID。  <br/> |
|memberADPath  <br/> |nvarchar (256)  <br/> |メンバーの識別名。  <br/> |
|memberRemoved  <br/> |NULL でない bit  <br/> |メンバーが追加された場合は False。メンバーが削除された場合は True。  <br/> |
   
**キー**

|**列**|**説明**|
|:-----|:-----|
|\<prinGuid, memberADPath\>  <br/> |主キー。  <br/> |
   

