---
title: tblPrincipalAffiliations
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 45fd8484-5837-44d2-85bb-45c83546607c
description: tblPrincipalAffiliations には、Active Directory ドメイン サービスのセキュリティ グループを含むドメイン内の Active Directory コンテナー内の場所でのメンバーシップを表すプリンシパルの所属が含まれています。
ms.openlocfilehash: c93edb552c63ebd4f7344926a7d43858b42506ae
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30897040"
---
# <a name="tblprincipalaffiliations"></a>tblPrincipalAffiliations
 
tblPrincipalAffiliations には、Active Directory ドメイン サービスのセキュリティ グループを含むドメイン内の Active Directory コンテナー内の場所でのメンバーシップを表すプリンシパルの所属が含まれています。
  
**列**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|principalID  <br/> |int 型、null でないです。  <br/> |関連のプリンシパルの ID です。  <br/> |
|affiliationID  <br/> |int 型、null でないです。  <br/> |所属を表すプリンシパルの ID です。 (システム ・ ユーザー ・ タイプ) を除く各主体が、自己の所属もします。  <br/> |
|インデックス  <br/> |int 型、null でないです。  <br/> |インデックスです。 自己所属の値は-1 になり、他の団体の順番に各 1 \<principalID、affiliationId\>バケットです。  <br/> |
|updatedBy  <br/> |int 型、null でないです。  <br/> |最新のアップデートを行った主体。 これは、通常、1 で、作業中のディレクトリ同期です。  <br/> |
   
**キー**

|**列**|**説明**|
|:-----|:-----|
|\<principalID、インデックス、affiliationID\>  <br/> |プライマリ ・ キーです。  <br/> |
|principalID  <br/> |TblPrincipal.prinID テーブル内の参照と外部キーです。  <br/> |
|affiliationID  <br/> |TblPrincipal.prinID テーブル内の参照と外部キーです。  <br/> |
   

