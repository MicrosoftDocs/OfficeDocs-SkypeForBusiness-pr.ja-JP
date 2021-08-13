---
title: tblPrincipalAffiliations
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
ms.assetid: 45fd8484-5837-44d2-85bb-45c83546607c
description: tblPrincipalAffiliations には、Active Directory のドメイン コンテナー内の Active Directory ドメイン サービス セキュリティ グループを含む場所のメンバーシップを記述する主要な所属が含まれます。
ms.openlocfilehash: 5eb67681e5823b8549deb01b44e0bcb771e26882a2cd713d9cf598ae0670335b
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54341672"
---
# <a name="tblprincipalaffiliations"></a>tblPrincipalAffiliations
 
tblPrincipalAffiliations には、Active Directory のドメイン コンテナー内の Active Directory ドメイン サービス セキュリティ グループを含む場所のメンバーシップを記述する主要な所属が含まれます。
  
**Columns**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|principalID  <br/> |NULL でない int  <br/> |所属プリンシパルの ID。  <br/> |
|affiliationID  <br/> |NULL でない int  <br/> |所属を表すプリンシパルの ID。各プリンシパル (system-user-types 除く) には自己所属も含まれます。  <br/> |
|index  <br/> |NULL でない int  <br/> |インデックス。 自己所属の値は -1 で、他の所属の場合は、各バケット内の 1 から順番に増加 \<principalID, affiliationId\> します。  <br/> |
|updatedBy  <br/> |NULL でない int  <br/> |最新の更新を実行したプリンシパル。通常は、Active Directory の同期を意味する 1 です。  <br/> |
   
**Keys**

|**Columns**|**Description**|
|:-----|:-----|
|\<principalID, index, affiliationID\>  <br/> |主キー。  <br/> |
|principalID  <br/> |tblPrincipal.prinID テーブル内の参照による外部キー。  <br/> |
|affiliationID  <br/> |tblPrincipal.prinID テーブル内の参照による外部キー。  <br/> |
   

