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
ms.localizationpriority: medium
ms.assetid: 0b94f555-6888-4fe0-a048-4660a2513276
description: tblPrincipalMemberDifference には、後の Active Directory ドメイン サービス同期手順でまだ処理されていないグループ メンバーシップの変更 (追加メンバーと削除メンバーの両方) が含まれます。
ms.openlocfilehash: c59e99ce43b6e0dfa5a41f4bfc515aa8a95ed958
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58601282"
---
# <a name="tblprincipalmemberdifference"></a>tblPrincipalMemberDifference
 
tblPrincipalMemberDifference には、後の Active Directory ドメイン サービス同期手順でまだ処理されていないグループ メンバーシップの変更 (追加メンバーと削除メンバーの両方) が含まれます。
  
**列**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|prinGuid  <br/> |NULL でない GUID  <br/> |変更されたグループのプリンシパル GUID。  <br/> |
|memberADPath  <br/> |nvarchar (256)  <br/> |メンバーの識別名。  <br/> |
|memberRemoved  <br/> |NULL でない bit  <br/> |メンバーが追加された場合は False。メンバーが削除された場合は True。  <br/> |
   
**Key**

|**列**|**説明**|
|:-----|:-----|
|\<prinGuid, memberADPath\>  <br/> |主キー。  <br/> |
   

