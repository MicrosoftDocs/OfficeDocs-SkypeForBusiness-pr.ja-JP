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
description: tblPrincipalMemberDifference には、グループ メンバーシップの変更 (メンバーの追加と削除の両方) が含まれます。この変更は、Active Directory ドメイン サービスの同期の後の手順でまだ処理されていません。
ms.openlocfilehash: 8fac76f1abfbd55d13d89c96bb23a6953d38edf9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809707"
---
# <a name="tblprincipalmemberdifference"></a>tblPrincipalMemberDifference
 
tblPrincipalMemberDifference には、グループ メンバーシップの変更 (メンバーの追加と削除の両方) が含まれます。この変更は、Active Directory ドメイン サービスの同期の以降の手順でまだ処理されていません。
  
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
   

